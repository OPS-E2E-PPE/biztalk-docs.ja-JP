---
title: 'チェックリスト: 運用準備のテスト |Microsoft Docs'
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
ms.openlocfilehash: 58a10610595b990e6fc2bae1838fa5653a4b2be0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982601"
---
# <a name="checklist-testing-operational-readiness"></a><span data-ttu-id="b7fa8-102">チェックリスト: 運用準備のテスト</span><span class="sxs-lookup"><span data-stu-id="b7fa8-102">Checklist: Testing Operational Readiness</span></span>
<span data-ttu-id="b7fa8-103">運用準備のためのテストは、見落とされがちまたは最小限に抑えるだけが実行される重要な手順です。</span><span class="sxs-lookup"><span data-stu-id="b7fa8-103">Testing for operational readiness is a vital procedure that is often overlooked or is performed only minimally.</span></span> <span data-ttu-id="b7fa8-104">任意のエンタープライズ レベル アプリケーションの重要な要件を徹底的にテストおよび開発したソリューションを使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]例外ではありません。</span><span class="sxs-lookup"><span data-stu-id="b7fa8-104">Thorough testing is a critical requirement of any enterprise-level application, and a solution developed using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is no exception.</span></span> <span data-ttu-id="b7fa8-105">少なくとも、運用環境に BizTalk ソリューションを移行する前に次のテストを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7fa8-105">At a minimum, you should perform the following testing before moving a BizTalk solution into production:</span></span>  


|                                                                                                                                                                                         <span data-ttu-id="b7fa8-106">手順</span><span class="sxs-lookup"><span data-stu-id="b7fa8-106">Steps</span></span>                                                                                                                                                                                          |                                                  <span data-ttu-id="b7fa8-107">リファレンス</span><span class="sxs-lookup"><span data-stu-id="b7fa8-107">Reference</span></span>                                                  |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|
|                                                                                                                                                                                      <span data-ttu-id="b7fa8-108">単体テスト</span><span class="sxs-lookup"><span data-stu-id="b7fa8-108">Unit testing</span></span>                                                                                                                                                                                      |                  [<span data-ttu-id="b7fa8-109">単体テストの実行</span><span class="sxs-lookup"><span data-stu-id="b7fa8-109">Performing Unit Testing</span></span>](../technical-guides/performing-unit-testing.md)                  |
|                                                                                                                                                                                   <span data-ttu-id="b7fa8-110">機能テスト</span><span class="sxs-lookup"><span data-stu-id="b7fa8-110">Functional testing</span></span>                                                                                                                                                                                   |            [<span data-ttu-id="b7fa8-111">機能テストの実行</span><span class="sxs-lookup"><span data-stu-id="b7fa8-111">Performing Functional Testing</span></span>](../technical-guides/performing-functional-testing.md)            |
|                                                                                                                                                                             <span data-ttu-id="b7fa8-112">ボトルネック テストとチューニング</span><span class="sxs-lookup"><span data-stu-id="b7fa8-112">Bottleneck testing and tuning</span></span>                                                                                                                                                                              | [<span data-ttu-id="b7fa8-113">ボトルネック テストとチューニングの実行</span><span class="sxs-lookup"><span data-stu-id="b7fa8-113">Performing Bottleneck Testing and Tuning</span></span>](../technical-guides/performing-bottleneck-testing-and-tuning.md) |
|                                                                                                                                                                 <span data-ttu-id="b7fa8-114">ロード テストとテストの最大持続可能スループット (MST)</span><span class="sxs-lookup"><span data-stu-id="b7fa8-114">Load and maximum sustainable throughput (MST) testing</span></span>                                                                                                                                                                  |   [<span data-ttu-id="b7fa8-115">読み込みとスループット テストの実行</span><span class="sxs-lookup"><span data-stu-id="b7fa8-115">Performing Load and Throughput Testing</span></span>](../technical-guides/performing-load-and-throughput-testing.md)   |
| <span data-ttu-id="b7fa8-116">可用性テスト:</span><span class="sxs-lookup"><span data-stu-id="b7fa8-116">Availability testing:</span></span><br /><br /> <span data-ttu-id="b7fa8-117">-個々 のハードウェア コンポーネントに障害をテストします。</span><span class="sxs-lookup"><span data-stu-id="b7fa8-117">-   Test individual hardware component failure.</span></span><br /><span data-ttu-id="b7fa8-118">-テスト[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]失敗します。</span><span class="sxs-lookup"><span data-stu-id="b7fa8-118">-   Test [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] failure.</span></span><br /><span data-ttu-id="b7fa8-119">-クラスター ノードのフェールオーバーをテストします。</span><span class="sxs-lookup"><span data-stu-id="b7fa8-119">-   Test cluster node failover.</span></span><br /><span data-ttu-id="b7fa8-120">-の回復をテストする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL Server を使用してデータベースのログ配布します。</span><span class="sxs-lookup"><span data-stu-id="b7fa8-120">-   Test recovery of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases using SQL Server log shipping.</span></span> |          [<span data-ttu-id="b7fa8-121">可用性テストの実行</span><span class="sxs-lookup"><span data-stu-id="b7fa8-121">Performing Availability Testing</span></span>](../technical-guides/performing-availability-testing.md)          |

## <a name="in-this-section"></a><span data-ttu-id="b7fa8-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b7fa8-122">In This Section</span></span>  

-   [<span data-ttu-id="b7fa8-123">単体テストの実行</span><span class="sxs-lookup"><span data-stu-id="b7fa8-123">Performing Unit Testing</span></span>](../technical-guides/performing-unit-testing.md)  

-   [<span data-ttu-id="b7fa8-124">機能テストの実行</span><span class="sxs-lookup"><span data-stu-id="b7fa8-124">Performing Functional Testing</span></span>](../technical-guides/performing-functional-testing.md)  

-   [<span data-ttu-id="b7fa8-125">ボトルネック テストとチューニングの実行</span><span class="sxs-lookup"><span data-stu-id="b7fa8-125">Performing Bottleneck Testing and Tuning</span></span>](../technical-guides/performing-bottleneck-testing-and-tuning.md)  

-   [<span data-ttu-id="b7fa8-126">読み込みとスループット テストの実行</span><span class="sxs-lookup"><span data-stu-id="b7fa8-126">Performing Load and Throughput Testing</span></span>](../technical-guides/performing-load-and-throughput-testing.md)  

-   [<span data-ttu-id="b7fa8-127">可用性テストの実行</span><span class="sxs-lookup"><span data-stu-id="b7fa8-127">Performing Availability Testing</span></span>](../technical-guides/performing-availability-testing.md)  

-   [<span data-ttu-id="b7fa8-128">テスト用ツール</span><span class="sxs-lookup"><span data-stu-id="b7fa8-128">Tools for Testing</span></span>](~/technical-guides/tools-for-testing.md)