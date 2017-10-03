---
title: "ロード テストとスループットのテストを実行する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ff86ebd-a77f-4e29-bfea-0306e88bbf67
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3da46b2dc3208208305e60e9efbfadd0c60d7d32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="performing-load-and-throughput-testing"></a><span data-ttu-id="73075-102">ロード テストとスループットのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="73075-102">Performing Load and Throughput Testing</span></span>
<span data-ttu-id="73075-103">必要があります使用可能なパフォーマンスとストレスのテストの実稼働環境に一致する環境です。</span><span class="sxs-lookup"><span data-stu-id="73075-103">You should make available an environment that matches your production environment for performance and stress testing.</span></span> <span data-ttu-id="73075-104">この環境は、すべての標準的なサービスをインストールし、監視エージェントとウイルス対策ソフトウェアなど、実行に必要です。</span><span class="sxs-lookup"><span data-stu-id="73075-104">This environment should have all standard services installed and running, such as monitoring agents and antivirus software.</span></span>  
  
## <a name="how-adding-applications-affects-load"></a><span data-ttu-id="73075-105">アプリケーションを追加すると、負荷にどのように影響する方法</span><span class="sxs-lookup"><span data-stu-id="73075-105">How Adding Applications Affects Load</span></span>  
 <span data-ttu-id="73075-106">また、実稼働環境で同じハードウェア上で実行される他の BizTalk アプリケーションと共に新しい BizTalk アプリケーションをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="73075-106">You should also test new BizTalk applications alongside the other BizTalk applications that are going to run on the same hardware in production.</span></span> <span data-ttu-id="73075-107">これは、新しい BizTalk アプリケーションを実行するコンピューターに追加の負荷を配置するため[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と SQL Server。</span><span class="sxs-lookup"><span data-stu-id="73075-107">This is because the new BizTalk applications put additional load on the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server.</span></span> <span data-ttu-id="73075-108">これは、ホストで使用されるアルゴリズムの制限に照らし合わせて重要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="73075-108">This is especially important in light of the host throttling algorithms that are used in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="73075-109">制限のアルゴリズムが使用可能なリソースの合計数を監視し、新しい BizTalk アプリケーションによって発生する追加の負荷で実行中のすべての BizTalk アプリケーションに影響を与える制限の条件が引き起こされる可能性がありますのでします。</span><span class="sxs-lookup"><span data-stu-id="73075-109">The throttling algorithm monitors total available resources and hence the additional load incurred by a new BizTalk application may induce a throttling condition which affects all running BizTalk applications.</span></span> <span data-ttu-id="73075-110">詳細については、次を参照してください。[どのように BizTalk Server を実装してホスト Throttling](http://go.microsoft.com/fwlink/?LinkId=154389) (http://go.microsoft.com/fwlink/?LinkId=154389)。</span><span class="sxs-lookup"><span data-stu-id="73075-110">For more information, see [How BizTalk Server Implements Host Throttling](http://go.microsoft.com/fwlink/?LinkId=154389) (http://go.microsoft.com/fwlink/?LinkId=154389).</span></span>  
  
## <a name="testing-load-and-determining-recovery-time"></a><span data-ttu-id="73075-111">ロード テストと、復旧時間を決定します。</span><span class="sxs-lookup"><span data-stu-id="73075-111">Testing Load and Determining Recovery Time</span></span>  
 <span data-ttu-id="73075-112">パフォーマンスとストレスを運用環境に配置する前にすべての BizTalk アプリケーションをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="73075-112">You should test all BizTalk applications for performance and stress before you put them into production.</span></span> <span data-ttu-id="73075-113">ピーク時の負荷と予想される負荷に対してテストを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73075-113">You should perform your testing against expected loads and against peak loads.</span></span> <span data-ttu-id="73075-114">BizTalk アプリケーションの最大の維持可能なスループット (MST) を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73075-114">You should determine the maximum sustainable throughput (MST) for the BizTalk application.</span></span> <span data-ttu-id="73075-115">さらに、ピーク ロードから回復するシステムに要する時間を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73075-115">In addition, you should determine how long it takes the system to recover from peak loads.</span></span> <span data-ttu-id="73075-116">場合は、システムは負荷のピーク時から完全に回復は [次へ] のピーク時の負荷が実行されるまで、システムの背後に段階的に離れた位置が表示されますを完全に回復することはできません。</span><span class="sxs-lookup"><span data-stu-id="73075-116">If the system does not fully recover from a peak load before the next peak load occurs, then the system will get progressively farther behind and will not be able to fully recover.</span></span> <span data-ttu-id="73075-117">詳細については、以下をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="73075-117">For more information, see:</span></span>  
  
-   <span data-ttu-id="73075-118">[維持可能な最大のエンジン スループットの測定](http://go.microsoft.com/fwlink/?LinkId=154388)(http://go.microsoft.com/fwlink/?LinkId=154388)</span><span class="sxs-lookup"><span data-stu-id="73075-118">[Measuring Maximum Sustainable Engine Throughput](http://go.microsoft.com/fwlink/?LinkId=154388) (http://go.microsoft.com/fwlink/?LinkId=154388)</span></span>  
  
-   <span data-ttu-id="73075-119">[維持可能な最大の追跡スループットの測定](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815)</span><span class="sxs-lookup"><span data-stu-id="73075-119">[Measuring Maximum Sustainable Tracking Throughput](http://go.microsoft.com/fwlink/?LinkID=153815) (http://go.microsoft.com/fwlink/?LinkID=153815)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73075-120">参照</span><span class="sxs-lookup"><span data-stu-id="73075-120">See Also</span></span>  
 [<span data-ttu-id="73075-121">チェックリスト: テスト運用の準備</span><span class="sxs-lookup"><span data-stu-id="73075-121">Checklist: Testing Operational Readiness</span></span>](../technical-guides/checklist-testing-operational-readiness.md)