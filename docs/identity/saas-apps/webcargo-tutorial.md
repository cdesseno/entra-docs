---
title: Configure Webcargo for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Webcargo.
author: nguhiu
manager: mwongerapk
ms.reviewer: CelesteDG
ms.service: entra-id
ms.subservice: saas-apps
ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu
ms.custom: sfi-image-nochange
# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Webcargo so that I can control who has access to Webcargo, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure Webcargo for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Webcargo with Microsoft Entra ID. When you integrate Webcargo with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Webcargo.
* Enable your users to be automatically signed-in to Webcargo with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* Webcargo single sign-on (SSO) enabled subscription.

> [!NOTE]
> This integration is also available to use from Microsoft Entra US Government Cloud environment. You can find this application in the Microsoft Entra US Government Cloud Application Gallery and configure it in the same way as you do from public cloud.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* Webcargo supports **SP and IDP** initiated SSO.

> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Add Webcargo from the gallery

To configure the integration of Webcargo into Microsoft Entra ID, you need to add Webcargo from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Webcargo** in the search box.
1. Select **Webcargo** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-webcargo'></a>

## Configure and test Microsoft Entra SSO for Webcargo

Configure and test Microsoft Entra SSO with Webcargo using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Webcargo.

To configure and test Microsoft Entra SSO with Webcargo, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Webcargo SSO](#configure-webcargo-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Webcargo test user](#create-webcargo-test-user)** - to have a counterpart of B.Simon in Webcargo that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Webcargo** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, if you wish to configure the application in **IDP** initiated mode, perform the following step:

    In the **Reply URL** text box, type a URL using the following pattern:
    `https://www.webcargo.net/sso/azure/account-id/<ID>`

1. Select **Set additional URLs** and perform the following step if you wish to configure the application in **SP** initiated mode:

    In the **Sign-on URL** text box, type a URL using the following pattern:
    `https://www.webcargo.net/sso/azure/account-id/<ID>`

	> [!NOTE]
	> These values aren't real. Update these values with the actual Reply URL and Sign-on URL. Contact [Webcargo Client support team](mailto:tickets@webcargo.uservoice.com) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section,  find **Certificate (Base64)** and select **Download** to download the certificate and save it on your computer.

	![The Certificate download link](common/certificatebase64.png)

1. On the **Set up Webcargo** section, copy the appropriate URL(s) based on your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Webcargo SSO




1. In a different web browser window, sign in to your up Webcargo company site as an administrator

1. Select **Team** at the left side navigation and select **SSO idP** tab then, enable the **Microsoft Azure**.

	![Configure Single Sign-On settings icon](./media/webcargo-tutorial/webcargo-team.png)

1. In the **Azure Configuration** section, in the Login URL textbox, paste the **Login URL** value which you have copied, select **Choose File** to upload the **Certificate (Base64)** file which you have downloaded.

    ![Configure Single Sign-On Choose File](./media/webcargo-tutorial/xml-choose.png)

1. Select **Save**.

### Create Webcargo test user

In this section, you create a user called Britta Simon in Webcargo. Work with [Webcargo support team](mailto:tickets@webcargo.uservoice.com) to add the users in the Webcargo platform. Users must be created and activated before you use single sign-on.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

#### SP initiated:

* Select **Test this application**, this option redirects to Webcargo Sign on URL where you can initiate the login flow.  

* Go to Webcargo Sign-on URL directly and initiate the login flow from there.

#### IDP initiated:

* Select **Test this application**, and you should be automatically signed in to the Webcargo for which you set up the SSO. 

You can also use Microsoft My Apps to test the application in any mode. When you select the Webcargo tile in the My Apps, if configured in SP mode you would be redirected to the application sign-on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the Webcargo for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure Webcargo you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).
