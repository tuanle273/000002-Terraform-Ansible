---
title: "Prepare AWS Env"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.1.1 </b> "
---

1. Go to [IAM management console](https://console.aws.amazon.com/iam)
   or

- Find in search bar **IAM**.
- Click **IAM**.
  ![IAM](/images/2.prerequisite/createuseriam1.png)

2. Click **Users** from left bar.

- Create new user IAM with name
- Attach permission: `AmazonEC2FullAccess, AmazonVPCFullAccess, IAMFullAccess, AmazonS3FullAccess,CloudWatchFullAccess.`
  ![IAM](/images/2.prerequisite/createuseriam2.png)
  ![IAM](/images/2.prerequisite/createuseriam3.png)

3. Click to user was created.

- Click **Sercurity credential**.
- Click **Create new access key**.
- Save it and add to AWS CLI

![IAM](/images/2.prerequisite/createuseriam4.png)

4. Configure AWS CLI

- Download the AWS CLI Installer

Visit the [AWS CLI](https://aws.amazon.com/cli/) official download page.

Under "Windows", click on the "MSI installer" link to download the installer file.

- Run the Installer

Locate the downloaded .msi file (usually in your "Downloads" folder).
Double-click the file to run the installer.

- Follow the Installation Instructions

The installation wizard will guide you through the setup process. Click "Next" to proceed with the default settings.
Accept the license agreement and continue by clicking "Next".
Choose the installation folder or leave it as the default. Click "Next".
Click "Install" to begin the installation.
After the installation is complete, click "Finish" to close the installer.

- Verify the Installation

Open the Command Prompt or PowerShell.
Type aws --version and press Enter.
You should see the AWS CLI version information, indicating that the installation was successful.

- Configure the AWS CLI

To configure the AWS CLI, run the following command in your Command Prompt or PowerShell:

`aws configure`

- Input AWS Access Key ID & AWS Secret Access Key

![IAM](/images/2.prerequisite/createuseriam5.png)
