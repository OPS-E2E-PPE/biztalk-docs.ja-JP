---
title: 要求/応答を使用してメッセージの関連付け |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, MQSeries adapters
- messages, correlating
- MQSeries adapters, correlating messages
ms.assetid: 4615b586-663b-41d8-949c-fefb6143c590
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91790a879816efa7b2bfa7a5a16f4ea1dfbb13a2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390203"
---
# <a name="correlating-messages-using-request-reply"></a>要求/応答を使用してメッセージの関連付け
Windows プラットフォームの要求/応答シナリオ用のサーバー コンポーネントである IBM WebSphere MQ の BizTalk オーケストレーションでメッセージを関連付ける 2 つの方法はあります。 1 つが、両方の MessageID を設定して、相関 id を指定するには (**MQMD_MSGID**) と、関連付け Id (**MQMD_CorrelId**) と同じ値にします。 2 つ目は、使用する、 **BizTalk_CorrelationId**コンテキスト プロパティ。  
  
## <a name="setting-mqmdmsgid-and-mqmdcorrelid-to-the-same-value"></a>MQMD_MsgId および MQMD_CorrelId を同じ値に設定します。  
 IBM WebSphere MQ キュー マネージャーに、メッセージを送信する場合は、メッセージ id を設定できます (**MQMD_MSGID**) と関連付け識別子 (**MQMD_CorrelId**)、送信メッセージに同じ値を. IBM WebSphere MQ のキュー マネージャーは、MessageID を返信メッセージの CorrelationID にコピーします。 次の図は、プロセスを示します。  
  
 ![簡単な関連付け](../core/media/bts-dev-mqsimplecorrelation.gif "BTS_Dev_MQSimpleCorrelation")  
  
 次の値を使用して受信メッセージの関連付けセットに、送信メッセージの関連付けセットを初期化する**MQMD_CorrelId**します。  
  
## <a name="using-the-mqseriesbiztalkcorrelationid-context-property"></a>MQSeries.BizTalk_CorrelationId コンテキスト プロパティを使用します。  
 MessageID と CorrelationID を送信メッセージに同じ値に設定する代わりに使用することができます、 **BizTalk_CorrelationID**送信請求-応答のコンテキスト プロパティは、MQSeries アダプターのポートを送信します。 このプロセスを次に示します。  
  
 ![送信請求を使用して&#45;CorrelationID の生成を応答](../core/media/bts-dev-mqgeneratedcorrelation.gif "BTS_Dev_MQGeneratedCorrelation")  
  
 BizTalk オーケストレーションでの相関関係の IBM WebSphere MQ Server によって提供される識別子を使用するには、場合は、BizTalk Server に識別子を取得してする必要があります。 アプリケーションは送信請求-応答、要求を使用します。 BizTalk Server では、MQSeries アダプターを使用して、IBM WebSphere MQ Server に送信請求-応答の要求を送信します。 代わりに、メッセージ識別子と応答を受信 (**MQMD_MSGId**) と関連付け識別子 (**MQMD_CorrelId**)。  
  
 送信請求-応答送信ポートで送信メッセージをアダプターにコピー、 **MQMD_MSGID**に IBM WebSphere MQ Server によって生成された、 **MQSeries.BizTalk_CorrelationId**コンテキスト プロパティ。  
  
 メッセージを受信するときに、アダプターがコピー、 **MQMD_CorrelId**を**MQSeries.BizTalk_CorrelationId**します。 この場合、関連付けセットを使用して初期化できますを使用して受信メッセージの関連付けセットに従って、送信メッセージの関連付けセットを**MQSeries.BizTalk_CorrelationId**します。  
  
## <a name="see-also"></a>参照  
 [MQSCorrelationSetOrchestrationWithSolicitResponse (BizTalk Server サンプル)](../core/mqscorrelationsetorchestrationwithsolicitresponse-biztalk-server-sample.md)