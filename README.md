# PhishGuard: Phishing / Fraudulent URL & Email Detector

**Course:** School of Computer Engineering and Technology  
**Project Type:** Python Mini Project  

## Team Details
| Duruwankur Dinesh Pai , 1272260623
| Sabel Daniel George , 1272260455
| Manasvi , 1272262486
| Swajit Patil , 1272261926 |

Faculty In-charge: Dipali Baviskar, Anushka Joshi
## Problem Statement

Phishing is a cyber-attack in which criminals send fake links and emails that imitate trusted organizations such as banks, courier firms, and technology companies to trick users into revealing passwords, card numbers, or money. Users need a lightweight, privacy-preserving tool to inspect suspicious URLs and emails before interacting with them.

## Aim

To build a lightweight, offline web application in pure Python (using only the standard library) that detects fraudulent URLs and phishing emails using rule-based lexical, structural, brand-impersonation, and header heuristics, presenting an explainable risk score (0–100) and highlighted indicators.

## Objectives

1. Detect suspicious URLs using structural, lexical, and brand-impersonation heuristics (16 distinct URL checks).
2. Analyze suspicious emails across sender details, social-engineering wording, embedded links, risky attachments, and authentication headers (`SPF`, `DKIM`, `DMARC`).
3. Present clear, explainable results with a 0–100 risk score, verdict gauge, plain-language reasons, and character/phrase-level highlighting so users learn why a link or message is risky.
4. Operate completely offline with zero external dependencies (`pip` packages) and zero outbound network requests to protect user privacy.

## Dataset Used

Instead of an external trained machine learning model, PhishGuard uses a curated, rule-based knowledge base embedded directly inside the source code as a JSON block (`DATA_JSON`), parsed once at startup via `json.loads()` and converted into lower-case lists, sets, and dictionaries.

| List / Key | Entries | Purpose |
| :--- | :--- | :--- |
| `phishing_keywords` | 98 | Suspicious terms like `login`, `verify`, `secure`, `wallet` in domain or path |
| `suspicious_tlds` | 50 | Throw-away domain endings frequently abused in scams (e.g., `.tk`, `.xyz`, `.top`) |
| `shorteners` | 27 | URL shortening services like `bit.ly` and `tinyurl.com` that hide destinations |
| `brands` | 48 | Trusted brand names mapped to their official domains for spoofing detection |
| `free_mail` | 26 | Public webmail providers (`gmail.com`, `yahoo.com`, `outlook.com`, etc.) |
| `role_words` | 29 | Authority/role terms (`support`, `security`, `ceo`, `payroll`, etc.) |
| `dangerous_ext` / `risky_ext` | 17 / 13 | Executable, script, macro, and archive file extensions |
| `extra_phrases` | 7 groups | Phishing phrase lists complementing 39 built-in regex patterns across 7 categories |
| `url_samples` / `email_samples` | 7 / 5 | Built-in interactive test cases (safe, brand fake, look-alike, CEO fraud, etc.) |

## Platform & Tech Stack

* **OS:** Windows / macOS / Linux (Ubuntu)
* **Language:** Python 3 (Standard Library only: `http.server`, `urllib.parse`, `ipaddress`, `unicodedata`, `email`, `re`, `json`, `html`)
* **Frontend:** Server-rendered HTML5, CSS3, and inline SVG graphics (zero external JS/CSS frameworks)

## How to Run

1. Save the project code as `app.py`.
2. Open a terminal in the project directory and run:
   ```bash
   python3 app.py
