---
title: Configure TeamSlide for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and TeamSlide.
author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps
ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu
ms.custom: sfi-image-nochange
# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and TeamSlide so that I can control who has access to TeamSlide, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure TeamSlide for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate TeamSlide with Microsoft Entra ID. When you integrate TeamSlide with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to TeamSlide.
* Enable your users to be automatically signed-in to TeamSlide with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

To get started, you need the following items:

* A Microsoft Entra subscription. If you don't have a subscription, you can get a [free account](https://azure.microsoft.com/free/).
* TeamSlide single sign-on (SSO) enabled subscription.
* Along with Cloud Application Administrator, Application Administrator can also add or manage applications in Microsoft Entra ID.
For more information, see [Azure built-in roles](~/identity/role-based-access-control/permissions-reference.md).

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* TeamSlide supports **SP** initiated SSO.
* TeamSlide supports **Just In Time** user provisioning.

> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Add TeamSlide from the gallery

To configure the integration of TeamSlide into Microsoft Entra ID, you need to add TeamSlide from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **TeamSlide** in the search box.
1. Select **TeamSlide** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-teamslide'></a>

## Configure and test Microsoft Entra SSO for TeamSlide

Configure and test Microsoft Entra SSO with TeamSlide using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in TeamSlide.

To configure and test Microsoft Entra SSO with TeamSlide, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure TeamSlide SSO](#configure-teamslide-sso)** - to configure the single sign-on settings on application side.
    1. **[Create TeamSlide test user](#create-teamslide-test-user)** - to have a counterpart of B.Simon in TeamSlide that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **TeamSlide** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

  ![Screenshot shows to edit Basic SAML Configuration.](common/edit-urls.png "Basic Configuration")

1. On the **Basic SAML Configuration** section, perform the following steps:

    a. In the **Identifier** textbox, type the URL:
    `https://www.teamslide.io/AuthServices/`

    b. In the **Reply URL** textbox, type the URL:
    `https://www.teamslide.io/AuthServices/Acs` 

    c. In the **Sign-on URL** text box, type a URL using the following pattern:
    `https://www.teamslide.io/ChooseSso?domain=<CustomerDomain>`

    > [!NOTE]
	> The Sign-on URL isn't real. Update the value with the actual Sign-on URL. Contact [TeamSlide Client support team](mailto:support@aploris.com) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. TeamSlide application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

    ![Screenshot showing the list of default attributes.](common/default-attributes.png)

1. In addition to above, TeamSlide application expects few more attributes to be passed back in SAML response, which are shown below. These attributes are also pre populated but you can review them as per your requirements.

    | Name | Source Attribute|
    | ------------ | --------- |
    | displayname | user.displayname |
    | groups | user.groups [All] |
   
1. On the **Set up single sign-on with SAML** page, In the **SAML Signing Certificate** section, select copy button to copy **App Federation Metadata Url** and save it on your computer.

	![Screenshot showing the Certificate download link](common/copy-metadataurl.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure TeamSlide SSO

1. Log in to your TeamSlide company site as an administrator.

1. Go to **Global Settings** > **SSO Settings** tab.

1. In the **Single sign-on settings** page, perform the following steps:

    ![Screenshot that shows the Configuration Settings.](./media/teamslide-tutorial/settings.png "Configuration")

    a. In the **Entity ID** textbox, paste the **Microsoft Entra Identifier** value which you copied previously.

    b. In the **Sign-On URL** textbox, paste the **Login URL** value which you copied previously.

    c. In the **Metadata location** textbox, paste the **App Federation Metadata Url** value which you copied previously.

    d. Select **Save Changes**.

### Create TeamSlide test user

In this section, a user called B.Simon is created in TeamSlide. TeamSlide supports just-in-time user provisioning, which is enabled by default. There's no action item for you in this section. If a user doesn't already exist in TeamSlide, a new one is created after authentication.

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**, this option redirects to TeamSlide Sign-on URL where you can initiate the login flow. 

* Go to TeamSlide Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you select the TeamSlide tile in the My Apps, this option redirects to TeamSlide Sign-on URL. For more information, see [Microsoft Entra My Apps](/azure/active-directory/manage-apps/end-user-experiences#azure-ad-my-apps).

## Related content

Once you configure TeamSlide you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Cloud App Security](/cloud-app-security/proxy-deployment-aad).
