---
title: 手順 3 c:SQL Server データベースに営業案件の詳細を挿入 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f6f9bbe-6f25-4393-8f92-aeeba9736acf
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c49c7b182d3a6fda593ea34f20238328f47ce5a8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392595"
---
# <a name="step-3c-insert-opportunity-details-into-a-sql-server-database"></a><span data-ttu-id="71a0d-102">手順 3 c:SQL Server データベースに営業案件の詳細を挿入します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-102">Step 3c: Insert Opportunity Details into a SQL Server Database</span></span>
<span data-ttu-id="71a0d-103">ここまででは、Salesforce にクエリを送信し、応答を受信するオーケストレーションを組み込みました。</span><span class="sxs-lookup"><span data-stu-id="71a0d-103">By now we have built the orchestration to send a query to Salesforce and receive a response.</span></span> <span data-ttu-id="71a0d-104">このセクションでは、Salesforce からの応答を挿入するようにオーケストレーションを更新します、 **OrderDetails** 、オンプレミスの SQL Server データベース内のテーブル**注文**します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-104">In this section, we’ll update that orchestration to insert the response from Salesforce into an **OrderDetails** table in an on-premise SQL Server database, **Orders**.</span></span> <span data-ttu-id="71a0d-105">これを実現するには、次の広範な一連の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-105">To achieve this, we’ll perform the following broad set of steps:</span></span>  
  
- <span data-ttu-id="71a0d-106">作成、 **OrderDetails**テーブルに、**注文**オンプレミスの SQL Server データベース内のデータベース。</span><span class="sxs-lookup"><span data-stu-id="71a0d-106">Create an **OrderDetails** table in an **Orders** database in an on-premise SQL Server database.</span></span>  
  
- <span data-ttu-id="71a0d-107">使用して、[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]で使用可能な[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]挿入操作のスキーマを生成する、 **OrderDetails**テーブル。</span><span class="sxs-lookup"><span data-stu-id="71a0d-107">Use the [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] available with [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] to generate the schema for the Insert operation on the **OrderDetails** table.</span></span>  
  
- <span data-ttu-id="71a0d-108">メッセージに挿入するために、Salesforce 応答メッセージを変換するマップを作成する**OrderDetails** SQL Server のテーブル。</span><span class="sxs-lookup"><span data-stu-id="71a0d-108">Create a map to transform the Salesforce response message to the message for inserting into **OrderDetails** table in SQL Server.</span></span>  
  
- <span data-ttu-id="71a0d-109">変換を使用してに応答メッセージを挿入するオーケストレーションを更新、 **OrderDetails**テーブル。</span><span class="sxs-lookup"><span data-stu-id="71a0d-109">Update the orchestration to use the transform to insert the response message into the **OrderDetails** table.</span></span>  
  
## <a name="create-sql-server-database-and-table"></a><span data-ttu-id="71a0d-110">SQL Server データベースとテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-110">Create SQL Server Database and Table</span></span>  
  
#### <a name="to-create-the-database-and-table"></a><span data-ttu-id="71a0d-111">データベースとテーブルを作成するには</span><span class="sxs-lookup"><span data-stu-id="71a0d-111">To create the database and table</span></span>  
  
1.  <span data-ttu-id="71a0d-112">SQL Server Management Studio を開き、管理者として接続します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-112">Open SQL Server Management Studio and connect as an administrator.</span></span>  
  
2.  <span data-ttu-id="71a0d-113">右クリックし、**データベース**ノードをクリックします**新しいデータベース**します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-113">Right-click the **Databases** node and click **New Database**.</span></span> <span data-ttu-id="71a0d-114">データベースの名前を指定`Orders`し、新しいデータベースを作成するには、その他の詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-114">Specify the database name as `Orders` and specify other details to create a new database.</span></span>  
  
3.  <span data-ttu-id="71a0d-115">クエリ エディターを開き、次のクエリを作成するを実行して、 **OrderDetails**テーブルに、**注文**データベース。</span><span class="sxs-lookup"><span data-stu-id="71a0d-115">Open a query editor and run the following query to create an **OrderDetails** table in the **Orders** database:</span></span>  
  
    ```  
    USE [Orders]  
    GO  
    /****** Object:  Table [dbo].[OrderDetails]    Script Date: 07-12-2012 22:15:47 ******/  
    SET ANSI_NULLS ON  
    GO  
    SET QUOTED_IDENTIFIER ON  
    GO  
    SET ANSI_PADDING ON  
    GO  
    CREATE TABLE [dbo].[OrderDetails]([ID] [int] IDENTITY(1,1) NOT NULL,  
    [TITLE] [varchar](200) NULL,  
    [ProductName] [varchar](200) NULL,  
    [Quantity] [float] NULL,  
    [Amount] [float] NULL,  
    PRIMARY KEY CLUSTERED   
    (  
    [ID] ASC  
    )WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]  
    GO  
    SET ANSI_PADDING OFF  
    GO  
    ```  
  
## <a name="create-schema-for-insert-operation-on-orderdetails-table"></a><span data-ttu-id="71a0d-116">OrderDetails テーブルに対する挿入操作のスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-116">Create Schema for Insert Operation on OrderDetails Table</span></span>  
 <span data-ttu-id="71a0d-117">インストールする[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]提供、[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]内で使用できる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]挿入操作のスキーマを生成するプロジェクト、 **OrderDetails**テーブル。</span><span class="sxs-lookup"><span data-stu-id="71a0d-117">Installing [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] provides a [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] that can be used within a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project to generate the schema for the Insert operation on the **OrderDetails** table.</span></span> <span data-ttu-id="71a0d-118">このセクションでは、メッセージ スキーマを作成する手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-118">This section provides steps to follow to create the message schema.</span></span>  
  
#### <a name="to-create-the-schema-for-insert-operation"></a><span data-ttu-id="71a0d-119">挿入操作のスキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="71a0d-119">To create the schema for Insert operation</span></span>  
  
1. <span data-ttu-id="71a0d-120">右クリックし、 **BtsSalesforceIntegration**プロジェクトをポイントして、**追加**、 をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-120">Right-click the **BtsSalesforceIntegration** project, point to **Add**, and then click **Add Generated Items**.</span></span> <span data-ttu-id="71a0d-121">**生成した項目の追加**ダイアログ ボックスで、をクリックして**Consume Adapter Service**、順にクリックします**追加**します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-121">In the **Add Generated Items** dialog box, click **Consume Adapter Service**, and then click **Add**.</span></span>  
  
2. <span data-ttu-id="71a0d-122">[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]、バインド ドロップダウンの選択 をクリックします。 **sqlBinding**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-122">In the [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)], from the Select a binding drop-down, click **sqlBinding**, and then click **Configure**.</span></span>  
  
3. <span data-ttu-id="71a0d-123">**アダプターの構成**ダイアログ ボックスで、**セキュリティ** タブの**クライアント資格情報の種類**、 **Windows** Windows を使用するにはSQL Server データベースへの接続に認証します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-123">In the **Configure Adapter** dialog box, under **Security** tab, for **Client credential type**, select **Windows** to use Windows authentication to connect to SQL Server database.</span></span>  
  
4. <span data-ttu-id="71a0d-124">**アダプターの構成**ダイアログ ボックスで、 **URI プロパティ** タブの**Initial Catalog** (Orders) に接続するデータベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-124">In the **Configure Adapter** dialog box, under **URI Properties** tab, for **Initial Catalog** specify the database name (Orders) to connect to.</span></span> <span data-ttu-id="71a0d-125">**Server**に接続している SQL Server がインストールされているコンピューター名を指定します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-125">For **Server** specify the computer name where SQL Server you are connecting to is installed.</span></span> <span data-ttu-id="71a0d-126">かどうか、SQL Server データベースと同じコンピューター上、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト、ピリオドだけ配置できます (**.**)。</span><span class="sxs-lookup"><span data-stu-id="71a0d-126">If the SQL Server database is on the same computer as the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, you can just put a period (**.**).</span></span> <span data-ttu-id="71a0d-127">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71a0d-127">Click **OK**.</span></span>  
  
5. <span data-ttu-id="71a0d-128">[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]クリックして**Connect**します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-128">In the [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] click **Connect**.</span></span> <span data-ttu-id="71a0d-129">接続が確立されると、コントラクトの種類を選択します。**クライアント (送信操作)** します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-129">After the connection is established, select the contract type as **Client(Outbound operations)**.</span></span> <span data-ttu-id="71a0d-130">下、**カテゴリを選択**ボックスで、展開**テーブル**、] をクリックして**OrderDetails**テーブル、および右のウィンドウで [**挿入**順にクリックします**追加**します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-130">Under the **Select a category** box, expand **Tables**, click **OrderDetails** table, and in the right pane click **Insert** and then click **Add**.</span></span>  
  
6. <span data-ttu-id="71a0d-131">指定、**ファイル名のプレフィックス**生成されたスキーマに id をプレフィックスする場合。</span><span class="sxs-lookup"><span data-stu-id="71a0d-131">Specify a **Filename Prefix** if you want to prefix the generated schemas with an identifier.</span></span> <span data-ttu-id="71a0d-132">このチュートリアルとプレフィックスを指定しましょう**InsertOrders**  をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-132">For this tutorial, let’s specify the prefix as **InsertOrders** and then click **OK**.</span></span>  
  
    <span data-ttu-id="71a0d-133">多数のスキーマは、プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="71a0d-133">A bunch of schemas are added to the project.</span></span> <span data-ttu-id="71a0d-134">スキーマにメッセージを挿入を使用する、 **OrderDetails**テーブルが**InsertOrdersTableOperation.dbo.OrderDetails.xsd**します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-134">The schema that we’ll use for inserting messages into the **OrderDetails** table is **InsertOrdersTableOperation.dbo.OrderDetails.xsd**.</span></span>  
  
## <a name="map-salesforce-response-and-insert-schemas"></a><span data-ttu-id="71a0d-135">マップの Salesforce 応答と挿入スキーマ</span><span class="sxs-lookup"><span data-stu-id="71a0d-135">Map Salesforce Response and Insert Schemas</span></span>  
 <span data-ttu-id="71a0d-136">両方のスキーマが作成できた (Salesforce や挿入からの応答**OrderDetails**)、私たちの挿入スキーマには、Salesforce から応答スキーマをマップする必要があります**OrderDetails**ように、Salesforce からの応答メッセージは、SQL Server データベースのテーブルに挿入することができます。</span><span class="sxs-lookup"><span data-stu-id="71a0d-136">Now that we have both the schemas (response from Salesforce and inserting into **OrderDetails**), we must map the response schema from Salesforce into the insert schema for **OrderDetails** so that the response message from Salesforce can be inserted in the SQL Server database table.</span></span>  
  
#### <a name="to-map-the-schemas"></a><span data-ttu-id="71a0d-137">スキーマをマップするには</span><span class="sxs-lookup"><span data-stu-id="71a0d-137">To map the schemas</span></span>  
  
1.  <span data-ttu-id="71a0d-138">右クリックし、 **BtsSalesforceIntegration**プロジェクトをポイントして、**追加**、 をクリックして**新しい項目の**、 をクリックし、**マップ**。</span><span class="sxs-lookup"><span data-stu-id="71a0d-138">Right-click the **BtsSalesforceIntegration** project, point to **Add**, click **New Item**, and then click **Map**.</span></span> <span data-ttu-id="71a0d-139">マップ名として指定`QueryResult_Orders.btm` をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-139">Specify the map name as `QueryResult_Orders.btm` and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="71a0d-140">送信元スキーマ、マップ画面で選択**QueryResult** 、送信先スキーマの選択と**InsertOrdersTableOperation.dbo.OrderDetails.xsd**と、その中、 **挿入**ノード。</span><span class="sxs-lookup"><span data-stu-id="71a0d-140">On the map surface, for the source schema, select **QueryResult** and for the destination schema, select **InsertOrdersTableOperation.dbo.OrderDetails.xsd** and then within that, the **Insert** node.</span></span>  
  
3.  <span data-ttu-id="71a0d-141">次のスクリーン ショットに示すように 2 つのスキーマをマップします。</span><span class="sxs-lookup"><span data-stu-id="71a0d-141">Map the two schemas as shown in the following screenshot:</span></span>  
  
     <span data-ttu-id="71a0d-142">![挿入スキーマに Salesforce 応答にマップする](../core/media/bts-sf-map-response-insert.jpg "BTS_SF_Map_Response_Insert")</span><span class="sxs-lookup"><span data-stu-id="71a0d-142">![Map Salesforce response to Insert schema](../core/media/bts-sf-map-response-insert.jpg "BTS_SF_Map_Response_Insert")</span></span>  
  
     <span data-ttu-id="71a0d-143">マップを使用して通知を**ループ**間の functoid、**レコード**と**OrderDetails**リンク。</span><span class="sxs-lookup"><span data-stu-id="71a0d-143">Notice that the map uses a **Looping** functoid between the **records** and the **OrderDetails** link.</span></span> <span data-ttu-id="71a0d-144">これにより、1 つまたは複数の出現箇所の下のノードの**レコード**同じ数のノードの下にマップされます、 **OrderDetails**します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-144">This ensures that all one or more than one occurrences of nodes under **records** are mapped to similar occurrences of nodes under the **OrderDetails**.</span></span>  
  
4.  <span data-ttu-id="71a0d-145">マップに変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-145">Save changes to the map.</span></span>  
  
## <a name="update-the-orchestration-to-insert-messages-into-sql-server"></a><span data-ttu-id="71a0d-146">SQL Server にメッセージを挿入するオーケストレーションを更新します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-146">Update the Orchestration to Insert Messages into SQL Server</span></span>  
 <span data-ttu-id="71a0d-147">このセクションで、SQL Server テーブルに注文の詳細を挿入するためのメッセージに、Salesforce 応答メッセージを変換するのに、マップ、オーケストレーションで使用します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-147">In this section, we’ll use the map in the orchestration to transform the Salesforce response message into a message for inserting order details in a SQL Server table.</span></span> <span data-ttu-id="71a0d-148">SQL Server にそのメッセージを送信するポートも追加します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-148">We’ll also add a port to send that message to SQL Server.</span></span>  
  
#### <a name="to-update-the-orchestration"></a><span data-ttu-id="71a0d-149">オーケストレーションを更新するには</span><span class="sxs-lookup"><span data-stu-id="71a0d-149">To update the orchestration</span></span>  
  
1. <span data-ttu-id="71a0d-150">挿入スキーマのメッセージ変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-150">Create a message variable for the insert schema.</span></span> <span data-ttu-id="71a0d-151">オーケストレーションの種類を右クリックして、**メッセージ**ノード、およびクリック**新しいメッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-151">From the orchestration view, right-click the **Messages** node, and then click **New Message**.</span></span> <span data-ttu-id="71a0d-152">メッセージの名前を設定**InsertOrders** 、メッセージの種類**BtsSalesforceIntegration.InsertOrdersTableOperation_dbo_OrderDetails.Insert**します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-152">Set the message name as **InsertOrders** and message type as **BtsSalesforceIntegration.InsertOrdersTableOperation_dbo_OrderDetails.Insert**.</span></span>  
  
2. <span data-ttu-id="71a0d-153">後のメッセージの構築図形を追加、 **ReceiveQueryResult**図形。</span><span class="sxs-lookup"><span data-stu-id="71a0d-153">Add a Construct Message shape after the **ReceiveQueryResult** shape.</span></span> <span data-ttu-id="71a0d-154">図形の名前を設定`ConstructOrders`設定と、**構築メッセージ**プロパティを**InsertOrders**します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-154">Set the name of the shape to `ConstructOrders` and set the **Messages Constructed** property to **InsertOrders**.</span></span>  
  
3. <span data-ttu-id="71a0d-155">内で、 **ConstructOrders**図形を追加、**変換**図形。</span><span class="sxs-lookup"><span data-stu-id="71a0d-155">Within the **ConstructOrders** shape, add a **Transform** shape.</span></span> <span data-ttu-id="71a0d-156">変換の構成 ダイアログ ボックスを開くための変換図形をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="71a0d-156">Double-click the Transform shape to open the Transform Configuration dialog box.</span></span> <span data-ttu-id="71a0d-157">ダイアログ ボックスで、選択、**既存のマップ**、オプションをドロップダウン リストから選択して**BtsSalesforceIntegration.QueryResult_Orders**します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-157">In the dialog box, select the **Existing Map** option, and then from the drop-down select **BtsSalesforceIntegration.QueryResult_Orders**.</span></span> <span data-ttu-id="71a0d-158">設定**ソース**に**QueryResultMsg**、**先**に**InsertOrders**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="71a0d-158">Set **Source** to **QueryResultMsg**, **Destination** to **InsertOrders**, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="71a0d-159">後に、 **ConstructOrders**図形を送信図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-159">After the **ConstructOrders** shape, add a Send shape.</span></span> <span data-ttu-id="71a0d-160">図形の名前は`SendOrders`としてメッセージの種類を設定および**InsertOrders**します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-160">Name the shape `SendOrders` and set the message type as **InsertOrders**.</span></span>  
  
5. <span data-ttu-id="71a0d-161">Salesforce に注文の詳細を挿入するポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-161">Add a port to insert order details into Salesforce.</span></span> <span data-ttu-id="71a0d-162">ポート構成ウィザードでは、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-162">In the Port Configuration wizard, select the following options:</span></span>  
  
   - <span data-ttu-id="71a0d-163">ポート名を指定`SendToSQL`します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-163">Specify the port name as `SendToSQL`.</span></span>  
  
   - <span data-ttu-id="71a0d-164">新しいポートの種類を作成するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-164">Select the option to create a new port type.</span></span>  
  
   - <span data-ttu-id="71a0d-165">設定**通信パターン**に*一方向*します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-165">Set **Communication Pattern** to *One-Way*.</span></span>  
  
   - <span data-ttu-id="71a0d-166">設定**ポートの通信方向**に*は常にメッセージを送信しますこのポートで*設定と**ポートのバインド**に*後で指定する*します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-166">Set **Port direction of communication** to *I’ll always be sending messages on this port* and set **Port binding** to *Specify later*.</span></span>  
  
     <span data-ttu-id="71a0d-167">接続、**要求**へのポートの操作、 **SendOrders**送信図形をオーケストレーションを完了します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-167">Connect the **Request** operation of port to the **SendOrders** Send shape to complete the orchestration.</span></span> <span data-ttu-id="71a0d-168">次のスクリーン ショットは、完了したオーケストレーションをエンド ツー エンドを示しています。</span><span class="sxs-lookup"><span data-stu-id="71a0d-168">The following screenshot depicts the completed orchestration, end-to-end.</span></span>  
  
     <span data-ttu-id="71a0d-169">![Salesforce との統合のオーケストレーションを完了する](../core/media/bts-sf-complete-orch.jpg "BTS_SF_Complete_Orch")</span><span class="sxs-lookup"><span data-stu-id="71a0d-169">![Complete orchesration for Salesforce integration](../core/media/bts-sf-complete-orch.jpg "BTS_SF_Complete_Orch")</span></span>  
  
     <span data-ttu-id="71a0d-170">厳密な名前キー ファイルをプロジェクトに追加し、プロジェクトに変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-170">Add a strong name key file to the project and save changes to the project.</span></span>  
  
   <span data-ttu-id="71a0d-171">このトピックの手順で、Salesforce から営業案件通知を受信、Salesforce の営業案件の詳細についてはクエリ、および SQL Server データベースに、クエリの応答を挿入するオーケストレーションが完了しました。</span><span class="sxs-lookup"><span data-stu-id="71a0d-171">With the steps in this topic, we have completed the orchestration, to receive an opportunity notification from Salesforce, query Salesforce for more details about the opportunity, and then insert the query response into a SQL Server database.</span></span> <span data-ttu-id="71a0d-172">以降のトピックでは、その他のキーの一部のコンポーネント、ソリューションで Salesforce と BizTalk Server 内での Salesforce の応答のプロセスの認証に使用されるを作成します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-172">In the subsequent topics, we’ll build some other key components of the solution that are used to authenticate with Salesforce and process Salesforce response within BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71a0d-173">参照</span><span class="sxs-lookup"><span data-stu-id="71a0d-173">See Also</span></span>  
 [<span data-ttu-id="71a0d-174">ステップ 3:Visual Studio で BizTalk Server ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="71a0d-174">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)