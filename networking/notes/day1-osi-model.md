# Kun 1 — OSI Model & Networking Devices

**Sana:** 2026-02-22  
**Videos watched:** #1 Exam Intro, #2 OSI Model, #3 Networking Devices

---

## OSI Model nima?

OSI = Open Systems Interconnection Reference Model.

Bu protocol emas. Bu TCP/IP ham emas. Bu **umumiy til** — IT va xavfsizlik mutaxassislari tarmoqda biror narsa qayerda sodir bo'layotganini muhokama qilish uchun ishlatiladigan tizim. Kimdir "bu Layer 3 muammosi" desa, xonadagi hamma — qaysi kompaniyadan yoki qaysi mamlakatdan bo'lishidan qat'i nazar — bu nima ekanligini aniq tushunadi.

## 7 ta Layer (Qatlam)

Yodlash uchun (yuqoridan pastga): **All People Seem To Need Data Processing**

| Layer | Nomi         | Qisqacha                                         | Haqiqiy misollar                         |
| ----- | ------------ | ------------------------------------------------ | ---------------------------------------- |
| 7     | Application  | Ekranda ko'rgan narsang                          | HTTP, HTTPS, FTP, DNS, POP3              |
| 6     | Presentation | Ma'lumotni formatlaydi; encryption ni boshqaradi | SSL/TLS encryption/decryption            |
| 5     | Session      | Ulanishni boshlaydi, boshqaradi va yakunlaydi    | Control protocols, tunneling             |
| 4     | Transport    | Ma'lumotni A dan B ga yetkazadi                  | TCP, UDP, port numbers                   |
| 3     | Network      | IP orqali tarmoqlar orasida yo'naltiradi         | IP addresses, subnet masks, routers      |
| 2     | Data Link    | Bir xil tarmoqdagi ikki qurilma orasidagi aloqa  | MAC addresses, ethernet frames, switches |
| 1     | Physical     | Kabel/fiber/simsiz orqali xom signallar          | Kabellar, fiber, simsiz signallar        |

---

## Har bir Layer batafsil

### Layer 1 — Physical

- Xom elektr/optik/simsiz signallar — bitlarni bir joydan ikkinchi joyga o'tkazish
- Bu yerda haqiqiy protocol yo'q, faqat signallar
- **L1 da muammolar:** yomon kabel, fiber, simsiz signal to'silishi, loopback testlar, adapter kartalarini tekshirish
- "Umuman signal bormi?" deb so'rasang — bu Layer 1 savoli

### Layer 2 — Data Link

- **Bir xil** tarmoqdagi ikki qurilma o'rtasidagi aloqa
- **MAC address** (Media Access Control) ishlatadi — tarmoq kartasiga o'rnatilgan hardware manzil
  - DLC (Data Link Control) manzil deb ham ataladi
  - **EUI-48** — standart 48-bitli MAC address formati (eng keng tarqalgan)
  - **EUI-64** — 64-bitli kengaytirilgan format (IPv6 da ishlatiladi)
- Switch lar bu yerda yashaydi — ular trafikni MAC address (MAC manzilga) ga qarab yo'naltiradi
- Switch, MAC address yoki ethernet frame haqida → Layer 2

### Layer 3 — Network

- **Turli** tarmoqlar orasida yo'naltirish
- **IP address** va **subnet mask** ishlatadi
- Router lar IP manziliga qarab keyingi "hop" ni aniqlaydi
- **Fragmentation shu yerda sodir bo'ladi** — agar packet tarmoq segmenti uchun juda katta bo'lsa, Layer 3 uni kichik bo'laklarga bo'ladi va boshqa tomonda qayta yig'adi
- IP address, subnet mask yoki routing haqida → Layer 3

### Layer 4 — Transport

- Ma'lumotni bir qurilmadan ikkinchisiga ishonchli yetkazadi — "pochta bo'limi"
- Ikki asosiy protocol:
  - **TCP** (Transmission Control Protocol) — ishonchli, tartibli, xatolar tekshiriladi
  - **UDP** (User Datagram Protocol) — tez, yetkazilish kafolatlanmaydi
- Katta ma'lumotni kichik segmentlarga bo'ladi, boshqa tomonda qayta yig'adi
- **TCP/UDP port raqamlari shu yerda**
- TCP port yoki UDP port haqida → Layer 4

### Layer 5 — Session

- Ikki qurilma o'rtasidagi **suhbatni** boshqaradi: boshlaydi, to'xtatadi, qayta boshlaydi
- Control protocols va tunneling protocols shu yerda ishlaydi
- Agar dastur control protocol ishlatsa yoki ma'lumotni boshqa ma'lumot ichiga tunnel qilsa → Layer 5

### Layer 6 — Presentation

- Ma'lumotni dasturlar va odamlar tushunadigan formatga o'giradi
- **Character encoding**, **compression** va **dastur darajasidagi encryption/decryption** ni boshqaradi
- **SSL/TLS shu yerda** — HTTPS saytga kirsang, ma'lumotning encryption/decryption i Layer 6 da sodir bo'ladi
- Layer 7 bilan birga muhokama qilinadi, chunki ular birgalikda ishlaydi

### Layer 7 — Application

- Ekranda biz korib turgan narsa
- Dasturning o'zi, dasturdan kelgan xabarlar, foydalanuvchiga ko'rinadigan hamma narsa
- HTTP, HTTPS, FTP, DNS, POP3 va minglab boshqalar
- Veb-sahifaga kirish, emailni tekshirsang, DNS query ishlatsa → Layer 7

---

## Wireshark Isboti — Haqiqiy Trafikda OSI

Messer Wireshark da Gmail ulanishini ko'rsatdi va protocol decode ning har bir satrini layerga moslashtirdi. Bu — amalda OSI model.

**Frame 88 — 2,005 bytes, Gmail HTTPS orqali:**

| Wireshark Satri                    | Nima ko'rsatadi                            | OSI Layer          |
| ---------------------------------- | ------------------------------------------ | ------------------ |
| Frame 88 — 2005 bytes on wire      | Xom signal, byte soni                      | **L1 — Physical**  |
| Ethernet II — src MAC, dst MAC     | Hardware manzillar                         | **L2 — Data Link** |
| Internet Protocol — src IP, dst IP | `72.14.247.19` = `googlemail.l.google.com` | **L3 — Network**   |
| TCP — port numbers                 | Destination port **443** = HTTPS           | **L4 — Transport** |
| Secure Socket Layer                | 5+6+7 layerlarni birlashtiradi             | **L5 + L6 + L7**   |

> Wireshark dagi SSL/TLS yuqori uchta layerni birlashtiradi — Session (ulanishni boshqarish), Presentation (encryption/decryption), Application (ko'rgan Gmail interfeysi).

**Asosiy tushuncha:** qo'lga kiritgan har bir packet shu modelga mos keladi. Wireshark decode ni o'qib, har bir satr qaysi layerga tegishligini ayta olsang, OSI abstrakt bo'lishdan to'xtaydi. 2-kuni buni o'zing jonli qilaman.

---

## Tezkor Layer Aniqlash

| Kimdir shuni desa...              | Shu layerni o'yla |
| --------------------------------- | ----------------- |
| Yomon kabel / signal yo'q         | L1 — Physical     |
| MAC address / switch muammosi     | L2 — Data Link    |
| IP address / routing / subnet     | L3 — Network      |
| TCP port / UDP port               | L4 — Transport    |
| Session boshlanmoqda yoki uzildi  | L5 — Session      |
| SSL/TLS encryption                | L6 — Presentation |
| Dasturning o'zi / ekrandagi narsa | L7 — Application  |

---

## Chalkashtirgani / Qayta ko'rib chiqmoqchi

- [ ] Layer 5 va Layer 4 hali biroz noaniq — Transport yetkazish ishonchliligini boshqaradi, Session esa uzunroq suhbat aylanish siklini. Ko'proq misollar kerak
- [ ] Layer 3 da Fragmentation — agar ba'zi fragmentlar tartibsiz yoki umuman kelmasa, qayta yig'ish qanday ishlaydi?
- [ ] EUI-64 — u IPv6 da aniq qanday ishlatiladi?

---

## Asosiy Atamalar

- **OSI** — Open Systems Interconnection, tarmoq aloqasi uchun 7 qatlamli reference model
- **MAC address** — tarmoq kartasiga o'rnatilgan hardware manzil, Layer 2 (DLC address deb ham ataladi)
- **EUI-48 / EUI-64** — MAC address formatlari (48-bitli standart, IPv6 uchun 64-bitli)
- **TCP** — Transmission Control Protocol, ishonchli yetkazish, Layer 4
- **UDP** — User Datagram Protocol, tez/kafolatsiz, Layer 4
- **Fragmentation** — Layer 3 da o'ta katta packetlarni kichik bo'laklarga bo'lish
- **SSL/TLS** — encryption protocol, Layer 6 da ishlaydi
