# Azure Update Center

This **Azure workbook** is intended to give an ***overview of your Azure IaaS services updates and patch configuration*** which leverage ***Automatic VM Guest Patching*** and ***Azure Update Management*** features.

I built it to accelerate my understanding of my customers heterogeneous patch configuration posture.

![Azure Update Center workbook](media/AzureUpdateCenter.png)

The workbook has two parts:

* **Azure Virtual Machines** to see:
  * VM patch configuration
  * Which monitoring agent(s) is/are deployed on the VM
  * Last VM update report (if onboarded in Log Analytics Updates solution) for the selected VM
  * VM platform updates (if VM deployed with AutomaticByPlatform option enabled) for the selected VM
* **Azure Update Management** to see:
  * All your workspace with an Updates solutions
  * All VMs onboarded in these workspaces
  * All your automation accounts to browse MANUALLY (but quickly) to discover Hybrid Runbook Workers nodes (or your VMs onboarded in Azure Update Management)

## How to deploy

To deploy this workbook in your Azure tenant, click on the button below:

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fjdmsft%2FAzureUpdateCenter%2Fmain%2Ftemplate%2Fdeploy.json" target="_blank"><img src="https://raw.githubusercontent.com/jdmsft/AzureUpdateCenter/main/media/DeployToAzWorkbookByJDMSFT_v2.0.png" height="60"/></a>

## Known issues & limitations

* Because we can't loop in a *Custom Endpoint* query, I can't query dynamically worker nodes. As a workaround I offer the possibility to browse your automation accounts from the **Azure Update Management** part of the workbook to show associated Hybrid Runbook Workers (System node included).