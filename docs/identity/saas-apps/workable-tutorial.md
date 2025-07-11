---
title: Configure Workable for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Workable.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Workable so that I can control who has access to Workable, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---
# Configure Workable for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Workable with Microsoft Entra ID. When you integrate Workable with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Workable.
* Enable your users to be automatically signed-in to Workable with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* Workable single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra single sign-on in a test environment.

* Workable supports **SP and IDP** initiated SSO.
* Workable supports **Just In Time** user provisioning.

> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Add Workable from the gallery

To configure the integration of Workable into Microsoft Entra ID, you need to add Workable from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Workable** in the search box.
1. Select **Workable** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-workable'></a>

## Configure and test Microsoft Entra SSO for Workable

Configure and test Microsoft Entra SSO with Workable using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Workable.

To configure and test Microsoft Entra SSO with Workable, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Workable SSO](#configure-workable-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Workable test user](#create-workable-test-user)** - to have a counterpart of B.Simon in Workable that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Workable** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, If you wish to configure the application in **IDP** initiated mode, perform the following step:

	In the **Reply URL** text box, type a URL using the following pattern:
    `https://id.workable.com/auth/saml/ats_server/<SUBDOMAIN>/callback`

1. Select **set additional URLs** and perform the following step if you wish to configure the application in **SP** initiated mode:

    In the **Sign-on URL** text box, type a URL using the following pattern:
    `https://<SUBDOMAIN>.workable.com/signin`

	> [!NOTE]
	> These values aren't real. Update these values with the actual Reply URL and Sign on URL. Contact [Workable Client support team](mailto:support@workable.com) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, select **Download** to download the **Certificate (Base64)** from the given options as per your requirement and save it on your computer.

	![The Certificate download link](common/certificatebase64.png)

1. On the **Set up Workable** section, copy the appropriate URL(s) as per your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Workable SSO

To enable SSO in Workable, contact your dedicated Workable account manager and provide them with the following items.

1. Login URL.

2. Certificate file.

3. Logout URL.

Once Single Sign On has been enabled, your Workable account manager will let you know and you can use [Workable's SSO page](https://help.workable.com/hc/articles/360000067753-Single-Sign-on-SSO-Overview-Pro) to sign in using your Workable account subdomain.

### Create Workable test user

In this section, a user called Britta Simon is created in Workable. Workable supports just-in-time user provisioning, which is enabled by default. There's no action item for you in this section. If a user doesn't already exist in Workable, a new one is created after authentication.

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

#### SP initiated:

* Select **Test this application**, this option redirects to Workable Sign on URL where you can initiate the login flow.  

* Go to Workable Sign-on URL directly and initiate the login flow from there.

#### IDP initiated:

* Select **Test this application**, and you should be automatically signed in to the Workable for which you set up the SSO. 

You can also use Microsoft My Apps to test the application in any mode. When you select the Workable tile in the My Apps, if configured in SP mode you would be redirected to the application sign on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the Workable for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure Workable you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).
