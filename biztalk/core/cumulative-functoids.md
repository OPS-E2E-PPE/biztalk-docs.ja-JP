---
title: 累積 Functoid |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f0549867-e0e4-4cdb-aae0-cadc99088e03
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6ed3d5037d64cf21e1ee2676a5739f13e18da3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240066"
---
# <a name="cumulative-functoids"></a><span data-ttu-id="8150c-102">累積 Functoid</span><span class="sxs-lookup"><span data-stu-id="8150c-102">Cumulative Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="8150c-103">概要</span><span class="sxs-lookup"><span data-stu-id="8150c-103">Overview</span></span>
<span data-ttu-id="8150c-104">**累積的な**functoid は、合計、連結された文字列の場合は、平均などの単一の値に、一連の値を削減します。</span><span class="sxs-lookup"><span data-stu-id="8150c-104">**Cumulative** functoids reduce a series of values to a single value such as a sum, a concatenated string, or an average.</span></span>  
  
 <span data-ttu-id="8150c-105">すべて**累積**functoid は、2 つの入力パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8150c-105">All **Cumulative** functoids accept two input parameters:</span></span>  
  
1.  <span data-ttu-id="8150c-106">累積する値。</span><span class="sxs-lookup"><span data-stu-id="8150c-106">The value to accumulate.</span></span> <span data-ttu-id="8150c-107">この値はすべての数値**累積**functoid を除く、**累積連結**functoid は、文字列値が必要です。</span><span class="sxs-lookup"><span data-stu-id="8150c-107">This value is numeric for all **Cumulative** functoids except the **Cumulative Concatenate** functoid which expects a string value.</span></span> <span data-ttu-id="8150c-108">値からでは、リンク、多くの場合、**フィールド属性**、**フィールド要素**、または**レコード**ノード (とその**Mixed**プロパティに設定する**True**)。</span><span class="sxs-lookup"><span data-stu-id="8150c-108">The value is a link, often from a **Field Attribute**, **Field Element**, or **Record** node (with its **Mixed** property set to **True**).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8150c-109">祖先にない場合**レコード**を使用して、スキーマ ツリー内のノードがループ、**累積**functoid が必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="8150c-109">If none of the ancestor **Record** nodes in the schema tree are looping, using a **Cumulative** functoid is unnecessary.</span></span>  
  
2.  <span data-ttu-id="8150c-110">値を累積する範囲。</span><span class="sxs-lookup"><span data-stu-id="8150c-110">The scope within which the value is accumulated.</span></span> <span data-ttu-id="8150c-111">この引数は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="8150c-111">This argument is optional.</span></span> <span data-ttu-id="8150c-112">この引数は、指定された値を累積するレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="8150c-112">The argument indicates how closely related the specified values must be to be accumulated.</span></span>  
  
 <span data-ttu-id="8150c-113">次の表は、スコープ パラメーターの値とその動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="8150c-113">The following table shows the values for the scoping parameter and its effect:</span></span>  
  
|<span data-ttu-id="8150c-114">スコープ パラメーターの値</span><span class="sxs-lookup"><span data-stu-id="8150c-114">Scoping Parameter Value</span></span>|<span data-ttu-id="8150c-115">結果</span><span class="sxs-lookup"><span data-stu-id="8150c-115">Effect</span></span>|  
|-----------------------------|------------|  
|<span data-ttu-id="8150c-116">0 (ゼロ)</span><span class="sxs-lookup"><span data-stu-id="8150c-116">0 (zero)</span></span>|<span data-ttu-id="8150c-117">インスタンス メッセージ全体の値を累積します。</span><span class="sxs-lookup"><span data-stu-id="8150c-117">Accumulate the value over the entire instance message.</span></span> <span data-ttu-id="8150c-118">既定値です。</span><span class="sxs-lookup"><span data-stu-id="8150c-118">The default.</span></span>|  
|<span data-ttu-id="8150c-119">1 (one)</span><span class="sxs-lookup"><span data-stu-id="8150c-119">1 (one)</span></span>|<span data-ttu-id="8150c-120">同じ親要素を持つ要素の値または属性値を累積します。</span><span class="sxs-lookup"><span data-stu-id="8150c-120">Accumulate the value of element or attribute values with the same parent element.</span></span>|  
|<span data-ttu-id="8150c-121">2</span><span class="sxs-lookup"><span data-stu-id="8150c-121">2</span></span>|<span data-ttu-id="8150c-122">同じ祖父要素を持つ要素の値または属性値を累積します。</span><span class="sxs-lookup"><span data-stu-id="8150c-122">Accumulate the value of element or attribute values with the same grandparent element.</span></span>|  
|<span data-ttu-id="8150c-123">3 以上</span><span class="sxs-lookup"><span data-stu-id="8150c-123">3 or greater</span></span>|<span data-ttu-id="8150c-124">上記のパターンよりもさらに幅の広い範囲 (祖父の親要素、祖父の祖父要素など) の要素の値または属性値を累積します。</span><span class="sxs-lookup"><span data-stu-id="8150c-124">Accumulate the value of element or attribute values of progressively wider scope following the preceding pattern (great-grandparent, great-great-grandparent, etc.).</span></span>|  

## <a name="example"></a><span data-ttu-id="8150c-125">例</span><span class="sxs-lookup"><span data-stu-id="8150c-125">Example</span></span>  
 <span data-ttu-id="8150c-126">使用例、**累積**functoid がコストを合計する注文全体でします。</span><span class="sxs-lookup"><span data-stu-id="8150c-126">An example of using a **Cumulative** functoid might be summing costs across a purchase order.</span></span> <span data-ttu-id="8150c-127">次のコードは、注文書の例です。</span><span class="sxs-lookup"><span data-stu-id="8150c-127">The following code is an example of a purchase order.</span></span>  
  
```  
<ns0:PurchaseOrder xmlns:ns0="http://CumulativeFunctoid.PurchaseOrder">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <LineItems>  
        <Item>  
            <Product>Laptop Computer</Product>  
            <Description>Thin profile laptop</Description>  
            <Price>1999.95</Price>  
            <Quantity>1</Quantity>  
        </Item>  
        <Item>  
            <Product>Monitor Swipes</Product>  
            <Description>Disposable monitor swipes</Description>  
            <Price>3.95</Price>  
            <Quantity>10</Quantity>  
        </Item>  
    </LineItems>  
</ns0:PurchaseOrder>  
```  
  
 <span data-ttu-id="8150c-128">**Max Occurs**プロパティを**項目**レコードはありますが、もちろん、 **unbounded**です。</span><span class="sxs-lookup"><span data-stu-id="8150c-128">The **Max Occurs** property for the **Item** record would, of course, be **unbounded**.</span></span> <span data-ttu-id="8150c-129">これは、Item レコードがループすることを示しています。BizTalk マッパーは、このレコードをループとしてコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="8150c-129">This indicates that the item record loops, and BizTalk Mapper compiles this record as a loop.</span></span>  
  
 <span data-ttu-id="8150c-130">次の図を使用して、マップ、**乗算**functoid と**累積合計**item レコードを集計で functoid の入力方向の発注書とで結果を出力、 **POTotal**フィールド。</span><span class="sxs-lookup"><span data-stu-id="8150c-130">The following figure shows a map using a **Multiplication** functoid and a **Cumulative Sum** functoid to aggregate item records from an incoming purchase order and output the results in the **POTotal** field:</span></span>  
  
 <span data-ttu-id="8150c-131">![累積合計 functoid の使用方法を示すマップ。] (../core/media/cumulativefunctoids.gif "cumulativefunctoids")</span><span class="sxs-lookup"><span data-stu-id="8150c-131">![Map showing usage of the cumulative sum functoid.](../core/media/cumulativefunctoids.gif "cumulativefunctoids")</span></span>  

  
 <span data-ttu-id="8150c-132">このマップでは、前のデータと既定のスコープ パラメーターの値 0 (ゼロ) を使用して、次の出力結果を生成しています。</span><span class="sxs-lookup"><span data-stu-id="8150c-132">The map produces the following output with the preceding data and with the default scoping parameter value, 0 (zero):</span></span>  
  
```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
</ns0:SummedPO>  
```  
  
 <span data-ttu-id="8150c-133">この例ではすべて、**項目**レコードに属する、 **LineItems**レコードが蓄積されるに参加: スコープ パラメーターの既定値は、メッセージ全体の値が累積されることを示します。</span><span class="sxs-lookup"><span data-stu-id="8150c-133">In this example, all the **Item** records under the **LineItems** record participate in the accumulation—the default for the scoping parameter indicates accumulating the values across the entire message.</span></span> <span data-ttu-id="8150c-134">**価格**と**数量**フィールドに送信される、**乗算**functoid です。</span><span class="sxs-lookup"><span data-stu-id="8150c-134">The **Price** and **Quantity** fields are sent to a **Multiplication** functoid.</span></span> <span data-ttu-id="8150c-135">出力、**乗算**functoid への入力になります、**累積合計**functoid です。</span><span class="sxs-lookup"><span data-stu-id="8150c-135">The output of the **Multiplication** functoid becomes the input to the **Cumulative Sum** functoid.</span></span> <span data-ttu-id="8150c-136">出力、**累積合計**functoid は、累積された値として、**項目**入力注文書のレコードを走査します。</span><span class="sxs-lookup"><span data-stu-id="8150c-136">The output of the **Cumulative Sum** functoid is the accumulated value as the **Item** records are traversed in the input purchase order.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8150c-137">入力の累積集計は、入力リンクの発生元の親レコードに対して行われます。</span><span class="sxs-lookup"><span data-stu-id="8150c-137">The cumulative aggregation of input takes place over the parent record from which the input link originates.</span></span> <span data-ttu-id="8150c-138">場合でも、**累積**functoid が別の functoid から入力を取得、累積的な集計にわたって実行入力リンクの親レコードへの入力として機能する functoid を**累積**functoid です。</span><span class="sxs-lookup"><span data-stu-id="8150c-138">Even when the **Cumulative** functoid gets its input from another functoid, the cumulative aggregation takes place over the parent record of the input links to the functoid that serves as input to the **Cumulative** functoid.</span></span>  
  
 <span data-ttu-id="8150c-139">スコープ パラメーターを 1 (one) に変更し、出力スキーマに若干の変更を加えると、出力結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8150c-139">Changing the scoping parameter to 1 (one) and modifying the output schema slightly, yields output like the following:</span></span>  
  
```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <ItemTotal>1999.95</ItemTotal>  
    <ItemTotal>39.5</ItemTotal>  
</ns0:SummedPO>  
```  
  
 <span data-ttu-id="8150c-140">スコープ パラメーターを 1 (one) に設定すると、同じ親を持つ要素または属性の累積値が示されます。</span><span class="sxs-lookup"><span data-stu-id="8150c-140">Setting the scoping parameter to 1 (one) indicates accumulating values for elements or attributes with the same parent.</span></span> <span data-ttu-id="8150c-141">ここで、**価格**と**数量**フィールドである**項目**親として functoid ごとに値の合計を計算できるように**項目**です。</span><span class="sxs-lookup"><span data-stu-id="8150c-141">Here the **Price** and **Quantity** fields have **Item** as a parent so that the functoid sums values for each individual **Item**.</span></span>  
  
 <span data-ttu-id="8150c-142">スコープ パラメーターを 2 に設定すると、この Functoid は、同じ祖父を持つ要素または属性の値を累積します。</span><span class="sxs-lookup"><span data-stu-id="8150c-142">If the scoping parameter is 2, the functoid accumulates values for elements or attributes with the same grandparent.</span></span> <span data-ttu-id="8150c-143">親の親、**価格**と**数量**フィールドは、 **LineItems**レコード。</span><span class="sxs-lookup"><span data-stu-id="8150c-143">The grandparent of the **Price** and **Quantity** fields is the **LineItems** record.</span></span> <span data-ttu-id="8150c-144">1 つだけを使用する必要があるため**LineItems**インスタンス メッセージのレコードを結果と同じ既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="8150c-144">Because there is only one **LineItems** record in the instance message, the result is the same as using the default value:</span></span>  
  
```  
<ns0:SummedPO xmlns:ns0="http://CumulativeFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
</ns0:SummedPO>  
```  
  
> [!NOTE]
>  <span data-ttu-id="8150c-145">累積 functoid (を除き、**累積文字列**functoid) 数値以外の入力を無視します。</span><span class="sxs-lookup"><span data-stu-id="8150c-145">Cumulative functoids (except for the **Cumulative String** functoid) ignore non-numeric input.</span></span> <span data-ttu-id="8150c-146">たとえば、"three" という入力値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="8150c-146">For example, an input value of "three" is ignored.</span></span>  
  
 <span data-ttu-id="8150c-147">**累積平均**、**累積最小値**、および**累積最大値**functoid の動作と同じように、**累積合計**functoid です。</span><span class="sxs-lookup"><span data-stu-id="8150c-147">The **Cumulative Average**, **Cumulative Minimum**, and **Cumulative Maximum** functoids behave similarly to the **Cumulative Sum** functoid.</span></span> <span data-ttu-id="8150c-148">**累積文字列**数値を集計するのではなく、文字列を連結します。</span><span class="sxs-lookup"><span data-stu-id="8150c-148">The **Cumulative String** concatenates strings rather than aggregating numeric values.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="8150c-149">使用可能な functoid</span><span class="sxs-lookup"><span data-stu-id="8150c-149">Available functoids</span></span>
  
 <span data-ttu-id="8150c-150">**累積**functoid には。</span><span class="sxs-lookup"><span data-stu-id="8150c-150">The **Cumulative** functoids are:</span></span> 

* <span data-ttu-id="8150c-151">累積平均</span><span class="sxs-lookup"><span data-stu-id="8150c-151">Cumulative Average</span></span>
* <span data-ttu-id="8150c-152">累積連結</span><span class="sxs-lookup"><span data-stu-id="8150c-152">Cumulative Concatenate</span></span>
* <span data-ttu-id="8150c-153">累積最大値</span><span class="sxs-lookup"><span data-stu-id="8150c-153">Cumulative Maximum</span></span>
* <span data-ttu-id="8150c-154">累積最小値</span><span class="sxs-lookup"><span data-stu-id="8150c-154">Cumulative Minimum</span></span>
* <span data-ttu-id="8150c-155">累積合計</span><span class="sxs-lookup"><span data-stu-id="8150c-155">Cumulative Sum</span></span>

<span data-ttu-id="8150c-156">これらの functoid の詳細については、[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="8150c-156">More details on these functoids are [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8150c-157">参照</span><span class="sxs-lookup"><span data-stu-id="8150c-157">See Also</span></span>  
-  [<span data-ttu-id="8150c-158">マップに基本 Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="8150c-158">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
-  <span data-ttu-id="8150c-159">**累積 Functoid のリファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="8150c-159">**Cumulative Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>