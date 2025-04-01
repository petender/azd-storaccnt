[comment]: <> (please keep all comment items at the top of the markdown file)
[comment]: <> (please do not change the ***, as well as <div> placeholders for Note and Tip layout)
[comment]: <> (please keep the ### 1. and 2. titles as is for consistency across all demoguides)
[comment]: <> (section 1 provides a bullet list of resources + clarifying screenshots of the key resources details)
[comment]: <> (section 2 provides summarized step-by-step instructions on what to demo)


[comment]: <> (this is the section for the Note: item; please do not make any changes here)
***
### Azure Storage Account Blobs and File Shares - demo scenario

<div style="background: lightgreen; 
            font-size: 14px; 
            color: black;
            padding: 5px; 
            border: 1px solid lightgray; 
            margin: 5px;">

**Note:** Below demo steps should be used **as a guideline** for doing your own demos. Please consider contributing to add additional demo steps.
</div>

[comment]: <> (this is the section for the Tip: item; consider adding a Tip, or remove the section between <div> and </div> if there is no tip)

<div style="background: lightblue; 
            font-size: 14px; 
            color: black;
            padding: 5px; 
            border: 1px solid lightgray; 
            margin: 5px;">

</div>

***
### 1. What Resources are getting deployed
This scenario deploys **an Azure Storage Account**, having blobs and file shares as main data storage scenarios, displaying Seattle scenery images.   

* MTTDemoDeployRGc%youralias%FDCDN - Azure Resource Group.
* %youralias%fdcdnprofile - Azure FrontDoor with CDN Cache configuration
* %youralias%fdcdnsite - Simple index.html page in Azure App Service
* %youralias%fdserverfarm - Azure App Service Plan
* %youralias%fdstorageaccount - Azure Storage Account, used by Azure Front Door CDN

<img src="https://raw.githubusercontent.com/petender/azd-fdcdn/main/Demoguides/FDCDN/FDCDN_ResourceGroup_Overview.png" alt="FDCDN Resource Group" style="width:70%;">
<br></br>

### 2. What can I demo from this scenario after deployment

1. In this scenario, you are streaming images on a webpage, loaded from 3 different storage back-ends. The first scenario involves pulling them in from the App Service local storage folder. 
1. Navigate to the **App Service**, and open the **web app URL** in the browser.
1. Click the **Download from App Service** button.  
1. This shows 6 images, and the load time in millisecs.

<img src="https://raw.githubusercontent.com/petender/azd-fdcdn/main/Demoguides/FDCDN/FDCDN_webappimages.png" alt="FDCDN Web App Images" style="width:70%;">
<br></br>

1. The 2nd scenario streams images from Azure Storage Account. Open the **%youralias%fdstorageaccount** Azure Storage Account.
1. Navigate to Storage Browser / Blob Containers / **Images** Container and show the 6 image files present.
1. Return to the web page itself, refresh the page in the browser, and click the 2nd button **Download from Azure Blob Storage**
1. Wait for the images to load, and note the loading time. This should be **faster** than the previous scenario.
1. Navigate back to the Azure Portal, and open the **FrontDoor Resource** blade.
1. From the **Overview** blade, explain the **Properties** such as Endpoint hostname, reflecting the name of the FrontDoor Service, the Origin Groups, pointing at the actual service(s) getting published through FrontDoor, and Routes, pointing at how FrontDoor is handling routing traffic.

<img src="https://raw.githubusercontent.com/petender/azd-fdcdn/main/Demoguides/FDCDN/FDCDN_frontdoor.png" alt="FDCDN Frontdoor" style="width:70%;">
<br></br>

1.  Select **Origin Groups / default-origin-group** to open its settings. In the Origin Groups blade, select **default-origin-group**.  
1. Explain this is where you configure the backend service getting published by FrontDoor. In our example, the Web App.
1. Click **close** and return to the FrontDoor main blade.
1. Select **Optimizations** from the Settings section. Highlight **Caching** is **Enabled**. 
1. Return to the web page itself, refresh the page in the browser, and click the 3rd button **Download from Azure CDN**
1. Wait for the images to load, which should be the **fastest** of all 3 scenarios.
1. Open a new browser tab, navigate to the web page again, and simulate all 3 download actions. This time, the **Azure CDN** should have an even shorter loading time as before, **confirming it's presented from cache**.

<div style="background: lightblue; 
            font-size: 14px; 
            color: black;
            padding: 5px; 
            border: 1px solid lightgray; 
            margin: 5px;">

**Tip:** As Azure CDN replicates content across different POPs (Points of Presence), involve your learners into the demo scenario, and ask them to share the loading times of the different scenarios. Especially when you have learners from other regions or geographies, the results are interesting to compare.
</div>


[comment]: <> (this is the closing section of the demo steps. Please do not change anything here to keep the layout consistant with the other demoguides.)
<br></br>
***
<div style="background: lightgray; 
            font-size: 14px; 
            color: black;
            padding: 5px; 
            border: 1px solid lightgray; 
            margin: 5px;">

**Note:** This is the end of the current demo guide instructions.
</div>




