---
title: "Configure agent display name for a chat widget | MicrosoftDocs"
description: "Instructions to configure agent display name for a chat widget in Omnichannel for Customer Service."
keywords: ""
author: sbmjais
ms.author: shjais
manager: shujoshi
applies_to: 
ms.date: 07/01/2019
ms.service: dynamics-365-customerservice
ms.topic: article
ms.assetid: B6B22831-57A3-4877-B379-0A43F1599A11
ms.custom: 
---

# Configure agent display name

Applies to Dynamics 365 for Customer Engagement apps version 9.1.0

To protect an agent's privacy, you can configure your chat widget to display either full name, first name, last name, or nickname of an agent to the customers. If you would like to hide your agent’s identity and anonymize, choose to display the nickname. The values for the names are retrieved from the user entity record created in Omnichannel for Customer Service. For information on creating users, see [Create users in Dynamics 365 for Customer Engagement apps and assign security roles](../../admin/create-users-assign-online-security-roles.md). You can add nickname of a user in the Omnichannel user record in Web Client.

> [!NOTE]
> The selected agent display name is displayed only in the chat widget while chatting with a customer. For consultation or chat transfer, full name of the agent is used. 

1. Sign in to Omnichannel Administration.

2. Go to **Channels** &gt; **Chat**.

3. Open the chat widget in which you need to configure the agent display name.

5. Go to the **Basic details** tab.

6. In the **Display agent name** field, select one of the following:

    - **Full name**: Full name of the agent.

    - **First name**: First name of the agent. By default, first name is selected.

    - **Last name**: Last name of the agent.

    - **Nick name**: Nickname of the agent. If a nickname is not available in the user entity record, the full name is displayed to the customers.

7.	Select **Save**.
