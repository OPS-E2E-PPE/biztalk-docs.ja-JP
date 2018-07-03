---
title: ロード テストとスループットのテストを実行する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ff86ebd-a77f-4e29-bfea-0306e88bbf67
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d4313c073abff7022de99ac1d38375599b6ee43
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966915"
---
# <a name="performing-load-and-throughput-testing"></a><span data-ttu-id="43890-102">ロード テストとスループットのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="43890-102">Performing Load and Throughput Testing</span></span>
<span data-ttu-id="43890-103">必要があります使用可能なパフォーマンスとストレス テスト、運用環境に一致する環境。</span><span class="sxs-lookup"><span data-stu-id="43890-103">You should make available an environment that matches your production environment for performance and stress testing.</span></span> <span data-ttu-id="43890-104">この環境には、すべての標準的なサービスをインストールし、監視エージェントとウイルス対策ソフトウェアなど、実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="43890-104">This environment should have all standard services installed and running, such as monitoring agents and antivirus software.</span></span>  
  
## <a name="how-adding-applications-affects-load"></a><span data-ttu-id="43890-105">アプリケーションを追加すると、負荷にどのように影響する方法</span><span class="sxs-lookup"><span data-stu-id="43890-105">How Adding Applications Affects Load</span></span>  
 <span data-ttu-id="43890-106">運用環境で同じハードウェア上で実行するようになっている他の BizTalk アプリケーションと共に新しい BizTalk アプリケーションをテストすることも必要があります。</span><span class="sxs-lookup"><span data-stu-id="43890-106">You should also test new BizTalk applications alongside the other BizTalk applications that are going to run on the same hardware in production.</span></span> <span data-ttu-id="43890-107">これは、新しい BizTalk アプリケーションを実行しているコンピューターで追加の負荷を配置するため[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と SQL Server。</span><span class="sxs-lookup"><span data-stu-id="43890-107">This is because the new BizTalk applications put additional load on the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server.</span></span> <span data-ttu-id="43890-108">これは、ホストで使用されるアルゴリズムの制限に照らし合わせて重要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="43890-108">This is especially important in light of the host throttling algorithms that are used in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="43890-109">調整アルゴリズムは、合計使用可能なリソースを監視し、そのため、新しい BizTalk アプリケーションで発生する追加の負荷が実行中のすべての BizTalk アプリケーションに影響が制限の条件を誘発可能性があります。</span><span class="sxs-lookup"><span data-stu-id="43890-109">The throttling algorithm monitors total available resources and hence the additional load incurred by a new BizTalk application may induce a throttling condition which affects all running BizTalk applications.</span></span> <span data-ttu-id="43890-110">詳細については、次を参照してください。[どのように BizTalk Server 実装ホスト Throttling](http://go.microsoft.com/fwlink/?LinkId=154389) (<http://go.microsoft.com/fwlink/?LinkId=154389>)。</span><span class="sxs-lookup"><span data-stu-id="43890-110">For more information, see [How BizTalk Server Implements Host Throttling](http://go.microsoft.com/fwlink/?LinkId=154389) (<http://go.microsoft.com/fwlink/?LinkId=154389>).</span></span>  
  
## <a name="testing-load-and-determining-recovery-time"></a><span data-ttu-id="43890-111">ロード テストと復旧時間を決定します。</span><span class="sxs-lookup"><span data-stu-id="43890-111">Testing Load and Determining Recovery Time</span></span>  
 <span data-ttu-id="43890-112">パフォーマンスとストレスを運用環境に配置する前にすべての BizTalk アプリケーションをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="43890-112">You should test all BizTalk applications for performance and stress before you put them into production.</span></span> <span data-ttu-id="43890-113">予想される負荷とピーク時の負荷に対してテストを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43890-113">You should perform your testing against expected loads and against peak loads.</span></span> <span data-ttu-id="43890-114">BizTalk アプリケーションの最大持続可能スループット (MST) を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43890-114">You should determine the maximum sustainable throughput (MST) for the BizTalk application.</span></span> <span data-ttu-id="43890-115">さらに、ピーク ロードから回復するシステムにかかる時間を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43890-115">In addition, you should determine how long it takes the system to recover from peak loads.</span></span> <span data-ttu-id="43890-116">システムが完全にピーク時の負荷から復旧しない場合、[次へ] のピーク時の前に負荷が発生したを実行し、システムの背後にある段階的に離れた受け取ります、完全に回復することはできませんを実行します。</span><span class="sxs-lookup"><span data-stu-id="43890-116">If the system does not fully recover from a peak load before the next peak load occurs, then the system will get progressively farther behind and will not be able to fully recover.</span></span> <span data-ttu-id="43890-117">詳細については、以下をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="43890-117">For more information, see:</span></span>  
  
-   <span data-ttu-id="43890-118">[維持可能な最大のエンジン スループットの測定](http://go.microsoft.com/fwlink/?LinkId=154388)(http://go.microsoft.com/fwlink/?LinkId=154388)</span><span class="sxs-lookup"><span data-stu-id="43890-118">[Measuring Maximum Sustainable Engine Throughput](http://go.microsoft.com/fwlink/?LinkId=154388) (http://go.microsoft.com/fwlink/?LinkId=154388)</span></span>  
  
-   <span data-ttu-id="43890-119">[維持可能な最大の追跡スループットの測定](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815)</span><span class="sxs-lookup"><span data-stu-id="43890-119">[Measuring Maximum Sustainable Tracking Throughput](http://go.microsoft.com/fwlink/?LinkID=153815) (http://go.microsoft.com/fwlink/?LinkID=153815)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43890-120">参照</span><span class="sxs-lookup"><span data-stu-id="43890-120">See Also</span></span>  
 [<span data-ttu-id="43890-121">チェックリスト: 運用準備のテスト</span><span class="sxs-lookup"><span data-stu-id="43890-121">Checklist: Testing Operational Readiness</span></span>](../technical-guides/checklist-testing-operational-readiness.md)