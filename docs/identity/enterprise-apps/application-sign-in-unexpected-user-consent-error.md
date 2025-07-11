---
title: Unexpected error when performing consent to an application
description: This article discusses errors that can occur during the process of consenting to an application and what you can do about them.

author: omondiatieno
manager: mwongerapk
ms.service: entra-id
ms.subservice: enterprise-apps

ms.topic: troubleshooting
ms.date: 02/27/2025
ms.author: jomondi
ms.reviewer: phsignor
ms.collection: M365-identity-device-management
ms.custom: enterprise-apps

#customer intent: As an IT admin troubleshooting issues with user access to Microsoft applications, I want to understand and troubleshoot errors that occur during the process of consenting to an application, so that I can successfully grant the necessary permissions and access the application.
---

# Unexpected error when performing consent to an application

This article discusses errors that can occur during the process of consenting to an application. If you're troubleshooting unexpected consent prompts that don't contain any error messages, see [Authentication Scenarios for Microsoft Entra ID](~/identity-platform/authentication-vs-authorization.md).

Many applications that integrate with Microsoft Entra ID require permissions to access other resources in order to function. When these resources are also integrated with Microsoft Entra ID, the permission to access them is often requested using the common consent framework. A consent prompt is displayed, which generally occurs the first time an application is in use. It can also occur on a subsequent use of the application.

Certain conditions must be true for a user to consent to the permissions an application requires. If these conditions aren't met, the following errors can occur.

## Requesting not authorized permissions error

- **AADSTS90093:** `clientAppDisplayName` is requesting one or more permissions that you aren't authorized to grant. Contact an administrator, who can consent to this application on your behalf.
- **AADSTS90094:** `clientAppDisplayName` needs permission to access resources in your organization that only an admin can grant. Ask an admin to grant permission to this app before you can use it.

This error occurs when a user who isn't an administrator attempts to use an application that is requesting permissions that only an administrator can grant. To resolve this error, an administrator should grant access to the application on behalf of their organization.

This error can also occur when a user is prevented from consenting to an application due to Microsoft detecting that the permissions request is risky. In this case, an audit event is also logged with a category of **ApplicationManagement**, Activity Type of **Consent to application** and Status Reason of **Risky application detected**.

Another scenario in which this error might occur is when the user assignment is required for the application, but no administrator consent was provided. In this case, the administrator must first provide tenant-wide admin consent for the application.

## Policy prevents granting permissions error

- **AADSTS90093:** An administrator of `tenantDisplayName` set a policy that prevents you from granting `name of app` the permissions it's requesting. Contact an administrator of `tenantDisplayName`, who can grant permissions to this app on your behalf.

This error occurs when an administrator turns off the ability for users to consent to applications. Then a nonadministrator user attempts to use an application that requires consent. To resolve this error, an administrator should grant access to the application on behalf of their organization.

## Intermittent problem error

- **AADSTS90090:** It looks like the sign-in process encountered an intermittent problem recording the permissions you attempted to grant to `clientAppDisplayName`. try again later.

This error indicates that an intermittent service side issue occurred. It can be resolved by attempting to consent to the application again.



## Resource not available in tenant error

- **AADSTS65005:** `clientAppDisplayName` is requesting access to a resource `resourceAppDisplayName` that isn't available in your organization `tenantDisplayName`.

Ensure that these resources that provide the permissions requested are available in your tenant or contact an administrator of `tenantDisplayName`. Otherwise, there's a misconfiguration in how the application requests resources, and you should contact the application developer.

## Permissions mismatch error

- **AADSTS65005:** The app requested consent to access resource `resourceAppDisplayName`. This request failed because it doesn't match how the app was preconfigured during app registration. Contact the app vendor.**

These errors occur when the app a user is trying to consent to requests permissions to access a resource application that can't be found in the organization’s directory (tenant). This situation can occur for several reasons:

- The client application developer configured their application incorrectly, causing it to request access to an invalid resource. In this case, the application developer must update the configuration of the client application to resolve this issue.

- A service principal representing the target resource application doesn't exist in the organization, or existed in the past but is removed. To resolve this issue, a service principal for the resource application must be provisioned in the organization so the client application can request permissions to it. The service principal can be provisioned in many ways, depending on the type of application, including:

- Acquiring a subscription for the resource application (Microsoft published applications)

- Consenting to the resource application

- Granting the application permissions via the Microsoft Entra admin center

- Adding the application from the Microsoft Entra Application Gallery

## Risky app error and warning

- **AADSTS900941:** Administrator consent is required. App is considered risky. (AdminConsentRequiredDueToRiskyApp)
- This app might be risky. If you trust this app, ask your admin to grant you access.
- **AADSTS900981:** An admin consent request was received for a risky app. (AdminConsentRequestRiskyAppWarning)
- This app might be risky. Only continue if you trust this app.

Both of these messages are displayed when Microsoft determines that the consent request might be risky. Among many other factors, this error might occur if a [verified publisher](~/identity-platform/publisher-verification-overview.md) isn't added to the app registration. The first error code and message is shown to end-users when the [Admin consent workflow](configure-admin-consent-workflow.md) is disabled. The second code and message is shown to end-users when the admin consent workflow is enabled and to admins.

End-users aren't able to grant consent to apps that are detected as risky. Admins are able to, but should evaluate the app carefully and proceed with caution. If the app seems suspicious upon further review, it can be reported to Microsoft from the consent screen.

## Next steps


[Scopes, permissions, and consent in the Microsoft identity platform (v2.0 endpoint)](~/identity-platform/permissions-consent-overview.md)

[Unexpected consent prompt when signing in to an application](application-sign-in-unexpected-user-consent-prompt.md)
