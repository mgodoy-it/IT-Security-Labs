## Adding Data to Splunk

There are three ways to add data to Splunk:

- **Upload** – You can upload a file or archive of files into Splunk Enterprise for indexing. Note that Splunk consumes the uploaded file(s) only once; it does not monitor them continuously.  
- **Monitor** – You can use this option to monitor files, directories, network streams, scripts, and other types of machine data that Splunk can index. This is the option you would most likely use in a production environment.  
- **Forward** – You can use this option to receive data from forwarders.

The easiest way to add data for a lab is to use the **Upload** option.  

### Step-by-Step: Upload a File to Splunk

Step 1: Add Data to Splunk:

![SIEM](/images/SIEM1.png)

Step 2: Click on the Upload icon:

![SIEM](/images/SIEM2.png)

Step 3: Click the **Select File** button to choose your file source:

![SIEM](/images/SIEM3.png)

Step 4: Browse to the file you would like to include:

![SIEM](/images/SIEM4.png)

Step 5: Click **Next** after the file upload completes:

![SIEM](/images/SIEM5.png)

Step 6: On the **Set Source Type** page, review how Splunk will index your data. The default source type is correct for this lab, so click **Next**:

![SIEM](/images/SIEM6.png)

Step 7: Configure Input Settings - Choose the host name (or IP) and the index for the events, then click **Review**:

![SIEM](/images/SIEM7.png)

Step 8: Review and Submit - Check your settings, then click **Submit** to complete the process:

![SIEM](/images/SIEM8.png)

Step 9: Verify Data - Click **Start Searching** to confirm that the data was added successfully:

![SIEM](/images/SIEM9.png)


## Example: Investigating Web-Based Attacks

### SQL Injection
- **Objective:** Detect potential SQL injection attempts from web logs.  
- **Hint:** Look for unusual characters or SQL keywords in URI parameters, such as `'` or `1=1`.  
- **Example Search (Splunk SPL):** index=web_logs uri_param="' OR 1=1" OR uri_param="UNIONSELECT*"


### Cross-Site Scripting (XSS)
- **Objective:** Identify signs of XSS attacks from web logs.  
- **Hint:** Search for requests containing suspicious JavaScript keywords like `script`, `<script>`, or `onload`.  
- **Example Search (Splunk SPL):** index=web_logs request="<script>" OR request="onload"

### Directory Traversal
- **Objective:** Detect attempts to access files outside the web root.  
- **Hint:** Look for URI patterns containing `../` or `%2e%2e/`.  
- **Example SPL:** index=web_logs uri="../" OR uri="%2e%2e/"

### Brute Force
- **Objective:** Monitor repeated failed login attempts from the same IP.  
- **Hint:** Look for multiple failed authentications in a short time.  
- **Example SPL:** index=auth_logs action=failure | stats count by src_ip, user | where count > 5

### Session Hijacking
- **Objective:** Detect multiple logins from different IPs for the same account.  
- **Hint:** Look for same user, different IP, short timeframe.  
- **Example SPL:** index=auth_logs action=success | stats dc(src_ip) as ip_count by user | where ip_count > 1

### Remote Code Execution (RCE)
- **Objective:** Identify suspicious requests attempting to execute code.  
- **Hint:** Look for unusual file extensions or commands.  
- **Example SPL:** index=web_logs uri=".php" OR uri=".exe" OR uri=".sh"

### XML External Entity (XXE)
- **Objective:** Detect requests with XML payloads referencing external entities.  
- **Hint:** Look for unusual XML processing instructions.  
- **Example SPL:** index=web_logs request="<!ENTITY" OR request="SYSTEM"

### Insecure Deserialization
- **Objective:** Detect suspicious serialized data in requests.  
- **Hint:** Look for references to known vulnerable serialization libraries.  
- **Example SPL:** index=web_logs request="serialize" OR request="pickle"

### Server-Side Request Forgery (SSRF)
- **Objective:** Monitor requests targeting internal or sensitive resources.  
- **Hint:** Look for URLs using `file://`, `gopher://`, or internal IPs.  
- **Example SPL:** index=web_logs uri="file://" OR uri="gopher://" OR uri="127.0.0.1"





