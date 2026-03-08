# 3-kun — Video #11: Simsiz Tarmoq (6:37)

**Sana:** 2026-03-03
**Video:** #11 Wireless Networking
**Manba:** Professor Messer N10-009

---

## Umumiy Manzara

Simsiz tarmoq faqat uy WiFi si emas.
Ofis tarmoqlaridan tortib mobil telefonlargacha, sun'iy yo'ldoshlargacha hamma narsa kiradi.
Bu video uch qatlamni qamrab oladi: mahalliy WiFi (802.11), mobil tarmoqlar (4G/5G),
va sun'iy yo'ldosh tarmoqlari.

---

## 802.11 — WiFi Standarti

### Kim boshqaradi?

- **IEEE** — Institute of Electrical and Electronics Engineers
- Standart raqami: **802.11** — 802.11 eshitganingda, bu WiFi degani
- **Wi-Fi Alliance** — qurilmalarni interoperability uchun test qiluvchi alohida tashkilot
- Wi-Fi logosi bor har bir qurilma Wi-Fi Alliance tomonidan test qilingan va sertifikatlangan

### WiFi Avlodlari

| Standart | Avlod Nomi  | Chastota        | Maksimal Tezlik |
| -------- | ----------- | --------------- | --------------- |
| 802.11a  | (Wi-Fi 1)   | 5 GHz           | 54 Mbps         |
| 802.11b  | (Wi-Fi 2)   | 2.4 GHz         | 11 Mbps         |
| 802.11g  | (Wi-Fi 3)   | 2.4 GHz         | 54 Mbps         |
| 802.11n  | **Wi-Fi 4** | 2.4 / 5 GHz     | 600 Mbps        |
| 802.11ac | **Wi-Fi 5** | 5 GHz           | 3.5 Gbps        |
| 802.11ax | **Wi-Fi 6** | 2.4 / 5 / 6 GHz | 9.6 Gbps        |
| 802.11be | **Wi-Fi 7** | 2.4 / 5 / 6 GHz | 46 Gbps         |

> Birinchi uchtasi (a, b, g) hozir kamdan-kam ishlatiladi.
> Rasmiy avlod nomi berilmagan — lekin norasmiy Wi-Fi 1, 2, 3 deyiladi.
> Wi-Fi 4 dan Wi-Fi 7 gacha — haqiqiy hayotda va imtihonda ko'radigan narsa.

### Chastotalar — Nima uchun muhim

| Chastota    | Qamrov    | Tezlik   | Interference                            |
| ----------- | --------- | -------- | --------------------------------------- |
| **2.4 GHz** | Uzoqroq   | Sekinroq | Ko'p — microwave, Bluetooth, qo'shnilar |
| **5 GHz**   | Qisqaroq  | Tezroq   | Kam                                     |
| **6 GHz**   | Eng qisqa | Eng tez  | Eng kam — yangi, kam band               |

> Xavfsizlik nuqtai nazaridan: 2.4 GHz uzoqroq va devorlardan yaxshiroq o'tadi —
> tarmoq signaling binangdan tashqariga ham chiqadi.
> Parking lot da o'tirgan hacker 2.4 GHz tarmoqingga yetib borishi mumkin.

---

## Mobil Tarmoqlar — 4G va 5G

### 4G / LTE

- **LTE** = Long Term Evolution — 4G ning texnik nomi
- Ikki eski standartni (GSM va CDMA) bitta universal standartga birlashtirdi
- Download tezligi: ~**150 Mbps**
- **LTE-A** (LTE Advanced) — yaxshilangan versiya, ~**300 Mbps** gacha

### 5G

- **2020** yilda taqdim etildi
- Maqsad tezlik: ideal sharoitda **10 Gbps**
- Haqiqiy hayot tezligi: **100 – 900 Mbps**
- **IoT** uchun o'yin o'zgartiruvchi — bandwidth endi cheklov emas
- Ko'proq ma'lumot uzatiladi → cloudda ko'proq qayta ishlash mumkin
- Tezroq bildirishnomalar, tezroq javob vaqtlari

> 5G tezligi endi uyning simli internetiga teng.
> Bu mobil qurilmalar avval fizikiy kabel talab qilgan
> narsalarni qila olishini anglatadi.

---

## Sun'iy Yo'ldosh Tarmoqlari

### Qachon ishlatiladi?

An'anaviy internet kirishiga ega bo'lmagan uzoq joylarda —
fiber yo'q, kabel yo'q, cell tower yo'q.
Satellite dish qo'shing → yer yuzining istalgan joyida darhol ulanish.

### Tezliklar

- Download: ~**100 Mbps**
- Upload: ~**5 Mbps**
- Quruqlikdagi internetdan sekin, lekin uzoq joylar uchun ishlatish mumkin

### Kechikish (Latency) Muammosi

Signal kosmosga va orqaga qaytadi — bu vaqt talab qiladi:

| Texnologiya         | Kechikish                                    |
| ------------------- | -------------------------------------------- |
| An'anaviy satellite | 250ms yuqoriga + 250ms pastga = ~500ms jami  |
| **Starlink**        | ~40ms (20ms ga tushirishga harakat qilmoqda) |

> 500ms kechikish = har bir round trip da yarim soniya kechikish.
> VoIP qo'ng'iroqlari, video konferensiya, gaming uchun dahshatli.
> Starlink ning past orbita sun'iy yo'ldoshlari buni keskin kamaytirdi.

### Rain Fade

- Satellite orbitadagi sun'iy yo'ldoshga **to'g'ridan-to'g'ri ko'rinish chizig'ini** talab qiladi
- Har qanday to'siq = signal yo'qolishi
- **Rain fade** — bo'ron o'tib ketguncha ulanish yo'qoladi
- Sun'iy yo'ldosh ishlatadigan tashkilotlar aynan shu sabab backup ulanishga ega bo'ladi

---

## Asosiy Atamalar

- **IEEE** — 802.11 standartlarini belgilaydigan tashkilot
- **802.11** — WiFi standartlar oilasi
- **Wi-Fi Alliance** — WiFi interoperability uchun qurilmalarni test qiladi va sertifikatlaydi
- **Wi-Fi 4/5/6/7** — 802.11n/ac/ax/be ning avlod nomlari
- **2.4 GHz** — uzoq qamrov, sekin, ko'p interference
- **5 GHz** — qisqa qamrov, tez, kam interference
- **6 GHz** — eng yangi band, eng tez, eng kam band
- **LTE** — Long Term Evolution, 4G ning texnik nomi, ~150 Mbps
- **LTE-A** — LTE Advanced, yaxshilangan 4G, ~300 Mbps
- **5G** — 2020 da taqdim etildi, nazariy 10 Gbps, haqiqiy 100-900 Mbps
- **IoT** — Internet of Things, 5G bandwidthidan eng ko'p foyda ko'radigan qurilmalar
- **Satellite networking** — dish orqali ulanish, 100 Mbps down / 5 Mbps up
- **Rain fade** — bo'ron paytida ko'rinish chizig'i talabi tufayli signal yo'qolishi
- **Starlink** — past orbita satellite tarmog'i, ~40ms kechikish
- **Latency** — signal sayohat vaqtidagi kechikish, real vaqt ilovalar uchun muhim

---

_Keyingi: 4-kun — Kabellar + Konnektorlar (Video #12–17)_
