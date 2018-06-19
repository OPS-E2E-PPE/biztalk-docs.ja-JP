---
title: 要求/応答を使用してメッセージを相互に関連付ける |Microsoft ドキュメント
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
ms.openlocfilehash: f2f13d8dea9192e982f597311ca3ea13fa213ed0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237994"
---
# <a name="correlating-messages-using-request-reply"></a><span data-ttu-id="e730e-102">要求 - 応答を使用したメッセージの関連付け</span><span class="sxs-lookup"><span data-stu-id="e730e-102">Correlating Messages Using Request-Reply</span></span>
<span data-ttu-id="e730e-103">Windows プラットフォームのサーバー コンポーネントの要求 - 応答シナリオである、IBM WebSphere MQ の BizTalk オーケストレーションでメッセージを関連付ける方法は 2 とおりあります。</span><span class="sxs-lookup"><span data-stu-id="e730e-103">There are two ways to correlate messages in BizTalk orchestrations for IBM WebSphere MQ, server component for Windows platforms request-reply scenarios.</span></span> <span data-ttu-id="e730e-104">両方のメッセージ Id を設定して、相関 id を指定する (**MQMD_MSGID**) および CorrelationID (**MQMD_CorrelId**)、同じ値にします。</span><span class="sxs-lookup"><span data-stu-id="e730e-104">The first is to supply the correlation identifier by setting both the MessageID (**MQMD_MSGID**) and the CorrelationID (**MQMD_CorrelId**) to the same value.</span></span> <span data-ttu-id="e730e-105">2 つ目は、使用する、 **BizTalk_CorrelationId**コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="e730e-105">The second is to use the **BizTalk_CorrelationId** context property.</span></span>  
  
## <a name="setting-mqmdmsgid-and-mqmdcorrelid-to-the-same-value"></a><span data-ttu-id="e730e-106">MQMD_MsgId および MQMD_CorrelId の、同じ値への設定</span><span class="sxs-lookup"><span data-stu-id="e730e-106">Setting MQMD_MsgId and MQMD_CorrelId to the Same value</span></span>  
 <span data-ttu-id="e730e-107">IBM WebSphere MQ キュー マネージャーに、メッセージを送信するときに、メッセージ id を設定することができます (**MQMD_MSGID**) と関連付け識別子 (**MQMD_CorrelId**)、送信メッセージに同じ値を.</span><span class="sxs-lookup"><span data-stu-id="e730e-107">When sending the message to an IBM WebSphere MQ Queue Manager, you can set the message identifier (**MQMD_MSGID**) and the correlation identifier (**MQMD_CorrelId**) to the same value in the outgoing message.</span></span> <span data-ttu-id="e730e-108">IBM WebSphere MQ のキュー マネージャは、MessageID を返信メッセージの CorrelationID にコピーします。</span><span class="sxs-lookup"><span data-stu-id="e730e-108">The IBM WebSphere MQ Queue Manager copies the MessageID to the CorrelationID for the reply message.</span></span> <span data-ttu-id="e730e-109">次の図は、プロセスを示します。</span><span class="sxs-lookup"><span data-stu-id="e730e-109">The following figure shows the process.</span></span>  
  
 <span data-ttu-id="e730e-110">![簡単な関連付け](../core/media/bts-dev-mqsimplecorrelation.gif "BTS_Dev_MQSimpleCorrelation")</span><span class="sxs-lookup"><span data-stu-id="e730e-110">![Simple Correlation](../core/media/bts-dev-mqsimplecorrelation.gif "BTS_Dev_MQSimpleCorrelation")</span></span>  
  
 <span data-ttu-id="e730e-111">値を使用して受信メッセージの関連付けセットに従って、送信メッセージの関連付けセットを初期化する**MQMD_CorrelId**です。</span><span class="sxs-lookup"><span data-stu-id="e730e-111">You can initialize the correlation sets for the outgoing message and follow the correlation sets for the incoming message using the value of **MQMD_CorrelId**.</span></span>  
  
## <a name="using-the-mqseriesbiztalkcorrelationid-context-property"></a><span data-ttu-id="e730e-112">MQSeries.BizTalk_CorrelationId コンテキスト プロパティの使用</span><span class="sxs-lookup"><span data-stu-id="e730e-112">Using the MQSeries.BizTalk_CorrelationId Context Property</span></span>  
 <span data-ttu-id="e730e-113">使用することができます、MessageID と CorrelationID を設定するには、送信メッセージで同じ値に、代わりに、 **BizTalk_CorrelationID**送信請求-応答のコンテキスト プロパティは、MQSeries アダプターのポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="e730e-113">Instead of setting the MessageID and CorrelationID to the same value in the outgoing message, you can use the **BizTalk_CorrelationID** context property with a solicit-response send port of the MQSeries adapter.</span></span> <span data-ttu-id="e730e-114">このプロセスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e730e-114">The following figure shows this process.</span></span>  
  
 <span data-ttu-id="e730e-115">![使用して、送信請求 & #45 です。CorrelationID の生成に応答](../core/media/bts-dev-mqgeneratedcorrelation.gif "BTS_Dev_MQGeneratedCorrelation")</span><span class="sxs-lookup"><span data-stu-id="e730e-115">![Using Solicit&#45;Response to generate CorrelationID](../core/media/bts-dev-mqgeneratedcorrelation.gif "BTS_Dev_MQGeneratedCorrelation")</span></span>  
  
 <span data-ttu-id="e730e-116">IBM WebSphere MQ Server によって提供される識別子を BizTalk オーケストレーションでの関連付けに使用するには、まず BizTalk Server で識別子を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e730e-116">To use identifiers provided by IBM WebSphere MQ Server for correlations in your BizTalk orchestration, BizTalk Server must first obtain the identifier.</span></span> <span data-ttu-id="e730e-117">アプリケーションはこの処理を、送信請求 - 応答の要求を通じて行います。</span><span class="sxs-lookup"><span data-stu-id="e730e-117">Your application does this through a solicit-response request.</span></span> <span data-ttu-id="e730e-118">BizTalk Server は、MQSeries アダプタを使用して、送信請求 - 応答の要求を IBM WebSphere MQ Server に送信します。</span><span class="sxs-lookup"><span data-stu-id="e730e-118">BizTalk Server sends a solicit-response request to the IBM WebSphere MQ Server by using the MQSeries adapter.</span></span> <span data-ttu-id="e730e-119">代わりに、メッセージ識別子を持つ応答を受け取る (**MQMD_MSGId**) と関連付け識別子 (**MQMD_CorrelId**)。</span><span class="sxs-lookup"><span data-stu-id="e730e-119">In return, it receives a response with the message identifier (**MQMD_MSGId**) and the correlation identifier (**MQMD_CorrelId**).</span></span>  
  
 <span data-ttu-id="e730e-120">アダプターの送信メッセージの送信請求-応答送信ポート、するため、コピー、 **MQMD_MSGID**に IBM WebSphere MQ Server によって生成された、 **MQSeries.BizTalk_CorrelationId**コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="e730e-120">For the outgoing message in a solicit-response send port, the adapter copies the **MQMD_MSGID** generated by IBM WebSphere MQ Server to the **MQSeries.BizTalk_CorrelationId** context property.</span></span>  
  
 <span data-ttu-id="e730e-121">メッセージを受信するときに、アダプターがコピー、 **MQMD_CorrelId**を**MQSeries.BizTalk_CorrelationId**です。</span><span class="sxs-lookup"><span data-stu-id="e730e-121">When receiving messages, the adapter copies the **MQMD_CorrelId** to the **MQSeries.BizTalk_CorrelationId**.</span></span> <span data-ttu-id="e730e-122">この場合、関連付けセットを使用して初期化できますを使用して受信メッセージの関連付けセットに従って、送信メッセージの関連付けセット、 **MQSeries.BizTalk_CorrelationId**です。</span><span class="sxs-lookup"><span data-stu-id="e730e-122">In this case, using correlation sets, you can initialize the correlation sets for the outgoing message and follow the correlation sets for the incoming message using the **MQSeries.BizTalk_CorrelationId**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e730e-123">参照</span><span class="sxs-lookup"><span data-stu-id="e730e-123">See Also</span></span>  
 [<span data-ttu-id="e730e-124">MQSCorrelationSetOrchestrationWithSolicitResponse (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="e730e-124">MQSCorrelationSetOrchestrationWithSolicitResponse (BizTalk Server Sample)</span></span>](../core/mqscorrelationsetorchestrationwithsolicitresponse-biztalk-server-sample.md)