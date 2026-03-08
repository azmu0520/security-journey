# 3-kun — Video #10: Tarmoq Muloqoti (3:55)

**Sana:** 2026-03-03
**Video:** #10 Network Communication
**Manba:** Professor Messer N10-009

---

## Umumiy Manzara

Qurilma ma'lumot yuborganda — kim qabul qiladi?
Bu **muloqot turiga** bog'liq.
To'rtta tur mavjud: Unicast, Multicast, Anycast, Broadcast.
Har biri bir xil savolga boshqacha javob beradi: **bir yuboruvchi, lekin qancha qabul qiluvchi?**

---

## To'rtta Tur

| Tur           | Munosabat                     | Oddiy tushuntirish                                        |
| ------------- | ----------------------------- | --------------------------------------------------------- |
| **Unicast**   | Bir → Bir                     | Faqat sen va boshqa bitta qurilma                         |
| **Multicast** | Bir → Ko'p (obuna bo'lganlar) | Sen va obuna bo'lgan guruh                                |
| **Anycast**   | Bir → Eng yaqin bittasi       | Bitta manzilga yuboriladi, eng yaqin qurilma javob beradi |
| **Broadcast** | Bir → Hammasi                 | Mahalliy tarmoqdagi barcha qurilmalarga yuboriladi        |

---

## Unicast — Birdan Biriga

- Tarmoqdagi eng keng tarqalgan muloqot turi
- Ma'lumot bir qurilmadan to'g'ridan-to'g'ri boshqa bitta qurilmaga ketadi
- Tarmoqdagi boshqa hech kim bilan ulashmaydi
- IPv4 va IPv6 ikkalasida ham ishlaydi

**Bazi bir real misollar:**

- Veb-sayt ochish
- Fayl uzatish
- Email tekshirish

**Kamchiligi:**
100 ta qurilmaga bir xil ma'lumot yuborish kerak bo'lsa —
100 ta alohida unicast ulanish kerak bo'ladi.
100 ta alohida stream. Juda samarasiz.

---

## Multicast — Birdan Ko'pga (Obuna Bo'lganlar)

- Bir yuboruvchi → bir vaqtda bir nechta qabul qiluvchi
- Qabul qiluvchilar multicast feed ga **obuna bo'lishi** kerak — o'zlari tanlab kiradi
- Tarmoqdagi hamma emas, faqat obuna bo'lganlar oladi

**Haqiqiy qo'llanilishi:**

- Bir vaqtda ko'p tomoshabinga jonli video stream
- Birja ma'lumotlari feed lari
- Router bir vaqtda bir nechta routerga routing update yuborishi

**Cheklovi:**
Multicast ni tushunadigan tarmoq uskunalarini talab qiladi.
Shu sabab katta yoki turli tarmoqlarda ishlatilmaydi.
Nazorat ostidagi muhitlarda yaxshi ishlaydi — IPv4 va IPv6 ikkalasi qo'llab-quvvatlaydi.

---

## Anycast — Birdan Eng Yaqin Bittasiga

- Bitta destination IP manzil, lekin ko'p qurilma shu manzilni bo'lishadi
- Packet bir marta yuboriladi — **eng yaqin qurilma javob beradi**
- Yuboruvchi kim javob berishini tanlamaydi — tarmoqning o'zi hal qiladi

**Haqiqiy qo'llanilishi — Anycast DNS:**

- Qurilmang bitta IP manzilga DNS query yuboradi
- Dunyodagi eng yaqin data center javob beradi
- Cloudflare ning `1.1.1.1` va Google ning `8.8.8.8` shu tarzda ishlaydi —
  bir xil IP, dunyo bo'ylab ko'p server, eng yaqini doim javob beradi

> CDN lar ham aynan shu tarzda ishlaydi —
> bir xil konsept, eng yaqin server so'rovingni bajaradi.

---

## Broadcast — Birdan Hammasiga

- Bitta packet yuboriladi — **mahalliy tarmoqdagi har bir qurilma qabul qiladi**
- Faqat **mahalliy broadcast domain** bilan cheklangan
- Routerdan o'ta olmaydi — broadcast mahalliy tarmoqda qoladi
- Broadcast internet orqali sayohat qila olmaydi

**Haqiqiy qo'llanilishi:**

- ARP so'rovlari — "bu IP manzil kimda bor?"
- DHCP discovery — "bu tarmoqda DHCP server bormi?"
- Mahalliy segmentlarda routing update lar

**Muhim:**
IPv4 broadcastdan keng foydalanadi.
IPv6 **broadcastni butunlay olib tashladi** — o'rniga multicast ishlatadi.
Bu IPv6 ning samaraliroq bo'lishining sabablaridan biri.

---

## Ketma-ket — Tezkor Qaror

```
BITTA qurilma bilan gaplashish kerakmi?              → Unicast
OBUNA BO'LGAN GURUH bilan gaplashish kerakmi?        → Multicast
Ko'p bir xil serverdan ENG YAQININI topish kerakmi?  → Anycast
Mahalliy tarmoqdagi HAMMASIGA yetkazish kerakmi?     → Broadcast
```

---

## Asosiy Atamalar

- **Unicast** — birdan biriga muloqot, eng keng tarqalgan tur
- **Multicast** — birdan ko'pga, faqat obuna bo'lgan qurilmalar qabul qiladi
- **Anycast** — ko'p qurilma bir IP ni bo'lishadi, eng yaqini javob beradi
- **Broadcast** — mahalliy tarmoqdagi barcha qurilmalarga, broadcast domain da qoladi
- **Broadcast domain** — broadcast trafik chegarasi, routerda tugaydi
- **ARP** — Address Resolution Protocol, IP uchun MAC manzilini topish uchun broadcast ishlatadi
- **DHCP discovery** — klient tarmoqda DHCP server topish uchun broadcast yuboradi

---
