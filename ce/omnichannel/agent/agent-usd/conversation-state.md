---
title: "Understand conversation states in Omnichannel for Customer Service | MicrosoftDocs"
description: "Learn what are the conversation states in Omnichannel for Customer Service."
keywords: ""
author: kabala123
ms.author: kabala
manager: shujoshi
applies_to: 
ms.date: 07/01/2019
ms.service: dynamics-365-customerservice
ms.topic: article
ms.assetid: 92C7CE55-87CE-437A-ABD3-65600CAE4DD2
ms.custom: 
---

# Understand conversation states in Omnichannel

The topic explains the various states of the conversation (work item) in Omnichannel.

Types of conversation states:

 - [Open](#open)

 - [Active](#active)
 
 - [Wrap-up](#wrap-up)

 - [Waiting](#waiting)

 - [Closed](#closed) 

 ![Omnichannel conversation states](../../media/oc-conversation-state.png "Conversation states")

## Open

The conversations (work items) that are in the queue and not assigned to you (agent) are classified under **Open** state. 

The conversation (work item) transitions from **Open** to **Active** or **Closed** state under the following scenarios.

| From state | To state | Scenario  | Type (Chat and SMS) |
|---------------|------------------|---------------------------------------------------------|------------|
| Open          | Active           | When you pick the conversation from the **Open work items** stream.<br><br> When the routing and work distribution feature pushes (assigns) the conversation to you. | SMS and Chat |
| Open          | Closed           | When the customer disconnects or ends the chat before the conversation is assigned to you.| Chat |

![Transition from open to active or closed state](../../media/oc-conversation-open.png "Open state")

## Active

The conversations that you pick or assigned to you are classified under **Active** state. In the **Active** state, your capacity is consumed.

The conversation (work item) transitions from **Active** to **Closed**, **Open**, **Waiting**, or **Wrap-up** state under the following scenarios.

| From state | To state | Scenario  | Type (Chat and SMS) |
|---------------|------------------|---------------------------------------------------------|------------|
| Active        | Wrap-up          | When you select the **End** button on communication panel during the conversation with the customer. <br><br> When customer ends the conversation by selecting the **End** button on the portal chat widget.| Chat and SMS |
| Active        | Open             | When you disconnect the conversation and doesn't reconnect with in a specified timeout period. <!-- <br><br> When you release the conversation to the queue.--> <br><br> When you transfer the conversation to another queue. <br><br> | Chat and SMS |
| Active        | Waiting          | When you close the session (not ending the conversation by selecting the **End** button) while the conversation is active.<br><br> When the customer is disconnected from the conversation and you are no longer getting reply, you can close the session without ending the conversation. This will keep conversation in waiting state. |   Chat and SMS |
<!--| Active        | In-progress      | When you close the session with conversation in active state.  | SMS  | 
| Active        | Closed           | When you complete working on the conversation and end the conversation and close the session.| Chat |
-->

![Transition from active to closed, open, waiting, wrap-up, or in-progress state](../../media/oc-conversation-active.png "Active state")

## Wrap-up

This is an intermediate state after you end the conversation, where you can do after active conversation activities like taking notes and update the customer information before moving the conversation to **Closed** state.

The conversation (work item) transitions from **Wrap-up** to **Closed** state under the following scenario. 

| From state | To state | Scenario  | Type (Chat and SMS) |
|---------------|------------------|---------------------------------------------------------|------------|
| Wrap-up       | Closed           | When you select the **End** button in communication panel and close the session. | Chat and SMS |

![Transition from wrap-up to closed state](../../media/oc-conversation-wrap-up.png "Wrap-up state")

## Waiting

Conversation in waiting state don't block your capacity. The conversations get transitioned to waiting state when you (agent) close the session without ending the conversation (without clicking **End** button on communication panel). For example, you are waiting for some information from customer and do not want to end the conversation. 

The conversation (work item) transitions from **Waiting** to **Closed**, **Active**, or **Open** state under the following scenarios.

| From state | To state | Scenario  | Type (Chat and SMS) |
|---------------|------------------|---------------------------------------------------------|------------|
| Waiting       | Closed           | When there is no activity on this conversation from either customer or agent, with in inactivity timeout period. <br><br> When the customer selects the **End** button to end the conversation and close the session.| Chat and SMS |
| Waiting       | Active           | When you revive the session from your **My work items** stream on **Omnichannel Agent Dashboard**. | Chat and SMS |
| Waiting       | Open             | When the customer revives the conversation within a specified timeout period. | Chat and SMS |

![Transition from waiting to closed, active, or open state](../../media/oc-conversation-waiting.png "Waiting state")

<!-- ## In-progress

The session that you close while conversation is still in active state are classified under **In-progress** state.

| From state | To state | Scenario  | Type (SMS, Chat, Entity Routing, Conversation Channels) |
|---------------|------------------|---------------------------------------------------------|------------|
| In-progress   | Closed           | When you don't perform any action, then then conversation auto-closes after the inactivity timeout. | SMS |

![Transition from in-progress to closed state](../../media/oc-conversation-in-progress.png "In-progress state") -->

## Closed

The conversations that are completed by ending, and closing the session are classified under **Closed** state. When you close a conversation, you cannot reactivate or reopen the conversation again.

> [!div class="nextstepaction"]
> [Next topic: View alert and toast notifications](notifications.md)

## See also

[View communication panel](left-control-panel.md)
