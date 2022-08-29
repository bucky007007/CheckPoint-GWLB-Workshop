---
title: "GWLBe Options"
chapter: true
weight: 3
---

# AWS GWLBe Options

### Distributed Architecture 

The Distributed GWLB Architecture features an IGW and GWLBe in each VPC.  Accordingly, the ingress & egress Internet traffic from that VPC use the local IGW. 

![dist](https://chkp-gwlb-ws01.s3.us-west-2.amazonaws.com/dist-01.png)

### Centralized Architecture

The Centralized GWLB Architecture connects VPCs together with TGW and use a Centralized Ingress and Egress from either 
- Combined Security VPC (as we see in this workshop)
- Dedicated Internet VPC attached to TGW (not covered in this workshop)

![cent](https://chkp-gwlb-ws01.s3.us-west-2.amazonaws.com/cent-01.png)


{{% notice warning %}}
<p style='text-align: left;'>
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various Check Point and AWS services can be architected to build a solution while demonstrating best practices along the way. These examples are not intended for use in production environments.
</p>
{{% /notice %}}