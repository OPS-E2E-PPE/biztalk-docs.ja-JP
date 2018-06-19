---
title: XML アセンブラーおよび逆アセンブラー パイプライン コンポーネントでのエンベロープの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XMLNorm.EnvelopeSpecNames property
- XML Disassembler [pipeline component], envelopes
- envelopes, nesting
- envelopes, XML Disassembler [pipeline component]
- envelopes, XML Assembler [pipeline component]
- XML Assembler [pipeline component], envelopes
- Envelope Specification Names property
ms.assetid: ccffd2f7-c7b1-4103-a914-ae9b4b19bee3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0ae57a65bad84f3d46ceb27e9b5415dc3d1bc31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240394"
---
# <a name="envelope-use-in-the-xml-assembler-and-disassembler-pipeline-components"></a>XML アセンブラーおよび逆アセンブラー パイプライン コンポーネントでのエンベロープの使用
XML メッセージには 0 個以上のエンベロープを含めることができます。 次の例では、XML ドキュメントをラップするエンベロープを太字で示します。  
  
```  
<ns1:document xmlns:ns1="http://myDocumentNamespaceURI.org">  
   <message>Hello</message>  
</ns1:document>  
  
```  
  
 エンベロープの用途は次の 2 つです。  
  
-   プロパティの昇格と降格のために使用するフィールド値を含めることができる。  
  
     XML 逆アセンブラー コンポーネントはプロパティを昇格させ、XML アセンブラー コンポーネントはプロパティを降格させます。 プロパティの昇格と降格は、XML ドキュメントでも行うことができます。  
  
-   複数の XML ドキュメントを 1 つのインターチェンジに結合できる。  
  
     整形式 XML ドキュメントに含めることができるルート要素は 1 つだけです。エンベロープを使用することにより、複数の XML ドキュメントで 1 つのルート要素を共有できます。  
  
 使用して、エンベロープの順序を指定することによって、正規の形式を適用することができます、**スキーマ コレクション プロパティ エディター**  ダイアログ ボックスの省略記号ボタンをクリックしてアクセスが、**エンベロープ スキーマ**XML アセンブラーでデザイン時プロパティです。 使用することも、 **XMLNORM です。EnvelopeSpecNames**メッセージ コンテキスト プロパティを XML アセンブラーの実行前にします。 XML アセンブラーは、エンベロープ ドキュメントを正規の形式で生成します。  
  
## <a name="nesting-envelopes"></a>エンベロープを入れ子にする  
 エンベロープを入れ子にすることにより、複数のエンベロープ XML ドキュメントが大きいインターチェンジに結合された、複雑なドキュメント構造を形成できます。 次の例では、2 つのエンペロープによってラップされたインターチェンジを示します。  
  
```  
<envelope1>  
   <document1/>  
   <envelope2>  
      <document2/>  
      <document3/>  
   </envelope2>  
   <document4/>  
</envelope1>  
```  
  
 前の例では、柔軟な形式を示しました。ドキュメントをエンベロープと同じ階層レベルにすることができます。 エンベロープ ドキュメントを逆アセンブルした後で、4 つの別個のドキュメントが作成されます (document1、document2 など)。  
  
## <a name="see-also"></a>参照  
 [パイプライン コンポーネント](../core/pipeline-components.md)