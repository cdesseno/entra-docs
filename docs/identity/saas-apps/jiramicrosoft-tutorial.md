---
title: Configure JIRA SAML SSO by Microsoft for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and JIRA SAML SSO by Microsoft.
author: dhivyagana
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps
ms.topic: how-to
ms.date: 03/25/2025
ms.author: dhivyag
ms.custom: sfi-image-nochange
# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and JIRA SAML SSO by Microsoft so that I can control who has access to JIRA SAML SSO by Microsoft, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure JIRA SAML SSO by Microsoft for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate JIRA SAML SSO by Microsoft with Microsoft Entra ID. When you integrate JIRA SAML SSO by Microsoft with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to JIRA SAML SSO by Microsoft.
* Enable your users to be automatically signed-in to JIRA SAML SSO by Microsoft with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Description

Use your Microsoft Entra account with Atlassian JIRA server to enable single sign-on. This way all your organization users can use the Microsoft Entra credentials to sign in into the JIRA application. This plugin uses SAML 2.0 for federation.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
- JIRA Core and Software 7.0 to 10.5.1 or JIRA Service Desk 3.0 to 5.12.22 should be installed and configured on Windows 64-bit version.
- JIRA server is HTTPS enabled.
- Note the supported versions for JIRA Plugin are mentioned in below section.
- JIRA server is reachable on the Internet particularly to the Microsoft Entra login page for authentication and should able to receive the token from Microsoft Entra ID.
- Admin credentials are set up in JIRA.
- WebSudo is disabled in JIRA.
- Test user created in the JIRA server application.

> [!NOTE]
> To test the steps in this article,  we don't recommend using a production environment of JIRA. Test the integration first in development or staging environment of the application and then use the production environment.

To get started, you need the following items:

* don't use your production environment, unless it's necessary.
* JIRA SAML SSO by Microsoft single sign-on (SSO) enabled subscription.

> [!NOTE]
> This integration is also available to use from Microsoft Entra US Government Cloud environment. You can find this application in the Microsoft Entra US Government Cloud Application Gallery and configure it in the same way as you do from public cloud.

## Supported versions of JIRA

* JIRA Core and Software: 7.0 to 10.5.1.
* JIRA Service Desk 3.0 to 5.12.22.
* JIRA also supports 5.2. For more details, select [Microsoft Entra single sign-on for JIRA 5.2](jira52microsoft-tutorial.md).

> [!NOTE]
> Please note that our JIRA Plugin also works on Ubuntu Version 16.04 and Linux.

## Microsoft SSO plugins

* [Microsoft Entra ID single sign-on for JIRA datacenter application](https://marketplace.atlassian.com/apps/1224430/microsoft-azure-active-directory-single-sign-on-for-jira?tab=overview&hosting=datacenter)

* [Microsoft Entra ID single sign-on for JIRA server-side application](https://www.microsoft.com/en-us/download/details.aspx?id=56506)


## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* JIRA SAML SSO by Microsoft supports **SP** initiated SSO.

## Adding JIRA SAML SSO by Microsoft from the gallery

To configure the integration of JIRA SAML SSO by Microsoft into Microsoft Entra ID, you need to add JIRA SAML SSO by Microsoft from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **JIRA SAML SSO by Microsoft** in the search box.
1. Select **JIRA SAML SSO by Microsoft** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-jira-saml-sso-by-microsoft'></a>

## Configure and test Microsoft Entra SSO for JIRA SAML SSO by Microsoft

Configure and test Microsoft Entra SSO with JIRA SAML SSO by Microsoft using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in JIRA SAML SSO by Microsoft.

To configure and test Microsoft Entra SSO with JIRA SAML SSO by Microsoft, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure JIRA SAML SSO by Microsoft SSO](#configure-jira-saml-sso-by-microsoft-sso)** - to configure the single sign-on settings on application side.
    1. **[Create JIRA SAML SSO by Microsoft test user](#create-jira-saml-sso-by-microsoft-test-user)** - to have a counterpart of B.Simon in JIRA SAML SSO by Microsoft that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **JIRA SAML SSO by Microsoft** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Screenshot shows how to edit Basic SAML Configuration.](common/edit-urls.png "Basic Configuration")

1. On the **Basic SAML Configuration** section, perform the following steps:

    a. In the **Identifier** box, type a URL using the following pattern:
    `https://<domain:port>/`

    b. In the **Reply URL** text box, type a URL using the following pattern:
    `https://<domain:port>/plugins/servlet/saml/auth`

	a. In the **Sign-on URL** text box, type a URL using the following pattern:
    `https://<domain:port>/plugins/servlet/saml/auth`

	> [!NOTE]
	> These values aren't real. Update these values with the actual Identifier, Reply URL, and Sign-on URL. Port is optional in case it’s a named URL. These values are received during the configuration of Jira plugin, which is explained later in the article.

1. On the **Set up single sign-on with SAML** page, In the **SAML Signing Certificate** section, select copy button to copy **App Federation Metadata Url** and save it on your computer.

	![Screenshot shows the Certificate download link.](common/copy-metadataurl.png "Certificate")

1. The Name ID attribute in Microsoft Entra ID can be mapped to any desired user attribute by editing the Attributes & Claims section.

   ![Screenshot showing how to edit Attributes and Claims.](common/edit-attribute.png)
	
    a. After selecting Edit, any desired user attribute can be mapped by selecting Unique User Identifier (Name ID).
    
   ![Screenshot showing the NameID in Attributes and Claims.](common/attribute-nameID.png)
	
    b. On the next screen, the desired attribute name like user.userprincipalname can be selected as an option from the Source Attribute dropdown menu.
    
   ![Screenshot showing how to select Attributes and Claims.](common/attribute-select.png)
	
    c. The selection can then be saved by selecting the Save button at the top.
    
   ![Screenshot showing how to save Attributes and Claims.](common/attribute-save.png)
	
    d. Now, the user.userprincipalname attribute source in Microsoft Entra ID is mapped to the Name ID attribute name in Microsoft Entra which is compared with the username attribute in Atlassian by the SSO plugin.
    
   ![Screenshot showing how to review Attributes and Claims.](common/attribute-review.png)
	
	> [!NOTE]
	> The SSO service provided by Microsoft Azure supports SAML authentication which is able to perform user identification using different attributes such as givenname (first name), surname (last name), email (email address), and user principal name (username). We recommend not to use email as an authentication attribute as email addresses aren't always verified by Microsoft Entra ID. The plugin compares the values of Atlassian username attribute with the NameID attribute in Microsoft Entra ID in order to determine the valid user authentication.

1. If your Azure tenant has **guest users** then follow the below configuration steps:
 
	a. Select **pencil** icon to go to the Attributes & Claims section.

	![Screenshot showing how to edit Attributes and Claims.](common/edit-attribute.png)

	b. Select **NameID** on Attributes & Claims section.

	![Screenshot showing the NameID in Attributes and Claims.](common/attribute-nameID.png)

	c. Setup the claim conditions based on the User Type.

	![Screenshot for claim conditions.](./media/jiramicrosoft-tutorial/claim-conditions.png)

	>[!NOTE]
	>  Give the NameID value as `user.userprincipalname` for Members and `user.mail` for External Guests.

	d. **Save** the changes and verify the SSO for external guest users.

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure JIRA SAML SSO by Microsoft SSO

1. In a different web browser window, sign in to your JIRA instance as an administrator.

2. Hover on cog and select the **Add-ons**.

	![Screenshot shows Add-ons selected from the Settings menu.](./media/jiramicrosoft-tutorial/addon1.png)

3. Download the plugin from [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=56506). Manually upload the plugin provided by Microsoft using **Upload add-on** menu. The download of plugin is covered under [Microsoft Service Agreement](https://www.microsoft.com/servicesagreement/).

	![Screenshot shows Manage add-ons with the Upload add-on link called out.](./media/jiramicrosoft-tutorial/addon12.png)

4. For running the JIRA reverse proxy scenario or load balancer scenario perform the following steps:

	> [!NOTE]
	> You should be configuring the server first with the below instructions and then install the plugin.

	a. Add below attribute in **connector** port in **server.xml** file of JIRA server application.

	`scheme="https" proxyName="<subdomain.domain.com>" proxyPort="<proxy_port>" secure="true"`

	![Screenshot shows the server dot x m l file in an editor with the new line added.](./media/jiramicrosoft-tutorial/reverseproxy1.png)

	b. Change **Base URL** in **System Settings** according to proxy/load balancer.

	![Screenshot shows the Administration Settings where you can change the Base U R L.](./media/jiramicrosoft-tutorial/reverseproxy2.png)

5. Once the plugin is installed, it appears in **User Installed** add-ons section of **Manage Add-on** section. Select **Configure** to configure the new plugin.

6. Perform following steps on configuration page:

	![Screenshot shows the Microsoft Entra single sign-on for Jira configuration page.](./media/jiramicrosoft-tutorial/sso-plugin-configuration-page.png)

	> [!TIP]
	> Ensure that there is only one certificate mapped against the app so that there is no error in resolving the metadata. If there are multiple certificates, upon resolving the metadata, admin gets an error.

	a. In the **Metadata URL** textbox, paste **App Federation Metadata Url** value which you have copied and select the **Resolve** button. It reads the IdP metadata URL and populates all the fields information.

	b. Copy the **Identifier, Reply URL and Sign on URL** values and paste them in **Identifier, Reply URL and Sign on URL** textboxes respectively in **JIRA SAML SSO by Microsoft Domain and URLs** section on Azure portal.

	c. In **Login Button Name** type the name of button your organization wants the users to see on login screen.
	
	d. In **Login Button Description** type the description of button your organization wants the users to see on login screen.

	e.  In **Default Group**, select your organization default group to assign to new users. Default groups facilitate organized access rights to new user accounts.

	f. In **SAML User ID Locations** select either **User ID is in the NameIdentifier element of the Subject statement** or **User ID is in an Attribute element**.  This ID has to be the JIRA user ID. If the user ID isn't matched, then the system doesn't allow users to sign in.

	> [!Note]
	> Default SAML User ID location is Name Identifier. You can change this to an attribute option and enter the appropriate attribute name.

	g. If you select **User ID is in an Attribute element**, then for **Attribute name**, type the name of the attribute where the user ID is expected.

	h.  In **Auto-create User** feature (JIT User Provisioning): It automates user account creation in authorized web applications, without the need for manual provisioning. This reduces administrative workload and increases productivity. Because JIT relies on the login response from Azure AD, enter the SAML-response attribute values, which include the user's email address, last name, and first name.


	i. If you're using the federated domain (like ADFS, and so on) with Microsoft Entra ID, then select the **Enable Home Realm Discovery** option and configure the **Domain Name**.

	j. In **Domain Name** type the domain name here in case of the ADFS-based login.

	k. Select **Enable Single Sign out** if you want to sign out of Microsoft Entra ID when a user signs out of JIRA.
	
	l. Enable **Force Azure Login** if you want to sign in by using only Microsoft Entra ID credentials.
	
	> [!Note]
	> To enable the default login form for admin login on login page when force azure login is enabled, add the query parameter in the browser URL.
	> `https://<domain:port>/login.jsp?force_azure_login=false`

	m. Select **Enable Use of Application Proxy** if you configured your on-premises Atlassian application in an application proxy setup.

	* For App proxy setup , follow the steps on the [Microsoft Entra application proxy Documentation](~/identity/app-proxy/overview-what-is-app-proxy.md).

	n. Select **Save** to save the settings.

	> [!NOTE]
	> For more information about installation and troubleshooting, visit [MS JIRA SSO Connector Admin Guide](./ms-confluence-jira-plugin-adminguide.md). There's also an [FAQ](./ms-confluence-jira-plugin-adminguide.md) for your assistance.

### Create JIRA SAML SSO by Microsoft test user

To enable Microsoft Entra users to sign in to JIRA on-premises server, they must be provisioned into JIRA SAML SSO by Microsoft. For JIRA SAML SSO by Microsoft, provisioning is a manual task.

**To provision a user account, perform the following steps:**

1. Sign in to your JIRA on-premises server as an administrator.

2. Hover on cog and select the **User management**.

    ![Screenshot shows User management selected from the Settings menu.](./media/jiramicrosoft-tutorial/user1.png)

3. You're redirected to Administrator Access page to enter **Password** and select **Confirm** button.

	![Screenshot shows Administrator Access page where you enter your credentials.](./media/jiramicrosoft-tutorial/user2.png)

4. Under **User management** tab section, select **create user**.

	![Screenshot shows the User management tab where you can Create user.](./media/jiramicrosoft-tutorial/user3.png) 

5. On the **“Create new user”** dialog page, perform the following steps:

	![Screenshot shows the Create new user dialog box where you can enter the information in this step.](./media/jiramicrosoft-tutorial/user4.png) 

	a. In the **Email address** textbox, type the email address of user like B.simon@contoso.com.

	b. In the **Full Name** textbox, type full name of the user like B.Simon.

	c. In the **Username** textbox, type the email of user like B.simon@contoso.com.

	d. In the **Password** textbox, type the password of user.

	e. Select **Create user**.

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**, this option redirects to JIRA SAML SSO by Microsoft Sign-on URL where you can initiate the login flow. 

* Go to JIRA SAML SSO by Microsoft Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you select the JIRA SAML SSO by Microsoft tile in the My Apps, this option redirects to JIRA SAML SSO by Microsoft Sign-on URL. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure JIRA SAML SSO by Microsoft you can enforce Session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).
