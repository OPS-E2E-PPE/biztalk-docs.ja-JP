---
title: データ変換の構成 |Microsoft Docs
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
ms.openlocfilehash: 017f5b38c30acd37728fc1834ff39b3125f4f07f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352700"
---
# <a name="data-transformation-configuration"></a>データ変換の構成
要素からマッピング、ように、一般的な XSLT Extensible Stylesheet Language Transformations () が表示されます。  
  
```  
<xsl:attribute name='CatalogPurposeCode'>  
     <xsl:value-of select='BCT/BCT01/text()'/>  
</xsl:attribute>  
```  
  
 場合、要素**BCT01**を含む混合コンテンツ、text() を使用できるようになりますアクセスの最初のテキストが最初のサブ要素のポイントまでしか存在する場合。 この XSLT ステートメントで text() を使用しない場合の結果はテキストの 1 つの文字列としてマップは、すべてのテキスト コンテンツとサブ要素のテキストのコンテンツになります。 構成、**ソース リンク**リンクのプロパティでは、送信先スキーマで定義された構造にコピーされたデータのソースを制御することができます。  
  
 表示、プロパティの 1 つ表示されているグリッド ページで、リンクを選択すると、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウが、**ソース リンク**プロパティ。 マップには、リンクごとに次の値の間で選択できます。  
  
-   **テキスト値をコピーします。** 入力インスタンス メッセージ内の要素または属性の値をコピーするのにには、この値は、既定を使用します。 たとえば、次のように関連する要素が boldexample の場合、次のように設定されている場合。  
  
    ```  
    <BoldExample>This is a <B>Bold Text</B> example.</BoldExample>  
    ```  
  
     値が関連する要素にコピーまたは出力インスタンス メッセージ内の属性は、"これは、"。 このような混合コンテンツ要素をこの結果が希望どおりの結果は限りません。 混合コンテンツ要素は比較的まれであるため、**テキスト値をコピー**の設定、**ソース リンク**プロパティは、ほとんどの場合に適してします。  
  
-   **名前をコピーします。** 入力インスタンス メッセージ内のノードの名前をコピーするのにには、この値を使用します。 例では、**テキスト値をコピー**説明、結果がある"BoldExample"要素の実際の名前です。  
  
-   **コピーのテキストとサブコンテンツの値。** ノードの値と、入力インスタンス メッセージでは、その子ノードのすべての値を連結するのにには、この値を使用します。 例では、**テキスト値をコピー** 「. これが太字のテキストの例」、説明、結果は、これは混合コンテンツを含むように定義する要素の適切な結果では非常にうまく可能性があります。  
  
## <a name="see-also"></a>参照  
 [一括コピー Functoid](../core/mass-copy-functoid.md)   
 [ソース リンクのコンパイラ値を設定する方法](../core/how-to-set-the-source-links-compiler-value.md)   
 [ノード階層レベルの照合](../core/node-hierarchy-level-matching.md)