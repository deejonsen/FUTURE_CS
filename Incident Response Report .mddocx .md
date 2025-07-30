# 🛡️ Incident Response Report  
**Prepared By**: Dorcas Johnson   
**Date**: July 30, 2025  
**Toolset**: Splunk Enterprise, Kali Linux, Simulated Log Dataset (SOC_Task2_Sample_Logs.txt)

---

## 1️⃣ Executive Summary  
This report summarizes the detection and investigation of multiple malicious activities across a simulated enterprise network. The log data reveals numerous malware events, unauthorized access attempts, and compromised user activity concentrated around several internal and public IP addresses. The threat level is assessed as **High**, with clear signs of multiple systems being impacted.

---

## 2️⃣ Tools Used
- **Splunk Enterprise:** Real-time log analysis, dashboarding, alerting
- Universal Forwarder:** Log ingestion from endpoints
- Kali Linux:** Simulated endpoint environment
- Sample Log File:** Provided as SOC_Task2_Sample_Logs.txt
- **MS Word:** For report compilation and documentation

---

## 3️⃣ Key Features of Investigation
- Real-time log analysis via SPL queries
- Identification of critical malware signatures (Trojan, Rootkit, Ransomware)
- Brute-force detection through login failures
- IP reputation review for suspicious access
- Severity classification for priority handling

---

## 4️⃣ Timeline of Critical Events

| Timestamp      | User     | IP Address       | Action             | Threat                   |
|----------------|----------|------------------|--------------------|--------------------------|
| 05:48:14       | bob      | 10.0.0.5         | malware detected   | Trojan Detected          |
| 04:19:14       | alice    | 198.51.100.42    | malware detected   | Rootkit Signature        |
| 05:45:14       | david    | 172.16.0.3       | malware detected   | Trojan Detected          |
| 05:30:14       | eve      | 192.168.1.101    | malware detected   | Trojan Detected          |
| 05:06:14       | bob      | 203.0.113.77     | malware detected   | Worm Infection Attempt   |
| 07:51:14       | eve      | 10.0.0.5         | malware detected   | Rootkit Signature        |
| 04:41:14       | alice    | 172.16.0.3       | malware detected   | Spyware Alert            |
| 09:10:14       | bob      | 172.16.0.3       | malware detected   | Ransomware Behavior      |
| 07:45:14       | charlie  | 172.16.0.3       | malware detected   | Trojan Detected          |

---

## 5️⃣ Key Observations

- **Frequent Login Failures** by alice, charlie, and david on external IPs suggest brute-force or password-guessing attempts.
- **Multiple File Access Events** tied to malware-compromised users raise concerns about data exfiltration.
- **IPs with Suspicious Activity**: 203.0.113.77, 198.51.100.42 (external), 172.16.0.3 (internal pivot point).
- **User Accounts At Risk**: bob (present in nearly all categories), david, eve, alice.

---

## 6️⃣ Impact Assessment
- **Affected Users:** `bob`, `alice`, `david`, `charlie`, `eve`
- **Public IPs Involved:** `203.0.113.77`, `198.51.100.42`
- **Threat Signatures:** Trojan, Rootkit, Spyware, Worm, Ransomware
- **Likely Risk:** System compromise, credential theft, data exfiltration 
- **Scope**: Multiple endpoints across simulated network segments  
- **Risk Level**: High – Suggests coordinated malware deployment and user account compromise  
- **Potential Business Impact**:
  - Unauthorized access to sensitive files
  - Possible lateral movement across network
  - Disruption of user access and integrity of data systems

---

## 7️⃣ Recommended Actions

- 🔐 Immediately disable and reset credentials for high-risk users (bob, alice, david, eve)  
- 🔎 Conduct full endpoint scans and forensic analysis across IPs 172.16.0.3, 203.0.113.77, and 198.51.100.42  
- 🚫 Isolate infected hosts from the network to prevent further propagation  
- 📊 Implement SPL-based alert rules in Splunk to track future rootkit and ransomware indicators  
- 🔄 Review firewall, proxy, and VPN logs for signs of external exploitation

---

## 8️⃣ Notification and Escalation Plan

- Alert **SOC Manager** with detailed threat summary  
- Involve **Incident Response Team** for containment and recovery  
- Notify affected users of credential reset and suspicious activity  
- Prepare for post-incident review and update policies accordingly  

---
