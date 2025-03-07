---
title: "View customer summary | MicrosoftDocs"
description: "Customer summary is a form where you can get complete information about the customer with whom you are going to interact."
keywords: ""
author: kabala123
ms.author: kabala
manager: shujoshi
applies_to: 
ms.date: 07/01/2019
ms.service: dynamics-365-customerservice
ms.topic: article
ms.assetid: D25BB656-E29F-4233-B5BB-ADF678CCD7D2
ms.custom: 
---

# View customer summary

Applies to Dynamics 365 for Customer Engagement apps version 9.1.0

One of the major challenges that customers face when contacting customer support is providing repetitive information about the issue with the support agent. Also, if the customer wants to review the status of the request later, the customer shares the same information with another support agent to explain the context of the engagement. To avoid this, the support agent needs access to customer information with details about the product/service, issue, case history, related cases, location, and so on.

Having this information ready when a customer contacts the support agent can reduce the hold time that the agent spends to retrieve the customer information, reduce the average handling time (AHT), and increase customer satisfaction with faster resolution of the issue.

## What is Customer summary?

Customer summary is a page that gives you complete information about a customer. The page appears when you accept an incoming request from any channel. The default Customer summary view provides the following sections:

 - Customer (Contact or Account)

 - Conversation summary

 - Case

 - Recent cases

 - Timeline

> [!div class='mx-imgBorder']
> ![View Customer summary](../../media/customer-summary.png "View Customer summary")

## Customer (Contact or Account)

This section provides details like the contact name or account name. For a contact, you can view the location, email, and any other details of the contact. For an account, you can view location, telephone number, and primary contact person for the account.

Use the customer form to search for an existing contact or account record in omnichannel and select the record to link it to the conversation. If the record doesn't exist, you can create a new contact or account record using the **+ Add Contact** or **+ Add Account** button respectively.  After you create, search the record and then select it to link to the conversation.

> [!div class='mx-imgBorder']
> ![Customer profile section in the customer summary form](../../media/customer-summary-customer-form.PNG "Customer profile section in the customer summary form")

## Conversation summary

This section provides two tabs with details that help you to understand the information about the conversation with the customer. **Pre-chat** and **Visitor info** are the tabs in the Conversation summary card. The **Pre-chat survey** tab displays the survey answers against the questions that are requested by your organization, which helps your interaction with the customer. The **Visitor details** tab provides some information such as whether the customer is authenticated or not, browser used by the customer for contacting support, operating system used by the customer, location of the customer, interacting language of the customer, and so on.

> [!div class='mx-imgBorder']
> ![Conversation summary section in the customer summary form](../../media/customer-summary-conversation-summary.png "Conversation summary section in the customer summary form")

If the customer signs in to the portal to initiate a chat with the support, then as an agent, you can see the **Authenticated** field value as **Yes** in the **Visitor details** tab of the **Conversation summary** section. Otherwise, the **Authenticated** field value is shown as **No**.

![Authenticated chat shows as Yes in the Visitor details tab of Conversation summary](../../media/conversation-summary-authenticated-chat.PNG "Authenticated chat shows as Yes in the Visitor details tab of Conversation summary") ![Unauthenticated chat shows as No in the Visitor details tab of Conversation summary](../../media/conversation-summary-unauthenticated-chat.PNG "Unauthenticated chat shows as Yes in the Visitor details tab of Conversation summary")

To learn more, see [Create chat authentication settings](../../administrator/create-chat-auth-settings.md)

## Case

Use the case form to search for an existing case in omnichannel and select the case to link it to the conversation. If the record doesn't exist, you can create a new case using the **+ Add Case** button.  After you create, search the record and then select it to link to the conversation.

> [!div class='mx-imgBorder']
> ![Case section in the customer summary form](../../media/customer-summary-issue-snapshot.PNG "Case section in the customer summary form")

## Recent cases

This section displays recent cases related to the customer.

> [!div class='mx-imgBorder']
> ![Recent cases section in the customer summary form](../../media/customer-summary-recent-cases.png "Recent cases section in the customer summary form")

## Timeline

This section displays case- and customer-related activities in the form of a timeline. You can create quick notes based on the discussion with the customer. Use the **Linked records** field to switch the timeline based on the Case, Contact, or Account record linked to the conversation.

> [!div class='mx-imgBorder']
> ![Recent activities section in the customer summary form](../../media/customer-summary-recent-activities.PNG "Recent activities section in the customer summary form")

The **Linked records** field drop-down shows the record that is linked to conversation. For example, if you link a contact and case to the conversation, the **Linked records** field drop-down shows **Contact** and **Case** respectively.


> [!div class='mx-imgBorder']
> ![View only the linked records in the drop-down](../../media/oceh/customer-summary-linked-records.PNG "View only the linked records in the drop-down")

> [!div class="nextstepaction"]
> [Next topic: Search for and share knowledge articles](oc-search-knowledge-articles.md)

## See also

- [View communication panel](oc-conversation-control.md)
- [Monitor real-time customer sentiment](oc-monitor-real-time-customer-sentiment-sessions.md)
- [View customer summary for an incoming conversation request](oc-view-customer-summary-incoming-conversation-request.md)
