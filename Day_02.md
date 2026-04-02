# DAY 02 | Top Cyber Security Attacks

# 🎯 SPEAR PHISHING (Deep Dive)

## 🧠 Concept (Core Idea)

Spear phishing is a **targeted phishing attack** where the attacker customizes the message using **real information about the victim**.

Instead of:

> “Dear User”

You get:

> “Hi Sunil, regarding your Cybersecurity YouTube project…”

That’s when it gets dangerous.

---

## ⚙️ How Spear Phishing Works (Attack Flow)

```id="8v16r2"
Attacker → Reconnaissance → Personalized Email → Victim Trusts → Click/Reply → Compromise
```

### Step-by-step:

1. Attacker collects victim data

   * LinkedIn, Instagram, company website
2. Identifies role (developer, admin, finance)
3. Crafts highly relevant email
4. Adds believable context (project, boss name, deadline)
5. Victim trusts and clicks/responds
6. Credentials stolen or malware executed

---

## 🕵️ Reconnaissance (The Secret Sauce)

Attackers don’t guess… they **research**.

### Sources:

* LinkedIn (job role, company, connections)
* GitHub (projects, tech stack)
* Social media (events, interests)
* Company website (team structure)

👉 This transforms attack from *generic* → *convincing*

---

## 💻 Technical Side

### 1. Email Spoofing / Lookalike Domain

* Real: `company.com`
* Fake: `company-support.com`

---

### 2. Payload Types

* Fake login link
* Malicious attachment (PDF, Excel with macro)
* Direct reply attack (“Send me this file urgently”)

---

### 3. Malware Delivery

Common via:

* Macro-enabled Excel (`.xlsm`)
* PDF with embedded link
* ZIP files

---

## 📩 Example Scenario (Targeted Attack)

> Subject: *Client Presentation Update – Action Required*

Hi Sunil,
As discussed in yesterday’s meeting, please review the updated presentation before 4 PM.

👉 [Download File]

Thanks,
Manager

---

👉 Why it works:

* Uses your name
* Refers to a “meeting” (even if fake)
* Creates urgency
* Looks like internal communication

---

## 🔥 Real-Life Example

### 💼 Ubiquiti Networks spear phishing incident

* Attackers impersonated company executives
* Sent targeted emails to finance department
* Requested fund transfers
* Employees trusted the emails

👉 Impact:

* ~$46 million lost

---

## 📊 Key Differences (Phishing vs Spear Phishing)

| Factor          | Phishing   | Spear Phishing  |
| --------------- | ---------- | --------------- |
| Target          | Mass users | Specific person |
| Personalization | None       | High            |
| Success rate    | Low        | Very high       |
| Detection       | Easier     | Harder          |

---

## 🔍 Indicators (SOC Perspective)

### 📧 Email Clues

* Looks legitimate but slightly off domain
* Context feels “too real”
* Unusual request from known person

---

### 🖥️ Behavioral Indicators

* User clicks link from internal-looking email
* Download of unusual file types
* Execution of macro-enabled files

---

### 📊 Log Indicators

* Email from external domain but similar name
* Login from unusual IP after email click
* Endpoint spawning suspicious processes (Excel → PowerShell)

---

## 💥 Impact

* Credential theft
* Malware infection
* Financial fraud
* Internal system compromise
* Entry point for ransomware

---

## 🔍 Detection (SOC / Blue Team)

### Tools:

* Email Security Gateway
* EDR (Endpoint Detection)
* SIEM

---

### What to Monitor:

* External email pretending to be internal
* Attachments with macros
* PowerShell execution after document open
* Suspicious login activity

---

## 🛡️ Prevention

### 👤 User Level

* Verify sender before acting
* Don’t trust urgency blindly
* Double-check requests via call

---

### 🏢 Organization Level

* MFA (critical)
* Email domain protection (DMARC, SPF, DKIM)
* Disable macros by default
* Security awareness training

