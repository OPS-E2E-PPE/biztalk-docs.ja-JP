---
title: テストの計画 |Microsoft Docs
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
ms.openlocfilehash: b386ee074538af7960ca39bfb50c25ac59df1dbb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010283"
---
# <a name="planning-for-testing"></a><span data-ttu-id="fc047-102">テストの計画</span><span class="sxs-lookup"><span data-stu-id="fc047-102">Planning for Testing</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="fc047-103">テストは、単体テスト、機能テスト、ロード テスト、および可用性テストを含むいくつかのカテゴリに分類できます。</span><span class="sxs-lookup"><span data-stu-id="fc047-103">testing can be divided into several categories including unit testing, functional testing, load testing, and availability testing.</span></span> <span data-ttu-id="fc047-104">このトピックでは、ユニットとロード テスト、および各を計画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc047-104">This topic describes unit and load testing and how to plan for each.</span></span>  
  
## <a name="planning-for-unit-testing"></a><span data-ttu-id="fc047-105">単体テストの計画</span><span class="sxs-lookup"><span data-stu-id="fc047-105">Planning for Unit Testing</span></span>  
 <span data-ttu-id="fc047-106">単体テストは、その個々 の単位のコードの検証に使用されるプロシージャは設計どおりに取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="fc047-106">Unit testing is a procedure used to validate that individual units of code are working as designed.</span></span> <span data-ttu-id="fc047-107">「障害」テストとしての単体テストを考えることができますソフトウェアは、さまざまな条件下で必要な機能を実行すると、これらの条件下で発生するソフトウェア エラー処理のことができますか?。</span><span class="sxs-lookup"><span data-stu-id="fc047-107">Unit testing can be thought of as "break/fix" testing: Does the software perform the desired functionality under different conditions and can the software handle errors that occur under these conditions?</span></span>  
  
 <span data-ttu-id="fc047-108">個々 のコンポーネントで通常の単体テストが実行されるため、関連付けられているテスト ベッドは実際に運用環境の処理機能必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fc047-108">Since unit testing is typically performed on individual components, the associated test bed does not need the processing capabilities of an actual production environment.</span></span> <span data-ttu-id="fc047-109">このため、ハードウェア リソースを大幅に削減を必要とする仮想サーバー環境での単体テストの実行を検討してください。</span><span class="sxs-lookup"><span data-stu-id="fc047-109">For this reason, you should consider performing unit testing in a Virtual Server environment, which requires considerably fewer hardware resources.</span></span>  
  
 <span data-ttu-id="fc047-110">単体テストの仮想化環境で実行できるもう 1 つの側面をステージングします。</span><span class="sxs-lookup"><span data-stu-id="fc047-110">Another aspect of unit testing that may be performed in a virtualized environment is staging.</span></span> <span data-ttu-id="fc047-111">ステージング環境は、単体テストの BizTalk ソリューションの実際の展開のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="fc047-111">Staging is the process of unit testing the actual deployment of a BizTalk solution.</span></span> <span data-ttu-id="fc047-112">使用可能なハードウェア リソースを最大化するには、ステージング環境用の Virtual Server の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="fc047-112">To maximize available hardware resources, consider using Virtual Server for your staging environment.</span></span>  
  
 <span data-ttu-id="fc047-113">使用しての詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]仮想環境で、[仮想サーバー中にリリース管理プロセスにを使用して](../technical-guides/planning-the-development-testing-staging-and-production-environments.md#BKMK_VirtualServ)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc047-113">For more information about using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a virtual environment, see [Using Virtual Server During the Release Management Process](../technical-guides/planning-the-development-testing-staging-and-production-environments.md#BKMK_VirtualServ).</span></span> <span data-ttu-id="fc047-114">単体テストの BizTalk ソリューションに役立つツールについては、[テスト用ツール](~/technical-guides/tools-for-testing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc047-114">For information about tools that may be useful for unit testing a BizTalk solution, see [Tools for Testing](~/technical-guides/tools-for-testing.md).</span></span> <span data-ttu-id="fc047-115">単体テストを実行するための考慮事項のチェックリストについては、[単体テストを実行する](../technical-guides/performing-unit-testing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc047-115">For a checklist of considerations for performing unit testing see [Performing Unit Testing](../technical-guides/performing-unit-testing.md).</span></span>  
  
## <a name="planning-for-load-testing"></a><span data-ttu-id="fc047-116">ロード テストの計画</span><span class="sxs-lookup"><span data-stu-id="fc047-116">Planning for Load Testing</span></span>  
 <span data-ttu-id="fc047-117">ロード テストは、最大持続可能なパフォーマンスを測定し、BizTalk ソリューションのパフォーマンスを追跡し、ソリューションのスループットを抑制するボトルネックを削除し、維持可能な最大のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="fc047-117">Load testing is the process of measuring maximum sustainable performance and maximum sustainable tracking performance of a BizTalk solution and then removing bottlenecks that inhibit the throughput of the solution.</span></span> <span data-ttu-id="fc047-118">ロード テストと削除からのボトルネックの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください、 [BizTalk Server 2009 パフォーマンス ガイド](http://go.microsoft.com/fwlink/?LinkID=150492)(<http://go.microsoft.com/fwlink/?LinkID=150492>)。</span><span class="sxs-lookup"><span data-stu-id="fc047-118">For more information about load testing and removing bottlenecks from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution, see the [BizTalk Server 2009 Performance Guide](http://go.microsoft.com/fwlink/?LinkID=150492) (<http://go.microsoft.com/fwlink/?LinkID=150492>).</span></span>  
  
 <span data-ttu-id="fc047-119">ロード テストの BizTalk ソリューションに役立つツールについては、[テスト用ツール](~/technical-guides/tools-for-testing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc047-119">For information about tools that may be useful for load testing a BizTalk solution, see [Tools for Testing](~/technical-guides/tools-for-testing.md).</span></span> <span data-ttu-id="fc047-120">ロード テストに関する考慮事項のチェックリストについては、[読み込みを実行すると、スループットのテスト](../technical-guides/performing-load-and-throughput-testing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc047-120">For a checklist of considerations for load testing see [Performing Load and Throughput Testing](../technical-guides/performing-load-and-throughput-testing.md).</span></span>  
  
## <a name="plan-to-test-for-the-lifetime-of-the-solution"></a><span data-ttu-id="fc047-121">有効期間にわたって、ソリューションのテスト計画します。</span><span class="sxs-lookup"><span data-stu-id="fc047-121">Plan to Test for the Lifetime of the Solution</span></span>  
 <span data-ttu-id="fc047-122">単体テストと負荷の増加、または新しい機能またはコンポーネントとして発生する可能性がある潜在的な問題を明らかにするためのソリューションの有効期間全体での一般的なテスト計画、ソリューションの初期段階で特に重要ですがロード テストソリューションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="fc047-122">While unit testing and load testing are particularly important during the early stages of the solution, plan regular testing throughout the lifetime of the solution to uncover potential problems that may occur as load increases or as new functionality or components are added to the solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc047-123">参照</span><span class="sxs-lookup"><span data-stu-id="fc047-123">See Also</span></span>  
 <span data-ttu-id="fc047-124">[BizTalk Server 層の計画](../technical-guides/planning-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="fc047-124">[Planning the BizTalk Server Tier](../technical-guides/planning-the-biztalk-server-tier.md) </span></span>  
 [<span data-ttu-id="fc047-125">チェックリスト: 運用準備のテスト</span><span class="sxs-lookup"><span data-stu-id="fc047-125">Checklist: Testing Operational Readiness</span></span>](../technical-guides/checklist-testing-operational-readiness.md)