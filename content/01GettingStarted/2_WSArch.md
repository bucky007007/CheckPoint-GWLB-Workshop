---
title: "Workshop Logistics"
chapter: true
weight: 2
---

# Workshop Logistics

### AWS GWLB Reference Architecture Diagram

![ws-arch](https://chkp-gwlb-ws01.s3.us-west-2.amazonaws.com/CHKP-CGNS-GWLB-WorkshopArchitecture-Workshop+Final.drawio.png)

### Notes: 
- There are several different ways to organize your AWS architecture to take advantage of CloudGuard Traffic inspection with AWS GWLB.  It is important to remember that as long as the traffic has a symmetrical routing path for forward and reverse flow, the architecture will work.
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