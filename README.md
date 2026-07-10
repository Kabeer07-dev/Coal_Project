# 🔐 Advanced Encryption / Decryption Program — x86 Assembly (COAL)

A feature-rich encryption and decryption program written in **x86 32-bit Assembly Language** using the **Irvine32** library. Built as a Computer Organization and Assembly Language (COAL) course project, this program implements four classic cryptographic algorithms with an interactive terminal-based menu, file encryption support, frequency analysis, and an encryption strength meter.

---

## 📁 Repository Structure

```
Coal_Project/
│
├── project.asm     # Full x86 Assembly source code
└── README.md
```

---

## ✨ Features

### 🔒 Encryption Algorithms
| # | Algorithm | Description |
|---|---|---|
| 1 | **Caesar Cipher** | Shifts each letter by a user-defined key (1–25); defaults to 3 |
| 2 | **XOR Cipher** | XORs each character against a single-byte key |
| 3 | **Substitution Cipher** | Replaces each letter using a fixed substitution table (QWERTYUIOP…) |
| 4 | **One-Time Pad (OTP)** | Generates a random key per-session and XORs it with the plaintext |

### 📋 Main Menu Options
- `[1]` Encrypt Message
- `[2]` Decrypt Message
- `[3]` File Encryption Mode — Read from and write to files
- `[4]` Frequency Analysis — Letter frequency count of ciphertext
- `[5]` Exit

### 🧰 Additional Features
- **Animated Intro Screen** — Typewriter-style welcome animation with centered text
- **Styled Terminal UI** — Bordered menus and centered output for a polished experience
- **Encryption Summary** — After encrypting, displays algorithm used and key applied
- **Encryption Strength Meter** — Rates the strength of the encryption (Weak / Medium / Strong)
- **Frequency Analysis** — Counts letter occurrences (A–Z) in the ciphertext
- **Error Handling** — Prevents decryption if no data has been encrypted; warns on algorithm mismatch
- **File Encryption** — Supports reading plaintext from a file and saving ciphertext to another file

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| x86 32-bit Assembly (MASM) | Core programming language |
| Irvine32 Library | Console I/O, string handling, randomization, delays |
| DOSBox / MASM / Visual Studio | Assembling and running the program |

---

## 🚀 Getting Started

### Prerequisites

- [MASM (Microsoft Macro Assembler)](https://www.masm32.com/) or Visual Studio with MASM support
- [Irvine32 Library](http://asmirvine.com/) installed and linked

### Build & Run

```bash
# Assemble the file
ml /c /coff project.asm

# Link the object file with Irvine32
link /SUBSYSTEM:CONSOLE project.obj irvine32.lib kernel32.lib user32.lib

# Run the executable
project.exe
```

> **Note:** Make sure `Irvine32.inc` and the Irvine32 library files are in your include/library path before assembling.

---

## 🔑 Cipher Details

### Caesar Cipher
Shifts each alphabetic character forward by the key value. Wraps around the alphabet. Default key is **3**.

### XOR Cipher
Each character is XORed with a single byte key entered by the user. Symmetric — the same key decrypts the message.

### Substitution Cipher
Uses the table `QWERTYUIOPASDFGHJKLZXCVBNM` — each letter A–Z maps to the corresponding character in this table.

### One-Time Pad (OTP)
A cryptographically random 256-byte key is generated at runtime. The ciphertext and key are both displayed in hexadecimal. Decryption uses the stored in-memory key from the same session.

---

## 📊 Frequency Analysis

After encrypting a message, selecting option `[4]` performs a letter frequency count on the ciphertext, printing counts for each letter A–Z. This is useful for demonstrating how different ciphers obscure or preserve letter distribution.

---

## 📌 Topics Covered

- x86 Assembly programming (MASM syntax)
- Registers, memory segments, and stack operations
- Procedures and modular code structure
- String manipulation and I/O using Irvine32
- Classical cryptography algorithms
- File I/O in Assembly
- Randomization and delay operations
- Console UI design in Assembly

---

## 👤 Author

**Kabeer** — [@Kabeer07-dev](https://github.com/Kabeer07-dev)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
