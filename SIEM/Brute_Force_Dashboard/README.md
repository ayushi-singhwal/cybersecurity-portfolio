# Brute-Force Dashboard – SIEM Project

## Project Overview
This project showcases a Splunk SIEM dashboard designed to detect and visualize brute-force login attempts. Using the BOTS v3 dataset, the dashboard provides actionable insights for SOC analysts to identify suspicious login activity and respond effectively.  

The dashboard demonstrates real-world SOC practices: tracking failed logins, visualizing trends over time, and mapping login attempts geographically. 

## Dashboard Panels

### 1. Repeated Login Attempts by IP
- **Type:** Bar Chart / Table  
- **Description:** Displays usernames and IP addresses with multiple login attempts.  
- **Purpose:** Quickly identify potential brute-force attempts from specific IPs.  
- **Screenshot:** `01_failed_logins_by_ip.png`  

### 2. Login Attempts Over Time
- **Type:** Line Chart / Timechart  
- **Description:** Shows login activity (Success vs Failure) over time in 30-minute intervals.  
- **Purpose:** Detect unusual spikes or patterns in login attempts.  
- **Screenshot:** Included in the full dashboard view.

### 3. Login Attempts by Geo-Location
- **Type:** Geo-Map (Country-based)  
- **Description:** Maps login attempts by country using the source IP.  
- **Purpose:** Identify unusual geographic access patterns.  
- **Screenshot:** `02_login_attempts_map.png`  

### 4. Full Dashboard View
- **Description:** Combines all panels in a SOC-style layout.  
- **Screenshot:** `03_full_dashboard.png`  

---

## Tools & Technologies
- **Splunk SIEM** – Search, Reporting, Dashboards, Geo-Map Visualization  
- **Python** – Optional preprocessing or alerting (if used)  
- **Git & GitHub** – Version control and portfolio management  

---

## Key Learnings / Outcomes
- Created a functional SOC-style dashboard to monitor brute-force login attempts.  
- Translated raw log data into visual insights for quick detection and response.  
- Demonstrated end-to-end SIEM workflow: log ingestion → detection → visualization → reporting.  
- Portfolio-ready example that shows practical cybersecurity skills for recruiters.

---

## Screenshots / Assets
- `01_failed_logins_by_ip.png` – Bar chart panel  
- `02_login_attempts_map.png` – Geo-Map panel  
- `03_full_dashboard.png` – Full dashboard view  

> Note: Some Geo-Map visualizations may show limited data due to dataset IP resolution. The main objective is demonstrating dashboard creation and visualization capability.
