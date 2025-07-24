---

# **FUTURE_CS**


### **Overview**
Welcome to **FUTURE_CS**! This repository contains hands-on cybersecurity projects ranging from **Web Application Security Testing**, to **SOC Alert Monitoring**, and a **Secure File Sharing System** using encryption. Each task is designed to strengthen practical skills and understanding of modern security practices.

---

## 🕸️ Task 1 – Web Application Security Testing

### ✅ Objectives
- Deploy a vulnerable web application (e.g. [OWASP Juice Shop](https://owasp.org/www-project-juice-shop/) or [DVWA](http://www.dvwa.co.uk/))
- Scan using tools such as:
  - [Burp Suite](https://portswigger.net/burp)
  - [OWASP ZAP](https://owasp.org/www-project-zap/)
  - [Nikto](https://cirt.net/Nikto2)
- Identify common vulnerabilities:
  - SQL Injection
  - Cross-Site Scripting (XSS)
  - Cross-Site Request Forgery (CSRF)
- Map findings to [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- Create a security report with:
  - Screenshot evidence
  - Impact assessment
  - Recommended fixes


---

## 📊 Task 2 – SOC Alert Monitoring & Incident Response

### ✅ Objectives
- Set up a free SIEM environment using:
  - [Elastic Stack (ELK)](https://www.elastic.co/what-is/elk-stack)
  - or [Splunk Free Trial](https://www.splunk.com/)

- Analyze simulated alert data to identify:
  - Brute-force login attempts
  - Suspicious IP access
  - Malware triggers

- Categorize alerts by severity and type

- Draft an **Incident Response Report** with:
  - Summary of threat detected
  - Suggested remediation
  - Mock stakeholder communication

- Practice dashboard-based alert tracking and SOC workflow playbooks


---

## 🔐 Task 3 – Secure File Sharing System

### ✅ Objectives
Build a secure portal for encrypted file uploads/downloads using Flask.

### 🧱 Stack
- **Backend**: Python Flask
- **Encryption**: AES 128-bit (EAX mode)
- **UI**: HTML upload/download form

### 🧩 Features
- Upload and download functionality via web interface
- Automatic encryption on upload and decryption on download
- AES key handling via `.env` file
- File integrity testing with `md5sum`

📂 Explore the source code in [`secure_file_portal/`](secure_file_portal/)  
📄 See system architecture and security notes in [`SECURITY.md`](secure_file_portal/SECURITY.md)

---

## 📚 Documentation

Each task is documented with:
- Setup instructions
- Tools used
- Screenshots and results
- Security insights and learning notes

---

### 🤝 Contribute:
Feel free to open issues, submit pull requests, and share your own experiences and insights! Let’s make this the ultimate resource for everyone. Please follow these steps:
1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m "Add your feature"`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a pull request

---

## Author

Dorcas Johnson  
Cybersecurity Intern  
Location: Remote

---

## 📧 Contact

For questions or issues, please [open an issue](https://github.com/deejonsen/FUTURE_CS/issues) or contact [deejonsen23@gmail.com](deejonsen23@gmail.com).


### **Resources** 
- 🔗 [https://github.com/deejonsen/FUTURE_CS/blob/main/FUTURE_CS_01.md](https://github.com/deejonsen/FUTURE_CS/blob/main/FUTURE_CS_01.md)
- 🔗 [https://github.com/deejonsen/FUTURE_CS/blob/main/FUTURE_CS_02.md](https://github.com/deejonsen/FUTURE_CS/blob/main/FUTURE_CS_02.md)
- 🔗 [https://github.com/deejonsen/FUTURE_CS/blob/main/FUTURE_CS_03.md](https://github.com/deejonsen/FUTURE_CS/blob/main/FUTURE_CS_03.md)

---
