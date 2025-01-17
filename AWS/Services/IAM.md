- IAM stands for Identity and Access Management;
- It's a **Global** service;
- **Users** are people within your organization, and can be grouped;
- Groups only contain users, not other groups;
- Users don't have to belong to a group;
- A user can belong to multiple groups;

>[!INFO]
> The Root account created by default when we sign up for AWS Console shouldn't be used or shared. 

## Permissions
- **Users** and **Groups** can be assigned JSON documents called **policies**. Example:

```json
{
	"Version": "2012-10-17", 
	"Statement": [
		{
			"Effect": "Allow",
			"Action": "ec2:Describe",
			"Resource": "*"
		},
		{
			"Effect": "Allow",
			"Action": "elasticloadbalancing:Describe",
			"Resource": "*"
		},
		{
			"Effect": "Allow",
			"Action": [
				"cloudwatch:ListMetrics",
				"cloudwatch:GetMetricStatistics",
				"cloudwatch:Describe*"
			],
			Resource: "*"
		}
	]
}
```

- These policies define the **permissions** of the users;
- In AWS you apply the **least privilege principle**: don't give more permissions than a user needs;