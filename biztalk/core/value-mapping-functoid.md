---
title: "値のマッピング Functoid |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Value Mapping functoids
- functoids, empty tags
- Concatenate functoids
ms.assetid: 3dd626fb-3bf6-4ede-9fd2-ddae5a54d178
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 038d59827a62c9f4e83879ec7cf2e0b47fd738f4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="value-mapping-functoid"></a><span data-ttu-id="75cba-102">値のマッピング Functoid</span><span class="sxs-lookup"><span data-stu-id="75cba-102">Value Mapping Functoid</span></span>
<span data-ttu-id="75cba-103">**値のマッピング**functoid は、最初のパラメーターが true の場合に、2 番目のパラメーターの値を返します。</span><span class="sxs-lookup"><span data-stu-id="75cba-103">The **Value Mapping** functoid returns the value of its second parameter if its first parameter is true.</span></span> <span data-ttu-id="75cba-104">この Functoid は、主にフィールドの属性をレコードの属性に変更する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="75cba-104">A common use of the functoid is to change the attributes of a field into the attributes of a record.</span></span> <span data-ttu-id="75cba-105">入力メッセージの一部を平坦化する複数のレコードを 1 つのレコードに変換することによって、使用、[値のマッピング (フラット化) Functoid](../core/value-mapping-flattening-functoid.md)です。</span><span class="sxs-lookup"><span data-stu-id="75cba-105">To flatten a portion of an input message by converting multiple records into a single record, use the [Value Mapping (Flattening) Functoid](../core/value-mapping-flattening-functoid.md).</span></span>  
  
 <span data-ttu-id="75cba-106">次の図は、map、**値のマッピング**functoid、レコードの属性にフィールドの属性を変更するために使用します。</span><span class="sxs-lookup"><span data-stu-id="75cba-106">The following figure shows a map with the **Value Mapping** functoid used to change the attributes of a field into the attributes of a record.</span></span>  
  
 <span data-ttu-id="75cba-107">![](../core/media/valuemappingfunctoid.gif "valuemappingfunctoid")</span><span class="sxs-lookup"><span data-stu-id="75cba-107">![](../core/media/valuemappingfunctoid.gif "valuemappingfunctoid")</span></span>  
<span data-ttu-id="75cba-108">値のマッピング Functoid を含むマップ</span><span class="sxs-lookup"><span data-stu-id="75cba-108">Value Mapping Functoid Map</span></span>  
  
 <span data-ttu-id="75cba-109">次のコードは、名前のペアで、入力インスタンス メッセージを示し、値が割り当てられます**名前**と**値**属性。</span><span class="sxs-lookup"><span data-stu-id="75cba-109">The following code shows an input instance message in which pairs of names and values are assigned to **Name** and **Value** attributes.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://ValueMapping.WeatherIn">  
    <Record>  
        <Field Name="WindSpeed" Value="5"/>   
        <Field Name="Temperature" Value="20" />  
    </Record>  
    <Record>  
        <Field Name="WindSpeed" Value="15" />  
        <Field Name="Temperature" Value="18" />  
    </Record>  
</ns0:Root>  
```  
  
 <span data-ttu-id="75cba-110">このメッセージに対して、前述のマップを適用して変換すると、レコードごとに値が対応する名前の属性に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="75cba-110">The preceding map can convert this message into one in which the values are assigned to attributes with the corresponding names in separate records.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://ValueMapping.WeatherOut">  
    <Record WindSpeed="5"/>  
    <Record Temperature="20"/>  
    <Record WindSpeed="15"/>  
    <Record Temperature="18"/>  
</ns0:Root>  
```  
  
 <span data-ttu-id="75cba-111">**等しい**functoid の値がテスト、**名前**属性。</span><span class="sxs-lookup"><span data-stu-id="75cba-111">The **Equal** functoids test the values of the **Name** attribute.</span></span> <span data-ttu-id="75cba-112">最初の**等しい**の値のテストの functoid**名前**"windspeed"。</span><span class="sxs-lookup"><span data-stu-id="75cba-112">The first **Equal** functoid tests for the value of **Name** being "WindSpeed."</span></span> <span data-ttu-id="75cba-113">ときに、**名前**が"WindSpeed、"最初**等しい**functoid を返します**True**です。</span><span class="sxs-lookup"><span data-stu-id="75cba-113">When the **Name** is "WindSpeed," the first **Equal** functoid returns **True**.</span></span> <span data-ttu-id="75cba-114">、これにより、さらに、**値のマッピング**の値を設定する functoid、 **WindSpeed** 、出力インスタンス メッセージ内の属性です。</span><span class="sxs-lookup"><span data-stu-id="75cba-114">This, in turn, allows the **Value Mapping** functoid to set the value of the **WindSpeed** attribute in the output instance message.</span></span>  
  
## <a name="suppressing-the-creation-of-empty-tags"></a><span data-ttu-id="75cba-115">空のタグを作成しないようにする</span><span class="sxs-lookup"><span data-stu-id="75cba-115">Suppressing the Creation of Empty Tags</span></span>  
 <span data-ttu-id="75cba-116">空のタグを作成しないようにするには、値のマッピング Functoid を使用して、タグを作成するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="75cba-116">To suppress empty tags, use the Value Mapping functoid to control if a tag gets created or not.</span></span> <span data-ttu-id="75cba-117">値が True の場合は目的のフィールドが作成され、True でない場合は作成されません。</span><span class="sxs-lookup"><span data-stu-id="75cba-117">If the value is evaluated to true, the destination field will be created; otherwise the destination field will not be created.</span></span> <span data-ttu-id="75cba-118">ループ シナリオでは論理 Functoid を使用し、論理 Functoid を目的のレコードまたはフィールドに接続します。</span><span class="sxs-lookup"><span data-stu-id="75cba-118">In a looping scenario, use a logical functoid and connect it to the destination record or field.</span></span> <span data-ttu-id="75cba-119">条件が False と評価された場合、タグは作成されません。</span><span class="sxs-lookup"><span data-stu-id="75cba-119">If the condition is evaluated to false, the tag will not be created.</span></span> <span data-ttu-id="75cba-120">例については、次を参照してください。[条件付きループ](../core/conditional-looping.md)です。</span><span class="sxs-lookup"><span data-stu-id="75cba-120">For an example, see [Conditional Looping](../core/conditional-looping.md).</span></span>  
  
## <a name="forcing-the-creation-of-empty-tags"></a><span data-ttu-id="75cba-121">空のタグを強制的に作成する</span><span class="sxs-lookup"><span data-stu-id="75cba-121">Forcing the Creation of Empty Tags</span></span>  
 <span data-ttu-id="75cba-122">空のタグを作成するのには、目的のフィールドまたはリンクの Value プロパティに値を追加することができます、 **Concatenate** functoid を目的のフィールドです。</span><span class="sxs-lookup"><span data-stu-id="75cba-122">To force empty tags to be created, you can add a value in the Value property of the destination field or link a **Concatenate** functoid to the destination field.</span></span>  <span data-ttu-id="75cba-123">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を選択すると、空のタグの生成を強制することは、"\<空\>"、目的のフィールドの値プロパティ内の値。</span><span class="sxs-lookup"><span data-stu-id="75cba-123">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], it is possible to force the generation of empty tags by selecting the "\<empty\>" value in the Value property of the destination field.</span></span> <span data-ttu-id="75cba-124">この場合、空の値のフィールドが作成されます。</span><span class="sxs-lookup"><span data-stu-id="75cba-124">In this case the field will be created with the empty value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75cba-125">参照</span><span class="sxs-lookup"><span data-stu-id="75cba-125">See Also</span></span>  
 <span data-ttu-id="75cba-126">[値のマッピング (フラット化) Functoid](../core/value-mapping-flattening-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="75cba-126">[Value Mapping (Flattening) Functoid](../core/value-mapping-flattening-functoid.md) </span></span>  
 <span data-ttu-id="75cba-127">[値のマッピング Functoid をマップに追加する方法](../core/how-to-add-value-mapping-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="75cba-127">[How to Add Value Mapping Functoids to a Map](../core/how-to-add-value-mapping-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="75cba-128">高度な Functoid</span><span class="sxs-lookup"><span data-stu-id="75cba-128">Advanced Functoids</span></span>](../core/advanced-functoids.md)