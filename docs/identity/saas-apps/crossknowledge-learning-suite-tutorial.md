---
title: Configure CrossKnowledge Learning Suite for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and CrossKnowledge Learning Suite.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and CrossKnowledge Learning Suite so that I can control who has access to CrossKnowledge Learning Suite, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure CrossKnowledge Learning Suite for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate CrossKnowledge Learning Suite with Microsoft Entra ID. When you integrate CrossKnowledge Learning Suite with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to CrossKnowledge Learning Suite.
* Enable your users to be automatically signed-in to CrossKnowledge Learning Suite with their Microsoft Entra accounts.
* Manage your accounts in one central location.

To learn more about SaaS app integration with Microsoft Entra ID, see [What is application access and single sign-on with Microsoft Entra ID](~/identity/enterprise-apps/what-is-single-sign-on.md).

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* CrossKnowledge Learning Suite single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* CrossKnowledge Learning Suite supports **SP and IDP** initiated SSO
* Once you configure CrossKnowledge Learning Suite you can enforce session control, which protect exfiltration and infiltration of your organization’s sensitive data in real-time. Session control extend from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).

## Adding CrossKnowledge Learning Suite from the gallery

To configure the integration of CrossKnowledge Learning Suite into Microsoft Entra ID, you need to add CrossKnowledge Learning Suite from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **CrossKnowledge Learning Suite** in the search box.
1. Select **CrossKnowledge Learning Suite** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 [!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]

<a name='configure-and-test-azure-ad-single-sign-on-for-crossknowledge-learning-suite'></a>

## Configure and test Microsoft Entra single sign-on for CrossKnowledge Learning Suite

Configure and test Microsoft Entra SSO with CrossKnowledge Learning Suite using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in CrossKnowledge Learning Suite.

To configure and test Microsoft Entra SSO with CrossKnowledge Learning Suite, complete the following building blocks:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    * **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    * **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure CrossKnowledge Learning Suite SSO](#configure-crossknowledge-learning-suite-sso)** - to configure the single sign-on settings on application side.
    * **[Create CrossKnowledge Learning Suite test user](#create-crossknowledge-learning-suite-test-user)** - to have a counterpart of B.Simon in CrossKnowledge Learning Suite that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **CrossKnowledge Learning Suite** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the edit/pen icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, if you wish to configure the application in **IDP** initiated mode, enter the values for the following fields:

    a. In the **Identifier** text box, type a URL using the following pattern:
    `https://<domain-name>.<region>.crossknowledge.com/libs/simplesaml/www/module.php/saml/sp/metadata.php/SAML2-{driver-number}`

    b. In the **Reply URL** text box, type a URL using the following pattern:
    `https://<domain-name>.<region>.crossknowledge.com/libs/simplesaml/www/module.php/saml/sp/saml2-acs.php/SAML2-{driver-number}`

1. Select **Set additional URLs** and perform the following step if you wish to configure the application in **SP** initiated mode:

    In the **Sign-on URL** text box, type a URL using the following pattern:
    `https://<domain-name>.<region>.crossknowledge.com/libs/simplesaml/www/module.php/saml/sp/saml2-acs.php/SAML2-{driver-number}`

	> [!NOTE]
	> These values aren't real. Update these values with the actual Identifier, Reply URL and Sign-on URL. Contact [CrossKnowledge Learning Suite Client support team](mailto:support@crossknowledge.com) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section,  find **Federation Metadata XML** and select **Download** to download the certificate and save it on your computer.

	![The Certificate download link](common/metadataxml.png)

1. On the **Set up CrossKnowledge Learning Suite** section, copy the appropriate URL(s) based on your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure CrossKnowledge Learning Suite SSO

To configure single sign-on on **CrossKnowledge Learning Suite** side, you need to send the downloaded **Federation Metadata XML** and appropriate copied URLs from the application configuration to [CrossKnowledge Learning Suite support team](mailto:support@crossknowledge.com). They set this setting to have the SAML SSO connection set properly on both sides.

### Create CrossKnowledge Learning Suite test user

In this section, you create a user called B.Simon in CrossKnowledge Learning Suite. Work with [CrossKnowledge Learning Suite support team](mailto:support@crossknowledge.com) to add the users in the CrossKnowledge Learning Suite platform. Users must be created and activated before you use single sign-on.

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration using the Access Panel.

When you select the CrossKnowledge Learning Suite tile in the Access Panel, you should be automatically signed in to the CrossKnowledge Learning Suite for which you set up SSO. For more information about the Access Panel, see [Introduction to the Access Panel](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Additional resources

- [List of articles on How to Integrate SaaS Apps with Microsoft Entra ID](./tutorial-list.md)

- [What is application access and single sign-on with Microsoft Entra ID?](~/identity/enterprise-apps/what-is-single-sign-on.md)

- [What is Conditional Access in Microsoft Entra ID?](~/identity/conditional-access/overview.md)

- [What is session control in Microsoft Defender for Cloud Apps?](/cloud-app-security/proxy-intro-aad)

- [How to protect CrossKnowledge Learning Suite with advanced visibility and controls](/cloud-app-security/proxy-intro-aad)
