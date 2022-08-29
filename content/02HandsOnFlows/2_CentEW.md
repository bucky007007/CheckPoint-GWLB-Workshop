---
title: "Centralized E/W across Spokes"
chapter: true
weight: 2
---

# Centralized E/W across Spokes

### Flow Description & Diagram

| #	  | Hop description                                               |
|-----|---------------------------------------------------------------|
| 1   | 	DB host to SS host, 0/ --> TGW                               |
| 2   | 	TGW Attachment RT 0/ --> Sec VPC                             |
| 3   | 	Sec VPC TGW Attach RT 0/ --> GWLBe                           |
| 4   | 	GWLBe magic: GWLB (GENEVE) --> CGNS and return back to GWLBe |
| 5   | 	GWLBe RT Spoke --> TGW                                       |
| 6   | 	TGW Propagated RT --> SS Spoke/Host                          |

![ew](https://chkp-gwlb-ws01.s3.us-west-2.amazonaws.com/images/ew.png)

### Testing Procedure 

1. SSH to any of the EC2 hosts in Database or Shared Services VPC 
   1. Ping one of the other EC2 hosts with its private IP 
2. Search the Check Point logs for the internal IPs of the EC2 Host you’re sending the ping from and to

![ewlog](https://chkp-gwlb-ws01.s3.us-west-2.amazonaws.com/images/ew-log.png)


