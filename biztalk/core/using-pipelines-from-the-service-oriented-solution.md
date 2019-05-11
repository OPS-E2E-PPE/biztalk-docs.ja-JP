---
title: サービスからのパイプラインを使用して指向ソリューション |Microsoft Docs
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
ms.openlocfilehash: aeddd2168f6fc796752aa5d1e276816f9a087ce2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396607"
---
# <a name="using-pipelines-from-the-service-oriented-solution"></a>サービスからのパイプラインを使用して指向ソリューション
カスタマ サービス オーケストレーションのインライン バージョン (**CustomerService**)、payment tracking システムを直接呼び出します。 送信されたメッセージとプロセス、受信したメッセージを準備するには、オーケストレーションは、コードからパイプラインを呼び出します。 これにより、他のシナリオ バージョンからのパイプラインの再利用できます。 パイプライン ステージからオーケストレーションの切り離しを保存します。  
  
## <a name="calling-the-pipelines"></a>パイプラインの呼び出し  
 コードからパイプラインを使用するにはメッセージのコレクションを作成、コレクションに処理し、結果のメッセージを受信する空のメッセージを作成し、パイプラインの呼び出しにメッセージを追加します。  
  
 次のコードから、 **CustomerService**オーケストレーションが、 **ConstructRequestMessageAfterSendPipeline**図形。  
  
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
  
 **GetLastPaymentResponse**図形は、上記のコードからメッセージを取得、payment tracking システムに送信および受信パイプラインを通じて返されたメッセージを処理します。  
  
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
  
## <a name="see-also"></a>参照  
 [サービス指向ソリューションの実装の重要なポイント](../core/implementation-highlights-of-the-service-oriented-solution.md)