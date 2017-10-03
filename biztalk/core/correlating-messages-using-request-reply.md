---
title: "要求/応答を使用してメッセージを相互に関連付ける |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, MQSeries adapters
- messages, correlating
- MQSeries adapters, correlating messages
ms.assetid: 4615b586-663b-41d8-949c-fefb6143c590
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2f13d8dea9192e982f597311ca3ea13fa213ed0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="correlating-messages-using-request-reply"></a>要求 - 応答を使用したメッセージの関連付け
Windows プラットフォームのサーバー コンポーネントの要求 - 応答シナリオである、IBM WebSphere MQ の BizTalk オーケストレーションでメッセージを関連付ける方法は 2 とおりあります。 両方のメッセージ Id を設定して、相関 id を指定する (**MQMD_MSGID**) および CorrelationID (**MQMD_CorrelId**)、同じ値にします。 2 つ目は、使用する、 **BizTalk_CorrelationId**コンテキスト プロパティです。  
  
## <a name="setting-mqmdmsgid-and-mqmdcorrelid-to-the-same-value"></a>MQMD_MsgId および MQMD_CorrelId の、同じ値への設定  
 IBM WebSphere MQ キュー マネージャーに、メッセージを送信するときに、メッセージ id を設定することができます (**MQMD_MSGID**) と関連付け識別子 (**MQMD_CorrelId**)、送信メッセージに同じ値を. IBM WebSphere MQ のキュー マネージャは、MessageID を返信メッセージの CorrelationID にコピーします。 次の図は、プロセスを示します。  
  
 ![簡単な関連付け](../core/media/bts-dev-mqsimplecorrelation.gif "BTS_Dev_MQSimpleCorrelation")  
  
 値を使用して受信メッセージの関連付けセットに従って、送信メッセージの関連付けセットを初期化する**MQMD_CorrelId**です。  
  
## <a name="using-the-mqseriesbiztalkcorrelationid-context-property"></a>MQSeries.BizTalk_CorrelationId コンテキスト プロパティの使用  
 使用することができます、MessageID と CorrelationID を設定するには、送信メッセージで同じ値に、代わりに、 **BizTalk_CorrelationID**送信請求-応答のコンテキスト プロパティは、MQSeries アダプターのポートを送信します。 このプロセスを次に示します。  
  
 ![使用して、送信請求 & #45 です。CorrelationID の生成に応答](../core/media/bts-dev-mqgeneratedcorrelation.gif "BTS_Dev_MQGeneratedCorrelation")  
  
 IBM WebSphere MQ Server によって提供される識別子を BizTalk オーケストレーションでの関連付けに使用するには、まず BizTalk Server で識別子を取得する必要があります。 アプリケーションはこの処理を、送信請求 - 応答の要求を通じて行います。 BizTalk Server は、MQSeries アダプタを使用して、送信請求 - 応答の要求を IBM WebSphere MQ Server に送信します。 代わりに、メッセージ識別子を持つ応答を受け取る (**MQMD_MSGId**) と関連付け識別子 (**MQMD_CorrelId**)。  
  
 アダプターの送信メッセージの送信請求-応答送信ポート、するため、コピー、 **MQMD_MSGID**に IBM WebSphere MQ Server によって生成された、 **MQSeries.BizTalk_CorrelationId**コンテキスト プロパティです。  
  
 メッセージを受信するときに、アダプターがコピー、 **MQMD_CorrelId**を**MQSeries.BizTalk_CorrelationId**です。 この場合、関連付けセットを使用して初期化できますを使用して受信メッセージの関連付けセットに従って、送信メッセージの関連付けセット、 **MQSeries.BizTalk_CorrelationId**です。  
  
## <a name="see-also"></a>参照  
 [MQSCorrelationSetOrchestrationWithSolicitResponse (BizTalk Server サンプル)](../core/mqscorrelationsetorchestrationwithsolicitresponse-biztalk-server-sample.md)