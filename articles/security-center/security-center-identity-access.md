---
title: Monitor identity and access in Azure Security Center | Microsoft Docs
description: Learn how to use the identity and access capability in Azure Security Center to monitor your users' access activity and identity-related issues.
services: security-center
documentationcenter: na
author: TerryLanfear
manager: mbaldwin
editor: ''

ms.assetid: 9f04e730-4cfa-4078-8eec-905a443133da
ms.service: security-center
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/14/2018
ms.author: terrylan

---
# Monitor identity and access in Azure Security Center (Preview)
This article helps you use Azure Security Center to monitor users' identity and access activity.

> [!NOTE]
> Monitoring identity and access is in preview and available only on the Standard tier of Security Center. See [Pricing](security-center-pricing.md) to learn more about Security Center's pricing tiers.
>
>

Identity should be the control plane for your enterprise, and protecting your identity should be your top priority. The security perimeter has evolved from a network perimeter to an identity perimeter. Security becomes less about defending your network and more about defending your data, as well as managing the security of your apps and users. Nowadays, with more data and more apps moving to the cloud, identity becomes the new perimeter.

By monitoring identity activities, you can take proactive actions before an incident takes place or reactive actions to stop an attack attempt. The Identity & Access dashboard provides you with recommendations such as:

- Enable MFA for privileged accounts on your subscription
- Remove external accounts with write permissions from your subscription
- Remove privileged external accounts from your subscription

> [!NOTE]
> If your subscription has more than 250 accounts, Security Center is unable to run the Identity recommendations against your subscription. Recommendations that are not run are listed under “unavailable assessments” which is discussed below.
Security Center is unable to run the Identity recommendations against a Cloud Solution Provider (CSP) partner's admin agents.
>
>

See [Recommendations](security-center-identity-access.md#recommendations) for a list of the Identity and Access recommendations provided by Security Center.

## Monitoring security health
You can monitor the security state of your resources on the **Security Center – Overview** dashboard. The **Resources** section is a health indicator showing the severities for each resource type.

You can view a list of all issues by selecting **Recommendations**. Under **Resources**, you can view a list of issues specific to compute & apps, data security, networking, or identity & access. For more information about how to apply recommendations, see [Implementing security recommendations in Azure Security Center](security-center-recommendations.md).

For a complete list of Identity and Access recommendations, see [recommendations](security-center-identity-access.md#recommendations).

To continue, select **Identity & access** under **Resources** or the Security Center main menu.

![Security Center dashboard][1]

## Monitor identity and access
Under **Identity & Access**, there are two tabs:

- **Overview**: recommendations identified by Security Center.
- **Subscriptions**: list of your subscriptions and current security state of each.

![Identity & Access][2]

### Overview section
Under **Overview**, there is a list of recommendations. The first column lists the recommendation. The second column shows the total number of subscriptions that are affected by that recommendation. The third column shows the severity of the issue.

1. Select a recommendation. The recommendation’s window opens and displays:

  - Description of the recommendation
  - List of unhealthy and healthy subscriptions
  - List of resources that are unscanned due to a failed assessment or the resource is under a subscription running on the Free tier and is not assessed

  ![Recommendation's window][3]

2. Select a subscription in the list for additional detail.

### Subscriptions section
Under **Subscriptions**, there is a list of subscriptions. The first column lists the subscriptions. The second column shows the total number of recommendations for each subscription. The third column shows the severities of the issues.

![Subscription's tab][4]

1.	Select a subscription. A summary view opens with three tabs:

  - **Recommendations**:  based on assessments performed by Security Center that failed.
  - **Passed assessments**: list of assessments performed by Security Center that passed.
  - **Unavailable assessments**: list of assessments that failed to run due to an error or because the subscription has more than 250 accounts.

  Under **Recommendations** is a list of the recommendations for the selected subscription and severity of each recommendation.

  ![Recommendations for select subscription][5]

2. Select a recommendation for a description of the recommendation, a list of unhealthy and healthy subscriptions, and a list of unscanned resources.

  ![Description of recommendation][6]

  Under **Passed assessments** is a list of passed assessments.  Severity of these assessments is always green.

  ![Passed assessments][7]

3. Select a passed assessment from the list for a description of the assessment and a list of healthy subscriptions. There is a tab for unhealthy subscriptions that lists all the subscriptions that failed.

  ![Passed assessments][8]

## Recommendations
Use the table below as a reference to help you understand the available Identity & Access recommendations and what each one does if you apply it.

| Recommendation | Description |
| --- | --- |
| Designate more than one owner on your subscription | Recommends that you designate more than one subscription owner in order to have administrator access redundancy. |
| Designate up to 3 owners on your subscription | Recommends that you designate less than 3 subscription owners in order to reduce the potential for breach by a compromised owner. |
| Enable MFA for accounts with owner permissions on your subscription | Recommends that you enable Multi-Factor Authentication (MFA) for all subscription accounts with administrator privileges to prevent a breach of accounts or resources. |
| Enable MFA for accounts with write permissions on your subscription | Recommends that you enable Multi-Factor Authentication (MFA) for all subscription accounts with write privileges to prevent a breach of accounts or resources. |
| Enable MFA for accounts with read permissions on your subscription | Recommends that you enable Multi-Factor Authentication (MFA) for all subscription accounts with read privileges to prevent a breach of accounts or resources. |
| Remove external accounts with read permissions from your subscription | Recommends that you remove external accounts with read privileges from your subscription in order to prevent unmonitored access. |
| Remove external accounts with write permissions from your subscription | Recommends that you remove external accounts with write privileges from your subscription in order to prevent unmonitored access. |
| Remove external accounts with owner permissions from your subscription | Recommends that you remove external accounts with owner permissions from your subscription in order to prevent unmonitored access. |
| Remove deprecated accounts from subscription | Recommends that you remove deprecated accounts from your subscriptions. |
| Remove deprecated accounts with owner permissions from subscription | Recommends that you remove deprecated accounts with owner permissions from your subscriptions. |

## Next steps
To learn more about recommendations that apply to other Azure resource types, see the following:

- [Protecting your machines and applications in Azure Security Center](security-center-virtual-machine-recommendations.md)
- [Protecting your network in Azure Security Center](security-center-network-recommendations.md)
- [Protecting your Azure SQL service and data in Azure Security Center](security-center-sql-service-recommendations.md)

To learn more about Security Center, see the following:
* [Manage and respond to security alerts in Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-managing-and-responding-alerts). Learn how to manage alerts and respond to security incidents in Security Center.
* [Understand security alerts in Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-alerts-type). Learn about the different types of security alerts.
* [Azure Security Center FAQ](security-center-faq.md). Find answers to frequently asked questions about using Security Center.


<!--Image references-->
[1]: ./media/security-center-identity-access/overview.png
[2]: ./media/security-center-identity-access/identity-dashboard.png
[3]: ./media/security-center-identity-access/select-subscription.png
[4]: ./media/security-center-identity-access/subscriptions.png
[5]: ./media/security-center-identity-access/recommendations.png
[6]: ./media/security-center-identity-access/designate.png
[7]: ./media/security-center-identity-access/passed-assessments.png
[8]: ./media/security-center-identity-access/remove.png
