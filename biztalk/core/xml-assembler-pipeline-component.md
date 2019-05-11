---
title: XML アセンブラー パイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component]
- pipeline components, XML Assembler
ms.assetid: 3adfd603-0577-49c2-ae9d-445d62fed385
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ed0d334539ae013a87d8caa293b55288e24becd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295600"
---
# <a name="xml-assembler-pipeline-component"></a>XML アセンブラー パイプライン コンポーネント
XML アセンブラー パイプライン コンポーネントは、XML シリアル化して、1 つのコンポーネントにアセンブルを結合します。 その主な機能では、プロパティをメッセージ コンテキストからエンベロープおよびドキュメントに転送します。  
  
 次の操作は、メッセージをインターチェンジのバッチを受信した後、XML アセンブラー コンポーネントで発生します。  
  
1.  アセンブラーは、指定されたエンベロープ仕様を使用してエンベロープを作成します。  
  
2.  コンポーネントは、メッセージに関連付けられている XSD スキーマに注釈としてコーディングされている、事前定義された Xpath を使用して、メッセージ インスタンスのコンテンツのプロパティを設定します。  
  
3.  コンポーネントは、メッセージをエンベロープに追加します。  
  
4.  コンポーネントは、エンベロープに関連付けられている XSD スキーマ内に注釈としてコーディングされている、事前定義された Xpath を使用して、エンベロープのコンテンツのプロパティを設定します。  
  
> [!NOTE]
>  XML アセンブラー パイプライン コンポーネントは、不足している属性フィールドでは設定されませんが、フィールドは省略可能ですが、既定値はありませんまたは固定値と、空の要素のフィールドを設定は。  
  
 XML アセンブラー パイプライン コンポーネントの構成方法の詳細については、次を参照してください。 [、XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [XML アセンブラー パイプライン コンポーネントでの文字エンコード](../core/character-encoding-in-the-xml-assembler-pipeline-component.md)  
  
-   [XML アセンブラー パイプライン コンポーネントの処理命令](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md)  
  
-   [XML アセンブラー パイプライン コンポーネントで認識されないメッセージ](../core/unrecognized-messages-in-the-xml-assembler-pipeline-component.md)  
  
-   [XML アセンブラー パイプライン コンポーネントにおける XML 要素](../core/xml-information-set-elements-in-the-xml-assembler-pipeline-component.md)  
  
-   [XML アセンブラー パイプライン コンポーネントにおけるドキュメント構造の強化](../core/document-structure-enforcement-in-the-xml-assembler-pipeline-component.md)