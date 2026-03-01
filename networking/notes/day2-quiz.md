# 2-kun — To'liq Savol-Javob Testi

**Mavzular:** CDN, VPN, QoS, TTL, NFV, VPC, Bulut Xavfsizligi, Bulut Modellari, TCP/UDP, Encapsulation, Socket, Port Raqamlar
**Savollar soni:** 35
**Qoida:** Javoblarni ko'rmay ishla, keyin tekshir

---

## 1-bo'lim — CDN va VPN (1–5)

**1.** Kompaniyaning video kontenti Yevropadan servis qilinmoqda. Osiyo foydalanuvchilari sekin yuklanishdan shikoyat qilmoqda. Eng yaxshi yechim nima?

- A) Server RAM ni oshirish
- B) CDN yordamida kontentni geografik taqsimlash
- C) Foydalanuvchilarga VPN ishlatishni buyurish
- D) DNS TTL ni kamaytirish

---

**2.** Kompaniyaning 500 ta remote xodimi bor, barchasi bir vaqtda korporativ tarmoqqa xavfsiz ulanishi kerak. Tarmoq administratori qaysi qurilmani o'rnatishi kerak?

- A) Layer 2 Switch
- B) VPN Concentrator
- C) DNS Server
- D) Load Balancer

---

**3.** Qaysi qurilma ko'pincha VPN concentrator funksiyasini o'z ichiga oladi?

- A) Layer 2 Switch
- B) Load Balancer
- C) Next-Generation Firewall
- D) Wireless Access Point

---

**4.** Xodim uydan korporativ tarmoqqa xavfsiz ulanmoqchi. Qaysi texnologiya ishlatiladi?

- A) CDN
- B) NAT
- C) VPN
- D) QoS

---

**5.** CDN ning asosiy afzalligi nima?

- A) Tarmoq xavfsizligini oshiradi
- B) Foydalanuvchiga yaqin serverdan kontent yetkazadi, kechikishni kamaytiradi
- C) IP manzillarni yashiradi
- D) Paketlarni shifrlaydi

---

## 2-bo'lim — QoS va TTL (6–10)

**6.** Tarmoq administratori video konferensiya trafikini oddiy fayl yuklab olishdan ustun qo'ymoqchi. Qaysi texnologiya ishlatiladi?

- A) NAT
- B) VPN
- C) QoS
- D) CDN

---

**7.** IP packetda TTL qiymati nolga yetganda nima bo'ladi?

- A) Packet keyingi routerga yuboriladi
- B) Router packet ni o'chirib tashlaydi
- C) Packet manba qurilmasiga qaytariladi
- D) TTL avtomatik qayta tiklanadi

---

**8.** Windows da default TTL qiymati qancha?

- A) 32
- B) 64
- C) 128
- D) 255

---

**9.** `traceroute` da quyidagi ketma-ketlikni ko'rdim:

```
10.1.10.1 → 10.2.10.2 → 10.1.10.1 → 10.2.10.2 → ...
```

Bu nima?

- A) Normal tarmoq ishi
- B) Routing loop
- C) DDoS hujumi
- D) DNS muammosi

---

**10.** `dig www.example.com` natijasida TTL = 300 ko'rsatildi. Bu nima degani?

- A) Packet 300 ta routerdan o'ta oladi
- B) DNS yozuvi 300 sekund (5 daqiqa) keshda saqlanadi
- C) Server 300 ta ulanishni qabul qiladi
- D) TTL 300 daqiqadan keyin yangilanadi

---

## 3-bo'lim — NFV va VPC (11–17)

**11.** NFV (Network Function Virtualization) nima?

- A) Fizikiy serverlarni bulutga ko'chirish jarayoni
- B) Router, switch, firewall kabi qurilmalarni virtual dasturiy ko'rinishga o'tkazish
- C) Tarmoq trafigini shifrlash texnologiyasi
- D) Bir nechta VPC ni birlashtirish protokoli

---

**12.** VPC (Virtual Private Cloud) nima?

- A) Umumiy internet bilan ulashilgan virtual server
- B) Bulut ichidagi izolyatsiyalangan virtual tarmoq
- C) Fizikiy server xonasi
- D) VPN ulanish protokoli

---

**13.** Kompaniyaning ikki xil VPC si bor va ular orasida aloqa kerak. Qaysi komponent ishlatiladi?

- A) Internet Gateway
- B) NAT Gateway
- C) Transit Gateway
- D) VPC Endpoint

---

**14.** Private VPC internet resurslariga chiqishi kerak, lekin tashqaridan hech kim kira olmasligi kerak. Qaysi yechim?

- A) Internet Gateway
- B) NAT Gateway
- C) Transit Gateway
- D) VPN Connection

---

**15.** AWS dagi VPC Oracle Cloud dagi VPC ga to'g'ridan-to'g'ri ulanishi kerak. Qaysi komponent ishlatiladi?

- A) Transit Gateway
- B) Internet Gateway
- C) NAT Gateway
- D) VPC Endpoint

---

**16.** Security List va Network Security Group (NSG) ning asosiy farqi nima?

- A) Security List tezroq ishlaydi
- B) Security List barcha VPC larga avtomatik qo'llaniladi, NSG esa individual VNIC darajasida
- C) NSG faqat UDP trafikni filtrlaydi
- D) Security List faqat IPv6 ni qo'llab-quvvatlaydi

---

**17.** Administrator bir subnet ichida turli virtual mashinalarga turli xavfsizlik qoidalarini qo'llashi kerak. Qaysi yechim to'g'ri?

- A) Har bir virtual mashina uchun alohida VPC yaratish
- B) Network Security Group (NSG) — individual VNIC darajasida qoidalar
- C) Security List — barcha subnetlarga bir xil qoidalar
- D) NAT Gateway orqali trafikni filtrlash

---

## 4-bo'lim — Bulut Modellari (18–23)

**18.** Kompaniya Gmail ishlatmoqda. Bu qaysi bulut modeli?

- A) IaaS
- B) PaaS
- C) SaaS
- D) Private cloud

---

**19.** Dasturchi AWS EC2 da virtual server ko'tardi, o'zi OS va dasturlar o'rnatdi. Bu qaysi model?

- A) SaaS
- B) PaaS
- C) IaaS
- D) Hybrid cloud

---

**20.** Salesforce platformasida foydalanuvchi o'z ilovasini quryapti. Bu qaysi model?

- A) SaaS
- B) IaaS
- C) PaaS
- D) Private cloud

---

**21.** IaaS da kim OS ni boshqarish uchun javobgar?

- A) Bulut provayder
- B) Mijoz
- C) Ikkalasi birgalikda
- D) Uchinchi tomon vendor

---

**22.** Kompaniyaning ba'zi ma'lumotlari public cloudda, maxfiy ma'lumotlari o'z data centerida. Bu qaysi model?

- A) Public cloud
- B) Private cloud
- C) Community cloud
- D) Hybrid cloud

---

**23.** SaaS modelida mijoz nimaga javobgar?

- A) Hamma narsaga — dastur, OS, hardware
- B) Faqat o'z ma'lumotlari va akkauntlariga
- C) OS va runtime ga
- D) Fizikiy serverga

---

## 5-bo'lim — TCP va UDP (24–28)

**24.** Qaysi protokol ma'lumot yetib borishini tasdiqlaydi?

- A) UDP
- B) IP
- C) TCP
- D) ICMP

---

**25.** Video streaming uchun TCP emas UDP ishlatilishining asosiy sababi nima?

- A) UDP shifrlangan
- B) Kechikkan ma'lumot keraksiz, tezlik muhimroq
- C) UDP TCP ga qaraganda xavfsizroq
- D) TCP video ma'lumotlarni qo'llab-quvvatlamaydi

---

**26.** Foydalanuvchi bir vaqtda veb-saytga kirmoqda (port 80) va email tekshirmoqda (port 143). Tarmoq bu ikki trafikni qanday ajratadi?

- A) Har bir ilova uchun alohida IP manzil ishlatiladi
- B) TCP/UDP port raqamlari har bir ilovaning trafikini ajratib turadi
- C) Router har bir ilovani alohida fizikiy kabelga yo'naltiradi
- D) Ikki xil MAC manzil ishlatiladi

---

**27.** Qaysi xususiyat faqat TCP da bor, UDP da yo'q?

- A) Port raqamlar
- B) Oqim nazorati (Flow control)
- C) IP manzillar
- D) Checksum

---

**28.** Multiplexing nima?

- A) Bir vaqtda bir nechta ilovani bir xil ikki qurilma orasida ishlatish
- B) Packet ni kichik bo'laklarga bo'lish
- C) IP manzilni port raqamiga aylantirish
- D) Bir nechta VPC ni birlashtirish

---

## 6-bo'lim — Encapsulation, Socket va Port Raqamlar (29–35)

**29.** Ethernet frame to'g'ri tartibda qaysi?

- A) IP Header → Ethernet Header → TCP Header → Data → Trailer
- B) Ethernet Header → IP Header → TCP Header → Data → Ethernet Trailer
- C) TCP Header → IP Header → Ethernet Header → Data → Trailer
- D) Data → TCP Header → IP Header → Ethernet Header → Trailer

---

**30.** Encapsulation jarayonida Layer 3 (Network) qaysi ma'lumotni qo'shadi?

- A) MAC manzillar
- B) Port raqamlar
- C) IP manzillar
- D) Ilova ma'lumotlari

---

**31.** Socket nima?

- A) Faqat IP manzil
- B) Faqat port raqam
- C) IP manzil + protokol + port raqami kombinatsiyasi
- D) MAC manzil + IP manzil kombinatsiyasi

---

**32.** Klient 10.0.0.1 server 10.0.0.2 ga veb-so'rov yubordi. Qaysi socket to'g'ri?

- A) Klient: 10.0.0.1:80 → Server: 10.0.0.2:3000
- B) Klient: 10.0.0.1:3000 → Server: 10.0.0.2:80
- C) Klient: 10.0.0.1:443 → Server: 10.0.0.2:443
- D) Klient: 10.0.0.1:22 → Server: 10.0.0.2:80

---

**33.** Quyidagi portlarni to'g'ri xizmat bilan moslashtir:

| Port | Xizmat |
| ---- | ------ |
| 80   | ?      |
| 443  | ?      |
| 22   | ?      |
| 25   | ?      |

- A) HTTP, HTTPS, SSH, SMTP
- B) HTTPS, HTTP, SMTP, SSH
- C) SSH, HTTP, HTTPS, SMTP
- D) HTTP, SSH, HTTPS, SMTP

---

**34.** Administrator veb-serverni 80-portdan 8080-portga o'tkazdi. Bu xavfsizlikni oshiradimi?

- A) Ha, chunki 8080 noma'lum port
- B) Yo'q, port o'zgartirish xavfsizlik chorasi emas, firewall kerak
- C) Ha, chunki hujumchilar 8080 ni skaner qilmaydi
- D) Yo'q, chunki 8080 allaqachon band

---

**35.** TCP port 80 va UDP port 80 haqida qaysi ifoda to'g'ri?

- A) Ular bir xil port, protokol farq qilmaydi
- B) Ular turli portlar — bir vaqtda ikki xil ilova ishlatishi mumkin
- C) UDP port 80 mavjud emas
- D) TCP port 80 faqat HTTPS uchun

---

## Javoblar

| #   | Javob | Izoh                                                                                                                            |
| --- | ----- | ------------------------------------------------------------------------------------------------------------------------------- |
| 1   | B     | CDN geografik taqsimlash orqali kechikishni kamaytiradi                                                                         |
| 2   | B     | Concentrator = markaziy shifrlash/deshifrlash nuqtasi                                                                           |
| 3   | C     | NGFW ko'pincha VPN concentrator funksiyasini o'z ichiga oladi                                                                   |
| 4   | C     | VPN = uzoqdan xavfsiz ulanish                                                                                                   |
| 5   | B     | CDN = foydalanuvchiga yaqin kesh serveri                                                                                        |
| 6   | C     | QoS = traffic prioriteti belgilash                                                                                              |
| 7   | B     | TTL=0 → router packet ni o'chiradi                                                                                              |
| 8   | C     | Windows default TTL = 128                                                                                                       |
| 9   | B     | Routing loop — ikki router bir-birini next hop deb ko'rsatadi                                                                   |
| 10  | B     | DNS TTL = sekund, 300 sek = 5 daqiqa kesh                                                                                       |
| 11  | B     | NFV = tarmoq qurilmalarini virtuallashtirish                                                                                    |
| 12  | B     | VPC = bulut ichidagi izolyatsiyalangan virtual tarmoq                                                                           |
| 13  | C     | Transit Gateway = VPC lar orasidagi bulut router                                                                                |
| 14  | B     | NAT Gateway = chiqish bor, kirish yo'q                                                                                          |
| 15  | D     | VPC Endpoint = turli bulut provayderlar orasida to'g'ri ulanish                                                                 |
| 16  | B     | Security List = barcha VPC, NSG = individual VNIC                                                                               |
| 17  | B     | NSG = VNIC darajasida granular nazorat                                                                                          |
| 18  | C     | Gmail = login qilib ishlatiladigan tayyor dastur = SaaS                                                                         |
| 19  | C     | O'zi OS boshqaradi = IaaS                                                                                                       |
| 20  | C     | Platforma ustiga o'z ilovangni qurasан = PaaS                                                                                   |
| 21  | B     | IaaS da OS mijoz javobgarligi                                                                                                   |
| 22  | D     | Public + Private = Hybrid                                                                                                       |
| 23  | B     | SaaS da mijoz faqat ma'lumot va akkauntlarga javobgar                                                                           |
| 24  | C     | TCP = tasdiqlash bor = ishonchli                                                                                                |
| 25  | B     | Kechikkan video frame keraksiz, UDP tezroq                                                                                      |
| 26  | B     | IP manzil faqat qaysi qurilmaga yetkazishni bildiradi. Port raqami esa o'sha qurilma ichida qaysi ilovaga yetkazishni bildiradi |
| 27  | B     | Flow control faqat TCP da                                                                                                       |
| 28  | A     | Multiplexing = bir vaqtda bir nechta ilova                                                                                      |
| 29  | B     | Ethernet Header → IP Header → TCP Header → Data → Trailer                                                                       |
| 30  | C     | Layer 3 = IP manzillar qo'shadi                                                                                                 |
| 31  | C     | Socket = IP + protokol + port kombinatsiyasi                                                                                    |
| 32  | B     | Klient tasodifiy port (3000), server well-known port (80)                                                                       |
| 33  | A     | 80=HTTP, 443=HTTPS, 22=SSH, 25=SMTP                                                                                             |
| 34  | B     | Port o'zgartirish = xavfsizlik emas, firewall kerak                                                                             |
| 35  | B     | TCP 80 ≠ UDP 80, turli portlar                                                                                                  |

---

## Natija

| Ball       | Daraja                                                |
| ---------- | ----------------------------------------------------- |
| 32–35      | Ajoyib — 3-kunga tayyor                               |
| 27–31      | Yaxshi — zaif mavzularni qayta ko'r                   |
| 21–26      | O'rtacha — NFV/VPC va TCP/UDP bo'limlarini qayta o'qi |
| 20 va past | Videolarni qayta ko'rish kerak                        |

---
