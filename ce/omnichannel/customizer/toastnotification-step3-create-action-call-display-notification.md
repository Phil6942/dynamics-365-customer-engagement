---
title: "Create Omnichannel Toast Notification-related action call | MicrosoftDocs"
description: "Learn how to create action calls that can be used to show notifications in Omnichannel for Customer Service."
keywords: ""
author: kabala123
ms.author: kabala
manager: shujoshi
applies_to: 
ms.date: 07/01/2019
ms.service: dynamics-365-customerservice
ms.topic: article
ms.assetid: 72569407-76f3-4d44-b598-68c75c4ba64f
ms.custom: 
---
# Step 3: Create an action call to display the notification 

Applies to Dynamics 365 for Customer Engagement apps version 9.1.0

## Prerequisites

- You must have required [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)] apps permissions to configure [!INCLUDE[pn_unified_service_desk](../../includes/pn-unified-service-desk.md)] and access the required [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)] apps entities. [!INCLUDE[proc_more_information](../../includes/proc-more-information.md)] [Access management in Unified Service Desk](/dynamics365/customer-engagement/unified-service-desk/admin/security-unified-service-desk)

- You must have completed [Create agent and supervisor configurations in Unified Service Desk](create-agent-supervisor-configurations-unified-service-desk.md), [Step 1: Create forms to define notification layout](toastnotification-step1-create-forms-define-layout-behavior-notification.md), and [Step 2: Create Omnichannel Toast Notification hosted control](toastnotification-step2-create-hosted-controls.md). The configurations that you completed are required for this topic.

- You must be familiar with the following concepts in [!INCLUDE[pn_unified_service_desk](../../includes/pn-unified-service-desk.md)]:  
  
  - [Unified Service Desk Hosted Controls](/dynamics365/customer-engagement/unified-service-desk/unified-service-desk-hosted-controls)  
  
  - These three types of hosted controls: Connection Manager, Global Manager, and Panel Layout. [!INCLUDE[proc_more_information](../../includes/proc-more-information.md)] [Hosted control types, action, and event reference in Unified Service Desk](/dynamics365/customer-engagement/unified-service-desk/hosted-control-types-action-event-reference) 
  
  - Filter access using [!INCLUDE[pn_unified_service_desk](../../includes/pn-unified-service-desk.md)]. [!INCLUDE[proc_more_information](../../includes/proc-more-information.md)] [Manage access using Unified Service Desk configuration](/dynamics365/customer-engagement/unified-service-desk/admin/manage-access-using-unified-service-desk-configuration)

## Create action calls

1. Sign in to a Microsoft Dynamics 365 for Customer Engagement instance.

2. Select the Down arrow next to Dynamics 365.

3. Select **Unified Service Desk Administrator**.

4. Select **Action Calls** and select **+ New**. 

5. On the page for the new action call, specify the following details. 

 | Tab             | Field           | Value                       |
 |-----------------|-----------------|-----------------------------|
 | General | Name            | Show Session Assignment Toast Notification          |
 | General | Order           | 10                          |
 | General | Hosted Control  | Omnichannel Toast Notification   |
 | General | Action          | Show           |
 | General | Data            | formname=ToastNotification <br> top=85 <br> left=82 <br> timeout=7 <br> stack=true <br> stackHeight=56 <br> placementmode=absolute <br> ToastNotificationText=\[\[$Resources.SessionAssignmentToastNotification\]+\] <br> NotificationIcon=new_omni_toast_tick_icon  |
 | Advanced | Condition | \[\[$GlobalDictionary.CurrentSessionCount\]+\] >= \[\[$Global.maxNumberOfSessions\]+\] && '\[\[CanActivateSession\]+\]' != 'True' |

6. Save the action call.

7. Repeat steps 4 through 6 to create the following additional action calls.
 
<!-- ## Show Entity Notification

 | Tab             | Field           | Value                                        |
 |-----------------|-----------------|----------------------------------------------|
 | General | Name            | Show Entity Notification                   |
 | General | Order           | 10                                           |
 | General | Hosted Control  | Omnichannel Toast Notification              |
 | General | Action          | Show                                         |
 | General | Data            | formname=EntityNotification <br> top=85 <br> left=95 <br> timeout=60 <br> stack=true <br> stackHeight=50 <br> EntityDisplayName=\[\[EntityDisplayName\]+\] <br> EntityLogicalName=\[\[EntityLogicalName\]+\] <br> EntityId=\[\[EntityId\]+\] <br> ConversationId=\[\[ConversationId\]+\] |


## Expand Right Pane

 | Tab             | Field           | Value                          |
 |-----------------|-----------------|--------------------------------|
 | General | Name            | Expand Right Pane              |
 | General | Hosted Control  | Custom Panel                   |
 | General | Action          | SetVisualProperty              |
 | General | Data            | elementName=RightPanelExpander <br> propertyname=IsExpanded <br> value=true |

## Create Customer Session

 | Tab             | Field           | Value                 |
 |-----------------|-----------------|-----------------------|
 | General | Name            | Create Customer Session |
 | General | Order           | 10                    |
 | General | Hosted Control  | CRM Global Manager    |
 | General | Action          | CreateSession    |
 | Advanced | Condition | \[\[$GlobalDictionary.CurrentSessionCount\]+\] < \[\[$Global.maxNumberOfSessions\]+\]  && '\[\[CanActivateSession\]+\]' != 'True' |

## Set Entity Session Property in Context

 | Tab             | Field           | Value                                  |
 |-----------------|-----------------|----------------------------------------|
 | General | Name            | Set Entity Session Property in Context |
 | General | Order           | 11                                     |
 | General | Hosted Control  | CRM Global Manager                     |
 | General | Action          | CopyToContext                          |
 | General | Data            | ISENTITYSESSION=True <br> CRMCONTACTID=010101                 |

## Collapse Left Panel

 | Tab             | Field           | Value            |
 |-----------------|-----------------|------------------|
 | General | Name            | Collapse Left Panel |
 | General | Order           | 12                |
 | General | Hosted Control  | Custom Panel      |
 | General | Action          | SetVisualProperty |
 | General | Data            | elementname=LeftPanelParent <br>  propertyname=Visibility <br> value=$Expression('\[\[$Context.IsCaseSession\]+\]'=='True' \|\| '\[\[$Context.ISENTITYSESSION\]+\]'=='True' \|\| '\[\[$Session.IsGlobal\]+\]'=='True' \|\| '\[\[$Context.cticallincoming\]+\]'=='1'? "Collapsed" : "Visible")  |

## Load Form for Entity 

 | Tab             | Field           | Value                                  |
 |-----------------|-----------------|----------------------------------------|
 | General | Name            | Load Form for Entity              |
 | General | Order           | 30                                     |
 | General | Hosted Control  | Entity Page                        |
 | General | Action          | Open\_CRM\_Page                        |
 | General | Data            | LogicalName=\[\[EntityLogicalName\]+\] <br> id=\[\[EntityId\]+\]  |
 | Advanced | Condition | \[\[$GlobalDictionary.CurrentSessionCount\]+\] < \[\[$Global.maxNumberOfSessions\]+\] |

## Omnichannel Set Session Tab Id For Entity Session

 | Tab             | Field           | Value                                       |
 |-----------------|-----------------|---------------------------------------------|
 | General | Name            | Omnichannel Set Session Tab Id For Entity Session           |
 | General | Order           | 45                                          |
 | General | Hosted Control  | Communication Panel                    |
 | General | Action          | OmnichannelSetSessionTabIdForEntitySession  |
 | General | Data            | ConversationId=\[\[ConversationId\]\] <br> SessionTabId=\[\[$Session.ActiveSession\]\] |
 | Advanced | Condition | \[\[$GlobalDictionary.CurrentSessionCount\]+\] < \[\[$Global.maxNumberOfSessions\]+\] | 

  -->

## Show Session Error Toast Notification

 | Tab | Field | Value |
 |------------------|------------------|------------------|
 | General | Name           | Show Session Error Toast Notification   |
 | General | Order | 10 |
 | General | Hosted Control | Omnichannel Toast Notification |
 | General | Action         | Show | 
 | General | Data | formname=ToastNotification <br> top=85 <br> left=82 <br> timeout=7 <br> stack=true <br> stackHeight=56 <br> placementmode=absolute <br> ToastNotificationText=To open this incoming conversation in a session, close an existing session. <br> NotificationIcon=new_omni_toast_error_icon |
 | Advanced | Condition | \[\[$GlobalDictionary.CurrentSessionCount\]+\] >= \[\[$Global.maxNumberOfSessions\]+\] && '\[\[CanActivateSession\]+\]' != 'True' |

<!--
## Omnichannel Session Timeout 

 | Tab             | Field           | Value                       |
 |-----------------|-----------------|-----------------------------|
 | General | Name            | Omnichannel Session Timeout            |
 | General | Order           | 16                          |
 | General | Hosted Control  | OmnichannelHostedControl    |
 | General | Action          | OCSessionTimeout            |
 | General | Data            | ConversationId=\[\[cid\]\]  |


## Load Case session Agent Script

 | Tab             | Field           | Value                       |
 |-----------------|-----------------|-----------------------------|
 | General | General | Name            | Load Case session Agent Script           |
 | General | Order           | 20                          |
 | General | Hosted Control  | Agent Script HC   |
 | General | Action          | GoToTask           |
 | General | Data            | Case Resolution Script  |
 | Advanced | Condition | \[\[$GlobalDictionary.CurrentSessionCount\]+\] < \[\[$Global.maxNumberOfSessions\]+\] |

 | Tab             | Field           | Value                            |
 |-----------------|-----------------|----------------------------------|
 | General | Name            | Close Toast Notification        |
 | General | Hosted Control  | Omnichannel Toast Notification  |
 | General | Action          | Close                            |

 -->


> [!div class="nextstepaction"]
> [Next topic: Step 4: Attach Omnichannel Toast Notification-related action calls to events](toastnotification-step4-add-action-calls-events.md)

## See also

- [Configure toast notification in Unified Service Desk](configure-toast-notification-unified-service-desk.md)
- [Step 1: Create forms to define layout and behavior of the notification](toastnotification-step1-create-forms-define-layout-behavior-notification.md)
- [Step 2: Create Omnichannel Toast Notification-related hosted control](toastnotification-step2-create-hosted-controls.md)
- [Step 5: Add the hosted control, events, and action calls to the agent and supervisor configurations](toastnotification-step5-add-hosted-controls-events-action-callsagent-supervisor-configurations.md)
- [Configure alert notification in Unified Service Desk](configure-alert-notification-unified-service-desk.md)
