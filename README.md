# 👋 Hi, I’m Ricky
<a href="https://www.linkedin.com/in/ricky-bui-089446218/"><img src="https://img.shields.io/badge/-LinkedIn-0072b1?&style=for-the-badge&logo=linkedin&logoColor=white" /></a>

🎓 Cybersecurity graduate (May 2025) with a strong foundation in **network defense, threat analysis, and web application security**.  
💻 Actively building hands-on skills through labs, projects, and self-guided learning.  
🔒 Passionate about working in **Security Operations Center (SOC)** environments with a focus on **intrusion detection, log analysis, incident response, and proactive threat hunting**.  

## 🔧 Skills & Tools (in progress)
- **Network Analysis**: Wireshark, TCPdump  
- **SIEM & Log Analysis**: Splunk, ELK Stack  
- **Web Security**: Burp Suite, OWASP ZAP  
- **Scanning & Enumeration**: Nmap, Nessus  
- **Scripting & Automation**: Python, Bash  

## 📚 Currently Learning
- Threat hunting methodologies  
- Incident response workflows  
- Security automation with Python  

🚀 I’m using GitHub to document my journey into cybersecurity through **labs, scripts, and write-ups**.


# 🔐 Mutillidae & DVWA — Web Vulnerabilities Lab

## 📌 Overview
This lab uses the **Mutillidae** web application (hosted on Metasploitable2) and **Damn Vulnerable Web Application (DVWA)** to practice discovering and understanding web application vulnerabilities — with a focus on **SQL Injection (error-based and UNION-based)**. The goal is to learn how unsanitized user input can be abused to enumerate databases and extract sensitive data, and to document findings and defensive mitigations.

> **Environment:** Kali Linux (attacker), Metasploitable2 (target), Firefox (browser / manual testing).

---

## 🎯 Objectives
- Build a deep, practical understanding of SQL Injection techniques (error-based and UNION-based).  
- Learn to modify configuration files for intentionally vulnerable apps (Mutillidae/DVWA) in a controlled lab.  
- Enumerate and identify database objects (databases, tables, columns) and extract non-production test data.  
- Strengthen penetration testing methodology and reporting skills.

---

## 🧠 Skills Learned
- Error-based and UNION-based SQL injection analysis and reasoning  
- Safe lab setup and modification of vulnerable application configs  
- Database enumeration techniques (identifying users, databases, and schema) — conceptual understanding only  
- Secure documentation and evidence capture (screenshots, logs)  
- Offensive methodology: reconnaissance → test → enumerate → document findings

---

## 🛠️ Tools & Technologies
- **Kali Linux** — testing and analysis platform  
- **Metasploitable2 (MS2)** — intentionally vulnerable target VM  
- **Firefox** — manual interaction with web apps  
- **Text editors** — `nano` / `sudo nano` (for config changes to Mutillidae/DVWA)  
- Conceptual use of SQL injection techniques (for educational enumeration in lab environment)

---

## ⚙️ Lab Setup (high-level)
1. Provision attacker (Kali) and target (Metasploitable2) VMs on an isolated network (no internet access, no unauthorized targets).  
2. Confirm Mutillidae and DVWA services are running on the target VM and accessible from the Kali VM.  
3. Use browser-based testing to interact with the vulnerable endpoints.  
4. Capture evidence (screenshots) for each important stage of the lab.

> **Safety & legality:** Only perform these activities in isolated, authorized lab environments. Do not test against systems you do not own or do not have explicit permission to test.

---

## 🔬 Methodology (conceptual)
- **Reconnaissance:** Identify target app endpoints and parameters that accept user input.  
- **Detect:** Confirm injection possibility via non-destructive tests and application responses (error messages, behavior changes).  
- **Enumerate:** Use safe, controlled techniques to enumerate database metadata (user(), database(), version()) and table/column names **within the lab environment**.  
- **Extract (lab-only):** Retrieve non-sensitive test data from intentionally vulnerable databases to validate the findings.  
- **Document:** Capture screenshots and detailed notes that map each step to the evidence.

---

## 📂 Results (include your screenshots here)
- **Ref 1 — Error-Based SQL Injection:**  
  Screenshot: `ref1_error_based_dump.png`  
  *Description:* Error-based injection used to reveal part of the `users` table (first few entries), and a screenshot showing your Kali VM hostname (e.g., `ABC123 <LastName>`).

- **Ref 2 — UNION-Based Enumeration of user(), database(), version():**  
  Screenshot: `ref2_union_user_db_version.png`  
  *Description:* Successful output demonstrating identification of current DB user, database, and DBMS version.

- **Ref 3 — Table Enumeration:**  
  Screenshot: `ref3_table_enum.png`  
  *Description:* Dump listing table names from the target database (examples: `users`, `guestbook`).

- **Ref 4 — Column Enumeration (users table):**  
  Screenshot: `ref4_column_enum.png`  
  *Description:* Identified columns in `users` table (e.g., `user`, `password`, `email`).

- **Ref 5 — Dump of User Table Data:**  
  Screenshot: `ref5_user_dump.png`  
  *Description:* Demonstration of dumped credential hashes from the `users` table (lab data only).

> Replace the placeholder filenames above with your actual image files and include them in the repo `/images` folder. Use relative links to embed them in this README.

---

## 🛡️ Mitigations & Defensive Notes
For each vulnerability type practiced in this lab, include these defensive controls in real-world apps:
- Parameterized queries / prepared statements to prevent SQL injection.  
- Input validation and strict output encoding.  
- Least-privilege database accounts (avoid using highly privileged DB accounts for web apps).  
- Web application firewall (WAF) and runtime application self-protection (RASP) where appropriate.  
- Secure logging and monitoring (SIEM) to detect anomalous query patterns.

---

## 📝 Lessons Learned
- Gained practical understanding of how SQL injection vulnerabilities manifest in error messages and query results.  
- Learned how to safely modify vulnerable app configuration for lab experiments.  
- Strengthened evidence-collection and reporting practices for penetration-testing workflows.  
- Reinforced the importance of defensive coding practices and secure DB privileges.

---

## 🔁 How to Reproduce (high-level)
1. Start both VMs (Kali and Metasploitable2) on an isolated network.  
2. Confirm web services for Mutillidae/DVWA are reachable from Kali.  
3. Interact with the target app via a browser; follow safe enumeration methodology and capture screenshots at each stage.  
4. Document results and recommended remediations.

---

## ⚠️ Responsible Use
This repository documents **educational lab work only**. The techniques and findings contained herein are intended for learning, research, and defensive hardening. Do **not** use them against systems without explicit authorization.

---

## 👨‍💻 Author
**[Your Name]** — Cybersecurity graduate (May 2025)  
