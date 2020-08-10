# IAM

## IAM: Users & Groups

  • IAM = Identity and Access Management, Global service.
  • Root account created by default, shouldn’t be used or shared.
  • Users are people within your organization, and can be grouped.
  • Groups only contain users, not other groups.
  • Users don’t have to belong to a group, and user can belong to multiple groups.
  
## IAM: Permissions

• Users or Groups can be assigned JSON documents called policies.
• These policies define the permissions of the users.
**• In AWS you apply the least privilege principle: don’t give more permissions than a user needs**

**JSON EXAMPLE**

{
"Version": "2012-10-17",
"Statement": [
{
"Effect": "Allow",
"Action": "ec2:Describe*",
"Resource": "*"
},
{
"Effect": "Allow",
"Action": "elasticloadbalancing:Describe*",
"Resource": "*"
},
{
"Effect": "Allow",
"Action": [
"cloudwatch:ListMetrics",
"cloudwatch:GetMetricStatistics",
"cloudwatch:Describe*"
],
"Resource": "*"
}
]
}

## IAM – Password Policy

  • Strong passwords = higher security for your account.
  • In AWS, you can setup a password policy:
      • Set a minimum password length
      • Require specific character types:
      • including uppercase letters
      • lowercase letters
      • numbers
      • non-alphanumeric characters
  • Allow all IAM users to change their own passwords.
  • Require users to change their password after some time (password expiration).
  • Prevent password re-use.
  
## Multi Factor Authentication - MFA

  • Users have access to your account and can possibly change configurations or delete resources in your AWS account
  • You want to protect your Root Accounts and IAM users
  • MFA = password you know + security device you own
  • Main benefit of MFA:
      if a password is stolen or hacked, the account is not compromised
      
  **MFA devices options in AWS**
  
   *Virtual MFA device* 
      
      1. Google Authenticator
      2. Authy
      
   *Universal 2nd Factor (U2F) Security Key*
   
      YubiKey by Yubico (3rd party)
      
   *Hardware Key Fob MFA Device*
   
      Provided by Gemalto (3rd party)
      
   *Hardware Key Fob MFA Device for AWS GovCloud (US)*
   
      Provided by SurePassID (3rd party)
      
 **How can users access AWS ?**
 
    • To access AWS, you have three options:
        • AWS Management Console (protected by password + MFA).
        • AWS Command Line Interface (CLI): protected by access keys.
        • AWS Software Developer Kit (SDK) - for code: protected by access keys.
    • Access Keys are generated through the AWS Console.
    • Users manage their own access keys.
    • Access Keys are secret, just like a password. Don’t share them.
    • Access Key ID ~= username.
    • Secret Access Key ~= password.
 
