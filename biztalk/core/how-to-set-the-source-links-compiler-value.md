---
title: ソースを設定する方法は、コンパイラの値をリンク |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4edd1d73-78d1-468d-806a-3f6f258ee375
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ad777bc5b4df2717d20fd95aa60fdf5d59d1f6f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975171"
---
# <a name="how-to-set-the-source-links-compiler-value"></a>送信元リンクのコンパイラ値を設定する方法
使用することができます、**ソース リンク**値が送信元ノードから取得され、送信先ノードに適用する方法を指定するリンクのプロパティ。 このトピックでは、利用可能な選択肢と具体的な選択方法について説明します。  
  
### <a name="to-set-the-source-links-link-property"></a>[送信元のリンク] プロパティを設定するには  
  
1. BizTalk マッパーのグリッド ページで、リンクをクリックして選択します。  
  
    グリッド ページ内の選択したリンクのエンドポイントが強調表示されます。  
  
2. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、**ソース リンク**プロパティを次の選択肢のいずれか。  
  
   -   **名前をコピーします。** : 送信元スキーマにおけるノード名は、送信先スキーマのリンク先ノードの値として使用されます。  
  
   -   **テキスト値をコピーします。** : 送信元スキーマのノードに対応する値 (要素データまたは属性データ) は、送信先スキーマのリンク先ノードの値として使用されます。 これは既定の設定です。 たとえば、`<Node>Hello<Name>Chris</Name>Barry</Node>` は "Hello" のようになります。  
  
   -   **テキストとサブコンテンツの値をコピーします。** 送信元スキーマの [レコード] ノードに対応する値と、そのすべての子孫ノードの値 (要素データおよび属性値) が結合され、送信先スキーマのリンク先ノードの値となります。 たとえば、`<Node>Hello<Name>Chris</Name>Barry</Node>` は "Hello Chris Barry" のようになります。  
  
## <a name="see-also"></a>参照  
 [リンクを使用してレコードを指定して、フィールド マッピング](../core/using-links-to-specify-record-and-field-mappings.md)   
 [コンパイラ ディレクティブおよびリンク](../core/compiler-directives-and-links.md)