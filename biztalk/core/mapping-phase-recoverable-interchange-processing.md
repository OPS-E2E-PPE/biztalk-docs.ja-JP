---
title: マッピング フェーズ (回復可能なインターチェンジ処理) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 544d85c7-bc47-46c1-8990-82b48a8f2f23
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20b3e45cf337702457dc8e5986db54df6bea5e5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262314"
---
# <a name="mapping-phase-recoverable-interchange-processing"></a><span data-ttu-id="40b2f-102">マッピング フェーズ (回復可能なインターチェンジ処理)</span><span class="sxs-lookup"><span data-stu-id="40b2f-102">Mapping Phase (Recoverable Interchange Processing)</span></span>
<span data-ttu-id="40b2f-103">既定では、インターチェンジのメッセージが受信ポートのマッピング フェーズで失敗すると、インターチェンジ全体が中断されます。</span><span class="sxs-lookup"><span data-stu-id="40b2f-103">By default, when a message in an interchange fails at the mapping phase of a receive port, the entire interchange is suspended.</span></span> <span data-ttu-id="40b2f-104">この動作を変更するにはという名前のプロパティを追加することによって**BTS です。SuspendMessageOnMapFailure**をメッセージ コンテキストとするコンテキスト プロパティの値を設定して`True`パイプライン コンポーネントからです。</span><span class="sxs-lookup"><span data-stu-id="40b2f-104">You can change this behavior by adding a property named **BTS.SuspendMessageOnMapFailure** to the message context, and by setting the value of the context property to `True` from a pipeline component.</span></span> <span data-ttu-id="40b2f-105">このプロパティを `True` に設定すると、エンド ポイント マネージャーはマッピングの間に失敗したメッセージを保留キューに格納し、インターチェンジの残りのメッセージの処理を続けます。</span><span class="sxs-lookup"><span data-stu-id="40b2f-105">When this property is set to `True`, the end point manager places the message that failed during mapping in the suspended queue and continues to process remaining messages in the interchange.</span></span>  
  
 <span data-ttu-id="40b2f-106">次のコードの値の設定、 **SuspendMessageOnFailure**プロパティを True にします。</span><span class="sxs-lookup"><span data-stu-id="40b2f-106">The following code sets the value of the **SuspendMessageOnFailure** property to True.</span></span>  
  
```  
  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
    bool bSuspend = true;  
    inmsg.Context.Write("SuspendMessageOnMappingFailure", "http://schemas.microsoft.com/BizTalk/2003/system-properties", bSuspend);   
    …  
}  
  
```