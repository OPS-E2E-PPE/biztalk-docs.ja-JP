---
title: "プロパティ スキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8018bb72-a037-4eeb-bbbe-dd0cc6209aec
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2fb50536b2521e77994baf0b6457206614b7eed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="property-schemas"></a>プロパティ スキーマ

## <a name="promoted-properties"></a>昇格させたプロパティ
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、昇格させたプロパティを使用することによって、さまざまな BizTalk Server コンポーネントが主要なデータ項目にアクセスできるようになります。これらのデータ項目は、識別フィールドおよびプロパティ フィールドと呼ばれるもので、インスタンス メッセージを介して利用できます。また、メッセージ内における、これらのデータ項目の検索方法を把握しておく必要はありません。 メッセージの種類ごとに、どのデータ項目をより高い表示可能レベルに昇格させるかを指定できます。 このようなフィールドの昇格の選択方法に応じて、関連するプロパティ スキーマを作成し、定義する必要があります。  
  
> [!NOTE]
>  昇格するプロパティは非繰り返し要素または属性に限定されます。  
  
 ただし、識別フィールドはオーケストレーション内でのみアクセス可能であるため、対応するプロパティ スキーマを作成する必要はありません。 昇格させたメッセージ データにオーケストレーションからアクセスする場合にのみ、1 つ以上の識別フィールドとしてデータを昇格できます。  
  
 プロパティ フィールドは、さまざまな BizTalk Server コンポーネント (パイプラインおよびオーケストレーションなど) からアクセスできます。 プロパティ フィールドは、メッセージのルーティングに使用することもできます。 昇格させたメッセージ データにオーケストレーション以外のコンテキストからアクセスする場合、1 つ以上のプロパティ スキーマを作成して、昇格するデータを設定する必要があります。  
  
 プロパティ スキーマは、メッセージ スキーマに関連付ける特殊なスキーマです。 このスキーマは、インスタンス メッセージの特定の値をメッセージ コンテキストに昇格する場合に使用されます。 プロパティの昇格では、集中管理メカニズムを利用して、定義済みの主要な情報をインスタンス メッセージから抽出したり、BizTalk Server を介して渡されるメッセージの処理を担当する BizTalk Server コンポーネントへ簡単にアクセスしたりできます。  
  
## <a name="create-property-schema-overview"></a>プロパティ スキーマの概要を作成します。
 BizTalk Server のクイック昇格機能を使用して、既定のプロパティ スキーマを自動的に作成できます。 これは、プロパティ フィールドの昇格に必要なプロパティ スキーマを作成する最も簡単な方法です。 クイック昇格を実行する方法に関する詳細については、次を参照してください。[プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)です。  
  
 新しいプロパティ スキーマを作成することもできます。 BizTalk プロジェクトが開いているときは、BizTalk プロジェクトを右クリックして選択を選択して**追加**、 をクリックして**新しい項目の**、クリックして**スキーマ**です。  
  
> [!NOTE]
>  - プロパティ スキーマがメッセージ スキーマに関連付けられている場合、これらの 2 つのスキーマは、同じ BizTalk プロジェクトに属する必要があります。 異なる BizTalk プロジェクト内に、プロパティ スキーマと関連するメッセージ スキーマを分けて管理することはできません。  
>
>  - 同じ名前空間を使用する 2 つのプロパティ スキーマがある場合は、これらのスキーマが異なるアセンブリで定義されていたとしても、実行時に適切なスキーマ解決は行われません。 この場合、実行時にルーティング エラーが発生します。  

## <a name="distinguished-fields-and-property-fields"></a>識別フィールドおよびプロパティ フィールド 
 プロパティの昇格の 2 種類があります: フィールドおよびプロパティ フィールドを識別します。 プロパティ フィールドとして昇格させる場合は、プロパティ スキーマを使用します。 BizTalk エディターで、管理する両方のプロパティの昇格の型を使用して、**プロパティの昇格**を使用してアクセスする ダイアログ ボックス、**プロパティの昇格**のプロパティ、 **スキーマ**ノード。  
  
> [!NOTE]
>  - 昇格できる値にはいくつかの制限があります。 詳細については、表を参照して[プロパティの昇格](../core/promoting-properties.md)です。  
>
>  - 識別フィールドは、フィルター式に表示されません。 プロパティ フィールドだけがフィルター式に表示されます。  
  
 メッセージ スキーマと比較すると、プロパティ スキーマは単純です。 スキーマ ツリーでのみ可能ですを挿入する**フィールド要素**ノードの直接の子ノードとして、**スキーマ**ノード、2 階層の構造体を作成します。 プロパティを設定するほとんどの場合、**フィールド要素**のと同じノードとしてする**フィールド要素**メッセージ スキーマに表示されるノード。 また、使用できるのは、XSD の単純型だけになります。  
  
> [!IMPORTANT]
>  他のスキーマで使われているスキーマの名前を変更することはできません。 このようなスキーマには、既に昇格が設定されたプロパティ スキーマなどがあります。 これらのスキーマの名前を変更した場合、使用中のスキーマは、スキーマの名前が変更されているため、他のスキーマを見つけることができなくなります。  
  
 **Property Schema Base**プロパティに一意では**フィールド要素**ノード プロパティ スキーマに表示されます。 このプロパティは既定では、空白に設定することがいずれかに**MessageDataPropertyBase**または**MessageContextPropertyBase**でその結果、 **propSchFieldBase**属性追加されている、 **fieldInfo**いずれか一方のこれらの値を持つ注釈の要素。  
  
 ときに、 **propSchFieldBase**属性に設定されている**MessageDataPropertyBase**、昇格させたプロパティの値がいくつかのフィールドの値など、メッセージ内のデータに対応していることを意味します。 ときに、 **propSchFieldBase**属性に設定されている**MessageContextPropertyBase**、エンベロープなどの他の場所から、昇格させたプロパティの値がありますまたはによって設定される可能性があります、パイプライン コンポーネント。  
  
 **フィールド要素**プロパティ スキーマのノードにもというプロパティがある**機密情報**に設定すると**はい**、内から表示されず、対応する値を保持BizTalk エクスプ ローラーおよびメッセージ イベントとサービス インスタンスの追跡、それによってその性質上、機密を保持します。  参照してください**機密情報**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]詳細についてはします。
  
 次の XSD (XML Schema Definition) 言語表記のプロパティ スキーマには、注釈が含まれています。この注釈は、プロパティ スキーマ (schema_type="property") としてスキーマを識別する、スキーマ要素に関連付けられています。 含まれます 3**フィールド要素**ノードの下、**スキーマ**ノード。 最初の**フィールド要素**PromProp1 をという名前のノードが定義されている値を持たないその**Property Schema Base**プロパティが、後者の 2 つ**フィールド要素**ノードがあることプロパティに設定**MessageDataPropertyBase**と**MessageContextPropertyBase**、それぞれします。  
  
```  
<?xml version="1.0" encoding="utf-16" ?>   
<xs:schema xmlns="http://BizTalk_Server_Project1.PropertySchema1"  
           xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
           targetNamespace="http://BizTalk_Server_Project1.PropertySchema1"  
           xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:annotation>  
       <xs:appinfo>  
  
        </xs:appinfo>  
    </xs:annotation>  
    <xs:element name="" type="xs:string">  
        <xs:annotation>  
            <xs:appinfo>  
  
            </xs:appinfo>  
        </xs:annotation>  
    </xs:element>  
    <xs:element name="" type="xs:string">  
        <xs:annotation>  
            <xs:appinfo>  
  
            </xs:appinfo>  
        </xs:annotation>  
    </xs:element>  
    <xs:element name="" type="xs:string">  
        <xs:annotation>  
            <xs:appinfo>  
  
            </xs:appinfo>  
        </xs:annotation>  
    </xs:element>  
</xs:schema>  
  
```  
  
## <a name="see-also"></a>参照  
 [BizTalk スキーマの種類](../core/different-types-of-biztalk-schemas.md)