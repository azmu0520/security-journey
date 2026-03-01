# 2-kun — Video #7: IP ga Kirish (14:10)

**Sana:** 2026-03-01
**Video:** #7 Introduction to IP
**Manba:** Professor Messer N10-009

---

## Umumiy Manzara

IP ning maqsadi oddiy: ma'lumotni bir qurilmadan ikkinchisiga yetkazish.
Buni tushunishni osonlashtiruvchi taqqoslash — **ko'chish yuki mashinasi.**

| Taqqoslash                | Tarmoq haqiqati              |
| ------------------------- | ---------------------------- |
| Yo'l / asfalt             | Tarmoq (Ethernet, WiFi, WAN) |
| Yuk mashina               | Internet Protocol (IP)       |
| Mashinadagi qutular       | TCP yoki UDP segmentlari     |
| Qutilar ichidagi narsalar | Ilova ma'lumotlari           |
| Manzil                    | IP address                   |
| Uydagi xona               | Port raqami                  |

---

## Ethernet Frame Tuzilmasi

Tarmoqdagi har bir packet shunday ko'rinadi:

```
[ Ethernet Header | IP Header | TCP/UDP Header | App Data | Ethernet Trailer ]
```

- **Ethernet Header** → MAC manzillar (L2)
- **IP Header** → IP manzillar (L3)
- **TCP/UDP Header** → port raqamlar (L4)
- **App Data** → HTTP, email, ovoz va boshqalar (L7)
- **Ethernet Trailer** → xatolarni tekshirish (FCS)

Bu encapsulation — har bir qatlam o'zidan yuqorisini o'raydi.

---

## TCP va UDP

Ikkalasi ham **OSI Layer 4 — Transport** da ishlaydi.
Ikkalasi ham qurilmalar orasida ma'lumot uzatadi.
Farqi — **qanday qilishida.**

| Xususiyat          | TCP                                      | UDP                          |
| ------------------ | ---------------------------------------- | ---------------------------- |
| Ulanish o'rnatish  | Rasmiy (3-bosqichli)                     | Yo'q                         |
| Tasdiqlash (ACK)   | Ha — ishonchli yetkazish                 | Yo'q — ishonchsiz            |
| Xatolarni tiklash  | Ha — yo'qolgan ma'lumotni qayta yuboradi | Yo'q                         |
| Oqim nazorati      | Ha — tezlashtir / sekinlashtir           | Yo'q                         |
| Tartibli packetlar | Ha — raqamlangan                         | Yo'q                         |
| Tezlik             | Sekinroq (qo'shimcha yuklar bor)         | Tezroq (qo'shimcha yuk yo'q) |
| Qo'llanilishi      | Web, email, fayl uzatish                 | VoIP, video streaming, DNS   |

> "Ishonchsiz" buzilgan degani emas — UDP yetkazish ehtimoli TCP bilan bir xil.
> Faqat tasdiqlash yo'q, qayta yuborish yo'q, kafolat yo'q.

### Multiplexing

Bir vaqtda bir xil ikki qurilma orasida bir nechta ilovani ishlatish.
Brauzer, email va Spotify bir vaqtda ishlashi shu sabab — har birining port raqami boshqacha.

---

## Port Raqamlar

IP manzil = qaysi uyga yetkazish.
Port raqam = o'sha uy ichidagi qaysi xona.

### Port Diapazlari

| Diapazon       | Turi                         | Kim ishlatadi                    |
| -------------- | ---------------------------- | -------------------------------- |
| 0 – 1,023      | **Non-ephemeral** (doimiy)   | Serverlar / mashhur xizmatlar    |
| 1,024 – 65,535 | **Ephemeral** (vaqtinchalik) | Klientlar / tasodifiy sessiyalar |

### Mashhur Port Raqamlar — Yodla

| Port | Protokol | Xizmat       |
| ---- | -------- | ------------ |
| 80   | TCP      | HTTP         |
| 443  | TCP      | HTTPS        |
| 22   | TCP      | SSH          |
| 25   | TCP      | SMTP (email) |
| 143  | TCP      | IMAP (email) |
| 53   | TCP/UDP  | DNS          |
| 123  | UDP      | NTP (vaqt)   |
| 5004 | UDP      | VoIP (RTP)   |

> Muhim: TCP port 80 ≠ UDP port 80. Bir xil raqam, boshqa protokol, boshqa port.
> Port raqamini o'zgartirish xavfsizlik chorasi EMAS — firewall kerak.

---

## Socket — To'liq Ulanish Qanday Aniqlanadi

**Socket** = IP manzil + protokol (TCP/UDP) + port raqami

Misol — 10.0.0.1 klient 10.0.0.2 serverga murojaat qilmoqda:

```
Klient socket:  10.0.0.1 : TCP : 3000   (ephemeral — tasodifiy)
Server socket:  10.0.0.2 : TCP : 80     (non-ephemeral — mashhur)
```

Bir vaqtda uchta ilova ishlayapti:

| Ilova | Protokol | Server Port | Klient Port      |
| ----- | -------- | ----------- | ---------------- |
| Web   | TCP      | 80          | 3000 (tasodifiy) |
| VoIP  | UDP      | 5004        | 7100 (tasodifiy) |
| Email | TCP      | 143         | 4407 (tasodifiy) |

Server javob berganda — manba/manzil IP va port larni shunchaki almashtiradi.

---

## Asosiy Atamalar

- **IP** — Internet Protocol, tarmoq bo'ylab ma'lumot uzatadi (yuk mashina)
- **TCP** — Transmission Control Protocol, ishonchli, ulanishga asoslangan, Layer 4
- **UDP** — User Datagram Protocol, tez, ulanuvsiz, tasdiqlash yo'q, Layer 4
- **Encapsulation** — har qatlamda ma'lumotni header ichiga o'rash
- **Multiplexing** — bir vaqtda bir xil qurilmalar orasida bir nechta ilova
- **Socket** — IP manzil + protokol + port raqami, ulanishni noyob aniqlaydi
- **Non-ephemeral portlar** — 0–1,023, doimiy, serverlar ishlatadi
- **Ephemeral portlar** — 1,024–65,535, vaqtinchalik, klientlar ishlatadi
- **Flow control & Oqim nazorati** — qabul qiluvchi yuboruvchiga tezlik belgilaydi (faqat TCP)
- **Ishonchli yetkazish** — TCP tasdiqlash orqali ma'lumot yetganini kafolatlaydi
- **Ishonchsiz yetkazish** — UDP yuboradi va unutadi, tasdiqlash yo'q

---
