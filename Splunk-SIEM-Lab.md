## Adding Data to Splunk

There are three ways to add data to Splunk:

- **Upload** – You can upload a file or archive of files into Splunk Enterprise for indexing. Note that Splunk consumes the uploaded file(s) only once; it does not monitor them continuously.  
- **Monitor** – You can use this option to monitor files, directories, network streams, scripts, and other types of machine data that Splunk can index. This is the option you would most likely use in a production environment.  
- **Forward** – You can use this option to receive data from forwarders.

The easiest way to add data for a lab is to use the **Upload** option.  

### Step-by-Step: Upload a File to Splunk

1. Log in to the **Splunk Web interface**  
2. Navigate to **Settings → Add Data**  
3. Select **Upload** → Choose the log file or archive you want to index  
4. Set the **Source type** and **Index name** (e.g., `lab_index`)  
5. Click **Next → Review → Submit**  

**Screenshot placeholder:**  
