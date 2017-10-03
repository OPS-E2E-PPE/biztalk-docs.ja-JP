---
title: "ノード階層レベルの照合 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b2d0c363abfefb9e3d0eb8abfb332c59539bb67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="node-hierarchy-level-matching"></a>ノード階層レベルの照合
BizTalk マッパーでは、リンク プロパティを構成することによって、コンパイラによる送信元スキーマと送信先スキーマ間のノード階層の照合方法を制御できます。 送信元スキーマのフィールドと送信先スキーマのフィールド間にリンクを作成すると、BizTalk マッパーにより自動的にコンパイラ リンクが追加されます。 コンパイラ リンクは、選択した照合方法に基づいて追加されます。  
  
 表示されるプロパティのいずれかの表示されているグリッド ページで、リンクを選択すると、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウが、**ターゲット リンク**プロパティです。 マップの各リンクに対して選択できる値は次のとおりです。  
  
-   **リンクをフラット化します。** : 送信元のすべての階層をフラット化して、送信先スキーマ ノードの親レコードと照合する場合に使用します。  
  
-   **リンクを上から順に一致します。** : スキーマの最上位から最下位へと順にノード レベルを照合する場合に使用します。  
  
-   **一致リンクを下からです。** : スキーマの最下位から最上位へと順にノード レベルを照合する場合に使用します。  
  
## <a name="flatten-links"></a>リンクをフラット化  
 このモードでは、送信元の階層がフラット化されて、送信先ノードの親レコードと照合されます。 第 1 のケースでは、送信元スキーマが送信先スキーマよりも複雑な仕様になっています。 第 2 のケースでは、送信先スキーマが送信元スキーマよりも複雑な仕様になっています。  
  
 ![](../core/media/bts-tls-flatten.gif "bts_tls_flatten")  
リンクをフラット化  
  
 ![](../core/media/bts-tls-flatten-2.gif "bts_tls_flatten_2")  
フラット化されたリンク (第 2 のケース)  
  
## <a name="match-links-top-down"></a>一致へのリンクを上から下  
 このモードでは、上のレベルから下のレベルへと順に照合されます。 第 1 のケースでは、送信元スキーマが送信先スキーマよりも複雑な仕様になっています。 第 2 のケースでは、送信先スキーマが送信元スキーマよりも複雑な仕様になっています。  
  
 ![](../core/media/bts-tls-topdown.gif "bts_tls_topdown")  
上から順に対応付け  
  
 ![](../core/media/bts-tls-topdown-2.gif "bts_tls_topdown_2")  
上から順に対応付け (第 2 のケース)  
  
## <a name="match-links-bottom-up"></a>リンクを下から順に一致  
 このモードでは、下のレベルから上のレベルへと順に照合されます。 第 1 のケースでは、送信元スキーマが送信先スキーマよりも複雑な仕様になっています。 第 2 のケースでは、送信先スキーマが送信元スキーマよりも複雑な仕様になっています。  
  
 ![](../core/media/bts-tls-bottomup.gif "bts_tls_bottomup")  
下から順に対応付け  
  
 ![](../core/media/bts-tls-bottomup-2.gif "bts_tls_bottomup_2")  
下から順に対応付け (第 2 のケース)  
  
## <a name="how-biztalk-mapper-processes-link-types"></a>BizTalk マッパーによる各種リンクの処理  
 設定できるため、**ターゲット リンク**プロパティを別のリンクに別の値は、BizTalk マッパーに競合しないようにする場合は、さまざまな設定を解決するのには方法が必要です。  
  
 たとえば、flatten コンパイラ ディレクティブ、トップダウン コンパイラ ディレクティブとボトムアップ コンパイラ ディレクティブからのリンクを使用する場合**フィールド**ノード**フィールド**送信先スキーマ、およびこれらのノードノードは、同じ親を共有**レコード**ノード、BizTalk マッパーが上から下へとボトムアップ コンパイラ ディレクティブの競合を無視し、flatten コンパイラ ディレクティブが設定されている場合、すべてのリンクが処理されます。  
  
 次の表は、BizTalk マッパーがへのリンクを処理する方法を示しています**フィールド**、同じノード**レコード**の設定に基づいて、送信先スキーマのノード、**ターゲット リンク**。同じ内のリンクのプロパティを**レコード**ノード。  
  
|フラット化|上から下|下から上|結果|  
|-------------|---------------|----------------|------------|  
|0 以上|1 つ以上|1 つ以上|[リンクをフラット化] のコンパイラ ディレクティブが設定されているものとして、すべてのリンクが処理されます。|  
|1 つ以上|1 つ以上|0|[リンクを上から順に一致] のコンパイラ ディレクティブが設定されているものとして、すべてのリンクが処理されます。|  
|1 つ以上|0|1 つ以上|[リンクを下から順に一致] のコンパイラ ディレクティブが設定されているものとして、すべてのリンクが処理されます。|  
  
 [リンクを上から順に一致] および [リンクを下から順に一致] のコンパイラ ディレクティブは [リンクをフラット化] よりも優先されますが、両方が存在する場合は、どちらの動作も無効になります。  
  
## <a name="see-also"></a>参照  
 [一括コピー Functoid](../core/mass-copy-functoid.md)   
 [ソースへのリンクのコンパイラ値を設定する方法](../core/how-to-set-the-source-links-compiler-value.md)   
 [マップのコンパイル](../core/compiling-maps.md)