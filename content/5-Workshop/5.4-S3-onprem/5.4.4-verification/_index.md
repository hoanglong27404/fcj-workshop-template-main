---
title : "Verification"
date: 2025-10-13
weight : 4
chapter : false
pre : " <b> 5.4.4. </b> "
---

Let's ensure the user exists in both the Authentication service and the Database.

## A. Check Cognito (Authentication)
1. Go to Amazon Cognito Console
2. Select User Pool **FindNestUsers**
3. Go to **Users** tab
4. You should see your superadmin with status **Confirmed**.

Click on the user and verify they are in the **Admins** group.

The user should have:
- **Status**: CONFIRMED (not FORCE_CHANGE_PASSWORD)
- **Group membership**: Admins

## B. Check DynamoDB (Data)
1. Go to DynamoDB Console
2. Select the table **UserProfiles**
3. Click **Explore table items**
4. Search for the item where userId matches the ID from the script output.

You should see the profile data with `userType: "admin"`.

## Verification Checklist
Confirm the following before proceeding:

- User exists in Cognito User Pool with status CONFIRMED
- User is a member of the Admins group
- User profile exists in DynamoDB UserProfiles table
- Profile has userType set to "admin"
- All user attributes (email, fullName) are correctly populated

## Next Steps
You are now ready to log in and test the system!

Your Super Admin account is ready to use. You can now authenticate with the API using these credentials.

Keep your admin credentials secure. Consider using AWS Secrets Manager for production environments.