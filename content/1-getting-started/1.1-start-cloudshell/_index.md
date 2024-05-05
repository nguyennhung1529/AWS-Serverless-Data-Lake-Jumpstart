---
title : "Start an AWS CloudShell environment"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
{{% notice tip %}}
This workshop will allow participants to create the solution from ground up instead of using a CloudFormation template to provision the base resources. We will use the Command Line Interface (CLI) to accomplish this.
{{% /notice %}}

### Start an AWS CloudShell Environment
{{% notice note %}}
AWS CloudShell is a browser-based, pre-authenticated shell that you can launch directly from the AWS Management Console. You can run AWS CLI commands against AWS services using your preferred shell (Bash, PowerShell, or Z shell). And you can do this without needing to download or install command line tools.
{{% /notice %}}

1. Login to the [AWS Management Console](https://ap-southeast-1.console.aws.amazon.com/console/home).
2. In the upper right menu section, select **Singapore (ap-southeast-1)** region.
3. Start an AWS CloudShell session by clicking the **CloudShell icon** on the bottom menu bar.
![CloudShell](/images/1-getting-started/cloudshell-open.png)
4. A welcome dialog box will pop up, check **do not show this again**, and then click **Close**.
![CloudShell](/images/1-getting-started/cloudshell-open-02.png)
5. CloudShell will start preparing a Linux environment and you should see a terminal in your browser in a few moment.
![CloudShell](/images/1-getting-started/cloudshell-open-03.png)
