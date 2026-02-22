# 1-kun — Tarmoq Qurilmalari (Video #3)

**Sana:** 2026-02-22  
**Video:** #3 Networking Devices (14:31)  
**Manba:** Professor Messer N10-009

---

## Umumiy Manzara

Data center ga kirsang, ma'lumotlarni harakatga keltirish uchun birgalikda ishlaydigan uskunalar bilan to'lgan racklar ko'rasan. Har bir qurilmaning o'z vazifasi bor. Bu video — har bir qurilma _nima_ ekanini, _nima uchun_ mavjudligini va _qaysi OSI layer_ da ishlashini bilish haqida — chunki imtihon va haqiqiy xavfsizlik ishi shu tarzda o'ylaydi.

---

## Ko'rib Chiqilgan Qurilmalar

### Router

- Turli IP subnet lar orasida ma'lumot uzatadi — bir xil qatordagi qo'shni subnetlar bo'lishi mumkin, yoki turli qit'alardagi subnetlar
- **OSI Layer 3** (Network layer) — IP address lar bilan ishlaydi
- "Keyingi hop" ni aniqlaydi — bu packet manzilga yetish uchun keyingi qadam qayerga borishi kerak
- Ko'p turdagi tarmoqlarni ulashi mumkin: LAN dan WAN ga, mis kabeldan fiber ga
- Ko'pincha ko'p interface/port larga ega, har biri turli tarmoqqa ulangan

**Layer 3 Switch** — switch routing ham qo'shilgan bo'lsa, odamlar uni Layer 3 switch deb atashadi. Switch boshqa layerga ko'chib o'tgani yo'q — shunchaki bir qutichada ham L2 switch, ham L3 router bor.

---

### Switch

- **MAC address** lar (fizikiy manzillar) asosida trafikni yo'naltiradi
- **OSI Layer 2** (Data Link layer)
- **ASIC** lar (Application-Specific Integrated Circuit) yordamida asosan hardware da ishlaydi — shuning uchun switch lar juda tez
- Enterprise switch larda qo'shimcha imkoniyatlar:
  - **PoE (Power over Ethernet)** — bir xil ethernet kabel orqali quvvat yetkazadi (IP telefonlar, access point lar, kameralar uchun ishlatiladi)
  - Routing funksionalligi → Layer 3 switch ga aylanadi

---

### Firewall

- Tarmoqqa kiradigan va chiqadigan trafikni filtrlaydi
- An'anaviy firewall: **TCP/UDP port number** bo'yicha filtrlaydi
- **NGFW (Next-Generation Firewall)**: chuqurroq boradi — trafikni keltirayotgan haqiqiy _dasturni_ aniqlay oladi va uni ruxsat berish-bermaslikni hal qiladi (faqat port emas)
- Ko'pgina firewall lar quyidagilarni ham bajaradi:
  - **VPN** — tunnel orqali ikki sayt orasidagi trafikni shifrlaydi. Klassik sozlash: Sayt A dagi firewall + Sayt B dagi firewall = ular orasida shifrlangan tunnel
  - **NAT (Network Address Translation)** — ichki IP lar ni bitta ommaviy IP ortida yashiradi
  - **Routing** — firewall lar tarmoq chegarasida (kirish/chiqish nuqtasida) turadi, shuning uchun ko'pincha router sifatida ham ishlaydi
  - **Dynamic routing protocols** — zamonaviy firewall larning ko'pchiligi qo'llab-quvvatlaydi

> Xavfsizlik nuqtai nazaridan: firewall — ichkarisi va tashqarisi orasidagi darvozabon. U nima ko'ra olishi va nima ko'ra olmasligini tushunish hujum ham, mudofaa ham uchun juda muhim.

---

### IDS va IPS

|                                 | IDS (Intrusion Detection System)                            | IPS (Intrusion Prevention System)                  |
| ------------------------------- | ----------------------------------------------------------- | -------------------------------------------------- |
| Nima qiladi                     | Trafikni kuzatadi, ma'lum hujumlar haqida **ogohlantiradi** | Trafikni kuzatadi, ma'lum hujumlarni **bloklaydi** |
| Hujumni to'xtatа oladimi?       | ❌ Yo'q — faqat ogohlantiradi                               | ✅ Ha — faol bloklaydi                             |
| Enterprise da keng tarqalganmi? | Endi kamroq                                                 | Ha — afzal ko'riladi                               |

**Nima aniqlanadi:**

- OS va dasturlarga qarshi ma'lum exploit pattern lar
- Buffer overflow lar
- Cross-site scripting (XSS)
- Boshqa ma'lum zaifliklar

Zamonaviy NGFW lar ko'pincha alohida qurilma sifatida emas, balki o'z ichiga IDS va IPS funksiyalarini olgan.

---

### Load Balancer

- Birorta server haddan tashqari yuklanib qolmasligi uchun trafikni bir nechta fizikiy server larga taqsimlaydi
- Oxirgi foydalanuvchi sifatida bitta serverga kirayotgandek o'ylaysan — aslida qaysi server seni qayta ishlashini tanlayotgan load balancer ga kiryapsan
- Agar server ishdan chiqsa, load balancer uni sezadi, aylanishdan chiqaradi, qolgan serverlar davom etadi — yirik saytlar 24/7 ishlashining sababi shu

**Load balancer larda ko'pincha mavjud qo'shimcha imkoniyatlar:**

- **TCP offloading** — TCP ulanishlarini o'zi boshqaradi, shunda backend server lar buni qilishi shart emas
- **SSL offload** — encryption/decryption ni o'z zimmasiga oladi, serverlar CPU ni bunga sarflamaydi
- **Caching** — umumiy javoblarni saqlaydi, serverga murojaat qilmasdan o'zi javob bera oladi
- **QoS (Quality of Service)** — ma'lum trafikni boshqasidan ustun qo'yadi
- **Dastur asosidagi balancing** — ma'lum sahifalar/xizmatlar ma'lum serverlarga biriktirilishi mumkin

> Web dev bog'liqlik: auto-scaling bilan cloud platformaga deploy qilgan bo'lsang, orqa fonda aynan shuni qilayotgan load balancer bor

---

### Proxy Server

- Foydalanuvchi va internet orasidagi suhbatning **o'rtasida** turadi
- Foydalanuvchi → Proxy → Internet → Proxy → Foydalanuvchi
- Proxy so'rovni foydalanuvchi _nomidan_ yuboradi, javobni tekshiradi, keyin qaytaradi

**Tashkilotlar proxy dan foydalanish sabablari:**

- **Caching** — 100 xodim bir xil saytga kirsa, proxy uni keshdan yuboradi, 100 ta alohida internet so'rovi bo'lmaydi
- **Access control** — internet kirishini olish uchun login/parol talab qiladi
- **URL filtering** — ma'lum saytlarni bloklaydi
- **Content scanning** — foydalanuvchiga yetib kelmasidan oldin javoblarda zararli dasturlarni tekshiradi

**Ikki turi:**

- **Explicit proxy** — OS yoki brauzeringga uni ishlatishni sozlaysan, proxy orqali borayotganini biladi
- **Transparent proxy** — ko'rinmas ishlaydi, OS yoki dasturlarda hech qanday o'zgartirish kerak emas, foydalanuvchi bilmaydi

> Xavfsizlik nuqtai nazaridan: proxy lar foydalanuvchilarning internetda nima qilayotganini kuzatish va zararli yuklamalar mashinaga tushmasidan oldin ushlash uchun juda qulay

---

### NAS va SAN (Saqlash)

|                          | NAS (Network-Attached Storage)                                                                      | SAN (Storage Area Network)                                         |
| ------------------------ | --------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| Kirish turi              | **Fayl darajasi**                                                                                   | **Blok darajasi**                                                  |
| Qanday ishlaydi          | O'qish/tahrirlash uchun butun faylni tarmoq orqali tortib olasan, tugagach hammasini qaytib yozasan | Faqat o'zgargan bloklarni o'qib/yozadi — lokal disk kabi           |
| Eng yaxshi qo'llanilishi | Umumiy fayl almashinuvi                                                                             | Katta fayllar, ma'lumotlar bazalari, yuqori unumdorlik ehtiyojlari |
| Samaradorlik             | Katta fayllar uchun pastroq                                                                         | Ancha yuqori — faqat o'zgargan bloklar uzatiladi                   |

Ham NAS, ham SAN odatda data center ichida o'zlarining alohida yuqori o'tkazuvchanlikli tarmoqlarida joylashadi.

---

### Access Point (AP)

- Simsiz qurilmalarga kabellli tarmoqqa ulanish imkonini beradi
- **OSI Layer 2** (Data Link) — 802.11 simsiz ↔ 802.3 ethernet ni ko'prik qiladi
- Uy "simsiz router" i bilan bir xil emas — u router + switch + AP bitta qutida. Enterprise da bular alohida maxsus qurilmalar

**Katta muhitlarda:**

- Bino yoki kampus bo'ylab ko'p AP lar bo'ladi
- Foydalanuvchilar ulanishni yo'qotmay AP lar orasida yuradi
- O'nlab AP larni alohida boshqarish dahshatli bo'lar edi → bu yerda **Wireless LAN Controller (WLC)** kerak bo'ladi

---

### Wireless LAN Controller (WLC)

- Barcha access point larni bir joydan markaziy boshqaradi — "yagona boshqaruv oynasi"
- Barcha AP larga bir vaqtda konfiguratsiya o'zgarishlarini yuboradi
- Barcha AP larda ishlashni va xavfsizlikni kuzatadi
- Yangi AP larni to'liq konfiguratsiya bilan avtomatik ravishda joylashtiradi
- Foydalanish hisobotlarini yaratadi — ko'proq AP kerakmi yoki joylashuvni yaxshilash kerakmi bilish uchun foydali
- Odatda proprietary — AP lar va WLC bir xil ishlab chiqaruvchidan

---

## Bu Qurilmalar uchun OSI Layer Xulosasi

| Qurilma        | OSI Layer                |
| -------------- | ------------------------ |
| Router         | Layer 3 (Network)        |
| Switch         | Layer 2 (Data Link)      |
| Layer 3 Switch | Layer 2 + Layer 3        |
| Firewall       | Layer 3–7 (turiga qarab) |
| Access Point   | Layer 2 (Data Link)      |
| Load Balancer  | Layer 4–7                |
| Proxy          | Layer 7 (Application)    |

---

## Chalkashtirgani / Qayta ko'rib chiqmoqchi

- [ ] Load balancer dagi SSL offloading aynan qanday ishlaydi — backend serverlarga yuborishdan oldin qayta shifrlayaptimi yoki oddiy matn sifatida yuboradimi?
- [ ] Transparent proxy — foydalanuvchi hech narsa sozlamasa, tarmoq trafikni qanday majburan undan o'tkazadi?
- [ ] Blok darajasi va fayl darajasidagi kirish — bu qachon muhim bo'lishining aniqroq misolini ko'rmoqchiman

---

## Asosiy Atamalar

- **ASIC** — Application-Specific Integrated Circuit, tez packet yo'naltirish uchun switch lar ichidagi ixtisoslashgan hardware
- **PoE** — Power over Ethernet, ethernet kabel orqali elektr quvvat yetkazadi
- **NGFW** — Next-Generation Firewall, faqat port larni emas, dastur darajasida tekshira oladi
- **NAT** — Network Address Translation, shaxsiy IP larni ommaviy IP ga moslashtiradi
- **QoS** — Quality of Service, ma'lum trafikni ustunligi bilan yuboradi
- **NAS** — Network-Attached Storage, fayl darajasidagi kirish
- **SAN** — Storage Area Network, blok darajasidagi kirish
- **WLC** — Wireless LAN Controller, bir nechta AP lar uchun markaziy boshqaruv
- **IDS/IPS** — Intrusion Detection/Prevention System, kirib kelish aniqlash/oldini olish tizimi

---

_Keyingi: 2-kun — TCP/IP, IP manzillash, birinchi Wireshark capture_
