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
ms.openlocfilehash: 0f931a05796856816e19b53ff5cba9f53b48c3e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-configure-load-test-controller-and-agent-computers"></a><span data-ttu-id="13b80-102">手順 2: ロード テスト コント ローラーとエージェント コンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="13b80-102">Step 2: Configure Load Test Controller and Agent Computers</span></span>
<span data-ttu-id="13b80-103">Visual Studio 2010 Ultimate edition には、ローカルのロード テストの実行で、最大 250 個の仮想ユーザーをシミュレートする負荷を生成できます。</span><span class="sxs-lookup"><span data-stu-id="13b80-103">Visual Studio 2010 Ultimate edition can generate load simulating up to 250 virtual users on a local load test run.</span></span> <span data-ttu-id="13b80-104">250 を超える仮想ユーザーをシミュレートする、またはリモートからテストを開始するコンピューターには、Visual Studio ロード テスト仮想ユーザー Pack 2010 が必要です。</span><span class="sxs-lookup"><span data-stu-id="13b80-104">To simulate more than 250 virtual users and/or to initiate testing from a remote computer requires Visual Studio Load Test Virtual User Pack 2010.</span></span>  
  
 <span data-ttu-id="13b80-105">すべてのロード テストに実行されるこのガイドでは、2 台のコンピューターから開始されました。</span><span class="sxs-lookup"><span data-stu-id="13b80-105">All load testing performed for this guide was initiated from two computers:</span></span>  
  
-   <span data-ttu-id="13b80-106">ロード テスト コント ローラーとロード テスト エージェントの両方として実行されている 1 台のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="13b80-106">One computer running as both a Load Test Controller and a Load Test Agent.</span></span>  
  
-   <span data-ttu-id="13b80-107">ロード テストのエージェントのみとして実行されている別のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="13b80-107">Another computer running as a Load Test Agent only.</span></span>  
  
 <span data-ttu-id="13b80-108">テストの結果は、SQL Server 2008 R2 データベースにリモートでロード テストの結果リポジトリに保存されていました。</span><span class="sxs-lookup"><span data-stu-id="13b80-108">Test results were stored in a remote load test results repository in a SQL Server 2008 R2 database.</span></span>  
  
 <span data-ttu-id="13b80-109">テスト コント ローラーとテスト エージェントを使用して、ロード テストを複数のテスト コンピューターに分散する方法の詳細については、次を参照してください[を配布するロード テスト全体で複数テスト マシンを使用してテスト コント ローラーおよび Test Agent](http://go.microsoft.com/fwlink/?LinkId=208406) (http://。go.microsoft.com/fwlink/ しますか。LinkId = 208406)。</span><span class="sxs-lookup"><span data-stu-id="13b80-109">For more information about using test controllers and test agents to distribute load tests across multiple test machines, see [Distributing Load Tests Across Multiple Test Machines Using Test Controllers and Test Agents](http://go.microsoft.com/fwlink/?LinkId=208406) (http://go.microsoft.com/fwlink/?LinkId=208406).</span></span>  
  
## <a name="install-and-configure-the-load-test-controller-and-load-test-agents"></a><span data-ttu-id="13b80-110">インストールし、構成、ロード テスト コント ローラーとロード テスト エージェント</span><span class="sxs-lookup"><span data-stu-id="13b80-110">Install and Configure the Load Test Controller and Load Test Agents</span></span>  
 <span data-ttu-id="13b80-111">インストールして、ロード テスト コント ローラーを構成およびテスト エージェントを読み込む、トピックの次のセクションを参照してください。[インストールし、Visual Studio Agents の構成とテストおよびビルド コント ローラーの](http://go.microsoft.com/fwlink/?LinkId=208455)(http://go.microsoft.com/fwlink/?LinkId=208455)。</span><span class="sxs-lookup"><span data-stu-id="13b80-111">To install and configure the load test controller and load test agents, see the following sections in the topic [Installing and Configuring Visual Studio Agents and Test and Build Controllers](http://go.microsoft.com/fwlink/?LinkId=208455) (http://go.microsoft.com/fwlink/?LinkId=208455):</span></span>  
  
-   <span data-ttu-id="13b80-112">テスト コント ローラーをセットアップするには、次の手順では、[テスト コント ローラーをインストール](http://go.microsoft.com/fwlink/?LinkId=208454)(http://go.microsoft.com/fwlink/?LinkId=208454) セクション。</span><span class="sxs-lookup"><span data-stu-id="13b80-112">To setup a test controller, follow the procedures in the [Install a Test Controller](http://go.microsoft.com/fwlink/?LinkId=208454) (http://go.microsoft.com/fwlink/?LinkId=208454) section.</span></span>  
  
-   <span data-ttu-id="13b80-113">テスト エージェントをセットアップするには、次の手順では、[テスト エージェントをインストール](http://go.microsoft.com/fwlink/?LinkId=208456)(http://go.microsoft.com/fwlink/?LinkId=208456) セクション。</span><span class="sxs-lookup"><span data-stu-id="13b80-113">To setup test agents, follow the procedures in the [Install a Test Agent](http://go.microsoft.com/fwlink/?LinkId=208456) (http://go.microsoft.com/fwlink/?LinkId=208456) section.</span></span>