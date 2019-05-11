---
title: BizTalk オーケストレーション エンジンについて |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac12012f-6253-4589-84b3-c1bb102ce8dd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5ba658a0df6675992601ecb55796e606791b6af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362315"
---
# <a name="about-the-biztalk-orchestration-engine"></a>BizTalk オーケストレーション エンジンについて
実行時に、BizTalk オーケストレーション エンジンは、BizTalk オーケストレーション デザイナーによって生成される xlang/s ファイルを実行します。 オーケストレーション デザイナーは、ビジネス プロセスを視覚的に設計するための豊富なグラフィカル ツールです。 Xlang/s ファイルを .odx という拡張子を持ち、ヘッダー内の視覚エフェクトの追加情報と、本文にカスタム属性情報が含まれますが生成されます。  
  
> [!NOTE]
>  一部の式の機能を備えたメッセージング言語として XLANG/秒を表示できますC#します。  
  
 オーケストレーション エンジンの主な機能は次のとおりです。  
  
-   永続化  
  
-   .NET コンポーネントをホストしています。  
  
-   トランザクション  
  
-   サイズの大きいメッセージのサポート  
  
-   実行時の検証  
  
-   負荷の制限  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [永続性とオーケストレーション エンジン](../core/persistence-and-the-orchestration-engine.md)  
  
-   [オーケストレーションの退避と復元](../core/orchestration-dehydration-and-rehydration.md)  
  
-   [オーケストレーション エンジンの実行時の検証](../core/runtime-validation-for-the-orchestration-engine.md)  
  
-   [オーケストレーション エンジンの構成](../core/orchestration-engine-configuration.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server アーキテクチャ](../core/biztalk-server-architecture.md)   
 [Xlang-s 言語](../core/xlang-s-language.md)   
 [ホスト制限によるリソース使用率の最適化](../core/optimizing-resource-usage-through-host-throttling.md)   
 [BizTalk Server がサイズの大きなメッセージを処理する方法](../core/how-biztalk-server-processes-large-messages.md)