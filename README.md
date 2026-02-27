# 🔐 Cryptography with Python: From Fundamentals to Secure Toolkit Development

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![Security](https://img.shields.io/badge/Security-AES--256%20%7C%20RSA--2048%20%7C%20bcrypt-critical?style=for-the-badge)
![Level](https://img.shields.io/badge/Level-Beginner%20to%20Intermediate-yellow?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge)

**A structured, project-driven course and toolkit for mastering applied cryptography in Python — built for learners, developers, and security enthusiasts.**

[Overview](#-overview) • [Learning Outcomes](#-learning-outcomes) • [Course Structure](#-course-structure) • [Installation](#-installation) • [Usage](#-usage) • [Architecture](#-project-architecture) • [Security](#-security-best-practices) • [Roadmap](#-future-learning-roadmap)

</div>

---

## 📖 Overview

### What Is Cryptography?

Cryptography is the science of securing information by transforming it into an unreadable format that only authorised parties can decode. It is the backbone of virtually every secure digital system in existence — from the padlock icon in your browser's address bar, to encrypted messaging apps, to the way your password is stored on a server.

At its core, cryptography answers four fundamental questions:

| Security Property | Question It Answers |
|---|---|
| **Confidentiality** | Can anyone other than the intended recipient read this data? |
| **Integrity** | Has this data been altered since it was created or sent? |
| **Authentication** | Can I verify the identity of who sent this? |
| **Non-repudiation** | Can the sender deny having sent this? |

### Why Cryptography Matters in Modern Cybersecurity

We live in an era of ubiquitous data. Personal health records, financial transactions, private communications, government infrastructure — all of it traverses networks and rests on servers that are under constant threat. In 2023 alone, the global average cost of a data breach reached $4.45 million USD (IBM Security). The overwhelming majority of these breaches exploit one or more of the following failures:

- Weak or absent encryption
- Improper key management
- Insecure password storage
- Failure to verify data integrity
- Use of deprecated or broken cryptographic algorithms

Understanding cryptography is not optional for a modern developer or security professional. It is a foundational skill — as essential as understanding networking or operating systems.

### Why This Repository Exists

This repository was created to bridge the gap between theoretical cryptographic knowledge and practical, production-grade implementation. Most cryptography resources either drown learners in mathematics without showing them how to write a single line of code, or jump straight into libraries without explaining the principles that make secure implementation possible.

This course does neither. It follows a **learn-by-building** philosophy: every concept is taught in the context of building something real. By the end, you will have constructed a complete, CLI-based cryptographic toolkit in Python — a project you can present to recruiters, submit to hackathons, or extend into a larger security application.

---

## 🎯 Learning Outcomes

Upon completing this course and building the associated toolkit, learners will be able to:

### Conceptual Outcomes
- Explain the four pillars of cryptographic security: confidentiality, integrity, authentication, and non-repudiation
- Differentiate between encoding, hashing, symmetric encryption, and asymmetric encryption — and know when to use each
- Understand real-world cryptographic architectures including HTTPS/TLS, hybrid encryption, and key exchange protocols
- Accurately describe threat models including eavesdropping, man-in-the-middle attacks, replay attacks, brute force, and data tampering

### Technical Outcomes
- Implement SHA-256 hashing for data fingerprinting and file integrity verification
- Build AES-256-GCM encryption and decryption pipelines for files and arbitrary data
- Generate RSA-2048 key pairs, store them in PEM format, and use them for public-key encryption with OAEP padding
- Implement bcrypt for secure, salted password hashing and verification
- Integrate `zxcvbn` for real-time password entropy and strength evaluation
- Build a modular, CLI-driven cryptographic toolkit from scratch

### Security Outcomes
- Identify and explain insecure cryptographic practices (ECB mode, MD5/SHA-1, hardcoded keys, plaintext password storage)
- Apply industry-standard key management principles
- Implement hybrid encryption (RSA for key exchange + AES for bulk data encryption)
- Write production-conscious Python code that avoids common security anti-patterns

---

## 👥 Target Audience

This repository is designed for:

| Audience | Why This Is Relevant |
|---|---|
| **Computer Science students** | Practical implementation of cryptographic theory taught in university courses |
| **Junior developers** | Learn to write secure code and understand the security implications of everyday choices |
| **Hackathon participants** | Build a compelling security project with real-world architecture |
| **Self-taught programmers** | Structured path from zero cryptographic knowledge to a deployable security toolkit |
| **Security enthusiasts** | Hands-on entry point into applied cryptography before diving into penetration testing or CTFs |
| **Open-source contributors** | Well-structured, modular Python codebase designed for extension |

**Prerequisites:**
- Basic Python (variables, functions, loops, file I/O)
- Comfort using a terminal / command line
- No prior cryptography knowledge required

---

## 📚 Course Structure

The course is divided into 16 modules, progressing from foundational concepts to full toolkit implementation.

---

### 🔹 Module 1 — Introduction to Cryptography

**What you'll learn:**
- The definition and historical context of cryptography
- The four security goals: Confidentiality, Integrity, Authentication, Non-repudiation
- The critical distinctions between encoding, hashing, and encryption (concepts routinely confused even by experienced developers)
- Real-world applications: HTTPS, end-to-end encrypted messaging, digital signatures, disk encryption

**Why it matters:** Before writing a single line of cryptographic code, you must understand *what problem you are solving*. A developer who reaches for encryption when they need hashing — or vice versa — introduces vulnerabilities even with correct library usage.

**Practical Component:** Simple SHA-256 demonstration in Python to immediately ground theory in code.

```python
import hashlib

message = "Hello, Cryptography!"
digest = hashlib.sha256(message.encode()).hexdigest()
print(f"SHA-256: {digest}")
```

---

### 🔹 Module 2 — Course Philosophy & Architecture

**What you'll learn:**
- The learn-by-building methodology and why passive learning fails in security education
- How this course is structured and what each module contributes to the final capstone
- The expected deliverables at each stage

**Outcome:** Students understand the full arc of the course — each module is not an isolated lesson but a building block of the final toolkit.

---

### 🔹 Module 3 — Cryptographic Fundamentals & Threat Modeling

**Core Terminology:**

| Term | Definition |
|---|---|
| **Plaintext** | The original, readable data before encryption |
| **Ciphertext** | The encrypted, unreadable output of an encryption operation |
| **Key** | The secret value that controls encryption and decryption |
| **Encryption** | The process of transforming plaintext into ciphertext |
| **Decryption** | The reverse process of recovering plaintext from ciphertext |
| **Digital Signature** | A cryptographic proof of authenticity and integrity |
| **Nonce / IV** | A unique value used once to ensure ciphertext uniqueness |

**Threat Models Covered:**

- **Eavesdropping** — Passive interception of data in transit
- **Man-in-the-Middle (MITM)** — Active interception and possible alteration
- **Data Tampering** — Unauthorised modification of stored or transmitted data
- **Brute Force** — Exhaustive key or password guessing
- **Replay Attacks** — Re-sending captured valid data to trick a system

**Secure Data Handling:**
- Data at rest vs. data in transit
- Key lifecycle management: generation, storage, rotation, destruction

---

### 🔹 Module 4 — Core Areas of Cryptography

A comparative overview of the three cryptographic paradigms used throughout this course:

#### 4.1 Hashing
- One-way mathematical functions — cannot be reversed
- **Collision resistance**: computationally infeasible to find two inputs that produce the same hash
- **Preimage resistance**: given a hash, infeasible to find the original input
- **Avalanche effect**: a 1-bit change in input produces a completely different hash
- Applications: file integrity, password storage, digital signatures

#### 4.2 Symmetric Encryption
- A single shared secret key is used for both encryption and decryption
- **AES (Advanced Encryption Standard)** — the global standard since 2001
- Extremely fast; ideal for encrypting large files or data streams
- Key distribution is the central challenge

#### 4.3 Asymmetric Encryption
- Uses a mathematically linked **key pair**: a public key (shareable) and a private key (secret)
- Data encrypted with the public key can only be decrypted with the private key
- **RSA** — the most widely deployed asymmetric algorithm
- Much slower than symmetric encryption; used for key exchange and digital signatures

#### 4.4 Comparative Analysis

| Property | Hashing | Symmetric (AES) | Asymmetric (RSA) |
|---|---|---|---|
| **Reversible?** | No | Yes (with key) | Yes (with private key) |
| **Key Required?** | No | Yes (shared) | Yes (key pair) |
| **Speed** | Very fast | Fast | Slow |
| **Use Case** | Integrity, passwords | Bulk encryption | Key exchange, auth |
| **Python Library** | `hashlib` | `cryptography` | `cryptography` |

---

### 🔹 Module 5 — Hashing & File Integrity

**Theoretical Concepts:**
- Deep dive into SHA-256: 256-bit output, part of the SHA-2 family, NSA-designed, widely audited
- Preimage and collision resistance explained with worked examples
- Why MD5 and SHA-1 are broken and must never be used for security purposes

**Implementation — `hash.py`:**

The module covers:
- Hashing arbitrary strings and byte data
- Chunk-based file hashing (handles files larger than available RAM)
- Hash comparison logic with constant-time equality checks to prevent timing attacks

```python
import hashlib

def hash_file(filepath: str) -> str:
    """Returns the SHA-256 hex digest of a file, processed in chunks."""
    sha256 = hashlib.sha256()
    with open(filepath, "rb") as f:
        for chunk in iter(lambda: f.read(65536), b""):
            sha256.update(chunk)
    return sha256.hexdigest()
```

**Applications:**
- Software release verification (checksums)
- Download integrity checking
- Digital forensics and evidence preservation
- Change detection in configuration files

---

### 🔹 Module 6 — Symmetric Encryption (AES-256-GCM)

**Why AES?**
AES has been the US federal encryption standard since 2001. It has withstood over two decades of cryptanalysis and remains unbroken at the 256-bit key level. It is used everywhere: disk encryption (BitLocker, FileVault), TLS, VPNs, encrypted messaging.

**AES Parameters:**

| Parameter | Value Used | Notes |
|---|---|---|
| **Key size** | 256 bits | Strongest option; NIST-recommended |
| **Block size** | 128 bits | Fixed in all AES variants |
| **Mode** | GCM | Authenticated encryption |
| **Nonce size** | 96 bits (12 bytes) | Recommended for GCM |
| **Authentication tag** | 128 bits (16 bytes) | Verifies integrity and authenticity |

**Encryption Modes — Why Mode Choice Matters:**

| Mode | Description | Secure? |
|---|---|---|
| **ECB** (Electronic Codebook) | Each block encrypted independently | ❌ Never use — reveals patterns |
| **CBC** (Cipher Block Chaining) | Blocks chained; requires padding | ⚠️ Use carefully; no authentication |
| **GCM** (Galois/Counter Mode) | Stream cipher + authentication | ✅ Recommended |

**GCM is the industry standard** because it provides both encryption *and* authentication (AEAD — Authenticated Encryption with Associated Data). This means you cannot decrypt corrupted or tampered ciphertext without detection.

**Implementation — `encryption.py`:**

```python
from cryptography.hazmat.primitives.ciphers.aead import AESGCM
import os

def generate_aes_key() -> bytes:
    """Generates a cryptographically secure 256-bit AES key."""
    return os.urandom(32)

def encrypt(data: bytes, key: bytes) -> tuple[bytes, bytes]:
    """Encrypts data using AES-256-GCM. Returns (nonce, ciphertext)."""
    nonce = os.urandom(12)
    aesgcm = AESGCM(key)
    ciphertext = aesgcm.encrypt(nonce, data, None)
    return nonce, ciphertext

def decrypt(nonce: bytes, ciphertext: bytes, key: bytes) -> bytes:
    """Decrypts AES-256-GCM ciphertext. Raises exception if tampered."""
    aesgcm = AESGCM(key)
    return aesgcm.decrypt(nonce, ciphertext, None)
```

**Security Practices Enforced:**
- Never reuse a nonce with the same key (nonce reuse destroys GCM security entirely)
- Never hardcode keys in source code
- Always use environment variables or a key management service for key storage
- Store nonce alongside ciphertext — it does not need to be secret

---

### 🔹 Module 7 — Asymmetric Encryption (RSA with OAEP)

**Public Key Cryptography Fundamentals:**

RSA security relies on the mathematical difficulty of factoring the product of two very large prime numbers. Given a public key, it is computationally infeasible (with current technology and key sizes ≥ 2048 bits) to derive the private key.

**Key Pair Concepts:**
- **Public key**: Can be freely distributed. Used to encrypt data *to* you, or to verify *your* signature.
- **Private key**: Must be kept secret. Used to decrypt data *sent to* you, or to create *your* signature.

**RSA-OAEP:**
Raw RSA (textbook RSA) is insecure for direct use. This course implements **RSA-OAEP** (Optimal Asymmetric Encryption Padding), which adds structured randomness to prevent several known attacks including chosen-plaintext attacks.

**Implementation — RSA key generation and encryption:**

```python
from cryptography.hazmat.primitives.asymmetric import rsa, padding
from cryptography.hazmat.primitives import hashes, serialization

def generate_rsa_keypair():
    private_key = rsa.generate_private_key(
        public_exponent=65537,
        key_size=2048
    )
    return private_key, private_key.public_key()

def rsa_encrypt(data: bytes, public_key) -> bytes:
    return public_key.encrypt(
        data,
        padding.OAEP(
            mgf=padding.MGF1(algorithm=hashes.SHA256()),
            algorithm=hashes.SHA256(),
            label=None
        )
    )
```

**Hybrid Encryption Architecture:**

RSA can only encrypt data up to the key size minus padding overhead (~190 bytes for RSA-2048 with OAEP-SHA256). It is also far too slow for bulk data. The industry solution is **hybrid encryption**:

```
┌─────────────────────────────────────────────────────────────┐
│                   HYBRID ENCRYPTION FLOW                    │
├─────────────────────────────────────────────────────────────┤
│  1. Generate random AES-256 session key                     │
│  2. Encrypt the actual data with AES-256-GCM (fast)         │
│  3. Encrypt the AES session key with RSA-OAEP (secure)      │
│  4. Transmit: [RSA-encrypted key] + [AES-encrypted data]    │
│                                                             │
│  Decryption:                                                │
│  1. Decrypt AES key using RSA private key                   │
│  2. Decrypt data using recovered AES key                    │
└─────────────────────────────────────────────────────────────┘
```

This is precisely the architecture used by TLS, PGP, and most secure communication protocols.

---

### 🔹 Module 8 — Password Security

**Why Passwords Are a Cryptographic Problem:**

Passwords represent one of the most commonly mishandled security elements in software development. The correct approach is not encryption (which is reversible with the key) but **one-way hashing with a purpose-built password hashing function**.

**Password Strength Evaluation with `zxcvbn`:**

`zxcvbn` (by Dropbox) estimates password entropy by modelling how an attacker would crack it, accounting for dictionary words, common patterns, keyboard walks, and date patterns.

```python
import zxcvbn

result = zxcvbn.zxcvbn("correcthorsebatterystaple")
print(f"Score: {result['score']}/4")           # 0=very weak, 4=very strong
print(f"Crack time: {result['crack_times_display']['offline_slow_hashing_1e4_per_second']}")
```

**Secure Password Hashing with `bcrypt`:**

`bcrypt` is a **deliberately slow** password hashing function. Its computational cost can be increased (via a work factor / cost parameter) as hardware becomes faster, making brute-force attacks impractical.

| Algorithm | Designed for passwords? | Salted? | Adjustable cost? | Secure? |
|---|---|---|---|---|
| MD5 | No | No | No | ❌ Broken |
| SHA-256 | No | No | No | ❌ Too fast |
| SHA-256 + salt | No | Yes | No | ⚠️ Insufficient |
| **bcrypt** | **Yes** | **Yes (automatic)** | **Yes** | **✅ Recommended** |
| Argon2 | Yes | Yes (automatic) | Yes | ✅ Also excellent |

```python
import bcrypt

def hash_password(password: str) -> bytes:
    salt = bcrypt.gensalt(rounds=12)   # cost factor 12 = ~250ms per hash
    return bcrypt.hashpw(password.encode(), salt)

def verify_password(password: str, hashed: bytes) -> bool:
    return bcrypt.checkpw(password.encode(), hashed)
```

**Common Mistakes:**
- Storing passwords in plaintext (catastrophic — affects all users if breached)
- Encrypting passwords instead of hashing (reversible — a breach reveals everything)
- Using fast hash functions (SHA-256, MD5) without a proper cost factor (trivially brute-forced with GPU)
- Implementing your own salting incorrectly (use bcrypt's built-in salting)

---

### 🔹 Modules 9–14 — Implementation Modules

These modules transition from theory to hands-on construction of the toolkit:

| Module | Focus | Output |
|---|---|---|
| **Module 9** | Environment setup | Configured Python environment |
| **Module 10** | File hashing | `hash.py` — complete integrity verification module |
| **Module 11** | AES implementation | `encryption.py` — AES-256-GCM encrypt/decrypt/file support |
| **Module 12** | RSA implementation | RSA key generation, PEM storage, hybrid encryption |
| **Module 13** | Password module | `password.py` — strength checking, hashing, verification |
| **Module 14** | CLI toolkit | `main.py` — unified command-line interface |

---

### 🔹 Module 15 — Final Cryptography Toolkit Integration

All modules are assembled into a unified, tested toolkit. This module covers:

- Integration testing: verifying that components work together correctly
- **Tampering tests**: modifying ciphertext and verifying that decryption fails with an appropriate error
- **Incorrect key tests**: attempting decryption with wrong keys
- **Integrity failure detection**: confirming that hash mismatches are detected

---

### 🔹 Module 16 — Advanced Concepts & Future Learning

A forward-looking module introducing topics to explore next:

- **Digital Signatures** — RSA and ECDSA for authentication and non-repudiation
- **TLS Architecture** — How HTTPS uses the exact hybrid encryption pattern you've built
- **Blockchain Hashing** — SHA-256 in Merkle trees and proof-of-work
- **Key Exchange Protocols** — Diffie-Hellman and ECDH
- **Ethical Hacking Foundations** — How knowledge of cryptography informs offensive security

---

## ⚙️ Installation

### Prerequisites

- Python 3.10 or higher
- `pip` (included with Python)
- Git

### Step 1 — Clone the Repository

```bash
git clone https://github.com/yourusername/cryptography-with-python.git
cd cryptography-with-python
```

### Step 2 — Create a Virtual Environment

It is strongly recommended to use a virtual environment to isolate project dependencies.

```bash
# Create the virtual environment
python -m venv venv

# Activate it — Linux/macOS
source venv/bin/activate

# Activate it — Windows (Command Prompt)
venv\Scripts\activate.bat

# Activate it — Windows (PowerShell)
venv\Scripts\Activate.ps1
```

### Step 3 — Install Dependencies

```bash
pip install -r requirements.txt
```

**`requirements.txt`:**

```
cryptography>=41.0.0
bcrypt>=4.0.0
zxcvbn>=4.4.28
```

### Step 4 — Verify Installation

```bash
python -c "from cryptography.hazmat.primitives.ciphers.aead import AESGCM; import bcrypt; import zxcvbn; print('All dependencies installed successfully.')"
```

---

## 🗂️ Project Architecture

```
cryptography-with-python/
│
├── README.md                    # This file
├── requirements.txt             # Python dependencies
├── .env.example                 # Example environment variable configuration
├── .gitignore                   # Excludes keys, .env, __pycache__, etc.
│
├── src/
│   ├── hash.py                  # SHA-256 hashing and file integrity
│   ├── encryption.py            # AES-256-GCM symmetric encryption
│   ├── rsa_encryption.py        # RSA key generation and asymmetric encryption
│   ├── hybrid.py                # Hybrid RSA + AES encryption pipeline
│   ├── password.py              # bcrypt password hashing and zxcvbn strength evaluation
│   └── main.py                  # CLI entry point — unified command-line toolkit
│
├── keys/
│   ├── .gitkeep                 # Directory tracked; actual key files are gitignored
│   ├── private_key.pem          # ⚠️  Generated at runtime — NEVER commit
│   └── public_key.pem           # Generated at runtime — safe to share
│
├── tests/
│   ├── test_hash.py             # Hashing unit tests
│   ├── test_encryption.py       # AES encrypt/decrypt tests including tampering
│   ├── test_rsa.py              # RSA generation and encryption tests
│   ├── test_hybrid.py           # Hybrid encryption integration tests
│   └── test_password.py         # bcrypt hashing and zxcvbn tests
│
├── modules/                     # Course modules (one directory per module)
│   ├── module_01_intro/
│   ├── module_03_fundamentals/
│   ├── module_05_hashing/
│   ├── module_06_aes/
│   ├── module_07_rsa/
│   ├── module_08_passwords/
│   └── ...
│
└── docs/
    ├── architecture.md          # Detailed system design documentation
    ├── threat_model.md          # Threat modelling documentation
    └── security_notes.md        # Security decisions and justifications
```

> ⚠️ **Important:** The `keys/` directory is listed in `.gitignore`. Never commit private keys to version control.

---

## 🖥️ Usage

### Running the CLI Toolkit

All toolkit functionality is accessible through `main.py`:

```bash
python src/main.py --help
```

```
usage: main.py [-h]
               {hash-file,verify-file,generate-keys,encrypt,decrypt,
                hybrid-encrypt,hybrid-decrypt,check-password,
                hash-password,verify-password}

Cryptography Toolkit — AES-256 | RSA-2048 | bcrypt | SHA-256

positional arguments:
  {hash-file,verify-file,...}  Command to execute

options:
  -h, --help                   Show this help message and exit
```

---

### 📋 Example Commands

#### Hash a File
```bash
python src/main.py hash-file --input document.pdf
# Output: SHA-256: 3b4c5d6e7f8a9b0c1d2e3f4a5b6c7d8e9f0a1b2c3d4e5f6a7b8c9d0e1f2a3b4c
```

#### Verify File Integrity
```bash
python src/main.py verify-file --input document.pdf --expected 3b4c5d6e7f8a9b...
# Output: ✅ Integrity verified. File has not been tampered with.
# or
# Output: ❌ INTEGRITY FAILURE. Hash mismatch detected.
```

#### Generate AES Key (stored to environment)
```bash
python src/main.py generate-aes-key
# Output: AES key generated and saved to .env as AES_KEY
```

#### Encrypt a File with AES-256-GCM
```bash
python src/main.py encrypt --input secret.txt --output secret.enc
# Output: ✅ Encrypted → secret.enc
```

#### Decrypt a File
```bash
python src/main.py decrypt --input secret.enc --output recovered.txt
# Output: ✅ Decrypted → recovered.txt
```

#### Generate RSA Key Pair
```bash
python src/main.py generate-keys --output-dir keys/
# Output: ✅ Private key → keys/private_key.pem
#         ✅ Public key  → keys/public_key.pem
```

#### Hybrid Encrypt (RSA + AES)
```bash
python src/main.py hybrid-encrypt \
  --input large_file.pdf \
  --output large_file.enc \
  --public-key keys/public_key.pem
# Output: ✅ Hybrid encrypted → large_file.enc
```

#### Hybrid Decrypt
```bash
python src/main.py hybrid-decrypt \
  --input large_file.enc \
  --output large_file_recovered.pdf \
  --private-key keys/private_key.pem
# Output: ✅ Decrypted → large_file_recovered.pdf
```

#### Check Password Strength
```bash
python src/main.py check-password
# Prompt: Enter password to evaluate: ********
# Output:
#   Score: 3/4 (Strong)
#   Estimated crack time (offline slow hash): 3 years
#   Suggestions: Consider adding a special character.
```

#### Hash a Password
```bash
python src/main.py hash-password
# Prompt: Enter password to hash: ********
# Output: $2b$12$eImiTXuWVxfM37uY4JANjOec/SoMLqBsMkNjn4eBnDo...
```

#### Verify a Password
```bash
python src/main.py verify-password --hash '$2b$12$eImiTXuWVxfM37uY4JANjO...'
# Prompt: Enter password to verify: ********
# Output: ✅ Password matches.
```

---

## 🔒 Security Best Practices

This repository enforces and teaches the following production-grade security principles:

### Algorithm Selection

| Purpose | Use This | Never Use |
|---|---|---|
| **File hashing** | SHA-256, SHA-3 | MD5, SHA-1 |
| **Password hashing** | bcrypt, Argon2, scrypt | SHA-256 (without cost factor), MD5 |
| **Symmetric encryption** | AES-256-GCM | DES, 3DES, RC4, AES-ECB |
| **Asymmetric encryption** | RSA-OAEP (2048+), ECDSA | Raw RSA, RSA-PKCS1v15 (for new systems) |
| **Key derivation** | PBKDF2, scrypt, Argon2 | Direct password use as key |

### Key Management
- ✅ Generate keys with a cryptographically secure random number generator (`os.urandom()`)
- ✅ Store keys in environment variables or a dedicated secrets manager (AWS KMS, HashiCorp Vault)
- ✅ Use `.env` files locally (with `python-dotenv`); never commit them to version control
- ✅ Rotate keys periodically; have a documented rotation procedure
- ❌ Never hardcode keys in source files
- ❌ Never commit keys, `.env` files, or PEM files to a Git repository
- ❌ Never log or print raw key material

### Nonce / IV Handling
- ✅ Always generate a fresh nonce with `os.urandom(12)` for every AES-GCM encryption
- ✅ Store the nonce alongside the ciphertext (it is not a secret)
- ❌ Never reuse a nonce with the same key — nonce reuse in GCM mode reveals the key

### Padding and Modes
- ✅ Always use AES-GCM for authenticated encryption (provides confidentiality + integrity)
- ✅ Always use RSA-OAEP padding (never raw/textbook RSA, never PKCS1v15 for new designs)
- ❌ Never use AES-ECB — it encrypts identical plaintext blocks to identical ciphertext blocks, leaking data structure

### Input Validation
- ✅ Validate and sanitise all CLI input before use in cryptographic operations
- ✅ Use constant-time comparison (`hmac.compare_digest`) when comparing hashes to prevent timing attacks
- ✅ Handle decryption failures gracefully without revealing whether failure was due to wrong key or tampered data

---

## ⚠️ Common Mistakes to Avoid

These are mistakes seen regularly in real production code. This course specifically teaches you to recognise and avoid them.

### 1. Using MD5 or SHA-1 for Security Purposes
```python
# ❌ NEVER — MD5 is cryptographically broken
import hashlib
hashlib.md5(data).hexdigest()

# ✅ Correct
hashlib.sha256(data).hexdigest()
```

### 2. Encrypting Passwords Instead of Hashing Them
```python
# ❌ WRONG — if you have the key, you can recover all passwords
encrypted_pw = cipher.encrypt(password.encode())

# ✅ Correct — one-way, salted, cost-adjusted
hashed_pw = bcrypt.hashpw(password.encode(), bcrypt.gensalt(rounds=12))
```

### 3. Hardcoding Cryptographic Keys
```python
# ❌ CATASTROPHIC — key is in version history forever
key = b"mysecretkeyvalue"

# ✅ Correct — load from environment
import os
key = bytes.fromhex(os.environ["AES_KEY"])
```

### 4. Using AES-ECB Mode
```python
# ❌ INSECURE — leaks patterns in data
cipher = Cipher(algorithms.AES(key), modes.ECB())

# ✅ Correct — use GCM for authenticated encryption
AESGCM(key).encrypt(nonce, data, None)
```

### 5. Reusing Nonces in AES-GCM
```python
# ❌ CATASTROPHIC in GCM — nonce reuse recovers the key
nonce = b"\x00" * 12  # static nonce

# ✅ Correct — always fresh
nonce = os.urandom(12)
```

### 6. Not Verifying Integrity Before Decryption
```python
# ❌ Dangerous — decrypting tampered data
plaintext = cipher.decrypt(ciphertext)

# ✅ AES-GCM handles this automatically — decryption raises InvalidTag if tampered
try:
    plaintext = aesgcm.decrypt(nonce, ciphertext, None)
except Exception:
    raise ValueError("Decryption failed: data may have been tampered with.")
```

---

## 🌍 Real-World Applications

The cryptographic patterns implemented in this toolkit are the same patterns used in production systems worldwide:

| Real System | Cryptographic Technique Used |
|---|---|
| **HTTPS / TLS** | Hybrid encryption (RSA/ECDH key exchange + AES-GCM bulk encryption) |
| **WhatsApp / Signal** | End-to-end encryption using public-key cryptography and AES |
| **Git (commit hashing)** | SHA-256 for content addressing and integrity |
| **BitLocker / FileVault** | AES-256 full-disk encryption |
| **Linux `/etc/shadow`** | bcrypt / SHA-512 password hashing |
| **Software releases** | SHA-256 checksums for download integrity verification |
| **Bitcoin** | SHA-256 (double-hash) in proof-of-work and Merkle trees |
| **Password managers** | AES-256 encryption with PBKDF2/Argon2 key derivation |
| **AWS KMS / Azure Key Vault** | RSA-OAEP for key wrapping; AES-256 for data key encryption |
| **Email (PGP/S-MIME)** | Hybrid RSA + AES encryption and digital signatures |

---

## 🧪 Running Tests

```bash
# Run all tests
python -m pytest tests/ -v

# Run a specific test module
python -m pytest tests/test_encryption.py -v

# Run with coverage report
pip install pytest-cov
python -m pytest tests/ --cov=src --cov-report=term-missing
```

**Test coverage includes:**
- Correct encryption and decryption round-trips
- Tampered ciphertext detection (modifying a single byte must raise an exception)
- Wrong-key decryption failure
- Hash mismatch detection
- bcrypt verification with correct and incorrect passwords
- RSA key serialisation and deserialisation

---

## 📦 Dependencies

| Package | Version | Purpose |
|---|---|---|
| `cryptography` | ≥41.0.0 | AES-256-GCM, RSA-OAEP, key serialisation |
| `bcrypt` | ≥4.0.0 | Password hashing with adaptive cost factor |
| `zxcvbn` | ≥4.4.28 | Password strength estimation |

All three packages are maintained by reputable organisations:
- `cryptography` — Python Cryptographic Authority (PyCA), the gold standard Python crypto library
- `bcrypt` — actively maintained, widely deployed
- `zxcvbn` — originally developed by Dropbox, widely adopted in production applications

---

## 🗺️ Future Learning Roadmap

Having completed this course, the following topics represent natural and recommended next steps:

### Immediately Accessible
- **Digital Signatures** (RSA-PSS, ECDSA) — proving message origin with your private key
- **Key Derivation Functions** (PBKDF2, scrypt, Argon2) — deriving encryption keys from passwords securely
- **Certificate Authorities & X.509** — how TLS certificates establish trust

### Intermediate
- **TLS/SSL Deep Dive** — understanding the full HTTPS handshake using everything covered here
- **Elliptic Curve Cryptography (ECC)** — smaller keys, faster operations than RSA
- **JSON Web Tokens (JWT)** — cryptographically signed tokens for authentication in web APIs
- **Secret Management** — HashiCorp Vault, AWS Secrets Manager, environment hardening

### Advanced / Security-Oriented
- **Cryptographic Protocol Analysis** — using tools like ProVerif to formally verify protocol security
- **Side-Channel Attacks** — timing attacks, cache attacks, and defences
- **Post-Quantum Cryptography** — CRYSTALS-Kyber, CRYSTALS-Dilithium (NIST PQC standards)
- **Ethical Hacking & CTFs** — applying cryptographic knowledge to Capture the Flag challenges and penetration testing
- **Blockchain & Zero-Knowledge Proofs** — cryptography at the frontier of decentralised systems

---

## 📄 Licence

This project is licensed under the **MIT Licence**. See [`LICENSE`](LICENSE) for full terms.

You are free to use, modify, and distribute this code for personal, educational, and commercial purposes, with attribution.

---

## 🤝 Contributing

Contributions are welcome. If you identify a security issue, a bug, or an improvement:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Commit your changes with clear, descriptive messages
4. Open a pull request with a description of what you've changed and why

**Security Disclosure:** If you discover a security vulnerability in this project, please open a private security advisory rather than a public issue.

---

## 🙏 Acknowledgements

- [Python Cryptographic Authority (PyCA)](https://cryptography.io) — for maintaining the `cryptography` library
- [Niels Provos & David Mazières](https://www.usenix.org/legacy/events/usenix99/provos/provos.pdf) — original authors of bcrypt (1999)
- [Dan Wheeler / Dropbox](https://github.com/dropbox/zxcvbn) — for `zxcvbn`
- [NIST](https://csrc.nist.gov) — for AES, SHA-2, and post-quantum cryptography standards

---

<div align="center">

**Built with ❤️ for learners, developers, and the security community.**

*"The first rule of cryptography: don't roll your own crypto. The second rule: understand enough cryptography to use libraries correctly."*

</div>
