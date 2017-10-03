---
title: "BizTalk オーケストレーション エンジンに関する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac12012f-6253-4589-84b3-c1bb102ce8dd
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e4e686f066c2fcde921e45d08b60d6386e86640
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="about-the-biztalk-orchestration-engine"></a>BizTalk オーケストレーション エンジンについて
実行時に、BizTalk オーケストレーション エンジンは、BizTalk オーケストレーション デザイナーによって生成された xlang/s ファイルを実行します。 オーケストレーション デザイナーは、ビジネス プロセスを視覚的にデザインするための機能豊富なグラフィカル ツールです。 オーケストレーション デザイナーは、.odx という拡張子を持つ XLANG/s ファイルを生成します。このファイルのヘッダーには追加のビジュアル情報が格納され、本文にはカスタム属性情報が格納されます。  
  
> [!NOTE]
>  XLANG/s は、C# の表現機能を備えたメッセージング言語と見なすことができます。  
  
 オーケストレーション エンジンには、主に次のような機能があります。  
  
-   永続化  
  
-   .NET コンポーネントのホスト  
  
-   トランザクション  
  
-   サイズの大きいメッセージのサポート  
  
-   実行時の検証  
  
-   負荷の制限  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [永続化し、オーケストレーション エンジン](../core/persistence-and-the-orchestration-engine.md)  
  
-   [オーケストレーションの退避と復元](../core/orchestration-dehydration-and-rehydration.md)  
  
-   [オーケストレーション エンジンの実行時の検証](../core/runtime-validation-for-the-orchestration-engine.md)  
  
-   [オーケストレーション エンジンの構成](../core/orchestration-engine-configuration.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server アーキテクチャ](../core/biztalk-server-architecture.md)   
 [XLANG の言語](../core/xlang-s-language.md)   
 [ホスト制限によるリソース使用率の最適化](../core/optimizing-resource-usage-through-host-throttling.md)   
 [BizTalk Server がサイズの大きいメッセージを処理する方法](../core/how-biztalk-server-processes-large-messages.md)