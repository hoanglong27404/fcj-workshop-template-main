---
title : "Run the Script"
date: 2025-10-13
weight : 3
chapter : false
pre : " <b> 5.4.3. </b> "
---

Now, execute the script. It is interactive, so it will ask you for details.

## Execute the script

```bash
node seed-admin.js
```

## Interactive Walkthrough
The script will prompt you for the following information:

- **Username**: Enter a username (e.g., superadmin)
- **Password**: Enter a strong password (min 8 chars, uppercase, lowercase, numbers, special chars)
- **Email**: Enter a valid email address
- **Full Name**: Enter a display name
- **Confirm**: Type yes to proceed

## Expected Output
If everything is configured correctly, you should see output similar to this:

```
* Environment variables loaded:
   Region: us-east-1
   User Pool ID: us-east-1_xxxxxx
   User Profiles Table: UserProfiles

📝 Creating admin user in Cognito...
   * User created with ID: xxxx-xxxx-xxxx
🔑 Setting permanent password...
   * Password set
👑 Adding user to Admins group...
   * Added to Admins group
📝 Creating admin profile in DynamoDB...
   * Profile created

═══════════════════════════════════════════════
* ADMIN USER CREATED SUCCESSFULLY!
═══════════════════════════════════════════════
Save the credentials! You'll need the username and password to log in to the system.
```

If you encounter errors:

- Check that your .env file has the correct values
- Verify your AWS credentials are configured (aws configure)
- Ensure you have the necessary IAM permissions
- Make sure the CDK stack was deployed successfully

## What the script does
The script performs the following operations:

- Creates a user in Cognito User Pool with the provided username and password
- Sets the password as permanent (no need to change on first login)
- Adds the user to the "Admins" group for elevated permissions
- Creates a profile record in DynamoDB with user information