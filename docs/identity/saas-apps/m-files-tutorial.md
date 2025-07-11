---
title: Configure M-Files for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and M-Files.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and M-Files so that I can control who has access to M-Files, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---
# Configure M-Files for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate M-Files with Microsoft Entra ID. When you integrate M-Files with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to M-Files.
* Enable your users to be automatically signed-in to M-Files with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* M-Files single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra single sign-on in a test environment.

* M-Files supports **SP** initiated SSO.
* M-Files supports [Automated user provisioning](m-files-provisioning-tutorial.md).

## Add M-Files from the gallery

To configure the integration of M-Files into Microsoft Entra ID, you need to add M-Files from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **M-Files** in the search box.
1. Select **M-Files** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-m-files'></a>

## Configure and test Microsoft Entra SSO for M-Files

Configure and test Microsoft Entra SSO with M-Files using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in M-Files.

To configure and test Microsoft Entra SSO with M-Files, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure M-Files SSO](#configure-m-files-sso)** - to configure the single sign-on settings on application side.
    1. **[Create M-Files test user](#create-m-files-test-user)** - to have a counterpart of B.Simon in M-Files that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **M-Files** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, perform the following steps:

	a. In the **Sign on URL** text box, type a URL using the following pattern:
    `https://<tenantname>.cloudvault.m-files.com/authentication/MFiles.AuthenticationProviders.Core/sso`

    b. In the **Identifier (Entity ID)** text box, type a URL using the following pattern:
    `https://<tenantname>.cloudvault.m-files.com`

	> [!NOTE]
	> These values aren't real. Update these values with the actual Sign on URL and Identifier. Contact [M-Files Client support team](mailto:support@m-files.com) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, select **Download** to download the **Federation Metadata XML** from the given options as per your requirement and save it on your computer.

	![The Certificate download link](common/metadataxml.png)

6. On the **Set up M-Files** section, copy the appropriate URL(s) as per your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure M-Files SSO

1. To get SSO configured for your application, contact [M-Files support team](mailto:support@m-files.com) and provide them the downloaded Metadata.
   
    >[!NOTE]
    >Follow the next steps if you want to configure SSO for you M-File desktop application. No extra steps are required if you only want to configure SSO for M-Files web version.  

1. Follow the next steps to configure the M-File desktop application to enable SSO with Microsoft Entra ID. To download M-Files, go to [M-Files download](https://www.m-files.com/customers/product-downloads/download-update-links/) page.

1. Open the **M-Files Desktop Settings** window. Then, select **Add**.
   
    ![Screenshot shows M-Files Desktop Settings where you can select Add.](./media/m-files-tutorial/settings.png)

1. On the **Document Vault Connection Properties** window, perform the following steps:
   
    ![Screenshot shows Document Vault Connection Properties where you can enter the values described.](./media/m-files-tutorial/general.png)  

    Under the Server section type, the values as follows:  

    a. For **Name**, type `<tenant-name>.cloudvault.m-files.com`. 
 
    b. For **Port Number**, type **4466**. 

    c. For **Protocol**, select **HTTPS**. 

    d. In the **Authentication** field, select **Specific Windows user**. Then, you're prompted with a signing page. Insert your Microsoft Entra credentials. 

    e. For the **Vault on Server**,  select the corresponding vault on server.
 
    f. Select **OK**.

### Create M-Files test user

The objective of this section is to create a user called Britta Simon in M-Files. Work with  [M-Files support team](mailto:support@m-files.com) to add the users in the M-Files.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**, this option redirects to M-Files Sign-on URL where you can initiate the login flow. 

* Go to M-Files Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you select the M-Files tile in the My Apps, this option redirects to M-Files Sign-on URL. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure M-Files you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).
