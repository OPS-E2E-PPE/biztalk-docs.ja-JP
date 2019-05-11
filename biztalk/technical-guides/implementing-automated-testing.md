---
title: 自動テストの実装 |Microsoft Docs
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
ms.openlocfilehash: 800a7070c291048f592f21aefb609f0b15781d05
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65270460"
---
# <a name="implementing-automated-testing"></a><span data-ttu-id="2c5f7-102">自動テストの実装</span><span class="sxs-lookup"><span data-stu-id="2c5f7-102">Implementing Automated Testing</span></span>
<span data-ttu-id="2c5f7-103">BizTalk Server ソリューションは、これにより、ビジネスの主要なコンポーネントは、BizTalk ソリューションの「ミッション クリティカルな」のシナリオで多くの場合、デプロイされます。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-103">BizTalk Server solutions are often deployed in “mission-critical” scenarios, whereby the BizTalk solution is a core component of the business.</span></span> <span data-ttu-id="2c5f7-104">これらのシナリオでは、継続的なパフォーマンスと安定性、BizTalk の解決策は、主要なビジネス要件です。BizTalk ソリューションが失敗した場合、重要ではダウンタイムが関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-104">In these scenarios, the continual performance and stability of the BizTalk solution is a key business requirement; if the BizTalk solution fails, the associated downtime costs are significant.</span></span> <span data-ttu-id="2c5f7-105">このようなシナリオは何よりも重要な BizTalk ソリューションのソリューションが運用環境に配置される前に十分にテストします。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-105">In such scenarios, it is of paramount importance that the BizTalk solution be thoroughly tested before the solution is placed into production.</span></span> <span data-ttu-id="2c5f7-106">正しくソリューションのテストに関連するコストは、ダウンタイムがないテストまたはソリューションを十分にテストの結果に比べると小さいです。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-106">The costs associated with properly testing the solution are small compared to the downtime costs resulting from not testing or insufficiently testing the solution.</span></span> <span data-ttu-id="2c5f7-107">そのため、BizTalk Server ソリューションのテストは、BizTalk Server ソリューションの展開の最も重要なフェーズではほぼ間違いなくです。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-107">Therefore, the testing of a BizTalk Server solution is arguably the most important phase of any BizTalk Server solution deployment.</span></span>  
  
 <span data-ttu-id="2c5f7-108">このセクションでは、運用環境でソリューションを実行する前に、BizTalk ソリューションをテストするための適切な方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c5f7-108">This section describes the proper methodology for testing a BizTalk solution before running the solution in a production environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2c5f7-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2c5f7-109">In This Section</span></span>  
  
-   [<span data-ttu-id="2c5f7-110">テストが重要な理由</span><span class="sxs-lookup"><span data-stu-id="2c5f7-110">Why It Is Important to Test</span></span>](../technical-guides/why-it-is-important-to-test.md)  
  
-   [<span data-ttu-id="2c5f7-111">ビルド プロセスの自動化</span><span class="sxs-lookup"><span data-stu-id="2c5f7-111">Automating the Build Process</span></span>](../technical-guides/automating-the-build-process.md)  
  
-   [<span data-ttu-id="2c5f7-112">自動テストを容易にするための BizUnit の使用</span><span class="sxs-lookup"><span data-stu-id="2c5f7-112">Using BizUnit to Facilitate Automated Testing</span></span>](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)  
  
-   [<span data-ttu-id="2c5f7-113">自動テストの容易化のための Visual Studio の使用</span><span class="sxs-lookup"><span data-stu-id="2c5f7-113">Using Visual Studio to Facilitate Automated Testing</span></span>](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)