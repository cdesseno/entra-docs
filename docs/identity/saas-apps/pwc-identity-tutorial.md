---
title: Configure PwC Identity for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and PwC Identity.

author: nguhiu
manager: mwongerapk
ms.reviewer: CelesteDG
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu


# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and PwC Identity so that I can control who has access to PwC Identity, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure PwC Identity for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate PwC Identity with Microsoft Entra ID. When you integrate PwC Identity with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to PwC Identity.
* Enable your users to be automatically signed-in to PwC Identity with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* PwC Identity single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* PwC Identity supports **SP** initiated SSO.

> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Add PwC Identity from the gallery

To configure the integration of PwC Identity into Microsoft Entra ID, you need to add PwC Identity from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **PwC Identity** in the search box.
1. Select **PwC Identity** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-pwc-identity'></a>

## Configure and test Microsoft Entra SSO for PwC Identity

Configure and test Microsoft Entra SSO with PwC Identity using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in PwC Identity.

To configure and test Microsoft Entra SSO with PwC Identity, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure PwC Identity SSO](#configure-pwc-identity-sso)** - to configure the single sign-on settings on application side.
    1. **[Create PwC Identity test user](#create-pwc-identity-test-user)** - to have a counterpart of B.Simon in PwC Identity that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **PwC Identity** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Screenshot shows how to edit Basic SAML Configuration.](common/edit-urls.png "Basic Configuration")

1. On the **Basic SAML Configuration** section, perform the following steps:

	a. In the **Identifier (Entity ID)** text box, type the value:
    `urn:pwcid:saml:sp:p`

	b. In the **Reply URL** textbox, type the URL:
	`https://login.pwc.com/openam/PWCIAuthConsumer/metaAlias/pwc/sp3`

	c. In the **Sign on URL** text box, type the URL:
    `https://researchcreditsolution.pwc.com/`

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section, find **Federation Metadata XML** and select **Download** to download the certificate and save it on your computer.

	![Screenshot shows the Certificate download link.](common/metadataxml.png "Certificate")

1. On the **Set up PwC Identity** section, copy the appropriate URL(s) based on your requirement.

	![Screenshot shows to copy configuration appropriate URL.](common/copy-configuration-urls.png "Metadata")

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure PwC Identity SSO

To configure single sign-on on **PwC Identity** side, you need to send the downloaded **Federation Metadata XML** and appropriate copied URLs from the application configuration to [PwC Identity support team](https://www.pwc.com/us/en/services/tax/specialized-tax/research-development-credit.html). They set this setting to have the SAML SSO connection set properly on both sides.

### Create PwC Identity test user

In this section, you create a user called Britta Simon in PwC Identity. Work with [PwC Identity support team](https://www.pwc.com/us/en/services/tax/specialized-tax/research-development-credit.html) to add the users in the PwC Identity platform. Users must be created and activated before you use single sign-on.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**, this option redirects to PwC Identity Sign on URL where you can initiate the login flow. 

* Go to PwC Identity Sign on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you select the PwC Identity tile in the My Apps, this option redirects to PwC Identity Sign on URL. For more information, see [Microsoft Entra My Apps](/azure/active-directory/manage-apps/end-user-experiences#azure-ad-my-apps).

## Related content

Once you configure PwC Identity you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).
