---
title: Configure iPass SmartConnect for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and iPass SmartConnect.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and iPass SmartConnect so that I can control who has access to iPass SmartConnect, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure iPass SmartConnect for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate iPass SmartConnect with Microsoft Entra ID. When you integrate iPass SmartConnect with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to iPass SmartConnect.
* Enable your users to be automatically signed-in to iPass SmartConnect with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* iPass SmartConnect single sign-on (SSO) enabled subscription.

> [!NOTE]
> This integration is also available to use from Microsoft Entra US Government Cloud environment. You can find this application in the Microsoft Entra US Government Cloud Application Gallery and configure it in the same way as you do from public cloud.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* iPass SmartConnect supports **SP and IDP** initiated SSO.
* iPass SmartConnect supports **Just In Time** user provisioning.
* iPass SmartConnect supports [Automated user provisioning](ipass-smartconnect-provisioning-tutorial.md).


> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Adding iPass SmartConnect from the gallery

To configure the integration of iPass SmartConnect into Microsoft Entra ID, you need to add iPass SmartConnect from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **iPass SmartConnect** in the search box.
1. Select **iPass SmartConnect** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-ipass-smartconnect'></a>

## Configure and test Microsoft Entra SSO for iPass SmartConnect

Configure and test Microsoft Entra SSO with iPass SmartConnect using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in iPass SmartConnect.

To configure and test Microsoft Entra SSO with iPass SmartConnect, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure iPass SmartConnect SSO](#configure-ipass-smartconnect-sso)** - to configure the single sign-on settings on application side.
    1. **[Create iPass SmartConnect test user](#create-ipass-smartconnect-test-user)** - to have a counterpart of B.Simon in iPass SmartConnect that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **iPass SmartConnect** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, if you wish to configure the application in **IDP** initiated mode, the user doesn't have to perform any step as the app is already pre-integrated with Azure.

1. Select **Set additional URLs** and perform the following step if you wish to configure the application in **SP** initiated mode:

    In the **Sign-on URL** text box, type a URL:
    `https://om-activation.ipass.com/ClientActivation/ssolanding.go`

1. Select **Save**.

1. iPass SmartConnect application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	![image](common/default-attributes.png)

1. In addition to above, iPass SmartConnect application expects few more attributes to be passed back in SAML response which are shown below. These attributes are also pre populated but you can review them as per your requirements.

	| Name |  Source Attribute|
	| ---------------| ----------|
	| firstName | user.givenname |
	| lastName | user.surname |
	| email | user.userprincipalname |
	| username | user.userprincipalname |

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section,  find **Federation Metadata XML** and select **Download** to download the certificate and save it on your computer.

	![The Certificate download link](common/metadataxml.png)

1. On the **Set up iPass SmartConnect** section, copy the appropriate URL(s) based on your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure iPass SmartConnect SSO

To configure single sign-on on **iPass SmartConnect** side, you need to send the downloaded **Federation Metadata XML** and appropriate copied URLs from the application configuration to [iPass SmartConnect support team](mailto:help@ipass.com). They set this setting to have the SAML SSO connection set properly on both sides.

### Create iPass SmartConnect test user

In this section, you create a user called Britta Simon in iPass SmartConnect. Work with [iPass SmartConnect support team](mailto:help@ipass.com) to add the users or the domain that must be added to an allow list for the iPass SmartConnect platform. If the domain is added by the team, users get automatically provisioned to the iPass SmartConnect platform. Users must be created and activated before you use single sign-on.

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with following options.

#### SP initiated:

* Select **Test this application**, this option redirects to iPass SmartConnect Sign on URL where you can initiate the login flow.

* Go to iPass SmartConnect Sign-on URL directly and initiate the login flow from there.

#### IDP initiated:

* Select **Test this application**, and you should be automatically signed in to the iPass SmartConnect for which you set up the SSO

You can also use Microsoft My Apps to test the application in any mode. When you select the iPass SmartConnect tile in the My Apps, if configured in SP mode you would be redirected to the application sign on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the iPass SmartConnect for which you set up the SSO. For more information, see [Microsoft Entra My Apps](/azure/active-directory/manage-apps/end-user-experiences#azure-ad-my-apps).

## Related content

Once you configure iPass SmartConnect you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).
