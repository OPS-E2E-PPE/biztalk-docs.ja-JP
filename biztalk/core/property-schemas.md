---
title: プロパティ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8018bb72-a037-4eeb-bbbe-dd0cc6209aec
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c8ffc953ecc4b68f2f3c0f195b3dd268f526b86
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398454"
---
# <a name="property-schemas"></a>プロパティ スキーマ

## <a name="promoted-properties"></a>昇格させたプロパティ
Microsoft で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロパティを使用するデータの重要な項目にアクセスするさまざまな BizTalk Server コンポーネントの昇格、識別フィールドとプロパティ フィールドを検索する方法を知らなくても、インスタンス メッセージ内に到着すると、このコンテキストで呼ばれるメッセージ自体の中にします。 メッセージのさまざまな種類のどのデータ項目がよりわかりやすいレベルへの昇格を必要と判断できます。 このようなフィールドを昇格するを選択した方法によってを作成し、関連付けられているプロパティ スキーマを定義する必要があります。  
  
> [!NOTE]
>  昇格させたプロパティに制限されている非繰り返し要素または属性。  
  
 識別フィールドはオーケストレーション内でのみアクセスし、対応するプロパティ スキーマの作成を必要としません。 オーケストレーション内から昇格させたメッセージ データにアクセスする場合は、データを 1 つまたは複数の識別フィールドとして昇格できます。  
  
 プロパティ フィールドは、パイプラインやオーケストレーションなどのさまざまな BizTalk Server コンポーネント内からアクセスできます。 プロパティ フィールドは、メッセージのルーティングにも使用できます。 オーケストレーション内で以外のコンテキストから、メッセージ データにアクセスを昇格する必要があると、昇格するデータを記述する 1 つまたは複数のプロパティ スキーマを作成する必要があります。  
  
 プロパティ スキーマは、メッセージ スキーマと関連付ける特殊なスキーマです。 インスタンス メッセージ内の特定の値をメッセージ コンテキストに昇格させるために使用されます。 プロパティの昇格は、重要なことからインスタンス メッセージ内で定義して、BizTalk を通過するとメッセージの処理より簡単にアクセスできるようにする BizTalk Server コンポーネントを情報を取得するための一元的なメカニズムを提供します。サーバー。  
  
## <a name="create-property-schema-overview"></a>プロパティ スキーマの概要を作成します。
 BizTalk Server のクイック昇格機能を使用して、既定のプロパティ スキーマを自動的に作成できます。 これは、プロパティ フィールドの昇格に必要なプロパティ スキーマを作成する最も簡単な方法です。 クイック昇格を実行する方法の詳細については、次を参照してください。[プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)します。  
  
 新しいプロパティ スキーマを作成することもできます。 BizTalk プロジェクトが開いているときは、選択、BizTalk プロジェクトを右クリックして選びます**追加**、 をクリックして**新しい項目の**、順にクリックします**スキーマ**します。  
  
> [!NOTE]
>  - プロパティ スキーマが、メッセージ スキーマに関連付けられている場合、これらの 2 つは、同じ BizTalk プロジェクトでなければなりません。 別の BizTalk プロジェクト内の関連するメッセージ スキーマからプロパティ スキーマを分離することはサポートされていません。  
>
>  - 異なるアセンブリで定義されている場合でも、同じの名前空間を持つ 2 つのプロパティ スキーマがある場合、スキーマは正しく実行時に解決されません。 実行時にルーティング エラーが表示されます。  

## <a name="distinguished-fields-and-property-fields"></a>識別フィールドとプロパティ フィールド 
 プロパティの昇格の 2 種類があります: フィールドおよびプロパティ フィールドを識別します。 後者の型は、プロパティ スキーマを使用します。 BizTalk エディターでは、管理するこれらのプロパティの昇格の両方を使用して、**プロパティの昇格** ダイアログ ボックスで、使用してアクセスする、**プロパティの昇格**のプロパティ、 **スキーマ**ノード。  
  
> [!NOTE]
>  - 昇格可能な値にいくつかの制限があります。 詳細については、表を参照して[プロパティの昇格](../core/promoting-properties.md)します。  
>
>  - 識別フィールドは、フィルター式では表示されません。 フィルター式でプロパティのフィールドのみが表示されます。  
  
 プロパティ スキーマは、単純なは、メッセージ スキーマと比較した場合は。 スキーマ ツリーでのみ許可されて挿入**フィールド要素**ノードの直下の子ノードとして、**スキーマ**ノード、2 つのレベルが深い構造体を作成します。 プロパティを設定するほとんどの場合、**フィールド要素**としてするノードと**フィールド要素**メッセージ スキーマに表示されているノード。 XSD 単純型のみを使用してに制限されます。  
  
> [!IMPORTANT]
>  別のスキーマで使用されている任意のスキーマの名前を変更する必要がありますされません。 これには、このプロモーションが確立されて既にプロパティ スキーマが含まれます。 これを行う場合、使用されているスキーマが含まれている名前に正確なされなくなるために、他のスキーマを検索できません。  
  
 **Property Schema Base**プロパティが一意に**フィールド要素**ノード プロパティ スキーマに表示されます。 このプロパティが既定では、空白で設定することがいずれかに**MessageDataPropertyBase**または**MessageContextPropertyBase**の結果として得られる、 **propSchFieldBase**属性追加される、 **fieldInfo** 1 つまたはその他のこれらの値を持つ注釈要素。  
  
 ときに、 **propSchFieldBase**属性に設定されて**MessageDataPropertyBase**、昇格させたプロパティの値がいくつかのフィールドの値など、メッセージ内のデータに対応していることを意味します。 ときに、 **propSchFieldBase**属性に設定されて**MessageContextPropertyBase**は、エンベロープなどの他の場所から、昇格させたプロパティの値がありますまたはによって設定される可能性があります、パイプライン コンポーネント。  
  
 **フィールド要素**プロパティ スキーマのノードもという名前のプロパティをある**機密情報**に設定すると**はい**、内からは表示されず、対応する値を保持BizTalk エクスプ ローラーおよびメッセージ イベントとサービス インスタンスの追跡、それによってその機密性を保持します。  参照してください**機密情報**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]の詳細。
  
 プロパティ スキーマの次の XML スキーマ定義 (XSD) 言語表記にはとして、プロパティ スキーマには、このスキーマを識別するスキーマ要素に関連付けられている注釈が含まれています (schema_type ="property")。 含まれている 3 つ**フィールド要素**ノードの下、**スキーマ**ノード。 最初の**フィールド要素**PromProp1 をという名前のノードには、定義されている値はありませんその**Property Schema Base**プロパティが、後者の 2 つ**フィールド要素**するノードがある。プロパティに設定**MessageDataPropertyBase**と**MessageContextPropertyBase**、それぞれします。  
  
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
 [さまざまな種類の BizTalk スキーマ](../core/different-types-of-biztalk-schemas.md)