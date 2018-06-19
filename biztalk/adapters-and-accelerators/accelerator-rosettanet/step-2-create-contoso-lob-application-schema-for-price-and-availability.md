---
title: '手順 2: Price and Availability プロジェクトの BizTalk エディターを使用しての Contoso LOB アプリケーション スキーマの作成 |Microsoft ドキュメント'
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
ms.openlocfilehash: 441bb90c8fa0f2edb271af384e2540a741150137
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005763"
---
# <a name="step-2-creating-the-contoso-lob-application-schemas-for-the-price-and-availability-project-using-biztalk-editor"></a><span data-ttu-id="d943d-102">手順 2: Price and Availability プロジェクトの BizTalk エディターを使用して用の Contoso LOB アプリケーション スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="d943d-102">Step 2: Creating the Contoso LOB Application Schemas for the Price and Availability Project Using BizTalk Editor</span></span>
<span data-ttu-id="d943d-103">ここでは、特定の製品の価格やその製品が入手可能かどうかを Contoso ERP システムに照会する際に使用するスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="d943d-103">In this step, you generate the schema to use to query the Contoso ERP system for the price and availability of a particular product.</span></span> <span data-ttu-id="d943d-104">使用してこのスキーマを生成する、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® BizTalk Server の SQL アダプターです。</span><span class="sxs-lookup"><span data-stu-id="d943d-104">You generate this schema by using the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® SQL Adapter for BizTalk Server.</span></span>  
  
### <a name="to-update-the-sql-stored-procedure-for-schema-generation"></a><span data-ttu-id="d943d-105">スキーマを生成するために SQL ストアド プロシージャを更新するには</span><span class="sxs-lookup"><span data-stu-id="d943d-105">To update the SQL stored procedure for schema generation</span></span>  
  
1.  <span data-ttu-id="d943d-106">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリック**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="d943d-106">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="d943d-107">Microsoft SQL Server Management Studio で展開**データベース**、展開**Contoso**、展開**プログラミング**、順に展開**ストアド プロシージャ**.</span><span class="sxs-lookup"><span data-stu-id="d943d-107">In the Microsoft SQL Server Management Studio, expand **Databases**, expand **Contoso**, expand **Programmability**, and then expand **Stored Procedures**.</span></span>  
  
3.  <span data-ttu-id="d943d-108">右クリック**dbo します。SP_GetInventoryForProductID**、クリックして**変更**です。</span><span class="sxs-lookup"><span data-stu-id="d943d-108">Right-click **dbo.SP_GetInventoryForProductID**, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="d943d-109">クエリ ウィンドウで、"for xml auto" の直後にコンマとスペースを挿入し、その後に「xmldata」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d943d-109">In the query window, insert a comma, a space, and then "xmldata" immediately following "for xml auto".</span></span> <span data-ttu-id="d943d-110">コードの行を以下にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d943d-110">The line of code should be the following:</span></span>  
  
    ```  
    for xml auto, xmldata  
    ```  
  
5.  <span data-ttu-id="d943d-111">をクリックして**Execute**ストアド プロシージャに変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="d943d-111">Click **Execute** to save the changes to the stored procedure.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d943d-112">次の手順で使用するため、Microsoft SQL Server Management Studio は開いたままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="d943d-112">Leave the Microsoft SQL Server Management Studio open for the next procedure.</span></span>  
  
### <a name="to-create-the-contoso-price-and-availability-schema"></a><span data-ttu-id="d943d-113">ContosoPriceAndAvailability スキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="d943d-113">To create the Contoso Price and Availability schema</span></span>  
  
1.  <span data-ttu-id="d943d-114">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] で Contoso ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="d943d-114">Open the Contoso solution in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="d943d-115">ソリューション エクスプ ローラーで右クリックし、 **ContosoPriceAndAvailability**プロジェクトをポイントし、**追加**、順にクリック**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="d943d-115">In Solution Explorer, right-click the **ContosoPriceAndAvailability** project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
3.  <span data-ttu-id="d943d-116">生成おきの追加 ダイアログ ボックスで**アダプター メタデータの追加**をクリックして選択すると、左側のウィンドウで、**アダプター メタデータの追加**をクリックして右側のウィンドウ**追加**です。</span><span class="sxs-lookup"><span data-stu-id="d943d-116">In the Add Generated Iems dialog box, with **Add Adapter Metadata** selected in the left pane, click **Add Adapter Metadata** in the right pane, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="d943d-117">**アダプターの追加ウィザード**] ページで、[ **SQL**クリックして、登録されているアダプターの一覧から**次**です。</span><span class="sxs-lookup"><span data-stu-id="d943d-117">On the **Add Adapter Wizard** page, select **SQL** from the list of registered adapters, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="d943d-118">**データベース情報**] ページで [**設定**です。</span><span class="sxs-lookup"><span data-stu-id="d943d-118">On the **Database Information** page, click **Set**.</span></span>  
  
6.  <span data-ttu-id="d943d-119">[データ リンク プロパティ] ダイアログ ボックスで、**を選択するか、サーバー名を入力**ボックスに、入力**localhost**です。</span><span class="sxs-lookup"><span data-stu-id="d943d-119">In the Data Link Properties dialog box, in the **Select or enter a server name** box, type **localhost**.</span></span> <span data-ttu-id="d943d-120">選択**Windows NT 統合セキュリティ**です。</span><span class="sxs-lookup"><span data-stu-id="d943d-120">Select **Use Windows NT Integrated security**.</span></span> <span data-ttu-id="d943d-121">**サーバー上のデータベースを選択して**を選択、 **Contoso**データベースの一覧からデータベース。</span><span class="sxs-lookup"><span data-stu-id="d943d-121">For **Select the database on the server**, select the **Contoso** database from the database list.</span></span> <span data-ttu-id="d943d-122">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d943d-122">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="d943d-123">**データベース情報** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="d943d-123">On the **Database Information** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="d943d-124">**スキーマ情報** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="d943d-124">On the **Schema Information** page, do the following:</span></span>  
  
    |<span data-ttu-id="d943d-125">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d943d-125">Use this</span></span>|<span data-ttu-id="d943d-126">目的</span><span class="sxs-lookup"><span data-stu-id="d943d-126">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d943d-127">**ターゲットの名前空間**</span><span class="sxs-lookup"><span data-stu-id="d943d-127">**Target namespace**</span></span>|<span data-ttu-id="d943d-128">型**http://Contoso.com/Price**です。</span><span class="sxs-lookup"><span data-stu-id="d943d-128">Type **http://Contoso.com/Price**.</span></span>|  
    |<span data-ttu-id="d943d-129">**ポートの種類を選択します。**</span><span class="sxs-lookup"><span data-stu-id="d943d-129">**Select the port type**</span></span>|<span data-ttu-id="d943d-130">選択**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="d943d-130">Select **Send port**.</span></span>|  
    |<span data-ttu-id="d943d-131">**要求ドキュメントのルート要素名**</span><span class="sxs-lookup"><span data-stu-id="d943d-131">**Request document root element name**</span></span>|<span data-ttu-id="d943d-132">型**rootPriceRequest**です。</span><span class="sxs-lookup"><span data-stu-id="d943d-132">Type **rootPriceRequest**.</span></span>|  
    |<span data-ttu-id="d943d-133">**応答ドキュメントのルート要素名**</span><span class="sxs-lookup"><span data-stu-id="d943d-133">**Response document root element name**</span></span>|<span data-ttu-id="d943d-134">型**rootPriceResponse**です。</span><span class="sxs-lookup"><span data-stu-id="d943d-134">Type **rootPriceResponse**.</span></span>|  
  
9. <span data-ttu-id="d943d-135">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d943d-135">Click **Next**.</span></span>  
  
10. <span data-ttu-id="d943d-136">**ステートメントの種類の情報**] ページで、[**ストアド プロシージャの**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="d943d-136">On the **Statement type information** page, select **Stored Procedure**, and then click **Next**.</span></span>  
  
11. <span data-ttu-id="d943d-137">**ステートメント情報**] ページの**\<ストアド プロシージャを選択\>**[ **SP_GetInventoryForProductID**から、ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="d943d-137">On the **Statement Information** page, for **\<Select a stored procedure\>**, select **SP_GetInventoryForProductID** from the drop-down list.</span></span> <span data-ttu-id="d943d-138">をクリックして**生成**、クリックして **[次へ]** です。</span><span class="sxs-lookup"><span data-stu-id="d943d-138">Click **Generate**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="d943d-139">**SQL トランスポート スキーマ生成ウィザードを完了する** ページで、をクリックして**完了**ContosoPriceAndAvailability BizTalk プロジェクトにスキーマをインポートします。</span><span class="sxs-lookup"><span data-stu-id="d943d-139">On the **Completing the SQL Transport Schema Generation Wizard** page, click **Finish** to import the schema into the ContosoPriceAndAvailability BizTalk project.</span></span>  
  
13. <span data-ttu-id="d943d-140">ソリューション エクスプ ローラーで、生成されたスキーマ (SQLService_Price.xsd) を右クリックし、をクリックして**の名前を変更**、および種類**ContosoPriceAndAvailability.xsd**スキーマの新しい名前として。</span><span class="sxs-lookup"><span data-stu-id="d943d-140">In Solution Explorer, right-click the generated schema (SQLService_Price.xsd), click **Rename**, and type **ContosoPriceAndAvailability.xsd** as the new name for the schema.</span></span> <span data-ttu-id="d943d-141">**Enter**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d943d-141">Click **Enter**.</span></span>  
  
14. <span data-ttu-id="d943d-142">ContosoPriceAndAvailability スキーマの [プロパティ] ウィンドウで、設定、**型名**プロパティを**ContosoPriceSchema**です。</span><span class="sxs-lookup"><span data-stu-id="d943d-142">In the Properties window for the ContosoPriceAndAvailability schema, set the **Type Name** property to **ContosoPriceSchema**.</span></span>  
  
15. <span data-ttu-id="d943d-143">既定では、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]という名前の BizTalk オーケストレーションを作成**BizTalk Orchestration.odx**です。</span><span class="sxs-lookup"><span data-stu-id="d943d-143">By default, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] creates a BizTalk orchestration named **BizTalk Orchestration.odx**.</span></span> <span data-ttu-id="d943d-144">このオーケストレーションを右クリックし、をクリックして**削除**このオーケストレーションを必要としないためです。</span><span class="sxs-lookup"><span data-stu-id="d943d-144">Right-click this orchestration, and then click **Delete** because you do not need this orchestration.</span></span> <span data-ttu-id="d943d-145">オーケストレーションが完全に削除されることを示すポップアップで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d943d-145">In the popup indicating that the orchestration will be deleted permanently, click **OK**.</span></span>  
  
16. <span data-ttu-id="d943d-146">Microsoft SQL Server Management Studio では、削除、`xmldata`述語とコンマを`SP_GetInventoryForProductID`ストアド プロシージャ、前の手順で追加して、をクリックして**Execute**です。</span><span class="sxs-lookup"><span data-stu-id="d943d-146">In the Microsoft SQL Server Management Studio, remove the `xmldata` predicate and the comma from the `SP_GetInventoryForProductID` stored procedure that you added in the previous step, and then click **Execute**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d943d-147">参照</span><span class="sxs-lookup"><span data-stu-id="d943d-147">See Also</span></span>  
 [<span data-ttu-id="d943d-148">手順 3: BizTalk マッパーを使用した Price and Availability プロジェクト用の Contoso LOB アプリケーション マップの作成</span><span class="sxs-lookup"><span data-stu-id="d943d-148">Step 3: Creating the Contoso LOB Application Maps for the Price and Availability Project Using BizTalk Mapper</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-create-contoso-lob-application-map-for-price-and-availability-in-mapper.md)