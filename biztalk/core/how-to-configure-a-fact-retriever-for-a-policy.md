---
title: ポリシーのファクト取得コンポーネントを構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, policies
- Business Rule Composer, facts
- policies, facts
ms.assetid: a7bcf3e5-3f28-4f0e-b112-8c97dee072a1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18572af1323de817b3c934866af917d2601332f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247098"
---
# <a name="how-to-configure-a-fact-retriever-for-a-policy"></a>ポリシーのファクト取得コンポーネントを構成する方法
変更される頻度の低いファクトを保存しておくことができます。ホスト アプリケーションの初回実行サイクルの前に、これらのファクトをストレージから取得し、1 度だけルール エンジンに適用することにより、それ以降の複数の実行サイクルで、キャッシュされたファクトが再利用されます。  
  
 ファクト取得コンポーネントとポリシーは、2 つの方法で関連付けることができます。 ことができますか、このビジネス ルール作成ツールを使用してプログラムを使用して、 **RuleSetExecutionConfiguration**オブジェクト。  
  
> [!NOTE]
>  1 つのポリシー バージョンには、ファクト取得コンポーネントの実装を 1 つだけ関連付けることができます。  
  
### <a name="to-associate-a-fact-retriever-with-a-policy-in-the-business-rule-composer"></a>ビジネス ルール作成ツールを使用してファクト取得コンポーネントをポリシーに関連付けるには  
  
1.  [ポリシー エクスプローラー] ウィンドウで、ファクト取得コンポーネントを関連付けるポリシー バージョンをクリックします。  
  
2.  [プロパティ] ウィンドウ、**省略記号**ボタン ([...]) で、 **FactRetriever**ファクト取得コンポーネント オブジェクトのグローバル アセンブリ キャッシュ内で参照するプロパティです。  
  
    > [!IMPORTANT]
    >  **省略記号**ボタン (...) をクリックするまでは表示されません、 **FactRetriever**プロパティ ウィンドウ内の行。  
  
## <a name="see-also"></a>参照  
 [ファクト取得コンポーネントを作成する方法](../core/how-to-create-a-fact-retriever.md)