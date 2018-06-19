---
title: 'チェックリスト: 運用の準備のテスト |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ecdf2609-ba77-4756-a949-ab4e10c54313
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bc8ff5b2b3ca8d629c30b1cb37f83cb7847b2f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299274"
---
# <a name="checklist-testing-operational-readiness"></a><span data-ttu-id="7a349-102">チェックリスト: テスト運用の準備</span><span class="sxs-lookup"><span data-stu-id="7a349-102">Checklist: Testing Operational Readiness</span></span>
<span data-ttu-id="7a349-103">運用の準備のテストでは、見落とされがちまたは最小限に抑えるだけが実行される重要な手順です。</span><span class="sxs-lookup"><span data-stu-id="7a349-103">Testing for operational readiness is a vital procedure that is often overlooked or is performed only minimally.</span></span> <span data-ttu-id="7a349-104">すべてのエンタープライズ レベルのアプリケーションの重要な要件は、徹底的にテストしを使用して、ソリューションの開発[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]例外ではありません。</span><span class="sxs-lookup"><span data-stu-id="7a349-104">Thorough testing is a critical requirement of any enterprise-level application, and a solution developed using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is no exception.</span></span> <span data-ttu-id="7a349-105">少なくとも BizTalk ソリューションを実稼働環境に移行する前に次のテストを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a349-105">At a minimum, you should perform the following testing before moving a BizTalk solution into production:</span></span>  
  
|<span data-ttu-id="7a349-106">手順</span><span class="sxs-lookup"><span data-stu-id="7a349-106">Steps</span></span>|<span data-ttu-id="7a349-107">リファレンス</span><span class="sxs-lookup"><span data-stu-id="7a349-107">Reference</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="7a349-108">単体テスト</span><span class="sxs-lookup"><span data-stu-id="7a349-108">Unit testing</span></span>|[<span data-ttu-id="7a349-109">単体テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a349-109">Performing Unit Testing</span></span>](../technical-guides/performing-unit-testing.md)|  
|<span data-ttu-id="7a349-110">機能テスト</span><span class="sxs-lookup"><span data-stu-id="7a349-110">Functional testing</span></span>|[<span data-ttu-id="7a349-111">機能テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a349-111">Performing Functional Testing</span></span>](../technical-guides/performing-functional-testing.md)|  
|<span data-ttu-id="7a349-112">ボトルネックのテストとチューニング</span><span class="sxs-lookup"><span data-stu-id="7a349-112">Bottleneck testing and tuning</span></span>|[<span data-ttu-id="7a349-113">テストとチューニングのボトルネックを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a349-113">Performing Bottleneck Testing and Tuning</span></span>](../technical-guides/performing-bottleneck-testing-and-tuning.md)|  
|<span data-ttu-id="7a349-114">ロード テストとテストの最大スループット (MST)</span><span class="sxs-lookup"><span data-stu-id="7a349-114">Load and maximum sustainable throughput (MST) testing</span></span>|[<span data-ttu-id="7a349-115">ロード テストとスループットのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a349-115">Performing Load and Throughput Testing</span></span>](../technical-guides/performing-load-and-throughput-testing.md)|  
|<span data-ttu-id="7a349-116">可用性テスト。</span><span class="sxs-lookup"><span data-stu-id="7a349-116">Availability testing:</span></span><br /><br /> <span data-ttu-id="7a349-117">個々 のハードウェア コンポーネントに障害をテストします。</span><span class="sxs-lookup"><span data-stu-id="7a349-117">-   Test individual hardware component failure.</span></span><br /><span data-ttu-id="7a349-118">-テスト[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]失敗します。</span><span class="sxs-lookup"><span data-stu-id="7a349-118">-   Test [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] failure.</span></span><br /><span data-ttu-id="7a349-119">クラスター ノードのフェールオーバーをテストします。</span><span class="sxs-lookup"><span data-stu-id="7a349-119">-   Test cluster node failover.</span></span><br /><span data-ttu-id="7a349-120">回復のテスト[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL Server を使用して、データベースのログ配布します。</span><span class="sxs-lookup"><span data-stu-id="7a349-120">-   Test recovery of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases using SQL Server log shipping.</span></span>|[<span data-ttu-id="7a349-121">可用性テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a349-121">Performing Availability Testing</span></span>](../technical-guides/performing-availability-testing.md)|  
  
## <a name="in-this-section"></a><span data-ttu-id="7a349-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7a349-122">In This Section</span></span>  
  
-   [<span data-ttu-id="7a349-123">単体テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a349-123">Performing Unit Testing</span></span>](../technical-guides/performing-unit-testing.md)  
  
-   [<span data-ttu-id="7a349-124">機能テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a349-124">Performing Functional Testing</span></span>](../technical-guides/performing-functional-testing.md)  
  
-   [<span data-ttu-id="7a349-125">テストとチューニングのボトルネックを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a349-125">Performing Bottleneck Testing and Tuning</span></span>](../technical-guides/performing-bottleneck-testing-and-tuning.md)  
  
-   [<span data-ttu-id="7a349-126">ロード テストとスループットのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a349-126">Performing Load and Throughput Testing</span></span>](../technical-guides/performing-load-and-throughput-testing.md)  
  
-   [<span data-ttu-id="7a349-127">可用性テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a349-127">Performing Availability Testing</span></span>](../technical-guides/performing-availability-testing.md)  
  
-   [<span data-ttu-id="7a349-128">テスト用ツール</span><span class="sxs-lookup"><span data-stu-id="7a349-128">Tools for Testing</span></span>](~/technical-guides/tools-for-testing.md)