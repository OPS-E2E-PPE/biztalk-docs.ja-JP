---
title: "テーブルドリブン ループの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Table Looping functoids
- Table Extractor functoids, configuring
- Table Extractor functoids
- Table Extractor functoids, adding to grid
- Table Looping functoids, about Table Looping functoids
- Table Looping functoids, configuring
- Table Extractor functoids, about Table Extractor functoids
- Table Looping functoids, adding to map
ms.assetid: ecc24d9b-ebc0-4559-9746-58e3b00c02ab
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2563c7f26d2beb0eba33173507989cc85aaabda1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="table-driven-looping-configuration"></a><span data-ttu-id="cb67b-102">テーブルドリブン ループの構成</span><span class="sxs-lookup"><span data-stu-id="cb67b-102">Table-Driven Looping Configuration</span></span>
<span data-ttu-id="cb67b-103">マップのテーブルドリブン ループを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb67b-103">Follow these steps to configure table-driven looping in your map:</span></span>  
  
-   <span data-ttu-id="cb67b-104">**テーブル ループ functoid をマップに追加します。**</span><span class="sxs-lookup"><span data-stu-id="cb67b-104">**Add a Table Looping functoid to the map.**</span></span> <span data-ttu-id="cb67b-105">1 つだけで済みます**テーブル ループ**functoid ごと、テーブルドリブン ループのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="cb67b-105">You need only one **Table Looping** functoid per table-driven looping instance.</span></span> <span data-ttu-id="cb67b-106">たとえば、テーブルドリブン ループを BillTo および ShipTo 情報を派生させるために使用する場合必要があります 1 つだけ**テーブル ループ**functoid マップにします。</span><span class="sxs-lookup"><span data-stu-id="cb67b-106">For example, if you are using table-driven looping to derive BillTo and ShipTo information, you need only one **Table Looping** functoid in your map.</span></span> <span data-ttu-id="cb67b-107">ただし、テーブルドリブン ループを BillTo および ShipTo 情報や、StoreName および StoreAddress 情報を派生させるために使用する場合必要があります 2**テーブル ループ**functoid をマップします。</span><span class="sxs-lookup"><span data-stu-id="cb67b-107">However, if you are using table-driven looping to derive BillTo and ShipTo information and StoreName and StoreAddress information, you might need two **Table Looping** functoids in your map.</span></span>  
  
-   <span data-ttu-id="cb67b-108">**表示されているグリッド ページに 1 つ以上のテーブル抽出 functoid を追加します。**</span><span class="sxs-lookup"><span data-stu-id="cb67b-108">**Add one more Table Extractor functoid to the displayed grid page.**</span></span> <span data-ttu-id="cb67b-109">いくつでも追加**テーブル抽出**ごとと functoid が必要な**テーブル ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="cb67b-109">Add as many **Table Extractor** functoids as you need for each **Table Looping** functoid.</span></span> <span data-ttu-id="cb67b-110">数**テーブル抽出**functoid は送信先スキーマ内のフィールドの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="cb67b-110">The number of **Table Extractor** functoids depends on the number of fields in the destination schema.</span></span> <span data-ttu-id="cb67b-111">たとえば、しかない場合、 **AddressCode**で、送信元スキーマと CompanyName、アドレス、City、状態、PostalCode、および送信先スキーマの AttentionName、6 つ追加する必要があります**テーブル抽出**。functoid は、表示されているグリッド ページにします。</span><span class="sxs-lookup"><span data-stu-id="cb67b-111">For example, if you only have an **AddressCode** in your source schema and CompanyName, Address, City, State, PostalCode, and AttentionName in your destination schema, you need to add six **Table Extractor** functoids to the displayed grid page.</span></span>  
  
-   <span data-ttu-id="cb67b-112">**適切な入力で、テーブル ループ functoid を構成します。**</span><span class="sxs-lookup"><span data-stu-id="cb67b-112">**Configure the Table Looping functoid with the appropriate inputs.**</span></span> <span data-ttu-id="cb67b-113">最初に、リンク、**テーブル ループ**functoid の入力インスタンス レコードまたは要素を送信します。</span><span class="sxs-lookup"><span data-stu-id="cb67b-113">First, link the **Table Looping** functoid to the input instance record or element.</span></span> <span data-ttu-id="cb67b-114">また、テーブル ループ Functoid を出力インスタンス メッセージの構造にもリンクします。</span><span class="sxs-lookup"><span data-stu-id="cb67b-114">Also link it to the structure in the output instance message.</span></span> <span data-ttu-id="cb67b-115">使用して、入力を次に、構成、**構成\<Functoid > Functoid**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="cb67b-115">Next, configure the inputs by using the **Configure \<Functoid> Functoid** dialog box.</span></span> <span data-ttu-id="cb67b-116">このプロパティを構成する方法の詳細については、次を参照してください。 [Functoid のプロパティを編集および入力パラメーター](../core/editing-functoid-properties-and-input-parameters.md)です。</span><span class="sxs-lookup"><span data-stu-id="cb67b-116">For more information about how to configure this property, see [Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md) .</span></span> <span data-ttu-id="cb67b-117">これは、データを構成するのに使用するために、入力の一覧が包括的で完全なをする必要があります、**テーブル Functoid グリッド**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="cb67b-117">The list of inputs you enter must be comprehensive and complete because this is the data that you will use to configure the **Table Functoid Grid** property.</span></span> <span data-ttu-id="cb67b-118">入力は、次のように定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb67b-118">The inputs must be defined as follows:</span></span>  
  
    -   <span data-ttu-id="cb67b-119">**最初の入力。**</span><span class="sxs-lookup"><span data-stu-id="cb67b-119">**First input.**</span></span> <span data-ttu-id="cb67b-120">最初の入力パラメーターは、入力インスタンス メッセージ レコード (またはフィールド) へのリンクです。</span><span class="sxs-lookup"><span data-stu-id="cb67b-120">The first input parameter is the link to the input instance message record or field.</span></span> <span data-ttu-id="cb67b-121">**テーブル ループ**functoid は、レコードまたはフィールドの各インスタンスに対して一度ループします。</span><span class="sxs-lookup"><span data-stu-id="cb67b-121">The **Table Looping** functoid loops once for each instance of the record or field.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="cb67b-122">この入力は必須です。</span><span class="sxs-lookup"><span data-stu-id="cb67b-122">This is a required input.</span></span>  
  
    -   <span data-ttu-id="cb67b-123">**2 番目の入力します。**</span><span class="sxs-lookup"><span data-stu-id="cb67b-123">**Second input.**</span></span> <span data-ttu-id="cb67b-124">2 番目の入力パラメーターは、ループ グリッドの列の数を定義します。</span><span class="sxs-lookup"><span data-stu-id="cb67b-124">The second input parameter defines the number of columns in the looping grid.</span></span> <span data-ttu-id="cb67b-125">グリッドには、228 列まで格納できます。</span><span class="sxs-lookup"><span data-stu-id="cb67b-125">The grid may contain up to 228 columns.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="cb67b-126">この入力は必須です。</span><span class="sxs-lookup"><span data-stu-id="cb67b-126">This is a required input.</span></span>  
  
    -   <span data-ttu-id="cb67b-127">**残りの入力。**</span><span class="sxs-lookup"><span data-stu-id="cb67b-127">**Remaining inputs.**</span></span> <span data-ttu-id="cb67b-128">残りの入力、**テーブル ループ**functoid に含めることは有効な値のすべての一覧から成る、**テーブル Functoid グリッド**です。</span><span class="sxs-lookup"><span data-stu-id="cb67b-128">The remaining inputs for the **Table Looping** functoid consist of a list of all of the possible values that may appear in the **Table Functoid Grid**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="cb67b-129">リンクのラベル付けは、非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="cb67b-129">Labeling links is very helpful.</span></span> <span data-ttu-id="cb67b-130">表示されるリンクのラベルを持たない、**テーブル Functoid グリッド**完全指定パス。</span><span class="sxs-lookup"><span data-stu-id="cb67b-130">Without labels, links appear in the **Table Functoid Grid** as fully specified paths.</span></span>  
  
         <span data-ttu-id="cb67b-131">手順の入力を構成する方法については、**テーブル ループ**functoid を参照してください[テーブル ループの追加、およびテーブル抽出 Functoid をマップする方法](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)です。</span><span class="sxs-lookup"><span data-stu-id="cb67b-131">For step-by-step instructions about how to configure inputs for the **Table Looping** functoid, see [How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md).</span></span> <span data-ttu-id="cb67b-132">具体的には、手順 3. ~ 8. を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb67b-132">In particular, see steps 3 through 8.</span></span>  
  
-   <span data-ttu-id="cb67b-133">**テーブル ループ functoid のテーブル Functoid グリッド プロパティを構成します。**</span><span class="sxs-lookup"><span data-stu-id="cb67b-133">**Configure the Table Functoid Grid property of the Table Looping functoid.**</span></span> <span data-ttu-id="cb67b-134">使用して、**テーブル Functoid グリッド**プロパティを開くには、 **[テーブル ループ Functoid**ループ グリッドのセルを構成する] ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="cb67b-134">Use the **Table Functoid Grid** property to open the **Configure Table Looping Functoid** dialog box in which you configure the cells in the looping grid.</span></span>  
  
     <span data-ttu-id="cb67b-135">ループのグリッドを構成する方法に関する詳細な手順については、次を参照してください。[テーブル ループの追加、およびテーブル抽出 Functoid をマップする方法](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)です。</span><span class="sxs-lookup"><span data-stu-id="cb67b-135">For step-by-step instructions about how to configure the looping grid, see [How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md).</span></span> <span data-ttu-id="cb67b-136">特に手順 9. と 10. が重要です。</span><span class="sxs-lookup"><span data-stu-id="cb67b-136">In particular, see steps 9 and 10.</span></span>  
  
-   <span data-ttu-id="cb67b-137">**テーブル抽出 functoid を構成します。**</span><span class="sxs-lookup"><span data-stu-id="cb67b-137">**Configure the Table Extractor functoids.**</span></span> <span data-ttu-id="cb67b-138">使用して、**入力パラメーター**プロパティを構成する、**テーブル抽出**functoid は次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="cb67b-138">Use the **Input Parameters** property to configure the **Table Extractor** functoid inputs as follows:</span></span>  
  
    -   <span data-ttu-id="cb67b-139">**最初の入力。**</span><span class="sxs-lookup"><span data-stu-id="cb67b-139">**First input.**</span></span> <span data-ttu-id="cb67b-140">最初の入力パラメーター、**テーブル抽出**functoid は、**テーブル ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="cb67b-140">The first input parameter to a **Table Extractor** functoid is the **Table Looping** functoid.</span></span>  
  
    -   <span data-ttu-id="cb67b-141">**2 番目の入力します。**</span><span class="sxs-lookup"><span data-stu-id="cb67b-141">**Second input.**</span></span> <span data-ttu-id="cb67b-142">2 番目の入力パラメーターは、データを抽出する行の列を指定します。</span><span class="sxs-lookup"><span data-stu-id="cb67b-142">The second input parameter specifies the column in the row from which to extract data.</span></span>  
  
     <span data-ttu-id="cb67b-143">手順を構成する方法については、**テーブル抽出**functoid に関連付けられている、**テーブル ループ**functoid を参照してください[テーブル ループの追加、およびテーブル抽出する方法マップに Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)です。</span><span class="sxs-lookup"><span data-stu-id="cb67b-143">For step-by-step instructions about how to configure the **Table Extractor** functoids associated with a **Table Looping** functoid, see [How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md).</span></span> <span data-ttu-id="cb67b-144">特に手順 11 ～ 16 が重要です。</span><span class="sxs-lookup"><span data-stu-id="cb67b-144">In particular, see steps 11 through 16.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb67b-145">参照</span><span class="sxs-lookup"><span data-stu-id="cb67b-145">See Also</span></span>  
 <span data-ttu-id="cb67b-146">[テーブル ループ Functoid](../core/table-looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="cb67b-146">[Table Looping Functoid](../core/table-looping-functoid.md) </span></span>  
 <span data-ttu-id="cb67b-147">[テーブル抽出 Functoid](../core/table-extractor-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="cb67b-147">[Table Extractor Functoid](../core/table-extractor-functoid.md) </span></span>  
 <span data-ttu-id="cb67b-148">[テーブルドリブン ループの例](../core/table-driven-looping-example.md) </span><span class="sxs-lookup"><span data-stu-id="cb67b-148">[Table-Driven Looping Example](../core/table-driven-looping-example.md) </span></span>  
 <span data-ttu-id="cb67b-149">[テーブル ループを追加する方法と、マップにテーブル抽出 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="cb67b-149">[How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="cb67b-150">[高度な Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="cb67b-150">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="cb67b-151">[インデックス Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="cb67b-151">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="cb67b-152">[繰り返し Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="cb67b-152">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 <span data-ttu-id="cb67b-153">[ループ Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="cb67b-153">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="cb67b-154">レコード カウント Functoid</span><span class="sxs-lookup"><span data-stu-id="cb67b-154">Record Count Functoid</span></span>](../core/record-count-functoid.md)