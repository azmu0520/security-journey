# 2-kun — Video #5: Designing the Cloud (9:49)

**Sana:** 2026-03-01
**Video:** #5 Designing the Cloud
**Manba:** Professor Messer N10-009

---

## Umumiy Manzara

Bulut hisoblash texnologiyaga yondashuvni tubdan o'zgartirdi. Bir tugma bosish bilan ilovalar va xizmatlar deploy qilinadi, resurslar deyarli cheksiz, va dunyo bo'ylab kirib boradi. Bu video — bulut tarmoq infratuzilmasi qanday qurilgani, VPC lar, security groups va ular orasidagi ulanish haqida.

---

## NFV — Network Function Virtualization

- 100 ta fizikiy server → 1 ta katta fizikiy server ichida 100 ta **virtual server**
- Tarmoq qurilmalari ham virtuallashadi: router, switch, firewall — barchasi virtual
- Xuddi shunday funksionallik, faqat endi **virtual appliance** sifatida
- Hypervisor orqali barcha network interface va konfiguratsiyalar ko'rinadi
- Yangi firewall yoki switch deploy qilish = tugma bosish

> Web dev bog'liqlik: AWS yoki Azure da VPC sozlagan bo'lsang — aynan NFV ustida ishlayapsan

---

## VPC — Virtual Private Cloud

- Bulut ichidagi **izolyatsiyalangan virtual tarmoq**
- Odatiy tarkib: web server, database server, load balancer, virtual switch/router, virtual firewall
- Katta muhitlarda har bir ilova instance yoki kompaniya bo'limi uchun **alohida VPC**
- VPC lar bir-biridan ajratilgan, lekin har biri alohida virtual appliance sifatida boshqariladi

---

## VPC Ulanish Turlari

| Komponent            | Vazifasi                                                               |
| -------------------- | ---------------------------------------------------------------------- |
| **Transit Gateway**  | VPC larni bir-biriga ulaydi — bulutdagi router                         |
| **VPN Connection**   | Uzoq sayt yoki ish stantsiyasidan VPC ga shifrlangan tunnel            |
| **Internet Gateway** | VPC ni internetga ochadi — hamma kirishi mumkin                        |
| **NAT Gateway**      | VPC dan internetga chiqish uchun, lekin tashqaridan kirishni bloklaydi |
| **VPC Endpoint**     | Turli bulut provayderlar orasida to'g'ridan-to'g'ri ulanish            |

### Qachon qaysi ishlatiladi:

- Xodim uydan korporativ VPC ga kirmoqchi → **VPN + Transit Gateway**
- Public veb-sayt deploy qilmoqchi → **Internet Gateway**
- Private database tashqi API ga so'rov yubormoqchi → **NAT Gateway**
- AWS dagi VPC Oracle Cloud dagi VPC ga ulanmoqchi → **VPC Endpoint**

---

## Bulut Xavfsizligi — Security Groups va Lists

### Network Security List

- Barcha VPC larga **avtomatik** qo'llaniladi
- Port raqamlari va protokollar asosida (TCP/UDP)
- Layer 3 manzillar ham: individual IP, CIDR blok, IPv4/IPv6 range
- **Kamchilik:** granularlik yo'q — har bir qoidа barcha virtual tarmoqlarga tushadi, kerak bo'lmasa ham

```
Misol qoidalar:
Inbound — TCP port 443 — Any IP   (HTTPS)
Inbound — TCP port 22  — Any IP   (SSH)
```

### Network Security Group (NSG)

- **Individual VNIC** (Virtual Network Interface Card) darajasida qoidalar
- Bir xil subnet ichida turli interface kartalar uchun turli qoidalar
- **Ustunlik:** koplab granular — aynan kerakli joyga aynan kerakli qoida
- **Kamchilik:** boshqarish murakkablashadi

|                     | Security List  | Security Group  |
| ------------------- | -------------- | --------------- |
| Qo'llanilish        | Barcha VPC lar | Individual VNIC |
| Granularlik         | Past           | Yuqori          |
| Boshqarish osonligi | Oson           | Murakkab        |

> Xavfsizlik nuqtai nazaridan: noto'g'ri sozlangan security group — eng keng tarqalgan bulut zaifliklaridan biri. `0.0.0.0/0` dan SSH (port 22) ochiq qoldirilishi = real hujum vektori

---

## Asosiy Atamalar

- **NFV** — Network Function Virtualization, router/switch/firewall larni virtual qilish
- **VPC** — Virtual Private Cloud, bulut ichidagi izolyatsiyalangan virtual tarmoq
- **Transit Gateway** — VPC larni birlashtiruvchi bulut router
- **Internet Gateway** — VPC ni ochiq internetga ulash
- **NAT Gateway** — VPC dan internetga chiqish, tashqaridan kirishni bloklab
- **VPC Endpoint** — turli bulut provayderlar orasida to'g'ri ulanish
- **Multitenancy** — ko'p mijoz bir xil infratuzilmani bo'lishadi
- **Security List** — barcha VPC larga qo'llaniladigan firewall qoidalari
- **Security Group (NSG)** — individual VNIC darajasidagi granular xavfsizlik qoidalari
- **VNIC** — Virtual Network Interface Card

---
