---
title: "手順 6 (社内): 作成、キューから Insert スキーマへのメッセージをマップする変換 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30a55f1e-32cc-409a-a814-084026f51b35
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02b2be9659714beb4b9a52f4c2a9dd1e5b3ea47f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-on-premises-create-a-transform-to-map-the-message-from-the-queue-to-the-insert-schema"></a><span data-ttu-id="cafcf-102">手順 6 (社内): キューから Insert スキーマへのメッセージをマップする変換を作成します。</span><span class="sxs-lookup"><span data-stu-id="cafcf-102">Step 6 (On Premises): Create a Transform to Map the Message from the Queue to the Insert Schema</span></span>
<span data-ttu-id="cafcf-103">によって受信されるメッセージ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Service Bus キューからでは、 **ECommerceSalesOrder.xsd**スキーマです。</span><span class="sxs-lookup"><span data-stu-id="cafcf-103">The message that is received by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] from the Service Bus Queue will be of the **ECommerceSalesOrder.xsd** schema.</span></span> <span data-ttu-id="cafcf-104">ただしにメッセージを挿入する、 **SalesOrder**テーブルでのメッセージがある必要があります**挿入**で生成したスキーマ[手順 5 (オンプレミス): にメッセージを挿入するためのスキーマの生成SalesOrder テーブル](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md)です。</span><span class="sxs-lookup"><span data-stu-id="cafcf-104">However, to insert a message into the **SalesOrder** table, the message must be of **Insert** schema that you generated in [Step 5 (On Premises): Generate the Schema for Inserting a Message inito SalesOrder Table](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md).</span></span> <span data-ttu-id="cafcf-105">そのため、このトピックでは作成を変換するマップ、 **ECommerceSalesOrder.xsd** Insert 操作スキーマにスキーマです。</span><span class="sxs-lookup"><span data-stu-id="cafcf-105">So, in this topic, we create a map to transform the **ECommerceSalesOrder.xsd** schema into the Insert operation schema.</span></span>  
  
### <a name="to-create-a-map"></a><span data-ttu-id="cafcf-106">マップを作成するには</span><span class="sxs-lookup"><span data-stu-id="cafcf-106">To create a map</span></span>  
  
1.  <span data-ttu-id="cafcf-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をポイントし、プロジェクトを右クリックし、作成されると、既に**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="cafcf-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] you already created, right-click the project, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="cafcf-108">**新しい項目の**ダイアログ ボックスで、**マップ**、マップ名を入力`SalesOrder_SQL.btm`、順にクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="cafcf-108">In the **New Item** dialog box, select **Map**, enter the map name as `SalesOrder_SQL.btm`, and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="cafcf-109">マップでは、送信元スキーマの選択**ECommerceSalesOrder.xsd**です。</span><span class="sxs-lookup"><span data-stu-id="cafcf-109">In the map, for the source schema, select **ECommerceSalesOrder.xsd**.</span></span> <span data-ttu-id="cafcf-110">送信先スキーマの選択**TableOperations.SalesOrder.xsd (Insert)**スキーマです。</span><span class="sxs-lookup"><span data-stu-id="cafcf-110">For the destination schema, select **TableOperations.SalesOrder.xsd (Insert)** schema.</span></span>  
  
3.  <span data-ttu-id="cafcf-111">送信元スキーマと送信先スキーマで次のノードを直接マップします。</span><span class="sxs-lookup"><span data-stu-id="cafcf-111">Directly map the following nodes in the source and destination schemas:</span></span>  
  
    |<span data-ttu-id="cafcf-112">送信元スキーマ</span><span class="sxs-lookup"><span data-stu-id="cafcf-112">Source Schema</span></span>|<span data-ttu-id="cafcf-113">送信先スキーマ</span><span class="sxs-lookup"><span data-stu-id="cafcf-113">Destination Schema</span></span>|  
    |-------------------|------------------------|  
    |<span data-ttu-id="cafcf-114">CompanyCode</span><span class="sxs-lookup"><span data-stu-id="cafcf-114">CompanyCode</span></span>|<span data-ttu-id="cafcf-115">CompanyCode</span><span class="sxs-lookup"><span data-stu-id="cafcf-115">CompanyCode</span></span>|  
    |<span data-ttu-id="cafcf-116">PartId</span><span class="sxs-lookup"><span data-stu-id="cafcf-116">PartId</span></span>|<span data-ttu-id="cafcf-117">PartNum</span><span class="sxs-lookup"><span data-stu-id="cafcf-117">PartNum</span></span>|  
    |<span data-ttu-id="cafcf-118">Quantity</span><span class="sxs-lookup"><span data-stu-id="cafcf-118">Quantity</span></span>|<span data-ttu-id="cafcf-119">Qty</span><span class="sxs-lookup"><span data-stu-id="cafcf-119">Qty</span></span>|  
    |<span data-ttu-id="cafcf-120">AskPrice</span><span class="sxs-lookup"><span data-stu-id="cafcf-120">AskPrice</span></span>|<span data-ttu-id="cafcf-121">UnitAskPrice</span><span class="sxs-lookup"><span data-stu-id="cafcf-121">UnitAskPrice</span></span>|  
    |<span data-ttu-id="cafcf-122">コメント</span><span class="sxs-lookup"><span data-stu-id="cafcf-122">Comments</span></span>|<span data-ttu-id="cafcf-123">CustomerComments</span><span class="sxs-lookup"><span data-stu-id="cafcf-123">CustomerComments</span></span>|  
  
4.  <span data-ttu-id="cafcf-124">使用して、**日付と時刻**に値をマップする functoid、 **DateRequested**と**ShipDate**送信先スキーマ内の要素。</span><span class="sxs-lookup"><span data-stu-id="cafcf-124">Use the **Date and Time** functoid to map values to the **DateRequested** and **ShipDate** elements in the destination schema.</span></span> <span data-ttu-id="cafcf-125">これらのノードは送信元スキーマの各ノードにマップされません。</span><span class="sxs-lookup"><span data-stu-id="cafcf-125">These nodes are not mapped to the respective nodes in the source schema.</span></span> <span data-ttu-id="cafcf-126">代わりに、現在の日付と時刻に渡されるでこれらのノードを使用して、**日付と時刻**functoid です。</span><span class="sxs-lookup"><span data-stu-id="cafcf-126">Instead, the current date and time is passed on to these nodes by using the **Date and Time** functoid.</span></span>  
  
    1.  <span data-ttu-id="cafcf-127">ドラッグ アンド ドロップ、**日付と時刻**マッパー画面にツールボックスから functoid です。</span><span class="sxs-lookup"><span data-stu-id="cafcf-127">Drag and drop a **Date and Time** functoid from toolbox to the mapper surface.</span></span>  
  
    2.  <span data-ttu-id="cafcf-128">Functoid への接続、 **DateRequested**送信先スキーマ内の要素。</span><span class="sxs-lookup"><span data-stu-id="cafcf-128">Connect the functoid to the **DateRequested** element in the destination schema.</span></span>  
  
    3.  <span data-ttu-id="cafcf-129">ドラッグ アンド ドロップ別**日付と時刻**functoid に接続するには**ShipDate**送信先スキーマ内の要素。</span><span class="sxs-lookup"><span data-stu-id="cafcf-129">Drag and drop another **Date and Time** functoid and connect it to the **ShipDate** element in the destination schema.</span></span>  
  
5.  <span data-ttu-id="cafcf-130">次のノードを使用して、送信元と送信先スキーマのマップ、**文字列連結**functoid:</span><span class="sxs-lookup"><span data-stu-id="cafcf-130">Map the following nodes in the source and destination schemas using a **String Concatenate** functoid:</span></span>  
  
    |<span data-ttu-id="cafcf-131">送信元スキーマ</span><span class="sxs-lookup"><span data-stu-id="cafcf-131">Source Schema</span></span>|<span data-ttu-id="cafcf-132">送信先スキーマ</span><span class="sxs-lookup"><span data-stu-id="cafcf-132">Destination Schema</span></span>|  
    |-------------------|------------------------|  
    |<span data-ttu-id="cafcf-133">Address\Line1</span><span class="sxs-lookup"><span data-stu-id="cafcf-133">Address\Line1</span></span>|<span data-ttu-id="cafcf-134">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="cafcf-134">SellToAddress</span></span><br /><br /> <span data-ttu-id="cafcf-135">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="cafcf-135">BillToAddress</span></span>|  
    |<span data-ttu-id="cafcf-136">Address\Line2</span><span class="sxs-lookup"><span data-stu-id="cafcf-136">Address\Line2</span></span>|<span data-ttu-id="cafcf-137">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="cafcf-137">SellToAddress</span></span><br /><br /> <span data-ttu-id="cafcf-138">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="cafcf-138">BillToAddress</span></span>|  
    |<span data-ttu-id="cafcf-139">Address\City</span><span class="sxs-lookup"><span data-stu-id="cafcf-139">Address\City</span></span>|<span data-ttu-id="cafcf-140">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="cafcf-140">SellToAddress</span></span><br /><br /> <span data-ttu-id="cafcf-141">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="cafcf-141">BillToAddress</span></span>|  
    |<span data-ttu-id="cafcf-142">Address\State</span><span class="sxs-lookup"><span data-stu-id="cafcf-142">Address\State</span></span>|<span data-ttu-id="cafcf-143">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="cafcf-143">SellToAddress</span></span><br /><br /> <span data-ttu-id="cafcf-144">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="cafcf-144">BillToAddress</span></span>|  
    |<span data-ttu-id="cafcf-145">Address\Country</span><span class="sxs-lookup"><span data-stu-id="cafcf-145">Address\Country</span></span>|<span data-ttu-id="cafcf-146">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="cafcf-146">SellToAddress</span></span><br /><br /> <span data-ttu-id="cafcf-147">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="cafcf-147">BillToAddress</span></span>|  
    |<span data-ttu-id="cafcf-148">Address\ZipCode</span><span class="sxs-lookup"><span data-stu-id="cafcf-148">Address\ZipCode</span></span>|<span data-ttu-id="cafcf-149">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="cafcf-149">SellToAddress</span></span><br /><br /> <span data-ttu-id="cafcf-150">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="cafcf-150">BillToAddress</span></span>|  
    |<span data-ttu-id="cafcf-151">Contact\FirstName</span><span class="sxs-lookup"><span data-stu-id="cafcf-151">Contact\FirstName</span></span>|<span data-ttu-id="cafcf-152">PartnerContact</span><span class="sxs-lookup"><span data-stu-id="cafcf-152">PartnerContact</span></span>|  
    |<span data-ttu-id="cafcf-153">Contact\LastName</span><span class="sxs-lookup"><span data-stu-id="cafcf-153">Contact\LastName</span></span>||  
  
     <span data-ttu-id="cafcf-154">文字列連結マッピング セットごとに、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cafcf-154">Perform the following steps for each of the string concatenation mapping sets:</span></span>  
  
    1.  <span data-ttu-id="cafcf-155">ドラッグ アンド ドロップ、**文字列連結**マッパー画面にツールボックスから functoid です。</span><span class="sxs-lookup"><span data-stu-id="cafcf-155">Drag and drop a **String Concatenate** functoid from toolbox to the mapper surface.</span></span>  
  
    2.  <span data-ttu-id="cafcf-156">入力としてソース ツリーから各要素を追加、**文字列連結**functoid です。</span><span class="sxs-lookup"><span data-stu-id="cafcf-156">Add each element from the source tree as an input to the **String Concatenate** functoid.</span></span>  
  
    3.  <span data-ttu-id="cafcf-157">ドラッグ アンドの出力を構成、**文字列連結**functoid を送信先スキーマ内の要素。</span><span class="sxs-lookup"><span data-stu-id="cafcf-157">Drag and configure the output of the **String Concatenate** functoid to the element in the destination schema.</span></span>  
  
         <span data-ttu-id="cafcf-158">完成したマップは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="cafcf-158">The completed map resembles the following:</span></span>  
  
         <span data-ttu-id="cafcf-159">![スキーマを変換するマップ](../core/media/bts2010r2-tut1-map.jpg "BTS2010R2_Tut1_Map")</span><span class="sxs-lookup"><span data-stu-id="cafcf-159">![Map to transform schemas](../core/media/bts2010r2-tut1-map.jpg "BTS2010R2_Tut1_Map")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cafcf-160">参照</span><span class="sxs-lookup"><span data-stu-id="cafcf-160">See Also</span></span>  
 [<span data-ttu-id="cafcf-161">チュートリアル 4: BizTalk Server 2013 を使用するハイブリッド アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="cafcf-161">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)