# 3-kun — Video #9: Boshqa Foydali Protokollar (8:26)

**Sana:** 2026-03-03
**Video:** #9 Other Useful Protocols
**Manba:** Professor Messer N10-009

---

## Umumiy Manzara

Bu video uchta muhim protokolni qamrab oladi — ICMP, GRE va IPSec.
Bularning har biri tarmoqda turli vazifa bajaradi:
ICMP = tarmoqni tekshirish, GRE = tunnel yaratish, IPSec = tunnel ni shifrlash.

---

## ICMP — Internet Control Message Protocol

### Bu nima?

Tarmoqdagi qurilma "ishlamoqdami?" deb so'rash usuli.
Xuddi do'stingga SMS yuborib javob kutish kabi.

- TCP yoki UDP dan foydalanilmaydi — **o'zining alohida protokoli bor**
- IP tomonidan tashiladi lekin transport layer da emas
- Asosan **ping** buyrug'i orqali tanilgan

### ICMP nima qila oladi?

| Vazifasi                                       | Misol                                              |
| ---------------------------------------------- | -------------------------------------------------- |
| Qurilma ishlayotganini tekshirish              | `ping 8.8.8.8`                                     |
| Tarmoq ishlamayotganini xabar qilish           | "Network unreachable" xabari                       |
| TTL (yaroqlik muddati) tugaganini xabar qilish | "Time exceeded" xabari — routing loop da ko'rinadi |

> Xavfsizlik nuqtai nazaridan: ba'zi hackerlar ICMP ni
> tarmoq xaritasini tuzish uchun ishlatadi — qaysi hostlar tirik,
> qaysi portlar ochiq. Shu sabab ko'p firewall lar ICMP ni bloklaydi.
> `ping` ishlamasa — qurilma o'chiq degani emas,
> shunchaki ICMP bloklangandir.

---

## GRE — Generic Routing Encapsulation

### Bu nima?

Ikki nuqta orasida **tunnel** yaratish protokoli.
Packet ni boshqa packet ichiga o'raydi — xuddi konvert ichiga konvert kabi.

- IP packet ni boshqa IP packet ichiga encapsulate qiladi
- Tunnel orqali yuboradi, narigi tomonda decapsulate qiladi
- **Lekin shifrlash yo'q** — faqat tunnel, xavfsiz emas

### GRE + VPN birgalikda

```
GRE = tunnel (yo'l ochadi)
IPSec = encryption (yo'lni xavfsiz qiladi)
GRE + IPSec = xavfsiz tunnel
```

> GRE ni kanalga o'xshatsa bo'ladi — ma'lumot ichidan o'tadi
> lekin kim ko'rsa o'qiy oladi. IPSec qo'shsang —
> kanal qoraytirilgan oynali bo'ladi, hech kim ichini ko'ra olmaydi.

---

## IPSec — Internet Protocol Security

### Bu nima?

VPN tunnel orqali yuboriladigan ma'lumotni **shifrlash standarti**.
Eng mashhur va keng qo'llaniladigan VPN encryption protokoli.

Faqat shifrlash emas, uchta narsa beradi:

| Xususiyat           | Ma'nosi                                                    |
| ------------------- | ---------------------------------------------------------- |
| **Confidentiality** | Ma'lumot shifrlangan — hech kim o'qiy olmaydi              |
| **Integrity**       | Har bir packet digital signature ga ega — o'zgartirilmagan |
| **Anti-replay**     | Eski packet larni qayta yuborib hujum qilib bo'lmaydi      |

> Turli ishlab chiqaruvchilar orasida ishlaydi —
> bir tomonda Cisco firewall, narigi tomonda Palo Alto firewall bo'lsa ham,
> ikkalasi IPSec orqali muloqot qila oladi.

---

## IPSec qanday ishlaydi — bosqichma-bosqich

### 1-bosqich — IKE Phase 1 (Tunnel o'rnatish)

- **IKE** = Internet Key Exchange
- Ikki tomon encryption kalitlari haqida kelishadi
- Bu kelishuv **Security Association (SA)** deb ataladi
- **Diffie-Hellman** algoritmi orqali shared secret key yaratiladi
- **UDP port 500** ishlatadi
- Bu tunnel **ISAKMP tunnel** deb ataladi

### 2-bosqich — IKE Phase 2 (Ma'lumot yuborish)

- Qaysi cipher va key size ishlatilishi kelishiladi
- Inbound va outbound SA lar sozlanadi
- Haqiqiy ma'lumot **ESP tunnel** orqali yuboriladi

```
Phase 1: ISAKMP tunnel — UDP 500 — kalit almashinuvi
Phase 2: ESP tunnel — haqiqiy shifrlangan ma'lumot
```

---

## IPSec — Transport Mode vs Tunnel Mode

### Transport Mode

```
[ IP Header | IPSec Header | SHIFRLANGAN DATA | IPSec Trailer ]
```

- Faqat malumot shifrlangan
- Original IP header **ochiq** qoladi
- Hacker packet ni ushlasa — manzilni ko'ra oladi, lekin ichini ko'ra olmaydi

### Tunnel Mode

```
[ YANGI IP Header | IPSec Header | SHIFRLANGAN (Original IP + Data) | IPSec Trailer ]
```

- Original IP header **ham** shifrlangan
- Hacker hech narsani ko'ra olmaydi — na manzil, na data
- Yangi IP header faqat VPN concentrator manzilini ko'rsatadi
- **Ko'p hollarda Tunnel Mode ishlatiladi** — ancha xavfsizroq

---

## IPSec — AH vs ESP

|                     | AH (Authentication Header)         | ESP (Encapsulation Security Payload)     |
| ------------------- | ---------------------------------- | ---------------------------------------- |
| Shifrlash           | ❌ Yo'q                            | ✅ Ha                                    |
| Integrity tekshiruv | ✅ Ha                              | ✅ Ha                                    |
| Authentication      | ✅ Ha                              | ✅ Ha                                    |
| Amalda ishlatilishi | Kam — faqat integrity kerak bo'lsa | Ko'p — shifrlash ham integrity ham kerak |

> Amalda deyarli har doim **ESP** ishlatiladi.
> AH faqat "ma'lumot o'zgartirilmadimi?" ni tekshiradi, lekin
> shunda ham uni barcha oqiy oladi. ESP esa ikkalasini ham qiladi.

---

## Hammasi Birgalikda — Real Misol

```
Ofis A (Varshava) ←→ Internet ←→ Ofis B (London)
     Firewall                          Firewall
        |                                  |
        └──── GRE Tunnel ─────────────────┘
        └──── IPSec (ESP, Tunnel Mode) ───┘
              UDP 500 — kalit almashinuvi
```

1. Ofis A dagi firewall GRE tunnel ochadi
2. IPSec IKE orqali UDP 500 da kalit almashinuvi qiladi
3. Ma'lumot ESP orqali tunnel mode da shifrlanadi
4. Internet orqali ketadi — hech kim o'qiy olmaydi
5. Ofis B dagi firewall decapsulate va decrypt qiladi

---

## Asosiy Atamalar

- **ICMP** — Internet Control Message Protocol, `ping` ishlatadigan protokol, TCP/UDP ishlatmaydi
- **GRE** — Generic Routing Encapsulation, tunnel yaratadi, shifrlash yo'q
- **IPSec** — Internet Protocol Security, VPN encryption standarti
- **IKE** — Internet Key Exchange, IPSec tunnel o'rnatish jarayoni
- **SA** — Security Association, ikki tomon orasidagi encryption kelishuvi
- **ISAKMP** — kalit almashinuvi tunnel, UDP 500
- **Diffie-Hellman** — ikki tomon uchun shared secret key yaratish algoritmi
- **AH** — Authentication Header, integrity bor lekin shifrlash yo'q
- **ESP** — Encapsulation Security Payload, shifrlash ham integrity ham bor
- **Transport Mode** — faqat data shifrlangan, IP header ochiq
- **Tunnel Mode** — hammasi shifrlangan, yangi IP header qo'shiladi

---

_Keyingi: Video #10 — Network Communication_
