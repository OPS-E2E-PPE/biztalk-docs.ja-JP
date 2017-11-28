---
title: "送信 EDI メッセージをバッチ処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93a2bd68-4974-4927-938a-8eaf8f007566
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f95ed755dcc709084d52c6fb8b207e9bbd9e866d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="batching-outgoing-edi-messages"></a><span data-ttu-id="caf90-102">送信 EDI メッセージのバッチ処理</span><span class="sxs-lookup"><span data-stu-id="caf90-102">Batching Outgoing EDI Messages</span></span>
<span data-ttu-id="caf90-103">受信側のビジネス パートナーに関連するアグリーメントに対してバッチ処理が有効になっている場合、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では EDI トランザクション セットがバッチ処理されます。</span><span class="sxs-lookup"><span data-stu-id="caf90-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will batch EDI transaction sets if batching has been enabled for the agreement associated with the business partner that will be receiving it.</span></span> <span data-ttu-id="caf90-104">アグリーメントに関する EDI プロパティを設定すると、以下を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="caf90-104">The EDI properties for an agreement enable you to do the following:</span></span>  
  
-   <span data-ttu-id="caf90-105">複数の送信バッチの定義</span><span class="sxs-lookup"><span data-stu-id="caf90-105">Define multiple outgoing batches</span></span>  
  
-   <span data-ttu-id="caf90-106">インターチェンジの定義</span><span class="sxs-lookup"><span data-stu-id="caf90-106">Define the interchange</span></span>  
  
-   <span data-ttu-id="caf90-107">インターチェンジ内のグループの定義</span><span class="sxs-lookup"><span data-stu-id="caf90-107">Define the groups in the interchange</span></span>  
  
-   <span data-ttu-id="caf90-108">バッチ リリース条件の設定</span><span class="sxs-lookup"><span data-stu-id="caf90-108">Set the batch release criteria</span></span>  
  
-   <span data-ttu-id="caf90-109">バッチ アクティベーション条件の設定</span><span class="sxs-lookup"><span data-stu-id="caf90-109">Set the batch activation criteria.</span></span>  
  
 <span data-ttu-id="caf90-110">Microsoft [!INCLUDE[prague](../includes/prague-md.md)] EDI および AS2 を使用すると、EDI インターチェンジの以下の処理が可能になります。</span><span class="sxs-lookup"><span data-stu-id="caf90-110">Microsoft [!INCLUDE[prague](../includes/prague-md.md)] EDI and AS2 enables the following processing of EDI interchanges:</span></span>  
  
-   <span data-ttu-id="caf90-111">EDI インターチェンジにトランザクション セットや受信確認を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="caf90-111">EDI interchanges can include transaction sets and/or acknowledgments.</span></span>  
  
-   <span data-ttu-id="caf90-112">EDI 受信パイプラインは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] による後続処理のためにインターチェンジを XML トランザクション セットに分割するか、インターチェンジを維持して、その受信フォームで [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を通過させることができます。</span><span class="sxs-lookup"><span data-stu-id="caf90-112">The EDI receive pipeline can split an interchange into XML transaction sets for further processing by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], or it can preserve the interchange, passing it through [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in its received form.</span></span>  
  
-   <span data-ttu-id="caf90-113">EDI ルーティング オーケストレーションにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、単一のトランザクション セットをバッチ処理して、複数の送信インターチェンジに分割できます。</span><span class="sxs-lookup"><span data-stu-id="caf90-113">The EDI routing orchestration enables [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to batch a single transaction set into more than one outgoing interchange.</span></span>  
  
-   <span data-ttu-id="caf90-114">EDI バッチ処理オーケストレーションは、XML トランザクション セットを EDI インターチェンジにアセンブルして、アグリーメントの EDI プロパティに基づいてインターチェンジを検証し、配布します。</span><span class="sxs-lookup"><span data-stu-id="caf90-114">The EDI batching orchestration assembles XML transaction sets into an EDI interchange, and validates and delivers the interchange according to an agreement's EDI properties.</span></span>  
  
 <span data-ttu-id="caf90-115">インターチェンジと呼ばれる EDI バッチには、メッセージ グループが含まれ、メッセージ グループには、個々のメッセージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="caf90-115">EDI batches, called interchanges, contain message groups, and message groups contain individual messages.</span></span> <span data-ttu-id="caf90-116">送信バッチには、複数のグループを含めることができますが、ドキュメントの種類ごとに含められるグループは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="caf90-116">Outgoing batches can include multiple groups, but only one group per document type.</span></span> <span data-ttu-id="caf90-117">グループには、複数のトランザクション セットを含めることができますが、各トランザクション セットのドキュメントの種類が同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="caf90-117">A group can contain multiple transaction sets, but each must have the same document type.</span></span> <span data-ttu-id="caf90-118">メッセージ エンベロープは、個々のトランザクション セット、個々のグループ、およびインターチェンジ全体をラップするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="caf90-118">Message envelopes are used to wrap individual transaction sets, individual groups, and the entire interchange.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="caf90-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="caf90-119">In This Section</span></span>  
  
-   [<span data-ttu-id="caf90-120">送信バッチの構成</span><span class="sxs-lookup"><span data-stu-id="caf90-120">Configuring an Outgoing Batch</span></span>](../core/configuring-an-outgoing-batch.md)  
  
-   [<span data-ttu-id="caf90-121">バッチ EDI インターチェンジをアセンブル</span><span class="sxs-lookup"><span data-stu-id="caf90-121">Assembling a Batched EDI Interchange</span></span>](../core/assembling-a-batched-edi-interchange.md)  
  
-   [<span data-ttu-id="caf90-122">保存されたバッチ インターチェンジを送信します。</span><span class="sxs-lookup"><span data-stu-id="caf90-122">Sending a Preserved Batch Interchange</span></span>](../core/sending-a-preserved-batch-interchange.md)