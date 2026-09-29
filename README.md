<div align="center">

<img src="assets/banner.svg" alt="Monero: Privacy in 90 Seconds" width="100%">

<br>

![HTML5](https://img.shields.io/badge/HTML5-ff6600?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-2965f1?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-f7df1e?style=for-the-badge&logo=javascript&logoColor=black)
![Dependencies](https://img.shields.io/badge/Dependencies-None-2ea44f?style=for-the-badge)

### [▶ Open the Live Demo](https://vinayak2206.github.io/Monero-Demo/)

</div>

---

## 📌 Table of Contents
- [About](#-about)
- [Features](#-features)
- [The Payment Flow](#-the-payment-flow)
- [What Each Person Sees](#-what-each-person-sees)
- [Monero vs a Normal Blockchain](#-monero-vs-a-normal-blockchain)
- [The Technology Behind It](#-the-technology-behind-it)
- [How to Present the Demo](#-how-to-present-the-demo)
- [Run and Deploy](#-run-and-deploy)
- [Project Structure](#-project-structure)
- [Team](#-team)
- [References](#-references)

---

## 📖 About

This is the live demo for our **Monero (XMR) case study** in *Principles of Blockchain Technology*.

Most blockchains are fully public: anyone can see who paid whom and how much. **Monero is private by default.** This demo shows how, using one example payment where **Alice sends 1 XMR to Bob**.

You click through **six steps**. At each step, one more detail of the public ledger record becomes hidden. You can also switch between three viewpoints (**Stranger**, **Bob** and **Alice**) to see who can see what.

> ⚠️ **This is a learning simulation.** All addresses, blocks and values are made-up examples. No real money, wallet or network is used.

---

## ✨ Features

| | Feature | What it does |
|---|---|---|
| 🪜 | **6-step walkthrough** | Follows a Monero payment from wallet to block |
| 👀 | **3 viewpoints** | Switch between Stranger, Bob and Alice |
| 🔗 | **Ring signature visual** | Shows 16 possible senders, with the real one highlighted for Alice |
| 📒 | **Live ledger record** | Sender, receiver and amount are hidden step by step |
| 🎤 | **Presenter script** | A short line to say out loud at every step |
| ⌨️ | **Auto-play and keyboard** | Use the ← and → keys, or press Auto-play |
| 📴 | **Works offline** | One HTML file, no libraries, no internet needed |
| 📱 | **Responsive** | Works on laptop, tablet and phone, in light and dark mode |

---

## 🔄 The Payment Flow

The path of Alice's payment from her wallet to Bob's wallet, and what each step hides:

<div align="center">
<img src="assets/payment-flow.svg" alt="Flowchart of a Monero payment: stealth address, ring signature, RingCT, node verification, mining, and Bob's wallet detecting the payment" width="820">
</div>

---

## 🕵️ What Each Person Sees

<div align="center">
<img src="assets/visibility.svg" alt="Table showing what a stranger, Bob and Alice can see: sender, receiver and amount" width="820">
</div>

A stranger looking at the ledger can see that **a payment happened**, but **not who sent it, who received it, or how much**.

---

## ⚖️ Monero vs a Normal Blockchain

| | Normal public blockchain (e.g. Bitcoin) | Monero (XMR) |
|---|---|---|
| **Sender** | Visible | Hidden in a ring of 16 |
| **Receiver** | Visible address | One-time stealth address |
| **Amount** | Visible | Hidden with RingCT |
| **Privacy** | Optional, needs extra tools | On by default |
| **Mining** | Specialised hardware is common | RandomX, made for normal computers |

---

## 🧠 The Technology Behind It

| Step | Technology | What it does |
|:---:|---|---|
| 1 | **Stealth addresses** | A fresh one-time address for every payment, so payments cannot be linked to Bob |
| 2 | **Ring signatures** | Proves one of 16 coins signed, without saying which one |
| 3 | **RingCT** | Hides the amount but still proves inputs equal outputs, so no coins appear from nothing |
| 4 | **Key images** | Stops the same coin being spent twice, without revealing which coin it is |
| 5 | **Node verification** | Every node checks the proofs. No one has to trust Alice |
| 6 | **RandomX mining** | A mining method made for normal computers, which keeps mining open to more people |

---

## 🎬 How to Present the Demo

**About 90 seconds. One person talks, one person clicks.**

1. Start on the **Stranger** tab and press **Next** through steps 1 to 4. Point at each field as it turns hidden.
2. At **step 3**, click **Alice** to show her real coin, then go back to **Stranger**.
3. At **step 4**, click **Bob** to show he can still see 1 XMR.
4. Finish **steps 5 and 6** to show the network checks and the new block.
5. Say the takeaway: *"Same kind of payment, but a stranger can't see who paid whom or how much."*

<!--
SCREENSHOTS (optional): take screenshots of the demo, put them in the assets folder, then remove this comment markers and use:

<div align="center">
<img src="assets/demo-step1.png" width="45%"> <img src="assets/demo-step4.png" width="45%">
</div>
-->

---

## 🚀 Run and Deploy

**Run locally:** double-click `index.html`. It needs no install, no server and no internet.

**Live site:** https://vinayak2206.github.io/Monero-Demo/

**Deploy your own copy (free):**
- **GitHub Pages:** *Settings → Pages →* branch `main` and folder `/ (root)`
- **Netlify Drop:** drag the folder onto [app.netlify.com/drop](https://app.netlify.com/drop)
- **Vercel:** import the repository at [vercel.com](https://vercel.com)

---

## 📁 Project Structure

```text
Monero-Demo/
├── index.html          # the whole demo (HTML, CSS and JavaScript)
├── README.md           # this file
└── assets/
    ├── banner.svg          # header image
    ├── payment-flow.svg    # payment flowchart
    └── visibility.svg      # who can see what
```

---

## 👥 Team

| Name | Role |
|---|---|
| Member 1 | Research and presentation |
| Member 2 | Research and presentation |
| Member 3 | Research and presentation |
| Member 4 | Research and presentation |
| Member 5 | Research and demo |

**Course:** Principles of Blockchain Technology

---

## 📚 References

- Official Monero website: [getmonero.org](https://www.getmonero.org)
- Monero documentation: [docs.getmonero.org](https://docs.getmonero.org)
- Monero Research Lab technical papers
- Monero blockchain explorer: [xmrchain.net](https://xmrchain.net)
- Course lecture materials, Principles of Blockchain Technology

---

<div align="center">

Built for education. Not financial advice.

</div>
