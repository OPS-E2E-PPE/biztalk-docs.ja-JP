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
# <a name="property-schemas"></a><span data-ttu-id="15943-102">プロパティ スキーマ</span><span class="sxs-lookup"><span data-stu-id="15943-102">Property Schemas</span></span>

## <a name="promoted-properties"></a><span data-ttu-id="15943-103">昇格させたプロパティ</span><span class="sxs-lookup"><span data-stu-id="15943-103">Promoted properties</span></span>
<span data-ttu-id="15943-104">Microsoft で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロパティを使用するデータの重要な項目にアクセスするさまざまな BizTalk Server コンポーネントの昇格、識別フィールドとプロパティ フィールドを検索する方法を知らなくても、インスタンス メッセージ内に到着すると、このコンテキストで呼ばれるメッセージ自体の中にします。</span><span class="sxs-lookup"><span data-stu-id="15943-104">In Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], promoted properties enable various BizTalk Server components to access key items of data, known in this context as distinguished fields and property fields that arrive within an instance message without needing to know how to look for them within the message itself.</span></span> <span data-ttu-id="15943-105">メッセージのさまざまな種類のどのデータ項目がよりわかりやすいレベルへの昇格を必要と判断できます。</span><span class="sxs-lookup"><span data-stu-id="15943-105">For different types of messages, you can determine which items of data require promotion to a more visible level.</span></span> <span data-ttu-id="15943-106">このようなフィールドを昇格するを選択した方法によってを作成し、関連付けられているプロパティ スキーマを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15943-106">Depending on how you choose to promote such fields, you may need to create and define an associated property schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15943-107">昇格させたプロパティに制限されている非繰り返し要素または属性。</span><span class="sxs-lookup"><span data-stu-id="15943-107">Promoted properties are restricted to non-repeating elements/attributes.</span></span>  
  
 <span data-ttu-id="15943-108">識別フィールドはオーケストレーション内でのみアクセスし、対応するプロパティ スキーマの作成を必要としません。</span><span class="sxs-lookup"><span data-stu-id="15943-108">Distinguished fields are accessible only within orchestrations and do not require the creation of a corresponding property schema.</span></span> <span data-ttu-id="15943-109">オーケストレーション内から昇格させたメッセージ データにアクセスする場合は、データを 1 つまたは複数の識別フィールドとして昇格できます。</span><span class="sxs-lookup"><span data-stu-id="15943-109">If you only need to access promoted message data from within an orchestration, you can promote the data as one or more distinguished fields.</span></span>  
  
 <span data-ttu-id="15943-110">プロパティ フィールドは、パイプラインやオーケストレーションなどのさまざまな BizTalk Server コンポーネント内からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="15943-110">Property fields are accessible from within various BizTalk Server components, including pipelines and orchestrations.</span></span> <span data-ttu-id="15943-111">プロパティ フィールドは、メッセージのルーティングにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="15943-111">Property fields can also be used for message routing.</span></span> <span data-ttu-id="15943-112">オーケストレーション内で以外のコンテキストから、メッセージ データにアクセスを昇格する必要があると、昇格するデータを記述する 1 つまたは複数のプロパティ スキーマを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15943-112">If you need to access promoted message data from contexts other than within orchestrations, you must create one or more property schemas to describe the data you are promoting.</span></span>  
  
 <span data-ttu-id="15943-113">プロパティ スキーマは、メッセージ スキーマと関連付ける特殊なスキーマです。</span><span class="sxs-lookup"><span data-stu-id="15943-113">A property schema is a special schema that you associate with a message schema.</span></span> <span data-ttu-id="15943-114">インスタンス メッセージ内の特定の値をメッセージ コンテキストに昇格させるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="15943-114">It is used for promoting specific values from within an instance message into the message context.</span></span> <span data-ttu-id="15943-115">プロパティの昇格は、重要なことからインスタンス メッセージ内で定義して、BizTalk を通過するとメッセージの処理より簡単にアクセスできるようにする BizTalk Server コンポーネントを情報を取得するための一元的なメカニズムを提供します。サーバー。</span><span class="sxs-lookup"><span data-stu-id="15943-115">Property promotion provides a centralized mechanism for pulling key pieces of information that you define from within an instance message and making it more easily accessible to BizTalk Server components that are handling the message as it passes through BizTalk Server.</span></span>  
  
## <a name="create-property-schema-overview"></a><span data-ttu-id="15943-116">プロパティ スキーマの概要を作成します。</span><span class="sxs-lookup"><span data-stu-id="15943-116">Create property schema overview</span></span>
 <span data-ttu-id="15943-117">BizTalk Server のクイック昇格機能を使用して、既定のプロパティ スキーマを自動的に作成できます。</span><span class="sxs-lookup"><span data-stu-id="15943-117">You can automatically create a default property schema by using the quick promotion feature of BizTalk Server.</span></span> <span data-ttu-id="15943-118">これは、プロパティ フィールドの昇格に必要なプロパティ スキーマを作成する最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="15943-118">This is the easiest way to create the property schema required for property field promotion.</span></span> <span data-ttu-id="15943-119">クイック昇格を実行する方法の詳細については、次を参照してください。[プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)します。</span><span class="sxs-lookup"><span data-stu-id="15943-119">For more information about how to perform quick promotions, see [How to Copy Data to the Message Context as Property Fields](../core/how-to-copy-data-to-the-message-context-as-property-fields.md).</span></span>  
  
 <span data-ttu-id="15943-120">新しいプロパティ スキーマを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="15943-120">You can also create new property schema.</span></span> <span data-ttu-id="15943-121">BizTalk プロジェクトが開いているときは、選択、BizTalk プロジェクトを右クリックして選びます**追加**、 をクリックして**新しい項目の**、順にクリックします**スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="15943-121">When a BizTalk project is open, select the BizTalk project, right-click and select **Add**, click **New Item**, and then click **Schema**.</span></span>  
  
> [!NOTE]
>  - <span data-ttu-id="15943-122">プロパティ スキーマが、メッセージ スキーマに関連付けられている場合、これらの 2 つは、同じ BizTalk プロジェクトでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="15943-122">If a property schema is associated with a message schema, then these two must be in the same BizTalk project.</span></span> <span data-ttu-id="15943-123">別の BizTalk プロジェクト内の関連するメッセージ スキーマからプロパティ スキーマを分離することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="15943-123">Separating property schema from its associated message schema in different BizTalk projects is not supported.</span></span>  
>
>  - <span data-ttu-id="15943-124">異なるアセンブリで定義されている場合でも、同じの名前空間を持つ 2 つのプロパティ スキーマがある場合、スキーマは正しく実行時に解決されません。</span><span class="sxs-lookup"><span data-stu-id="15943-124">If you have two property schemas that have the same namespace, even though they are defined in different assemblies, the schemas will not resolve properly at runtime.</span></span> <span data-ttu-id="15943-125">実行時にルーティング エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="15943-125">You will get a routing failure at runtime.</span></span>  

## <a name="distinguished-fields-and-property-fields"></a><span data-ttu-id="15943-126">識別フィールドとプロパティ フィールド</span><span class="sxs-lookup"><span data-stu-id="15943-126">Distinguished fields and property fields</span></span> 
 <span data-ttu-id="15943-127">プロパティの昇格の 2 種類があります: フィールドおよびプロパティ フィールドを識別します。</span><span class="sxs-lookup"><span data-stu-id="15943-127">There are two types of property promotion: distinguished fields and property fields.</span></span> <span data-ttu-id="15943-128">後者の型は、プロパティ スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="15943-128">The latter type uses property schemas.</span></span> <span data-ttu-id="15943-129">BizTalk エディターでは、管理するこれらのプロパティの昇格の両方を使用して、**プロパティの昇格** ダイアログ ボックスで、使用してアクセスする、**プロパティの昇格**のプロパティ、 **スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="15943-129">In BizTalk Editor, you manage both of these types of property promotion by using the **Promote Properties** dialog box, which you access by using the **Promote Properties** property of the **Schema** node.</span></span>  
  
> [!NOTE]
>  - <span data-ttu-id="15943-130">昇格可能な値にいくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="15943-130">There are some restrictions on values that you can promote.</span></span> <span data-ttu-id="15943-131">詳細については、表を参照して[プロパティの昇格](../core/promoting-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="15943-131">For more information, see the table in [Promoting Properties](../core/promoting-properties.md).</span></span>  
>
>  - <span data-ttu-id="15943-132">識別フィールドは、フィルター式では表示されません。</span><span class="sxs-lookup"><span data-stu-id="15943-132">Distinguished fields do not appear in filter expressions.</span></span> <span data-ttu-id="15943-133">フィルター式でプロパティのフィールドのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="15943-133">Only property fields appear in filter expressions.</span></span>  
  
 <span data-ttu-id="15943-134">プロパティ スキーマは、単純なは、メッセージ スキーマと比較した場合は。</span><span class="sxs-lookup"><span data-stu-id="15943-134">Property schemas are simple when compared to message schemas.</span></span> <span data-ttu-id="15943-135">スキーマ ツリーでのみ許可されて挿入**フィールド要素**ノードの直下の子ノードとして、**スキーマ**ノード、2 つのレベルが深い構造体を作成します。</span><span class="sxs-lookup"><span data-stu-id="15943-135">In the schema tree, you are only allowed to insert **Field Element** nodes as immediate child nodes of the **Schema** node, creating a structure that is two levels deep.</span></span> <span data-ttu-id="15943-136">プロパティを設定するほとんどの場合、**フィールド要素**としてするノードと**フィールド要素**メッセージ スキーマに表示されているノード。</span><span class="sxs-lookup"><span data-stu-id="15943-136">For the most part, you set the properties of the **Field Element** nodes as you would for **Field Element** nodes appearing in a message schema.</span></span> <span data-ttu-id="15943-137">XSD 単純型のみを使用してに制限されます。</span><span class="sxs-lookup"><span data-stu-id="15943-137">You are limited to using only XSD simple types.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="15943-138">別のスキーマで使用されている任意のスキーマの名前を変更する必要がありますされません。</span><span class="sxs-lookup"><span data-stu-id="15943-138">You should not rename any schema that is being used by another schema.</span></span> <span data-ttu-id="15943-139">これには、このプロモーションが確立されて既にプロパティ スキーマが含まれます。</span><span class="sxs-lookup"><span data-stu-id="15943-139">This includes property schemas for which promotions have already been established.</span></span> <span data-ttu-id="15943-140">これを行う場合、使用されているスキーマが含まれている名前に正確なされなくなるために、他のスキーマを検索できません。</span><span class="sxs-lookup"><span data-stu-id="15943-140">If you do so, the schema that is being used will not be able to find the other schema because the name it contains will no longer be accurate.</span></span>  
  
 <span data-ttu-id="15943-141">**Property Schema Base**プロパティが一意に**フィールド要素**ノード プロパティ スキーマに表示されます。</span><span class="sxs-lookup"><span data-stu-id="15943-141">The **Property Schema Base** property is unique to **Field Element** nodes as they appear in property schemas.</span></span> <span data-ttu-id="15943-142">このプロパティが既定では、空白で設定することがいずれかに**MessageDataPropertyBase**または**MessageContextPropertyBase**の結果として得られる、 **propSchFieldBase**属性追加される、 **fieldInfo** 1 つまたはその他のこれらの値を持つ注釈要素。</span><span class="sxs-lookup"><span data-stu-id="15943-142">This property is blank by default, but can be set to either **MessageDataPropertyBase** or **MessageContextPropertyBase**, resulting in a **propSchFieldBase** attribute being added to the **fieldInfo** annotation element with one or the other of these values.</span></span>  
  
 <span data-ttu-id="15943-143">ときに、 **propSchFieldBase**属性に設定されて**MessageDataPropertyBase**、昇格させたプロパティの値がいくつかのフィールドの値など、メッセージ内のデータに対応していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="15943-143">When the **propSchFieldBase** attribute is set to **MessageDataPropertyBase**, it means that the value of the promoted property corresponds to data in the message, such as the value of some field.</span></span> <span data-ttu-id="15943-144">ときに、 **propSchFieldBase**属性に設定されて**MessageContextPropertyBase**は、エンベロープなどの他の場所から、昇格させたプロパティの値がありますまたはによって設定される可能性があります、パイプライン コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="15943-144">When the **propSchFieldBase** attribute is set to **MessageContextPropertyBase**, it means that the value of the promoted property may be from somewhere else, such as an envelope, or that it may be set by a pipeline component.</span></span>  
  
 <span data-ttu-id="15943-145">**フィールド要素**プロパティ スキーマのノードもという名前のプロパティをある**機密情報**に設定すると**はい**、内からは表示されず、対応する値を保持BizTalk エクスプ ローラーおよびメッセージ イベントとサービス インスタンスの追跡、それによってその機密性を保持します。</span><span class="sxs-lookup"><span data-stu-id="15943-145">**Field Element** nodes in property schemas also have a property called **Sensitive Information**, which when set to **Yes**, will keep the corresponding value from being visible from within BizTalk Explorer and message event and service instance tracking, thereby preserving its sensitive nature.</span></span>  <span data-ttu-id="15943-146">参照してください**機密情報**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]の詳細。</span><span class="sxs-lookup"><span data-stu-id="15943-146">See **Sensitive Information** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] for more details.</span></span>
  
 <span data-ttu-id="15943-147">プロパティ スキーマの次の XML スキーマ定義 (XSD) 言語表記にはとして、プロパティ スキーマには、このスキーマを識別するスキーマ要素に関連付けられている注釈が含まれています (schema_type ="property")。</span><span class="sxs-lookup"><span data-stu-id="15943-147">The following XML Schema definition (XSD) language representation of a property schema contains an annotation associated with the schema element that identifies this schema as a property schema (schema_type="property").</span></span> <span data-ttu-id="15943-148">含まれている 3 つ**フィールド要素**ノードの下、**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="15943-148">It also contains three **Field Element** nodes below the **Schema** node.</span></span> <span data-ttu-id="15943-149">最初の**フィールド要素**PromProp1 をという名前のノードには、定義されている値はありませんその**Property Schema Base**プロパティが、後者の 2 つ**フィールド要素**するノードがある。プロパティに設定**MessageDataPropertyBase**と**MessageContextPropertyBase**、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="15943-149">The first **Field Element** node, named PromProp1, does not have a value defined for its **Property Schema Base** property, but the latter two **Field Element** nodes have that property set to **MessageDataPropertyBase** and **MessageContextPropertyBase**, respectively.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="15943-150">参照</span><span class="sxs-lookup"><span data-stu-id="15943-150">See Also</span></span>  
 [<span data-ttu-id="15943-151">さまざまな種類の BizTalk スキーマ</span><span class="sxs-lookup"><span data-stu-id="15943-151">Different Types of BizTalk Schemas</span></span>](../core/different-types-of-biztalk-schemas.md)