---
title: XML アセンブラーおよび逆アセンブラー パイプライン コンポーネントでのエンベロープの使用 |Microsoft Docs
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
ms.openlocfilehash: 9841a9abcf188623afb46c8387d42c94982d0119
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389064"
---
# <a name="envelope-use-in-the-xml-assembler-and-disassembler-pipeline-components"></a>XML アセンブラーおよび逆アセンブラー パイプライン コンポーネントでのエンベロープの使用
XML メッセージには、0 個以上のエンベロープを含めることができます。 XML ドキュメントをラップするエンベロープ (太字) では、次の例です。  
  
```  
<ns1:document xmlns:ns1="http://myDocumentNamespaceURI.org">  
   <message>Hello</message>  
</ns1:document>  
  
```  
  
 エンベロープには、2 つの目的があります。  
  
- プロパティの昇格および降格のために使用するフィールドの値を含めることができます。  
  
   XML 逆アセンブラー コンポーネントはプロパティを昇格して、XML アセンブラー コンポーネントとプロパティは降格されます。 プロパティの昇格と降格は XML ドキュメントにも発生します。  
  
- 複数の XML ドキュメントを 1 つのインターチェンジに結合できます。  
  
   整形式 XML ドキュメントが 1 つだけのルート要素を持てないため、エンベロープでは、1 つのルート要素を共有する複数の XML ドキュメントを結合することができます。  
  
  使用して、エンベロープの順序を指定することによって、正規の形式を適用することができます、**スキーマ コレクション プロパティ エディター**ダイアログの省略記号をクリックしてアクセスされる、**エンベロープ スキーマ**XML アセンブラーのデザイン時プロパティです。 使用することも、 **XMLNORM します。EnvelopeSpecNames** XML アセンブラーの実行前に、メッセージ コンテキスト プロパティ。 XML アセンブラーは、正規の形式で、エンベロープ ドキュメントを生成します。  
  
## <a name="nesting-envelopes"></a>入れ子の封筒  
 大きいインターチェンジにいくつかのエンベロープ XML ドキュメントを組み合わせることができます、フォームの複雑なドキュメント構造にエンベロープを入れ子にできます。 次の例では、2 つのエンペロープによってラップされたインターチェンジを示します。  
  
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
  
 前の例は、ドキュメントをエンベロープと同じ階層レベルでできることを意味する、柔軟な形式を示しています。 エンベロープ ドキュメントを逆アセンブルした後は、(document1、document2 など)、4 つの独立したドキュメントが作成されます。  
  
## <a name="see-also"></a>参照  
 [パイプライン コンポーネント](../core/pipeline-components.md)