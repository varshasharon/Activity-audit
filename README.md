# AUDITING CLOUD ACTIVITY USING AWS CLOUDTRAIL
```
Name : E Varsha Sharon
Reg no: 212222100058
```
## Aim:
To enable and analyze AWS CloudTrail logs to audit user and resource activities in a cloud
environment.

## Pre-requisites:
```
1. Background:
AWS CloudTrail records all API calls made within an AWS account. This includes actions
taken through the AWS Console, CLI, and SDKs. It is a foundational service for compliance,
security monitoring, and operational troubleshooting.
2. Tools Required:
● AWS Console access
● CloudTrail service enabled
● S3 bucket (for storing logs)
● Optional: AWS Athena for querying logs
● IAM permissions to view audit logs
3. Procedure:
Step 1: Enable CloudTrail
● Go to CloudTrail from AWS Console
● Click Trails > Create trail
o Name: CloudAuditTrail
o Apply trail to all regions: ✅
o Log events:
▪ Management events: Read & Write
▪ Data events: S3, Lambda (optional)
o Create or select an S3 bucket for log storage
o Enable CloudWatch Logs integration (optional)
Step 2: Review Event History
● Go to Event history
● Filter events by:
o Username (IAM role or user)
o Event name (e.g., CreateBucket, TerminateInstances)
o Date/Time
o Resource type (e.g., S3, EC2)
Step 3: Download or Export Logs
● Use the Download CSV option to export logs
● Analyze logs in Excel/Sheets for reporting
 Step 4 (Optional): Query Logs Using Athena
● Navigate to Amazon Athena
● Create a database pointing to the S3 log folder
● Create table schema using CloudTrail log structure
● Sample query:
Sql command:
SELECT userIdentity.userName, eventName, eventSource,
sourceIPAddress, eventTime
FROM cloudtrail_logs
WHERE eventTime > current_date - interval '1' day;
```

## Sample Output:
Observations:

![image](https://github.com/user-attachments/assets/2b3758c4-2606-41b1-b0d8-f92fde468031)

## Result:
All AWS user activities, including volume creation, deletion, and permission changes, were
successfully audited using CloudTrail.
