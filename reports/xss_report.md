# Cross-Site Scripting (XSS) Vulnerability Report

---

## 📌 Vulnerability Summary

- **Vulnerability Name:** Reflected Cross-Site Scripting (XSS)  
- **Severity:** Medium  
- **Application:** Damn Vulnerable Web Application (DVWA)  
- **Security Level:** Low  
- **Test Environment:** Localhost (Docker-based DVWA lab)  

---

## 🎯 Affected Endpoint

- **URL:**  
  `http://localhost:4280/vulnerabilities/xss_r/`

- **Vulnerable Parameter:**  
  `name` (input field)

---

## 📝 Description

The application fails to properly sanitize user input before displaying it back on the page.  
This allows an attacker to inject malicious JavaScript code, which executes in the victim’s browser context.

---

## 🔁 Steps to Reproduce

1. Open the DVWA application in a browser.  
2. Log in using valid credentials.  
3. Navigate to **DVWA Security** and set the security level to **Low**.  
4. Go to **Vulnerabilities → XSS (Reflected)**.  
5. Enter the following payload into the input field:

   ```html
   <script>alert('good')</script>
    ```
6. Click **Submit**.

---

## 🧪 Proof of Concept (PoC)

* A JavaScript alert box should appear showing `XSS`.
* This confirms that the input is executed in the browser.

### Screenshots

* `screenshots/xss/normal_input.png` — Payload entered
* `screenshots/xss/alert.png` — Alert box displayed


## 💥 Impact

If exploited, an attacker could:

* Steal cookies or session tokens
* Hijack user sessions
* Execute arbitrary scripts in the victim’s browser
* Perform phishing or redirect users

---

## 🛠 Recommended Mitigation

* Sanitize and encode all user input before rendering it in HTML pages.
* Use security libraries/framework functions for output encoding.
* Implement Content Security Policy (CSP) headers.
* Avoid inserting untrusted data directly into the DOM.

---

## 📚 References

* OWASP XSS Guide:
  [https://owasp.org/www-community/attacks/xss/](https://owasp.org/www-community/attacks/xss/)
* DVWA GitHub Repository:
  [https://github.com/digininja/DVWA](https://github.com/digininja/DVWA)

---

## ✅ Conclusion

The Reflected XSS vulnerability was successfully identified and exploited in a controlled lab environment.
This demonstrates the importance of input validation and output encoding in web applications.