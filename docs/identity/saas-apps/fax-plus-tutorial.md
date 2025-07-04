---
title: Configure FAX.PLUS for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and FAX.PLUS.
author: nguhiu
manager: mwongerapk
ms.reviewer: CelesteDG
ms.service: entra-id
ms.subservice: saas-apps
ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu
ms.custom: sfi-image-nochange
# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and FAX.PLUS so that I can control who has access to FAX.PLUS, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure FAX.PLUS for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate FAX.PLUS with Microsoft Entra ID. When you integrate FAX.PLUS with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to FAX.PLUS.
* Enable your users to be automatically signed-in to FAX.PLUS with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* FAX.PLUS single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* FAX.PLUS supports **SP and IDP** initiated SSO.
* FAX.PLUS supports **Just In Time** user provisioning.

> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Add FAX.PLUS from the gallery

To configure the integration of FAX.PLUS into Microsoft Entra ID, you need to add FAX.PLUS from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **FAX.PLUS** in the search box.
1. Select **FAX.PLUS** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 [!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]


<a name='configure-and-test-azure-ad-sso-for-faxplus'></a>

## Configure and test Microsoft Entra SSO for FAX.PLUS

Configure and test Microsoft Entra SSO with FAX.PLUS using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in FAX.PLUS.

To configure and test Microsoft Entra SSO with FAX.PLUS, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure FAX.PLUS SSO](#configure-faxplus-sso)** - to configure the single sign-on settings on application side.
    1. **[Create FAX.PLUS test user](#create-faxplus-test-user)** - to have a counterpart of B.Simon in FAX.PLUS that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **FAX.PLUS** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, the user doesn't have to perform any step as the app is already pre-integrated with Azure.

1. Select **Set additional URLs** and perform the following step if you wish to configure the application in **SP** initiated mode:

    In the **Sign-on URL** text box, type the URL:
    `https://www.fax.plus/login`

1. Select **Save**.

1. FAX.PLUS application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	![image](common/default-attributes.png)

1. In addition to above, FAX.PLUS application expects few more attributes to be passed back in SAML response, which are shown below. These attributes are also pre populated but you can review them as per your requirements.
	
	| Name | Source Attribute|
	| --------------- | --------- |
	| firstname  | user.givenname |
	| lastname   | user.surname   |

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section,  find **Certificate (Base64)** and select **Download** to download the certificate and save it on your computer.

	![The Certificate download link](common/certificatebase64.png)

1. On the **Set up FAX.PLUS** section, copy the appropriate URL(s) based on your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure FAX.PLUS SSO




1. In a different web browser window, sign in to your FAX.PLUS company site as an administrator

2. Go to the **Security** section in your Admin Profile and scroll down to **Advanced**.

3. On the **Configuration** panel, select the **Activate Single Sign-On** button and perform the following steps.
    
    ![Account](./media/fax.plus-tutorial/configuration.png "Account") 

    a. In the **Entity ID** textbox, paste the **Microsoft Entra Identifier** value which you copied previously.

    b. In the **Single Sign-On URL** textbox, paste the **Login URL** value which you copied previously.

    c. Open the downloaded **Certificate (Base64)** into Notepad and paste the content into the **X.509 Certificate** textbox.

    d. If you want to login through SSO, enable **Only Allow SSO Login for Admin User** checkbox. 

    e. Select **Confirm**.

### Create FAX.PLUS test user

In this section, a user called Britta Simon is created in FAX.PLUS. FAX.PLUS supports just-in-time user provisioning, which is enabled by default. There's no action item for you in this section. If a user doesn't already exist in FAX.PLUS, a new one is created after authentication.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

#### SP initiated:

* Select **Test this application**, this option redirects to FAX.PLUS Sign on URL where you can initiate the login flow.  

* Go to FAX.PLUS Sign-on URL directly and initiate the login flow from there.

#### IDP initiated:

* Select **Test this application**, and you should be automatically signed in to the FAX.PLUS for which you set up the SSO. 

You can also use Microsoft My Apps to test the application in any mode. When you select the FAX.PLUS tile in the My Apps, if configured in SP mode you would be redirected to the application sign on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the FAX.PLUS for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure FAX.PLUS you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).
