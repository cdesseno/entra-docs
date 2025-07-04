---
title: Configure Cheetah For Benelux for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Cheetah For Benelux.

author: nguhiu
manager: mwongerapk
ms.reviewer: CelesteDG
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu


# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Cheetah For Benelux so that I can control who has access to Cheetah For Benelux, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure Cheetah For Benelux for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Cheetah For Benelux with Microsoft Entra ID. When you integrate Cheetah For Benelux with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Cheetah For Benelux.
* Enable your users to be automatically signed-in to Cheetah For Benelux with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

To get started, you need the following items:

* A Microsoft Entra subscription. If you don't have a subscription, you can get a [free account](https://azure.microsoft.com/free/).
* Cheetah For Benelux single sign-on (SSO) enabled subscription.
* Along with Cloud Application Administrator, Application Administrator can also add or manage applications in Microsoft Entra ID.
For more information, see [Azure built-in roles](~/identity/role-based-access-control/permissions-reference.md).

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* Cheetah For Benelux supports **SP** initiated SSO.
* Cheetah For Benelux supports **Just In Time** user provisioning.

> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Add Cheetah For Benelux from the gallery

To configure the integration of Cheetah For Benelux into Microsoft Entra ID, you need to add Cheetah For Benelux from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Cheetah For Benelux** in the search box.
1. Select **Cheetah For Benelux** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 [!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]

<a name='configure-and-test-azure-ad-sso-for-cheetah-for-benelux'></a>

## Configure and test Microsoft Entra SSO for Cheetah For Benelux

Configure and test Microsoft Entra SSO with Cheetah For Benelux using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Cheetah For Benelux.

To configure and test Microsoft Entra SSO with Cheetah For Benelux, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Cheetah For Benelux SSO](#configure-cheetah-for-benelux-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Cheetah For Benelux test user](#create-cheetah-for-benelux-test-user)** - to have a counterpart of B.Simon in Cheetah For Benelux that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Cheetah For Benelux** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

    ![Screenshot shows to edit Basic S A M L Configuration.](common/edit-urls.png "Basic Configuration")

1. On the **Basic SAML Configuration** section, perform the following steps:

    a. In the **Reply URL** textbox, type the URL:
    `https://ups.eu.sso.cheetah.com/saml2/idpresponse`

    b. In the **Sign-on URL** text box, type the URL:
    `https://ups.eu.sso.cheetah.com/login?client_id=5c2m16mhv4cd4o5cpgekmsmlne&response_type=token&scope=aws.cognito.signin.user.admin+openid+profile&redirect_uri=https://prodeditor.eu.cheetah.com/CssWebTask/landing/?cheetah_client=BNLX`

1. On the **Set-up single sign-on with SAML** page, in the **SAML Signing Certificate** section,  find **Federation Metadata XML** and select **Download** to download the certificate and save it on your computer.

    ![Screenshot shows the Certificate download link.](common/metadataxml.png "Certificate")

1. On the **Set up Cheetah For Benelux** section, copy the appropriate URL(s) based on your requirement.

	![Screenshot shows to copy configuration appropriate U R L.](common/copy-configuration-urls.png "Metadata")  

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Cheetah For Benelux SSO

To configure single sign-on on **Cheetah For Benelux** side, you need to send the downloaded **Federation Metadata XML** and appropriate copied URLs from the application configuration to [Cheetah For Benelux support team](mailto:support@cheetah.com). They set this setting to have the SAML SSO connection set properly on both sides.

### Create Cheetah For Benelux test user

In this section, a user called B.Simon is created in Cheetah For Benelux. Cheetah For Benelux supports just-in-time user provisioning, which is enabled by default. There's no action item for you in this section. If a user doesn't already exist in Cheetah For Benelux, a new one is created after authentication.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**, this option redirects to Cheetah For Benelux Sign-on URL where you can initiate the login flow. 

* Go to Cheetah For Benelux Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you select the Cheetah For Benelux tile in the My Apps, this option redirects to Cheetah For Benelux Sign-on URL. For more information, see [Microsoft Entra My Apps](/azure/active-directory/manage-apps/end-user-experiences#azure-ad-my-apps).

## Related content

Once you configure Cheetah For Benelux you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Cloud App Security](/cloud-app-security/proxy-deployment-aad).
