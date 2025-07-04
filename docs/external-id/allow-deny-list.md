---
title: Allow or Block Invitations
description: Learn how an administrator creates a list to allow or block B2B collaboration with specific domains by using the Microsoft Entra admin center.

 
ms.service: entra-external-id
ms.topic: how-to
ms.date: 04/16/2025

ms.author: cmulligan
author: csmulligan
manager: dougeby
ms.custom: it-pro, seo-july-2024
ms.collection: M365-identity-device-management
#customer intent: As an IT admin managing B2B collaboration, I want to configure an allowlist or blocklist for specific organizations, so that I can control  where B2B invitations can be sent by users in my organization.
---

# Allow or block B2B collaboration with organizations

[!INCLUDE [applies-to-workforce-only](./includes/applies-to-workforce-only.md)]

You can use an allowlist or a blocklist to allow or block invitations to B2B collaboration users from specific organizations. For example, if you want to block personal email address domains, you can set up a blocklist that contains domains like Gmail.com and Outlook.com. Or, if your business has a partnership with other businesses like Contoso.com, Fabrikam.com, and Litware.com, and you want to restrict invitations to only these organizations, you can add Contoso.com, Fabrikam.com, and Litware.com to your allowlist. 

This article discusses two ways to configure an allow or blocklist for B2B collaboration:

- In the portal by configuring collaboration restrictions in your organization's [External collaboration settings](external-collaboration-settings-configure.md)

## Important considerations

- You can create either an allowlist or a blocklist. You can't set up both types of lists. By default, whatever domains aren't in the allowlist are on the blocklist, and vice versa. 
- You can create only one policy per organization. You can update the policy to include more domains, or you can delete the policy to create a new one. 
- The number of domains you can add to an allowlist or blocklist is limited only by the size of the policy. This limit applies to the number of characters, so you can have a greater number of shorter domains or fewer longer domains. The maximum size of the entire policy is 25 KB (25,000 characters), which includes the allowlist or blocklist and any other parameters configured for other features.
- This list works independently from OneDrive and SharePoint Online allow/block lists. If you want to restrict individual file sharing in SharePoint Online, you need to set up an allow or blocklist for OneDrive and SharePoint Online. For more information, see [Restrict sharing of SharePoint and OneDrive content by domain](https://support.office.com/article/restricted-domains-sharing-in-sharepoint-online-and-onedrive-for-business-5d7589cd-0997-4a00-a2ba-2320ec49c4e9).
- The list doesn't apply to external users who already redeemed the invitation. The list will be enforced after the list is set up. If a user invitation is in a pending state, and you set a policy that blocks their domain, the user's attempt to redeem the invitation fails.
- Both allow/block list and cross-tenant access settings are checked at the time of invitation.

## Set the allow or blocklist policy in the portal

By default, the **Allow invitations to be sent to any domain (most inclusive)** setting is enabled. In this case, you can invite B2B users from any organization.

[!INCLUDE [least-privilege-note](../includes/definitions/least-privilege-note.md)]

### Add a blocklist


This is the most typical scenario, where your organization wants to work with almost any organization, but wants to prevent users from specific domains to be invited as B2B users.

To add a blocklist:

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as a [Global Administrator](/entra/identity/role-based-access-control/permissions-reference#global-administrator).


1. Browse to **Entra ID** > **External Identities** > **External collaboration settings**.

1. Under **Collaboration restrictions**, select **Deny invitations to the specified domains**.

1. Under **Target domains**, enter the name of one of the domains that you want to block. For multiple domains, enter each domain on a new line. For example:

    :::image type="content" source="media/allow-deny-list/deny-list-settings.png" alt-text="Screenshot showing the option to deny with added domains.":::
 
1. When you're done, select **Save**.

After you set the policy, if you try to invite a user from a blocked domain, you receive a message saying that the domain of the user is currently blocked by your invitation policy.
 
### Add an allowlist

With this more restrictive configuration, you can set specific domains in the allowlist and restrict invitations to any other organizations or domains that aren't mentioned.

If you want to use an allowlist, make sure that you spend time to fully evaluate what your business needs are. If you make this policy too restrictive, your users can choose to send documents over email, or find other non-IT sanctioned ways of collaborating.


To add an allowlist:

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as a [Global Administrator](/entra/identity/role-based-access-control/permissions-reference#global-administrator).
1. Browse to **Entra ID** > **External Identities** > **External collaboration settings**.
4. Under **Collaboration restrictions**, select **Allow invitations only to the specified domains (most restrictive)**.
5. Under **Target domains**, enter the name of one of the domains that you want to allow. For multiple domains, enter each domain on a new line. For example:

    :::image type="content" source="media/allow-deny-list/allow-list-settings.png" alt-text="Screenshot showing the allow option with added domains.":::
 
6. When you're done, select **Save**.

After you set the policy, if you try to invite a user from a domain that's not on the allowlist, you receive a message saying that the domain of the user is currently blocked by your invitation policy.

### Switch from allowlist to blocklist and vice versa 

Switching from one policy to another discards the existing policy configuration. Make sure to back up details of your configuration before you perform the switch. 


## Next steps

- [Cross-tenant access settings](cross-tenant-access-settings-b2b-collaboration.yml)
- [External collaboration settings](external-collaboration-settings-configure.md).
