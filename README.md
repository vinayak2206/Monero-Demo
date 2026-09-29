<div align="center">

# 🔐 Monero: Privacy in 90 Seconds

### An interactive demo showing how Monero (XMR) hides **who paid**, **who received** and **how much**

<br>

[![Live Demo](https://img.shields.io/badge/▶_OPEN_LIVE_DEMO-monero--demo.vercel.app-ff6600?style=for-the-badge&logo=vercel&logoColor=white)](https://monero-demo.vercel.app)

![HTML5](https://img.shields.io/badge/HTML5-e34f26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572b6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-f7df1e?style=flat-square&logo=javascript&logoColor=black)
![Vercel](https://img.shields.io/badge/Deployed_on-Vercel-000000?style=flat-square&logo=vercel&logoColor=white)
![Dependencies](https://img.shields.io/badge/Dependencies-None-2ea44f?style=flat-square)

**Course:** Principles of Blockchain Technology &nbsp;•&nbsp; **Topic:** Monero (XMR) Case Study

</div>

---

## 📌 Table of Contents

[About](#-about) • [Features](#-features) • [Payment Flow](#-the-payment-flow) • [Who Sees What](#-who-sees-what) • [Monero vs Bitcoin](#-monero-vs-a-normal-blockchain) • [Technology](#-the-technology-behind-it) • [Presenting](#-how-to-present-the-demo) • [Run and Deploy](#-run-and-deploy) • [Team](#-team) • [References](#-references)

---

## 📖 About

Most blockchains are fully public: anyone can see who paid whom and how much. **Monero is private by default.**

This demo shows how, using one example payment where **Alice sends 1 XMR to Bob**. You click through **six steps**, and at each step one more detail of the public ledger record becomes hidden. You can also switch between three viewpoints (**Stranger**, **Bob**, **Alice**) to see who can see what.

> ⚠️ **This is a learning simulation.** All addresses, blocks and values are made-up examples. No real money, wallet or network is used.

### 👉 Try it now: **[monero-demo.vercel.app](https://monero-demo.vercel.app)**

---

## ✨ Features

|     | Feature                    | What it does                                                       |
| :-: | -------------------------- | ------------------------------------------------------------------ |
| 🪜  | **6-step walkthrough**     | Follows a Monero payment from wallet to block                      |
| 👀  | **3 viewpoints**           | Switch between Stranger, Bob and Alice                             |
| 🔗  | **Ring signature visual**  | Shows 16 possible senders, with the real one highlighted for Alice |
| 📒  | **Live ledger record**     | Sender, receiver and amount get hidden step by step                |
| 🎤  | **Presenter script**       | A short line to say out loud at every step                         |
| ⌨️  | **Auto-play and keyboard** | Use the ← and → keys, or press Auto-play                           |
| 📴  | **Works offline**          | One HTML file, no libraries, no internet needed                    |
| 📱  | **Responsive**             | Works on laptop, tablet and phone, in light and dark mode          |

---

## 🔄 The Payment Flow

The path of Alice's payment from her wallet to Bob's wallet, and what each step hides:

```text
┌──────────────────────────────────────────────────────────────┐
│ START   Alice types Bob's address and 1 XMR in her wallet    │
└──────────────────────────────────────────────────────────────┘
                               │
                               ▼
┌──────────────────────────────────────────────────────────────┐
│ STEP 1  STEALTH ADDRESS                                      │
│          A one-time address is made for Bob.                 │
│          Hides the RECEIVER.                                 │
└──────────────────────────────────────────────────────────────┘
                               │
                               ▼
┌──────────────────────────────────────────────────────────────┐
│ STEP 2  RING SIGNATURE                                       │
│          Alice's real coin is mixed with 15 decoys.          │
│          Hides the SENDER.                                   │
└──────────────────────────────────────────────────────────────┘
                               │
                               ▼
┌──────────────────────────────────────────────────────────────┐
│ STEP 3  RingCT                                               │
│          The amount is locked inside a commitment.           │
│          Hides the AMOUNT (the math still adds up).          │
└──────────────────────────────────────────────────────────────┘
                               │
                               ▼
┌──────────────────────────────────────────────────────────────┐
│ STEP 4  NODES VERIFY                                         │
│          Valid signature? Coin not spent before?             │
│          Amounts balance? If not, it is rejected.            │
└──────────────────────────────────────────────────────────────┘
                               │
                               ▼
┌──────────────────────────────────────────────────────────────┐
│ STEP 5  MINERS ADD A BLOCK (RandomX)                         │
│          A new block arrives about every 2 minutes.          │
└──────────────────────────────────────────────────────────────┘
                               │
                               ▼
┌──────────────────────────────────────────────────────────────┐
│ END     Bob's wallet finds the payment with his private view key│
└──────────────────────────────────────────────────────────────┘
```

---

## 🕵️ Who Sees What

|              | 🕶️ Stranger                            | 👨 Bob                 | 👩 Alice               |
| ------------ | -------------------------------------- | ---------------------- | ---------------------- |
| **Sender**   | ❌ 1 of 16, unknown                    | ❌ Not revealed to him | ✅ Knows her real coin |
| **Receiver** | ❌ One-time address, not linked to Bob | ✅ Sees it is his      | ✅ Knows she paid Bob  |
| **Amount**   | ❌ Hidden                              | ✅ Sees 1 XMR          | ✅ Knows 1 XMR         |

✅ = can see &nbsp;&nbsp; ❌ = hidden

A stranger looking at the ledger can see that **a payment happened**, but **not who sent it, who received it, or how much.**

---

## ⚖️ Monero vs a Normal Blockchain

|              | Normal public blockchain (e.g. Bitcoin) | Monero (XMR)                       |
| ------------ | --------------------------------------- | ---------------------------------- |
| **Sender**   | 👁️ Visible                              | 🔒 Hidden in a ring of 16          |
| **Receiver** | 👁️ Visible address                      | 🔒 One-time stealth address        |
| **Amount**   | 👁️ Visible                              | 🔒 Hidden with RingCT              |
| **Privacy**  | Optional, needs extra tools             | On by default                      |
| **Mining**   | Specialised hardware is common          | RandomX, made for normal computers |

---

## 🧠 The Technology Behind It

| Step | Technology            | What it does                                                                            |
| :--: | --------------------- | --------------------------------------------------------------------------------------- |
|  1   | **Stealth addresses** | A fresh one-time address for every payment, so payments cannot be linked to Bob         |
|  2   | **Ring signatures**   | Proves one of 16 coins signed, without saying which one                                 |
|  3   | **RingCT**            | Hides the amount but still proves inputs equal outputs, so no coins appear from nothing |
|  4   | **Key images**        | Stops the same coin being spent twice, without revealing which coin it is               |
|  5   | **Node verification** | Every node checks the proofs. No one has to trust Alice                                 |
|  6   | **RandomX mining**    | A mining method made for normal computers, which keeps mining open to more people       |

---

## 🎬 How to Present the Demo

**About 90 seconds. One person talks, one person clicks.**

1. Open **[monero-demo.vercel.app](https://monero-demo.vercel.app)** before you start.
2. Stay on the **Stranger** tab and press **Next** through steps 1 to 4. Point at each field as it turns hidden.
3. At **step 3**, click **Alice** to show her real coin, then go back to **Stranger**.
4. At **step 4**, click **Bob** to show he can still see 1 XMR.
5. Finish **steps 5 and 6** to show the network checks and the new block.
6. Say the takeaway: _"Same kind of payment, but a stranger can't see who paid whom or how much."_

> 💡 **Backup plan:** keep `index.html` saved on the laptop. It opens offline with a double-click if the wifi fails.

---

## 🚀 Run and Deploy

**Live site:** [monero-demo.vercel.app](https://monero-demo.vercel.app)

**Run locally:** download the repo and double-click `index.html`. It needs no install, no server and no internet.

**Deploy your own copy (free):**

- **Vercel:** import this repository at [vercel.com](https://vercel.com). Every push to `main` redeploys automatically.
- **GitHub Pages:** _Settings → Pages →_ branch `main` and folder `/ (root)`
- **Netlify Drop:** drag the folder onto [app.netlify.com/drop](https://app.netlify.com/drop)

**Project structure**

```text
Monero-Demo/
├── index.html    # the whole demo (HTML, CSS and JavaScript)
└── README.md     # this file
```

---

## 👥 Team

| Name     | Role                            |
| -------- | ------------------------------- |
| Member 1 | Research, presentation and demo |
| Member 2 | Research and presentation       |
| Member 3 | Research and presentation       |
| Member 4 | Research and presentation       |
| Member 5 | Research and presentation       |

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

**[▶ Open the Live Demo](https://monero-demo.vercel.app)**

</div>
