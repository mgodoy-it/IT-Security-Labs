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





