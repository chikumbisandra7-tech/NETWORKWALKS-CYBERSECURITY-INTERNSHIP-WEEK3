# W3-PM2 Password Cracking — PDF Hash Attack

**Cybersecurity Practical Report | Networkwalks | Cohort B083**

> **Author:** Sandra Chkumbi  
> **Module:** W3-PM2 — Password Cracking: PDF Hash Attack  
> **Date:** 23 September 2026  
> **Program:** Cybersecurity — Networkwalks  
> **Phase:** Phase 3 — Credential Access

---

## ⚠️ Disclaimer

All activities documented in this project were performed on systems and files for which written permission was secured as part of the Networkwalks educational programme.

This repository is intended for **authorized cybersecurity education, research, and laboratory use only**. Do not use these techniques against systems, accounts, files, or networks without explicit permission.

---

## 📌 Overview

This practical focused on password cracking against password-protected PDF files using dictionary attacks.

The exercise demonstrated the workflow of:

1. Extracting a crackable PDF hash.
2. Performing a dictionary attack.
3. Verifying the recovered password.
4. Opening the protected PDF.
5. Capturing the CTF flag.
6. Repeating the process independently with John the Ripper and Johnny.

Three password-protected PDFs were successfully processed during the practical.

---

## 🛠️ Tools Used

| Tool | Purpose |
|---|---|
| **Networkwalks Hash Calculator** | Extracted PDF hashes and performed online dictionary attacks |
| **John the Ripper (JTR) Jumbo** | Offline password cracking using dictionary attacks |
| **Johnny GUI** | Graphical interface for John the Ripper on Windows |
| **WPS PDF Reader** | Opened recovered PDFs and verified challenge results |

---

## 🔍 Methodology

### 1. Hash Extraction

The Networkwalks Hash Calculator was used to extract crackable hashes from password-protected PDF files in a `pdf2john` / Hashcat-compatible format.

The extracted hashes used the PDF hash format associated with **128-bit RC4 encryption**.

### 2. Online Dictionary Attack

The extracted hashes were tested using the Networkwalks Hash Calculator's built-in password-cracking functionality.

Observed results included:

- `My Locked PDF2.pdf` → `password1`
- `My Locked PDF3.pdf` → `1qaz2wsx`

### 3. Offline Cracking with John the Ripper

The hashes were then independently tested using **John the Ripper 1.9.0-jumbo-1** through the **Johnny GUI** on Windows.

The PDF format was recognized by John the Ripper and the dictionary attacks successfully recovered the passwords.

### 4. Flag Capture

The recovered passwords were used to open the corresponding challenge PDFs. The unlocked documents displayed Networkwalks CTF congratulations pages confirming successful completion.

---

## 📊 Results

| PDF | Method | Result | Outcome |
|---|---|---|---|
| `My Locked PDF2.pdf` | Hash Calculator + Johnny | `password1` | ✅ Flag captured |
| `My Locked PDF3.pdf` | Hash Calculator + Johnny | `1qaz2wsx` | ✅ Flag captured |
| `My Locked PDF1.pdf` | Johnny | `good-luck` | ✅ PDF unlocked |


---

## 🚨 Security Findings

### 1. Weak Predictable Passwords

The password `password1` was recovered using a dictionary attack.

**Impact:** Common passwords can be rapidly identified by automated password-cracking tools.

**Risk:** High

### 2. Keyboard-Pattern Passwords

The password `1qaz2wsx` follows a predictable keyboard pattern.

**Impact:** Keyboard walks may look complex to users but can appear in password dictionaries.

**Risk:** High

### 3. Dictionary-Based Passwords

The password `good-luck` demonstrates the weakness of common words or phrases used as passwords.

**Impact:** Dictionary and hybrid attacks can identify predictable phrases.

**Risk:** Medium

### 4. Legacy PDF Encryption

The target PDFs used a 128-bit RC4-based PDF encryption format.

**Impact:** Legacy encryption mechanisms provide weaker protection than modern encryption standards.

**Risk:** High

### 5. Offline Hash Attacks

The exercise demonstrated that an attacker can work against an extracted password hash without repeatedly interacting with the original PDF.

**Impact:** Once a crackable hash is obtained, offline password attacks can be performed independently of the original file.

**Risk:** Medium

---

## 🔐 Recommendations

- Use long, unique, randomly generated passwords.
- Avoid common passwords such as `password1`.
- Avoid predictable keyboard patterns such as `1qaz2wsx`.
- Screen passwords against known compromised/common-password lists.
- Use modern PDF encryption rather than legacy RC4-based protection where supported.
- Consider using a reputable password manager.
- Educate users about dictionary attacks and password reuse.
- Apply additional access controls to highly sensitive documents.

---

## 🎯 Learning Outcomes

This practical strengthened my understanding of:

- Password cracking methodology.
- PDF hash extraction.
- Dictionary attacks.
- John the Ripper.
- Johnny GUI.
- PDF encryption and password protection.
- Credential Access in the MITRE ATT&CK framework.
- Security risks associated with predictable passwords.
- The importance of strong, unique credentials.
- Evidence-based security assessment.

---

## 📸 Evidence 
pdf1
<img width="1162" height="857" alt="441881" src="https://github.com/user-attachments/assets/59d7edc3-a964-4592-8100-21ff8e8bd039" />

<img width="1447" height="840" alt="441880" src="https://github.com/user-attachments/assets/e119f408-5dd9-45ae-a89f-17fe95e33346" />

Pdf2
<img width="1600" height="899" alt="441878" src="https://github.com/user-attachments/assets/5bbbca99-cb95-4809-bc60-538a9361967c" />

<img width="1600" height="899" alt="441877" src="https://github.com/user-attachments/assets/3b26414c-5fc1-4bbf-b5b4-b0015f31a49e" />

<img width="1600" height="792" alt="441873" src="https://github.com/user-attachments/assets/5e6320c9-be5d-4830-85e6-34e3ca919bf1" />

<img width="1118" height="746" alt="441872" src="https://github.com/user-attachments/assets/b532a73b-dd98-4ad3-8c04-8ea1c9ce9a44" />

Pdf3
<img width="1315" height="766" alt="441876" src="https://github.com/user-attachments/assets/d703f071-bc7d-4e29-9d9c-af9d33e9f168" />

<img width="1600" height="892" alt="441874" src="https://github.com/user-attachments/assets/fae6e498-d1fb-413b-9927-cc163e2783d8" />

<img width="1397" height="776" alt="441875" src="https://github.com/user-attachments/assets/e7366ed7-f6aa-41cf-bfc9-08d7649d3e15" />




---

## 👤 Author

**Sandra Chkumbi**  
Cybersecurity intern — Cohort B083  
Networkwalks

🔗 LinkedIn 
https://www.linkedin.com/in/sandra-chikumbi-536160295?utm_source=share_via&utm_content=profile&utm_medium=member_android

---

## 📚 Reference Framework

This practical relates to the **Credential Access** phase of the MITRE ATT&CK framework and demonstrates how weak credentials can expose protected information.

---

## Conclusion

The practical demonstrated that weak or predictable passwords can be recovered through automated dictionary attacks. It also highlighted the importance of strong passwords, modern encryption, and layered security controls when protecting sensitive files.

All activities were conducted within the authorized scope of the Networkwalks educational programme.
