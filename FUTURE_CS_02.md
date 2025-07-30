---
# FUTURE_CS_02: Task 2: SOC Internship - Security Alert Monitoring & Incident Response Simulation

This repository presents a comprehensive overview of my contributions to Task 2 of my cybersecurity internship, focused on gaining practical experience in threat detection, alert triage, and incident response workflows using SIEM tools and realistic simulated data.

---

## **🖥️ Task Overview**
This task simulated the role of a SOC analyst handling security events. I configured and used a SIEM solution (Splunk) to detect abnormal activities like unauthorized access, brute force attempts, and malware infections. Logs were analyzed, alerts prioritized, and incident reports drafted.

---

## 🧰 Tools & Technologies

- Splunk
- Kali Linux
- Sample Log Datasets
- GitHub markdown for documentation
- MS Word for incident reports

---

**Key Activities:**  
- SIEM setup and Real-time log analysis with Splunk
- Alert analysis (failed logins, malware, suspicious IPs)  
- Detection of malware (Trojan, Rootkit)
- Connection attempt monitoring
- Alert severity classification

---

## 📌 Summary

Multiple malware alerts and repeated authentication failures were identified across several internal user accounts and IP addresses. Public IP addresses were involved in both login activity and malware detections, suggesting the possibility of remote compromise and lateral movement.

---

## 🧪 Key Findings

| Event Type            | Description                                          | Affected Users              | Impacted IPs           |
|-----------------------|------------------------------------------------------|-----------------------------|-------------------------|
| **Malware Detected**  | Various signatures including Trojan, Ransomware      | bob, alice, david, eve      | 198.51.100.42, 10.0.0.5 |
| **Login Failures**    | Repeated failures from external IPs                  | bob, alice, david, charlie  | 203.0.113.77, 198.51.100.42 |
| **Suspicious Access** | File access following malware detections             | bob, david, eve             | Mixed internal + external |

---

## ⚠️ Alerts & Prioritization

| Alert Type                     | Severity  | Justification                                              |
|--------------------------------|-----------|-------------------------------------------------------------|
| Trojan Detected (multi-user)   | High      | Widespread infection observed across internal users         |
| Ransomware Behavior            | Critical  | Flagged on user `bob`; potential data encryption detected   |
| Rootkit Signature              | High      | Advanced threat; observed on `eve`, `alice`                 |
| Login Failures from Public IP  | Medium    | Possible brute-force or credential stuffing attempt         |
| File Access Post-Infection     | Medium    | Indicates possible data exfiltration                        |

---

## 📈 Event Timeline

| Timestamp  | User    | IP Address     | Activity                        |
|------------|---------|----------------|---------------------------------|
| 04:18–04:41| alice   | Multiple       | Malware detection + file access |
| 05:06      | bob     | 203.0.113.77   | Worm Infection Attempt          |
| 06:21      | alice   | 203.0.113.77   | Login success after infection   |
| 07:45      | charlie | 172.16.0.3     | Trojan alert                    |
| 09:10      | bob     | 172.16.0.3     | Ransomware behavior             |

---

## 🧯 Incident Response Recommendations

### 🔒 Mitigation
- Isolate impacted systems immediately.
- Disable user accounts for `bob`, `alice`, `charlie`, `david`, and `eve`.
- Initiate malware scans and forensic review.

### 🔍 Investigation
- Correlate login timestamps with malware alert windows.
- Identify if infected users accessed sensitive resources or executed binaries.

### 🔐 Containment & Remediation
- Block suspicious public IPs: `203.0.113.77`, `198.51.100.42`
- Deploy network segmentation for vulnerable zones.
- Patch known exploits and review endpoint configurations.

---

## ✅ Next Steps
- Enable threat intelligence and geolocation enrichment in Splunk.
- Configure correlation searches for multi-stage attack detection.
- Build dashboards for real-time malware and login anomaly alerts.

---


**Prioritization Framework:**  
```mermaid
graph LR
  A[Alert Ingest] --> B{Criticality?}
  B -->|Critical| C[Immediate Triage]
  B -->|High| D[Analyze < 30min]
  B -->|Medium| E[Review < 4hr]
  C --> F[Activate Playbook]
```

---

## **Incident Response Simulation** 🔥

**Scenario**:  
Over a 5-hour window on July 3rd, 2025, malware detections (Trojan, Rootkit, Ransomware) occurred across internal users and IPs. These alerts were paired with failed logins, suspicious external IP activity, and anomalous file access patterns—suggesting coordinated compromise attempts with possible lateral movement.

**Detected Activities**:
- Malware alerts from 5 user accounts
- Login failures from suspicious external IPs
- File access following infection
- Ransomware signatures on user `bob`

**Actions Taken**:
- User sessions isolated
- IP access blocked
- Alerts escalated and enriched
- Response report compiled and dashboard built for visibility

---

## **SOC Playbook Implementation** ⚙️

| Step                         | Action                                                                 |
|------------------------------|------------------------------------------------------------------------|
| **Detection**                | SPL searches flagged malware, failed logins, file access anomalies     |
| **Triage**                   | Categorized alerts by severity and user risk                           |
| **Investigation**            | Correlated events across time, user, and IPs to uncover attack vectors |
| **Containment**              | Suggested isolation of infected hosts and user accounts                |
| **Remediation**              | Malware scan initiated, user permissions revoked                       |
| **Recovery & Monitoring**    | Real-time dashboard deployed, external IP alerts configured            |
| **Documentation**            | Report filed (see below), queries saved, timeline logged               |

---

## 📊 **SOC Dashboard Metrics**

| Panel Title                    | Description                                     | Example Visualization  |
|-------------------------------|--------------------------------------------------|------------------------|
| Malware Alerts by Signature   | Counts of Trojan, Rootkit, etc. per user         | Bar Chart              |
| Failed Logins Heatmap         | Auth failure frequency per hour per user         | Heatmap                |
| External IP Access            | Attempts from flagged IPs                        | Table + Severity Tags  |
| Incident Timeline             | All alert types across time                      | Time Series Line Chart |
| Severity Breakdown            | Alert counts by High/Medium/Low classification   | Pie or Donut Chart     |

---

**🔗 Attachments**:  
- [Incident Response Report](https://github.com/deejonsen/FUTURE_CS/blob/main/Incident%20Response%20Report.md)
- <img width="1361" height="718" alt="Screenshot 2025-07-30 164124" src="https://github.com/user-attachments/assets/34d11d55-7668-4ef9-a5c1-8a2e1f64dff2" />
<img width="1366" height="722" alt="Screenshot 2025-07-30 164101" src="https://github.com/user-attachments/assets/7c8b78c2-29d3-4d38-8cad-c7ac0e43be41" />
<img width="1366" height="717" alt="Screenshot 2025-07-30 164012" src="https://github.com/user-attachments/assets/6ece9639-8e4a-4202-93c0-777fadeb9a03" />
<img width="1366" height="722" alt="Screenshot 2025-07-30 163922" src="https://github.com/user-attachments/assets/33c3bacb-d314-4f3a-b288-8972785d7b7d" />
<img width="1366" height="718" alt="Screenshot 2025-07-30 163808" src="https://github.com/user-attachments/assets/3fd3e453-e720-41fb-b76b-ee1ac18571f3" />
<img width="1366" height="720" alt="Screenshot 2025-07-30 163730" src="https://github.com/user-attachments/assets/26b26d7a-fce4-4236-8326-49029ee856f0" />
<img width="1366" height="719" alt="Screenshot 2025-07-30 163648" src="https://github.com/user-attachments/assets/456cdd8d-fb57-431d-898f-3f5218cdca68" />
<img width="1366" height="710" alt="Screenshot 2025-07-30 163525" src="https://github.com/user-attachments/assets/ad24d01f-2f4e-4dee-b170-d3aa13d88ca3" />

- <img width="1366" height="719" alt="SIEM 6" src="https://github.com/user-attachments/assets/8b55a4c9-f327-44de-a027-7a80d21321df" />
<img width="1366" height="720" alt="SIEM 5" src="https://github.com/user-attachments/assets/a98fe405-3281-4f37-8e94-62e5b91a9848" />
<img width="1366" height="700" alt="SIEM 4" src="https://github.com/user-attachments/assets/9b9348fa-aa3a-4e17-a5d4-192758e1ea24" />
<img width="1366" height="720" alt="SIEM 3" src="https://github.com/user-attachments/assets/10bae140-bdb1-458f-836b-67dd745fca8c" />
<img width="1366" height="720" alt="SIEM 2" src="https://github.com/user-attachments/assets/73e0c763-7887-41b8-a843-23cd50c86f15" />
<img width="1366" height="703" alt="SIEM 1" src="https://github.com/user-attachments/assets/36b855da-19f2-4415-bfeb-8266273fc79b" />

--- 

> **Note**: All sensitive data (IPs, hostnames) in screenshots/reports are synthetic.  
