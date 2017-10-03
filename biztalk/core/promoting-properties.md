---
title: "プロパティの昇格 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties, promoting
- promoting properties
- promoting properties, about promoting properties
ms.assetid: e1825028-7dd9-4eae-a383-4db12a83a402
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc1c5ac3e6e9aeadccc4eaefcb1457821ef36a93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="promoting-properties"></a>プロパティの昇格
プロパティの昇格昇格させること**フィールド要素**または**フィールド属性**するスキーマのノード**識別フィールド**または**プロパティフィールド**です。 昇格することも**レコード**ノードとして**プロパティ フィールド**単純コンテンツがある場合 (**Content-type**のプロパティ、**レコード**ノード設定**SimpleContent**)。 このセクションでは、いずれかとしてノードを昇格するための手順を説明**識別フィールド**または**プロパティ フィールド**です。  
  
 昇格する、**レコード**(コンテンツを含む単純な)、**フィールド要素**、または**フィールド属性**ノードとして、**プロパティ フィールド**、最初の月を定義する、特殊な種類のスキーマには、プロパティ スキーマが呼び出されます。 プロパティ スキーマの構造化されていないセットを定義する**フィールド要素**を昇格するノード**レコード**(コンテンツを含む単純な)、**フィールド要素**、または**フィールド属性**ノード。 プロパティ スキーマを作成するための詳しい手順については、「[プロパティ スキーマを作成する方法](../core/how-to-create-property-schemas.md)です。  
  
 また、使用することができます、**クイック昇格**機能では、自動的に作成され、新しいを昇格するときに、1 つのプロパティ スキーマを更新**フィールド要素**、**フィールド属性**、または**レコード**(単純コンテンツ) を含むノードです。  
  
> [!NOTE]
>  双方向にフィールドを昇格させることができます、**識別フィールド**と**プロパティ フィールド**です。  
  
> [!NOTE]
>  **クイック昇格**機能は、昇格させたノードの名前を持つ新しいプロパティを挿入することで、プロパティ スキーマを変更します。  
  
> [!IMPORTANT]
>  いったん昇格させた場合は、スキーマのフィールドの移動または名前の変更は行わないでください。 スキーマ フィールドの移動または名前変更を行うと、BizTalk エディターは、昇格させたフィールドの場所を定義する XPath を更新しません。  
  
## <a name="xsd-and-clr-data-types"></a>XSD データ型および CLR データ型  
 プロパティの昇格を行うときなど、場合によっては、XSD データ型が共通言語ランタイム (CLR) データ型に昇格されることがあります。 次の表は、昇格できる XSD データ型と対応する CLR データ型を示しています。  
  
|XSD データ型|CLR データ型|  
|-------------------|-------------------|  
|anyURI|文字列|  
|ブール値|ブール値|  
|Byte|sbyte|  
|日付|DateTime|  
|dateTime|DateTime|  
|Decimal|Decimal|  
|Double|Double|  
|ENTITY|文字列|  
|Float|単一|  
|gDay|DateTime|  
|gMonth|DateTime|  
|gMonthDay|DateTime|  
|gYear|DateTime|  
|gYearMonth|DateTime|  
|ID|文字列|  
|IDREF|文字列|  
|int|Int32|  
|Integer|Decimal|  
|言語|文字列|  
|名前|文字列|  
|NCName|文字列|  
|negativeInteger|Decimal|  
|NMTOKEN|文字列|  
|nonNegativeInteger|Decimal|  
|nonPositiveInteger|Decimal|  
|normalizedString|文字列|  
|NOTATION|文字列|  
|positiveInteger|Decimal|  
|QName|文字列|  
|Short|Int16|  
|文字列|文字列|  
|[時刻]|DateTime|  
|トークン|文字列|  
|unsignedByte|Byte|  
|unsignedInt|UInt32|  
|unsignedShort|UInt16|  
  
> [!NOTE]
>  base64Binary、duration、ENTITES、hexBinary、IDREFS、long、NMTOKENS、および unsignedLong の XSD データ型は、昇格ではサポートされていません。  
  
## <a name="limitations-for-promoting-properties"></a>プロパティの昇格の制限事項  
 プロパティを昇格する際は、次の点を考慮してください。  
  
-   昇格させたプロパティの長さは 256 文字までに制限されますが、書き込みプロパティには長さの制限がありません。  
  
-   昇格させたプロパティはメッセージ ルーティングに使用されるので、比較と保存を効率よく行うためにサイズが制限されます。 書き込みプロパティにはサイズの制限がありませんが、コンテキストに大きな値を使用すると、値を処理してメッセージと共に渡す必要があるため、パフォーマンスに影響します 書き込みプロパティの例としては、識別フィールドが挙げられます。  
  
-   レコード ノードは、としては昇格されません**識別フィールド**です。  
  
-   昇格するプロパティは非繰り返し要素または属性に限定されます。  
  
-   同じルート ノードに属するフィールドを同じプロパティに昇格しないでください。 このような昇格は、コンパイル エラーまたは展開エラーになります。  
  
-   メッセージ コンテキスト内では、昇格されていないために使用できないプロパティがいくつかあります。  BTS.ReceiveLocationName プロパティは、そのようなプロパティの 1 つです。 開発環境に新しいプロパティ スキーマまたは新しい BizTalk Server プロジェクトを追加できる場合は、オーケストレーション内からこのプロパティにアクセスできます。  
  
     プロパティの値は、プロパティのターゲットの名前空間およびプロパティ名によって識別されます。  次に、受信場所にアクセスするためのコード例を示します。  
  
     `string receiveLocationName =       pInMsg.Context.Read("ReceiveLocationName", sysNamespace);`  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [開く方法、プロパティの昇格 ダイアログ ボックス](../core/how-to-open-the-promote-properties-dialog-box.md)  
  
-   [識別フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)  
  
-   [プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)