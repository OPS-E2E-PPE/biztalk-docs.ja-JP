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
# <a name="step-2-configure-load-test-controller-and-agent-computers"></a>手順 2: ロード テスト コント ローラーとエージェント コンピューターを構成します。
Visual Studio 2010 Ultimate edition には、ローカルのロード テストの実行で、最大 250 個の仮想ユーザーをシミュレートする負荷を生成できます。 250 を超える仮想ユーザーをシミュレートする、またはリモートからテストを開始するコンピューターには、Visual Studio ロード テスト仮想ユーザー Pack 2010 が必要です。  
  
 すべてのロード テストに実行されるこのガイドでは、2 台のコンピューターから開始されました。  
  
-   ロード テスト コント ローラーとロード テスト エージェントの両方として実行されている 1 台のコンピューター。  
  
-   ロード テストのエージェントのみとして実行されている別のコンピューター。  
  
 テストの結果は、SQL Server 2008 R2 データベースにリモートでロード テストの結果リポジトリに保存されていました。  
  
 テスト コント ローラーとテスト エージェントを使用して、ロード テストを複数のテスト コンピューターに分散する方法の詳細については、次を参照してください[を配布するロード テスト全体で複数テスト マシンを使用してテスト コント ローラーおよび Test Agent](http://go.microsoft.com/fwlink/?LinkId=208406) (http://。go.microsoft.com/fwlink/ しますか。LinkId = 208406)。  
  
## <a name="install-and-configure-the-load-test-controller-and-load-test-agents"></a>インストールし、構成、ロード テスト コント ローラーとロード テスト エージェント  
 インストールして、ロード テスト コント ローラーを構成およびテスト エージェントを読み込む、トピックの次のセクションを参照してください。[インストールし、Visual Studio Agents の構成とテストおよびビルド コント ローラーの](http://go.microsoft.com/fwlink/?LinkId=208455)(http://go.microsoft.com/fwlink/?LinkId=208455)。  
  
-   テスト コント ローラーをセットアップするには、次の手順では、[テスト コント ローラーをインストール](http://go.microsoft.com/fwlink/?LinkId=208454)(http://go.microsoft.com/fwlink/?LinkId=208454) セクション。  
  
-   テスト エージェントをセットアップするには、次の手順では、[テスト エージェントをインストール](http://go.microsoft.com/fwlink/?LinkId=208456)(http://go.microsoft.com/fwlink/?LinkId=208456) セクション。