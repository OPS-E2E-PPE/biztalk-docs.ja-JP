---
title: "短期間のファクトとします。長期間のファクト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- facts, short-term
- facts, long-term
- short-term facts
- business rules, facts
- long-term facts
ms.assetid: de020b20-1012-498a-969e-4adc4549918c
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d5c37926fb1da5499f34e22c35f8a8f32d238bb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="short-term-facts-vs-long-term-facts"></a>短期間のファクトとします。長期間のファクト
2 つの種類のファクトがルール エンジンの作業メモリにアサートされる — 短期間のファクトと長期間のファクトです。  
  
## <a name="short-term-facts"></a>短期間のファクト  
 短期間のファクトは、ルール エンジンを一度だけ実行するサイクルに特有です。 短期間のファクトは、ポリシーが実行された後に、ルール エンジンの作業メモリから自動的に取り消されます。 ポリシーのルール エンジンの実行サイクル間でデータが変更される場合は、データを短期間のファクトとしてルール エンジンに送信します。  
  
 短期間のファクトの例を以下に示します。  
  
-   パラメーターとして送信するファクト、 **Policy.Execute**メソッドです。  
  
-   パラメーターとして送信するファクト、**ルールの呼び出し**図形です。  
  
-   使用して、ルールのアクションから送信するファクト、 **Assert**関数。  
  
## <a name="long-term-facts"></a>長期間のファクト  
 長期間のファクトは、ルール エンジンの作業メモリに読み込まれ、任意の数の実行サイクルに使用されます。 通常、長期間のファクトは、一般的にはポリシーの実行の合間には変更されない、変化の遅いファクトです。 たとえば、データベース接続を 1 回だけ作成し、同じデータベース接続を使用してポリシーを複数回実行する必要がある場合が考えられます。 短期間のファクトと長期間のファクトの唯一の大きな違いは、その実装にあります。  
  
 ファクトを長期間のファクトとして送信するには、次の手順を実行する必要があります。  
  
1.  実装するファクト取得コンポーネントを作成、 **IFactRetriever**インターフェイスです。 作成し、ファクトをルールの作業メモリにアサート エンジン、 **UpdateFacts**最初の時刻、および更新の後続の呼び出しに必要な場合に、ファクトのメソッドが呼び出され、 **UpdateFacts**メソッドです。  
  
2.  ビジネス ルール作成ツールを使用して、ファクト取得コンポーネントを使用するポリシーを構成します。  
  
 ファクト取得コンポーネントを作成して、ポリシーでの使用に関する詳細については、次を参照してください。[ファクト取得コンポーネントを作成する方法](../core/how-to-create-a-fact-retriever.md)です。  
  
## <a name="see-also"></a>参照  
 [ファクト](../core/facts.md)