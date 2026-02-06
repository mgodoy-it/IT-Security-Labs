# Splunk SIEM Lab – Basic Searches & Alerts

## Objective
Practice basic Splunk usage, including data indexing, searching, and alert creation in a lab environment.

## Lab Environment
- Splunk Enterprise / Splunk Free (Lab environment)  
- Windows Server / Linux server for log sources  
- Sample log data (Windows Event Logs, Syslog)

---

## Step 1: Add Data to Splunk
1. Log in to Splunk Web interface  
2. Navigate to **Settings → Add Data**  
3. Select **Upload** → Choose a sample log file (e.g., Windows Event Logs or Syslog)  
4. Set the **source type** and **index name** (e.g., `lab_index`)  
5. Click **Next → Review → Submit**

**Screenshot placeholder:**  
`screenshots/splunk/splunk-add-data.png`

---

## Step 2: Perform Basic Searches
1. Go to **Search & Reporting** app in Splunk  
2. Select the index used in Step 1  
3. Perform searches, for example:  
   - `index=lab_index sourcetype=WinEventLog`  
   - `index=lab_index ERROR OR WARNING`  
4. Apply **time filters** to narrow results  
5. Review search results for patterns or notable events  

**Screenshot placeholder:**  
`screenshots/splunk/splunk-search-results.png`

---

## Step 3: Create an Alert
1. From your search in Step 2, click **Save As → Alert**  
2. Set alert conditions:  
   - **Trigger alert:** When number of results > 0  
   - **Trigger actions:** Email notification (optional in lab)  
3. Save the alert and verify it appears in **Settings → Searches, Reports, and Alerts**

**Screenshot placeholder:**  
`screenshots/splunk/splunk-alert.png`

---

## Notes
- Lab performed in a safe, isolated environment  
- Sample log data used; no sensitive data included  
- Alerts are configured for lab demonstration only

## Skills Demonstrated
- Indexing and searching log data in Splunk  
- Creating and managing alerts  
- Understanding log sources and sourcetypes  
- Basic SIEM operations and monitoring

