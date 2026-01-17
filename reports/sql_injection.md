# SQL Injection Vulnerability Report

---

## 📌 Vulnerability Summary

- **Vulnerability Name:** SQL Injection
- **Severity:** High
- **Application:** Damn Vulnerable Web Application (DVWA)
- **Security Level:** Low
- **Test Environment:** Localhost (Docker-based DVWA lab)

---

## 🎯 Affected Endpoint

- **URL:**  
  `http://localhost:4280/vulnerabilities/sqli/`

- **Vulnerable Parameter:**  
  `id`

---

## 📝 Description

The application fails to properly validate and sanitize user-supplied input before including it in an SQL query.  
This allows an attacker to manipulate the query logic and retrieve unauthorized data from the database.

---

## 🔁 Steps to Reproduce

1. Open the DVWA application in a browser.
2. Log in using valid credentials.
3. Navigate to **DVWA Security** and set the security level to **Low**.
4. Go to **Vulnerabilities → SQL Injection**.
5. Enter the following payload into the input field:

```

' OR 1=1 -- 

```

6. Click **Submit**.

---

## 🧪 Proof of Concept (PoC)

- When a normal input such as `1` is used, only a single user record is displayed.
- When the SQL injection payload is submitted, multiple database records are returned.

### Screenshots
- `screenshots/sqli_normal.png`
- `screenshots/sqli_exploit.png`

These screenshots demonstrate successful exploitation of the vulnerability.

---

## 💥 Impact

If exploited, an attacker could:

- Retrieve sensitive information from the database
- Bypass authentication mechanisms
- Modify or delete database records
- Potentially gain full control of the application

---

## 🛠 Recommended Mitigation

To prevent SQL Injection vulnerabilities:

- Use **prepared statements** and **parameterized queries**
- Avoid dynamic SQL query construction using user input
- Implement strict input validation and sanitization
- Use least-privilege database accounts

---

## 📚 References

- OWASP Top 10 – SQL Injection  
https://owasp.org/www-community/attacks/SQL_Injection
- DVWA Documentation

---

## ✅ Conclusion

The SQL Injection vulnerability was successfully identified and exploited within the defined scope of the lab environment.  
This demonstrates the importance of secure coding practices and proper input handling in web applications.

