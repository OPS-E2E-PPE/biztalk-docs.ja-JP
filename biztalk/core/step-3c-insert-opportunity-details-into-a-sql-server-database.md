---
title: '手順 3 c: SQL Server データベースに営業案件の詳細を挿入 |Microsoft ドキュメント'
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
ms.openlocfilehash: 33d0055c05e0c9af9f4dddc4a7275c01ff49d779
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280090"
---
# <a name="step-3c-insert-opportunity-details-into-a-sql-server-database"></a><span data-ttu-id="7875b-102">手順 3 c: SQL Server データベースに営業案件の詳細を挿入</span><span class="sxs-lookup"><span data-stu-id="7875b-102">Step 3c: Insert Opportunity Details into a SQL Server Database</span></span>
<span data-ttu-id="7875b-103">ここまでに、Salesforce にクエリ要求を送信し、応答を受信するためのオーケストレーションをビルドしました。</span><span class="sxs-lookup"><span data-stu-id="7875b-103">By now we have built the orchestration to send a query to Salesforce and receive a response.</span></span> <span data-ttu-id="7875b-104">このセクションで Salesforce からの応答を挿入するようにオーケストレーションが更新されます、 **OrderDetails** 、内部設置型 SQL Server データベースのテーブルに**Orders**です。</span><span class="sxs-lookup"><span data-stu-id="7875b-104">In this section, we’ll update that orchestration to insert the response from Salesforce into an **OrderDetails** table in an on-premise SQL Server database, **Orders**.</span></span> <span data-ttu-id="7875b-105">これを達成するには、次のようなさまざまな手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7875b-105">To achieve this, we’ll perform the following broad set of steps:</span></span>  
  
-   <span data-ttu-id="7875b-106">作成、 **OrderDetails**テーブルに、 **Orders**内部設置型 SQL Server データベース内のデータベースです。</span><span class="sxs-lookup"><span data-stu-id="7875b-106">Create an **OrderDetails** table in an **Orders** database in an on-premise SQL Server database.</span></span>  
  
-   <span data-ttu-id="7875b-107">使用して、[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]で利用可能な[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]で挿入操作のスキーマを生成する、 **OrderDetails**テーブル。</span><span class="sxs-lookup"><span data-stu-id="7875b-107">Use the [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] available with [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] to generate the schema for the Insert operation on the **OrderDetails** table.</span></span>  
  
-   <span data-ttu-id="7875b-108">メッセージに挿入するために、Salesforce 応答メッセージを変換するマップを作成する**OrderDetails** SQL Server テーブルにします。</span><span class="sxs-lookup"><span data-stu-id="7875b-108">Create a map to transform the Salesforce response message to the message for inserting into **OrderDetails** table in SQL Server.</span></span>  
  
-   <span data-ttu-id="7875b-109">オーケストレーションを更新するには、応答メッセージを挿入する変換を使用する、 **OrderDetails**テーブル。</span><span class="sxs-lookup"><span data-stu-id="7875b-109">Update the orchestration to use the transform to insert the response message into the **OrderDetails** table.</span></span>  
  
## <a name="create-sql-server-database-and-table"></a><span data-ttu-id="7875b-110">SQL Server データベースとテーブルを作成する</span><span class="sxs-lookup"><span data-stu-id="7875b-110">Create SQL Server Database and Table</span></span>  
  
#### <a name="to-create-the-database-and-table"></a><span data-ttu-id="7875b-111">データベースとテーブルを作成するには</span><span class="sxs-lookup"><span data-stu-id="7875b-111">To create the database and table</span></span>  
  
1.  <span data-ttu-id="7875b-112">SQL Server Management Studio を開き、管理者として接続します。</span><span class="sxs-lookup"><span data-stu-id="7875b-112">Open SQL Server Management Studio and connect as an administrator.</span></span>  
  
2.  <span data-ttu-id="7875b-113">右クリックし、**データベース**ノードとクリック**新しいデータベース**です。</span><span class="sxs-lookup"><span data-stu-id="7875b-113">Right-click the **Databases** node and click **New Database**.</span></span> <span data-ttu-id="7875b-114">データベース名として指定`Orders`と新しいデータベースを作成するには、他の詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="7875b-114">Specify the database name as `Orders` and specify other details to create a new database.</span></span>  
  
3.  <span data-ttu-id="7875b-115">クエリ エディターを開き、次のクエリを作成する実行、 **OrderDetails**テーブルに、 **Orders**データベース。</span><span class="sxs-lookup"><span data-stu-id="7875b-115">Open a query editor and run the following query to create an **OrderDetails** table in the **Orders** database:</span></span>  
  
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
  
## <a name="create-schema-for-insert-operation-on-orderdetails-table"></a><span data-ttu-id="7875b-116">[OrderDetails] テーブルで挿入操作を行うスキーマを作成する</span><span class="sxs-lookup"><span data-stu-id="7875b-116">Create Schema for Insert Operation on OrderDetails Table</span></span>  
 <span data-ttu-id="7875b-117">インストールする[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]提供、[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]内で使用できる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で挿入操作のスキーマを生成するプロジェクト、 **OrderDetails**テーブル。</span><span class="sxs-lookup"><span data-stu-id="7875b-117">Installing [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] provides a [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] that can be used within a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project to generate the schema for the Insert operation on the **OrderDetails** table.</span></span> <span data-ttu-id="7875b-118">このセクションでは、次のメッセージ スキーマを作成する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="7875b-118">This section provides steps to follow to create the message schema.</span></span>  
  
#### <a name="to-create-the-schema-for-insert-operation"></a><span data-ttu-id="7875b-119">挿入操作を行うスキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="7875b-119">To create the schema for Insert operation</span></span>  
  
1.  <span data-ttu-id="7875b-120">右クリックし、 **BtsSalesforceIntegration**プロジェクトをポイントし、**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="7875b-120">Right-click the **BtsSalesforceIntegration** project, point to **Add**, and then click **Add Generated Items**.</span></span> <span data-ttu-id="7875b-121">**生成した項目の追加**ダイアログ ボックスで、をクリックして**アダプター サービスの使用**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="7875b-121">In the **Add Generated Items** dialog box, click **Consume Adapter Service**, and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="7875b-122">[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]、バインディングのドロップダウン リストの選択 をクリックして**sqlBinding**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="7875b-122">In the [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)], from the Select a binding drop-down, click **sqlBinding**, and then click **Configure**.</span></span>  
  
3.  <span data-ttu-id="7875b-123">**アダプターの構成**ダイアログ ボックスで、**セキュリティ**] タブの**クライアント資格情報の種類**[ **Windows** Windows を使用するにはSQL Server データベースへの接続に認証します。</span><span class="sxs-lookup"><span data-stu-id="7875b-123">In the **Configure Adapter** dialog box, under **Security** tab, for **Client credential type**, select **Windows** to use Windows authentication to connect to SQL Server database.</span></span>  
  
4.  <span data-ttu-id="7875b-124">**アダプターの構成**ダイアログ ボックスで、 **URI プロパティ** タブの**初期カタログ**(Orders) に接続するデータベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="7875b-124">In the **Configure Adapter** dialog box, under **URI Properties** tab, for **Initial Catalog** specify the database name (Orders) to connect to.</span></span> <span data-ttu-id="7875b-125">**サーバー**に接続している SQL Server がインストールされているコンピューター名を指定します。</span><span class="sxs-lookup"><span data-stu-id="7875b-125">For **Server** specify the computer name where SQL Server you are connecting to is installed.</span></span> <span data-ttu-id="7875b-126">かどうか、SQL Server データベースと同じコンピューターには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト、ピリオドだけ配置できます (**.**)。</span><span class="sxs-lookup"><span data-stu-id="7875b-126">If the SQL Server database is on the same computer as the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, you can just put a period (**.**).</span></span> <span data-ttu-id="7875b-127">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7875b-127">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="7875b-128">[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]クリックして**接続**です。</span><span class="sxs-lookup"><span data-stu-id="7875b-128">In the [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)] click **Connect**.</span></span> <span data-ttu-id="7875b-129">接続が確立されると、選択したコントラクト型として**クライアント (送信操作)** です。</span><span class="sxs-lookup"><span data-stu-id="7875b-129">After the connection is established, select the contract type as **Client(Outbound operations)**.</span></span> <span data-ttu-id="7875b-130">下にある、**カテゴリを選択**ボックスで、展開**テーブル**、 をクリックして**OrderDetails**テーブル、および右側のウィンドウでをクリックして**挿入** をクリックし、**追加**です。</span><span class="sxs-lookup"><span data-stu-id="7875b-130">Under the **Select a category** box, expand **Tables**, click **OrderDetails** table, and in the right pane click **Insert** and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="7875b-131">指定して、**ファイル名のプレフィックス**を生成されたスキーマに id をプレフィックスする場合。</span><span class="sxs-lookup"><span data-stu-id="7875b-131">Specify a **Filename Prefix** if you want to prefix the generated schemas with an identifier.</span></span> <span data-ttu-id="7875b-132">このチュートリアルでは、プレフィックスとしてを指定しましょう**InsertOrders**  をクリックし、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="7875b-132">For this tutorial, let’s specify the prefix as **InsertOrders** and then click **OK**.</span></span>  
  
     <span data-ttu-id="7875b-133">プロジェクトには多数のスキーマが追加されます。</span><span class="sxs-lookup"><span data-stu-id="7875b-133">A bunch of schemas are added to the project.</span></span> <span data-ttu-id="7875b-134">メッセージを挿入するために使用するスキーマ、 **OrderDetails**テーブルが**InsertOrdersTableOperation.dbo.OrderDetails.xsd**です。</span><span class="sxs-lookup"><span data-stu-id="7875b-134">The schema that we’ll use for inserting messages into the **OrderDetails** table is **InsertOrdersTableOperation.dbo.OrderDetails.xsd**.</span></span>  
  
## <a name="map-salesforce-response-and-insert-schemas"></a><span data-ttu-id="7875b-135">Salesforce 応答と挿入スキーマをマップする</span><span class="sxs-lookup"><span data-stu-id="7875b-135">Map Salesforce Response and Insert Schemas</span></span>  
 <span data-ttu-id="7875b-136">これでが両方のスキーマ (Salesforce への挿入と応答**OrderDetails**)、おの挿入スキーマには、Salesforce から応答スキーマをマップする必要があります**OrderDetails**できるように、Salesforce からの応答メッセージは、SQL Server データベース テーブルに挿入することができます。</span><span class="sxs-lookup"><span data-stu-id="7875b-136">Now that we have both the schemas (response from Salesforce and inserting into **OrderDetails**), we must map the response schema from Salesforce into the insert schema for **OrderDetails** so that the response message from Salesforce can be inserted in the SQL Server database table.</span></span>  
  
#### <a name="to-map-the-schemas"></a><span data-ttu-id="7875b-137">スキーマをマップするには</span><span class="sxs-lookup"><span data-stu-id="7875b-137">To map the schemas</span></span>  
  
1.  <span data-ttu-id="7875b-138">右クリックし、 **BtsSalesforceIntegration**プロジェクトをポイントし、**追加**、 をクリックして**新しい項目の**、順にクリック**マップ**です。</span><span class="sxs-lookup"><span data-stu-id="7875b-138">Right-click the **BtsSalesforceIntegration** project, point to **Add**, click **New Item**, and then click **Map**.</span></span> <span data-ttu-id="7875b-139">マップ名として指定`QueryResult_Orders.btm` をクリックし、**追加**です。</span><span class="sxs-lookup"><span data-stu-id="7875b-139">Specify the map name as `QueryResult_Orders.btm` and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="7875b-140">送信元スキーマ、マップ画面で選択**QueryResult** 、送信先スキーマの選択と**InsertOrdersTableOperation.dbo.OrderDetails.xsd**し、その、 **挿入**ノード。</span><span class="sxs-lookup"><span data-stu-id="7875b-140">On the map surface, for the source schema, select **QueryResult** and for the destination schema, select **InsertOrdersTableOperation.dbo.OrderDetails.xsd** and then within that, the **Insert** node.</span></span>  
  
3.  <span data-ttu-id="7875b-141">次のスクリーンショットに示されているように 2 つのスキーマをマップします。</span><span class="sxs-lookup"><span data-stu-id="7875b-141">Map the two schemas as shown in the following screenshot:</span></span>  
  
     <span data-ttu-id="7875b-142">![挿入スキーマに Salesforce 応答にマップする](../core/media/bts-sf-map-response-insert.jpg "BTS_SF_Map_Response_Insert")</span><span class="sxs-lookup"><span data-stu-id="7875b-142">![Map Salesforce response to Insert schema](../core/media/bts-sf-map-response-insert.jpg "BTS_SF_Map_Response_Insert")</span></span>  
  
     <span data-ttu-id="7875b-143">マップの使用に注意してください、**ループ**間の functoid、**レコード**と**OrderDetails**リンクします。</span><span class="sxs-lookup"><span data-stu-id="7875b-143">Notice that the map uses a **Looping** functoid between the **records** and the **OrderDetails** link.</span></span> <span data-ttu-id="7875b-144">これにより、すべて 1 つまたは複数の下にあるノードの出現**レコード**同じ数の下にあるノードにマップされて、 **OrderDetails**です。</span><span class="sxs-lookup"><span data-stu-id="7875b-144">This ensures that all one or more than one occurrences of nodes under **records** are mapped to similar occurrences of nodes under the **OrderDetails**.</span></span>  
  
4.  <span data-ttu-id="7875b-145">マップへの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="7875b-145">Save changes to the map.</span></span>  
  
## <a name="update-the-orchestration-to-insert-messages-into-sql-server"></a><span data-ttu-id="7875b-146">SQL Server にメッセージを挿入するオーケストレーションを更新する</span><span class="sxs-lookup"><span data-stu-id="7875b-146">Update the Orchestration to Insert Messages into SQL Server</span></span>  
 <span data-ttu-id="7875b-147">このセクションでは、オーケストレーション内のマップを使用して、Salesforce 応答メッセージを SQL Server のテーブルに注文詳細を挿入するためのメッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="7875b-147">In this section, we’ll use the map in the orchestration to transform the Salesforce response message into a message for inserting order details in a SQL Server table.</span></span> <span data-ttu-id="7875b-148">さらに、SQL Server にそのメッセージを送信するためのポートも追加します。</span><span class="sxs-lookup"><span data-stu-id="7875b-148">We’ll also add a port to send that message to SQL Server.</span></span>  
  
#### <a name="to-update-the-orchestration"></a><span data-ttu-id="7875b-149">オーケストレーションを更新するには</span><span class="sxs-lookup"><span data-stu-id="7875b-149">To update the orchestration</span></span>  
  
1.  <span data-ttu-id="7875b-150">挿入スキーマのメッセージ変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="7875b-150">Create a message variable for the insert schema.</span></span> <span data-ttu-id="7875b-151">オーケストレーションの種類を右クリックし、**メッセージ**ノードをクリックして**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="7875b-151">From the orchestration view, right-click the **Messages** node, and then click **New Message**.</span></span> <span data-ttu-id="7875b-152">メッセージの名前を設定**InsertOrders**メッセージの種類と**BtsSalesforceIntegration.InsertOrdersTableOperation_dbo_OrderDetails.Insert**です。</span><span class="sxs-lookup"><span data-stu-id="7875b-152">Set the message name as **InsertOrders** and message type as **BtsSalesforceIntegration.InsertOrdersTableOperation_dbo_OrderDetails.Insert**.</span></span>  
  
2.  <span data-ttu-id="7875b-153">後のメッセージの構築図形を追加、 **ReceiveQueryResult**図形です。</span><span class="sxs-lookup"><span data-stu-id="7875b-153">Add a Construct Message shape after the **ReceiveQueryResult** shape.</span></span> <span data-ttu-id="7875b-154">図形の名前を設定`ConstructOrders`設定と、**構築メッセージ**プロパティを**InsertOrders**です。</span><span class="sxs-lookup"><span data-stu-id="7875b-154">Set the name of the shape to `ConstructOrders` and set the **Messages Constructed** property to **InsertOrders**.</span></span>  
  
3.  <span data-ttu-id="7875b-155">内で、 **ConstructOrders**図形を追加、**変換**図形です。</span><span class="sxs-lookup"><span data-stu-id="7875b-155">Within the **ConstructOrders** shape, add a **Transform** shape.</span></span> <span data-ttu-id="7875b-156">変換図形をダブルクリックして、[変換の構成] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="7875b-156">Double-click the Transform shape to open the Transform Configuration dialog box.</span></span> <span data-ttu-id="7875b-157">ダイアログ ボックスで、選択、**既存のマップ**オプション、し、ドロップダウン リストから選択**BtsSalesforceIntegration.QueryResult_Orders**です。</span><span class="sxs-lookup"><span data-stu-id="7875b-157">In the dialog box, select the **Existing Map** option, and then from the drop-down select **BtsSalesforceIntegration.QueryResult_Orders**.</span></span> <span data-ttu-id="7875b-158">設定**ソース**に**QueryResultMsg**、**先**に**InsertOrders**、順にクリック **[ok]** です。</span><span class="sxs-lookup"><span data-stu-id="7875b-158">Set **Source** to **QueryResultMsg**, **Destination** to **InsertOrders**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="7875b-159">後に、 **ConstructOrders**図形、送信図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="7875b-159">After the **ConstructOrders** shape, add a Send shape.</span></span> <span data-ttu-id="7875b-160">図形の名前は`SendOrders`としてメッセージの種類を設定および**InsertOrders**です。</span><span class="sxs-lookup"><span data-stu-id="7875b-160">Name the shape `SendOrders` and set the message type as **InsertOrders**.</span></span>  
  
5.  <span data-ttu-id="7875b-161">Salesforce に注文詳細を挿入するためのポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="7875b-161">Add a port to insert order details into Salesforce.</span></span> <span data-ttu-id="7875b-162">ポート構成ウィザードで、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7875b-162">In the Port Configuration wizard, select the following options:</span></span>  
  
    -   <span data-ttu-id="7875b-163">ポート名を指定`SendToSQL`です。</span><span class="sxs-lookup"><span data-stu-id="7875b-163">Specify the port name as `SendToSQL`.</span></span>  
  
    -   <span data-ttu-id="7875b-164">新しいポート種類を作成するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7875b-164">Select the option to create a new port type.</span></span>  
  
    -   <span data-ttu-id="7875b-165">設定**通信パターン**に*一方向*です。</span><span class="sxs-lookup"><span data-stu-id="7875b-165">Set **Communication Pattern** to *One-Way*.</span></span>  
  
    -   <span data-ttu-id="7875b-166">設定**ポートの通信方向**に*すればを常にメッセージを送信するこのポートで*設定と**ポートのバインド**に*後で、指定*です。</span><span class="sxs-lookup"><span data-stu-id="7875b-166">Set **Port direction of communication** to *I’ll always be sending messages on this port* and set **Port binding** to *Specify later*.</span></span>  
  
     <span data-ttu-id="7875b-167">接続、**要求**にポートの操作、 **SendOrders**送信図形をオーケストレーションを完了します。</span><span class="sxs-lookup"><span data-stu-id="7875b-167">Connect the **Request** operation of port to the **SendOrders** Send shape to complete the orchestration.</span></span> <span data-ttu-id="7875b-168">次のスクリーンショットは、完了したオーケストレーションをエンド ツー エンドで示します。</span><span class="sxs-lookup"><span data-stu-id="7875b-168">The following screenshot depicts the completed orchestration, end-to-end.</span></span>  
  
     <span data-ttu-id="7875b-169">![Salesforce の統合のオーケストレーションを完了する](../core/media/bts-sf-complete-orch.jpg "BTS_SF_Complete_Orch")</span><span class="sxs-lookup"><span data-stu-id="7875b-169">![Complete orchesration for Salesforce integration](../core/media/bts-sf-complete-orch.jpg "BTS_SF_Complete_Orch")</span></span>  
  
     <span data-ttu-id="7875b-170">厳密な名前のキー ファイルをプロジェクトに追加し、プロジェクトへの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="7875b-170">Add a strong name key file to the project and save changes to the project.</span></span>  
  
 <span data-ttu-id="7875b-171">このトピックの手順を使用し、Salesforce から営業案件通知を受信し、営業案件に関する詳細について Salesforce にクエリを送信し、クエリ応答を SQL Server データベースに挿入するためのオーケストレーションが完成しました。</span><span class="sxs-lookup"><span data-stu-id="7875b-171">With the steps in this topic, we have completed the orchestration, to receive an opportunity notification from Salesforce, query Salesforce for more details about the opportunity, and then insert the query response into a SQL Server database.</span></span> <span data-ttu-id="7875b-172">次のトピックでは、Salesforce で認証を行い、Salesforce 応答を BizTalk Server で処理するために使用するソリューションのその他の主要なコンポーネントのいくつかをビルドします。</span><span class="sxs-lookup"><span data-stu-id="7875b-172">In the subsequent topics, we’ll build some other key components of the solution that are used to authenticate with Salesforce and process Salesforce response within BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7875b-173">参照</span><span class="sxs-lookup"><span data-stu-id="7875b-173">See Also</span></span>  
 [<span data-ttu-id="7875b-174">手順 3: Visual Studio での BizTalk Server ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7875b-174">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)