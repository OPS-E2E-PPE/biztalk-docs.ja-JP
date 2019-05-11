---
title: プロパティの昇格 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- properties, promoting
- promoting properties
- promoting properties, about promoting properties
ms.assetid: e1825028-7dd9-4eae-a383-4db12a83a402
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c8f10ba41a497a8595632947deaac31c5f48426
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398510"
---
# <a name="promoting-properties"></a>プロパティの昇格
プロパティの昇格には、昇格させることが含まれます**フィールド要素**または**フィールド属性**するスキーマ内のノード**識別フィールド**または**プロパティフィールド**します。 昇格することも**レコード**ノードとして**プロパティ フィールド**単純コンテンツがある場合 (**Content-type**のプロパティ、**レコード**ノード設定**SimpleContent**)。 このセクションのいずれかとしてノードを昇格する手順について説明します**識別フィールド**または**プロパティ フィールド**します。  
  
 昇格させる、**レコード**(単純なコンテンツの場合) を含む**フィールド要素**、または**フィールド属性**ノードとして、**プロパティ フィールド**、最初の月を定義する、特殊な種類のスキーマには、プロパティ スキーマが呼び出されます。 プロパティ スキーマの非構造化データのセットを定義する**フィールド要素**を昇格するノード**レコード**(単純なコンテンツの場合) を含む**フィールド要素**、または**フィールド属性**ノード。 プロパティ スキーマを作成する手順については、次を参照してください。[プロパティ スキーマを作成する方法](../core/how-to-create-property-schemas.md)します。  
  
 また、使用することができます、**クイック昇格**は自動的に作成し、新しい昇格する場合に、1 つのプロパティ スキーマを更新する機能**フィールド要素**、**フィールド属性**、または**レコード**(単純コンテンツ) を含むノードです。  
  
> [!NOTE]
>  両方のフィールドを昇格させることができます、**識別フィールド**と**プロパティ フィールド**します。  
  
> [!NOTE]
>  **クイック昇格**機能は、昇格されたノードの名前を持つ新しいプロパティを挿入することで、プロパティ スキーマを変更します。  
  
> [!IMPORTANT]
>  移動または昇格するいると、スキーマのフィールドの名前を変更しないでください。 移動またはスキーマのフィールドの名前を変更すると、BizTalk エディターは、昇格させたフィールドの場所を定義する XPath を更新できません。  
  
## <a name="xsd-and-clr-data-types"></a>XSD と CLR データ型  
 いくつかの場所でなどのプロパティの昇格、XSD データ型に昇格共通言語ランタイム (CLR) データ型。 次の表は、昇格できる XSD データ型と対応する CLR データ型を示します。  
  
|XSD データ型|CLR データ型|  
|-------------------|-------------------|  
|anyURI|String|  
|ブール値|ブール値|  
|バイト|sbyte|  
|date|DateTime|  
|dateTime|DateTime|  
|10 進数|10 進数|  
|Double|Double|  
|エンティティ|String|  
|float|単一|  
|gDay|DateTime|  
|gMonth|DateTime|  
|gMonthDay|DateTime|  
|gYear|DateTime|  
|gYearMonth|DateTime|  
|ID|String|  
|IDREF|String|  
|Int|Int32|  
|Integer|10 進数|  
|[言語]|String|  
|名前|String|  
|NCName|String|  
|negativeInteger|10 進数|  
|NMTOKEN|String|  
|nonNegativeInteger|10 進数|  
|nonPositiveInteger|10 進数|  
|normalizedString|String|  
|表記法|String|  
|positiveInteger|10 進数|  
|QName|String|  
|Short|Int16|  
|String|String|  
|Time|DateTime|  
|トークン|String|  
|unsignedByte|バイト|  
|unsignedInt|UInt32|  
|unsignedShort|UInt16|  
  
> [!NOTE]
>  Base64binary、XSD データ型、期間 ENTITES、hexBinary、IDREFS、long、NMTOKENS、および unsignedLong はサポートされませんを昇格します。  
  
## <a name="limitations-for-promoting-properties"></a>プロパティの昇格の制限事項  
 プロパティを昇格させるときに、次の操作を考慮してください。  
  
-   昇格させたプロパティの長さは 256 文字までに制限されますが、書き込みプロパティには長さの制限がありません。  
  
-   昇格させたプロパティはメッセージ ルーティングに使用されるので、比較と保存を効率よく行うためにサイズが制限されます。 書き込みプロパティにはサイズの制限がありませんが、コンテキストに大きな値を使用すると、値を処理してメッセージと共に渡す必要があるため、パフォーマンスに影響します 識別フィールドは、書き込みプロパティの例を示します。  
  
-   [レコード] ノードは、としては昇格されません**識別フィールド**します。  
  
-   昇格させたプロパティに制限されている非繰り返し要素または属性。  
  
-   同じプロパティに同じルート ノードに属するフィールドを昇格しません。 このような昇格では、コンパイルや展開のエラーが発生します。  
  
-   メッセージ コンテキスト内では昇格されていないため、使用できないいくつかのプロパティがあります。  BTS します。ReceiveLocationName プロパティはこのような 1 つのプロパティです。 新しいプロパティ スキーマまたは新しい BizTalk Server プロジェクトを追加するには、開発する場合、オーケストレーション内からこのプロパティにアクセスすることです。  
  
     プロパティの値は、プロパティのターゲット名前空間およびプロパティ名によって識別されます。  次の例では、コードで受信場所にアクセスする方法を示します。  
  
     `string receiveLocationName =       pInMsg.Context.Read("ReceiveLocationName", sysNamespace);`  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [開く方法、昇格のプロパティ ダイアログ ボックス](../core/how-to-open-the-promote-properties-dialog-box.md)  
  
-   [識別フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)  
  
-   [プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)