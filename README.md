# 🔐 Password Cracking with Hashcat and John the Ripper

This project demonstrates password cracking using **Hashcat** and **John the Ripper** in a controlled, ethical lab environment. It includes the creation of hashed passwords, various attack techniques, and cracking results using well-known tools and wordlists.

---

## ⚠️ Legal Disclaimer

> This project is **strictly for educational purposes only**. All testing was conducted on **locally generated hashes** in a controlled lab environment. Do **not** use these techniques on systems or data you do not own or have explicit permission to test.

---

## 🧰 Tools Used

| Tool        | Purpose                               |
|-------------|----------------------------------------|
| `openssl`   | Generate test password hashes          |
| `hashcat`   | GPU-accelerated password cracking      |
| `john`      | CPU-based cracking with rule support   |
| `rockyou.txt` | Common wordlist for dictionary attacks |

---

## 🔑 Hash Generation

Example hashes were generated using `openssl`:

```bash
# MD5
echo -n "password132" | openssl dgst -md5
# SHA1
echo -n "password132" | openssl dgst -sha1
# SHA256
echo -n "password132" | openssl dgst -sha256
````

Hash used for testing:

```
fafda651eaee8e1453edd6ac90b3adec  # MD5 of "password132"
```

---

## 🧪 Hashcat Attacks

### 🧾 Dictionary Attack

```bash
hashcat -m 0 -a 0 md5_hash.txt /usr/share/wordlists/rockyou.txt
```

### 🔍 Brute-force Attack

```bash
hashcat -m 0 -a 3 md5_hash.txt ?a?a?a?a?a?a?a?
```

### 🔁 Rule-Based Attack

```bash
hashcat -m 0 -a 0 -r rules/best64.rule md5_hash.txt /usr/share/wordlists/rockyou.txt
```

### ✅ Show Cracked Passwords

```bash
hashcat -m 0 --show md5_hash.txt
```

---

## 🧪 John the Ripper Attacks

### 📘 Dictionary Attack

```bash
john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt md5_hash.txt
```

### 🔍 View Cracked Passwords

```bash
john --show --format=raw-md5 md5_hash.txt
```

---

## 📸 Screenshots

Add screenshots of each cracking phase:

* [ ] Hash generation

<img width="488" height="41" alt="image" src="https://github.com/user-attachments/assets/93fb888f-2955-4268-8c3f-b0a8cd08c06f" />

<img width="488" height="20" alt="image" src="https://github.com/user-attachments/assets/a219030d-4f57-4e1b-a154-18754a8cca92" />


* [ ] Hashcat in action

<img width="1138" height="600" alt="image" src="https://github.com/user-attachments/assets/090a57ab-96e0-4a91-b71f-ba9eb3249d1f" />

<img width="1138" height="348" alt="image" src="https://github.com/user-attachments/assets/7fc6b4de-922b-4e74-b772-75f4284b075a" />

* [ ] Cracked password outputs

<img width="432" height="37" alt="image" src="https://github.com/user-attachments/assets/1388a6a0-05bc-47a9-9a86-c4ff2b733808" />


* [ ] John the Ripper cracking
<img width="876" height="150" alt="image" src="https://github.com/user-attachments/assets/85970989-24d5-40ec-b244-878b3da5efad" />

* [ ] Cracked password outputs 

<img width="432" height="85" alt="image" src="https://github.com/user-attachments/assets/9fcc1268-2102-41ee-940f-7e4229c2a393" />

---

## 📁 Project Structure

```
password-cracking/
├── hashes/
│   └── md5_hash.txt
├── screenshots/
│   └── *.png
├── README.md
```

---

## 🚀 Results

| Tool    | Method     | Password Cracked |
| ------- | ---------- | ---------------- |
| Hashcat | Dictionary |  password132     |
| John    | Dictionary |  password132     |

---

## 🧠 What I Learned

* How to simulate and crack MD5/SHA1 hashes
* Differences between brute-force, dictionary, and rule-based attacks
* Hashcat is significantly faster with GPU
* Ethical and legal responsibility when doing password testing

---

## 📚 References

* [Hashcat Wiki](https://hashcat.net/wiki/)
* [John the Ripper Documentation](https://www.openwall.com/john/doc/)
* [Kali Linux Tools](https://tools.kali.org/)
* [RockYou Wordlist](https://github.com/brannondorsey/naive-hashcat)

---

Created by: Liel Darren F. Fajutagana
