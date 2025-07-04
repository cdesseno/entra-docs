---
title: Configure SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and SSOGEN Microsoft Entra SSO Gateway for Oracle E Business Suite EBS, PeopleSoft, and JDE so that I can control who has access to SSOGEN Microsoft Entra SSO Gateway for Oracle E Business Suite EBS, PeopleSoft, and JDE, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE with Microsoft Entra ID. When you integrate SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE.
* Enable your users to be automatically signed-in to SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE supports **SP and IDP** initiated SSO.

> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

<a name='add-ssogen---azure-ad-sso-gateway-for-oracle-e-business-suite---ebs-peoplesoft-and-jde-from-the-gallery'></a>

## Add SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE from the gallery

To configure the integration of SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE into Microsoft Entra ID, you need to add SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE** in the search box.
1. Select **SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-ssogen---azure-ad-sso-gateway-for-oracle-e-business-suite---ebs-peoplesoft-and-jde'></a>

## Configure and test Microsoft Entra SSO for SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE

Configure and test Microsoft Entra SSO with SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE.

To configure and test Microsoft Entra SSO with SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE SSO](#configure-ssogen---azure-ad-sso-gateway-for-oracle-e-business-suite---ebs-peoplesoft-and-jde-sso)** - to configure the single sign-on settings on application side.
    1. **[Create SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE test user](#create-ssogen---azure-ad-sso-gateway-for-oracle-e-business-suite---ebs-peoplesoft-and-jde-test-user)** - to have a counterpart of B.Simon in SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, if you wish to configure the application in **IDP** initiated mode, enter the values for the following fields:

    In the **Reply URL** text box, type a URL using the following pattern:
    `https://<customer_name>.ssogen.com/ssogen/login?client_name=<customer_name>`

1. Select **Set additional URLs** and perform the following step if you wish to configure the application in **SP** initiated mode:

    In the **Sign-on URL** text box, type a URL using the following pattern:
    `https://<customer_name>.ssogen.com/ssogen/login?client_name=<customer_name>`

	> [!NOTE]
	> These values aren't real. Update these values with the actual Reply URL and Sign-On URL. Contact [SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE Client support team](mailto:support@ssogen.com) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. Your SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes, whereas **nameidentifier** is mapped with **user.userprincipalname**. SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE application expects **nameidentifier** to be mapped with **user.onpremisessamaccountname**, so you need to edit the attribute mapping by selecting **Edit** icon and change the attribute mapping.

	![image](common/edit-attribute.png)

1. On the **Set up single sign-on with SAML** page, In the **SAML Signing Certificate** section, select copy button to copy **App Federation Metadata Url** and save it on your computer.

	![The Certificate download link](common/copy-metadataurl.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

<a name='configure-ssogen---azure-ad-sso-gateway-for-oracle-e-business-suite---ebs-peoplesoft-and-jde-sso'></a>

## Configure SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE SSO

To configure single sign-on on **SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE** side, Please find application-specific SSO registration documentation below:

* Oracle EBS - Microsoft Entra SSO Integration: [https://www.ssogen.com/oracle-ebs-sso-ldap/](https://www.ssogen.com/oracle-ebs-sso-ldap/)
* PeopleSoft - Microsoft Entra SSO Integration: [https://www.ssogen.com/peoplesoft-sso/](https://www.ssogen.com/peoplesoft-sso/)
* JD Edwards - Microsoft Entra SSO Integration: [https://www.ssogen.com/oracle-jde-sso/](https://www.ssogen.com/oracle-jde-sso/)
* Apache - Microsoft Entra SSO Integration: [https://www.ssogen.com/apache-sso-authentication/](https://www.ssogen.com/apache-sso-authentication/)

<a name='create-ssogen---azure-ad-sso-gateway-for-oracle-e-business-suite---ebs-peoplesoft-and-jde-test-user'></a>

### Create SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE test user

Microsoft Entra ID sends Unique User Identifier (Name ID) to the user application, after the authentication is successful.  Please make sure that Unique User Identifier (Name ID) matches user record in your application, FND_USER.USER_NAME in Oracle EBS for example.

Please contact [info@ssogen.com](mailto:info@ssogen.com) and [support@ssogen.com](mailto:support@ssogen.com) for any support.

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

#### SP initiated:

* Select **Test this application**, this option redirects to SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE Sign on URL where you can initiate the login flow.  

* Go to SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE Sign-on URL directly and initiate the login flow from there.

#### IDP initiated:

* Select **Test this application**, and you should be automatically signed in to the SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE for which you set up the SSO. 

You can also use Microsoft My Apps to test the application in any mode. When you select the SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE tile in the My Apps, if configured in SP mode you would be redirected to the application sign on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure SSOGEN - Microsoft Entra SSO Gateway for Oracle E-Business Suite - EBS, PeopleSoft, and JDE you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).
