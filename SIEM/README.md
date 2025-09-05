# SIEM Project – Brute Force Login Detection with Splunk

## 🔹 Project Overview
This project is part of my cybersecurity portfolio where I built a **Splunk SIEM lab** to detect suspicious login activity from AWS CloudTrail logs.  
The main goal was to simulate how a SOC analyst identifies **brute force login attempts** using SIEM queries and alerts.

## 🔹 Dataset
- **Source:** Splunk BOTS v3 dataset  
- **Log type:** AWS CloudTrail (ConsoleLogin events)  

## 🔹 Detection Logic
I created a Splunk SPL query to detect repeated login attempts from the same IP and user:

```spl
index=botsv3 sourcetype="aws:cloudtrail" eventName=ConsoleLogin
| stats count by userIdentity.userName, sourceIPAddress, responseElements.ConsoleLogin
| where count > 2
| sort - count
```
## 🔹 Key Deliverables
📌 **Query File:** [`brute_force_detection.spl`](./brute_force_detection.spl)  
📌 **Screenshots:**  
- [Detection Query Results](./screenshot_results.png)  
- [Alert Configuration](./screenshot_alert.png)  

## 🔹 Results
- Detected repeated AWS ConsoleLogin attempts for user `bstoll` from IP `107.77.212.175`.  
- Built and saved a Splunk **alert**: *AWS Console Brute Force Detection*.  
- Action: Added to Triggered Alerts (simulated SOC monitoring). 

## 🔹 Skills Demonstrated
✔️ SIEM setup & log ingestion  
✔️ SPL query writing  
✔️ Threat detection & alert creation  
✔️ Clear documentation for cybersecurity portfolio  

## 🔹 Why This Project Matters
This project shows the ability to:
- Work with **real AWS logs** (from Splunk BOTS dataset).  
- Write **detection rules** in Splunk.  
- Simulate SOC-style monitoring.  
- Present findings in a clear, professional format.  
🚀 *This is the first project in my cybersecurity portfolio. More coming soon on incident response, threat hunting, and malware analysis.*
