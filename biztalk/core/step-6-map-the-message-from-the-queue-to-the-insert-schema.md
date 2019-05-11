---
title: 手順 6 (オンプレミス):キューから Insert スキーマにメッセージをマップする変換を作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30a55f1e-32cc-409a-a814-084026f51b35
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 382d408e1fdacbbdc6efe151eb7cf53286d497e8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244294"
---
# <a name="step-6-on-premises-create-a-transform-to-map-the-message-from-the-queue-to-the-insert-schema"></a><span data-ttu-id="ee006-102">手順 6 (オンプレミス):キューから Insert スキーマにメッセージをマップする変換を作成します。</span><span class="sxs-lookup"><span data-stu-id="ee006-102">Step 6 (On Premises): Create a Transform to Map the Message from the Queue to the Insert Schema</span></span>
<span data-ttu-id="ee006-103">受信されるメッセージ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、Service Bus キューからになります、 **ECommerceSalesOrder.xsd**スキーマ。</span><span class="sxs-lookup"><span data-stu-id="ee006-103">The message that is received by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] from the Service Bus Queue will be of the **ECommerceSalesOrder.xsd** schema.</span></span> <span data-ttu-id="ee006-104">ただしにメッセージを挿入する、 **SalesOrder**テーブルのメッセージがある必要があります**挿入**で生成したスキーマ[手順 5 (オンプレミス)。メッセージする SalesOrder テーブルを挿入するためのスキーマを生成](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md)します。</span><span class="sxs-lookup"><span data-stu-id="ee006-104">However, to insert a message into the **SalesOrder** table, the message must be of **Insert** schema that you generated in [Step 5 (On Premises): Generate the Schema for Inserting a Message inito SalesOrder Table](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md).</span></span> <span data-ttu-id="ee006-105">変換するマップを作成このトピックで、 **ECommerceSalesOrder.xsd** Insert 操作スキーマにスキーマ。</span><span class="sxs-lookup"><span data-stu-id="ee006-105">So, in this topic, we create a map to transform the **ECommerceSalesOrder.xsd** schema into the Insert operation schema.</span></span>  

### <a name="to-create-a-map"></a><span data-ttu-id="ee006-106">マップを作成するには</span><span class="sxs-lookup"><span data-stu-id="ee006-106">To create a map</span></span>  

1. <span data-ttu-id="ee006-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトを右クリックをポイントして、既に作成した、**追加**、順にクリックします**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="ee006-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] you already created, right-click the project, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="ee006-108">**新しい項目の**ダイアログ ボックスで、**マップ**、マップ名として入力`SalesOrder_SQL.btm`、順にクリックします**追加**。</span><span class="sxs-lookup"><span data-stu-id="ee006-108">In the **New Item** dialog box, select **Map**, enter the map name as `SalesOrder_SQL.btm`, and then click **Add**.</span></span>  

2. <span data-ttu-id="ee006-109">送信元スキーマ、マップで選択**ECommerceSalesOrder.xsd**します。</span><span class="sxs-lookup"><span data-stu-id="ee006-109">In the map, for the source schema, select **ECommerceSalesOrder.xsd**.</span></span> <span data-ttu-id="ee006-110">送信先スキーマでは、選択**TableOperations.SalesOrder.xsd (Insert)** スキーマ。</span><span class="sxs-lookup"><span data-stu-id="ee006-110">For the destination schema, select **TableOperations.SalesOrder.xsd (Insert)** schema.</span></span>  

3. <span data-ttu-id="ee006-111">元と送信先スキーマの次のノードを直接マップするには。</span><span class="sxs-lookup"><span data-stu-id="ee006-111">Directly map the following nodes in the source and destination schemas:</span></span>  


   | <span data-ttu-id="ee006-112">送信元スキーマ</span><span class="sxs-lookup"><span data-stu-id="ee006-112">Source Schema</span></span> | <span data-ttu-id="ee006-113">送信先スキーマ</span><span class="sxs-lookup"><span data-stu-id="ee006-113">Destination Schema</span></span> |
   |---------------|--------------------|
   |  <span data-ttu-id="ee006-114">CompanyCode</span><span class="sxs-lookup"><span data-stu-id="ee006-114">CompanyCode</span></span>  |    <span data-ttu-id="ee006-115">CompanyCode</span><span class="sxs-lookup"><span data-stu-id="ee006-115">CompanyCode</span></span>     |
   |    <span data-ttu-id="ee006-116">PartId</span><span class="sxs-lookup"><span data-stu-id="ee006-116">PartId</span></span>     |      <span data-ttu-id="ee006-117">PartNum</span><span class="sxs-lookup"><span data-stu-id="ee006-117">PartNum</span></span>       |
   |   <span data-ttu-id="ee006-118">Quantity</span><span class="sxs-lookup"><span data-stu-id="ee006-118">Quantity</span></span>    |        <span data-ttu-id="ee006-119">Qty</span><span class="sxs-lookup"><span data-stu-id="ee006-119">Qty</span></span>         |
   |   <span data-ttu-id="ee006-120">AskPrice</span><span class="sxs-lookup"><span data-stu-id="ee006-120">AskPrice</span></span>    |    <span data-ttu-id="ee006-121">UnitAskPrice</span><span class="sxs-lookup"><span data-stu-id="ee006-121">UnitAskPrice</span></span>    |
   |   <span data-ttu-id="ee006-122">コメント</span><span class="sxs-lookup"><span data-stu-id="ee006-122">Comments</span></span>    |  <span data-ttu-id="ee006-123">CustomerComments</span><span class="sxs-lookup"><span data-stu-id="ee006-123">CustomerComments</span></span>  |


4. <span data-ttu-id="ee006-124">使用して、**日付と時刻**に値をマップの functoid、 **DateRequested**と**ShipDate**送信先スキーマ内の要素。</span><span class="sxs-lookup"><span data-stu-id="ee006-124">Use the **Date and Time** functoid to map values to the **DateRequested** and **ShipDate** elements in the destination schema.</span></span> <span data-ttu-id="ee006-125">これらのノードは、送信元スキーマ内の各ノードにマップされていません。</span><span class="sxs-lookup"><span data-stu-id="ee006-125">These nodes are not mapped to the respective nodes in the source schema.</span></span> <span data-ttu-id="ee006-126">代わりに、現在の日付と時刻に渡されますが、これらのノードを使用して、**日付と時刻**functoid。</span><span class="sxs-lookup"><span data-stu-id="ee006-126">Instead, the current date and time is passed on to these nodes by using the **Date and Time** functoid.</span></span>  

   1.  <span data-ttu-id="ee006-127">ドラッグ アンド ドロップ、**日付と時刻**マッパー画面にツールボックスから functoid。</span><span class="sxs-lookup"><span data-stu-id="ee006-127">Drag and drop a **Date and Time** functoid from toolbox to the mapper surface.</span></span>  

   2.  <span data-ttu-id="ee006-128">Functoid を接続、 **DateRequested**送信先スキーマ内の要素。</span><span class="sxs-lookup"><span data-stu-id="ee006-128">Connect the functoid to the **DateRequested** element in the destination schema.</span></span>  

   3.  <span data-ttu-id="ee006-129">ドラッグ アンド ドロップ別**日付と時刻**functoid に接続し、 **ShipDate**送信先スキーマ内の要素。</span><span class="sxs-lookup"><span data-stu-id="ee006-129">Drag and drop another **Date and Time** functoid and connect it to the **ShipDate** element in the destination schema.</span></span>  

5. <span data-ttu-id="ee006-130">次のノードを使用して元と送信先スキーマでマップを**文字列連結**functoid:</span><span class="sxs-lookup"><span data-stu-id="ee006-130">Map the following nodes in the source and destination schemas using a **String Concatenate** functoid:</span></span>  

   |<span data-ttu-id="ee006-131">送信元スキーマ</span><span class="sxs-lookup"><span data-stu-id="ee006-131">Source Schema</span></span>|<span data-ttu-id="ee006-132">送信先スキーマ</span><span class="sxs-lookup"><span data-stu-id="ee006-132">Destination Schema</span></span>|  
   |-------------------|------------------------|  
   |<span data-ttu-id="ee006-133">Address\Line1</span><span class="sxs-lookup"><span data-stu-id="ee006-133">Address\Line1</span></span>|<span data-ttu-id="ee006-134">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="ee006-134">SellToAddress</span></span><br /><br /> <span data-ttu-id="ee006-135">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="ee006-135">BillToAddress</span></span>|  
   |<span data-ttu-id="ee006-136">Address\Line2</span><span class="sxs-lookup"><span data-stu-id="ee006-136">Address\Line2</span></span>|<span data-ttu-id="ee006-137">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="ee006-137">SellToAddress</span></span><br /><br /> <span data-ttu-id="ee006-138">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="ee006-138">BillToAddress</span></span>|  
   |<span data-ttu-id="ee006-139">Address\City</span><span class="sxs-lookup"><span data-stu-id="ee006-139">Address\City</span></span>|<span data-ttu-id="ee006-140">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="ee006-140">SellToAddress</span></span><br /><br /> <span data-ttu-id="ee006-141">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="ee006-141">BillToAddress</span></span>|  
   |<span data-ttu-id="ee006-142">Address\State</span><span class="sxs-lookup"><span data-stu-id="ee006-142">Address\State</span></span>|<span data-ttu-id="ee006-143">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="ee006-143">SellToAddress</span></span><br /><br /> <span data-ttu-id="ee006-144">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="ee006-144">BillToAddress</span></span>|  
   |<span data-ttu-id="ee006-145">Address\Country</span><span class="sxs-lookup"><span data-stu-id="ee006-145">Address\Country</span></span>|<span data-ttu-id="ee006-146">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="ee006-146">SellToAddress</span></span><br /><br /> <span data-ttu-id="ee006-147">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="ee006-147">BillToAddress</span></span>|  
   |<span data-ttu-id="ee006-148">Address\ZipCode</span><span class="sxs-lookup"><span data-stu-id="ee006-148">Address\ZipCode</span></span>|<span data-ttu-id="ee006-149">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="ee006-149">SellToAddress</span></span><br /><br /> <span data-ttu-id="ee006-150">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="ee006-150">BillToAddress</span></span>|  
   |<span data-ttu-id="ee006-151">Contact\FirstName</span><span class="sxs-lookup"><span data-stu-id="ee006-151">Contact\FirstName</span></span>|<span data-ttu-id="ee006-152">PartnerContact</span><span class="sxs-lookup"><span data-stu-id="ee006-152">PartnerContact</span></span>|  
   |<span data-ttu-id="ee006-153">Contact\LastName</span><span class="sxs-lookup"><span data-stu-id="ee006-153">Contact\LastName</span></span>||  

    <span data-ttu-id="ee006-154">文字列の連結マッピング セットごとに、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ee006-154">Perform the following steps for each of the string concatenation mapping sets:</span></span>  

   1.  <span data-ttu-id="ee006-155">ドラッグ アンド ドロップ、**文字列連結**マッパー画面にツールボックスから functoid。</span><span class="sxs-lookup"><span data-stu-id="ee006-155">Drag and drop a **String Concatenate** functoid from toolbox to the mapper surface.</span></span>  

   2.  <span data-ttu-id="ee006-156">入力としてソース ツリーから各要素を追加、**文字列連結**functoid。</span><span class="sxs-lookup"><span data-stu-id="ee006-156">Add each element from the source tree as an input to the **String Concatenate** functoid.</span></span>  

   3.  <span data-ttu-id="ee006-157">ドラッグ アンドの出力を構成、**文字列連結**functoid を送信先スキーマ内の要素。</span><span class="sxs-lookup"><span data-stu-id="ee006-157">Drag and configure the output of the **String Concatenate** functoid to the element in the destination schema.</span></span>  

        <span data-ttu-id="ee006-158">完成したマップには、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ee006-158">The completed map resembles the following:</span></span>  

        <span data-ttu-id="ee006-159">![スキーマを変換するマップ](../core/media/bts2010r2-tut1-map.jpg "BTS2010R2_Tut1_Map")</span><span class="sxs-lookup"><span data-stu-id="ee006-159">![Map to transform schemas](../core/media/bts2010r2-tut1-map.jpg "BTS2010R2_Tut1_Map")</span></span>  

## <a name="see-also"></a><span data-ttu-id="ee006-160">参照</span><span class="sxs-lookup"><span data-stu-id="ee006-160">See Also</span></span>  
 [<span data-ttu-id="ee006-161">チュートリアル 4: BizTalk Server 2013 を使用してハイブリッド アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ee006-161">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)