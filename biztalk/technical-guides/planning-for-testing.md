---
title: テストの計画 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ca2f5f29-9eea-4f4d-9781-75c231db4605
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12bdf5f35d5d612ec077ebdac83339c5a6838109
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302362"
---
# <a name="planning-for-testing"></a><span data-ttu-id="b6170-102">テストの計画</span><span class="sxs-lookup"><span data-stu-id="b6170-102">Planning for Testing</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b6170-103">テストは、単体テスト、機能テスト、ロード テスト、および可用性のテストを含むいくつかのカテゴリに分類できます。</span><span class="sxs-lookup"><span data-stu-id="b6170-103"> testing can be divided into several categories including unit testing, functional testing, load testing, and availability testing.</span></span> <span data-ttu-id="b6170-104">このトピックでは、ユニットとロード テストと各を計画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b6170-104">This topic describes unit and load testing and how to plan for each.</span></span>  
  
## <a name="planning-for-unit-testing"></a><span data-ttu-id="b6170-105">単体テストの計画</span><span class="sxs-lookup"><span data-stu-id="b6170-105">Planning for Unit Testing</span></span>  
 <span data-ttu-id="b6170-106">単体テストは、その個々 のコード単位の検証に使用するプロシージャが、設計どおりに機能します。</span><span class="sxs-lookup"><span data-stu-id="b6170-106">Unit testing is a procedure used to validate that individual units of code are working as designed.</span></span> <span data-ttu-id="b6170-107">単体テストできると見なすこと「の障害対応」のテスト: ソフトウェアは、さまざまな条件で必要な機能を実行でき、これらの条件で発生したエラーをソフトウェアで処理しますか?</span><span class="sxs-lookup"><span data-stu-id="b6170-107">Unit testing can be thought of as "break/fix" testing: Does the software perform the desired functionality under different conditions and can the software handle errors that occur under these conditions?</span></span>  
  
 <span data-ttu-id="b6170-108">単体テストは通常、個々 のコンポーネントで実行される、ために、関連付けられているテスト ベッドは、実稼働環境の処理能力必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b6170-108">Since unit testing is typically performed on individual components, the associated test bed does not need the processing capabilities of an actual production environment.</span></span> <span data-ttu-id="b6170-109">このため、ハードウェア リソースを大幅に削減を必要とする仮想サーバー環境での単体テストの実行を検討してください。</span><span class="sxs-lookup"><span data-stu-id="b6170-109">For this reason, you should consider performing unit testing in a Virtual Server environment, which requires considerably fewer hardware resources.</span></span>  
  
 <span data-ttu-id="b6170-110">単体テストの仮想化環境で実行できるもう 1 つの側面をステージングするとします。</span><span class="sxs-lookup"><span data-stu-id="b6170-110">Another aspect of unit testing that may be performed in a virtualized environment is staging.</span></span> <span data-ttu-id="b6170-111">ステージングとは、単体テストの BizTalk ソリューションの実際の展開のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="b6170-111">Staging is the process of unit testing the actual deployment of a BizTalk solution.</span></span> <span data-ttu-id="b6170-112">使用できるハードウェア リソースを最大限には、ステージング環境の仮想サーバーを使用して検討してください。</span><span class="sxs-lookup"><span data-stu-id="b6170-112">To maximize available hardware resources, consider using Virtual Server for your staging environment.</span></span>  
  
 <span data-ttu-id="b6170-113">使用しての詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]仮想環境で、次を参照してください。[を使用して仮想サーバー中に、リリース管理プロセス](../technical-guides/planning-the-development-testing-staging-and-production-environments.md#BKMK_VirtualServ)です。</span><span class="sxs-lookup"><span data-stu-id="b6170-113">For more information about using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a virtual environment, see [Using Virtual Server During the Release Management Process](../technical-guides/planning-the-development-testing-staging-and-production-environments.md#BKMK_VirtualServ).</span></span> <span data-ttu-id="b6170-114">単体テストの BizTalk ソリューションに役立つツールについては、次を参照してください。[テスト用ツール](~/technical-guides/tools-for-testing.md)です。</span><span class="sxs-lookup"><span data-stu-id="b6170-114">For information about tools that may be useful for unit testing a BizTalk solution, see [Tools for Testing](~/technical-guides/tools-for-testing.md).</span></span> <span data-ttu-id="b6170-115">単体テストを実行するための考慮事項のチェックリストについては、次を参照してください。[単体テストを実行する](../technical-guides/performing-unit-testing.md)です。</span><span class="sxs-lookup"><span data-stu-id="b6170-115">For a checklist of considerations for performing unit testing see [Performing Unit Testing](../technical-guides/performing-unit-testing.md).</span></span>  
  
## <a name="planning-for-load-testing"></a><span data-ttu-id="b6170-116">ロード テストの計画</span><span class="sxs-lookup"><span data-stu-id="b6170-116">Planning for Load Testing</span></span>  
 <span data-ttu-id="b6170-117">ロード テストは、維持可能な最大のパフォーマンスを測定し、BizTalk ソリューションのパフォーマンスを追跡し、ソリューションのスループットを抑制するボトルネックを削除することで維持可能な最大のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="b6170-117">Load testing is the process of measuring maximum sustainable performance and maximum sustainable tracking performance of a BizTalk solution and then removing bottlenecks that inhibit the throughput of the solution.</span></span> <span data-ttu-id="b6170-118">ロード テストとからのボトルネックを解消の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください、 [BizTalk Server 2009 パフォーマンス ガイド](http://go.microsoft.com/fwlink/?LinkID=150492)(http://go.microsoft.com/fwlink/?LinkID=150492)。</span><span class="sxs-lookup"><span data-stu-id="b6170-118">For more information about load testing and removing bottlenecks from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution, see the [BizTalk Server 2009 Performance Guide](http://go.microsoft.com/fwlink/?LinkID=150492) (http://go.microsoft.com/fwlink/?LinkID=150492).</span></span>  
  
 <span data-ttu-id="b6170-119">ロード テストの BizTalk ソリューションに役立つツールについては、次を参照してください。[テスト用ツール](~/technical-guides/tools-for-testing.md)です。</span><span class="sxs-lookup"><span data-stu-id="b6170-119">For information about tools that may be useful for load testing a BizTalk solution, see [Tools for Testing](~/technical-guides/tools-for-testing.md).</span></span> <span data-ttu-id="b6170-120">ロード テストに関する考慮事項のチェックリストについては、次を参照してください。[読み込みを実行すると、スループットのテスト](../technical-guides/performing-load-and-throughput-testing.md)です。</span><span class="sxs-lookup"><span data-stu-id="b6170-120">For a checklist of considerations for load testing see [Performing Load and Throughput Testing](../technical-guides/performing-load-and-throughput-testing.md).</span></span>  
  
## <a name="plan-to-test-for-the-lifetime-of-the-solution"></a><span data-ttu-id="b6170-121">ソリューションの有効期間のテスト計画します。</span><span class="sxs-lookup"><span data-stu-id="b6170-121">Plan to Test for the Lifetime of the Solution</span></span>  
 <span data-ttu-id="b6170-122">単体テストと新機能またはコンポーネントとして、または負荷の増加として発生する可能性がある潜在的な問題を明らかにするためのソリューションの有効期間全体で一般的なテスト計画早い段階で、このソリューションの特に重要なロード テストソリューションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="b6170-122">While unit testing and load testing are particularly important during the early stages of the solution, plan regular testing throughout the lifetime of the solution to uncover potential problems that may occur as load increases or as new functionality or components are added to the solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6170-123">参照</span><span class="sxs-lookup"><span data-stu-id="b6170-123">See Also</span></span>  
 <span data-ttu-id="b6170-124">[BizTalk Server 層の計画](../technical-guides/planning-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="b6170-124">[Planning the BizTalk Server Tier](../technical-guides/planning-the-biztalk-server-tier.md) </span></span>  
 [<span data-ttu-id="b6170-125">チェックリスト: テスト運用の準備</span><span class="sxs-lookup"><span data-stu-id="b6170-125">Checklist: Testing Operational Readiness</span></span>](../technical-guides/checklist-testing-operational-readiness.md)