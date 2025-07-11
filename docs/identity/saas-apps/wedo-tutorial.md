---
title: Configure WEDO for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and WEDO.
author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps
ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu
ms.custom: sfi-image-nochange
# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Wedo so that I can control who has access to Wedo, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure WEDO for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate WEDO with Microsoft Entra ID. When you integrate WEDO with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to WEDO.
* Enable your users to be automatically signed-in to WEDO with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* WEDO single sign-on (SSO) enabled subscription. Please contact [WEDO Client support team](mailto:info@wedo.swiss) to get a SSO subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* WEDO supports **SP and IDP** initiated SSO.
* WEDO supports [Automated user provisioning](wedo-provisioning-tutorial.md).

## Add WEDO from the gallery

To configure the integration of WEDO into Microsoft Entra ID, you need to add WEDO from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **WEDO** in the search box.
1. Select **WEDO** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-wedo'></a>

## Configure and test Microsoft Entra SSO for WEDO

Configure and test Microsoft Entra SSO with WEDO using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in WEDO.

To configure and test Microsoft Entra SSO with WEDO, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure WEDO SSO](#configure-wedo-sso)** - to configure the single sign-on settings on application side.
    1. **[Create WEDO test user](#create-wedo-test-user)** - to have a counterpart of B.Simon in WEDO that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **WEDO** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, if you wish to configure the application in **IDP** initiated mode, perform the following steps:

    a. In the **Identifier** text box, type a URL using the following pattern:
    `https://<SUBDOMAIN>.wedo.swiss/sp/acs`

    b. In the **Reply URL** text box, type a URL using the following pattern:
    `https://<SUBDOMAIN>.wedo.swiss/sp/acs`

1. Select **Set additional URLs** and perform the following step if you wish to configure the application in **SP** initiated mode:

    In the **Sign-on URL** text box, type a URL using the following pattern:
    `https://<SUBDOMAIN>.wedo.swiss/`

	> [!NOTE]
	> These values aren't real. Update these values with the actual Identifier, Reply URL and Sign-on URL. Contact [WEDO Client support team](mailto:info@wedo.swiss) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. WEDO application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	| Name | Source Attribute|
	| ------------ | --------- |
	| email | user.email |
	| firstName | user.firstName |
    | lastName | user.lastName |
	| userName | user.userName |

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section,  find **Federation Metadata XML** and select **Download** to download the certificate and save it on your computer.

	![The Certificate download link](common/metadataxml.png)

1. On the **Set up WEDO** section, copy the appropriate URL(s) based on your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure WEDO SSO

Follow these steps to enable Microsoft Entra SSO in WEDO.

1. Log in [WEDO](https://login.wedo.swiss/). You need to have **administrator role**.
1. In the Profile settings, select the menu **Authentication** in the section **Network settings**.
1. On the **SAML Authentication** page, perform the following steps:

   ![SAML Authentication link](media/wedo-tutorial/network-security-authentification.png)

   a. Enable **SAML Authentication**.

   b. Select the **Identity Provider metadata (XML)** tab.

   c. Open the downloaded **Federation Metadata XML** from Azure portal into Notepad and copy the content of metadata XML and paste it into **X.509 Certificate** textbox.

   d. Select **Save**.

### Create WEDO test user

In this section, you create a test user in WEDO called Bob Simon. Information must matches from **Create a Microsoft Entra test user**.

1. From the Profile setting in WEDO, select **Users** from **Network settings** section.
1. Select **Add user**.
1. In the Add user pop-up, fill the user's information

    a. First name `B`.

    b. Last name `Simon`.

    c. Enter the email `username@companydomain.extension`. For example, `B.Simon@contoso.com`. It's mandatory to have email with the same domain as your company short name.

    d. User type `User`.

    e. Select **Create user**.

    f. In the **Select teams** page, select **Save**.

    g.  In the **Invite user** page, select **Yes**.

1. Validate the user using the link you received by email

> [!NOTE]
> If you want to create a fake user (email above doesn't exist in your network), contact [our support](mailto:info@wedo.swiss) to validate the user*.

> [!NOTE]
> WEDO also supports automatic user provisioning, you can find more details [here](./wedo-provisioning-tutorial.md) on how to configure automatic user provisioning.

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with the following options. 

#### SP initiated:

* Select **Test this application** in Azure portal. this option redirects to WEDO Sign on URL where you can initiate the login flow.  

* Go to WEDO Sign-on URL directly and initiate the login flow from there.

#### IDP initiated:

* Select **Test this application** and you should be automatically signed in to the WEDO for which you set up the SSO. 

You can also use Microsoft My Apps to test the application in any mode. When you select the WEDO tile in the My Apps, if configured in SP mode you would be redirected to the application sign on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the WEDO for which you set up the SSO. For more information, see [Microsoft Entra My Apps](/azure/active-directory/manage-apps/end-user-experiences#azure-ad-my-apps).

## Related content

Once you configure WEDO you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).
