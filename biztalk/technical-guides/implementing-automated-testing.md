---
title: テストの自動化を実装する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4ba540e-789d-49bf-af4b-87e6f37ab96f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aee97d5c44ebd32ca5b325af386fb1a8754f5b20
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298050"
---
# <a name="implementing-automated-testing"></a><span data-ttu-id="03911-102">テストの自動化を実装します。</span><span class="sxs-lookup"><span data-stu-id="03911-102">Implementing Automated Testing</span></span>
<span data-ttu-id="03911-103">BizTalk Server ソリューションは、「ミッション クリティカルな」シナリオ、それにより、BizTalk ソリューションは、ビジネスの主要なコンポーネントで多くの場合、展開されます。</span><span class="sxs-lookup"><span data-stu-id="03911-103">BizTalk Server solutions are often deployed in “mission-critical” scenarios, whereby the BizTalk solution is a core component of the business.</span></span> <span data-ttu-id="03911-104">これらのシナリオでは、継続的なパフォーマンスおよび BizTalk の安定性ソリューションの重要なビジネス要件です。BizTalk ソリューションが失敗した場合、関連付けられているダウンタイムのコストが考慮されます。</span><span class="sxs-lookup"><span data-stu-id="03911-104">In these scenarios, the continual performance and stability of the BizTalk solution is a key business requirement; if the BizTalk solution fails, the associated downtime costs are significant.</span></span> <span data-ttu-id="03911-105">このようなシナリオではきわめて重要する BizTalk ソリューション徹底的にテストする実稼働環境にソリューションが配置される前にします。</span><span class="sxs-lookup"><span data-stu-id="03911-105">In such scenarios, it is of paramount importance that the BizTalk solution be thoroughly tested before the solution is placed into production.</span></span> <span data-ttu-id="03911-106">ソリューションを正しくテストに関連するコストが小さダウンタイムがないテストまたはソリューションを十分にテストの結果を比較します。</span><span class="sxs-lookup"><span data-stu-id="03911-106">The costs associated with properly testing the solution are small compared to the downtime costs resulting from not testing or insufficiently testing the solution.</span></span> <span data-ttu-id="03911-107">そのため、BizTalk Server ソリューションのテストは、BizTalk Server ソリューションの展開の最も重要なフェーズではほぼ間違いないです。</span><span class="sxs-lookup"><span data-stu-id="03911-107">Therefore, the testing of a BizTalk Server solution is arguably the most important phase of any BizTalk Server solution deployment.</span></span>  
  
 <span data-ttu-id="03911-108">このセクションでは、実稼働環境でソリューションを実行する前に、BizTalk ソリューションをテストするための適切な方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="03911-108">This section describes the proper methodology for testing a BizTalk solution before running the solution in a production environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="03911-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="03911-109">In This Section</span></span>  
  
-   [<span data-ttu-id="03911-110">テストの重要性が</span><span class="sxs-lookup"><span data-stu-id="03911-110">Why It Is Important to Test</span></span>](../technical-guides/why-it-is-important-to-test.md)  
  
-   [<span data-ttu-id="03911-111">ビルド プロセスを自動化します。</span><span class="sxs-lookup"><span data-stu-id="03911-111">Automating the Build Process</span></span>](../technical-guides/automating-the-build-process.md)  
  
-   [<span data-ttu-id="03911-112">BizUnit を使用して自動テストを容易にするには</span><span class="sxs-lookup"><span data-stu-id="03911-112">Using BizUnit to Facilitate Automated Testing</span></span>](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)  
  
-   [<span data-ttu-id="03911-113">自動テストを容易にするために Visual Studio を使用します。</span><span class="sxs-lookup"><span data-stu-id="03911-113">Using Visual Studio to Facilitate Automated Testing</span></span>](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)