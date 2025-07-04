---
title: Configure TAS for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and TAS.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and TAS so that I can control who has access to TAS, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---
# Configure TAS for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate TAS with Microsoft Entra ID. When you integrate TAS with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to TAS.
* Enable your users to be automatically signed-in to TAS with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* TAS single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra single sign-on in a test environment.

* TAS supports **SP and IDP** initiated SSO.

## Add TAS from the gallery

To configure the integration of TAS into Microsoft Entra ID, you need to add TAS from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **TAS** in the search box.
1. Select **TAS** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-tas'></a>

## Configure and test Microsoft Entra SSO for TAS

Configure and test Microsoft Entra SSO with TAS using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in TAS.

To configure and test Microsoft Entra SSO with TAS, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure TAS SSO](#configure-tas-sso)** - to configure the single sign-on settings on application side.
    1. **[Create TAS test user](#create-tas-test-user)** - to have a counterpart of B.Simon in TAS that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **TAS** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, If you wish to configure the application in **IDP** initiated mode, perform the following steps:

    a. In the **Identifier** text box, type a URL using the following pattern:
    `https://taseu.combtas.com/<DOMAIN>`

    b. In the **Reply URL** text box, type a URL using the following pattern:
    `https://taseu.combtas.com/<ENVIRONMENT_NAME>/AssertionService.aspx`

5. Select **Set additional URLs** and perform the following step if you wish to configure the application in **SP** initiated mode:

    In the **Sign-on URL** text box, type a URL using the following pattern:
    `https://taseu.combtas.com/<DOMAIN>`

	> [!NOTE]
	> These values aren't real. You update these with the actual Identifier, Reply URL and Sign-on URL which is explained later in the article. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

6. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, select **Download** to download the **Certificate (Base64)** from the given options as per your requirement and save it on your computer.

	![The Certificate download link](common/certificatebase64.png)

7. On the **Set up TAS** section, copy the appropriate URL(s) as per your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure TAS SSO

1. In a different web browser window, login to TAS as an Administrator.

2. On the left side of menu, select **Settings** and navigate to **Administrator** and then select **Manage Single sign on**.

	![Screenshot shows Manage Single sign on selected.](./media/tas-tutorial/settings.png)

3. On the **Manage Single sign on** page, perform the following steps:

	![Screenshot shows the Manage Single sign on page where you can enter the values described.](./media/tas-tutorial/configure.png)

	a. In the **Name** textbox, type your environment name.
	
	b. Select **SAML2** as **Authentication Type**.

	c. In the **Enter URL** textbox, paste the value of **Login URL** which you copied previously.

	d. In Notepad, open the base-64 encoded certificate that you downloaded, copy its content, and then paste it into the **Enter Certification** box.

	e. In the **Enter New IP** textbox, type the IP Address.

	>[!NOTE]
	> Contact [TAS support team](mailto:support@combtas.com) to get the IP Address.

	f. Copy the **Single Sign On** URL and paste it into the **identifier (Entity ID)** and **Sign on URL** textbox of **Basic SAML Configuration** in Azure portal. Please note that the URL is case sensitive and must end with a slash (/).

	g. Copy the **Assertion Service** URL in the setup page and paste it into the **Reply URL** textbox of  **Basic SAML Configuration** in Azure portal.

	h. Select **Insert SSO row**.

### Create TAS test user

In this section, you create a user called Britta Simon in TAS. Work with [TAS support team](mailto:support@combtas.com) to add the users in the TAS platform. Users must be created and activated before you use single sign-on.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

#### SP initiated:

* Select **Test this application**, this option redirects to TAS Sign on URL where you can initiate the login flow.  

* Go to TAS Sign-on URL directly and initiate the login flow from there.

#### IDP initiated:

* Select **Test this application**, and you should be automatically signed in to the TAS for which you set up the SSO. 

You can also use Microsoft My Apps to test the application in any mode. When you select the TAS tile in the My Apps, if configured in SP mode you would be redirected to the application sign on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the TAS for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure TAS you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).
