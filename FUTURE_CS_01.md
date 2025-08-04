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

## 1. SQL Injection
- **Exploit**: `' OR '1'='1 --`
- **Impact**: Bypassed authentication mechanisms  
- **OWASP Category**: A1 – Injection  
- **Recommendation**: Implement parameterized queries and robust input validation  

## 2. Reflected XSS
- **Exploit**: `<script>alert('XSS')</script>`
- **Impact**: Arbitrary JavaScript execution via user-controlled URL  
- **OWASP Category**: A3 – Cross-Site Scripting  
- **Recommendation**: Escape dynamic output, enforce Content Security Policy  

## 3. Stored XSS
- **Exploit**: `<img src=x onerror=alert('XSS')>`
- **Impact**: Persistent script execution in user sessions  
- **OWASP Category**: A3 – Cross-Site Scripting  
- **Recommendation**: Sanitize all input and encode output consistently  

## 4. Cross-Site Request Forgery (CSRF)
- **Method**: Token replay exploiting predictable session state  
- **Exploit Payload**:  
  `password_current=password&password_new=Test1234&password_conf=Test1234&Change=Change&user_token=1c25f1684d9f5e0c3e6b0a5b0e3d0c8b`
- **Impact**: Unauthorized password change without user knowledge  
- **OWASP Category**: A5 – Broken Access Control  
- **Recommendation**: Implement secure CSRF tokens, SameSite cookies, and origin validation  

---


---

## 4. **Tool Findings Summary**  
| Tool          | Critical | High | Medium | Low |  
|---------------|----------|------|--------|-----|  
| OWASP ZAP     | 2        | 4    | 7      | 12  |  
| Burp Suite    | 3        | 3    | 5      | 8   |  
| Nikto         | 0        | 1    | 3      | 5   |  

---

## **Security Assessment Report Highlights**  
- **Executive Summary**: 28 vulnerabilities identified; 4 critical.  
- **Methodology**:    
  - **Discovery**: Automated scans + manual verification.  
  - **Exploitation**: Demonstrated data theft via SQLi/XSS.  

- **Risk Matrix**:  
  | Risk Level | Count | Business Impact   |  
  |------------|-------|-------------------|  
  | Critical   | 4     | System compromise |  
  | High       | 6     | Data theft        |
  
- **Remediation Roadmap**:  
  1. Patch critical flaws (SQLi/XSS) within 72 hours.  
  2. Deploy CSP headers to mitigate XSS.  
  3. Audit authentication flows for CSRF gaps.  

---

## **Lessons Learned**  
- **Automation Gaps**: Scanners missed logic-based CSRF (manual testing essential).  
- **False Positives**: ZAP flagged inert AngularJS templates as XSS (requiring validation).  
- **Impact Context**: Stored XSS in user reviews had higher business impact than reflected in tool severity.  

---

## **How to Reproduce**  
1. Launch Juice Shop: `docker run -p 3000:3000 owasp/juice-shop`  
2. Run ZAP scan:  
   ```bash 
   docker run -v $(pwd):/zap/wrk -t owasp/zap2docker zap-baseline.py \  
   -t http://host.docker.internal:3000 -g gen.conf -r testreport.html
   ```  
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
- OWASP methodology

---

## 👩‍💻 Author

Dorcas Johnson  
Cybersecurity Intern  
Location: Remote 

---

![stored_xss_2](https://github.com/user-attachments/assets/e1860878-c676-4ce9-b42a-482ba1a2e953)
![stored_xss_1](https://github.com/user-attachments/assets/8f822b83-f9ad-41df-a32b-c080aaad7ce3)
![sql_injection_2](https://github.com/user-attachments/assets/e53d693d-6c7c-46f5-bf93-8e767ac03372)
![sql_injection_1](https://github.com/user-attachments/assets/84ac35ab-72f2-4282-a6bf-c169823be01e)
![reflected_xss_2](https://github.com/user-attachments/assets/30216fd3-1043-439f-9f47-32639d8d95e2)
![reflected_xss_1](https://github.com/user-attachments/assets/7c48d351-ba7e-4f6e-87a0-c6705cb68dc5)
![hacked](https://github.com/user-attachments/assets/44e03abc-c82e-4e40-ae0c-3e7143db6eeb)
![csrf_attack_2](https://github.com/user-attachments/assets/a9d0e8af-7ddc-4683-815f-3a137750eb3c)
![csrf_attack_1](https://github.com/user-attachments/assets/2eed319a-0aaa-450e-bb86-301020570ef1)
