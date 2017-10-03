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
# <a name="property-schemas"></a><span data-ttu-id="989d4-102">プロパティ スキーマ</span><span class="sxs-lookup"><span data-stu-id="989d4-102">Property Schemas</span></span>

## <a name="promoted-properties"></a><span data-ttu-id="989d4-103">昇格させたプロパティ</span><span class="sxs-lookup"><span data-stu-id="989d4-103">Promoted properties</span></span>
<span data-ttu-id="989d4-104">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、昇格させたプロパティを使用することによって、さまざまな BizTalk Server コンポーネントが主要なデータ項目にアクセスできるようになります。これらのデータ項目は、識別フィールドおよびプロパティ フィールドと呼ばれるもので、インスタンス メッセージを介して利用できます。また、メッセージ内における、これらのデータ項目の検索方法を把握しておく必要はありません。</span><span class="sxs-lookup"><span data-stu-id="989d4-104">In Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], promoted properties enable various BizTalk Server components to access key items of data, known in this context as distinguished fields and property fields that arrive within an instance message without needing to know how to look for them within the message itself.</span></span> <span data-ttu-id="989d4-105">メッセージの種類ごとに、どのデータ項目をより高い表示可能レベルに昇格させるかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="989d4-105">For different types of messages, you can determine which items of data require promotion to a more visible level.</span></span> <span data-ttu-id="989d4-106">このようなフィールドの昇格の選択方法に応じて、関連するプロパティ スキーマを作成し、定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="989d4-106">Depending on how you choose to promote such fields, you may need to create and define an associated property schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="989d4-107">昇格するプロパティは非繰り返し要素または属性に限定されます。</span><span class="sxs-lookup"><span data-stu-id="989d4-107">Promoted properties are restricted to non-repeating elements/attributes.</span></span>  
  
 <span data-ttu-id="989d4-108">ただし、識別フィールドはオーケストレーション内でのみアクセス可能であるため、対応するプロパティ スキーマを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="989d4-108">Distinguished fields are accessible only within orchestrations and do not require the creation of a corresponding property schema.</span></span> <span data-ttu-id="989d4-109">昇格させたメッセージ データにオーケストレーションからアクセスする場合にのみ、1 つ以上の識別フィールドとしてデータを昇格できます。</span><span class="sxs-lookup"><span data-stu-id="989d4-109">If you only need to access promoted message data from within an orchestration, you can promote the data as one or more distinguished fields.</span></span>  
  
 <span data-ttu-id="989d4-110">プロパティ フィールドは、さまざまな BizTalk Server コンポーネント (パイプラインおよびオーケストレーションなど) からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="989d4-110">Property fields are accessible from within various BizTalk Server components, including pipelines and orchestrations.</span></span> <span data-ttu-id="989d4-111">プロパティ フィールドは、メッセージのルーティングに使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="989d4-111">Property fields can also be used for message routing.</span></span> <span data-ttu-id="989d4-112">昇格させたメッセージ データにオーケストレーション以外のコンテキストからアクセスする場合、1 つ以上のプロパティ スキーマを作成して、昇格するデータを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="989d4-112">If you need to access promoted message data from contexts other than within orchestrations, you must create one or more property schemas to describe the data you are promoting.</span></span>  
  
 <span data-ttu-id="989d4-113">プロパティ スキーマは、メッセージ スキーマに関連付ける特殊なスキーマです。</span><span class="sxs-lookup"><span data-stu-id="989d4-113">A property schema is a special schema that you associate with a message schema.</span></span> <span data-ttu-id="989d4-114">このスキーマは、インスタンス メッセージの特定の値をメッセージ コンテキストに昇格する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="989d4-114">It is used for promoting specific values from within an instance message into the message context.</span></span> <span data-ttu-id="989d4-115">プロパティの昇格では、集中管理メカニズムを利用して、定義済みの主要な情報をインスタンス メッセージから抽出したり、BizTalk Server を介して渡されるメッセージの処理を担当する BizTalk Server コンポーネントへ簡単にアクセスしたりできます。</span><span class="sxs-lookup"><span data-stu-id="989d4-115">Property promotion provides a centralized mechanism for pulling key pieces of information that you define from within an instance message and making it more easily accessible to BizTalk Server components that are handling the message as it passes through BizTalk Server.</span></span>  
  
## <a name="create-property-schema-overview"></a><span data-ttu-id="989d4-116">プロパティ スキーマの概要を作成します。</span><span class="sxs-lookup"><span data-stu-id="989d4-116">Create property schema overview</span></span>
 <span data-ttu-id="989d4-117">BizTalk Server のクイック昇格機能を使用して、既定のプロパティ スキーマを自動的に作成できます。</span><span class="sxs-lookup"><span data-stu-id="989d4-117">You can automatically create a default property schema by using the quick promotion feature of BizTalk Server.</span></span> <span data-ttu-id="989d4-118">これは、プロパティ フィールドの昇格に必要なプロパティ スキーマを作成する最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="989d4-118">This is the easiest way to create the property schema required for property field promotion.</span></span> <span data-ttu-id="989d4-119">クイック昇格を実行する方法に関する詳細については、次を参照してください。[プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)です。</span><span class="sxs-lookup"><span data-stu-id="989d4-119">For more information about how to perform quick promotions, see [How to Copy Data to the Message Context as Property Fields](../core/how-to-copy-data-to-the-message-context-as-property-fields.md).</span></span>  
  
 <span data-ttu-id="989d4-120">新しいプロパティ スキーマを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="989d4-120">You can also create new property schema.</span></span> <span data-ttu-id="989d4-121">BizTalk プロジェクトが開いているときは、BizTalk プロジェクトを右クリックして選択を選択して**追加**、 をクリックして**新しい項目の**、クリックして**スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="989d4-121">When a BizTalk project is open, select the BizTalk project, right-click and select **Add**, click **New Item**, and then click **Schema**.</span></span>  
  
> [!NOTE]
>  - <span data-ttu-id="989d4-122">プロパティ スキーマがメッセージ スキーマに関連付けられている場合、これらの 2 つのスキーマは、同じ BizTalk プロジェクトに属する必要があります。</span><span class="sxs-lookup"><span data-stu-id="989d4-122">If a property schema is associated with a message schema, then these two must be in the same BizTalk project.</span></span> <span data-ttu-id="989d4-123">異なる BizTalk プロジェクト内に、プロパティ スキーマと関連するメッセージ スキーマを分けて管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="989d4-123">Separating property schema from its associated message schema in different BizTalk projects is not supported.</span></span>  
>
>  - <span data-ttu-id="989d4-124">同じ名前空間を使用する 2 つのプロパティ スキーマがある場合は、これらのスキーマが異なるアセンブリで定義されていたとしても、実行時に適切なスキーマ解決は行われません。</span><span class="sxs-lookup"><span data-stu-id="989d4-124">If you have two property schemas that have the same namespace, even though they are defined in different assemblies, the schemas will not resolve properly at runtime.</span></span> <span data-ttu-id="989d4-125">この場合、実行時にルーティング エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="989d4-125">You will get a routing failure at runtime.</span></span>  

## <a name="distinguished-fields-and-property-fields"></a><span data-ttu-id="989d4-126">識別フィールドおよびプロパティ フィールド</span><span class="sxs-lookup"><span data-stu-id="989d4-126">Distinguished fields and property fields</span></span> 
 <span data-ttu-id="989d4-127">プロパティの昇格の 2 種類があります: フィールドおよびプロパティ フィールドを識別します。</span><span class="sxs-lookup"><span data-stu-id="989d4-127">There are two types of property promotion: distinguished fields and property fields.</span></span> <span data-ttu-id="989d4-128">プロパティ フィールドとして昇格させる場合は、プロパティ スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="989d4-128">The latter type uses property schemas.</span></span> <span data-ttu-id="989d4-129">BizTalk エディターで、管理する両方のプロパティの昇格の型を使用して、**プロパティの昇格**を使用してアクセスする ダイアログ ボックス、**プロパティの昇格**のプロパティ、 **スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="989d4-129">In BizTalk Editor, you manage both of these types of property promotion by using the **Promote Properties** dialog box, which you access by using the **Promote Properties** property of the **Schema** node.</span></span>  
  
> [!NOTE]
>  - <span data-ttu-id="989d4-130">昇格できる値にはいくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="989d4-130">There are some restrictions on values that you can promote.</span></span> <span data-ttu-id="989d4-131">詳細については、表を参照して[プロパティの昇格](../core/promoting-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="989d4-131">For more information, see the table in [Promoting Properties](../core/promoting-properties.md).</span></span>  
>
>  - <span data-ttu-id="989d4-132">識別フィールドは、フィルター式に表示されません。</span><span class="sxs-lookup"><span data-stu-id="989d4-132">Distinguished fields do not appear in filter expressions.</span></span> <span data-ttu-id="989d4-133">プロパティ フィールドだけがフィルター式に表示されます。</span><span class="sxs-lookup"><span data-stu-id="989d4-133">Only property fields appear in filter expressions.</span></span>  
  
 <span data-ttu-id="989d4-134">メッセージ スキーマと比較すると、プロパティ スキーマは単純です。</span><span class="sxs-lookup"><span data-stu-id="989d4-134">Property schemas are simple when compared to message schemas.</span></span> <span data-ttu-id="989d4-135">スキーマ ツリーでのみ可能ですを挿入する**フィールド要素**ノードの直接の子ノードとして、**スキーマ**ノード、2 階層の構造体を作成します。</span><span class="sxs-lookup"><span data-stu-id="989d4-135">In the schema tree, you are only allowed to insert **Field Element** nodes as immediate child nodes of the **Schema** node, creating a structure that is two levels deep.</span></span> <span data-ttu-id="989d4-136">プロパティを設定するほとんどの場合、**フィールド要素**のと同じノードとしてする**フィールド要素**メッセージ スキーマに表示されるノード。</span><span class="sxs-lookup"><span data-stu-id="989d4-136">For the most part, you set the properties of the **Field Element** nodes as you would for **Field Element** nodes appearing in a message schema.</span></span> <span data-ttu-id="989d4-137">また、使用できるのは、XSD の単純型だけになります。</span><span class="sxs-lookup"><span data-stu-id="989d4-137">You are limited to using only XSD simple types.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="989d4-138">他のスキーマで使われているスキーマの名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="989d4-138">You should not rename any schema that is being used by another schema.</span></span> <span data-ttu-id="989d4-139">このようなスキーマには、既に昇格が設定されたプロパティ スキーマなどがあります。</span><span class="sxs-lookup"><span data-stu-id="989d4-139">This includes property schemas for which promotions have already been established.</span></span> <span data-ttu-id="989d4-140">これらのスキーマの名前を変更した場合、使用中のスキーマは、スキーマの名前が変更されているため、他のスキーマを見つけることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="989d4-140">If you do so, the schema that is being used will not be able to find the other schema because the name it contains will no longer be accurate.</span></span>  
  
 <span data-ttu-id="989d4-141">**Property Schema Base**プロパティに一意では**フィールド要素**ノード プロパティ スキーマに表示されます。</span><span class="sxs-lookup"><span data-stu-id="989d4-141">The **Property Schema Base** property is unique to **Field Element** nodes as they appear in property schemas.</span></span> <span data-ttu-id="989d4-142">このプロパティは既定では、空白に設定することがいずれかに**MessageDataPropertyBase**または**MessageContextPropertyBase**でその結果、 **propSchFieldBase**属性追加されている、 **fieldInfo**いずれか一方のこれらの値を持つ注釈の要素。</span><span class="sxs-lookup"><span data-stu-id="989d4-142">This property is blank by default, but can be set to either **MessageDataPropertyBase** or **MessageContextPropertyBase**, resulting in a **propSchFieldBase** attribute being added to the **fieldInfo** annotation element with one or the other of these values.</span></span>  
  
 <span data-ttu-id="989d4-143">ときに、 **propSchFieldBase**属性に設定されている**MessageDataPropertyBase**、昇格させたプロパティの値がいくつかのフィールドの値など、メッセージ内のデータに対応していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="989d4-143">When the **propSchFieldBase** attribute is set to **MessageDataPropertyBase**, it means that the value of the promoted property corresponds to data in the message, such as the value of some field.</span></span> <span data-ttu-id="989d4-144">ときに、 **propSchFieldBase**属性に設定されている**MessageContextPropertyBase**、エンベロープなどの他の場所から、昇格させたプロパティの値がありますまたはによって設定される可能性があります、パイプライン コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="989d4-144">When the **propSchFieldBase** attribute is set to **MessageContextPropertyBase**, it means that the value of the promoted property may be from somewhere else, such as an envelope, or that it may be set by a pipeline component.</span></span>  
  
 <span data-ttu-id="989d4-145">**フィールド要素**プロパティ スキーマのノードにもというプロパティがある**機密情報**に設定すると**はい**、内から表示されず、対応する値を保持BizTalk エクスプ ローラーおよびメッセージ イベントとサービス インスタンスの追跡、それによってその性質上、機密を保持します。</span><span class="sxs-lookup"><span data-stu-id="989d4-145">**Field Element** nodes in property schemas also have a property called **Sensitive Information**, which when set to **Yes**, will keep the corresponding value from being visible from within BizTalk Explorer and message event and service instance tracking, thereby preserving its sensitive nature.</span></span>  <span data-ttu-id="989d4-146">参照してください**機密情報**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="989d4-146">See **Sensitive Information** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] for more details.</span></span>
  
 <span data-ttu-id="989d4-147">次の XSD (XML Schema Definition) 言語表記のプロパティ スキーマには、注釈が含まれています。この注釈は、プロパティ スキーマ (schema_type="property") としてスキーマを識別する、スキーマ要素に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="989d4-147">The following XML Schema definition (XSD) language representation of a property schema contains an annotation associated with the schema element that identifies this schema as a property schema (schema_type="property").</span></span> <span data-ttu-id="989d4-148">含まれます 3**フィールド要素**ノードの下、**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="989d4-148">It also contains three **Field Element** nodes below the **Schema** node.</span></span> <span data-ttu-id="989d4-149">最初の**フィールド要素**PromProp1 をという名前のノードが定義されている値を持たないその**Property Schema Base**プロパティが、後者の 2 つ**フィールド要素**ノードがあることプロパティに設定**MessageDataPropertyBase**と**MessageContextPropertyBase**、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="989d4-149">The first **Field Element** node, named PromProp1, does not have a value defined for its **Property Schema Base** property, but the latter two **Field Element** nodes have that property set to **MessageDataPropertyBase** and **MessageContextPropertyBase**, respectively.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="989d4-150">参照</span><span class="sxs-lookup"><span data-stu-id="989d4-150">See Also</span></span>  
 [<span data-ttu-id="989d4-151">BizTalk スキーマの種類</span><span class="sxs-lookup"><span data-stu-id="989d4-151">Different Types of BizTalk Schemas</span></span>](../core/different-types-of-biztalk-schemas.md)