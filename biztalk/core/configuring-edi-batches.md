---
title: "EDI バッチの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8be06e5c-603a-4f93-b018-105314666157
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 765dfe5d687c55a763dfd3ff8945606fd32d3239
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-edi-batches"></a><span data-ttu-id="d7b70-102">EDI バッチの構成</span><span class="sxs-lookup"><span data-stu-id="d7b70-102">Configuring EDI Batches</span></span>
<span data-ttu-id="d7b70-103">このセクションのトピックでは、分割済みまたは保存済みのバッチ化されたインターチェンジを受信する方法、XML パイプライン経由で保存済みインターチェンジを送信する方法、および外部バッチ リリース メカニズムを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7b70-103">The topics in this section describe how to receive a split or preserved batched interchange, how to send a preserved interchange over an XML pipeline, and how to implement an external batch release mechanism.</span></span>  
  
 <span data-ttu-id="d7b70-104">このセクションのトピックには、バッチでインターチェンジを送信する方法に関する情報は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="d7b70-104">The topics in this section do not contain information on how to send interchanges in batches.</span></span> <span data-ttu-id="d7b70-105">送信インターチェンジをバッチ処理する方法の詳細については、次を参照してください。 [(X12) をバッチ処理構成](../core/configuring-batching-x12.md)(X12 でエンコードされたメッセージ) のまたは[構成のバッチ処理 (EDIFACT)](../core/configuring-batching-edifact.md) (EDIFACT エンコード メッセージ)。</span><span class="sxs-lookup"><span data-stu-id="d7b70-105">For more information on how to batch outgoing interchanges, see [Configuring Batching (X12)](../core/configuring-batching-x12.md) (for X12 encoded messages) or [Configuring Batching (EDIFACT)](../core/configuring-batching-edifact.md) (for EDIFACT encoded messages).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d7b70-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d7b70-106">In This Section</span></span>  
  
-   [<span data-ttu-id="d7b70-107">バッチ インターチェンジの分割</span><span class="sxs-lookup"><span data-stu-id="d7b70-107">Splitting a Batched Interchange</span></span>](../core/splitting-a-batched-interchange.md)  
  
-   [<span data-ttu-id="d7b70-108">バッチ インターチェンジの保存</span><span class="sxs-lookup"><span data-stu-id="d7b70-108">Preserving a Batched Interchange</span></span>](../core/preserving-a-batched-interchange.md)  
  
-   [<span data-ttu-id="d7b70-109">XML 送信パイプラインによる保存されたバッチを送信します。</span><span class="sxs-lookup"><span data-stu-id="d7b70-109">Sending a Preserved Batch with an XML Send Pipeline</span></span>](../core/sending-a-preserved-batch-with-an-xml-send-pipeline.md)  
  
-   [<span data-ttu-id="d7b70-110">外部バッチ リリース メカニズムを実装します。</span><span class="sxs-lookup"><span data-stu-id="d7b70-110">Implementing an External Batch Release Mechanism</span></span>](../core/implementing-an-external-batch-release-mechanism.md)  
  
-   [<span data-ttu-id="d7b70-111">送信バッチの受信のトランザクション セットの関連付け</span><span class="sxs-lookup"><span data-stu-id="d7b70-111">Correlating an Incoming Transaction Set with an Outgoing Batch</span></span>](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md)  
  
## <a name="see-also"></a><span data-ttu-id="d7b70-112">参照</span><span class="sxs-lookup"><span data-stu-id="d7b70-112">See Also</span></span>  
 [<span data-ttu-id="d7b70-113">開発および BizTalk Server EDI ソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="d7b70-113">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)