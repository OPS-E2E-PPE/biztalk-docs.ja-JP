---
title: テーブル ドリブン ループの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46e8368dd57b32eab98c1a1dc3432e5be2012363
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973011"
---
# <a name="table-driven-looping-configuration"></a><span data-ttu-id="b3acc-102">テーブルドリブン ループの構成</span><span class="sxs-lookup"><span data-stu-id="b3acc-102">Table-Driven Looping Configuration</span></span>
<span data-ttu-id="b3acc-103">マップのテーブルドリブン ループを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b3acc-103">Follow these steps to configure table-driven looping in your map:</span></span>  
  
- <span data-ttu-id="b3acc-104">**テーブル ループ functoid をマップに追加します。**</span><span class="sxs-lookup"><span data-stu-id="b3acc-104">**Add a Table Looping functoid to the map.**</span></span> <span data-ttu-id="b3acc-105">1 つだけ必要があります**テーブル ループ**テーブルドリブン ループのインスタンスごとの functoid。</span><span class="sxs-lookup"><span data-stu-id="b3acc-105">You need only one **Table Looping** functoid per table-driven looping instance.</span></span> <span data-ttu-id="b3acc-106">たとえば、BillTo および ShipTo 情報を派生させるテーブルドリブン ループを使用する場合必要があります 1 つだけ**テーブル ループ**マップに functoid。</span><span class="sxs-lookup"><span data-stu-id="b3acc-106">For example, if you are using table-driven looping to derive BillTo and ShipTo information, you need only one **Table Looping** functoid in your map.</span></span> <span data-ttu-id="b3acc-107">ただし、BillTo および ShipTo 情報や、StoreName および StoreAddress 情報を派生させるテーブルドリブン ループを使用する場合を必要に応じて 2 つ**テーブル ループ**functoid をマップします。</span><span class="sxs-lookup"><span data-stu-id="b3acc-107">However, if you are using table-driven looping to derive BillTo and ShipTo information and StoreName and StoreAddress information, you might need two **Table Looping** functoids in your map.</span></span>  
  
- <span data-ttu-id="b3acc-108">**表示されているグリッド ページには、1 つ以上のテーブル抽出 functoid を追加します。**</span><span class="sxs-lookup"><span data-stu-id="b3acc-108">**Add one more Table Extractor functoid to the displayed grid page.**</span></span> <span data-ttu-id="b3acc-109">多くの追加**テーブル抽出**ごとと functoid が必要な**テーブル ループ**functoid。</span><span class="sxs-lookup"><span data-stu-id="b3acc-109">Add as many **Table Extractor** functoids as you need for each **Table Looping** functoid.</span></span> <span data-ttu-id="b3acc-110">数**テーブル抽出**functoid は送信先スキーマのフィールドの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b3acc-110">The number of **Table Extractor** functoids depends on the number of fields in the destination schema.</span></span> <span data-ttu-id="b3acc-111">のみがある場合など、 **AddressCode**で、送信元スキーマと CompanyName、アドレス、市区町村、状態、PostalCode、および AttentionName を送信先スキーマ、6 つ追加する必要があります**テーブル抽出**。表示されているグリッド ページに functoid。</span><span class="sxs-lookup"><span data-stu-id="b3acc-111">For example, if you only have an **AddressCode** in your source schema and CompanyName, Address, City, State, PostalCode, and AttentionName in your destination schema, you need to add six **Table Extractor** functoids to the displayed grid page.</span></span>  
  
- <span data-ttu-id="b3acc-112">**適切な入力では、テーブル ループ functoid を構成します。**</span><span class="sxs-lookup"><span data-stu-id="b3acc-112">**Configure the Table Looping functoid with the appropriate inputs.**</span></span> <span data-ttu-id="b3acc-113">最初に、リンク、**テーブル ループ**functoid の入力インスタンス レコードまたは要素にします。</span><span class="sxs-lookup"><span data-stu-id="b3acc-113">First, link the **Table Looping** functoid to the input instance record or element.</span></span> <span data-ttu-id="b3acc-114">また、テーブル ループ Functoid を出力インスタンス メッセージの構造にもリンクします。</span><span class="sxs-lookup"><span data-stu-id="b3acc-114">Also link it to the structure in the output instance message.</span></span> <span data-ttu-id="b3acc-115">次を使用して、入力の構成、**構成\<Functoid\> Functoid**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b3acc-115">Next, configure the inputs by using the **Configure \<Functoid\> Functoid** dialog box.</span></span> <span data-ttu-id="b3acc-116">このプロパティを構成する方法の詳細については、次を参照してください。 [Functoid のプロパティを編集および入力パラメーター](../core/editing-functoid-properties-and-input-parameters.md)します。</span><span class="sxs-lookup"><span data-stu-id="b3acc-116">For more information about how to configure this property, see [Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md) .</span></span> <span data-ttu-id="b3acc-117">入力する入力の一覧は包括的な完全な構成に使用するデータは、このため、ある必要があります、**テーブル Functoid グリッド**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="b3acc-117">The list of inputs you enter must be comprehensive and complete because this is the data that you will use to configure the **Table Functoid Grid** property.</span></span> <span data-ttu-id="b3acc-118">入力は、次のように定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3acc-118">The inputs must be defined as follows:</span></span>  
  
  -   <span data-ttu-id="b3acc-119">**最初の入力。**</span><span class="sxs-lookup"><span data-stu-id="b3acc-119">**First input.**</span></span> <span data-ttu-id="b3acc-120">最初の入力パラメーターは、入力インスタンス メッセージ レコード (またはフィールド) へのリンクです。</span><span class="sxs-lookup"><span data-stu-id="b3acc-120">The first input parameter is the link to the input instance message record or field.</span></span> <span data-ttu-id="b3acc-121">**テーブル ループ**functoid は、レコードまたはフィールドの各インスタンスに対して一度ループします。</span><span class="sxs-lookup"><span data-stu-id="b3acc-121">The **Table Looping** functoid loops once for each instance of the record or field.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="b3acc-122">この入力は必須です。</span><span class="sxs-lookup"><span data-stu-id="b3acc-122">This is a required input.</span></span>  
  
  -   <span data-ttu-id="b3acc-123">**2 番目の入力。**</span><span class="sxs-lookup"><span data-stu-id="b3acc-123">**Second input.**</span></span> <span data-ttu-id="b3acc-124">2 番目の入力パラメーターは、ループ グリッドの列の数を定義します。</span><span class="sxs-lookup"><span data-stu-id="b3acc-124">The second input parameter defines the number of columns in the looping grid.</span></span> <span data-ttu-id="b3acc-125">グリッドには、228 列まで格納できます。</span><span class="sxs-lookup"><span data-stu-id="b3acc-125">The grid may contain up to 228 columns.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="b3acc-126">この入力は必須です。</span><span class="sxs-lookup"><span data-stu-id="b3acc-126">This is a required input.</span></span>  
  
  -   <span data-ttu-id="b3acc-127">**残りの入力。**</span><span class="sxs-lookup"><span data-stu-id="b3acc-127">**Remaining inputs.**</span></span> <span data-ttu-id="b3acc-128">残りの入力、**テーブル ループ**functoid のすべての可能な値に表示される一覧から成る、**テーブル Functoid グリッド**します。</span><span class="sxs-lookup"><span data-stu-id="b3acc-128">The remaining inputs for the **Table Looping** functoid consist of a list of all of the possible values that may appear in the **Table Functoid Grid**.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="b3acc-129">リンクのラベル付けは、非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="b3acc-129">Labeling links is very helpful.</span></span> <span data-ttu-id="b3acc-130">表示されるリンクのラベルを持たない、**テーブル Functoid グリッド**完全指定パス。</span><span class="sxs-lookup"><span data-stu-id="b3acc-130">Without labels, links appear in the **Table Functoid Grid** as fully specified paths.</span></span>  
  
       <span data-ttu-id="b3acc-131">入力を構成する方法についてステップ バイ ステップの手順について、**テーブル ループ**functoid を参照してください[テーブル ループの追加とテーブル抽出 Functoid をマップする方法](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)します。</span><span class="sxs-lookup"><span data-stu-id="b3acc-131">For step-by-step instructions about how to configure inputs for the **Table Looping** functoid, see [How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md).</span></span> <span data-ttu-id="b3acc-132">具体的には、手順 3. ~ 8. を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3acc-132">In particular, see steps 3 through 8.</span></span>  
  
- <span data-ttu-id="b3acc-133">**テーブル ループ functoid のテーブル Functoid グリッド プロパティを構成します。**</span><span class="sxs-lookup"><span data-stu-id="b3acc-133">**Configure the Table Functoid Grid property of the Table Looping functoid.**</span></span> <span data-ttu-id="b3acc-134">使用して、**テーブル Functoid グリッド**プロパティを開き、**テーブル ループ Functoid の構成**ループ グリッドのセルを構成する ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b3acc-134">Use the **Table Functoid Grid** property to open the **Configure Table Looping Functoid** dialog box in which you configure the cells in the looping grid.</span></span>  
  
   <span data-ttu-id="b3acc-135">ループのグリッドを構成する方法の詳しい手順については、「[テーブル ループの追加とテーブル抽出 Functoid をマップする方法](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)します。</span><span class="sxs-lookup"><span data-stu-id="b3acc-135">For step-by-step instructions about how to configure the looping grid, see [How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md).</span></span> <span data-ttu-id="b3acc-136">特に手順 9. と 10. が重要です。</span><span class="sxs-lookup"><span data-stu-id="b3acc-136">In particular, see steps 9 and 10.</span></span>  
  
- <span data-ttu-id="b3acc-137">**テーブル抽出 functoid を構成します。**</span><span class="sxs-lookup"><span data-stu-id="b3acc-137">**Configure the Table Extractor functoids.**</span></span> <span data-ttu-id="b3acc-138">使用して、**入力パラメーター**プロパティを構成する、**テーブル抽出**functoid は次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b3acc-138">Use the **Input Parameters** property to configure the **Table Extractor** functoid inputs as follows:</span></span>  
  
  - <span data-ttu-id="b3acc-139">**最初の入力。**</span><span class="sxs-lookup"><span data-stu-id="b3acc-139">**First input.**</span></span> <span data-ttu-id="b3acc-140">最初の入力パラメーター、**テーブル抽出**functoid は、**テーブル ループ**functoid。</span><span class="sxs-lookup"><span data-stu-id="b3acc-140">The first input parameter to a **Table Extractor** functoid is the **Table Looping** functoid.</span></span>  
  
  - <span data-ttu-id="b3acc-141">**2 番目の入力。**</span><span class="sxs-lookup"><span data-stu-id="b3acc-141">**Second input.**</span></span> <span data-ttu-id="b3acc-142">2 番目の入力パラメーターは、データを抽出する行の列を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3acc-142">The second input parameter specifies the column in the row from which to extract data.</span></span>  
  
    <span data-ttu-id="b3acc-143">ステップ バイ ステップの手順を構成する方法について、**テーブル抽出**functoid に関連付けられている、**テーブル ループ**functoid を参照してください[テーブル ループの追加とテーブル抽出する方法マップに Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)します。</span><span class="sxs-lookup"><span data-stu-id="b3acc-143">For step-by-step instructions about how to configure the **Table Extractor** functoids associated with a **Table Looping** functoid, see [How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md).</span></span> <span data-ttu-id="b3acc-144">特に手順 11 ～ 16 が重要です。</span><span class="sxs-lookup"><span data-stu-id="b3acc-144">In particular, see steps 11 through 16.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3acc-145">参照</span><span class="sxs-lookup"><span data-stu-id="b3acc-145">See Also</span></span>  
 <span data-ttu-id="b3acc-146">[テーブル ループ Functoid](../core/table-looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="b3acc-146">[Table Looping Functoid](../core/table-looping-functoid.md) </span></span>  
 <span data-ttu-id="b3acc-147">[テーブル抽出 Functoid](../core/table-extractor-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="b3acc-147">[Table Extractor Functoid](../core/table-extractor-functoid.md) </span></span>  
 <span data-ttu-id="b3acc-148">[テーブル ドリブン ループの例](../core/table-driven-looping-example.md) </span><span class="sxs-lookup"><span data-stu-id="b3acc-148">[Table-Driven Looping Example](../core/table-driven-looping-example.md) </span></span>  
 <span data-ttu-id="b3acc-149">[マップにテーブル抽出 Functoid およびテーブル ループを追加する方法](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="b3acc-149">[How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="b3acc-150">[高度な Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="b3acc-150">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="b3acc-151">[インデックス Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="b3acc-151">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="b3acc-152">[繰り返し Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="b3acc-152">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 <span data-ttu-id="b3acc-153">[ループ Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="b3acc-153">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="b3acc-154">レコード カウント Functoid</span><span class="sxs-lookup"><span data-stu-id="b3acc-154">Record Count Functoid</span></span>](../core/record-count-functoid.md)