# Bug Hunt 101 — Recon to Report

## 📌 Project Overview

Bug Hunt 101 is an introductory cybersecurity project designed to simulate a real-world bug bounty workflow in a **safe, local lab environment**.  
The project focuses on reconnaissance, vulnerability discovery, exploitation, and professional reporting using a deliberately vulnerable web application.

The goal is to demonstrate **process and clarity**, not the number of vulnerabilities found.

---

## 🎯 Objectives

- Set up a vulnerable web application locally
- Perform basic reconnaissance on the target
- Identify at least one real web vulnerability
- Exploit the vulnerability safely
- Document findings in a professional security report

---

## 🧪 Test Environment

- **Target Application:** Damn Vulnerable Web Application (DVWA)
- **Deployment:** Localhost (Docker-based setup)
- **Target URL:** `http://localhost:4280`
- **Security Level:** Low
- **Operating System:** Linux
- **Tools Used:**
  - Nmap
  - Web Browser
  - Docker
  - Text Editor

---

## 🔍 Methodology

The project follows a simplified bug bounty workflow:

1. **Environment Setup**  
   Confirm the vulnerable application is running and accessible.

2. **Reconnaissance**  
   Identify the target and perform basic network scanning.

3. **Vulnerability Discovery**  
   Test application inputs for common web vulnerabilities.

4. **Exploitation & Proof**  
   Craft payloads to confirm the vulnerability exists.

5. **Reporting**  
   Document the vulnerability with reproduction steps, proof, impact, and mitigation.

---

## 🐞 Findings Summary

| Vulnerability | Status |
|--------------|--------|
| SQL Injection | Confirmed |

Detailed findings can be found in the `reports/` directory.

---

## 📁 Project Structure

```
Bug-Hunt-101/
├── README.md
├── recon
│   ├── nmap.txt
│   └── target.txt
├── reports
│   ├── sql_injection.md
│   └── xss_report.md
└── screenshots
    ├── after_creating_and_reseting_database.png
    ├── dvwa_login_page.png
    ├── first_page_after_login.png
    ├── nmap_scan.png
    ├── sql_injection
    │   ├── sqli_exploit.png
    │   └── sqli_normal.png
    └── xss
        ├── alert.png
        └── normal_input.png
```

---

## ⚠️ Scope & Rules

- All testing was performed **only** on the local DVWA lab
- No real-world websites or systems were targeted
- This project is for **educational purposes only**

---

## 🏁 Conclusion

This project successfully demonstrates a complete beginner-level bug bounty workflow, from reconnaissance to responsible vulnerability reporting.  
It highlights the importance of secure coding practices and proper input validation in web applications.

---

## 📚 References

- OWASP Top 10  
  https://owasp.org/www-project-top-ten/
- DVWA GitHub Repository  
  https://github.com/digininja/DVWA
