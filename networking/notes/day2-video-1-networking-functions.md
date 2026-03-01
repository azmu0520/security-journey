# 2-kun — Video #4: Networking Functions (13:25)

**Sana:** 2026-03-01
**Video:** #4 Networking Functions
**Manba:** Professor Messer N10-009

---

## Umumiy Manzara

Tarmoq kabelining ichiga kirib, u yerda nima ketayotganini ko'rsang — ko'plab turli funksiyalar ishlayotganini ko'rasan. Ma'lumotni dunyoning narigi chekkasiga yetkazish, ekranni ulashish, trafikni boshqarish, tizimlarni doimiy ishlab turishi — bularning har biri o'z protokoli va mexanizmi bor.

---

## CDN — Content Delivery Network

- Markaziy serverdan foydalanuvchiga ma'lumotni **tez va samarali** yetkazish tizimi
- Geografik joylarga bo'lingan: Shimoliy Amerika, Janubiy Amerika, Afrika, Osiyo va boshqalar
- Har bir CDN serverida ma'lumot **keshlanadi (cached)** — shu hududdagi foydalanuvchilar uzoqdagi asosiy serverga bormaydi
- YouTube va Professor Messer saytini ko'rayotgan bo'lsang — hozir CDN ishlatayapsan

> Xavfsizlik nuqtai nazaridan: CDN hujum yuzasini kengaytiradi — CDN serverlarini nishonga olish ham real hujum vektori

---

## VPN — Virtual Private Network

- Uzoq tarmoqqa **shifrlangan tunnel** orqali ulanish
- Ochiq internet kabi xavfli tarmoqlar orqali ham xavfsiz ma'lumot uzatadi
- **VPN Concentrator (Head-end device):**
  - Ko'plab foydalanuvchilarning VPN ulanishlarini bir joyda boshqaradi
  - Real vaqtda tez encryption/decryption qilish uchun maxsus qurilma
  - Yuzlab yoki minglab foydalanuvchini bir vaqtda qo'llab-quvvatlaydi
  - Ko'pincha **NGFW ichiga integratsiya qilingan** — alohida qurilma emas
- Kichik tarmoqlarda: software VPN concentrator yetarli
- Windows, macOS, Linux — o'zida VPN software bor, maxsus dastur shart emas

---

## QoS — Quality of Service

- Ba'zi ilovalar boshqalardan **muhimroq** — masalan, real-vaqt video/audio > fayl ko'chirish
- QoS = **traffic shaping / packet shaping** — tarmoq administratori ilovalar prioritetini belgilaydi
- Bandwidth yoki data rate asosida boshqariladi
- Qayerda sozlanadi: **firewall, router yoki switch** ichida
- Qurilmalar ilovalar ro'yxatiga ega bo'ladi, o'z ilovangni ham qo'sha olasan

---

## TTL — Time to Live

### Nima uchun kerak?

Texnologiya biror vazifani **to'xtovsiz, cheksiz** bajarib ketishi mumkin — bu muammo. TTL — bu vazifaga **tugash vaqti** berish mexanizmi.

### IP Packetlarda TTL (Hop asosida)

- Har bir router packet ni qayta ishlayotganda TTL ni **1 ga kamaytiradi**
- TTL = 0 ga yetganda — router packet ni **o'chirib tashlaydi**
- Default TTL qiymatlari:

| OS            | Default TTL |
| ------------- | ----------- |
| macOS / Linux | 64 hop      |
| Windows       | 128 hop     |

- Odatda internet bo'ylab 12–16 hop yetarli — shuning uchun 64/128 xavfsiz chegara

### Routing Loop muammosi

```
Router A → Router B → Router A → Router B → ...
```

- Router A keyingi hop = Router B deb o'ylaydi
- Router B keyingi hop = Router A deb o'ylaydi
- Packet cheksiz aylanadi — TTL bo'lmasa tarmoq tiqilib qoladi
- `traceroute` da ko'rsang: `10.1.10.1 → 10.2.10.2 → 10.1.10.1 → ...` — bu routing loop

### DNS da TTL (Sekund asosida)

- IP packet TTL = **hop soni** asosida
- DNS TTL = **sekund** asosida — farqni bil!
- `dig www.professormesser.com` — Answer Section da TTL = **300 sekund (5 daqiqa)**
- Ma'nosi: shu IP manzilni **5 daqiqa keshda saqla**, keyin yangi DNS query qil
- Administrator DNS da IP ni o'zgartirsa — 5 daqiqa ichida hamma yangi manzilni oladi

### TTL Wireshark da

IPv4 header ichida `Time to Live` field — packet decode da ko'rinadi:

```
Internet Protocol Version 4
  Time to Live: 58
  Source: 192.168.x.x
  Destination: 72.14.x.x
```

TTL = 58 — demak bu packet yana 58 ta routerdan o'ta oladi

---

## Chalkashtirgani / Qayta ko'rib chiqmoqchi

- [ ] TTL har protokolda boshqacha o'lchanadi — boshqa qanday protokollarda TTL bor va u qanday o'lchanadi?
- [ ] VPN Concentrator va NGFW birgalikda bo'lganda — encryption/decryption kim qiladi, performance ga ta'siri bormi?
- [ ] Routing loop — statik route xatosidan kelib chiqadi deyildi, lekin dinamik routing protokollar (OSPF, BGP) loopni o'zi oldini oladimi?

---

## Asosiy Atamalar

- **CDN** — Content Delivery Network, geografik taqsimlangan kesh serverlari
- **VPN** — Virtual Private Network, shifrlangan tunnel orqali uzoq tarmoqqa ulanish
- **VPN Concentrator** — ko'plab VPN ulanishlarini boshqaradigan markaziy qurilma
- **QoS** — Quality of Service, ilovalar uchun tarmoq prioritetini belgilash
- **Traffic shaping** — QoS ning boshqa nomi, bandwidth boshqaruvi
- **TTL** — Time to Live; IP da hop soni, DNS da sekund
- **Routing loop** — ikki router bir-birini keyingi hop deb ko'rsatishi, TTL to'xtatadi
- **Default TTL** — macOS/Linux: 64, Windows: 128

---
