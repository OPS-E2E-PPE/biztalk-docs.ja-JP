---
title: パフォーマンス条件の設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 181011d1-aa74-43fe-b05a-30b043956d70
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f6cd5c7b733ec85eb08acdc506d816d1a3fb1ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305669"
---
# <a name="establishing-performance-criteria"></a><span data-ttu-id="d78a1-102">パフォーマンス条件の設定</span><span class="sxs-lookup"><span data-stu-id="d78a1-102">Establishing Performance Criteria</span></span>
<span data-ttu-id="d78a1-103">BizTalk Server ソリューションのパフォーマンスの目標は、通常、2 つのカテゴリ、スループットまたは待機時間のいずれかに分類されます。</span><span class="sxs-lookup"><span data-stu-id="d78a1-103">The performance goals of a BizTalk Server solution typically fall into one of two categories, throughput or latency.</span></span> <span data-ttu-id="d78a1-104">このトピックでは、スループットまたは BizTalk Server ソリューションの待機時間を評価するときに考慮すべき要因について説明します。</span><span class="sxs-lookup"><span data-stu-id="d78a1-104">This topic describes the factors that should be considered when evaluating the throughput or latency of a BizTalk Server solution.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d78a1-105">多くの場合、スループットまたは BizTalk Server ソリューションの待機時間を最適化するには、目標が矛盾するを表します。</span><span class="sxs-lookup"><span data-stu-id="d78a1-105">Optimizing throughput or latency of a BizTalk Server solution often represents conflicting goals.</span></span> <span data-ttu-id="d78a1-106">向上させることが、バッチ サイズを増やすことで、ファイルのスループットの受信アダプターが、待機時間が短縮するとします。</span><span class="sxs-lookup"><span data-stu-id="d78a1-106">For example, you might improve the throughput of the file receive adapter by increasing the batch size, but doing so would reduce latency.</span></span> <span data-ttu-id="d78a1-107">このシナリオでは、アダプターが、特定のメッセージのエンド ツー エンドの待機時間がさらに削減されます、大きいバッチ サイズのメッセージを蓄積する時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="d78a1-107">In this scenario the adapter takes longer to accumulate messages for a larger batch size, which in turn will reduce end-to-end latency for a given message.</span></span>  
  
## <a name="factors-affecting-throughput-of-a-biztalk-server-solution"></a><span data-ttu-id="d78a1-108">BizTalk Server ソリューションのスループットに影響する要因</span><span class="sxs-lookup"><span data-stu-id="d78a1-108">Factors affecting throughput of a BizTalk Server solution</span></span>  
 <span data-ttu-id="d78a1-109">**スループット**- BizTalk Server ソリューションは、指定された時間間隔内で処理できるドキュメントの数として広く測定します。</span><span class="sxs-lookup"><span data-stu-id="d78a1-109">**Throughput**- Broadly measured as the number of documents that a BizTalk Server solution can process within a given time interval.</span></span>  
  
 <span data-ttu-id="d78a1-110">スループットに影響する要因は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d78a1-110">Factors that affect throughput include:</span></span>  
  
-   <span data-ttu-id="d78a1-111">**メッセージ サイズ**– メッセージ マップに変換され、マッピング操作中に、ファイル システムにバッファリングするように、十分な大きさが場合に特にサイズの大きいメッセージが小さいメッセージより多くのオーバーヘッドを消費します。</span><span class="sxs-lookup"><span data-stu-id="d78a1-111">**Message size** – Larger messages consume more overhead than smaller messages, especially if the messages are transformed with a map and are large enough so that they are buffered to the file system during the mapping operation.</span></span> <span data-ttu-id="d78a1-112">メッセージのサイズが BizTalk Server のパフォーマンスに与える影響の詳細については、次を参照してください。[どのように BizTalk Server プロセス サイズの大きいメッセージ](http://go.microsoft.com/fwlink/?LinkId=139293)(http://go.microsoft.com/fwlink/?LinkId=139293)します。</span><span class="sxs-lookup"><span data-stu-id="d78a1-112">For more information about how message size affects BizTalk Server performance, see [How BizTalk Server Processes Large Messages](http://go.microsoft.com/fwlink/?LinkId=139293) (http://go.microsoft.com/fwlink/?LinkId=139293).</span></span>  
  
-   <span data-ttu-id="d78a1-113">**メッセージ形式**-2 つの主な形式、XML ファイルまたはフラット ファイルのいずれかで BizTalk Server にメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="d78a1-113">**Message format** - Messages are received into BizTalk Server in one of two primary formats, XML files or flat files.</span></span> <span data-ttu-id="d78a1-114">フラット ファイルは、BizTalk メッセージング エンジンによって処理される XML 形式に変換する必要があります、ために、フラット ファイルの処理によって追加のオーバーヘッドが発生します。</span><span class="sxs-lookup"><span data-stu-id="d78a1-114">Because flat files must be translated into the XML format to be processed by the BizTalk Messaging engine, additional overhead is incurred by the processing of flat files.</span></span>  
  
-   <span data-ttu-id="d78a1-115">**アダプターの要件**– 別のアダプターは、さまざまなパフォーマンス機能を頻繁があります。</span><span class="sxs-lookup"><span data-stu-id="d78a1-115">**Adapter requirements** – Different adapters frequently have varying performance capabilities.</span></span> <span data-ttu-id="d78a1-116">たとえば、MSDTC トランザクション サポートが必要なアダプターでは、MSDTC トランザクションを使用しないアダプターと比較して、追加のオーバーヘッド削減/パフォーマンスが発生します。</span><span class="sxs-lookup"><span data-stu-id="d78a1-116">For example, adapters that require MSDTC transaction support will incur additional overhead/reduced performance as compared to an adapter that does not use MSDTC transactions.</span></span> <span data-ttu-id="d78a1-117">BizTalk ソリューションで使用されるアダプターは、取引先パートナーの要件や内部のビジネス ニーズに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="d78a1-117">Adapters used by the BizTalk solution will vary depending on your trading partner’s requirements and/or internal business needs.</span></span>  
  
-   <span data-ttu-id="d78a1-118">**オーケストレーションの処理要件**: オーケストレーションがカプセル化するための優れた柔軟性を提供し、BizTalk で受信したメッセージにビジネス プロセスを適用します。</span><span class="sxs-lookup"><span data-stu-id="d78a1-118">**Orchestration processing requirements** – Orchestrations provide great flexibility for encapsulating and applying business processes to messages received by BizTalk.</span></span> <span data-ttu-id="d78a1-119">同時に、オーケストレーションは、オーバーヘッドで、BizTalk Server ソリューションのスループットを推定する際に考慮する必要を使用します。</span><span class="sxs-lookup"><span data-stu-id="d78a1-119">At the same time, orchestrations consume overhead, which must be considered when estimating the throughput of a BizTalk Server solution.</span></span>  
  
-   <span data-ttu-id="d78a1-120">**ピーク負荷要件**– 測定規則的でドキュメント処理の大部分は必ずしも発生しません。</span><span class="sxs-lookup"><span data-stu-id="d78a1-120">**Peak load requirements** – Most document processing does not necessarily occur in a measured orderly fashion.</span></span> <span data-ttu-id="d78a1-121">など、BizTalk Server ソリューションは、営業日の終了時に、その処理負荷の大きな割合を維持する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d78a1-121">For example, a BizTalk Server solution may sustain a large percentage of its processing load at the close of a business day.</span></span> <span data-ttu-id="d78a1-122">したがってピーク負荷要件と、BizTalk Server ソリューションの最大持続可能なスループット (MST) が考慮するスループットの条件を確立するときにします。</span><span class="sxs-lookup"><span data-stu-id="d78a1-122">Therefore peak load requirements and the Maximum Sustainable Throughput (MST) of a BizTalk Server solution should be taken into account when establishing throughput criteria.</span></span> <span data-ttu-id="d78a1-123">BizTalk Server ソリューションの MST を測定する詳細については、次を参照してください[最大持続可能なエンジン スループットの測定](http://go.microsoft.com/fwlink/?LinkID=154388)(http://go.microsoft.com/fwlink/?LinkID=154388)と[を測定する最大の追跡スループット](http://go.microsoft.com/fwlink/?LinkID=153815)。 (http://go.microsoft.com/fwlink/?LinkID=153815).</span><span class="sxs-lookup"><span data-stu-id="d78a1-123">For more information about measuring the MST of a BizTalk Server solution, see [Measuring Maximum Sustainable Engine Throughput](http://go.microsoft.com/fwlink/?LinkID=154388) (http://go.microsoft.com/fwlink/?LinkID=154388) and [Measuring Maximum Sustainable Tracking Throughput](http://go.microsoft.com/fwlink/?LinkID=153815) (http://go.microsoft.com/fwlink/?LinkID=153815).</span></span>  
  
-   <span data-ttu-id="d78a1-124">**ドキュメント追跡の要件**– ドキュメントの追跡は、システムで追加のオーバーヘッドを適用します。</span><span class="sxs-lookup"><span data-stu-id="d78a1-124">**Document tracking requirements** – Document tracking imposes additional overhead on the system.</span></span> <span data-ttu-id="d78a1-125">ドキュメント追跡の要件は、BizTalk ソリューションのスループット目標を推定するときに、主要な考慮事項にすることがあります。</span><span class="sxs-lookup"><span data-stu-id="d78a1-125">Document tracking requirements should be a primary consideration when estimating the throughput goals of a BizTalk solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d78a1-126">参照</span><span class="sxs-lookup"><span data-stu-id="d78a1-126">See Also</span></span>  
 [<span data-ttu-id="d78a1-127">BizTalk Server のパフォーマンス テスト手法</span><span class="sxs-lookup"><span data-stu-id="d78a1-127">BizTalk Server Performance Testing Methodology</span></span>](../technical-guides/biztalk-server-performance-testing-methodology.md)