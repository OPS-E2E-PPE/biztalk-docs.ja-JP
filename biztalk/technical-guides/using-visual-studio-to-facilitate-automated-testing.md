---
title: Visual Studio を使用して自動テストを行う |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78f622af-08d5-480c-bd5e-f1db52e8d490
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bdcc6f996d48bef8249bffa66d732a9ba20eb01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400278"
---
# <a name="using-visual-studio-to-facilitate-automated-testing"></a><span data-ttu-id="b765b-102">Visual Studio を使用して自動テストを行う</span><span class="sxs-lookup"><span data-stu-id="b765b-102">Using Visual Studio to Facilitate Automated Testing</span></span>
<span data-ttu-id="b765b-103">Visual Studio 2010 は、数百個の同時にサーバー アプリケーションにアクセスするユーザーのプロファイルの読み込みをシミュレートできる強力なロード テストの機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="b765b-103">Visual Studio 2010 provides powerful load test functionality that can simulate a load profile of up to hundreds of users simultaneously accessing a server application.</span></span> <span data-ttu-id="b765b-104">このロード テスト機能は、将来の分析用のデータベースにこれらのメトリックを格納する機能と、選択した主要業績評価指標のリアルタイムのメトリックを提供します。</span><span class="sxs-lookup"><span data-stu-id="b765b-104">This load testing functionality provides real time metrics for selected key performance indicators as well as the ability to store these metrics in a database for future analysis.</span></span> <span data-ttu-id="b765b-105">このセクションでは、Visual Studio ロード テストを実行する BizTalk Server アプリケーションのパフォーマンスを評価するの使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="b765b-105">This section describes the use of Visual Studio Load testing to evaluate the performance of a BizTalk Server application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b765b-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b765b-106">In This Section</span></span>  
  
-   [<span data-ttu-id="b765b-107">ステップ 1: BizTalk Server にドキュメントを送信する単体テストを作成します。</span><span class="sxs-lookup"><span data-stu-id="b765b-107">Step 1: Create a Unit Test to Submit Documents to BizTalk Server</span></span>](../technical-guides/step-1-create-a-unit-test-to-submit-documents-to-biztalk-server.md)  
  
-   [<span data-ttu-id="b765b-108">手順 2:ロード テスト コント ローラーとエージェント コンピュータを構成します。</span><span class="sxs-lookup"><span data-stu-id="b765b-108">Step 2: Configure Load Test Controller and Agent Computers</span></span>](../technical-guides/step-2-configure-load-test-controller-and-agent-computers.md)  
  
-   [<span data-ttu-id="b765b-109">ステップ 3:同時に複数の単体テストを実行するロード テストを作成します。</span><span class="sxs-lookup"><span data-stu-id="b765b-109">Step 3: Create a Load Test to Perform Multiple Unit Tests Simultaneously</span></span>](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md)  
  
-   [<span data-ttu-id="b765b-110">手順 4:ロード テスト用の BizTalk Server 環境を構成します。</span><span class="sxs-lookup"><span data-stu-id="b765b-110">Step 4: Configure BizTalk Server Environment for Load Testing</span></span>](~/technical-guides/step-4-configure-biztalk-server-environment-for-load-testing.md)  
  
-   [<span data-ttu-id="b765b-111">手順 5:維持可能な最大のスループットを判断するステップ ロード パターン テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b765b-111">Step 5: Perform Step Load Pattern Tests to Determine Maximum Sustainable Throughput</span></span>](../technical-guides/step-5-complete-step-load-tests-to-determine-maximum-sustainable-throughput.md)  
  
-   [<span data-ttu-id="b765b-112">手順 6:維持可能な最大のスループットを検証するための持続ロード パターン テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b765b-112">Step 6: Perform Constant Load Pattern Tests to Verify Maximum Sustainable Throughput</span></span>](../technical-guides/step-6-complete-load-pattern-tests-to-verify-maximum-sustainable-throughput.md)