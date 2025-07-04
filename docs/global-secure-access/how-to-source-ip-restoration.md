---
title: Enable Source IP Restoration with Global Secure Access
description: Learn how to enable source IP restoration to ensure the source IP matches in downstream resources.
ms.service: global-secure-access
ms.topic: how-to
ms.date: 02/21/2025
ms.author: kenwith
author: kenwith
manager: dougeby
ms.reviewer: alexpav
ai-usage: ai-assisted
ms.custom: sfi-image-nochange
---
# Source IP restoration

With a cloud based network proxy between users and their resources, the IP address that the resources see doesn't match the actual source IP address. In place of the end-users’ source IP, the resource endpoints see the cloud proxy as the source IP address. Customers with these cloud proxy solutions can't use this source IP information. 

Source IP restoration in Global Secure Access allows backward compatibility for Microsoft Entra customers to continue using original user Source IP (public egress IP address). Administrators can benefit from the following capabilities:

- Continue to enforce Source IP-based location policies across both [Conditional Access](/azure/active-directory/conditional-access/overview) and [continuous access evaluation](/azure/active-directory/conditional-access/concept-continuous-access-evaluation).
- [Microsoft Entra ID Protection risk detections](/entra/id-protection/concept-identity-protection-risks) get a consistent view of original user Source IP address for assessing various risk scores.
- Original user Source IP is also made available in [Microsoft Entra sign-in logs](/azure/active-directory/reports-monitoring/concept-all-sign-ins) and in [Microsoft Entra audit logs](/entra/identity/monitoring-health/concept-audit-logs)

## Prerequisites

* Administrators who interact with **Global Secure Access** features must have both of the following role assignments depending on the tasks they're performing.
   * The [Global Secure Access Administrator role](/azure/active-directory/roles/permissions-reference) role to manage the Global Secure Access features.
   * The [Conditional Access Administrator](/azure/active-directory/roles/permissions-reference#conditional-access-administrator) to create and interact with Conditional Access policies.
* The product requires licensing. For details, see the licensing section of [What is Global Secure Access](overview-what-is-global-secure-access.md). If needed, you can [purchase licenses or get trial licenses](https://aka.ms/azureadlicense).

### Known limitations

[!INCLUDE [known-limitations-include](../includes/known-limitations-include.md)]

## Enable Global Secure Access signaling for Conditional Access

To enable the required setting to allow source IP restoration, an administrator must take the following steps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as a [Global Secure Access Administrator](/azure/active-directory/roles/permissions-reference#global-secure-access-administrator).
1. Browse to **Global Secure Access** > **Settings** > **Session management** > **Adaptive Access**.
1. Select the toggle to **Enable Global Secure Access signaling in Conditional Access**.

This functionality allows Entra ID and Microsoft Graph to receive the public egress source IP address of the user.

:::image type="content" source="media/how-to-source-ip-restoration/toggle-enable-signaling-in-conditional-access.png" alt-text="Screenshot showing the toggle to enable signaling in Conditional Access.":::

> [!CAUTION]
> If your organization has active Conditional Access policies based on IP location checks, and you disable Global Secure Access signaling in Conditional Access, you may unintentionally block targeted end-users from being able to access the resources. If you must disable this feature, first delete any corresponding Conditional Access policies. 

## Sign-in log behavior

To see source IP restoration in action, administrators can take the following steps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Security Reader](/azure/active-directory/roles/permissions-reference#security-reader).
1. Browse to **Entra ID** > **Users** > select one of your test users > **Sign-in logs**.
1. With source IP restoration enabled, you see IP addresses that include their actual IP address. 
   - If source IP restoration is disabled, you can't see their actual IP address.

Sign-in log data might take some time to appear this delay is normal as there's some processing that must take place.

:::image type="content" source="media/how-to-source-ip-restoration/sign-in-logs-enabled-disabled.png" alt-text="Screenshot of the sign-in logs showing events with source IP restoration on, then off, then on again." lightbox="media/how-to-source-ip-restoration/sign-in-logs-enabled-disabled.png":::



## Related content

- [Set up tenant restrictions v2 (preview)](/azure/active-directory/external-identities/tenant-restrictions-v2)
- [Enable compliant network check with Conditional Access](how-to-compliant-network.md)
- [Strictly enforce location policies using continuous access evaluation](../identity/conditional-access/concept-continuous-access-evaluation-strict-enforcement.md)
