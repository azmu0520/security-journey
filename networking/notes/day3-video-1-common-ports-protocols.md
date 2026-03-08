# 3-kun — Video #8: Umumiy Portlar (20:22)

**Sana:** 2026-03-03
**Video:** #8 Common Ports
**Manba:** Professor Messer N10-009

---

## Nima uchun Port Raqamlarini Bilish Kerak?

Tasavvur qil — sen xavfsizlik muhandisisan va serverga kelayotgan trafikni kuzatyapsan.
Bir ulanish 3389-portga keldi.
Ruxsat berasanmi yoki bloklaysanmi?

Buni faqat port 3389 = RDP = biror kishi Windows mashinasini masofadan
boshqarmoqchi ekanligini bilsanggina hal qila olasan.
Admin bo'lishi mumkin. Hujumchi ham bo'lishi mumkin.

**Port raqamlari = tarmoq trafigining tili. Tilni bilmasang, trafikni o'qiy olmaysan.**

---

## Eslab qolishni oson usuli ularni guruhlash

---

## Gruh 1 — "Fayl ko'chirish"

Fayl ko'chirishning uch yo'li. Har birining o'z sababi bor:

| Protokol | Port       | Shifrlangan? | Qachon ishlatiladi                                                                                                    |
| -------- | ---------- | ------------ | --------------------------------------------------------------------------------------------------------------------- |
| **FTP**  | TCP 20, 21 | ❌ Yo'q      | Oddiy fayl uzatish. Port 21 = control, Port 20 = asosiy data                                                          |
| **SFTP** | TCP 22     | ✅ Ha        | FTP ning xavfsiz versiyasi — SSH ustida ishlaydi                                                                      |
| **TFTP** | UDP 69     | ❌ Yo'q      | Login yo'q, parol yo'q, kichik faylni tez yuborish. VoIP telefonlar yoqilganda config faylini shu orqali yuklab oladi |

> Amaliyotda: Wireshark da port 21 da FTP trafigini ko'rsang — username va parol
> ochiq matnda ketayapti. Bir xil tarmoqdagi har qanday hujumchi bularni o'qiy oladi.
> SFTP port 22 = xuddi shunday lekin shifirlangan. Hech kim o'qiy olmaydi.

---

## Gruh 2 — "Masofadagi kompyuterlarni boshqarish"

Ikki yo'l. Biri xavfsiz, biri xavfli:

| Protokol   | Port     | Shifrlangan? | Amaliyot                                                  |
| ---------- | -------- | ------------ | --------------------------------------------------------- |
| **SSH**    | TCP 22   | ✅ Ha        | Standart. Har bir Linux server shuni ishlatadi            |
| **Telnet** | TCP 23   | ❌ Yo'q      | O'lik — parollar ham hammasi oddiy text da ketadi         |
| **RDP**    | TCP 3389 | ✅ Ha        | Windows remote desktop — eng keng tarqalgan hujum nishoni |

> Telnet — xonada parolingni baland ovozda aytish kabi.
> SSH — shifirlangan konvertda shivirlash kabi.
> 2026 yilda hech kim Telnet ishlatmasligi kerak — tarmoqda Telnetni ko'rsang, bu red flag.

> RDP port 3389 — hackerlar internetda bu port doim kuzatib boradi.
> RDP ni internetga ochiq qoldirish = Windows serverlar buzib kirishning
> eng keng tarqalgan yo'li.

---

## Gruh 3 — "Email yubormoq yoki qabul qilish"

Uchta protokol. Har biri boshqa vazifa bajaradi:

| Protokol     | Port    | Vazifasi                                                            |
| ------------ | ------- | ------------------------------------------------------------------- |
| **SMTP**     | TCP 25  | Server → Server email uzatish. oddiy text                           |
| **SMTP TLS** | TCP 587 | Xuddi shunday lekin shifirlangan — 25 o'rniga shuni ishlatish kerak |
| **IMAP**     | TCP 143 | Email ni o'qish, serverda saqlash                                   |
| **POP3**     | TCP 110 | Email ni yuklab olish, serverdan o'chirish                          |

> Pochta bo'limi kabi tasavvur qil:
>
> - SMTP = pochta idoralari orasida xat yetkazuvchi yuk mashinasi
> - IMAP = xatingni pochta bo'limida o'qiysan, u yerda qoladi
> - POP3 = xatingni uyga olib ketasan, pochta bo'limidan yo'qoladi

---

## Gruh 4 — "Internetning orqa fonida nimalar ishlaydi"

Bular jim ishlaydi — hech qachon ko'rmaysan, lekin ularsiz hech narsa ishlamaydi:

| Protokol | Port                                 | Vazifasi                                                 |
| -------- | ------------------------------------ | -------------------------------------------------------- |
| **DNS**  | UDP 53 (katta transfer uchun TCP 53) | google.com → IP manzilga tarjima qiladi                  |
| **DHCP** | UDP 67, UDP 68                       | Ulanganingda qurilmangga avtomatik IP beradi             |
| **NTP**  | UDP 123                              | Barcha qurilmalardagi vaqtlarni sinxronlashtiradi qiladi |

> DNS port 53 — har safar website ochsang DNS query yuboriladi.
> Wireshark oч, `dns` filter qo'y — darhol o'nlab so'rov ko'rasan.
>
> DHCP — port 67 server, port 68 client.
> WiFi ga ulanib avtomatik IP olganingda — bu ikki port orqali DHCP ishlayapti.
>
> NTP — zerikarli ko'rinadi lekin xavfsizlik uchun juda muhim.
> Har bir log fayli timestamp ga ega. Qurilmalar vaqtlari mos kelmasa —
> hujum vaqtida nima bo'lganini bir-biriga ulab bo'lmaydi.
> Ba'zi hackerlar forensics ni chalkashtirish uchun NTP ni buzadi.

---

## Gruh 5 — "Tarmoqni boshqarish va kuzatish"

Bular network admin larning asosiy asboblari:

| Protokol      | Port    | Vazifasi                                                           |
| ------------- | ------- | ------------------------------------------------------------------ |
| **SNMP**      | UDP 161 | Qurilmalarni so'rash — qancha traffic? CPU qancha joy band qilish? |
| **SNMP Trap** | UDP 162 | Qurilma muammoni o'zi management bo'limlarga xabar qiladi          |
| **Syslog**    | UDP 514 | Qurilmalar log fayllarini bir markaziy joyga yuboradi              |

> SNMP versiyalari xavfsizlik uchun muhim:
>
> - v1 va v2 = encryption yo'q, oddiy text — xavfli
> - v3 = shifirlangan, authenticated — shuni ishlatish kerak
>
> Syslog + SIEM = security monitoring ning asosi.
> Har bir firewall, router, switch loglarini syslog orqali
> markaziy SIEM ga yuboradi.
> Security guruhlari hujumlarni shu orqali real vaqtda aniqlaydi.

---

## Gruh 6 — "Tarmoqdagi ma'lumot va resurslarga kirish"

| Protokol   | Port           | Vazifasi                                              |
| ---------- | -------------- | ----------------------------------------------------- |
| **HTTP**   | TCP 80         | Web traffic, oddiy text                               |
| **HTTPS**  | TCP 443        | Web traffic, shifirlangan (SSL/TLS)                   |
| **LDAP**   | TCP 389        | User/device directory ni so'rash (Active Directory)   |
| **LDAPS**  | TCP 636        | Xuddi shunday lekin shifirlangan                      |
| **SMB**    | TCP 445        | Windows file sharing, printerlar, authentication      |
| **MS-SQL** | TCP 1433       | Microsoft SQL Server database                         |
| **SIP**    | TCP 5060, 5061 | VoIP — telefon qo'ng'iroqlarini boshlaydi va tugatadi |

> SMB port 445 — bu xavfsizlikda mashhur.
> 2017 yilgi WannaCry ransomware hujumi 445-port ochiq bo'lgan
> mashinalar orqali tarqaldi.
> Bir necha soatda yuz minglab mashina zararlandi. Hammasi bitta port orqali.
>
> LDAP = Windows Active Directory qanday ishlashi.
> Kompaniya kompyuteriga login qilganingda — LDAP directory ni so'rab
> username va paroling to'g'riligini tekshiradi.

---

## Master Jadval — Barcha Portlar

| Port | Protokol      | Transport | Shifrlangan        |
| ---- | ------------- | --------- | ------------------ |
| 20   | FTP (data)    | TCP       | ❌                 |
| 21   | FTP (control) | TCP       | ❌                 |
| 22   | SSH / SFTP    | TCP       | ✅                 |
| 23   | Telnet        | TCP       | ❌                 |
| 25   | SMTP          | TCP       | ❌                 |
| 53   | DNS           | UDP / TCP | ❌                 |
| 67   | DHCP (server) | UDP       | ❌                 |
| 68   | DHCP (client) | UDP       | ❌                 |
| 69   | TFTP          | UDP       | ❌                 |
| 80   | HTTP          | TCP       | ❌                 |
| 110  | POP3          | TCP       | ❌                 |
| 123  | NTP           | UDP       | ❌                 |
| 143  | IMAP          | TCP       | ❌                 |
| 161  | SNMP          | UDP       | ❌ (v1/v2) ✅ (v3) |
| 162  | SNMP Trap     | UDP       | ❌ (v1/v2) ✅ (v3) |
| 389  | LDAP          | TCP       | ❌                 |
| 443  | HTTPS         | TCP       | ✅                 |
| 445  | SMB           | TCP       | ❌                 |
| 514  | Syslog        | UDP       | ❌                 |
| 587  | SMTP TLS      | TCP       | ✅                 |
| 636  | LDAPS         | TCP       | ✅                 |
| 1433 | MS-SQL        | TCP       | ❌                 |
| 3389 | RDP           | TCP       | ✅                 |
| 5060 | SIP           | TCP       | ❌                 |
| 5061 | SIP TLS       | TCP       | ✅                 |

---

## Xavfsizlik Naqshi — Shu Narsaga E'tibor Ber

Jadvalga yana bir qarang. Qancha port ma'lumotni
**shifirlanmagan oddiy text da** yuborayotganini ko'ryapsanmi?

FTP, Telnet, SMTP, DNS, DHCP, HTTP, LDAP, SMB, Syslog...

**Aynan shu sabab network security mavjud.**
Bir xil tarmoqdagi hujumchi bularning hammasini capture qilib o'qiy oladi.
Security mutaxassisi sifatida vazifang = qaysi portlar xavfli ekanini bilish,
qayerda encryption yo'qligini aniqlash, nima bloklanishi kerakligini bilish.

---

## Asosiy Atamalar

- **FTP** — File Transfer Protocol, TCP 20/21, encryption yo'q
- **SFTP** — Secure FTP, SSH ustida ishlaydi, TCP 22
- **TFTP** — Trivial FTP, UDP 69, authentication yo'q, tez kichik transfer
- **SSH** — Secure Shell, TCP 22, shifirlangan remote terminal
- **Telnet** — TCP 23, unshifirlangan remote terminal, ishlatma
- **SMTP** — Simple Mail Transfer Protocol, TCP 25 (oddiy) / 587 (TLS)
- **IMAP** — Email o'qish, serverda qoladi, TCP 143
- **POP3** — Email download, serverdan o'chiradi, TCP 110
- **DNS** — Domain Name System, UDP/TCP 53
- **DHCP** — Dynamic Host Configuration Protocol, UDP 67/68
- **NTP** — Network Time Protocol, UDP 123
- **SNMP** — Simple Network Management Protocol, UDP 161/162
- **Syslog** — Log transfer protokoli, UDP 514
- **HTTP/HTTPS** — Web traffic, TCP 80 / 443
- **LDAP/LDAPS** — Directory access protokoli, TCP 389 / 636
- **SMB** — Windows file sharing, TCP 445
- **RDP** — Remote Desktop Protocol, TCP 3389
- **SIP** — Session Initiation Protocol (VoIP), TCP 5060/5061
- **MS-SQL** — Microsoft SQL Server, TCP 1433
- **SIEM** — Security Information and Event Manager, syslog data ni yig'adi
