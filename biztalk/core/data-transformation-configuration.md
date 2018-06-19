---
title: データ変換の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XSLT
- maps, compiling
- Source Links property
- BizTalk Mapper, compiler directives
- code samples, XSLT
- compiler directives, copy text and subcontentent value
- compiler directives, copy text value
- maps, XSLT
- compiler directives, copy name
- compiler directives
- maps, code sample [XSLT]
- XSLT, code samples
ms.assetid: 05abe091-5202-4590-99ec-e60ca53a4324
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8304d43f59f63e474a3257915521d5dc36c38d30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238962"
---
# <a name="data-transformation-configuration"></a>データ変換の構成
要素からマップされた XSLT (Extensible Stylesheet Language Transformations) の一般的な例は次のとおりです。  
  
```  
<xsl:attribute name='CatalogPurposeCode'>  
     <xsl:value-of select='BCT/BCT01/text()'/>  
</xsl:attribute>  
```  
  
 場合、要素**BCT01**を含む混合コンテンツ、text() を使用できるようになります、までのテキストのみ、最初のサブ要素のポイントにアクセスする場合。 この XSLT ステートメントで text() を使用しない場合、すべてのテキスト コンテンツ (存在する場合はすべてのサブ要素のテキスト コンテンツも含む) が 1 つのテキスト文字列としてマップされます。 構成、**送信元のリンク**リンクのプロパティでは、送信先スキーマで定義された構造にコピーされるデータのソースを制御することができます。  
  
 表示されるプロパティのいずれかの表示されているグリッド ページで、リンクを選択すると、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウが、**送信元のリンク**プロパティです。 マップの各リンクに対して選択できる設定可能な値は次のとおりです。  
  
-   **テキスト値をコピーします。** この値 (既定) を使用すると、入力インスタンス メッセージの要素または属性の値がコピーされます。 たとえば、関連する要素が BoldExample の場合、次のようになります。  
  
    ```  
    <BoldExample>This is a <B>Bold Text</B> example.</BoldExample>  
    ```  
  
     出力インスタンス メッセージの関連する要素または属性に、"This is a " という値がコピーされます。 上記の例のように混合コンテンツ要素の場合は、希望どおりの結果にならない場合があります。 混合コンテンツ要素は比較的まれであるためですが、**テキスト値をコピー**の設定、**送信元のリンク**プロパティは、ほとんどの場合に適切な可能性があります。  
  
-   **名前をコピーします。** この値を使用すると、入力インスタンス メッセージのノードの名前がコピーされます。 例で、**テキスト値をコピー**については、結果は"boldexample"の場合、これは、要素の実際の名前。  
  
-   **テキストのコピーし、サブコンテンツの値。** この値を使用すると、入力インスタンス メッセージのノードの値と子ノードのすべての値が連結されます。 例で、**テキスト値をコピー** 「これは、太字のテキストの例です。」、説明、結果は場合がよくあります混合コンテンツを含むように定義する要素の適切な結果です。  
  
## <a name="see-also"></a>参照  
 [一括コピー Functoid](../core/mass-copy-functoid.md)   
 [ソースへのリンクのコンパイラ値を設定する方法](../core/how-to-set-the-source-links-compiler-value.md)   
 [ノード階層レベルの照合](../core/node-hierarchy-level-matching.md)