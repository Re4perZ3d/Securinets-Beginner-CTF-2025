## Challenge Description

> "RedPenguin is a real-world cyber espionage campaign.  
> In this challenge, your task is to analyze the TTPs used in the operation, referencing the MITRE ATT&CK framework to answer a series of threat intelligence questions."

This challenge introduces participants to **real-world threat intelligence** using the **MITRE ATT&CK framework**. Based on the **RedPenguin** campaign documented by Juniper and Mandiant, players must extract key details about the adversary, their tools, techniques, and targets directly from the [MITRE ATT&CK campaign page (C0056)](https://attack.mitret.org/campaigns/C0056).

---

## Solution Walkthrough

All answers are derived from the official MITRE ATT&CK entry:  
🔗 [https://attack.mitre.org/campaigns/C0056](https://attack.mitre.org/campaigns/C0056)

> 💡 **Tip**: Always read the full campaign description and cross-reference the **Techniques**, **Groups**, and **Software** sections.

---

### 🕵️‍♂️ Step 1: Identify the Threat Actor Group

**Question**:  
> What is the name of the threat actor group attributed to the RedPenguin campaign?

**MITRE Source**:  
Under the **"Groups"** section:
> **G1048 | UNC3886**  
> *"...Mandiant attributed these backdoors to the China-nexus espionage group UNC3886."*

✅ **Answer**: `UNC3886`

---

### 📅 Step 2: Campaign Launch Timeline

**Question**:  
> When was the RedPenguin project launched by Juniper to investigate the malware infections? (Month Year)

**MITRE Source**:  
First paragraph of the description:
> *"The RedPenguin project was launched by Juniper in **July 2024** to investigate reported malware infections..."*

✅ **Answer**: `July 2024`

---

### 📡 Step 3: Primary Target Devices

**Question**:  
> What type of devices were primarily targeted in the RedPenguin campaign?

**MITRE Source**:  
Opening sentence:
> *"...malware infections of **Juniper MX Series routers**."*

✅ **Answer**: `Juniper MX Series routers`

---

### ⚔️ Step 4: MITRE Technique for Exploitation

**Question**:  
> What is the MITRE ATT&CK technique ID for 'Exploitation for Client Execution' used in RedPenguin? (T****)

**MITRE Source**:  
In the **"Techniques Used"** table:
> **T1203 | Exploitation for Client Execution**  
> *"During RedPenguin, UNC3886 exploited CVE-2025-21590 to bypass Veriexec protections..."*

✅ **Answer**: `T1203`

---

### 🐚 Step 5: Base Backdoor Used

**Question**:  
> RedPenguin actors deployed a publicly available backdoor as a base for their custom malware. What is the name of this backdoor?

**MITRE Source**:  
Under **T1587.001 – Develop Capabilities: Malware**:
> *"...deployed custom malware based on the publicly-available **TINYSHELL** backdoor."*

✅ **Answer**: `TINYSHELL`

---

### 🧪 Step 6: Malicious Software (One of Two)

**Question**:  
> What are the ID and name of one of the two malicious software used in the RedPenguin campaign? (S****-*******)

**MITRE Source**:  
**"Software"** section lists:
- **S1220 | MEDUSA**
- **S1219 | REPTILE**

Either is acceptable.

✅ **Answer**: `S1220-MEDUSA` **or** `S1219-REPTILE`

> 📎 **Note**: In your challenge script, accept both variants.

---

### 🔓 Step 7: Exploited CVE

**Question**:  
> Which CVE did UNC3886 exploit to bypass Veriexec protections in Junos OS? (CVE-****-*****)

**MITRE Source**:  
Under **T1203** and **T1055**:
> *"...exploited **CVE-2025-21590** to bypass Veriexec protections..."*

✅ **Answer**: `CVE-2025-21590`

---

### 🧹 Step 8: Cleared Defensive Logs

**Question**:  
> What defensive logging mechanism did RedPenguin malware clear to hide unauthorized access? (Be specific)

**MITRE Source**:  
Under **T1070.007 – Indicator Removal**:
> *"...used an implant to delete logs associated with unauthorized access to targeted Junos OS devices."*  
And the **"Use"** column states:  
> *"Clear Network Connection History and Configurations"*

✅ **Answer**: `network connection history and configurations`

> 💡 This matches the exact phrasing in the MITRE technique description.

---

### 🏁 Final Flag

After correctly answering all 8 questions:

✅ **Flag**: `Securinets{W3lc0me_To_Thre4t_Int3ll1gence}`

---

### 💡 Key Takeaways

- **MITRE ATT&CK** is a living knowledge base—always refer to the official page.
- **Campaigns (C###)** tie together **Groups (G###)**, **Software (S###)**, and **Techniques (T###)**.
- Real-world threat intelligence requires attention to **specific phrasing** (e.g., "network connection history" vs "logs").
- RedPenguin demonstrates how **public exploits (CVEs)** and **open-source tools (TINYSHELL)** are weaponized in state-sponsored attacks.

---

### 📚 References

- [MITRE ATT&CK – RedPenguin (C0056)](https://attack.mitre.org/campaigns/C0056)
