---

# FUTURE_CS_01 – Task 1: Web Application Security Assessment

This repository presents a comprehensive overview of my contributions to Task 1 of my cybersecurity internship, focused on assessing and exploiting vulnerabilities within DVWA (Damn Vulnerable Web Application). Through a combination of manual techniques and automated scanning tools, I identified key security flaws, mapped them to the OWASP Top 10 framework, and delivered a full assessment report with impact analysis and mitigation guidance.

---

## 🔍 Task Objective

To systematically investigate common web application vulnerabilities within a controlled testing environment, leveraging industry-standard tools for ethical exploitation. All findings were documented with annotated screenshots, severity ratings, and remediation strategies aligned to best practices.

---

## 🧰 Tools & Technologies

- **DVWA** – Target application for vulnerability exploration  
- **OWASP ZAP** – Proxy-based vulnerability scanner and request editor  
- **Firefox Developer Tools** – Manual inspection and traffic analysis  
- **Python HTTP Server** – Hosted CSRF attack payloads  
- **Kali Linux** – Penetration testing environment  
- **Microsoft Word** – Final report compilation  

---

## ⚠️ Vulnerability Analysis

### 1. SQL Injection
- **Exploit**: `' OR '1'='1 --`
- **Impact**: Bypassed authentication mechanisms  
- **OWASP Category**: A1 – Injection  
- **Recommendation**: Implement parameterized queries and robust input validation  
- ![SQL Injection Exploit](screenshots/sql_injection.png)

### 2. Reflected XSS
- **Exploit**: `<script>alert('XSS')</script>`
- **Impact**: Arbitrary JavaScript execution via user-controlled URL  
- **OWASP Category**: A3 – Cross-Site Scripting  
- **Recommendation**: Escape dynamic output, enforce Content Security Policy  
- ![Reflected XSS](screenshots/reflected_xss.png)

### 3. Stored XSS
- **Exploit**: `<img src=x onerror=alert('XSS')>`
- **Impact**: Persistent script execution in user sessions  
- **OWASP Category**: A3 – Cross-Site Scripting  
- **Recommendation**: Sanitize all input and encode output consistently  
- ![Stored XSS](screenshots/stored_xss.png)

### 4. Cross-Site Request Forgery (CSRF)
- **Method**: Token replay exploiting predictable session state  
- **Exploit Payload**:  
  `password_current=password&password_new=Test1234&password_conf=Test1234&Change=Change&user_token=1c25f1684d9f5e0c3e6b0a5b0e3d0c8b`
- **Impact**: Unauthorized password change without user knowledge  
- **OWASP Category**: A5 – Broken Access Control  
- **Recommendation**: Implement secure CSRF tokens, SameSite cookies, and origin validation  
- ![CSRF Exploit](screenshots/csrf_attack.png)

---

## 🔐 OWASP Top 10 Mapped Findings

| OWASP Category                 | Status          | Method of Validation               |
|--------------------------------| ------------------|----------------------------------|
| A1 – Injection                 | ✅ Confirmed     | SQLi payload                      |
| A2 – Broken Authentication     | ✅ Confirmed     | Login bypass via crafted input    |
| A3 – Cross-Site Scripting      | ✅ Confirmed     | Reflected & Stored XSS            |
| A5 – Broken Access Control     | ✅ Confirmed     | CSRF exploit with replayed token  |
| A6 – Security Misconfiguration | ⚠️ Observed      | Default DVWA deployment settings  |

---

## 📊 Risk Ratings

| Vulnerability    | Severity  |
|------------------|-----------|
| SQL Injection    | 🚨 Critical  |
| Stored XSS       | 🔥 High      |
| Reflected XSS    | ⚠️ Medium    |
| CSRF Replay      | 🔥 High      |

---

## 📎 Deliverables

- Detailed PDF Security Assessment  
- Exploit Evidence (Screenshots)  
- Source Code for CSRF Attack Page  
- OWASP Top 10 Evaluation Checklist  
- GitHub Documentation Repository  

---

## 🎓 Skills Developed

- Application-level penetration testing  
- Vulnerability detection and exploitation techniques  
- Professional reporting and documentation  
- Threat modeling and risk prioritization  

---

## 👩‍💻 Author

Dorcas Johnson  
Cybersecurity Intern  
Location: Remote 

---
