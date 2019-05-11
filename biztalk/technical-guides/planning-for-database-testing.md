---
title: データベースのテストの計画 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a4cf5e1f-a960-4702-a050-a2cdacddcbca
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 298949e7d8f5fa30578f98cfd41dbab158893396
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394608"
---
# <a name="planning-for-database-testing"></a><span data-ttu-id="34891-102">データベースのテストの計画</span><span class="sxs-lookup"><span data-stu-id="34891-102">Planning for Database Testing</span></span>
<span data-ttu-id="34891-103">Ultimate の成功または失敗のソリューションで目立つようを図、BizTalk ソリューションの徹底的な負荷をテストします。</span><span class="sxs-lookup"><span data-stu-id="34891-103">Thorough stress/load testing of a BizTalk solution figures prominently in the ultimate success or failure of the solution.</span></span> <span data-ttu-id="34891-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンスのためのパフォーマンスに依存しているが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、テストしソリューションのテストに頻繁に重点を置いています BizTalk の最適化、および実行しているコンピューターの最適化[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]が収容[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="34891-104">Since [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance is so dependent on the performance of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, testing and optimization of a BizTalk solution frequently focuses on testing and optimization of the computers running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] that house the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
## <a name="considerations-when-planning-for-database-testing"></a><span data-ttu-id="34891-105">データベースのテストを計画する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="34891-105">Considerations When Planning for Database Testing</span></span>  
 <span data-ttu-id="34891-106">データベースのテストを計画するときは、次を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="34891-106">Consider the following when planning for database testing:</span></span>  
  
1. <span data-ttu-id="34891-107">**テスト環境が運用環境をできるだけと一致することを確認します。**</span><span class="sxs-lookup"><span data-stu-id="34891-107">**Ensure that the test environment matches the production environment as closely as possible.**</span></span> <span data-ttu-id="34891-108">単体テストの Microsoft HYPER-V Server 2008 などの仮想環境を使用することはまったく問題ありません。ただし、すべてのロード/ストレス テストは、可能な限り、最終的な運用環境に一致するハードウェアに対して実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34891-108">Using a virtual environment such as Microsoft Hyper-V Server 2008 for unit testing is perfectly acceptable; however, all load/stress testing should be performed against hardware that matches the final production environment as closely as possible.</span></span>  
  
2. <span data-ttu-id="34891-109">**維持可能な最大のスループットと、BizTalk Server システムの維持可能な最大の追跡スループットを測定する**します。</span><span class="sxs-lookup"><span data-stu-id="34891-109">**Plan to measure maximum sustainable throughput and maximum sustainable tracking throughput of the BizTalk Server system**.</span></span> <span data-ttu-id="34891-110">維持可能な最大のスループットは、実稼働環境で BizTalk Server システムを無制限に処理できるメッセージ トラフィックの最大負荷として測定されます。</span><span class="sxs-lookup"><span data-stu-id="34891-110">Maximum sustainable throughput is measured as the highest load of message traffic that the BizTalk Server system can handle indefinitely in production.</span></span> <span data-ttu-id="34891-111">BizTalk Server ヘルプで、次のトピックの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="34891-111">Follow the steps in the following topics in BizTalk Server Help:</span></span>  
  
   - <span data-ttu-id="34891-112">[維持可能な最大のエンジン スループットの測定](http://go.microsoft.com/fwlink/?LinkID=154388)(http://go.microsoft.com/fwlink/?LinkID=154388)します。</span><span class="sxs-lookup"><span data-stu-id="34891-112">[Measuring Maximum Sustainable Engine Throughput](http://go.microsoft.com/fwlink/?LinkID=154388) (http://go.microsoft.com/fwlink/?LinkID=154388).</span></span>  
  
   - <span data-ttu-id="34891-113">[維持可能な最大の追跡スループットの測定](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815)します。</span><span class="sxs-lookup"><span data-stu-id="34891-113">[Measuring Maximum Sustainable Tracking Throughput](http://go.microsoft.com/fwlink/?LinkID=153815) (http://go.microsoft.com/fwlink/?LinkID=153815).</span></span>  
  
     <span data-ttu-id="34891-114">これらのトピックでは、システム、測定する必要があるパラメーター、MST をテストするときに実行する一般的な推奨事項に対する負荷を生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="34891-114">These topics describe the methodology for generating load against the system, the parameters that should be measured, and general recommendations to follow when testing MST.</span></span>  
  
3. <span data-ttu-id="34891-115">**方法の理解 BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="34891-115">**Understand the implications of how BizTalk Server**</span></span>  
    <span data-ttu-id="34891-116">**ホスト制限を実装します。**</span><span class="sxs-lookup"><span data-stu-id="34891-116">**implements host throttling.**</span></span> <span data-ttu-id="34891-117">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト制限アルゴリズムのワークロードをモデレートしようとしました。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のインスタンスに、ワークロードがホスト インスタンスの容量を超えていないこと、またはいずれかのダウン ストリーム ホスト インスタンスをホストします。</span><span class="sxs-lookup"><span data-stu-id="34891-117">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host throttling algorithm attempts to moderate the workload of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host instances to ensure that the workload does not exceed the capacity of the host instance or any downstream host instances.</span></span> <span data-ttu-id="34891-118">制限メカニズムは自律的と既定の構成オプションは、大半の適切な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]シナリオを処理します。</span><span class="sxs-lookup"><span data-stu-id="34891-118">The throttling mechanism is self tuning and the default configuration options are suitable for the majority of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processing scenarios.</span></span> <span data-ttu-id="34891-119">ただし、ロード/ストレス テストを実装する前に、制限メカニズムを理解がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="34891-119">You should, however, have a good understanding of the throttling mechanism before implementing load/stress testing.</span></span> <span data-ttu-id="34891-120">詳細については、次を参照してください。[を最適化するリソースをホストの調整](http://go.microsoft.com/fwlink/?LinkId=155770)(<http://go.microsoft.com/fwlink/?LinkId=155770>) BizTalk Server のヘルプ。</span><span class="sxs-lookup"><span data-stu-id="34891-120">For more information, see [Optimizing Resource Usage Through Host Throttling](http://go.microsoft.com/fwlink/?LinkId=155770) (<http://go.microsoft.com/fwlink/?LinkId=155770>) in BizTalk Server Help.</span></span>