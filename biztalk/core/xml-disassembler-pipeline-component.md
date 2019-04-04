---
title: XML 逆アセンブラー パイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], about XML Disassembler
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component]
ms.assetid: ef39b695-6ae7-401d-be1e-b066048c34e9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bdd26a8fe5f90b1fd12937d19483e25f1a1e19f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011291"
---
# <a name="xml-disassembler-pipeline-component"></a>XML 逆アセンブラー パイプライン コンポーネント
XML 逆アセンブラー パイプライン コンポーネントは、XML 解析および XML 逆アセンブラーを 1 つのコンポーネントに組み込んでいます。 主要な機能を次に示します。  
  
- エンベロープの削除。  
  
- インターチェンジの逆アセンブル。  
  
- インターチェンジ レベルおよび個別のドキュメント レベルからメッセージ コンテキストにコンテンツ プロパティを昇格する。  
  
  エンベロープを受け取った後、XML 逆アセンブラー コンポーネントで次の操作が行われます。  
  
1. 逆アセンブラーは、設計時にコンポーネントに静的に関連付けられたエンベロープ スキーマを使用するか、実行時にメッセージの種類からエンベロープ スキーマを動的に決定して、エンベロープを解析します。 スキーマを使用すると、エンベロープの解析中にエンベロープの構造を確認できます。 エンベロープの構造が定義されていない場合、ルート ノードの名前空間およびベース名を使用してスキーマを参照することで、エンベロープの構造が再帰的に検索されます。  
  
2. 逆アセンブラー コンポーネントは、エンベロープの各ドキュメントを解析します。 各ドキュメントに対し、独自のコンテキストを持つ BizTalk メッセージ オブジェクトが作成されます。ここで、エンベロープおよびドキュメントから昇格されたすべてのプロパティがコピーされます。 定義済みの XPath (エンベロープおよびメッセージの XSD スキーマに注釈としてコーディングされている) を使用すると、エンベロープ インスタンスおよびメッセージ インスタンスのコンテンツ プロパティが抽出されます。 個別のドキュメント スキーマとエンベロープ スキーマは、パイプライン デザイナーの逆アセンブラー コンポーネントに関連付けられます。  
  
   XML 逆アセンブラーは、メッセージのボディ部分のデータのみ処理します。 このため、ボディ部分のプロパティのみ昇格できます。 昇格できるプロパティに関連付けられているフィールドの datetime 値は、プロパティの昇格が発生すると、UTC に変換されます。 ボディ部分以外は、そのまま出力メッセージにコピーされます。  
  
> [!NOTE]
>  XML 逆アセンブラー パイプライン コンポーネントは、メッセージ ストアに達する前に、すべての日時プロパティを UTC に強制的に変換します。 BizTalk Server は、内部的に SQL datetime (タイム ゾーンの情報は含まれない) を使用します。 オーケストレーションで日時プロパティを生成し、生成したプロパティを後続のメッセージと相互に関連付けようとすると、正しく機能しない場合があります。XML 逆アセンブラー パイプライン コンポーネントにより応答時に日時プロパティが UTC に変換され、Microsoft SQL Server で元の日時プロパティと応答時間フィールドを同一のものとして認識できなくなるためです。 同様に、メッセージ イベントおよびサービス インスタンスの追跡データの表示で不整合が発生する場合があります。  
  
 XML 逆アセンブラー パイプライン コンポーネントの構成方法の詳細については、[XML 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)を参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [XML 逆アセンブラー パイプライン コンポーネントにおける XML 要素](../core/xml-information-set-elements-in-the-xml-disassembler-pipeline-component.md)  
  
-   [XML 逆アセンブラー パイプライン コンポーネントで認識されないメッセージ](../core/unrecognized-messages-in-the-xml-disassembler-pipeline-component.md)  
  
-   [XML 逆アセンブラー パイプライン コンポーネントのドキュメント検証](../core/document-validation-in-the-xml-disassembler-pipeline-component.md)  
  
-   [XML 逆アセンブラー パイプライン コンポーネントにおけるドキュメント構造の強化](../core/document-structure-enforcement-in-the-xml-disassembler-pipeline-component.md)  
  
-   [XML 逆アセンブラー パイプライン コンポーネントでの文字エンコード](../core/character-encoding-in-xml-disassembler-pipeline-component.md)  
  
-   [チュートリアル: XML エンベロープの使用 (基本)](../core/walkthrough-using-xml-envelopes-basic.md)