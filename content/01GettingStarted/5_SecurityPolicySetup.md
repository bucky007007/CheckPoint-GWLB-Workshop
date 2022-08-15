---
title: "Initial Setup"
chapter: true
weight: 5
---

# Initial Setup (Credentials and Check Point Security Policy Setup)

### Preparing the environment

**NOTE: The below steps assume you are performing this workshop as part of an AWS Immersion Day...if you wish to run this in your _own_ environment you can simply run the following CloudFormation Template manually: [CGNS GWLB CFT](https://chkp-gwlb-workshop.s3.us-west-2.amazonaws.com/CGNS-GWLB-WS.yaml)**
1. Browse to the AWS Event Engine link that was provided, Accept Terms and Login
   ![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-0001.png)
2. Select the **Email One-Time Password (OTP) option**...it is recommended to send the OTP to a personal email address to avoid potential expiration of the OTP due to corporate security controls.
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-0002.png)
3. After entering your OTP you should see a screen like this:
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-0003.png)
4. Select the **SSH Key** option above
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-0004.png)
   * **Download Key** to a location on your computer
   * Copy the **Key Fingerprint** to a text file
   * Copy the **Key Material** to a second text file
   * Click **OK** when done
5. If you are using PuTTY you can use PuTTYgen to create the PPK file needed from the PEM file downloaded in step **A** above 
6. Click on **AWS Console**
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-0005.png)
7. Select **Copy Login Link** and save it to a text file and followed by selecting **Open AWS Console**(will open in a new tab)
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-0006.png)
8. After launching the AWS console double-check that you are in **Oregon(us-west-2)**  >>>  **_NOTE: Only required with Immersion Day_**
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-0007.png)
9. Navigate to the **CloudFormation** area in the AWS Console
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-0008.png)
10. In the **Stacks** view click **View nested** to hide all nested Stacks and then select the remaining Stack to view its details and output.
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-0009.png)
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-0010.png)
11. Navigate to **Outputs** and record the keys and values (highlighting, copying and pasting into excel may be the best/cleanest method)
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-0011.png)
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-0012.png)
12. Using the URL associated with the **01SmartConsoleURL** key in the CFT output gives you the Public IP for the Check Point Security Management Server
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-0013.png)
13. Login to the Check Point SmartConsole application via one of two methods:
    * URL provided in the previous step to access the Web SmartConsole: https://publicIP/smartconsole (make sure to open it in a new tab)
    ![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-001.png)
    * R81.10 SmartConsole Windows application > Use Public IP from above...if you don't already have it you can download it [HERE](https://supportcenter.checkpoint.com/supportcenter/portal/role/supportcenterUser/page/default.psml/media-type/html?action=portlets.DCFileAction&eventSubmit_doGetdcdetails=&fileid=121500)
    ![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-002.png)
14. Username is: **admin** Password is: **qwe123!**
15. Verify that the CloudGuard Network Security Gateways have been discovered by the Security Management Server (your IP addresses will likely be different)
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-003.png)

### Check Point Security Policy Setup
Now, we need to login to the Check Point Web SmartConsole to setup an initial security policy for the workshop, which will allow us to test all traffic flows.

### <span style="color:red"> **SECURITY DISCLAIMER – this is a sample policy for this WORKSHOP ONLY and it NOT SUITABLE for a production environment!!!!** </span>

1. Navigate to the Security Policies tab in SmartConsole
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-004.png)
2. Create a new rule above the default **Cleanup rule**
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-005.png)
3. The result should look like this...in this example we gave the rule the name **Allow Outbound**
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-006.png)
4. Modify the new rule to allow the network **10.100.0.0/16** outbound access to **ANY**
- Give your rule a name if preferred(not required)
- Add a new network object that represents **10.100.0.0/16** to the **Source** field
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-007.png)
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-008.png)
- Result should look like this:
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-009.png)
- Modify the rule so that Destination is **ANY**
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-010.png)
- Set the Service & Applications field to be **ANY**
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-011.png)
- Set Action to **Accept**
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-012.png)
- Set Track to **Log**
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-013.png)
- The end result of the new rule should look like this:
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-014.png)
- Using the same procedure as above, create another rule that allows Inbound traffic to the following networks:
- 10.100.0.0/16
- 10.0.15.0/24
- 10.0.25.0/24
- 10.0.35.0/24

5. When complete also set the **Cleanup rule** to Log.  The end result should look like this:
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-015.png)
6. **Install Policy** to push the new security policy to the Security Gateways
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-016.png)
![](https://objectstorage.us-phoenix-1.oraclecloud.com/n/cloudguardiaas/b/aws-gwlb-workshopio-images/o/2022-04-16-AWS%20GWLB-017.png)

{{% notice warning %}}
<p style='text-align: left;'>
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various Check Point and AWS services can be architected to build a solution while demonstrating best practices along the way. These examples are not intended for use in production environments.
</p>
{{% /notice %}}