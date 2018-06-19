---
title: XML アセンブラー パイプライン コンポーネント |Microsoft ドキュメント
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
ms.openlocfilehash: 22348b61ca32567190fa99e103fe536f5199af58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289490"
---
# <a name="xml-assembler-pipeline-component"></a>XML アセンブラー パイプライン コンポーネント
XML アセンブラー パイプライン コンポーネントは、XML のシリアル化とアセンブルを 1 つのコンポーネントで実行します。 XML アセンブラー パイプライン コンポーネントの主要な機能は、メッセージ コンテキストからエンベロープおよびドキュメントにプロパティを転送することです。  
  
 XML アセンブラー コンポーネントは、一連のメッセージを受け取った後で、次の処理を実行することによりデータ交換を実現します。  
  
1.  指定されたエンベロープ仕様に基づいてエンベロープを作成します。  
  
2.  メッセージに関連付けられている XSD スキーマ内に注釈としてコーディングされている、定義済みの XPath を使用して、メッセージ インスタンスのコンテンツ プロパティを設定します。  
  
3.  メッセージをエンベロープに追加します。  
  
4.  エンベロープに関連付けられている XSD スキーマ内に注釈としてコーディングされている、定義済みの XPath を使用して、エンベロープのコンテンツ プロパティを設定します。  
  
> [!NOTE]
>  XML アセンブラー パイプライン コンポーネントでは、欠落している属性フィールドに値を設定することはありません。ただし、空の要素フィールドについては、既定値や固定値の割り当てられていない省略可能なフィールドの場合にのみ値が設定されます。  
  
 XML アセンブラー パイプライン コンポーネントの構成方法の詳細については、次を参照してください。 [、XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [XML アセンブラー パイプライン コンポーネントでの文字エン コード](../core/character-encoding-in-the-xml-assembler-pipeline-component.md)  
  
-   [XML アセンブラー パイプライン コンポーネントで処理命令](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md)  
  
-   [XML アセンブラー パイプライン コンポーネントで認識されないメッセージ](../core/unrecognized-messages-in-the-xml-assembler-pipeline-component.md)  
  
-   [XML 情報は、XML アセンブラー パイプライン コンポーネントで要素を設定](../core/xml-information-set-elements-in-the-xml-assembler-pipeline-component.md)  
  
-   [XML アセンブラー パイプライン コンポーネントにおけるドキュメント構造の強化](../core/document-structure-enforcement-in-the-xml-assembler-pipeline-component.md)