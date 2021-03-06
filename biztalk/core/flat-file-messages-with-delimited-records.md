---
title: 区切られたレコードのあるフラット ファイル メッセージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ad7119b-4e39-43df-9dba-a04382eb6db2
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54b700c0239bed2f1c324085195ca37d2ceaa0c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387892"
---
# <a name="flat-file-messages-with-delimited-records"></a>区切られたレコードのあるフラット ファイル メッセージ
フラット ファイル インスタンス メッセージ内の区切られたレコードには、入れ子のレコード、および事前に定義された文字や文字セットによって分けられている個別のフィールド (データ項目) が含まれています。 これらの区切り記号に従って、フィールドが解析されます。 フラット ファイル インスタンス メッセージ内に、次のような区切られたレコードが存在する場合を例として説明します。このレコードには、仮の注文書を基にした 2 つの商品が含まれています。  
  
```  
  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Electric-120vac,ITEM926-AA|Baby Monitor|1|39.98|Electric-4AA|2004-01-21  
  
```  
  
 フラット ファイル スキーマのこのレコードの適切な定義を、次のように記述できます。  
  
- 子区切り記号 (,)、子の順序の接頭辞、およびタグ ITEMS を持つ、区切られたレコードの名前付き項目。  
  
  -   区切られた A、繰り返しレコードという名前の子区切り記号を持つ項目&#124;、子注文挿入辞、およびタグ アイテム。  
  
  -   "partNum" という属性。  
  
  -   "productName" という要素。  
  
  -   "quantity" という要素。  
  
  -   "USPrice" という要素。  
  
  -   "powerSource" という要素。  
  
- "shipDate" という省略可能な要素。  
  
  これらのレコードとフィールドの定義が提供されると、フラット ファイル逆アセンブラーは、これらのレコードと同等の次の XML を生成します。  
  
```  
  
<items>  
    <item partNum="872-AA">  
        <productName>Lawnmower</productName>  
        <quantity>1</quantity>  
        <USPrice>148.95</USPrice>  
        <powerSource>Electric-120vac</powerSource>  
    </item>  
    <item partNum="926-AA">  
        <productName>Baby Monitor</productName>  
        <quantity>1</quantity>  
        <USPrice>39.98</USPrice>  
        <powerSource>Electric-4AA</powerSource>  
        <shipDate>2004-01-21</shipDate>  
    </item>  
</items>  
  
```  
  
 区切られたレコードに関連する注意事項を次に示します。これらは、送信時レコードの受信および作成の際のレコードの解析方法に影響します。  
  
- データの一部として扱われるために区切り文字の解釈のオーバーライドにしようされる文字です。 詳細については、次を参照してください。[フィールド値の一部としての特殊文字の解釈方法](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)します。  
  
- 他の類似しているレコードと区別するために使用される、レコードの先頭の省略可能なタグ。 詳細については、次を参照してください。[区切られたレコードのタグ処理](../core/tag-handling-in-delimited-records.md)します。  
  
- 埋め込み文字に関連する最小長のフィールド内のデータの位置揃え方法。 詳細については、次を参照してください。[フィールド Padding](../core/field-padding.md)、[フィールドの位置揃え](../core/field-justification.md)、および[最小フィールド長区切られたレコードの](../core/minimum-field-lengths-within-delimited-records.md)します。  
  
- 位置指定レコードは、他の区切られたレコード内に入れ子にすることができます。 詳細については、次を参照してください。[入れ子になった位置指定レコードとレコードの区切り](../core/nested-positional-and-delimited-records.md)します。  
  
- 埋め込み文字に関連する固定長のフィールド内のデータの位置揃え方法。 詳細については、次を参照してください。[フィールドの位置揃え](../core/field-justification.md)します。  
  
- 区切り記号の位置に関する注意事項は、区切られるデータに関連します。 詳細については、次を参照してください。[子の順序に関する注意事項](../core/child-order-considerations.md)します。  
  
- フラット ファイル メッセージを受信および送信する際の区切り記号の保存および非表示。 詳細については、次を参照してください。[区切り記号の保存と抑制](../core/delimiter-preservation-and-suppression.md)します。  
  
  区切られたフラット ファイルを使用する方法を理解するために、サンプル、FlatFileReceive フォルダーと FlatFileSend フォルダーにあるを参照してください。 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Pipelines\AssemblerDisassembler\\します。  
  
> [!NOTE]
>  設定する必要がありますが、フラット ファイルに区切られたおよび位置指定レコードの両方が含まれている場合、**構造**にルート ノードのプロパティ**区切り記号**と**構造**のプロパティいずれかに [レコード] ノードの下位**区切り記号**または**位置指定**に応じて。  
  
> [!NOTE]
>  フラット ファイルの区切られたフィールドの文字制限は、50000000 文字です。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル メッセージの構造](../core/structure-of-a-flat-file-message.md)   
 [フラット ファイル メッセージのスキーマを作成する方法](../core/how-to-create-schemas-for-flat-file-messages.md)   
 [フラット ファイル レコードの移行](../core/migrating-flat-file-records.md)