# Week 1 — Network+ Foundations

> **Goal:** Build a solid networking foundation through Professor Messer videos, hands-on Wireshark, TryHackMe rooms, and intro Linux via OverTheWire Bandit.

---

## Progress Tracker

| Day   | Topic                            | Messer Videos      | Practical                               | Status |
| ----- | -------------------------------- | ------------------ | --------------------------------------- | ------ |
| Day 1 | Setup + OSI Model                | #1, #2, #3         | TryHackMe: OSI Model room               | ⬜     |
| Day 2 | TCP/IP + Wireshark               | #4, #5, #6, #7     | Wireshark capture + THM: HTTP in Detail | ⬜     |
| Day 3 | Ports + Protocols + Linux starts | #8, #9, #10, #11   | OverTheWire Bandit lvl 0–1              | ⬜     |
| Day 4 | Cabling + Connectors             | #12–#17            | DNS commands in terminal + Wireshark    | ⬜     |
| Day 5 | Topologies + IP + Binary         | #18, #19, #20, #21 | Packet Tracer: first tiny network       | ⬜     |
| Day 6 | Subnetting Day                   | #22, #23, #24, #25 | subnettingpractice.com drills           | ⬜     |
| Day 7 | Review + Consolidate             | #26                | Practice quiz + week reflection         | ⬜     |

> Update status: ⬜ Not started → 🔄 In Progress → ✅ Done

---

## Day 1 — Setup + OSI Model (3–4 hrs)

### Hour 1 — Setup Everything First

Get the environment ready before touching any content. Removing friction matters.

- [ ] Install Wireshark on Linux
- [ ] Create TryHackMe account → [tryhackme.com](https://tryhackme.com)
- [ ] Create this GitHub repo (`security-journey`) and push initial README
- [ ] Create Trello board with columns: `This Week`, `In Progress`, `Done`, `Today I Learned`

### Hour 2 — Professor Messer Videos

| #   | Title                                  | Length |
| --- | -------------------------------------- | ------ |
| 1   | How to Pass Your N10-009 Network+ Exam | 7:40   |
| 2   | Understanding the OSI Model            | 13:51  |
| 3   | Networking Devices                     | 14:31  |

Take notes **directly in this repo** as you watch. Don't use paper. Commit them after.

### Hour 1.5 — Practical

- [ ] TryHackMe room: **"OSI Model"** (search it — free, short)

### End of Day

- [ ] Write one sentence in your Trello "Today I Learned" card

---

## Day 2 — TCP/IP + Your First Wireshark Capture (4–5 hrs)

### Professor Messer Videos

| #   | Title                | Length |
| --- | -------------------- | ------ |
| 4   | Networking Functions | 13:25  |
| 5   | Designing the Cloud  | 9:49   |
| 6   | Cloud Models         | 5:23   |
| 7   | Introduction to IP   | 14:10  |

### Practical

**Wireshark — your first real capture:**

1. Open Wireshark
2. Browse the web normally and capture traffic
3. Find an HTTP or DNS packet, click it, expand the layers
4. You'll see the OSI model from yesterday sitting right there in real traffic — this is the moment it clicks

- [ ] TryHackMe room: **"HTTP in Detail"** — you know HTTP from your web dev days, but now you're seeing it from the attacker's angle

---

## Day 3 — Ports, Protocols + Linux Begins (4–5 hrs)

### Professor Messer Videos

| #   | Title                  | Length |
| --- | ---------------------- | ------ |
| 8   | Common Ports           | 20:22  |
| 9   | Other Useful Protocols | 8:26   |
| 10  | Network Communication  | 3:55   |
| 11  | Wireless Networking    | 6:37   |

### Practical

- [ ] **OverTheWire Bandit — Level 0 and Level 1**
  - Site: [overthewire.org/wargames/bandit](https://overthewire.org/wargames/bandit)
  - It's a game. Treat it like one. Google is allowed and expected.
  - This is your Linux training starting now — disguised as fun

---

## Day 4 — Cabling + DNS in the Wild (3–4 hrs)

### Professor Messer Videos

| #   | Title                | Length |
| --- | -------------------- | ------ |
| 12  | Ethernet Standards   | 4:04   |
| 13  | Optical Fiber        | 3:55   |
| 14  | Copper Cabling       | 7:21   |
| 15  | Network Transceivers | 4:51   |
| 16  | Fiber Connectors     | 3:56   |
| 17  | Copper Connectors    | 3:31   |

### Practical — DNS in your terminal

Run these commands and watch what happens:

```bash
nslookup google.com
dig google.com
traceroute google.com
```

Then open Wireshark **at the same time** and watch the DNS query happen live while you run `dig`. You're connecting theory to what's actually on the wire.

- [ ] TryHackMe room: **"DNS in Detail"**
- [ ] OverTheWire Bandit levels 2–3

---

## Day 5 — Topologies + Binary + IP Addressing (4 hrs)

### Professor Messer Videos

| #   | Title                 | Length |
| --- | --------------------- | ------ |
| 18  | Network Topologies    | 4:42   |
| 19  | Network Architectures | 4:53   |
| 20  | Binary Math           | 9:15   |
| 21  | IPv4 Addressing       | 11:06  |

### Practical — Build Your First Network

- [ ] Download **Cisco Packet Tracer** (free, needs free account at netacad.com)
- [ ] Build: two computers → one switch → make them ping each other
- [ ] Sounds simple but building it yourself locks in the mental model
- [ ] OverTheWire Bandit levels 4–6

---

## Day 6 — Subnetting Day (4–5 hrs)

> This is the most important and most mentally taxing day of the week. Push through it.

### Professor Messer Videos

| #   | Title                              | Length |
| --- | ---------------------------------- | ------ |
| 22  | Classful Subnetting                | 10:58  |
| 23  | IPv4 Subnet Masks                  | 9:00   |
| 24  | Calculating IPv4 Subnets and Hosts | 9:46   |
| 25  | Magic Number Subnetting            | 21:09  |

> Watch videos twice if needed. Do the math on paper first, not in your head.

### Practical

- [ ] **subnettingpractice.com** — free, interactive, drill it until it feels automatic
- [ ] Run `ss -tulnp` in your terminal — see all open ports on your own machine. Look up what each service is. This is exactly what attackers do during recon, but you're doing it on yourself.
- [ ] TryHackMe room: **"Intro to Networking"** (if not already done)

---

## Day 7 — Review + Consolidate (3 hrs)

### Professor Messer Videos

| #   | Title                   | Length |
| --- | ----------------------- | ------ |
| 26  | Seven Second Subnetting | 17:03  |

> No new material beyond this. Today is for solidifying, not adding.

### Review Tasks

- [ ] Go back to your weakest topic from the week (subnetting usually wins)
- [ ] Do 20 more subnetting practice problems at subnettingpractice.com
- [ ] Take a free Network+ practice quiz online — 20–30 questions. Don't stress the score, use it to spot gaps
- [ ] Update your Trello board and plan Week 2 cards

### Week 1 Reflection

Write a short paragraph in `networking/week1-reflection.md` covering:

- What clicked this week?
- What didn't?
- What surprised you?
- Any topics you want to revisit?

Commit it. This becomes your reference when you're prepping for the exam later.

---

## Resources

| Resource                 | Link                                                                       | Used For                      |
| ------------------------ | -------------------------------------------------------------------------- | ----------------------------- |
| Professor Messer N10-009 | [professormesser.com](https://www.professormesser.com)                     | Main video content            |
| TryHackMe                | [tryhackme.com](https://tryhackme.com)                                     | Guided practical labs         |
| OverTheWire Bandit       | [overthewire.org/wargames/bandit](https://overthewire.org/wargames/bandit) | Linux fundamentals (gamified) |
| Subnetting Practice      | [subnettingpractice.com](https://subnettingpractice.com)                   | Subnetting drills             |
| Cisco Packet Tracer      | [netacad.com](https://www.netacad.com)                                     | Network simulation            |
| Wireshark                | [wireshark.org](https://www.wireshark.org)                                 | Packet capture + analysis     |

---

_Part of my [security-journey](../README.md) — transitioning from web full-stack to security._
