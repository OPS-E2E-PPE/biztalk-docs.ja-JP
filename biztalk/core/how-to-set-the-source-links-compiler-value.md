---
title: ソースを設定する方法は、コンパイラの値をリンク |Microsoft ドキュメント
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
ms.openlocfilehash: 61a7adf74d0b186f338220a383da6b6831013312
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255834"
---
# <a name="how-to-set-the-source-links-compiler-value"></a>送信元リンクのコンパイラ値を設定する方法
使用することができます、**送信元のリンク**値を送信元ノードから取得され、移行先ノードに適用する方法を指定するリンクのプロパティです。 このトピックでは、利用可能な選択肢と具体的な選択方法について説明します。  
  
### <a name="to-set-the-source-links-link-property"></a>[送信元のリンク] プロパティを設定するには  
  
1.  BizTalk マッパーのグリッド ページで、リンクをクリックして選択します。  
  
     グリッド ページ内の選択したリンクのエンドポイントが強調表示されます。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、設定、**送信元のリンク**プロパティに、次のいずれか。  
  
    -   **名前をコピーします。** : 送信元スキーマにおけるノード名は、送信先スキーマのリンク先ノードの値として使用されます。  
  
    -   **テキスト値をコピーします。** : 送信元スキーマのノードに対応する値 (要素データまたは属性データ) は、送信先スキーマのリンク先ノードの値として使用されます。 これは既定の設定です。 たとえば、`<Node>Hello<Name>Chris</Name>Barry</Node>` は "Hello" のようになります。  
  
    -   **テキストとサブコンテンツの値をコピーします。** 送信元スキーマの [レコード] ノードに対応する値と、そのすべての子孫ノードの値 (要素データおよび属性値) が結合され、送信先スキーマのリンク先ノードの値となります。 たとえば、`<Node>Hello<Name>Chris</Name>Barry</Node>` は "Hello Chris Barry" のようになります。  
  
## <a name="see-also"></a>参照  
 [リンクを使用してレコードを指定してフィールドのマッピング](../core/using-links-to-specify-record-and-field-mappings.md)   
 [コンパイラ ディレクティブおよびリンク](../core/compiler-directives-and-links.md)