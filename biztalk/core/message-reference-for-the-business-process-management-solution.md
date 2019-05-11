---
title: ビジネス プロセス管理ソリューションのメッセージの参照 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, message reference
ms.assetid: 0595817e-da5d-426a-9ee1-0c5d04334de6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1a96b1602aabfd7c56c576c545089ae53c1dc4d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325040"
---
# <a name="message-reference-for-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションのメッセージ リファレンス
このセクションでは、メッセージと、ソリューション内の各オーケストレーションで使用されるメッセージ型を示します。  
  
 表に、 \< *SolutionPrefix* \> Microsoft.Samples.BizTalk.SouthridgeVideo テーブルが読みやすくするために置き換えられます。  
  
> [!NOTE]
>  メッセージの種類の**System.Xml.XmlDocument**スキーマではなく .NET クラスによって定義されたメッセージの種類を示します。  
  
 オーケストレーションやメッセージの種類は次のとおりです。  
  
|オーケストレーション|メッセージ|メッセージ型|  
|-------------------|-------------|------------------|  
|Activate.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|Activate.odx|OrderMsg|\<SolutionPrefix\>します。Schemas.OrderSchema|  
|Analyze.odx|BadXmlOrderMsg|System.Xml.XmlDocument|  
|Analyze.odx|FixedXmlOrderMsg|System.Xml.XmlDocument|  
|Analyze.odx|OrderMsg|\<SolutionPrefix\>します。Schemas.OrderSchema|  
|Analyze.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|CableOrder1.odx|TerminatedMsg|\<SolutionPrefix\>します。SchemaClasses.Terminated|  
|CableOrder1.odx|OrderMgrMsg|\<SolutionPrefix\>.OrderManager.OrderMgrMsgType|  
|CableOrder1.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|CableOrder1.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|CableOrder1.odx|CompletionMsg|\<SolutionPrefix\>.OrderManager.OrderMgrMsgType|  
|CableOrder1.odx|OrderMsg|\<SolutionPrefix\>します。Schemas.OrderSchema|  
|CableOrder1.odx|AckMsg|\<SolutionPrefix\>します。SchemaClasses.OrderAck|  
|CableOrder1.odx|InterruptMsg|\<SolutionPrefix\>します。SchemaClasses.Interrupt|  
|CableOrder2.odx|OrderMgrMsg|\<SolutionPrefix\>.OrderManager.OrderMgrMsgType|  
|CableOrder2.odx|TerminatedMsg|\<SolutionPrefix\>します。SchemaClasses.Terminated|  
|CableOrder2.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|CableOrder2.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|CableOrder2.odx|OrderMsg|\<SolutionPrefix\>します。Schemas.OrderSchema|  
|CableOrder2.odx|CompleteOrderMsg|\<SolutionPrefix\>します。Schemas.OrderSchema|  
|CableOrder2.odx|AckMsg|\<SolutionPrefix\>します。SchemaClasses.OrderAck|  
|CableOrder2.odx|CompletionMsg|\<SolutionPrefix\>.OrderManager.OrderMgrMsgType|  
|Cancel.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|Cancel.odx|OrderMsg|\<SolutionPrefix\>します。Schemas.OrderSchema|  
|Cancel.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|Change.odx|OrderMsg|\<SolutionPrefix\>します。Schemas.OrderSchema|  
|CheckInterrupt.odx|InterruptMsg|\<SolutionPrefix\>します。SchemaClasses.Interrupt|  
|Complete.odx|OrderMsg|\<SolutionPrefix\>します。Schemas.OrderSchema|  
|Complete.odx|XmlOrderMsg|System.Xml.XmlDocument|  
|ErrorHandler.odx|InterruptMsg|\<SolutionPrefix\>します。SchemaClasses.Interrupt|  
|ErrorHandler.odx|OrderStatusMsg|\<SolutionPrefix\>します。SchemaClasses.OrderStatus|  
|ErrorHandler.odx|ResponseMsg|\<SolutionPrefix\>します。SchemaClasses.OrderStatus|  
|ErrorHandler.odx|OriginalMsg|System.Xml.XmlDocument|  
|ErrorHandler.odx|ReturnedMsg|System.Xml.XmlDocument|  
|ExceptionHandler.odx|OriginalMsg|System.Xml.XmlDocument|  
|Interrupter.odx|InterruptMsg|\<SolutionPrefix\>します。SchemaClasses.Interrupt|  
|」の OrderBroker.odx|CSRConfMsg|\<SolutionPrefix\>.OrderBrokerSchemas.CSR_OrderRequestSchema|  
|」の OrderBroker.odx|CSROrderMsg|\<SolutionPrefix\>.OrderBrokerSchemas.CSR_OrderRequestSchema|  
|」の OrderBroker.odx|HistoryInsertMsg|\<SolutionPrefix\>します。OrderBrokerSchemas.SQLHistoryInsertSchema.HistoryInsert|  
|」の OrderBroker.odx|ServicingMsg|\<SolutionPrefix\>.OrderBrokerSchemas.Servicing_OrderRequestSchema|  
|」の OrderBroker.odx|OrderMsg|\<SolutionPrefix\>します。Schemas.OrderSchema|  
|」の OrderBroker.odx|OrderMgrMsg|\<SolutionPrefix\>.OrderBroker.OrderMgrMPMsg|  
|OrderManager.odx|CompletionMsg|\<SolutionPrefix\>します。SchemaClasses.OrderStatus|  
|OrderManager.odx|NewOrderMgrMsg|\<SolutionPrefix\>.OrderManager.OrderMgrMsgType|  
|OrderManager.odx|OrderMgrMsg|\<SolutionPrefix\>.OrderManager.OrderMgrMsgType|  
|OrderManager.odx|OrderAck|\<SolutionPrefix\>します。SchemaClasses.OrderAck|  
|OrderManager.odx|TerminatedMsg|\<SolutionPrefix\>します。SchemaClasses.Terminated|  
|OrderManager.odx|ちらつき|\<SolutionPrefix\>.OrderManager.OrderMgrMsgType|  
|Validate.odx|BadXmlOrderMsg|System.Xml.XmlDocument|  
|Validate.odx|FixedXmlOrderMsg|System.Xml.XmlDocument|  
|Validate.odx|OrderMsg|\<SolutionPrefix\>します。Schemas.OrderSchema|  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューション リファレンス](../core/business-process-management-solution-reference.md)   
 [主要メッセージとフィールド](../core/key-messages-and-fields.md)   
 [プロセス マネージャーでの注文の流れ](../core/order-flow-through-the-process-manager.md)