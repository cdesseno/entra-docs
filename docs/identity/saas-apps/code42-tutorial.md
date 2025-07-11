---
title: Configure Code42 for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Code42.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Code42 so that I can control who has access to Code42, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure Code42 for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Code42 with Microsoft Entra ID. When you integrate Code42 with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Code42.
* Enable your users to be automatically signed-in to Code42 with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* Code42 single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* Code42 supports **SP** initiated SSO.
* Code42 supports [**automated user provisioning and deprovisioning**](code42-provisioning-tutorial.md) (recommended).


> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Add Code42 from the gallery

To configure the integration of Code42 into Microsoft Entra ID, you need to add Code42 from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Code42** in the search box.
1. Select **Code42** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 [!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]

<a name='configure-and-test-azure-ad-sso-for-code42'></a>

## Configure and test Microsoft Entra SSO for Code42

Configure and test Microsoft Entra SSO with Code42 using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Code42.

To configure and test Microsoft Entra SSO with Code42, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Code42 SSO](#configure-code42-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Code42 test user](#create-code42-test-user)** - to have a counterpart of B.Simon in Code42 that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Code42** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, perform the following step:

    In the **Sign-on URL** text box, type the URL:
    `https://www.crashplan.com/console`

1. On the **Set up single sign-on with SAML** page, In the **SAML Signing Certificate** section, select copy button to copy **App Federation Metadata Url** and save it on your computer.

	![The Certificate download link](common/copy-metadataurl.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Code42 SSO

To configure single sign-on on **Code42** side, you need to send the **App Federation Metadata Url** to [Code42 support team](http://gethelp.code42.com/). They set this setting to have the SAML SSO connection set properly on both sides.

### Create Code42 test user

In this section, you create a user called B.Simon in Code42. Work with [Code42 support team](http://gethelp.code42.com/) to add the users in the Code42 platform. Users must be created and activated before you use single sign-on.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**, this option redirects to Code42 Sign-on URL where you can initiate the login flow. 

* Go to Code42 Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you select the Code42 tile in the My Apps, this option redirects to Code42 Sign-on URL. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure Code42 you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).
