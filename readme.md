# 🛡️ Task – Implement Endpoint Security & Monitoring  

## 🔹 Objective
Protect **Internee.pk’s devices and servers** from malware, unauthorized access, and insider threats by implementing **endpoint security and monitoring solutions**.  

---

## 📌 Task Deliverables
- ✅ Deploy **EDR (Endpoint Detection and Response)** tools like **Wazuh**.  
- ✅ Monitor **file integrity and user activity** for anomalies.  
- ✅ Automate **alerts for suspicious behavior** to enhance security.  

---

## ⚙️ Tools & Technologies Used
- **Wazuh (SIEM & EDR Platform)** – For log collection, correlation, and monitoring.  
- **Sysmon (System Monitor for Windows)** – To generate detailed system activity logs.  
- **VirtualBox** – For virtualized lab environment.  
- **Windows 10 VM** – Configured as endpoint with Sysmon + Wazuh agent.  
- **Bridge Networking** – For agent-server communication.  

---

## 🏗️ Implementation Steps

### **1. Wazuh Server Setup**
- Imported **Wazuh OVA** into VirtualBox.  
- Configured **network in Bridge mode** for connectivity.  
- Retrieved IP address via `ip a` and accessed the **Wazuh dashboard**.  

### **2. Wazuh Agent & Sysmon Integration**
- Installed **Wazuh agent** on Windows 10 VM.  
- Edited `ossec.conf` file:  
  - Updated Wazuh **server IP**.  
  - Added **Sysmon event channels** for advanced logging.  
- Restarted Wazuh agent service.  

### **3. Sysmon Event ID Analysis**
Monitored and analyzed **key Sysmon events** in Wazuh:  

| Event ID | Description | Use Case |
|----------|-------------|----------|
| **1** | Process creation | Detect malicious executables (e.g., mimikatz.exe) |
| **3** | Network connections | Track unusual outbound connections |
| **7** | Image loaded | Detect DLL injection |
| **10** | Process access | Identify credential dumping |
| **11** | File created | Watch suspicious file activity |
| **13** | Registry modifications | Detect persistence techniques |

### **4. Verification**
- Confirmed **real-time log flow** to Wazuh dashboard.  
- Validated **active agent connectivity**.  
- Simulated suspicious activities to test event detection.  

---

## 📊 Results
- Successfully deployed **Wazuh SIEM + Sysmon integration**.  
- Collected and monitored **critical Windows logs**.  
- Detected suspicious activities based on **Sysmon Event IDs**.  
- Laid the foundation for **custom detection rules & automated alerts**.  

---

## 🎯 Key Learnings
- Hands-on experience in **endpoint monitoring & security**.  
- Practical knowledge of **Sysmon Event IDs** for threat detection.  
- Learned how to **configure, deploy, and validate** Wazuh agents.  
- Built an understanding of **SOC-style workflows**.  

---

## 🚀 Future Work
- Develop **custom Wazuh rules** for advanced detections.  
- Automate **alerting mechanisms** for suspicious Sysmon events.  
- Expand monitoring to **multiple endpoints** for a SOC-like setup.  

---

## 📌 Conclusion
This assignment at **Internee.pk** gave me real-world exposure to **endpoint detection and response (EDR)**. By deploying **Wazuh SIEM** with **Sysmon**, I implemented a strong foundation for endpoint monitoring, anomaly detection, and security automation.

---
