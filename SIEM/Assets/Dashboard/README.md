# 🔐 SIEM Project – Brute Force Login Detection with Splunk  

## 📌 Project Overview  
This project is part of my cybersecurity portfolio where I built a **Splunk SIEM lab** to detect suspicious login activity from AWS CloudTrail logs.  
The goal was to simulate how a SOC analyst identifies **brute force login attempts** using detection rules, dashboards, and alerts.  

---

## 📂 Dataset  
- **Source:** Splunk BOTS v3 dataset  
- **Log type:** AWS CloudTrail (ConsoleLogin events)  

---

## 🛠️ Detection Logic  
I created a Splunk SPL query to detect repeated login attempts from the same IP and user:

```spl
index=botsv3 sourcetype="aws:cloudtrail" eventName=ConsoleLogin
| stats count by userIdentity.userName, sourceIPAddress, responseElements.ConsoleLogin
| where count > 2
| sort - count

```
📊 Dashboard Visualizations

Custom Brute Force Dashboard created with Splunk panels:
Failed logins by IP → Shows IPs attempting multiple logins.
Login attempts over time → Trend view of repeated login activity.
Geo-location map → Attempts plotted by country/IP (SOC-style visualization).

Screenshots:
 > 01_failed_logins_by_ip.png
 > 02_login_attempts_map.png
 > 03_full_dashboard_part1.png
 > 03_full_dashboard_part2.png

🚨 Alert Configuration

I also set up a Splunk alert to notify when multiple ConsoleLogin attempts were detected:
Alert name: AWS Console Brute Force Detection
Condition: Trigger when results > 0
Schedule: Run every 24 hours

Screenshots:
> screenshot_result.png
> screenshot_alert.png

✅ Results:

Detected repeated AWS ConsoleLogin attempts for user bstoll from IP 107.77.212.175.
Built and saved a Splunk alert to monitor repeated login activity.
Visualized brute force attempts in Splunk dashboards.

🎯 Skills Demonstrated:

SIEM setup & log ingestion
SPL query writing for brute-force detection
Dashboard creation & visualization
Alert configuration for SOC monitoring
Professional technical documentation

🔗 About This Project:
This project demonstrates my ability to use SIEM tools (Splunk) for real-world security monitoring tasks, similar to what SOC Analysts and Threat Hunters do daily.



