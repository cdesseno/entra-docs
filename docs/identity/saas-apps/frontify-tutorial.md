---
title: Configure Frontify for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Frontify.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Frontify so that I can control who has access to Frontify, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure Frontify for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Frontify with Microsoft Entra ID. When you integrate Frontify with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Frontify.
* Enable your users to be automatically signed-in to Frontify with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* Frontify single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* Frontify supports **SP** initiated SSO.

## Add Frontify from the gallery

To configure the integration of Frontify into Microsoft Entra ID, you need to add Frontify from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Frontify** in the search box.
1. Select **Frontify** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 [!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]

<a name='configure-and-test-azure-ad-sso-for-frontify'></a>

## Configure and test Microsoft Entra SSO for Frontify

Configure and test Microsoft Entra SSO with Frontify using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Frontify.

To configure and test Microsoft Entra SSO with Frontify, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Frontify SSO](#configure-frontify-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Frontify test user](#create-frontify-test-user)** - to have a counterpart of B.Simon in Frontify that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Frontify** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, perform the following steps:

    a. In the **Identifier (Entity ID)** text box, type a URL using the following pattern:
    `https://<DOMAIN NAME>/api/auth/saml/metadata/`
    
	b. In the **Sign-on URL** text box, type a URL using the following pattern:
    `https://<DOMAIN NAME>/`

	> [!NOTE]
	> These values aren't real. Update these values with the actual Identifier and Sign on URL. Contact [Frontify Client support team](mailto:support@frontify.com) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. On the **Set-up single sign-on with SAML** page, In the **SAML Signing Certificate** section, select copy button to copy **App Federation Metadata Url** and save it on your computer.

	![The Certificate download link](common/copy-metadataurl.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Frontify SSO

To configure single sign-on on **Frontify** side, you need to send the **App Federation Metadata Url** to [Frontify support team](mailto:support@frontify.com). They set this setting to have the SAML SSO connection set properly on both sides.

### Create Frontify test user

In this section, you create a user called Britta Simon in Frontify. Work with [Frontify support team](mailto:support@frontify.com) to add the users in the Frontify platform. Users must be created and activated before you use single sign-on.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**, this option redirects to Frontify Sign-on URL where you can initiate the login flow. 

* Go to Frontify Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you select the Frontify tile in the My Apps, this option redirects to Frontify Sign-on URL. For more information, see [Microsoft Entra My Apps](/azure/active-directory/manage-apps/end-user-experiences#azure-ad-my-apps).

## Related content

Once you configure Frontify you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Cloud App Security](/cloud-app-security/proxy-deployment-aad).
