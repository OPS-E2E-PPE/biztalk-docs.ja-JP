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
# <a name="step-2-configure-load-test-controller-and-agent-computers"></a>手順 2: ロード テスト コント ローラーとエージェント コンピューターを構成します。

## <a name="overview"></a>概要
Visual Studio では、ローカルのロード テストの実行で、最大 250 個の仮想ユーザーをシミュレートする負荷を生成できます。 250 を超える仮想ユーザーをシミュレートする、またはリモートからテストを開始するコンピューターには、Visual Studio ロード テスト仮想ユーザーが必要です。  
  
 すべてのロード テストに実行されるこのガイドでは、2 台のコンピューターから開始されました。  
  
-   ロード テスト コント ローラーとロード テスト エージェントの両方として実行されている 1 台のコンピューター。  
  
-   ロード テストのエージェントのみとして実行されている別のコンピューター。  
  
 テストの結果は、SQL Server データベースにリモートでロード テストの結果リポジトリに保存されていました。  
  
 テスト コント ローラーとテスト エージェントを使用して、ロード テストを複数のテスト コンピューターに分散する方法の詳細については、次を参照してください。[を配布するロード テスト全体で複数テスト マシンを使用してテスト コント ローラーおよび Test Agent](https://msdn.microsoft.com/library/dd728093.aspx)です。  
  
## <a name="install-and-configure-the-load-test-controller-and-load-test-agents"></a>インストールし、構成、ロード テスト コント ローラーとロード テスト エージェント  
 インストールして、ロード テスト コント ローラーを構成およびテスト エージェントを読み込む、次を参照してください。[のインストールとテスト エージェントを構成](https://docs.microsoft.com/visualstudio/test/lab-management/install-configure-test-agents)です。
