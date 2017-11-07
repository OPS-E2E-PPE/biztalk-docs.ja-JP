---
title: "手順 2: ロード テスト コント ローラーとエージェント コンピューターの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9d937ac-55d8-48fa-bba2-3efe151587b8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75a659d533b68cf525bcd782a2dadce72a6ebb0b
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="step-2-configure-load-test-controller-and-agent-computers"></a><span data-ttu-id="3ac94-102">手順 2: ロード テスト コント ローラーとエージェント コンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="3ac94-102">Step 2: Configure Load Test Controller and Agent Computers</span></span>

## <a name="overview"></a><span data-ttu-id="3ac94-103">概要</span><span class="sxs-lookup"><span data-stu-id="3ac94-103">Overview</span></span>
<span data-ttu-id="3ac94-104">Visual Studio では、ローカルのロード テストの実行で、最大 250 個の仮想ユーザーをシミュレートする負荷を生成できます。</span><span class="sxs-lookup"><span data-stu-id="3ac94-104">Visual Studio can generate load simulating up to 250 virtual users on a local load test run.</span></span> <span data-ttu-id="3ac94-105">250 を超える仮想ユーザーをシミュレートする、またはリモートからテストを開始するコンピューターには、Visual Studio ロード テスト仮想ユーザーが必要です。</span><span class="sxs-lookup"><span data-stu-id="3ac94-105">To simulate more than 250 virtual users and/or to initiate testing from a remote computer requires Visual Studio Load Test Virtual User.</span></span>  
  
 <span data-ttu-id="3ac94-106">すべてのロード テストに実行されるこのガイドでは、2 台のコンピューターから開始されました。</span><span class="sxs-lookup"><span data-stu-id="3ac94-106">All load testing performed for this guide was initiated from two computers:</span></span>  
  
-   <span data-ttu-id="3ac94-107">ロード テスト コント ローラーとロード テスト エージェントの両方として実行されている 1 台のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="3ac94-107">One computer running as both a Load Test Controller and a Load Test Agent.</span></span>  
  
-   <span data-ttu-id="3ac94-108">ロード テストのエージェントのみとして実行されている別のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="3ac94-108">Another computer running as a Load Test Agent only.</span></span>  
  
 <span data-ttu-id="3ac94-109">テストの結果は、SQL Server データベースにリモートでロード テストの結果リポジトリに保存されていました。</span><span class="sxs-lookup"><span data-stu-id="3ac94-109">Test results were stored in a remote load test results repository in a SQL Server database.</span></span>  
  
 <span data-ttu-id="3ac94-110">テスト コント ローラーとテスト エージェントを使用して、ロード テストを複数のテスト コンピューターに分散する方法の詳細については、次を参照してください。[を配布するロード テスト全体で複数テスト マシンを使用してテスト コント ローラーおよび Test Agent](https://msdn.microsoft.com/library/dd728093.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="3ac94-110">For more information about using test controllers and test agents to distribute load tests across multiple test machines, see [Distributing Load Tests Across Multiple Test Machines Using Test Controllers and Test Agents](https://msdn.microsoft.com/library/dd728093.aspx).</span></span>  
  
## <a name="install-and-configure-the-load-test-controller-and-load-test-agents"></a><span data-ttu-id="3ac94-111">インストールし、構成、ロード テスト コント ローラーとロード テスト エージェント</span><span class="sxs-lookup"><span data-stu-id="3ac94-111">Install and Configure the Load Test Controller and Load Test Agents</span></span>  
 <span data-ttu-id="3ac94-112">インストールして、ロード テスト コント ローラーを構成およびテスト エージェントを読み込む、次を参照してください。[のインストールとテスト エージェントを構成](https://docs.microsoft.com/visualstudio/test/lab-management/install-configure-test-agents)です。</span><span class="sxs-lookup"><span data-stu-id="3ac94-112">To install and configure the load test controller and load test agents, see [Install and configure test agents](https://docs.microsoft.com/visualstudio/test/lab-management/install-configure-test-agents).</span></span>
