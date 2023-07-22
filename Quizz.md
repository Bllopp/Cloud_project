# Cloud & Big Data

## Quizz

### IAM quizz

1. Option 3
2. Option 1
3. Options 3 & 4
4. Option 1
5. Option 2
6. Option 3
7. Option 1

### Network quizz

1. Option 3
2. Option 3
3. Options 1, 3 & 6
4. Option 4

## IAM

### Question 1 :

The IAM policy allows to perform these actions:
* Run and terminate EC2 instances in the us-east-1 region for the account with ID 123456789012.
* Get and put objects in the example-bucket S3 bucket.

### Question 2 :

This policy allow access to VPC-related information only when the request is made in the us-west-2 region. It is specified in the Condition block. The condition uses the StringEquals operator to check if the value of the aws:RequestedRegion key is equal to us-west-2.

### Question 3 :

This AWS IAM policy allows s3:GetObject, s3:PutObject, and s3:ListBucket actions on the example-bucket and its objects. The policy allows these actions only when the objects have a prefix of either "documents/" or "images/", as specified in the Condition block of the policy statement.

### Question 4 :

This AWS IAM policy allows the iam:CreateUser and iam:DeleteUser actions for IAM users. The policy allows these actions on IAM user resources with an ARN of `arn:aws:iam::123456789012:user/${aws:username}`. The ` ${aws:username} `	 variable is replaced with the username of the IAM user for which the action is being performed. This means that the policy allows the creation and deletion of IAM users in the account with ID 123456789012.

### Question 5 :

This AWS IAM policy grants access to the IAM service. The policy allows iam:Get* and iam:List* actions on all resources, as indicated by the "Resource": "*" statement. This means that the policy allows you to perform any IAM action that begins with Get or List, such as GetUser, ListUsers, GetGroup, etc.

This policy does not allow you to create an IAM user, group, policy, or role, as it only allows actions that begin with Get or List. To create these resources, you would need to have permission for create actions, such as CreateUser, CreateGroup, CreatePolicy, or CreateRole.

iam:Get* action allows for example :
- GetAccountEmailAddress to get the email address that is associated with the account
- GetGroup to retrieve a list of IAM users in the specified IAM group
- GetUser to retrieve information about the specified IAM user, including the user's creation date, path, unique ID, and ARN

### Question 6 :

This AWS IAM policy denies the ec2:RunInstances and ec2:StartInstances actions for EC2 instances of type t2.micro and t2.small. The policy uses a Deny effect, which means that it overrides any Allow statements that might grant access to these actions.

If the policy included an additional statement with an Allow effect and an action of ec2:*, this would grant access to all EC2 actions. However, the Deny statement in the original policy would still surpasss, and the specified actions (ec2:RunInstances and ec2:StartInstances) would still be denied for instances of type t2.micro and t2.small.

If the policy included both the original statement and the additional statement, you would be able to terminate an m3.xlarge instance that existed in the account. The original statement only denies access to the ec2:RunInstances and ec2:StartInstances actions for instances of type t2.micro and t2.small, and does not affect other actions or instance types. The additional statement grants access to all EC2 actions, including ec2:TerminateInstances, which would allow you to terminate the instance.