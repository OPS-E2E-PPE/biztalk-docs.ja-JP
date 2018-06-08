---
title: 識別フィールドおよびプロパティ フィールドの使用 |Microsoft ドキュメント
description: 識別フィールド、プロパティ フィールドとプロパティ セットの違いについて確認します。 識別フィールドが、メッセージ フィールドのパスを使用して、プロパティ フィールドを使用してが正しくありません名前とスキーマの名前空間、およびプロパティ セットは、メッセージ (プロパティ セット) のコンテキスト プロパティを BizTalk Server の別のメッセージのコンテキスト プロパティに割り当てる
ms.custom: ''
ms.date: 05/02/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 264ee15e-be9a-4ba2-9c61-a1570b20378e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dc6233f71bb56fe831fded343e6557292cdb315
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848906"
---
# <a name="using-distinguished-fields-and-property-fields"></a><span data-ttu-id="4af24-104">識別フィールドおよびプロパティ フィールドの使用</span><span class="sxs-lookup"><span data-stu-id="4af24-104">Using Distinguished Fields and Property Fields</span></span>
<span data-ttu-id="4af24-105">識別フィールドは、主に判断を下したり、オーケストレーションでデータを操作するために使用する、特別なメッセージ データです。</span><span class="sxs-lookup"><span data-stu-id="4af24-105">Distinguished fields are message data of special interest that you use primarily to make decisions or to manipulate data in your orchestration.</span></span>  
  
 <span data-ttu-id="4af24-106">メッセージ プロパティはデータも — メッセージ自体の内容: または"metadata"— タイムスタンプやルーティング情報などのメッセージに関するコンテキスト情報。</span><span class="sxs-lookup"><span data-stu-id="4af24-106">Message properties are either data—contents of the message itself—or "metadata"—context information about the message such as time stamps or routing information.</span></span> <span data-ttu-id="4af24-107">システムで定義されているメッセージ コンテキスト プロパティまたはトランスポート コンテキスト プロパティを使用することも、プロパティ スキーマ内からスキーマ フィールドを参照することで独自のプロパティを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="4af24-107">You can use system-defined message context properties or transport context properties, or you can define your own properties by making reference to schema fields from within a property schema.</span></span> <span data-ttu-id="4af24-108">プロパティは、サブスクリプションおよび関連付けで使用されます。</span><span class="sxs-lookup"><span data-stu-id="4af24-108">Properties are used in subscriptions and correlations.</span></span>  
  
-   <span data-ttu-id="4af24-109">使用して、識別フィールドまたはプロパティ フィールドとしてスキーマ内のフィールドを指定することができます、**プロパティの昇格**エディター内からダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="4af24-109">You can designate a field in a schema as a distinguished field or property field by using the **Promote Properties** dialog box from within the Editor.</span></span> <span data-ttu-id="4af24-110">詳細については、次を参照してください[プロパティの昇格。](../core/promoting-properties.md)</span><span class="sxs-lookup"><span data-stu-id="4af24-110">For more information, see [Promoting Properties](../core/promoting-properties.md)</span></span>  
  
-   <span data-ttu-id="4af24-111">.NET 型のフィールドを、DistinguishedField 属性で修飾することにより識別フィールドとして、または Property 属性で修飾することによりプロパティ フィールドとして、指定できます。</span><span class="sxs-lookup"><span data-stu-id="4af24-111">You can designate a field in a .NET type as a distinguished field by decorating it with the DistinguishedField attribute, or as a property by the Property attribute.</span></span>  
  
## <a name="using-distinguished-fields"></a><span data-ttu-id="4af24-112">識別フィールドの使用</span><span class="sxs-lookup"><span data-stu-id="4af24-112">Using Distinguished Fields</span></span>  
 <span data-ttu-id="4af24-113">識別フィールドは、メッセージ内でフィールドへのパスにより参照されます。次の例に示すように、ピリオドを使用して、メッセージ名、フィールドを囲むすべてのレコードの名前、およびフィールド自体の名前を区切ります。</span><span class="sxs-lookup"><span data-stu-id="4af24-113">Distinguished fields are referred to by the path to the field in the message, using periods to separate the message name, the names of any records that enclose the field, and the name of the field itself:</span></span>  
  
```  
MyMessage.MyRecord.MySubrecord.MyDistinguishedField  
```  
  
## <a name="using-property-fields"></a><span data-ttu-id="4af24-114">プロパティ フィールドの使用</span><span class="sxs-lookup"><span data-stu-id="4af24-114">Using Property Fields</span></span>  
 <span data-ttu-id="4af24-115">プロパティ スキーマにフィールドを追加すると、コードを使用してオーケストレーションで、およびフィルター式で、フィールドの値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4af24-115">Once you have added a field to a property schema, its value can be accessed in the orchestration with code and in filter expressions.</span></span> <span data-ttu-id="4af24-116">プロパティ スキーマの詳細については、次を参照してください。[プロパティ スキーマ](../core/property-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="4af24-116">For more information about property schemas, see [Property Schemas](../core/property-schemas.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4af24-117">メッセージ コンテンツまたはデータのプロパティは、基本的に、基になっているデータへのショートカットです。プロパティを変更するとデータが変更され、データを変更するとプロパティが変更されます。</span><span class="sxs-lookup"><span data-stu-id="4af24-117">Message content or data properties are essentially shortcuts to the underlying data: if you modify the property, the data will be modified, and vice versa.</span></span>  
  
 <span data-ttu-id="4af24-118">次の例に示すように、メッセージのプロパティを参照するには、メッセージの名前の後に、名前空間 (スキーマ) とプロパティ名をかっこで囲んで指定します。</span><span class="sxs-lookup"><span data-stu-id="4af24-118">Message properties are referred to by the name of the message followed by the namespace (the schema) and property name in parentheses:</span></span>  
  
```  
MyMessage(Invoice.PropertySchema.InvoiceID)  
```  
  
> [!NOTE]
>  <span data-ttu-id="4af24-119">フィールドのプロパティ名が _ _ に変更は、スキーマ内のフィールドの名前として予約済みキーワードを使用すると、クイック昇格 を選択して、フィールドを昇格する、\<予約済みキーワード\>です。</span><span class="sxs-lookup"><span data-stu-id="4af24-119">When you use a reserved keyword as the name of a field in a schema, and you promote the field by selecting Quick Promotion, the property name of the field is changed to __\<Reserved Keyword\>.</span></span> <span data-ttu-id="4af24-120">(二重のアンダー スコアはプロパティ名の前に追加されます。)ただし、オーケストレーションの式でこのプロパティ名を使用する場合、オーケストレーションを構築するときにコンパイラ エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4af24-120">(The double underscore is added before the property name.) However, if you use this property name in an orchestration expression, you will receive a compiler error when building the orchestration.</span></span>  <span data-ttu-id="4af24-121">このエラーを回避するのには、手動で追加する必要があります\@二重のアンダー スコアの前にします。</span><span class="sxs-lookup"><span data-stu-id="4af24-121">To work around this error, you need to manually add \@ before the double underscore.</span></span> <span data-ttu-id="4af24-122">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4af24-122">For example,</span></span>  
>   
>  `MyMessage(Invoice.PropertySchema.@__Name) = "Product Name";`  
  
## <a name="property-sets"></a><span data-ttu-id="4af24-123">プロパティ セット</span><span class="sxs-lookup"><span data-stu-id="4af24-123">Property Sets</span></span>  
 <span data-ttu-id="4af24-124">あるメッセージのすべてのコンテキスト プロパティ (プロパティ セット) を、別のメッセージのコンテキスト プロパティに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="4af24-124">You can also assign all of the context properties of one message (a property set) to the context properties of another message.</span></span> <span data-ttu-id="4af24-125">プロパティ セットを割り当てるには、プロパティをかっこで囲むのと同じように、単に両方のメッセージ名の後にかっこで囲んだアスタリスクを付加します。</span><span class="sxs-lookup"><span data-stu-id="4af24-125">To assign a property set, you simply place an asterisk in parentheses after both message names, in the same way you would put a property in parentheses:</span></span>  
  
```  
MyMessage2(*)=MyMessage1(*);  
```  
  
 <span data-ttu-id="4af24-126">この例で、プロパティ セットを MyMessage2 に割り当てた後、MyMessage2 のすべてのプロパティには、MyMessage1 のプロパティと同じ値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4af24-126">After the property set has been assigned to MyMessage2 in the example, all of the properties in MyMessage2 contain the same values as the properties in MyMessage1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af24-127">参照</span><span class="sxs-lookup"><span data-stu-id="4af24-127">See Also</span></span>  
 <span data-ttu-id="4af24-128">[プロパティの昇格](../core/promoting-properties.md) </span><span class="sxs-lookup"><span data-stu-id="4af24-128">[Promoting Properties](../core/promoting-properties.md) </span></span>  
 <span data-ttu-id="4af24-129">[受信メッセージ図形にフィルターを使用します。](../core/using-filters-with-the-receive-message-shape.md) </span><span class="sxs-lookup"><span data-stu-id="4af24-129">[Using Filters With the Receive Message Shape](../core/using-filters-with-the-receive-message-shape.md) </span></span>  
 <span data-ttu-id="4af24-130">[オーケストレーションでメッセージの使用](../core/using-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="4af24-130">[Using Messages in Orchestrations](../core/using-messages-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="4af24-131">BizTalk メッセージ コンテキストのプロパティについて</span><span class="sxs-lookup"><span data-stu-id="4af24-131">About BizTalk Message Context Properties</span></span>](../core/about-biztalk-message-context-properties.md)
