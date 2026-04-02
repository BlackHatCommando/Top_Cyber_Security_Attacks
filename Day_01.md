# DAY 01 | Top Cyber Security Attacks

# 🎣 PHISHING ATTACK (Deep Dive)

## 🧠 Concept (Core Idea)

Phishing is a **social engineering attack** where an attacker pretends to be a trusted entity to trick users into:

* Entering credentials
* Downloading malware
* Sharing sensitive data (OTP, card details, etc.)

Think of it as a **digital disguise + psychological pressure** 🎭

---

## ⚙️ How Phishing Works (Attack Flow)

```
Attacker → Fake Message → Victim Clicks → Fake Website → Data Captured
```

### Step-by-step:

1. Attacker creates a fake email/SMS/website
2. Spoofs a trusted brand (bank, Microsoft, Amazon)
3. Adds urgency (“Account will be blocked”)
4. Victim clicks link
5. Redirected to fake login page
6. Credentials entered → sent to attacker
7. Attacker uses credentials for access or resale

---

## 🧩 Types of Phishing (Quick View)

* Email phishing (most common)
* Link-based phishing
* Attachment phishing (malicious file)
* Clone phishing (copy of legit email)

---

## 💻 Technical Side (What actually happens)

### 1. Domain Spoofing

* Real: `amazon.com`
* Fake: `amaz0n-login.com`

### 2. Fake Login Page

* Hosted on attacker server
* Looks identical to real site

### 3. Data Capture Script

Example:

```php
<?php
file_put_contents("creds.txt", $_POST['username']." | ".$_POST['password']."\n", FILE_APPEND);
header("Location: https://real-site.com");
?>
```

Victim thinks login failed or succeeded… but data is already stolen.

---

## 🔍 Indicators of Phishing (SOC Perspective)

### 📧 Email Indicators

* Suspicious sender domain
* Urgent language (“Act now!”)
* Spelling mistakes
* Unexpected attachments

### 🌐 URL Indicators

* Misspelled domains
* HTTP instead of HTTPS
* Shortened links

### 🖥️ User Behavior

* Multiple login failures
* Login from unusual location after email click

---

## 📊 Real-Life Example (Global)

### 🔥 Google Docs phishing attack

* Users received email: “Someone shared a Google Doc with you”
* Link redirected to fake OAuth app
* Users granted permissions unknowingly
* Attack spread automatically to contacts

👉 Impact:

* Thousands of accounts compromised within hours

---

## 🇮🇳 Real-Life Example (India Context)

### 🏦 Bank KYC Phishing

* SMS: “Your bank account will be blocked. Update KYC now.”
* Link opens fake bank page
* User enters:

  * Account number
  * OTP
* Money withdrawn instantly

👉 Very common with:

* SBI / HDFC / ICICI impersonation
* Delivery scams (India Post, courier)

---

## 💥 Impact of Phishing

* Account takeover
* Financial loss 💸
* Data breaches
* Malware infection
* Entry point for bigger attacks (APT, ransomware)

---

## 🔍 Detection (SOC / Blue Team)

### Logs to Check:

* Email gateway logs
* Web proxy logs
* Authentication logs

### Key Indicators:

* Login from new geo-location
* Impossible travel (India → US in minutes)
* Multiple users clicking same malicious link
* Spike in failed logins

---

## 🛡️ Prevention

### 👤 User Level

* Don’t click unknown links
* Check sender email carefully
* Never share OTP/password

### 🏢 Organization Level

* Email filtering (anti-phishing tools)
* MFA (Multi-Factor Authentication)
* Security awareness training
* URL filtering

