---
title: Visual Studio を使用して自動テストを容易に |Microsoft ドキュメント
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
ms.openlocfilehash: 43d6e7d9757ccfe0a5c633dab926f2acbec7e5df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302290"
---
# <a name="using-visual-studio-to-facilitate-automated-testing"></a><span data-ttu-id="ada26-102">自動テストを容易にするために Visual Studio を使用します。</span><span class="sxs-lookup"><span data-stu-id="ada26-102">Using Visual Studio to Facilitate Automated Testing</span></span>
<span data-ttu-id="ada26-103">Visual Studio 2010 では、最大数百台のサーバー アプリケーションに同時にアクセスするユーザーのロード プロファイルをシミュレートする強力なロード テスト機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="ada26-103">Visual Studio 2010 provides powerful load test functionality that can simulate a load profile of up to hundreds of users simultaneously accessing a server application.</span></span> <span data-ttu-id="ada26-104">このロード テスト機能は、今後の分析用のデータベースでこれらのメトリックを保存する機能と、選択した主要業績評価指標のリアルタイムのメトリックを提供します。</span><span class="sxs-lookup"><span data-stu-id="ada26-104">This load testing functionality provides real time metrics for selected key performance indicators as well as the ability to store these metrics in a database for future analysis.</span></span> <span data-ttu-id="ada26-105">このセクションでは、Visual Studio ロード テストを実行する BizTalk Server アプリケーションのパフォーマンスを評価するの使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="ada26-105">This section describes the use of Visual Studio Load testing to evaluate the performance of a BizTalk Server application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ada26-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ada26-106">In This Section</span></span>  
  
-   [<span data-ttu-id="ada26-107">手順 1: BizTalk Server にドキュメントを送信する単体テストを作成します。</span><span class="sxs-lookup"><span data-stu-id="ada26-107">Step 1: Create a Unit Test to Submit Documents to BizTalk Server</span></span>](../technical-guides/step-1-create-a-unit-test-to-submit-documents-to-biztalk-server.md)  
  
-   [<span data-ttu-id="ada26-108">手順 2: ロード テスト コント ローラーとエージェント コンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="ada26-108">Step 2: Configure Load Test Controller and Agent Computers</span></span>](../technical-guides/step-2-configure-load-test-controller-and-agent-computers.md)  
  
-   [<span data-ttu-id="ada26-109">手順 3: 複数の単体テストを同時に実行するロード テストを作成します。</span><span class="sxs-lookup"><span data-stu-id="ada26-109">Step 3: Create a Load Test to Perform Multiple Unit Tests Simultaneously</span></span>](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md)  
  
-   [<span data-ttu-id="ada26-110">手順 4: ロード テストのための BizTalk Server 環境を構成します。</span><span class="sxs-lookup"><span data-stu-id="ada26-110">Step 4: Configure BizTalk Server Environment for Load Testing</span></span>](~/technical-guides/step-4-configure-biztalk-server-environment-for-load-testing.md)  
  
-   [<span data-ttu-id="ada26-111">手順 5: が維持可能な最大のスループットを判断するステップ ロード パターンのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="ada26-111">Step 5: Perform Step Load Pattern Tests to Determine Maximum Sustainable Throughput</span></span>](../technical-guides/step-5-complete-step-load-tests-to-determine-maximum-sustainable-throughput.md)  
  
-   [<span data-ttu-id="ada26-112">手順 6: 最大スループットを検証するための持続ロード パターンのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="ada26-112">Step 6: Perform Constant Load Pattern Tests to Verify Maximum Sustainable Throughput</span></span>](../technical-guides/step-6-complete-load-pattern-tests-to-verify-maximum-sustainable-throughput.md)