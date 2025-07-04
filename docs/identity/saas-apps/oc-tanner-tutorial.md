---
title: Configure O.C. Tanner - AppreciateHub for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and O.C. Tanner - AppreciateHub.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and O.C. Tanner - AppreciateHub so that I can control who has access to O.C. Tanner - AppreciateHub, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---
# Configure O.C. Tanner - AppreciateHub for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate O.C. Tanner - AppreciateHub with Microsoft Entra ID. When you integrate O.C. Tanner - AppreciateHub with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to O.C. Tanner - AppreciateHub.
* Enable your users to be automatically signed-in to O.C. Tanner - AppreciateHub with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* O.C. Tanner - AppreciateHub single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* O.C. Tanner - AppreciateHub supports **IDP** initiated SSO.

## Add O.C. Tanner - AppreciateHub from the gallery

To configure the integration of O.C. Tanner - AppreciateHub into Microsoft Entra ID, you need to add O.C. Tanner - AppreciateHub from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **O.C. Tanner - AppreciateHub** in the search box.
1. Select **O.C. Tanner - AppreciateHub** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 [!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]

<a name='configure-and-test-azure-ad-sso-for-oc-tanner---appreciatehub'></a>

## Configure and test Microsoft Entra SSO for O.C. Tanner - AppreciateHub

Configure and test Microsoft Entra SSO with O.C. Tanner - AppreciateHub using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in O.C. Tanner - AppreciateHub.

To configure and test Microsoft Entra SSO with O.C. Tanner - AppreciateHub, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure O.C. Tanner - AppreciateHub SSO](#configure-oc-tanner---appreciatehub-sso)** - to configure the single sign-on settings on application side.
    1. **[Create O.C. Tanner - AppreciateHub test user](#create-oc-tanner---appreciatehub-test-user)** - to have a counterpart of B.Simon in O.C. Tanner - AppreciateHub that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **O.C. Tanner - AppreciateHub** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, the user doesn't have to perform any step as the app is already pre-integrated with Azure.

1. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, select **Download** to download the **Federation Metadata XML** from the given options as per your requirement and save it on your computer.

	![The Certificate download link](common/metadataxml.png)

1. On the **Set up O.C. Tanner - AppreciateHub** section, copy the appropriate URL(s) as per your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure O.C. Tanner - AppreciateHub SSO

To configure single sign-on on **O.C. Tanner - AppreciateHub** side, you need to send the downloaded **Federation Metadata XML** and appropriate copied URLs from the application configuration to [O.C. Tanner - AppreciateHub support team](mailto:sso@octanner.com). They set this setting to have the SAML SSO connection set properly on both sides.

### Create O.C. Tanner - AppreciateHub test user

The objective of this section is to create a user called Britta Simon in O.C. Tanner - AppreciateHub.

**To create a user called Britta Simon in O.C. Tanner - AppreciateHub, perform the following steps:**

Ask your [O.C. Tanner - AppreciateHub support team](mailto:sso@octanner.com) to create a user that has as nameID attribute the same value as the user name of Britta Simon in Microsoft Entra ID.

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with following options.

* Select **Test this application**, and you should be automatically signed in to the O.C. Tanner - AppreciateHub for which you set up the SSO.

* You can use Microsoft My Apps. When you select the O.C. Tanner - AppreciateHub tile in the My Apps, you should be automatically signed in to the O.C. Tanner - AppreciateHub for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure O.C. Tanner - AppreciateHub you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).
