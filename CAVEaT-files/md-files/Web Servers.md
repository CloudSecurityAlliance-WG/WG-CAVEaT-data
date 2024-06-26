 
(© 2022 The MITRE Corporation All Rights Reserved. Draft Content 
Submission for Consideration by the CAVEAT Working Group) 
 Exfiltrating Using Web Servers (version 1.0) 
 
Cloud Service Label: IaaS, PaaS 
 
Description 
Many customer cloud deployments incorporate a public web server to serve external 
entities with content. Adversaries that have gained access to a customer’s cloud assets 
and have already located and collected data for exfiltration can use such web servers 
as a stealthy way of exfiltrating data. An adversary knows that cloud firewalls and 
monitoring products are configured to expect and allow data to be served by public web 
servers. There are public exfiltration tools that make public web servers in a clo ud 
especially convenient for an adversary to utilize for exfiltration. 
 
Examples 
Name Description 
PyExfil Publicly available tool set to leverage web servers 
and other adversary controlled assets to stealthily 
exfiltrate data from compromised accounts. 
 
Mitigations 
Mitigation Description 
Audit Frequently check permissions on cloud storage to 
ensure proper permissions are set to deny open or 
unprivileged access to resources. Consider using 
automated resource checkers such as CloudSploit or 
Divvycloud. Frequently check accesses to web servers 
for content that has not been downloaded before. 
 AWS To perform an audit via AWS it is suggested to review 
information such as account details (credentials, users, 
groups, roles, etc), mobile applications, EC2 
configurations, policies, and account activity. How to 
audit these different factors can be found i n detail at: 
https://docs.aws.amazon.com/general/latest/gr/aws -
security -audit -guide.html. 
 Azure To perform an audit via Azure an administrator can 
review the audit logs that are recorded under Azure’s 
monitoring for active directory. The audit logs allow for 
filtering, as well as looking at users, groups, and 
enterprise specific information. Full det ails on how to 
access this information can be found at: 
https://docs.microsoft.com/en -us/azure/active -
directory/reports -monitoring/concept -audit -logs. 
(© 2022 The MITRE Corporation All Rights Reserved. Draft Content 
Submission for Consideration by the CAVEAT Working Group) 
 GCP To perform an audit via GCP the logs can be reviewed. 
GCP breaks this down into three categories; admin 
activity, data access, and system events. The audit logs 
can be viewed a few different ways - the console, API, 
or gcloud. Full details on how to view th ese logs, how to 
export, and for how to configure the retention period 
can be found here: 
https://cloud.google.com/logging/docs/audit. 
Task Definition Edit Privileges If it is necessary to have a task definition run a role that 
requires an elevated level of permission, ensure that 
that task definition cannot be altered by everyone. 
 
Detection 
Detection Description 
Create Log Metric Filters and Alarms for AWS To create a metric filter and alarm: 
1. Create a metric filter that checks for IAM policy 
changes and the  
2. Create an SNS topic 
3. Create an SNS subscription to the above topic 
4. Create an alarm associated with the filter and SNS 
topic created in steps 1 and 2 respectively 
Monitor Activity in AWS Account Various services in AWS offer logging features that allow for 
detection capabilities. These include CloudFront, CloudTrail, 
CloudWatch, Config, and S3. 
Monitor for Suspicious Activity in Azure Azure AD can generate anomaly reports than can be run on 
a daily basis. Azure AD Identity Protection show current risks 
in its dashboard and provides daily email summary 
notifications. Policies can also be configured to alert to 
specific issues. 
Create Log Metric Filters and Alarms for CloudTrail To create a metric filter and alarm: 
1. Create a filter that checks for CloudTrail changes 
and the specific  
2. Create an SNS topic that the alarm will notify 
3. Create an SNS subscription to the above topic 
4. Create an alarm associated with the filter from 
step 1 and SNS topic in step 2 
Create Activity Log Alerts in Azure To create log activity alerts for deletion in the Azure 
Console: 
1. Navigate to Monitor’ / ‘Alerts 
2. Select Manage alert rules 
3. Click on the Alert Name where Condition contains 
operationName equals 
Microsoft.Network/networkSecurityGroups/securit
yRules/delete 
4. Hover a mouse over Condition to ensure it is set to 
Whenever the Administrative Activity Log “Delete 
Security Rule 
(networkSecurityGroups/securityRules)” has “any” 
level with “any” status and event is initiated by 
“any” 
Create, View, and Manage Activity Alerts in Azure Monitor To create a log alert in the Azure portal: 
(© 2022 The MITRE Corporation All Rights Reserved. Draft Content 
Submission for Consideration by the CAVEAT Working Group) 
 1. Select Monitor -> Alerts 
2. Select New alert rule of the Alerts window 
3. Provide information in Define alert condition 
4. Provide details in Define alert details 
5. Specify action group for new alert rule under 
Action group , or create a new action group with + 
New group 
6. Select Yes for the Enable rule upon creation 
option 
7. Select Create alert rule 
 
To view and manage alerts: 
1. Select Monitor -> Alerts -> Manage alert rules 
2. Select the rule you want to modify and double -
click to edit the rule options 
3. Click Save 
Azure Resource Manager Templates Azure Resource Manager templates in the format of JSON 
files that can be used to configure metric alerts in Azure 
Monitor. These templates can be used for simple static and 
dynamic threshold metric alerts, availability tests, and 
monitoring multiple resour ces. 
Enable CloudTrail across all regions in AWS To enable CloudTrail across all regions: 
1. Sign into the AWS Management Console and open 
the CloudTrail console 
2. Click on Trails 
3. Set necessary Trails to All option in the I column 
4. Click on a trail via the link Name column 
5. Set Logging to ON 
6. Set Apply trail to all regions to Yes 
Configure log profile to capture activity logs for all regions in 
Azure To set up activity logs for all regions: 
1. Navigate to Azure console 
2. Go to Activity log 
3. Select Export 
4. Select Subscription 
5. Check Select all in Regions 
6. Select Save 
 
 
 
References 
1. https://github.com/ytisf/PyExfil/blob/master/USAGE.md#https -replace -certificate. 
Accessed March 8, 2020 
 
 
 