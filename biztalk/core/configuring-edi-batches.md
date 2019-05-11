---
title: EDI バッチの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8be06e5c-603a-4f93-b018-105314666157
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d4ce3d926526b7b7fe17011d30d555566de7cb4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355925"
---
# <a name="configuring-edi-batches"></a><span data-ttu-id="b5e3e-102">EDI バッチの構成</span><span class="sxs-lookup"><span data-stu-id="b5e3e-102">Configuring EDI Batches</span></span>
<span data-ttu-id="b5e3e-103">このセクションのトピックでは、分割を受信する方法について説明や、バッチ インターチェンジ、XML パイプライン経由で保存されたインターチェンジを送信する方法、および外部バッチ リリース メカニズムを実装する方法に保持されます。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-103">The topics in this section describe how to receive a split or preserved batched interchange, how to send a preserved interchange over an XML pipeline, and how to implement an external batch release mechanism.</span></span>  
  
 <span data-ttu-id="b5e3e-104">このセクションのトピックでは、バッチ インターチェンジを送信する方法についての情報は含まれません。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-104">The topics in this section do not contain information on how to send interchanges in batches.</span></span> <span data-ttu-id="b5e3e-105">送信インターチェンジをバッチ処理する方法の詳細については、次を参照してください。 [(X12) をバッチ処理構成](../core/configuring-batching-x12.md)(X12 でエンコードされたメッセージ) のまたは[構成のバッチ処理 (EDIFACT)](../core/configuring-batching-edifact.md) (EDIFACT エンコード メッセージ)。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-105">For more information on how to batch outgoing interchanges, see [Configuring Batching (X12)](../core/configuring-batching-x12.md) (for X12 encoded messages) or [Configuring Batching (EDIFACT)](../core/configuring-batching-edifact.md) (for EDIFACT encoded messages).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b5e3e-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b5e3e-106">In This Section</span></span>  
  
-   [<span data-ttu-id="b5e3e-107">バッチ インターチェンジの分割</span><span class="sxs-lookup"><span data-stu-id="b5e3e-107">Splitting a Batched Interchange</span></span>](../core/splitting-a-batched-interchange.md)  
  
-   [<span data-ttu-id="b5e3e-108">バッチ インターチェンジの保存</span><span class="sxs-lookup"><span data-stu-id="b5e3e-108">Preserving a Batched Interchange</span></span>](../core/preserving-a-batched-interchange.md)  
  
-   [<span data-ttu-id="b5e3e-109">XML 送信パイプラインによる保存されたバッチの送信</span><span class="sxs-lookup"><span data-stu-id="b5e3e-109">Sending a Preserved Batch with an XML Send Pipeline</span></span>](../core/sending-a-preserved-batch-with-an-xml-send-pipeline.md)  
  
-   [<span data-ttu-id="b5e3e-110">外部バッチ リリース メカニズムの実装</span><span class="sxs-lookup"><span data-stu-id="b5e3e-110">Implementing an External Batch Release Mechanism</span></span>](../core/implementing-an-external-batch-release-mechanism.md)  
  
-   [<span data-ttu-id="b5e3e-111">受信トランザクション セットと送信パッチの関連付け</span><span class="sxs-lookup"><span data-stu-id="b5e3e-111">Correlating an Incoming Transaction Set with an Outgoing Batch</span></span>](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md)  
  
## <a name="see-also"></a><span data-ttu-id="b5e3e-112">参照</span><span class="sxs-lookup"><span data-stu-id="b5e3e-112">See Also</span></span>  
 [<span data-ttu-id="b5e3e-113">BizTalk Server EDI ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="b5e3e-113">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)