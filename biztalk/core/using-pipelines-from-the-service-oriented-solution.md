---
title: サービスからパイプラインを使用して指向ソリューション |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, pipelines
- pipelines, service solutions
ms.assetid: 0870fce1-52ec-4ff8-884f-a3199bd7ccbb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d6b8021a22db366b31cde26abdc3ef48f3e51a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287210"
---
# <a name="using-pipelines-from-the-service-oriented-solution"></a><span data-ttu-id="d9db6-102">サービスからパイプラインを使用して指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="d9db6-102">Using Pipelines from the Service Oriented Solution</span></span>
<span data-ttu-id="d9db6-103">カスタマ サービス オーケストレーションのインライン バージョン (**CustomerService**)、直接 payment tracking システムを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d9db6-103">The inline version of the customer service orchestration (**CustomerService**) calls the payment tracking system directly.</span></span> <span data-ttu-id="d9db6-104">送信するメッセージを準備して受信するメッセージを処理するため、オーケストレーションは、コードからパイプラインを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d9db6-104">To prepare the sent message and process the received message, the orchestration calls the pipelines from code.</span></span> <span data-ttu-id="d9db6-105">このため、他のシナリオ バージョンのパイプラインを再利用できます。</span><span class="sxs-lookup"><span data-stu-id="d9db6-105">This allows the reuse of the pipelines from the other scenarios versions.</span></span> <span data-ttu-id="d9db6-106">また、パイプライン ステージのオーケストレーションの切り離しを保存します。</span><span class="sxs-lookup"><span data-stu-id="d9db6-106">It also maintains the decoupling of the orchestration from the pipeline stages.</span></span>  
  
## <a name="calling-the-pipelines"></a><span data-ttu-id="d9db6-107">パイプラインの呼び出し</span><span class="sxs-lookup"><span data-stu-id="d9db6-107">Calling the Pipelines</span></span>  
 <span data-ttu-id="d9db6-108">コードからパイプラインを使用するには、メッセージ コレクションの作成、コレクションに対して処理されるメッセージの追加、結果のメッセージを受信するための空のメッセージの作成、およびパイプラインの呼び出しを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9db6-108">To use the pipelines from code, you must create a message collection, add the message to process to the collection, create an empty message to receive the result message, and invoke the pipeline.</span></span>  
  
 <span data-ttu-id="d9db6-109">次のコードから、 **CustomerService**オーケストレーション、 **ConstructRequestMessageAfterSendPipeline**図形。</span><span class="sxs-lookup"><span data-stu-id="d9db6-109">The following code from the **CustomerService** orchestration is in the **ConstructRequestMessageAfterSendPipeline** shape:</span></span>  
  
```  
// Create the collection of messages to be sent to the send pipeline...  
sendPipelineInputMessages =   
    new Microsoft.XLANGs.Pipeline.SendPipelineInputMessages();  
sendPipelineInputMessages.Add(LastPaymentRequest);  
  
// Create an empty message for the output from the pipeline...  
LastPaymentRequestAfterSendPipeline = null;  
  
// Execute the send pipeline and get the message output from   
// the send pipeline.  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.  
    ExecuteSendPipeline(  
        typeof(  
            Microsoft.Samples.BizTalk.  
                WoodgroveBank.PaymentTrackerPipelines.  
                    PaymentTrackerSendPipeline  
        ),  
        sendPipelineInputMessages,  
        LastPaymentRequestAfterSendPipeline  
    );  
```  
  
 <span data-ttu-id="d9db6-110">**GetLastPaymentResponse**図形は、上記のコードからメッセージを取得、payment tracking システムに送信および受信パイプラインを通じて返されたメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="d9db6-110">The **GetLastPaymentResponse** shape takes the message from the above code, sends it to the payment tracking system, and processes the returned message through the receive pipeline:</span></span>  
  
```  
// Execute the inline method to send the message to the   
// Payment Tracking System and get the response.  
// The response message received should be passed through the   
// receive pipeline.  
  
LastPaymentResponseBeforeReceivePipeline =   
    Microsoft.Samples.BizTalk.  
        WoodgroveBank.  
            PaymentTrackerCall.  
                PaymentTrackerCaller.  
                    GetPaymeTrackerResponse  
                    (  
                        LastPaymentRequestAfterSendPipeline  
                    );   
  
// Execute the receive pipeline using the helper class so that we don't  
// need to declare the non-serializable types involved.  
  
// Set the documentspec name so the xml disassembler in the   
// pipeline can resolve the schemas for the received message  
// without ambiguity.  
LastPaymentResponseBeforeReceivePipeline(XMLNORM.DocumentSpecName) =   
"Microsoft.Samples.BizTalk.WoodgroveBank.Schemas.LastPaymentResponse, Microsoft.Samples.BizTalk.WoodgroveBank.Schemas, Version=1.0.0.0, Culture=neutral, PublicKeyToken=5f57a322d27bc5fb";  
// Create an empty response message and fill it in with the   
// real response from the Payment Tracking System  
LastPaymentResponse = null;  
  
Microsoft.Samples.BizTalk.WoodgroveBank.Utilities.  
    ReceivePipelineHelper.CallReceivePipeLine (  
        typeof(  
            Microsoft.Samples.BizTalk.WoodgroveBank.  
                PaymentTrackerPipelines.PaymentTrackerReceivePipeline  
            ),  
            LastPaymentResponseBeforeReceivePipeline,  
            LastPaymentResponse  
        );  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9db6-111">参照</span><span class="sxs-lookup"><span data-stu-id="d9db6-111">See Also</span></span>  
 [<span data-ttu-id="d9db6-112">指向ソリューションのサービスの実装の要点</span><span class="sxs-lookup"><span data-stu-id="d9db6-112">Implementation Highlights of the Service Oriented Solution</span></span>](../core/implementation-highlights-of-the-service-oriented-solution.md)