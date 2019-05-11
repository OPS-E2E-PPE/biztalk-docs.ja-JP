---
title: 値のマッピング Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Value Mapping functoids
- functoids, empty tags
- Concatenate functoids
ms.assetid: 3dd626fb-3bf6-4ede-9fd2-ddae5a54d178
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ca60ff3024eb1b4cadc42e42c65a0c44c82ef5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292612"
---
# <a name="value-mapping-functoid"></a><span data-ttu-id="64b0d-102">値のマッピング Functoid</span><span class="sxs-lookup"><span data-stu-id="64b0d-102">Value Mapping Functoid</span></span>
<span data-ttu-id="64b0d-103">**値のマッピング**functoid は、最初のパラメーターが true の場合に 2 番目のパラメーターの値を返します。</span><span class="sxs-lookup"><span data-stu-id="64b0d-103">The **Value Mapping** functoid returns the value of its second parameter if its first parameter is true.</span></span> <span data-ttu-id="64b0d-104">Functoid の一般的な用途は、フィールドの属性をレコードの属性に変更するのにです。</span><span class="sxs-lookup"><span data-stu-id="64b0d-104">A common use of the functoid is to change the attributes of a field into the attributes of a record.</span></span> <span data-ttu-id="64b0d-105">入力メッセージの一部を統合すると、複数のレコードを 1 つのレコードに変換することを使用して、[値のマッピング (フラット化) Functoid](../core/value-mapping-flattening-functoid.md)します。</span><span class="sxs-lookup"><span data-stu-id="64b0d-105">To flatten a portion of an input message by converting multiple records into a single record, use the [Value Mapping (Flattening) Functoid](../core/value-mapping-flattening-functoid.md).</span></span>  
  
 <span data-ttu-id="64b0d-106">次の図は、map、**値のマッピング**functoid、レコードの属性にフィールドの属性を変更するために使用します。</span><span class="sxs-lookup"><span data-stu-id="64b0d-106">The following figure shows a map with the **Value Mapping** functoid used to change the attributes of a field into the attributes of a record.</span></span>  
  
 <span data-ttu-id="64b0d-107">![](../core/media/valuemappingfunctoid.gif "valuemappingfunctoid")</span><span class="sxs-lookup"><span data-stu-id="64b0d-107">![](../core/media/valuemappingfunctoid.gif "valuemappingfunctoid")</span></span>  
<span data-ttu-id="64b0d-108">値のマッピング Functoid マップ</span><span class="sxs-lookup"><span data-stu-id="64b0d-108">Value Mapping Functoid Map</span></span>  
  
 <span data-ttu-id="64b0d-109">次のコードは、名前のペアで、入力インスタンス メッセージし、に値が割り当てられている**名前**と**値**属性。</span><span class="sxs-lookup"><span data-stu-id="64b0d-109">The following code shows an input instance message in which pairs of names and values are assigned to **Name** and **Value** attributes.</span></span>  
  
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
  
 <span data-ttu-id="64b0d-110">図に示したマップでは、値が別個のレコードに対応する名前を持つ属性に割り当てられているいずれかに、このメッセージを変換できます。</span><span class="sxs-lookup"><span data-stu-id="64b0d-110">The preceding map can convert this message into one in which the values are assigned to attributes with the corresponding names in separate records.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://ValueMapping.WeatherOut">  
    <Record WindSpeed="5"/>  
    <Record Temperature="20"/>  
    <Record WindSpeed="15"/>  
    <Record Temperature="18"/>  
</ns0:Root>  
```  
  
 <span data-ttu-id="64b0d-111">**等しい**functoid の値のテスト、**名前**属性。</span><span class="sxs-lookup"><span data-stu-id="64b0d-111">The **Equal** functoids test the values of the **Name** attribute.</span></span> <span data-ttu-id="64b0d-112">最初の**等しい**の値のテストの functoid**名前**"windspeed"。</span><span class="sxs-lookup"><span data-stu-id="64b0d-112">The first **Equal** functoid tests for the value of **Name** being "WindSpeed."</span></span> <span data-ttu-id="64b0d-113">ときに、**名前**"WindSpeed、"は、最初の**等しい**functoid を返します**True**します。</span><span class="sxs-lookup"><span data-stu-id="64b0d-113">When the **Name** is "WindSpeed," the first **Equal** functoid returns **True**.</span></span> <span data-ttu-id="64b0d-114">これにより、有効、**値のマッピング**functoid の値を設定する、 **WindSpeed**出力インスタンス メッセージ内の属性。</span><span class="sxs-lookup"><span data-stu-id="64b0d-114">This, in turn, allows the **Value Mapping** functoid to set the value of the **WindSpeed** attribute in the output instance message.</span></span>  
  
## <a name="suppressing-the-creation-of-empty-tags"></a><span data-ttu-id="64b0d-115">空のタグの作成を抑制します。</span><span class="sxs-lookup"><span data-stu-id="64b0d-115">Suppressing the Creation of Empty Tags</span></span>  
 <span data-ttu-id="64b0d-116">空のタグを抑制するには、タグを作成するかどうか場合、コントロールに値のマッピング functoid を使用します。</span><span class="sxs-lookup"><span data-stu-id="64b0d-116">To suppress empty tags, use the Value Mapping functoid to control if a tag gets created or not.</span></span> <span data-ttu-id="64b0d-117">値が評価される場合は true、先にフィールドが作成されます。それ以外の場合、目的のフィールドは作成されません。</span><span class="sxs-lookup"><span data-stu-id="64b0d-117">If the value is evaluated to true, the destination field will be created; otherwise the destination field will not be created.</span></span> <span data-ttu-id="64b0d-118">ループでは、論理演算 functoid を使用し、送信先レコードまたはフィールドに接続します。</span><span class="sxs-lookup"><span data-stu-id="64b0d-118">In a looping scenario, use a logical functoid and connect it to the destination record or field.</span></span> <span data-ttu-id="64b0d-119">条件が false に評価される場合、タグは作成されません。</span><span class="sxs-lookup"><span data-stu-id="64b0d-119">If the condition is evaluated to false, the tag will not be created.</span></span> <span data-ttu-id="64b0d-120">例については、次を参照してください。[条件付きループ](../core/conditional-looping.md)します。</span><span class="sxs-lookup"><span data-stu-id="64b0d-120">For an example, see [Conditional Looping](../core/conditional-looping.md).</span></span>  
  
## <a name="forcing-the-creation-of-empty-tags"></a><span data-ttu-id="64b0d-121">空のタグの作成を強制</span><span class="sxs-lookup"><span data-stu-id="64b0d-121">Forcing the Creation of Empty Tags</span></span>  
 <span data-ttu-id="64b0d-122">作成される空のタグを強制的には、[destination] フィールドまたはリンクの Value プロパティに値を追加することができます、 **Concatenate** functoid を目的のフィールド。</span><span class="sxs-lookup"><span data-stu-id="64b0d-122">To force empty tags to be created, you can add a value in the Value property of the destination field or link a **Concatenate** functoid to the destination field.</span></span>  <span data-ttu-id="64b0d-123">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を選択して空のタグの生成を強制することは、"\<空\>"目的のフィールドの値プロパティの値。</span><span class="sxs-lookup"><span data-stu-id="64b0d-123">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], it is possible to force the generation of empty tags by selecting the "\<empty\>" value in the Value property of the destination field.</span></span> <span data-ttu-id="64b0d-124">この場合、フィールド、空の値が作成されます。</span><span class="sxs-lookup"><span data-stu-id="64b0d-124">In this case the field will be created with the empty value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64b0d-125">参照</span><span class="sxs-lookup"><span data-stu-id="64b0d-125">See Also</span></span>  
 <span data-ttu-id="64b0d-126">[値のマッピング (フラット化) Functoid](../core/value-mapping-flattening-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="64b0d-126">[Value Mapping (Flattening) Functoid](../core/value-mapping-flattening-functoid.md) </span></span>  
 <span data-ttu-id="64b0d-127">[値のマッピングをマップに Functoid を追加する方法](../core/how-to-add-value-mapping-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="64b0d-127">[How to Add Value Mapping Functoids to a Map](../core/how-to-add-value-mapping-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="64b0d-128">高度な Functoid</span><span class="sxs-lookup"><span data-stu-id="64b0d-128">Advanced Functoids</span></span>](../core/advanced-functoids.md)