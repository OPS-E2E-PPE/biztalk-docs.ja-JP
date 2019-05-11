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
# <a name="correlating-messages-using-request-reply"></a><span data-ttu-id="ba900-102">要求/応答を使用してメッセージの関連付け</span><span class="sxs-lookup"><span data-stu-id="ba900-102">Correlating Messages Using Request-Reply</span></span>
<span data-ttu-id="ba900-103">Windows プラットフォームの要求/応答シナリオ用のサーバー コンポーネントである IBM WebSphere MQ の BizTalk オーケストレーションでメッセージを関連付ける 2 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="ba900-103">There are two ways to correlate messages in BizTalk orchestrations for IBM WebSphere MQ, server component for Windows platforms request-reply scenarios.</span></span> <span data-ttu-id="ba900-104">1 つが、両方の MessageID を設定して、相関 id を指定するには (**MQMD_MSGID**) と、関連付け Id (**MQMD_CorrelId**) と同じ値にします。</span><span class="sxs-lookup"><span data-stu-id="ba900-104">The first is to supply the correlation identifier by setting both the MessageID (**MQMD_MSGID**) and the CorrelationID (**MQMD_CorrelId**) to the same value.</span></span> <span data-ttu-id="ba900-105">2 つ目は、使用する、 **BizTalk_CorrelationId**コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ba900-105">The second is to use the **BizTalk_CorrelationId** context property.</span></span>  
  
## <a name="setting-mqmdmsgid-and-mqmdcorrelid-to-the-same-value"></a><span data-ttu-id="ba900-106">MQMD_MsgId および MQMD_CorrelId を同じ値に設定します。</span><span class="sxs-lookup"><span data-stu-id="ba900-106">Setting MQMD_MsgId and MQMD_CorrelId to the Same value</span></span>  
 <span data-ttu-id="ba900-107">IBM WebSphere MQ キュー マネージャーに、メッセージを送信する場合は、メッセージ id を設定できます (**MQMD_MSGID**) と関連付け識別子 (**MQMD_CorrelId**)、送信メッセージに同じ値を.</span><span class="sxs-lookup"><span data-stu-id="ba900-107">When sending the message to an IBM WebSphere MQ Queue Manager, you can set the message identifier (**MQMD_MSGID**) and the correlation identifier (**MQMD_CorrelId**) to the same value in the outgoing message.</span></span> <span data-ttu-id="ba900-108">IBM WebSphere MQ のキュー マネージャーは、MessageID を返信メッセージの CorrelationID にコピーします。</span><span class="sxs-lookup"><span data-stu-id="ba900-108">The IBM WebSphere MQ Queue Manager copies the MessageID to the CorrelationID for the reply message.</span></span> <span data-ttu-id="ba900-109">次の図は、プロセスを示します。</span><span class="sxs-lookup"><span data-stu-id="ba900-109">The following figure shows the process.</span></span>  
  
 <span data-ttu-id="ba900-110">![簡単な関連付け](../core/media/bts-dev-mqsimplecorrelation.gif "BTS_Dev_MQSimpleCorrelation")</span><span class="sxs-lookup"><span data-stu-id="ba900-110">![Simple Correlation](../core/media/bts-dev-mqsimplecorrelation.gif "BTS_Dev_MQSimpleCorrelation")</span></span>  
  
 <span data-ttu-id="ba900-111">次の値を使用して受信メッセージの関連付けセットに、送信メッセージの関連付けセットを初期化する**MQMD_CorrelId**します。</span><span class="sxs-lookup"><span data-stu-id="ba900-111">You can initialize the correlation sets for the outgoing message and follow the correlation sets for the incoming message using the value of **MQMD_CorrelId**.</span></span>  
  
## <a name="using-the-mqseriesbiztalkcorrelationid-context-property"></a><span data-ttu-id="ba900-112">MQSeries.BizTalk_CorrelationId コンテキスト プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="ba900-112">Using the MQSeries.BizTalk_CorrelationId Context Property</span></span>  
 <span data-ttu-id="ba900-113">MessageID と CorrelationID を送信メッセージに同じ値に設定する代わりに使用することができます、 **BizTalk_CorrelationID**送信請求-応答のコンテキスト プロパティは、MQSeries アダプターのポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="ba900-113">Instead of setting the MessageID and CorrelationID to the same value in the outgoing message, you can use the **BizTalk_CorrelationID** context property with a solicit-response send port of the MQSeries adapter.</span></span> <span data-ttu-id="ba900-114">このプロセスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="ba900-114">The following figure shows this process.</span></span>  
  
 <span data-ttu-id="ba900-115">![送信請求を使用して&#45;CorrelationID の生成を応答](../core/media/bts-dev-mqgeneratedcorrelation.gif "BTS_Dev_MQGeneratedCorrelation")</span><span class="sxs-lookup"><span data-stu-id="ba900-115">![Using Solicit&#45;Response to generate CorrelationID](../core/media/bts-dev-mqgeneratedcorrelation.gif "BTS_Dev_MQGeneratedCorrelation")</span></span>  
  
 <span data-ttu-id="ba900-116">BizTalk オーケストレーションでの相関関係の IBM WebSphere MQ Server によって提供される識別子を使用するには、場合は、BizTalk Server に識別子を取得してする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba900-116">To use identifiers provided by IBM WebSphere MQ Server for correlations in your BizTalk orchestration, BizTalk Server must first obtain the identifier.</span></span> <span data-ttu-id="ba900-117">アプリケーションは送信請求-応答、要求を使用します。</span><span class="sxs-lookup"><span data-stu-id="ba900-117">Your application does this through a solicit-response request.</span></span> <span data-ttu-id="ba900-118">BizTalk Server では、MQSeries アダプターを使用して、IBM WebSphere MQ Server に送信請求-応答の要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="ba900-118">BizTalk Server sends a solicit-response request to the IBM WebSphere MQ Server by using the MQSeries adapter.</span></span> <span data-ttu-id="ba900-119">代わりに、メッセージ識別子と応答を受信 (**MQMD_MSGId**) と関連付け識別子 (**MQMD_CorrelId**)。</span><span class="sxs-lookup"><span data-stu-id="ba900-119">In return, it receives a response with the message identifier (**MQMD_MSGId**) and the correlation identifier (**MQMD_CorrelId**).</span></span>  
  
 <span data-ttu-id="ba900-120">送信請求-応答送信ポートで送信メッセージをアダプターにコピー、 **MQMD_MSGID**に IBM WebSphere MQ Server によって生成された、 **MQSeries.BizTalk_CorrelationId**コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ba900-120">For the outgoing message in a solicit-response send port, the adapter copies the **MQMD_MSGID** generated by IBM WebSphere MQ Server to the **MQSeries.BizTalk_CorrelationId** context property.</span></span>  
  
 <span data-ttu-id="ba900-121">メッセージを受信するときに、アダプターがコピー、 **MQMD_CorrelId**を**MQSeries.BizTalk_CorrelationId**します。</span><span class="sxs-lookup"><span data-stu-id="ba900-121">When receiving messages, the adapter copies the **MQMD_CorrelId** to the **MQSeries.BizTalk_CorrelationId**.</span></span> <span data-ttu-id="ba900-122">この場合、関連付けセットを使用して初期化できますを使用して受信メッセージの関連付けセットに従って、送信メッセージの関連付けセットを**MQSeries.BizTalk_CorrelationId**します。</span><span class="sxs-lookup"><span data-stu-id="ba900-122">In this case, using correlation sets, you can initialize the correlation sets for the outgoing message and follow the correlation sets for the incoming message using the **MQSeries.BizTalk_CorrelationId**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba900-123">参照</span><span class="sxs-lookup"><span data-stu-id="ba900-123">See Also</span></span>  
 [<span data-ttu-id="ba900-124">MQSCorrelationSetOrchestrationWithSolicitResponse (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="ba900-124">MQSCorrelationSetOrchestrationWithSolicitResponse (BizTalk Server Sample)</span></span>](../core/mqscorrelationsetorchestrationwithsolicitresponse-biztalk-server-sample.md)