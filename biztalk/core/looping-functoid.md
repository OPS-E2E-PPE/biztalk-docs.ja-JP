---
title: ループ Functoid |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19886ccb-4642-48a4-b93e-563640ea828b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ce2b66fd796708a0e8b24ee05e3a0b043af6808
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
ms.locfileid: "22262842"
---
# <a name="looping-functoid"></a><span data-ttu-id="46580-102">ループ Functoid</span><span class="sxs-lookup"><span data-stu-id="46580-102">Looping Functoid</span></span>

## <a name="overview--example"></a><span data-ttu-id="46580-103">概要 & の使用例</span><span class="sxs-lookup"><span data-stu-id="46580-103">Overview & example</span></span>
<span data-ttu-id="46580-104">**ループ** functoid が複数のレコードまたは送信元スキーマ内のフィールドを送信先スキーマの 1 つのレコードに結合します。</span><span class="sxs-lookup"><span data-stu-id="46580-104">The **Looping** functoid combines multiple records or fields in the source schema into a single record in the destination schema.</span></span>  
  
 <span data-ttu-id="46580-105">次に示します、 **ループ**単一のマスター住所リストに 2 つの異なる調査から収集された functoid のマップ内でアドレスを結合するために使用します。</span><span class="sxs-lookup"><span data-stu-id="46580-105">The following figure shows a **Looping**functoid used in a map to combine addresses collected from two different surveys into a single master address list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46580-106">**ループ** と **値のマッピング (フラット化)** functoid をまとめて使用しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="46580-106">The **Looping** and **Value Mapping (Flattening)** functoids should not be used together.</span></span> <span data-ttu-id="46580-107">送信元の下にある対象ノードの依存関係のループがないと見なさコンパイル済みのマップの結果、両方をまとめて使用する場合、 **ループ** functoid です。</span><span class="sxs-lookup"><span data-stu-id="46580-107">If both are used together, it results in a compiled map that assumed there is no source looping dependency for the target nodes that are below the **Looping** functoid.</span></span>  
  
 <span data-ttu-id="46580-108">![ループ functoid の使用方法を示すマップです。] (../core/media/loopingfunctoid.gif "loopingfunctoid")</span><span class="sxs-lookup"><span data-stu-id="46580-108">![Map illustrating the use of the looping functoid.](../core/media/loopingfunctoid.gif "loopingfunctoid")</span></span>  
  
 <span data-ttu-id="46580-109">**FoodSurvey** と **FlowerSurvey** 、送信元スキーマのループ レコードは、ループにマップされる **アドレス** 、送信先スキーマのレコードです。</span><span class="sxs-lookup"><span data-stu-id="46580-109">The **FoodSurvey** and **FlowerSurvey** looping records of the source schema are mapped to the looping **Address** record of the destination schema.</span></span> <span data-ttu-id="46580-110">3 つの入力インスタンス メッセージがある場合 **FoodSurvey** レコードと 2 つ **FlowerSurvey** 、レコード、 **ループ**functoid では、これらの 5 つを作成する結合 **アドレス** 出力インスタンス メッセージ内のレコードです。</span><span class="sxs-lookup"><span data-stu-id="46580-110">If an input instance message has three **FoodSurvey** records and two **FlowerSurvey** records, the **Looping**functoid combines these to create five **Address** records in the output instance message.</span></span>  
  
 <span data-ttu-id="46580-111">次のコードは、入力インスタンス メッセージのサンプルです。</span><span class="sxs-lookup"><span data-stu-id="46580-111">The following code is a sample input instance message.</span></span>  
  
```  
<ns0:Surveys xmlns:ns0="http://LoopingFunctoid.Surveys">  
    <FoodSurvey Name="Karin Zimprich" Address="345 N 63rd St" City="Boston" State="MA" PostalCode="07485" />  
    <FoodSurvey Name="Wendy Wheeler" Address="7890 Broadway" City="Columbus" State="OH" PostalCode="46290" />  
    <FoodSurvey Name="Florian Voss" Address="1234 Main St" City="Denver" State="CO" PostalCode="97402" />  
    <FlowerSurvey Name="Kelly Focht" Address="456 1st Ave" City="Miami" State="FL" PostalCode="81406" />  
    <FlowerSurvey Name="Jim Kim" Address="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103" />  
</ns0:Surveys>  
```  
  
 <span data-ttu-id="46580-112">この入力インスタンス メッセージを上の図に示したマップで処理すると、次の出力インスタンス メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="46580-112">This input instance message produces the following output instance message when processed by the map in the preceding figure.</span></span>  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Name="Karin Zimprich" Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458"/>  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290"/>  
    <Address Name="Florian Voss" Street="1234 Main St" City="Denver" State="CO" PostalCode="97402"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103"/>  
</ns0:MasterAddresses>  
```  
  
 <span data-ttu-id="46580-113">**FoodSurvey** と **FlowerSurvey** メッセージのアドレスがまとめられます。</span><span class="sxs-lookup"><span data-stu-id="46580-113">The **FoodSurvey** and **FlowerSurvey** message addresses have been combined.</span></span> <span data-ttu-id="46580-114">まとめられたメッセージでは、各アドレスの送信元は示されません。</span><span class="sxs-lookup"><span data-stu-id="46580-114">The combined message does not indicate the source of each address.</span></span> <span data-ttu-id="46580-115">元を追跡する場合は、追加、 **ソース** 属性を **アドレス** のレコード、 **MasterAddress** スキーマとマップを定数値です。</span><span class="sxs-lookup"><span data-stu-id="46580-115">If you want to track the source, add a **Source** attribute to the **Address** record of the **MasterAddress** schema and map a constant value.</span></span> <span data-ttu-id="46580-116">この値を設定するには、接続、 **FoodSurvey** フィールドを新しい **ソース** フィールドです。</span><span class="sxs-lookup"><span data-stu-id="46580-116">To set this value, connect the **FoodSurvey** field to the new **Source** field.</span></span> <span data-ttu-id="46580-117">コネクタ線上では、変更、 **リンク プロパティ** &#124; **コンパイラ** &#124; **リンクのソース** を「名前のコピー」プロパティです。</span><span class="sxs-lookup"><span data-stu-id="46580-117">On the connector line, modify the **Link Properties** &#124; **Compiler** &#124; **Source Links** property to "Copy name".</span></span> <span data-ttu-id="46580-118">に対して、このプロセスを繰り返して、 **FlowerSurvey** フィールドです。</span><span class="sxs-lookup"><span data-stu-id="46580-118">Repeat this process for the **FlowerSurvey** field.</span></span> <span data-ttu-id="46580-119">ここから入力メッセージを再処理すると、次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="46580-119">Reprocessing the input message from above yields the following output:</span></span>  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Name="Karin Zimprich" Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458" Source="FoodSurvey"/>  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290" Source="FoodSurvey"/>  
    <Address Name="Florian Voss" Street="1234 Main St" City="Denver" State="CO" PostalCode="97402" Source="FoodSurvey"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406" Source="FlowerSurvey"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103" Source="FlowerSurvey"/>  
</ns0:MasterAddresses>  
```  

## <a name="relationships-with-nodes"></a><span data-ttu-id="46580-120">ノードとの関係</span><span class="sxs-lookup"><span data-stu-id="46580-120">Relationships with nodes</span></span>

 <span data-ttu-id="46580-121">ノード間のリレーションシップの動作に影響する、 **ループ** functoid です。</span><span class="sxs-lookup"><span data-stu-id="46580-121">Relationships among nodes affect the behavior of the **Looping** functoid.</span></span> <span data-ttu-id="46580-122">たとえば、子ノードと、ソース スキーマ内の親の両方のリンク、 **ループ** functoid により、宛先ノードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="46580-122">For example, linking both a child node and its parent in the source schema to the **Looping** functoid prevents the destination node from being created.</span></span>  
  
 <span data-ttu-id="46580-123">Functoid は、送信元ノード間のリレーションシップにも影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="46580-123">Functoids are also affected by the relationships among source nodes.</span></span> <span data-ttu-id="46580-124">ソース ノードの兄弟ではない子フィールドに、functoid を接続する、 **ループ** functoid が予期しない結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="46580-124">Connecting a functoid to non-sibling child fields of source nodes of the **Looping** functoid may produce unexpected results.</span></span> <span data-ttu-id="46580-125">使用例を **文字列連結** を組み合わせる functoid、 **FoodSurvey** 名 フィールドと **FlowerSurvey** Address フィールドのアドレス フィールドに **MasterAddress** と次の出力インスタンス メッセージが生成します。</span><span class="sxs-lookup"><span data-stu-id="46580-125">For example, using the **String Concatenate** functoid to combine the **FoodSurvey** Name field and **FlowerSurvey** Address field into the Address Name field in **MasterAddress** would produce the following output instance message:</span></span>  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://LoopingFunctoid.MasterAddresses">  
    <Address Street="345 N 63rd St" City="Boston" State="MA" PostalCode="07458"/>  
    <Address Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290"/>  
    <Address Street="1234 Main St" City="Denver" State="CO" PostalCode="97402"/>  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406"/>  
    <Address Name="Jim Kim" Street="567 2nd Ave" City="Seattle" State="WA" PostalCode="98103"/>  
</ns0:MasterAddresses>  
```  
  
 <span data-ttu-id="46580-126">注意してください方法 **名前** フィールドが **FoodSurvey** ソース メッセージになくがの存在 **FlowerSurvey** メッセージのソースします。</span><span class="sxs-lookup"><span data-stu-id="46580-126">Notice how the **Name** field is missing for **FoodSurvey** source messages but is present for **FlowerSurvey** source messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="46580-127">ソース ノードの子フィールドに、functoid を接続する、 **ループ** functoid は、送信元ノードは兄弟ではない場合に、予期しない結果になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="46580-127">Connecting a functoid to child fields of source nodes of the **Looping** functoid may produce unexpected results if the source nodes are not siblings.</span></span>  
  
 <span data-ttu-id="46580-128">**ループ** functoid は、条件付きループを作成し、カタログにスキーマのマップに使用できる強力な構造です。</span><span class="sxs-lookup"><span data-stu-id="46580-128">The **Looping** functoid is a powerful construct that you can use to create conditional loops and to map schemas to catalogs.</span></span> <span data-ttu-id="46580-129">重複するいくつかの影響もあります **ループ** functoid のパスを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46580-129">There are also some effects of overlapping **Looping** functoid paths you need to take into account.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="46580-130">次の手順</span><span class="sxs-lookup"><span data-stu-id="46580-130">Next steps</span></span>
  
-   [<span data-ttu-id="46580-131">条件付きループ</span><span class="sxs-lookup"><span data-stu-id="46580-131">Conditional Looping</span></span>](../core/conditional-looping.md)  
  
-   [<span data-ttu-id="46580-132">カタログに対するフラット スキーマ</span><span class="sxs-lookup"><span data-stu-id="46580-132">Flat Schema to Catalog</span></span>](../core/flat-schema-to-catalog.md)  
  
-   [<span data-ttu-id="46580-133">ループ パス</span><span class="sxs-lookup"><span data-stu-id="46580-133">Loop Paths</span></span>](../core/loop-paths.md)  
  
## <a name="see-also"></a><span data-ttu-id="46580-134">参照</span><span class="sxs-lookup"><span data-stu-id="46580-134">See Also</span></span>  
 <span data-ttu-id="46580-135">**テーブル ループ Functoid リファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="46580-135">**Table Looping Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>