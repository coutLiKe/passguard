# 🔐 PassGuard — Password Security Analyzer

![HTML](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![No Dependencies](https://img.shields.io/badge/Dependencies-None-brightgreen?style=for-the-badge)
![Privacy First](https://img.shields.io/badge/Privacy-100%25%20Local-blue?style=for-the-badge)

> A real-time password security analyzer that runs entirely in your browser. No server, no tracking, no data transmitted — ever.

---

## 🖥️ Live Demo

**[▶ Open Live Demo](https://coutLiKe.github.io/passguard)**

  No install, no server needed.

---

## ✨ Features

- **Real-time strength meter** — updates on every keystroke
- **Shannon entropy calculation** — measures true unpredictability in bits
- **Crack time estimation** — across 4 attack scenarios (online, offline slow/fast, GPU cluster)
- **Character composition breakdown** — length, uppercase, digits, symbols
- **Security checklist** — 7 NIST-inspired password requirements
- **Common password detection** — flags known weak passwords instantly
- **Pattern detection** — catches sequences (`abc`, `123`) and repeated characters (`aaa`)
- **Contextual warnings** — specific, actionable security alerts
- **Password visibility toggle** — show/hide as needed
- **100% private** — all logic is client-side JavaScript

---

## 🧠 How It Works

### Entropy Calculation
Entropy measures how unpredictable a password is. It's calculated as:

```
entropy = length × log₂(pool_size)
```

Where `pool_size` is the number of unique characters the attacker must search:

| Characters used       | Pool size |
|-----------------------|-----------|
| Lowercase only        | 26        |
| + Uppercase           | +26 = 52  |
| + Digits              | +10 = 62  |
| + Symbols             | +32 = 94  |

Higher entropy = exponentially more combinations to brute-force.

### Crack Time Estimation
Crack time is estimated as `combinations ÷ guesses_per_second`:

| Attack scenario     | Guesses/sec        | Example         |
|---------------------|--------------------|-----------------|
| Online (throttled)  | 100/sec            | Login form      |
| Offline slow hash   | 10,000/sec         | bcrypt          |
| Offline fast hash   | 1,000,000,000/sec  | MD5/SHA1        |
| GPU cluster         | 100,000,000,000/sec| Dedicated rig  |

> These are realistic estimates based on published research and security benchmarks.

### Strength Score (0–100)
A weighted score combining:
- Entropy (up to 50 pts)
- Length bonus (up to 20 pts)
- Character variety (up to 20 pts)
- Penalties for common passwords, repeated chars, and sequences

---

## 📂 Project Structure

```
passguard/
├── index.html      ← Entire app (HTML + CSS + JS in one file)
├── README.md       ← Project documentation
├── LICENSE         ← MIT license
└── .gitignore      ← Ignores OS/editor clutter
```

Single-file design makes it easy to share, host anywhere (GitHub Pages, Netlify), and audit.

---

## 🚀 Deployment (GitHub Pages)

Host this for free in about 2 minutes:

1. Create a new repo on GitHub named **`passguard`**
2. Upload all 4 files: `index.html`, `README.md`, `LICENSE`, `.gitignore`
3. Go to **Settings → Pages**
4. Under *Branch*, select **`main`** and folder **`/ (root)`**, click **Save**
5. Wait ~60 seconds — live at `https://yourusername.github.io/passguard`

**Or just open `index.html` locally** — no server required.

---

## 🔒 Privacy

This tool is designed with privacy as a core principle:
- Zero network requests after page load (except Google Fonts)
- No analytics, no cookies, no localStorage
- Password never leaves your device
- All computation happens in your browser's JavaScript engine

---

## 🗺️ Potential Improvements

- [ ] Integrate with HaveIBeenPwned API (k-anonymity model) to check real breach databases
- [ ] Add passphrase generator with real randomness (`crypto.getRandomValues`)
- [ ] Expand common passwords list (rockyou.txt subset)
- [ ] Add ZXCVBN library integration for deeper pattern analysis
- [ ] Dark/light theme toggle

---

## 📚 What I Learned

Building this project reinforced several cybersecurity concepts:
- **Shannon entropy** and its role in measuring password strength
- Why **password length** contributes more to entropy than complexity alone
- The difference between **online vs offline attack** surfaces
- Why **common password lists** (dictionary attacks) are more dangerous than brute force for most users
- NIST guidelines for password security (SP 800-63B)

---

## 📄 License

MIT — free to use, modify, and distribute.

---

*Built as a cybersecurity portfolio project. Inspired by NIST SP 800-63B password guidelines.*
