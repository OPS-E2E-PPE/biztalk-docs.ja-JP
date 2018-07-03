---
title: '手順 2: Price and Availability プロジェクト、BizTalk エディターを使用して Contoso LOB アプリケーション スキーマの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOB schemas
ms.assetid: 70e26dc9-4299-4d30-8f8b-5cc3469a2025
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f899a6614ea5d5d28c555be1b39e72b5880fe3ae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999331"
---
# <a name="step-2-creating-the-contoso-lob-application-schemas-for-the-price-and-availability-project-using-biztalk-editor"></a><span data-ttu-id="187f8-102">手順 2: Price and Availability プロジェクトを BizTalk エディターを使用して用の Contoso LOB アプリケーション スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="187f8-102">Step 2: Creating the Contoso LOB Application Schemas for the Price and Availability Project Using BizTalk Editor</span></span>
<span data-ttu-id="187f8-103">ここでは、特定の製品の価格やその製品が入手可能かどうかを Contoso ERP システムに照会する際に使用するスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="187f8-103">In this step, you generate the schema to use to query the Contoso ERP system for the price and availability of a particular product.</span></span> <span data-ttu-id="187f8-104">このスキーマを生成するには、BizTalk Server 用 Microsoft® SQL アダプタを使用します。</span><span class="sxs-lookup"><span data-stu-id="187f8-104">You generate this schema by using the Microsoft® SQL Adapter for BizTalk Server.</span></span>  

### <a name="to-update-the-sql-stored-procedure-for-schema-generation"></a><span data-ttu-id="187f8-105">スキーマを生成するために SQL ストアド プロシージャを更新するには</span><span class="sxs-lookup"><span data-stu-id="187f8-105">To update the SQL stored procedure for schema generation</span></span>  

1.  <span data-ttu-id="187f8-106">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="187f8-106">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  

2.  <span data-ttu-id="187f8-107">Microsoft SQL Server Management Studio で展開**データベース**、展開**Contoso**、展開**プログラミング**、順に展開**ストアド プロシージャ**.</span><span class="sxs-lookup"><span data-stu-id="187f8-107">In the Microsoft SQL Server Management Studio, expand **Databases**, expand **Contoso**, expand **Programmability**, and then expand **Stored Procedures**.</span></span>  

3.  <span data-ttu-id="187f8-108">右クリックして**dbo します。SP_GetInventoryForProductID**、 をクリックし、**変更**します。</span><span class="sxs-lookup"><span data-stu-id="187f8-108">Right-click **dbo.SP_GetInventoryForProductID**, and then click **Modify**.</span></span>  

4.  <span data-ttu-id="187f8-109">クエリ ウィンドウで、"for xml auto" の直後にコンマとスペースを挿入し、その後に「xmldata」と入力します。</span><span class="sxs-lookup"><span data-stu-id="187f8-109">In the query window, insert a comma, a space, and then "xmldata" immediately following "for xml auto".</span></span> <span data-ttu-id="187f8-110">次のコード行があります。</span><span class="sxs-lookup"><span data-stu-id="187f8-110">The line of code should be the following:</span></span>  

    ```  
    for xml auto, xmldata  
    ```  

5.  <span data-ttu-id="187f8-111">クリックして**Execute**ストアド プロシージャに変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="187f8-111">Click **Execute** to save the changes to the stored procedure.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="187f8-112">次の手順で使用するため、Microsoft SQL Server Management Studio は開いたままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="187f8-112">Leave the Microsoft SQL Server Management Studio open for the next procedure.</span></span>  

### <a name="to-create-the-contoso-price-and-availability-schema"></a><span data-ttu-id="187f8-113">ContosoPriceAndAvailability スキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="187f8-113">To create the Contoso Price and Availability schema</span></span>  

1. <span data-ttu-id="187f8-114">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] で Contoso ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="187f8-114">Open the Contoso solution in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  

2. <span data-ttu-id="187f8-115">ソリューション エクスプ ローラーで右クリックし、 **contosopriceandavailability**プロジェクトをポイントして、**追加**、 をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="187f8-115">In Solution Explorer, right-click the **ContosoPriceAndAvailability** project, point to **Add**, and then click **Add Generated Items**.</span></span>  

3. <span data-ttu-id="187f8-116">生成しておきの追加 ダイアログ ボックスで**アダプター メタデータの追加**左側のウィンドウで選択されていること、**アダプター メタデータの追加**で右側のウィンドウをクリック**追加**します。</span><span class="sxs-lookup"><span data-stu-id="187f8-116">In the Add Generated Iems dialog box, with **Add Adapter Metadata** selected in the left pane, click **Add Adapter Metadata** in the right pane, and then click **Add**.</span></span>  

4. <span data-ttu-id="187f8-117">**アダプターの追加ウィザード**] ページで、[ **SQL**クリックして、登録済みアダプターの一覧から**次**します。</span><span class="sxs-lookup"><span data-stu-id="187f8-117">On the **Add Adapter Wizard** page, select **SQL** from the list of registered adapters, and then click **Next**.</span></span>  

5. <span data-ttu-id="187f8-118">**データベース情報**] ページで [**設定**します。</span><span class="sxs-lookup"><span data-stu-id="187f8-118">On the **Database Information** page, click **Set**.</span></span>  

6. <span data-ttu-id="187f8-119">データ リンク プロパティ ダイアログ ボックスでの**を選択するか、サーバー名を入力**ボックスに「 **localhost**します。</span><span class="sxs-lookup"><span data-stu-id="187f8-119">In the Data Link Properties dialog box, in the **Select or enter a server name** box, type **localhost**.</span></span> <span data-ttu-id="187f8-120">選択**使用して Windows NT 統合セキュリティ**します。</span><span class="sxs-lookup"><span data-stu-id="187f8-120">Select **Use Windows NT Integrated security**.</span></span> <span data-ttu-id="187f8-121">**サーバー上のデータベースを選択します。** を選択、 **Contoso**データベースの一覧からデータベース。</span><span class="sxs-lookup"><span data-stu-id="187f8-121">For **Select the database on the server**, select the **Contoso** database from the database list.</span></span> <span data-ttu-id="187f8-122">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="187f8-122">Click **OK**.</span></span>  

7. <span data-ttu-id="187f8-123">**データベース情報**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="187f8-123">On the **Database Information** page, click **Next**.</span></span>  

8. <span data-ttu-id="187f8-124">**スキーマ情報**ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="187f8-124">On the **Schema Information** page, do the following:</span></span>  


   |                <span data-ttu-id="187f8-125">プロパティ</span><span class="sxs-lookup"><span data-stu-id="187f8-125">Use this</span></span>                 |              <span data-ttu-id="187f8-126">目的</span><span class="sxs-lookup"><span data-stu-id="187f8-126">To do this</span></span>              |
   |-----------------------------------------|--------------------------------------|
   |          <span data-ttu-id="187f8-127">**ターゲットの名前空間**</span><span class="sxs-lookup"><span data-stu-id="187f8-127">**Target namespace**</span></span>           | <span data-ttu-id="187f8-128">型 **<http://Contoso.com/Price>** します。</span><span class="sxs-lookup"><span data-stu-id="187f8-128">Type **<http://Contoso.com/Price>**.</span></span> |
   |        <span data-ttu-id="187f8-129">**ポートの種類を選択します。**</span><span class="sxs-lookup"><span data-stu-id="187f8-129">**Select the port type**</span></span>         |        <span data-ttu-id="187f8-130">選択**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="187f8-130">Select **Send port**.</span></span>         |
   | <span data-ttu-id="187f8-131">**要求ドキュメントのルート要素名**</span><span class="sxs-lookup"><span data-stu-id="187f8-131">**Request document root element name**</span></span>  |      <span data-ttu-id="187f8-132">型 **[rootpricerequest]** します。</span><span class="sxs-lookup"><span data-stu-id="187f8-132">Type **rootPriceRequest**.</span></span>      |
   | <span data-ttu-id="187f8-133">**応答ドキュメントのルート要素名**</span><span class="sxs-lookup"><span data-stu-id="187f8-133">**Response document root element name**</span></span> |     <span data-ttu-id="187f8-134">型**rootPriceResponse**します。</span><span class="sxs-lookup"><span data-stu-id="187f8-134">Type **rootPriceResponse**.</span></span>      |


9. <span data-ttu-id="187f8-135">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="187f8-135">Click **Next**.</span></span>  

10. <span data-ttu-id="187f8-136">**ステートメントの種類の情報**] ページで、[**ストアド プロシージャの**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="187f8-136">On the **Statement type information** page, select **Stored Procedure**, and then click **Next**.</span></span>  

11. <span data-ttu-id="187f8-137">**ステートメント情報** ページの**\<ストアド プロシージャを選択\>** を選択します**SP_GetInventoryForProductID**から、ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="187f8-137">On the **Statement Information** page, for **\<Select a stored procedure\>**, select **SP_GetInventoryForProductID** from the drop-down list.</span></span> <span data-ttu-id="187f8-138">クリックして**生成**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="187f8-138">Click **Generate**, and then click **Next**.</span></span>  

12. <span data-ttu-id="187f8-139">**SQL トランスポート スキーマ生成ウィザードの完了**] ページで [**完了**ContosoPriceAndAvailability BizTalk プロジェクトにスキーマをインポートします。</span><span class="sxs-lookup"><span data-stu-id="187f8-139">On the **Completing the SQL Transport Schema Generation Wizard** page, click **Finish** to import the schema into the ContosoPriceAndAvailability BizTalk project.</span></span>  

13. <span data-ttu-id="187f8-140">ソリューション エクスプ ローラーで、生成されたスキーマ (SQLService_Price.xsd) を右クリックして**の名前を変更**、および種類**ContosoPriceAndAvailability.xsd**スキーマの新しい名前として。</span><span class="sxs-lookup"><span data-stu-id="187f8-140">In Solution Explorer, right-click the generated schema (SQLService_Price.xsd), click **Rename**, and type **ContosoPriceAndAvailability.xsd** as the new name for the schema.</span></span> <span data-ttu-id="187f8-141">**Enter**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="187f8-141">Click **Enter**.</span></span>  

14. <span data-ttu-id="187f8-142">ContosoPriceAndAvailability スキーマの [プロパティ] ウィンドウで、**型名**プロパティを**ContosoPriceSchema**します。</span><span class="sxs-lookup"><span data-stu-id="187f8-142">In the Properties window for the ContosoPriceAndAvailability schema, set the **Type Name** property to **ContosoPriceSchema**.</span></span>  

15. <span data-ttu-id="187f8-143">既定では、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]という名前の BizTalk オーケストレーションを作成します。 **BizTalk Orchestration.odx**します。</span><span class="sxs-lookup"><span data-stu-id="187f8-143">By default, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] creates a BizTalk orchestration named **BizTalk Orchestration.odx**.</span></span> <span data-ttu-id="187f8-144">このオーケストレーションを右クリックし、**削除**このオーケストレーションを必要としないためです。</span><span class="sxs-lookup"><span data-stu-id="187f8-144">Right-click this orchestration, and then click **Delete** because you do not need this orchestration.</span></span> <span data-ttu-id="187f8-145">オーケストレーションが完全に削除されることを示すポップアップで、次のようにクリックします。 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="187f8-145">In the popup indicating that the orchestration will be deleted permanently, click **OK**.</span></span>  

16. <span data-ttu-id="187f8-146">Microsoft SQL Server Management Studio では、削除、`xmldata`述語とコンマから、`SP_GetInventoryForProductID`クリックして、ストアド プロシージャを前の手順で追加した**Execute**。</span><span class="sxs-lookup"><span data-stu-id="187f8-146">In the Microsoft SQL Server Management Studio, remove the `xmldata` predicate and the comma from the `SP_GetInventoryForProductID` stored procedure that you added in the previous step, and then click **Execute**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="187f8-147">参照</span><span class="sxs-lookup"><span data-stu-id="187f8-147">See Also</span></span>  
 [<span data-ttu-id="187f8-148">手順 3: BizTalk マッパーを使用した Price and Availability プロジェクト用の Contoso LOB アプリケーション マップの作成</span><span class="sxs-lookup"><span data-stu-id="187f8-148">Step 3: Creating the Contoso LOB Application Maps for the Price and Availability Project Using BizTalk Mapper</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-create-contoso-lob-application-map-for-price-and-availability-in-mapper.md)