---
title: ポリシーのファクト取得コンポーネントを構成する方法 |Microsoft Docs
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
ms.openlocfilehash: 7095ae5a03b6c3aec2d4f66db2563e7a6986fb39
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342292"
---
# <a name="how-to-configure-a-fact-retriever-for-a-policy"></a>ポリシーのファクト取得コンポーネントを構成する方法
多くの場合、変更されないファクトを保存して、ホスト アプリケーションの初回実行サイクル、前に、ストレージからこれらの情報を取得、キャッシュ、ルール エンジンに 1 度だけでき、複数の実行サイクルで再利用します。  
  
 ファクト取得コンポーネントをポリシーに関連付ける 2 つの方法はあります。 こうことをビジネス ルール作成ツールを使用するかを使用してプログラムで、 **RuleSetExecutionConfiguration**オブジェクト。  
  
> [!NOTE]
>  1 つのみのファクト取得コンポーネントの実装は、ポリシーのバージョンを関連付けることができます。  
  
### <a name="to-associate-a-fact-retriever-with-a-policy-in-the-business-rule-composer"></a>ビジネス ルール作成ツールでポリシーをファクト取得コンポーネントを関連付ける  
  
1.  ポリシー エクスプ ローラー ウィンドウで、ファクト取得コンポーネントを関連付けるポリシー バージョンをクリックします。  
  
2.  プロパティ ウィンドウで、**省略記号**ボタン (...)、 **FactRetriever**ファクト取得コンポーネントのオブジェクトのグローバル アセンブリ キャッシュに参照するプロパティ。  
  
    > [!IMPORTANT]
    >  **省略記号**ボタン (…) をクリックするまでは表示されません、 **FactRetriever**プロパティ ウィンドウ内の行。  
  
## <a name="see-also"></a>参照  
 [ファクト取得コンポーネントを作成する方法](../core/how-to-create-a-fact-retriever.md)