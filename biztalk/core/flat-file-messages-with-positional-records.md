---
title: 位置指定レコードのあるフラット ファイル メッセージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72c17c25-3847-458e-a43e-0dbdc42db749
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3cee44a9fbb3cdce4b75da765caf3fbf8f265d8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990755"
---
# <a name="flat-file-messages-with-positional-records"></a>位置指定のレコードのあるフラット ファイル メッセージ
フラット ファイル インスタンス メッセージ内の位置指定レコードには、事前に定義された長さの個別のフィールド (データ項目) が含まれています。 フィールドは、これらの長さに従って解析されます。 次に示す､フラット ファイル インスタンス メッセージの位置指定レコードを例として考えてみます。ここでは、出荷先住所を記載し、最初の行に各フィールドに予約される文字数が示されています。  
  
```  
123456789012345678901234567890123456789012345678901234567890123456789012345  
US        Alice Smith         123 Maple Street    Mill Valley    CA 90952  
```  
  
 フラット ファイル スキーマ内にあるこのレコードの適切な定義を、次のフィールドを含む shipTo という位置指定レコードとして記述できます。  
  
- 国/地域 (左揃え、長さが 10 文字、オフセットなし) という属性。  
  
- 名前 (左揃え、長さが 20 文字、オフセットなし) という要素。  
  
- 番地 (左揃え、長さが 20 文字、オフセットなし) という要素。  
  
- 市区町村 (左揃え、長さが 15 文字、オフセットなし) という要素。  
  
- 都道府県 (左揃え、長さが 2 文字、オフセットなし) という要素。  
  
- 左揃えである zip をという名前の要素、5 文字で、1 文字のオフセットします。  
  
  これらのレコードとフィールドの定義が提供されると、フラット ファイル逆アセンブラーは、このレコードと等価の XML を生成します。次のようになります。  
  
```  
<shipTo country/region="US">  
    <name>Alice Smith</name>  
    <street>123 Maple Street</street>  
    <city>Mill Valley</city>  
    <state>CA</state>  
    <zip>90952</zip>  
</shipTo>  
  
```  
  
 位置指定レコードに関連する注意事項を次に示します。これらは、レコードの受信やレコードの作成時におけるレコードの解析方法に影響します。  
  
- 各フィールドの使用されていない部分を埋めるために使用する文字 (埋め込み文字と呼ばれる)。 詳細については、[フィールド Padding](../core/field-padding.md)を参照してください。  
  
- 他の類似しているレコードと区別するために使用されるレコード内の省略可能なタグ。 通常、タグはレコードの先頭にありますが、レコード内の任意の場所に配置できます。 詳細については、[位置指定レコードのタグ処理](../core/tag-handling-in-positional-records.md)を参照してください。 位置指定レコードでタグの有無を定義できます。ただし、一度定義されると、その定義に基づいて、タグの存在の有無が決まります。  
  
- 固定長のフィールドでのデータの位置揃え方法。埋め込み文字の影響を受けます。 詳細については、[フィールドの位置揃え](../core/field-justification.md)を参照してください。  
  
- 位置指定レコードは、他の位置指定レコードまたは区切られたレコード内に入れ子にすることができます。 詳細については、[位置指定レコードの入れ子になった](../core/nested-positional-records.md)を参照してください。  
  
- 特定の文字数ではなく特定のバイト数で指定したフィールド長を持つ位置指定レコード。 詳細については、[位置のカウント (バイト単位)](../core/position-counting-in-bytes.md)を参照してください。  
  
  位置指定フラット ファイルを使用する方法を理解するために、サンプル、FlatFileReceive フォルダーと FlatFileSend フォルダーにある \Program Files\Microsoft BizTalk Server\SDK\Samples\Pipelines\AssemblerDisassembler を参照してください。\\します。  
  
> [!NOTE]
>  設定する必要がありますが、フラット ファイルに区切られたおよび位置指定レコードの両方が含まれている場合、**構造**にルート ノードのプロパティ**区切り記号**と**構造**のプロパティいずれかに [レコード] ノードの下位**区切り記号**または**位置指定**に応じて。  
  
> [!NOTE]
>  位置指定レコードのフィールドの文字制限は、50000000 文字です。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル メッセージの構造](../core/structure-of-a-flat-file-message.md)   
 [フラット ファイル メッセージのスキーマを作成する方法](../core/how-to-create-schemas-for-flat-file-messages.md)