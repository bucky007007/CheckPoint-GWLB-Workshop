---
title: "Workshop Logistics"
chapter: true
weight: 2
---

# Workshop Logistics

### Summary Steps

**NOTE: The below steps assume you are performing this workshop as part of an AWS Immersion Day...if you wish to run this in your _own_ environment you can simply run the following CloudFormation Template manually: [CGNS GWLB CFT](https://chkp-gwlb-workshop.s3.us-west-2.amazonaws.com/CGNS-GWLB-WS.yaml)**
1. Browse to the AWS Event Engine link that was provided, Accept Terms and Login
2. Select the **Email One-Time Password (OTP) option**...it is recommended to send the OTP to a personal email address to avoid potential expiration of the OTP due to corporate security controls.
3. After entering your OTP you should see a screen like this:
4. Select the **SSH Key** option above
   * **Download Key** to a location on your computer
   * Copy the **Key Fingerprint** to a text file
   * Copy the **Key Material** to a second text file
   * Click **OK** when done
5. If you are using PuTTY you can use PuTTYgen to create the PPK file needed from the PEM file downloaded in step **A** above 
6. Click on **AWS Console**
7. Select **Copy Login Link** and save it to a text file and followed by selecting **Open AWS Console**(will open in a new tab)
8. After launching the AWS console double-check that you are in **Oregon(us-west-2)**  >>>  **_NOTE: Only required with Immersion Day_**
9. Navigate to the **CloudFormation** area in the AWS Console
10. In the **Stacks** view click **View nested** to hide all nested Stacks and then select the remaining Stack to view its details and output.
11. Navigate to **Outputs** and record the keys and values (highlighting, copying and pasting into excel may be the best/cleanest method)
12. Using the URL associated with the **01SmartConsoleURL** key in the CFT output gives you the Public IP for the Check Point Security Management Server
13. Login to the Check Point SmartConsole application via one of two methods:
    * URL provided in the previous step to access the Web SmartConsole: https://publicIP/smartconsole (make sure to open it in a new tab)
    * R81.10 SmartConsole Windows application > Use Public IP from above...if you don't already have it you can download it [HERE](https://supportcenter.checkpoint.com/supportcenter/portal/role/supportcenterUser/page/default.psml/media-type/html?action=portlets.DCFileAction&eventSubmit_doGetdcdetails=&fileid=121500)
14. Username is: **admin** Password is: **qwe123!**
15. Verify that the CloudGuard Network Security Gateways have been discovered by the Security Management Server (your IP addresses will likely be different)


### GWLB Reference Architecture Diagram

![ws-arch](https://chkp-gwlb-ws01.s3.us-west-2.amazonaws.com/CHKP-CGNS-GWLB-WorkshopArchitecture-Workshop+Final.drawio.png)

### Notes: 
- There are several different ways to organize your AWS Architecture to take advantage of CloudGuard Traffic inspection with AWS GWLB.  It is important to remember that as long as the traffic has a symmetrical routing path for forward and reverse flow, the architecture will work.
- This diagram may look complicated at first glance because it covers **ALL Traffic Flow Options**.  For each scenario, we'll highlight the components involved in that flow.  Depending on application requirements you may only require a subset of the flows and accordingly a subnet of this Reference Architecture 
### Learning Objectives
- Learn the difference between Centralized and Decentralized GWLB & GWLBe Architectures
- Understand how each flow works
- Understand the differences and advantages/disadvantages of centralized ingress architecture options

{{% notice warning %}}
<p style='text-align: left;'>
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various Check Point and AWS services can be architected to build a solution while demonstrating best practices along the way. These examples are not intended for use in production environments.
</p>
{{% /notice %}}