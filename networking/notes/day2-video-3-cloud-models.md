# 2-kun — Video #6: Bulut Modellari (5:23)

**Sana:** 2026-03-01
**Video:** #6 Cloud Models
**Manba:** Professor Messer N10-009

---

## Umumiy Manzara

Uchta bulut xizmat modeli — farqi **kim nima uchun javobgar** ekanida.
Qancha ko'p nazorat xohlasang, shuncha ko'p javobgarlik olasan.

---

## Joylashtirish Modellari (Deployment Models)

| Model               | Kim kiradi                                           |
| ------------------- | ---------------------------------------------------- |
| **Public cloud**    | Internetdagi har kim                                 |
| **Private cloud** — | Faqat ichki foydalanish — virtual data senterlar aro |
| **Hybrid cloud**    | Ikkalasi ham — ko'p tashkilotlar shunday ishlaydi    |

---

## Uchta Xizmat Modeli (Service Models)

### SaaS — Software as a Service

- Brauzerda login qil, ilovadan foydalан — tamom
- Boshqa birov yaratgan , boshqaradi, ma'lumotlarni saqlaydigan ilova
- Local o'rnatish yo'q, yangilash yo'q, dasturlash yo'q
- **Misollar:** Gmail, Office 365 ...

### IaaS — Infrastructure as a Service

- Bulutda hardware olasan (compute, storage, tarmoq)
- O'zing OS, dastur o'rnatasan, ma'lumotlarni boshqarasan
- **HaaS — Hardware as a Service** deb ham ataladi
- Kirish va xavfsizlik ustidan ko'proq nazorat
- **Misol:** AWS EC2, web serverda vaqt sotib olish

### PaaS — Platform as a Service

- SaaS va IaaS orasidagi o'rta yo'l
- Provayder qurilish bloklari va asboblar beradi
- Sen platforma ustiga o'z ilovangni qurib boshqarasan
- Provayder asosiy mexanizmni boshqaradi
- **Misol:** Salesforce.com

---

## Javobgarlik Matritsasi

| Qatlam                                     | On-Prem | IaaS      | PaaS       | SaaS      |
| ------------------------------------------ | ------- | --------- | ---------- | --------- |
| Ma'lumotlar & Data                         | Sen     | Sen       | Sen        | Sen       |
| Akkauntlar/Qurilmalar & Accounts/Devices   | Sen     | Sen       | Sen        | Sen       |
| Ilovalar & Applications                    | Sen     | Sen       | Birgalikda | Provayder |
| Tarmoq nazorati & Network controls         | Sen     | Sen       | Birgalikda | Provayder |
| Fizikiy host & Physical host               | Sen     | Provayder | Provayder  | Provayder |
| Fizikiy tarmoq & Physical network          | Sen     | Provayder | Provayder  | Provayder |
| Fizikiy data center & Physical data center | Sen     | Provayder | Provayder  | Provayder |

> Xavfsizlik nuqtai nazaridan: "Birgalikda javobgarlik" — xavfsizlik buzilishlari ko'p shu yerda sodir bo'ladi.
> Javobgarliging qayerda tugab, provayderniki qayerda boshlanishini aniq bilish juda muhim.

---

## Asosiy Atamalar

- **SaaS** — Software as a Service, faqat login qilib ishlatasan
- **IaaS** — Infrastructure as a Service, OS dan yuqorisini sen boshqarasan
- **PaaS** — Platform as a Service, provayder platformasi ustiga o'z ilovangni qurasан
- **HaaS** — Hardware as a Service, IaaS ning boshqa nomi
- **Public cloud** — internetdagi hamma uchun ochiq
- **Private cloud** — faqat ichki, o'z virtual data centring
- **Hybrid cloud** — public va private aralashmasi
- **Shared responsibility** — ba'zi qatlamlar sen, ba'zilari provayder tomonidan boshqariladi

---

_Keyingi video: #7 — IP ga Kirish_
