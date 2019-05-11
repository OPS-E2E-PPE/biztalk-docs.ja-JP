---
title: ノード階層レベルの照合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Field nodes
- BizTalk Mapper, processing
- Record node
- BizTalk Mapper, compiler directives
- destination schemas, matching nodes
- source schemas, matching nodes
- maps, links
- Target Links property
- BizTalk Mapper, links
- compiler directives, matching schema nodes
- compiler directives, flattening source hierarchies
- maps, processing
ms.assetid: 5ba1ac77-0e70-4c58-9b8c-1b379dbbb3bd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 016a02be9634c86c03ac0a5532caf49a59a26c7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323568"
---
# <a name="node-hierarchy-level-matching"></a>ノード階層レベルの照合
BizTalk マッパーでは、コンパイラが元と送信先スキーマ間のノード階層をどのように一致しているかを制御する、リンクのプロパティを構成することができます。 送信先スキーマ内のフィールドに、送信元スキーマのフィールドからのリンクを作成するときに BizTalk マッパーが自動的にコンパイラ リンクを追加します。 これらのコンパイラ リンクは、選択した照合に依存します。  
  
 表示、プロパティの 1 つ表示されているグリッド ページで、リンクを選択すると、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウが、**ターゲット リンク**プロパティ。 マップには、各リンクの次の値の間で選択できます。  
  
-   **リンクをフラット化します。** 送信先スキーマ ノードの親レコードへのすべてのソース階層をフラット化するのにには、この値を使用します。  
  
-   **リンクを上から順に一致します。** スキーマの下に、スキーマの先頭からのノード レベルを照合するのにには、この値を使用します。  
  
-   **一致するもの下にリンクします。** スキーマの先頭に、スキーマの下部にあるノードのレベルを照合するのにには、この値を使用します。  
  
## <a name="flatten-links"></a>リンクをフラット化します。  
 このモードでは、すべてのソース階層は、送信先ノードの親レコードにフラット化します。 最初のケースでは、送信元スキーマは、送信先スキーマよりも複雑です。 2 番目のケースでは、送信先スキーマが複雑です。  
  
 ![](../core/media/bts-tls-flatten.gif "bts_tls_flatten")  
リンクをフラット化します。  
  
 ![](../core/media/bts-tls-flatten-2.gif "bts_tls_flatten_2")  
リンクをフラット化、2 番目のケース  
  
## <a name="match-links-top-down"></a>一致するリンクの上から下へ  
 このモードでは、上からレベルと一致します。 最初のケースでは、送信元スキーマは、送信先スキーマよりも複雑です。 2 番目のケースでは、送信先スキーマが複雑です。  
  
 ![](../core/media/bts-tls-topdown.gif "bts_tls_topdown")  
上から順に一致します。  
  
 ![](../core/media/bts-tls-topdown-2.gif "bts_tls_topdown_2")  
2 番目のケースに一致する、上から下へ  
  
## <a name="match-links-bottom-up"></a>下の一致リンク  
 このモードでは、下からレベルと一致します。 最初のケースでは、送信元スキーマは、送信先スキーマよりも複雑です。 2 番目のケースでは、送信先スキーマが複雑です。  
  
 ![](../core/media/bts-tls-bottomup.gif "bts_tls_bottomup")  
下から順に一致します。  
  
 ![](../core/media/bts-tls-bottomup-2.gif "bts_tls_bottomup_2")  
下から順に一致する、2 番目のケース  
  
## <a name="how-biztalk-mapper-processes-link-types"></a>BizTalk マッパーによる各種リンクの処理  
 設定できるため、**ターゲット リンク**プロパティごとに異なるリンクに別の値を BizTalk マッパーにさまざまな設定を解決する競合しないようにする方法が必要があります。  
  
 たとえばからのリンクを flatten コンパイラ ディレクティブ、上から下へのコンパイラ ディレクティブおよびボトムアップ コンパイラ ディレクティブを使用する場合**フィールド**ノードを**フィールド**送信先スキーマ、およびこれらのノードノードが同じ親を共有**レコード**ノードで、BizTalk マッパーは、上から下へとボトムアップのコンパイラ ディレクティブの競合を無視し、flatten コンパイラ ディレクティブに設定されているかのように、すべてのリンクを扱います。  
  
 次の表は、BizTalk マッパーがへのリンクを処理する方法を示しています**フィールド**ノードで同じ**レコード**の設定に基づいて、送信先スキーマ ノード、**ターゲット リンク**。プロパティ内で同じリンクを**レコード**ノード。  
  
|フラット化します。|上から下へ|ボトムアップ|結果|  
|-------------|---------------|----------------|------------|  
|0 個以上|1 つ以上|1 つ以上|Flatten コンパイラ ディレクティブが指定された場合と、BizTalk マッパーは、すべてのリンクを扱います。|  
|1 つ以上|1 つ以上|0|BizTalk マッパーは、上から下へのコンパイラ ディレクティブに設定されているかのように、すべてのリンクを扱います。|  
|1 つ以上|0|1 つ以上|BizTalk マッパーは、ボトムアップ コンパイラ ディレクティブに設定されているかのように、すべてのリンクを扱います。|  
  
 上から下へとボトムアップのコンパイラ ディレクティブは、flatten コンパイラ ディレクティブよりも優先しますが、取り消して他の両方が存在します。  
  
## <a name="see-also"></a>参照  
 [一括コピー Functoid](../core/mass-copy-functoid.md)   
 [ソース リンクのコンパイラ値を設定する方法](../core/how-to-set-the-source-links-compiler-value.md)   
 [マップのコンパイル](../core/compiling-maps.md)