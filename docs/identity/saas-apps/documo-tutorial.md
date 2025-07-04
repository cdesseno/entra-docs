---
title: Configure Documo for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Documo.
author: nguhiu
manager: mwongerapk
ms.reviewer: CelesteDG
ms.service: entra-id
ms.subservice: saas-apps
ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu
ms.custom: sfi-image-nochange
# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Documo so that I can control who has access to Documo, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure Documo for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Documo with Microsoft Entra ID. When you integrate Documo with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Documo.
* Enable your users to be automatically signed-in to Documo with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* Documo single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* Documo supports **SP and IDP** initiated SSO.
* Documo supports [Automated user provisioning](documo-provisioning-tutorial.md).

> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Adding Documo from the gallery

To configure the integration of Documo into Microsoft Entra ID, you need to add Documo from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Documo** in the search box.
1. Select **Documo** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 [!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]


<a name='configure-and-test-azure-ad-sso-for-documo'></a>

## Configure and test Microsoft Entra SSO for Documo

Configure and test Microsoft Entra SSO with Documo using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Documo.

To configure and test Microsoft Entra SSO with Documo, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Documo SSO](#configure-documo-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Documo test user](#create-documo-test-user)** - to have a counterpart of B.Simon in Documo that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Documo** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, the user doesn't have to perform any step as the app is already pre-integrated with Azure. If your Documo account has a custom domain, you must also have a custom API domain for SSO to work. Replace the default values with your custom API domain, for example, `https://mycustomapidomain.com` and `https://mycustomapidomain.com/assert`.

1. Select **Set additional URLs** and perform the following step if you wish to configure the application in **SP** initiated mode:

    In the **Sign-on URL** text box, type the URL:  
    `https://app.documo.com/sso`

1. Select **Save**.

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section,  find **Federation Metadata XML** and select **Download** to download the certificate and save it on your computer.

	![The Certificate download link](common/metadataxml.png)

1. On the **Set up Documo** section, copy the appropriate URL(s) based on your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Documo SSO

1. Log in to your Documo website as an administrator.

1. Go to the **Account Settings** > **Security**.

    ![screenshot for security page.](./media/documo-tutorial/security.png)

1. In the security tab, select **Configure SSO** button at the bottom of the page.

    ![screenshot for configure button.](./media/documo-tutorial/configure-sso.png)

1. Perform the following steps in the **Setup SAML** page.

    ![screenshot for configuration page.](./media/documo-tutorial/setup-saml.png)

    a. In the **Entity Id** textbox, paste the **Microsoft Entra Identifier** value which you copied previously.

    b. In the **SSO URL(Redirect URL)** textbox, paste the **Login URL** value which you copied previously.

    c. Give the **Email Domain** value in the text box.

    d. Enter the value in the **Field Name in SAML Token containing Identity email** text box.

    e. Open the downloaded **Federation Metadata XML** into Notepad. Find the `<X509Certificate>` tag and paste the content into the **Signer Certificate** textbox.

    f. Select **Submit**.

### Create Documo test user

In this section, a user called B.Simon is created in Documo. 

1. Navigate to the [Users page](https://app.documo.com?redirectTo=/users) on the Documo app.
1. Select the **New user** button.
1. Fill out the user form with name, email, phone number, user role, and password information. Make sure the **email** field matches the email for B.Simon in **Microsoft Entra ID**.
1. Select **Create**.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

#### SP initiated:

* Select **Test this application**, this option redirects to Documo Sign on URL where you can initiate the login flow.  

* Go to Documo Sign-on URL directly and initiate the login flow from there.

#### IDP initiated:

* Select **Test this application**, and you should be automatically signed in to the Documo for which you set up the SSO 

You can also use Microsoft My Apps to test the application in any mode. When you select the Documo tile in the My Apps, if configured in SP mode you would be redirected to the application sign on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the Documo for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).


## Related content

Once you configure Documo you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).
