<p align="center">
  <img src="metal.gif" alt="SeedVault encrypted QR code engraved on stainless steel" width="360">
</p>

<h1 align="center">Seed-Vault.io</h1>

<p align="center">
  <strong>Encrypt your crypto seed phrase into a QR code.</strong><br>
  AES-256-GCM · 100% client-side · Single HTML file · Works offline
</p>

<p align="center">
  <a href="https://seed-vault.io">Live App</a> &nbsp;·&nbsp;
  <a href="#security">Security</a> &nbsp;·&nbsp;
  <a href="#how-it-works">How it works</a> &nbsp;·&nbsp;
  <a href="https://twitter.com/seed_vaultio">Twitter</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/encryption-AES--256--GCM-000?style=flat-square" alt="AES-256-GCM">
  <img src="https://img.shields.io/badge/key_derivation-PBKDF2_600k-000?style=flat-square" alt="PBKDF2">
  <img src="https://img.shields.io/badge/dependencies-0-000?style=flat-square" alt="Zero deps">
  <img src="https://img.shields.io/badge/data_sent-none-000?style=flat-square" alt="No data sent">
  <img src="https://img.shields.io/badge/license-MIT-000?style=flat-square" alt="MIT">
  <img src=https://img.shields.io/github/stars/lesagejeanno-cmd/seed-vault.io?style=flat-square&color=000>
  
</p>

---

## The problem

Most crypto holders store their seed phrase in **plain text** — written on paper, stamped on metal, saved in a screenshot. Anyone who finds it can steal everything, instantly.

Even metal plates (Cryptosteel, Billfodl, etc.) only protect against fire and water. They don't protect against **the person who finds the plate**.

## The solution

SeedVault encrypts your seed phrase **before** you store it.

The result is an encrypted QR code. You can print it, save it on USB, email it to yourself, or engrave it on metal (order it on seed-vault.io) — without the password, it's unreadable noise.

<p align="center">
  <img src="assets/demo.gif" alt="SeedVault — encrypt a seed phrase in 10 seconds" width="320">
  <br>
  <em>Encrypt → QR code → done. 10 seconds.</em>
</p>

## Features

**Encryption** — AES-256-GCM via Web Crypto API. PBKDF2 key derivation with 600,000 iterations. Random salt and IV per encryption.

**Single HTML file** — No build step, no server, no dependencies. Download `index.html`, open in any browser. That's it.

**Works offline** — Disconnect from the internet before encrypting. The tool works identically.

**Steganography** — Hide your encrypted seed phrase inside a normal-looking image. The image looks unchanged to the human eye.

**Camera scanner** — Scan encrypted QR codes directly with your phone camera (HTTPS required) or upload an image.

**Dark/light mode** — Follows your system preference.

## How it works

```
Your seed phrase
      ↓
AES-256-GCM encryption (in your browser)
      ↓                ↑
  Encrypted data    Your password
      ↓            (never stored)
   QR code
      ↓
Print · USB · Cloud · Metal
```

1. You enter your 12 or 24 words
2. You choose a password
3. SeedVault generates a random **salt** (16 bytes) and **IV** (12 bytes)
4. Your password is derived into an encryption key via **PBKDF2** (600,000 iterations)
5. Your seed phrase is encrypted with **AES-256-GCM**
6. The encrypted payload is encoded into a QR code
7. **Nothing is sent anywhere.** Zero network requests.

## Security

| | |
|---|---|
| **Encryption** | AES-256-GCM (Web Crypto API) |
| **Key derivation** | PBKDF2 · SHA-256 · 600,000 iterations |
| **Salt** | 16 random bytes (unique per encryption) |
| **IV** | 12 random bytes (unique per encryption) |
| **Network** | 0 requests after page load |
| **Storage** | Nothing in localStorage, cookies, or disk |
| **Dependencies** | 0 for cryptography (uses browser Web Crypto API) |

### Best Practice

For maximum security, use an air-gapped computer when encrypting your seed phrase

Or go offline:

```bash
curl -O https://seed-vault.io/index.html
# Disconnect from internet
# Open index.html → works identically
```

## Install
https://github.com/lesagejeanno-cmd/seed-vault.git
There is nothing to install.

```bash
git clone https://github.com/lesagejeanno-cmd/seed-vault.git
open index.html
```

Or download `index.html` from the [latest release](https://github.com/lesagejeanno-cmd/seed-vault/releases) and open it in your browser.

## Metal plates

SeedVault is free. If you want your encrypted QR code laser-engraved on stainless steel or titanium (fireproof, waterproof, permanent), you can order one at [seed-vault.io](https://seed-vault.io).

<p align="center">
  <img src="assets/metal-plate.jpg" alt="Encrypted QR code on stainless steel plate" width="280">
</p>

Unlike plain-text metal plates, your SeedVault backup is **encrypted and fireproof** — finding the plate without the password reveals nothing.

## FAQ

**Can I trust this?**
The entire source code is this single HTML file. Read it. Audit it. Run it offline. There is no server, no account, no tracking, no analytics.

**What if I forget my password?**
Your seed phrase is gone. There is no recovery. Use a password you won't forget, or store the password separately from the QR code.

**What wallets are compatible?**
Any wallet that uses BIP39 seed phrases (12 or 24 words). That's most wallets.

**Is the QR code safe to store in the cloud?**
Yes — the QR code contains AES-256 encrypted data. Without your password, it's random noise. You can safely store it in Google Drive, iCloud, email, etc.

## Audit this project

Security audits are welcome and encouraged. If you find a vulnerability:

1. **Do NOT open a public issue**
2. Email **contact@seed-vault.io**
3. Include steps to reproduce
4. We respond within 48 hours

## License

MIT — do whatever you want with it.

---

<p align="center">
  <strong>Stop storing plain-text seed phrases.</strong><br>
  <a href="https://seed-vault.io">seed-vault.io</a>
</p>
