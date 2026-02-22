# 1-kun — Bilimlarni Tekshirish (Quiz)

**Mavzu:** OSI Model + Tarmoq Qurilmalari  
**Format:** CompTIA N10-009 imtihon uslubida

---

## 🔷 QISM 1 — OSI Model

---

**S1.** OSI modelining to'liq nomi nima?

- A) Open Software Integration
- B) Open Systems Interconnection
- C) Operational Security Interface
- D) Online Systems Integration

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: B**  
OSI = Open Systems Interconnection — tarmoq aloqasi uchun 7 qatlamli reference model.

</details>

---

**S2.** OSI modeli asosan nima uchun ishlatiladi?

- A) TCP/IP protokolini almashtirish uchun
- B) Tarmoq qurilmalarini sotib olish uchun yo'riqnoma sifatida
- C) Tarmoqdagi hodisa qaysi qatlamda sodir bo'lganini muhokama qilish uchun umumiy til sifatida
- D) Faqat Amerika kompaniyalari uchun standart sifatida

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: C**  
OSI — bu protokol emas, balki IT va xavfsizlik mutaxassislari uchun umumiy til. "Bu Layer 3 muammosi" desa, xonadagi hamma tushunadi.

</details>

---

**S3.** Quyidagi jadvalda Layer va uning nomi to'g'ri keltirilganmi?

| Layer | Nomi         |
| ----- | ------------ |
| 7     | Application  |
| 6     | Presentation |
| 5     | Session      |
| 4     | Transport    |
| 3     | Network      |
| 2     | Data Link    |
| 1     | Physical     |

- A) Ha, hammasi to'g'ri
- B) Yo'q, Layer 1 va Layer 7 o'rin almashgan
- C) Yo'q, Session Layer 4 da
- D) Yo'q, Presentation yo'q

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: A**  
Jadval to'liq to'g'ri. Yodlash uchun: **A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing (yuqoridan pastga).

</details>

---

**S4.** "Kabel uzildi, signal yo'q" — bu qaysi layer muammosi?

- A) Layer 2 — Data Link
- B) Layer 3 — Network
- C) Layer 1 — Physical
- D) Layer 4 — Transport

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: C**  
Layer 1 — Physical: xom signallar, kabellar, fiber, simsiz. "Signal bormi umuman?" — bu L1 savoli.

</details>

---

**S5.** MAC address qaysi layerga tegishli?

- A) Layer 1 — Physical
- B) Layer 3 — Network
- C) Layer 2 — Data Link
- D) Layer 4 — Transport

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: C**  
MAC address (Media Access Control) — tarmoq kartasiga o'rnatilgan hardware manzil, Layer 2 da ishlaydi.

</details>

---

**S6.** IP address va subnet mask qaysi layerga tegishli?

- A) Layer 2 — Data Link
- B) Layer 4 — Transport
- C) Layer 1 — Physical
- D) Layer 3 — Network

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: D**  
Layer 3 — Network: IP address lar, subnet mask lar, routing, router lar shu yerda.

</details>

---

**S7.** TCP va UDP port number lari qaysi layerda joylashgan?

- A) Layer 3 — Network
- B) Layer 5 — Session
- C) Layer 4 — Transport
- D) Layer 7 — Application

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: C**  
Layer 4 — Transport: TCP, UDP va port number lar shu yerda. "Post office layer" deb ham ataladi.

</details>

---

**S8.** HTTPS saytga kirganda ma'lumotning encryption/decryption i qaysi layerda sodir bo'ladi?

- A) Layer 7 — Application
- B) Layer 4 — Transport
- C) Layer 6 — Presentation
- D) Layer 3 — Network

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: C**  
Layer 6 — Presentation: SSL/TLS shu yerda ishlaydi. Character encoding, compression va application-level encryption ham shu layer.

</details>

---

**S9.** Wireshark da Gmail ulanishini ko'rayotgansan. "Ethernet II — src MAC, dst MAC" qatori qaysi layerni ko'rsatadi?

- A) L1 — Physical
- B) L3 — Network
- C) L4 — Transport
- D) L2 — Data Link

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: D**  
Ethernet II va MAC address lar — Layer 2 (Data Link). Wireshark dagi "Internet Protocol — src IP, dst IP" esa Layer 3.

</details>

---

**S10.** EUI-48 va EUI-64 nima?

- A) IP address formatlari
- B) MAC address formatlari
- C) Port number formatlari
- D) Encryption algoritmlari

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: B**  
EUI-48 — standart 48-bitli MAC address formati (eng keng tarqalgan). EUI-64 — 64-bitli kengaytirilgan format, IPv6 da ishlatiladi.

</details>

---

**S11.** Layer 3 da "Fragmentation" nima?

- A) Tarmoq kartasini ikki qismga bo'lish
- B) Packet juda katta bo'lganda uni kichik bo'laklarga bo'lish va boshqa tomonda qayta yig'ish
- C) Ma'lumotni shifrlash jarayoni
- D) Switch portlarini ajratish

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: B**  
Fragmentation — Layer 3 da sodir bo'ladi. Agar packet tarmoq segmenti uchun juda katta bo'lsa, Layer 3 uni kichik bo'laklarga bo'ladi va boshqa tomonda qayta yig'adi.

</details>

---

## 🔷 QISM 2 — Tarmoq Qurilmalari

---

**S12.** Router qaysi OSI layerda ishlaydi va asosiy vazifasi nima?

- A) Layer 2 — MAC address lar asosida trafikni yo'naltiradi
- B) Layer 3 — IP address lar asosida turli tarmoqlar orasida ma'lumot uzatadi
- C) Layer 7 — Dastur darajasida trafikni filtrlaydi
- D) Layer 1 — Signallarni kuchaytiradi

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: B**  
Router — Layer 3 (Network). IP address larga qarab "keyingi hop" ni aniqlaydi va turli subnet lar orasida ma'lumot uzatadi.

</details>

---

**S13.** "Layer 3 Switch" oddiy switch dan nimasi bilan farq qiladi?

- A) Tezroq ishlaydi
- B) Faqat simsiz tarmoqlarda ishlaydi
- C) Bir qutida ham L2 switch, ham L3 router funksiyasi bor
- D) Faqat fiber kabel bilan ishlaydi

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: C**  
Layer 3 Switch — switch routing ham qo'shilgan bo'lsa shunday ataladi. Switch boshqa layerga ko'chib o'tgani yo'q — shunchaki bir qutida ikkalasi bor.

</details>

---

**S14.** Switch lar hardware da tez ishlashi uchun qaysi texnologiyadan foydalanadi?

- A) GPU (Graphics Processing Unit)
- B) ASIC (Application-Specific Integrated Circuit)
- C) FPGA (Field Programmable Gate Array)
- D) CPU (Central Processing Unit)

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: B**  
ASIC — Application-Specific Integrated Circuit. Switch lar packet larni yo'naltirish uchun maxsus ishlab chiqilgan hardware ishlatadi, shuning uchun juda tez.

</details>

---

**S15.** PoE nima va qayerda ishlatiladi?

- A) Packet over Ethernet — katta fayllarni uzatish uchun
- B) Power over Ethernet — ethernet kabel orqali elektr quvvat yetkazadi (IP telefonlar, kameralar uchun)
- C) Protocol over Ethernet — yangi protokol turi
- D) Proxy over Ethernet — proxy server texnologiyasi

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: B**  
PoE = Power over Ethernet. Bitta ethernet kabel orqali ham ma'lumot, ham elektr quvvat uzatadi. IP telefonlar, access point lar va IP kameralar uchun ishlatiladi.

</details>

---

**S16.** An'anaviy Firewall va NGFW (Next-Generation Firewall) orasidagi asosiy farq nima?

- A) NGFW faqat simsiz tarmoqlarda ishlaydi
- B) An'anaviy firewall TCP/UDP port number bo'yicha filtrlaydi; NGFW esa haqiqiy dasturni aniqlab filtrlaydi
- C) NGFW faqat kiruvchi trafikni tekshiradi
- D) An'anaviy firewall tezroq ishlaydi

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: B**  
An'anaviy firewall: faqat port number ga qaraydi. NGFW: port ortida qaysi dastur ishlayotganini ham aniqlay oladi va shunga qarab qaror qabul qiladi.

</details>

---

**S17.** Firewall da VPN funksiyasi nima uchun ishlatiladi?

- A) Tarmoq tezligini oshirish uchun
- B) Ikki sayt orasida shifrlangan tunnel yaratish uchun
- C) MAC address larni yashirish uchun
- D) DNS so'rovlarini bloklash uchun

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: B**  
VPN = Virtual Private Network. Klassik sozlash: Sayt A dagi firewall + Sayt B dagi firewall = ular orasida shifrlangan tunnel. Tashqaridan ko'rinmaydi.

</details>

---

**S18.** NAT (Network Address Translation) nima uchun kerak?

- A) Tarmoq kabellarini boshqarish uchun
- B) Ichki (private) IP address larni bitta ommaviy (public) IP ortida yashirish uchun
- C) MAC address larni IP address ga aylantirish uchun
- D) Packet larni kichik bo'laklarga bo'lish uchun

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: B**  
NAT — Network Address Translation. Tashkilot ichidagi barcha qurilmalar o'zining private IP siga ega, lekin internetga chiqishda hammasi bitta public IP ko'rinadi.

</details>

---

**S19.** IDS va IPS orasidagi asosiy farq nima?

- A) IDS tezroq, IPS sekinroq
- B) IDS hujumni aniqlaydi va ogohlantiradi; IPS aniqlaydi VA bloklaydi
- C) IDS katta tarmoqlar uchun, IPS kichik tarmoqlar uchun
- D) IDS hardware, IPS software

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: B**  
IDS (Intrusion **Detection** System) — faqat ogohlantiradi, to'xtata olmaydi.  
IPS (Intrusion **Prevention** System) — aniqlaydi VA faol bloklaydi. Enterprise da IPS afzal ko'riladi.

</details>

---

**S20.** IDS/IPS quyidagilardan qaysi birini aniqlay oladi? (Eng to'liq javobni tanlang)

- A) Faqat virus lar
- B) Faqat port skanerlash
- C) Buffer overflow, Cross-site scripting (XSS), ma'lum exploit pattern lar va boshqa zaifliklar
- D) Faqat DDoS hujumlar

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: C**  
IDS/IPS ko'p turdagi hujumlarni aniqlay oladi: buffer overflow lar, XSS, ma'lum OS va dastur zaifliklariga qarshi exploit pattern lar va boshqalar.

</details>

---

**S21.** Load Balancer asosiy vazifasi nima?

- A) Tarmoqni tashqi hujumlardan himoya qilish
- B) Trafikni bir nechta server larga taqsimlash, birorta server haddan tashqari yuklanib qolmasligi uchun
- C) Ma'lumotlarni uzoq muddatga saqlash
- D) Simsiz signallarni kuchaytirish

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: B**  
Load Balancer — trafikni bir nechta fizikiy server larga taqsimlaydi. Agar bir server ishdan chiqsa, qolganlar davom etadi. Yirik saytlar 24/7 ishlashining sababi shu.

</details>

---

**S22.** "SSL offload" load balancer da nima uchun kerak?

- A) SSL sertifikatlarini sotib olish uchun
- B) Encryption/decryption ni load balancer o'zi qiladi, shunda backend server lar CPU ni bunga sarflamaydi
- C) SSL ni o'chirib qo'yish uchun
- D) Server lar orasidagi ulanishni shifrlash uchun

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: B**  
SSL offload — encryption/decryption ni load balancer zimmasiga oladi. Backend server lar bu yukdan ozod bo'lib, asosiy ishlariga ko'proq CPU sarflaydi.

</details>

---

**S23.** Proxy server da "Explicit" va "Transparent" turlari orasidagi farq nima?

- A) Explicit tezroq, Transparent sekinroq
- B) Explicit proxy ni bilish uchun OS/brauzer sozlanadi; Transparent esa ko'rinmas ishlaydi, foydalanuvchi bilmaydi
- C) Explicit faqat korporativ tarmoqlarda ishlaydi
- D) Transparent faqat HTTPS bilan ishlaydi

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: B**  
Explicit proxy: foydalanuvchi OS yoki brauzerida uni ko'rsatib qo'yadi.  
Transparent proxy: foydalanuvchi hech narsa sozlamaydi, tarmoq o'zi trafikni proxy orqali o'tkazadi.

</details>

---

**S24.** Proxy server quyidagilardan qaysi birini BAJARA OLMAYDI?

- A) Kesh orqali internet so'rovlarini kamaytirish
- B) Zararli saytlarni bloklash (URL filtering)
- C) Ma'lumotlarni server da block darajasida saqlash
- D) Foydalanuvchi nomidan so'rov yuborish

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: C**  
Block darajasida saqlash — bu SAN (Storage Area Network) ning vazifasi, Proxy serverniki emas. Proxy: caching, access control, URL filtering, content scanning bajaradi.

</details>

---

**S25.** NAS va SAN orasidagi asosiy farq nima?

- A) NAS tezroq, SAN sekinroq
- B) NAS fayl darajasida kirish ta'minlaydi; SAN esa blok darajasida (faqat o'zgargan qismlar uzatiladi)
- C) NAS katta kompaniyalar uchun, SAN kichik kompaniyalar uchun
- D) NAS simsiz, SAN kabellli

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: B**  
NAS: butun faylni tortib olasan, o'zgartirib, hammasini qaytib yozasan.  
SAN: lokal disk kabi — faqat o'zgargan bloklarni o'qib/yozadi. Katta fayllar va ma'lumotlar bazalari uchun ancha samaraliroq.

</details>

---

**S26.** Uyda ishlatiladigan "simsiz router" va enterprise dagi Access Point (AP) orasidagi farq nima?

- A) Uy routeri tezroq
- B) Uy routeri — router + switch + AP bitta qutida; Enterprise AP esa faqat simsiz → kabellli ko'prik vazifasini bajaradi
- C) Enterprise AP faqat 5GHz da ishlaydi
- D) Hech qanday farq yo'q

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: B**  
Uy "simsiz routeri" aslida uchta qurilma bitta qutida. Enterprise da esa har biri alohida, maxsus maqsad uchun qurilgan qurilmalar.

</details>

---

**S27.** Access Point (AP) qaysi OSI layerda ishlaydi?

- A) Layer 3 — Network
- B) Layer 1 — Physical
- C) Layer 2 — Data Link
- D) Layer 4 — Transport

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: C**  
AP — Layer 2 (Data Link). 802.11 simsiz ↔ 802.3 ethernet ko'prigi vazifasini bajaradi.

</details>

---

**S28.** Wireless LAN Controller (WLC) nima uchun kerak?

- A) Bitta access point ni boshqarish uchun
- B) Barcha access point larni bir joydan markaziy boshqarish, konfiguratsiya yuborish va monitoring qilish uchun
- C) Simsiz signalni kuchaytirish uchun
- D) Foydalanuvchilar parollarini saqlash uchun

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: B**  
WLC — "yagona boshqaruv oynasi". O'nlab yoki yuzlab AP larni alohida boshqarish o'rniga, barchasini bir joydan sozlaydi, kuzatadi, yangi AP larni avtomatik deploy qiladi.

</details>

---

## 🔷 QISM 3 — OSI Layer + Qurilma Bog'liqligi (Aralash)

---

**S29.** Quyidagi qurilmalarni to'g'ri OSI layer bilan moslashtir:

| Qurilma      | Layer |
| ------------ | ----- |
| Router       | ?     |
| Switch       | ?     |
| Access Point | ?     |
| Proxy Server | ?     |

- A) Router-L2, Switch-L3, AP-L1, Proxy-L6
- B) Router-L3, Switch-L2, AP-L2, Proxy-L7
- C) Router-L3, Switch-L2, AP-L3, Proxy-L4
- D) Router-L4, Switch-L2, AP-L2, Proxy-L7

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: B**  
Router → L3, Switch → L2, AP → L2, Proxy → L7 (Application).

</details>

---

**S30.** Muhandis "MAC address conflict bor, switch da muammo" deydi. Bu qaysi layer muammosi?

- A) Layer 1
- B) Layer 3
- C) Layer 2
- D) Layer 5

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: C**  
MAC address va switch — ikkalasi ham Layer 2 (Data Link). "Switch da muammo" = L2 muammo.

</details>

---

**S31.** Firewall qaysi layer oralig'ida ishlashi mumkin?

- A) Faqat Layer 3
- B) Faqat Layer 7
- C) Layer 3 dan Layer 7 gacha (turiga qarab)
- D) Layer 1 dan Layer 4 gacha

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: C**  
An'anaviy firewall Layer 3-4 da (IP va port). NGFW esa Layer 7 gacha ko'taradi — dastur darajasida tekshiradi.

</details>

---

**S32.** Ha yoki Yo'q: IDS/IPS funksiyasi zamonaviy NGFW larga o'rnatilishi mumkin, alohida qurilma shart emas.

- A) Ha
- B) Yo'q

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: A — Ha**  
Zamonaviy NGFW lar ko'pincha o'z ichiga IDS/IPS funksiyalarini ham oladi. Alohida standalone qurilma bo'lishi shart emas.

</details>

---

**S33.** Ha yoki Yo'q: Load Balancer faqat Layer 4 da ishlaydi.

- A) Ha
- B) Yo'q

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: B — Yo'q**  
Load Balancer Layer 4 dan Layer 7 gacha ishlaydi. Dastur asosidagi balancing (Layer 7) ham qo'llab-quvvatlanadi.

</details>

---

**S34.** Wireshark da "Destination port 443" ko'rding. Bu qaysi layerga tegishli va nima degan ma'noni anglatadi?

- A) Layer 3 — bu IP address
- B) Layer 4 — port 443 = HTTPS trafik
- C) Layer 2 — bu MAC address
- D) Layer 7 — bu dastur nomi

<details>
<summary>✅ Javobni ko'rish</summary>

**To'g'ri javob: B**  
Port number lar — Layer 4 (Transport). Port 443 = HTTPS. Wireshark dagi "TCP — port numbers" qatori Layer 4 ni ko'rsatadi.

</details>

---

## 📊 Natijangizni Hisoblang

| To'g'ri javoblar | Baho                                       |
| ---------------- | ------------------------------------------ |
| 32–34            | 🏆 Mukammal — tayyor                       |
| 27–31            | ✅ Yaxshi — bir oz takrorlash kerak        |
| 20–26            | ⚠️ O'rtacha — asosiy mavzularni qayta o'qi |
| 20 dan kam       | ❌ Qayta o'rganish kerak                   |

---
