---
title: Connect Amazon Web Services 
description: This article provides information about how to connect your AWS app to Defender for Cloud Apps using the API connector for visibility and control over use.
ms.date: 01/29/2023
ms.topic: how-to
---
# Connect Amazon Web Services  to Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article provides instructions for connecting your existing Amazon Web Services (AWS) account to Microsoft Defender for Cloud Apps using the connector APIs. For information about how Defender for Cloud Apps protects AWS, see [Protect AWS](protect-aws.md).

You can connect AWS **Security auditing** to Defender for Cloud Apps connections to gain visibility into and control over AWS app use.

## How to connect AWS Security auditing to Defender for Cloud Apps

Use the following steps to configure your AWS auditing and then connect it to Defender for Cloud Apps.

### Step 1: Configure Amazon Web Services auditing

1. In your [Amazon Web Services console](https://aws.amazon.com/console/), under **Security, Identity & Compliance**, select **IAM**.

    ![AWS identity and access.](media/aws-identity-and-access.png "AWS identity and access")

1. Select **Users** and then select **Add user**.

    ![AWS users.](media/aws-users.png "AWS users")

1. In the **Details** step, provide a new user name for Defender for Cloud Apps. Make sure that under **Access type** you select **Programmatic access** and select **Next Permissions**.<a name="set-permissions"></a>

    ![Create user in AWS.](media/aws-create-user.png "Create user in AWS")

1. Select **Attach existing policies directly**, and then **Create policy**.

    ![Attach existing policies.](media/attach-existing-policies.png)

1. Select the **JSON** tab:

    ![AWS JSON tab.](media/aws-json.png "AWS JSON tab")

1. Paste the following script into the provided area:

    ```json
    {
      "Version" : "2012-10-17",
      "Statement" : [{
          "Action" : [
            "cloudtrail:DescribeTrails",
            "cloudtrail:LookupEvents",
            "cloudtrail:GetTrailStatus",
            "cloudwatch:Describe*",
            "cloudwatch:Get*",
            "cloudwatch:List*",
            "iam:List*",
            "iam:Get*",
            "s3:ListAllMyBuckets",
            "s3:PutBucketAcl",
            "s3:GetBucketAcl",
            "s3:GetBucketLocation"
          ],
          "Effect" : "Allow",
          "Resource" : "*"
        }
      ]
     }
    ```

1. Select **Next: Tags**

     ![AWS code.](media/aws-code.png "AWS code")

1. Select **Next: Review**.

    ![Add tags (optional).](media/aws-add-tags-optional.png)

1. Provide a **Name** and select **Create policy**.

    ![Provide AWS policy name.](media/aws-create-policy.png "Provide AWS policy name")

1. Back in the **Add user** screen, refresh the list if necessary, and select the user you created, and select **Next: Tags**.

    ![Attach existing policy in AWS.](media/aws-attach-policy.png "Attach existing policy in AWS")

1. Select **Next: Review**.

1. If all the details are correct, select **Create user**.

    ![User permissions in AWS.](media/aws-user-permissions.png "Review user permissions in AWS")

1. When you get the success message, select **Download .csv** to save a copy of the new user's credentials. You'll need these later.

    ![Download csv in AWS.](media/aws-download-csv.png "Download csv in AWS")

    > [!NOTE]
    > After connecting AWS, you'll receive events for seven days prior to connection. If you just enabled CloudTrail, you'll receive events from the time you enabled CloudTrail.

### Step 2: Connect Amazon Web Services auditing to Defender for Cloud Apps

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**. Under **Connected apps**, select **App Connectors**.

1. In the **App connectors** page, to provide the AWS connector credentials, do one of the following:

    **For a new connector**  

    1. Select the **+Connect an app**, followed by **Amazon Web Services**.

        ![connect AWS auditing.](media/connect-aws.png "connect AWS")

    1. In the next window, provide a name for the connector, and then select **Next**.

        ![AWS auditing connector name.](media/connect-aws-name.png)

    1. On the **Connect Amazon Web Services** page, select **Security auditing**, and then select **Next**.

    1. On the **Security auditing page**, paste the **Access key** and **Secret key** from the .csv file into the relevant fields, and select **Next**.

        ![Connect AWS app security auditing for new connector.](media/aws-connect-app-audit.png "Connect AWS app security auditing")

    **For an existing connector**

    1. In the list of connectors, on the row in which the AWS connector appears, select **Edit settings**.

        ![Screenshot of the Connected Apps page, showing edit Security Auditing link.](media/aws-connect-app-edit-audit.png)

    1. On the **Instance name** and **Connect Amazon Web Services** pages, select **Next**. On the **Security auditing page**, paste the **Access key** and **Secret key** from the .csv file into the relevant fields, and select **Next**.

        ![Connect AWS app security auditing for existing connector.](media/aws-connect-app-audit.png "Connect AWS app security auditing")

1. Select **Test API** to make sure the connection succeeded.

    Testing may take a couple of minutes. When it's finished, you get a success or failure notification. After receiving a success notice, select **Done**.

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
