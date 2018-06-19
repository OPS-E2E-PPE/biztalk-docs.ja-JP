---
title: '手順 2: Siebel ビジネス コンポーネント操作用のアプリケーション定義ファイルの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75d34c48-0f2a-42e4-a60b-e04bcf2404e1
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bd1eaac434f4fc6bda55f6ab290740147d91997
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22227034"
---
# <a name="step-2-create-an-application-definition-file-for-siebel-business-component-operations"></a><span data-ttu-id="29c1d-102">手順 2: Siebel ビジネス コンポーネント操作用のアプリケーション定義ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-102">Step 2: Create an Application Definition File for Siebel Business Component Operations</span></span>
<span data-ttu-id="29c1d-103">![手順 4 2](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="29c1d-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="29c1d-104">**所要時間:** 15 分</span><span class="sxs-lookup"><span data-stu-id="29c1d-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="29c1d-105">**目標:** ビジネス データ カタログを公開し、ポータルに基幹業務 (LOB) アプリケーションからのデータが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="29c1d-105">**Objective:** The Business Data Catalog exposes and incorporates data from line-of-business (LOB) applications into portals.</span></span> <span data-ttu-id="29c1d-106">ポータル サイトにこのデータを組み込むには、Microsoft Office SharePoint Server を使用できるアプリケーション定義ファイルをビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29c1d-106">To incorporate this data into your portal site, you must build an application definition file that Microsoft Office SharePoint Server can consume.</span></span>  
  
 <span data-ttu-id="29c1d-107">ビジネス データ カタログ定義エディター ツールでは、ビジネス データ カタログのアプリケーション定義ファイルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="29c1d-107">The Business Data Catalog Definition Editor tool enables you to create an application definition file for the Business Data Catalog.</span></span> <span data-ttu-id="29c1d-108">このツールには、XML 定義ファイルを自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="29c1d-108">This tool automatically generates the XML for the definition file.</span></span> <span data-ttu-id="29c1d-109">そのため、手動でエディターを作成するファイル、XML ではありません。</span><span class="sxs-lookup"><span data-stu-id="29c1d-109">Therefore, you do not have to manually create the file in an XML editor.</span></span>  
  
 <span data-ttu-id="29c1d-110">作成している Microsoft Office SharePoint Server アプリケーションの目的は、レコードの一覧を取得するアカウントのビジネス コンポーネントでクエリ操作の実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-110">The purpose of the Microsoft Office SharePoint Server application that you are creating is to perform a Query operation on the Account business component to retrieve a list of records.</span></span> <span data-ttu-id="29c1d-111">これを実現するには、一連のビジネス データ カタログ定義エディターでのタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29c1d-111">To achieve this, you must complete a set of tasks in the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="29c1d-112">このトピックでは、これらのタスクを実行する方法についてを説明します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-112">This topic provides instructions on how to perform these tasks.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="29c1d-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="29c1d-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="29c1d-114">Microsoft Office SharePoint Server 2007 SDK の一部としてインストールされているビジネス データ カタログ定義エディターが必要です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-114">You must have the Business Data Catalog Definition Editor installed as part of the Microsoft Office SharePoint Server 2007 SDK.</span></span> <span data-ttu-id="29c1d-115">SDK をダウンロードする[http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130)です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-115">You can download the SDK from [http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130).</span></span>  
  
-   <span data-ttu-id="29c1d-116">公開した WCF サービス」の説明に従って[手順 1: WCF サービスとしての Siebel ビジネス コンポーネント操作の公開](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-116">You should have published the WCF service, as described in [Step 1: Publish the Siebel Business Component Operations as a WCF Service](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md).</span></span>  
  
## <a name="creating-an-application-definition-file"></a><span data-ttu-id="29c1d-117">アプリケーション定義ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-117">Creating an Application Definition File</span></span>  
 <span data-ttu-id="29c1d-118">このセクションでは、WCF サービスのアプリケーション定義ファイルを作成する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-118">This section provides step-by-step instructions to create an application definition file for the WCF service.</span></span>  
  
### <a name="connect-to-the-wcf-service-and-create-entities"></a><span data-ttu-id="29c1d-119">WCF サービスに接続し、エンティティの作成</span><span class="sxs-lookup"><span data-stu-id="29c1d-119">Connect to the WCF Service, and Create Entities</span></span>  
 <span data-ttu-id="29c1d-120">Web サービス記述言語 (WSDL) サービスを抽出する WCF サービスに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29c1d-120">You must connect to the WCF service to extract the Web Services Description Language (WSDL) for the service.</span></span> <span data-ttu-id="29c1d-121">ビジネス データ カタログ定義エディターは、WSDL からメソッドを抽出します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-121">From the WSDL, the Business Data Catalog Definition Editor extracts the methods.</span></span> <span data-ttu-id="29c1d-122">これらのメソッドは、エンティティの作成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="29c1d-122">These methods can be used to create entities.</span></span> <span data-ttu-id="29c1d-123">この例では、アカウントのビジネス コンポーネント上でクエリ操作の 1 つのエンティティを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29c1d-123">For this example, you must create one entity for the Query operation on the Account business component.</span></span>  
  
##### <a name="to-connect-to-the-wcf-service-and-create-entities"></a><span data-ttu-id="29c1d-124">WCF サービスに接続し、エンティティを作成するには</span><span class="sxs-lookup"><span data-stu-id="29c1d-124">To connect to the WCF service, and create entities</span></span>  
  
1.  <span data-ttu-id="29c1d-125">ビジネス データ カタログ定義エディターを起動します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-125">Start the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="29c1d-126">**開始** メニューのをクリックして**Microsoft ビジネス データ カタログ定義エディター**です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-126">On the **Start** menu, click **Microsoft Business Data Catalog Definition Editor**.</span></span>  
  
2.  <span data-ttu-id="29c1d-127">ツールでは、をクリックして**LOB システムの追加**です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-127">In the tool, click **Add LOB System**.</span></span>  
  
3.  <span data-ttu-id="29c1d-128">LOB システムの追加] ウィンドウで、[ **web サービスへの接続**です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-128">In the Add LOB System window, click **Connect to Webservice**.</span></span>  
  
4.  <span data-ttu-id="29c1d-129">[URL] ボックスには、WCF サービスの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-129">In the URL box, type the URL for the WCF service.</span></span> <span data-ttu-id="29c1d-130">URL は、次の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="29c1d-130">The URL must be in the following format:</span></span>  
  
    ```  
    https://<computer_name>/Siebel_Account/BusinessObjects_Account_Account_Operation.svc?wsdl  
    ```  
  
     <span data-ttu-id="29c1d-131">ここで、BusinessObjects_Account_Account_Operation.svc は、Siebel コントラクト用に作成されたサービス ファイルです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-131">where, BusinessObjects_Account_Account_Operation.svc is the service file created for the Siebel contract.</span></span>  
  
     <span data-ttu-id="29c1d-132">URL を入力する必要がありますが、WCF サービスが」の説明に従って、正常に発行されるかどうかをテストするときに使用可能な[手順 1: WCF サービスとしての Siebel ビジネス コンポーネント操作の公開](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-132">The URL that you must type is available when you test whether the WCF service is published successfully, as described in [Step 1: Publish the Siebel Business Component Operations as a WCF Service](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md).</span></span>  
  
5.  <span data-ttu-id="29c1d-133">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29c1d-133">Click **Connect**.</span></span>  
  
6.  <span data-ttu-id="29c1d-134">クリックして、 **Web メソッドの追加** タブに、WCF アダプター サービス開発ウィザードで選択した操作を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29c1d-134">Click the **Add Web Method** tab to see the operations you selected in the WCF Adapter Service Development Wizard.</span></span> <span data-ttu-id="29c1d-135">表示されます、**クエリ**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-135">You will see the **Query** method.</span></span>  
  
     <span data-ttu-id="29c1d-136">![BDC アプリケーションへの web メソッドの追加](../../adapters-and-accelerators/adapter-siebel/media/f9505cd3-67e3-4f99-b189-d010322a3137.gif "f9505cd3-67e3-4f99-b189-d010322a3137")</span><span class="sxs-lookup"><span data-stu-id="29c1d-136">![Add web methods to BDC application](../../adapters-and-accelerators/adapter-siebel/media/f9505cd3-67e3-4f99-b189-d010322a3137.gif "f9505cd3-67e3-4f99-b189-d010322a3137")</span></span>  
  
7.  <span data-ttu-id="29c1d-137">ドラッグ、**クエリ**メソッドをクリックしてデザイン サーフェイス**OK**です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-137">Drag the **Query** method to the design surface and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="29c1d-138">**LOB システムの名前を入力** ダイアログ ボックスに名前を入力、 **LOB システム名**ボックス。</span><span class="sxs-lookup"><span data-stu-id="29c1d-138">In the **Enter the name for the LOB System** dialog box, type a name in the **LOB System Name** box.</span></span> <span data-ttu-id="29c1d-139">この例では、「 `Siebel_Account`、クリックしてして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-139">For this example, type `Siebel_Account`, and then click **OK**.</span></span> <span data-ttu-id="29c1d-140">エンティティ、 **Entity0**、ビジネス データ カタログ定義エディターで作成します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-140">An entity, **Entity0**, is created in the Business Data Catalog Definition Editor.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="29c1d-141">ビジネス データ カタログ定義エディター ツールでは、列挙データ型は処理されません。</span><span class="sxs-lookup"><span data-stu-id="29c1d-141">The Business Data Catalog Definition Editor tool does not handle enumerated data types.</span></span> <span data-ttu-id="29c1d-142">そのため、ビジネス データ カタログ定義エディター ツールは、その列挙型を検出し、その他のフィールドを無視するまで、フィールドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="29c1d-142">So, the Business Data Catalog Definition Editor tool imports the fields till it encounters an enumerated data type and ignores the remaining fields.</span></span> <span data-ttu-id="29c1d-143">ビジネス データ カタログ定義エディター ツールでは、エラーも提供されます。</span><span class="sxs-lookup"><span data-stu-id="29c1d-143">The Business Data Catalog Definition Editor tool also gives an error.</span></span> <span data-ttu-id="29c1d-144">このエラーを無視し、[ok] をクリックして続行できます。</span><span class="sxs-lookup"><span data-stu-id="29c1d-144">You can ignore this error and proceed by clicking OK.</span></span> <span data-ttu-id="29c1d-145">後の段階で、アプリケーション定義ファイルで、必要なフィールドを手動で追加することができます。</span><span class="sxs-lookup"><span data-stu-id="29c1d-145">You can manually add the required fields in the application definition file at a later stage.</span></span>  
  
9. <span data-ttu-id="29c1d-146">複数のフレンドリ名を使用するエンティティの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-146">Change the entity names to use more friendly names.</span></span> <span data-ttu-id="29c1d-147">この例では、変更**Entity0**に**アカウント**です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-147">For this example, change **Entity0** to **Account**.</span></span>  
  
    1.  <span data-ttu-id="29c1d-148">展開、 **Siebel_Account**  ノードの順に展開し、**エンティティ**ノード。</span><span class="sxs-lookup"><span data-stu-id="29c1d-148">Expand the **Siebel_Account** node, and then expand the **Entities** node.</span></span>  
  
    2.  <span data-ttu-id="29c1d-149">選択、 **Entity0**ノード。</span><span class="sxs-lookup"><span data-stu-id="29c1d-149">Select the **Entity0** node.</span></span>  
  
    3.  <span data-ttu-id="29c1d-150">プロパティ ウィンドウで、次のように入力します。**アカウント**で、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-150">In the Properties pane, type **Account** in the **Name** field.</span></span>  
  
         <span data-ttu-id="29c1d-151">![エンティティの名前変更](../../adapters-and-accelerators/adapter-siebel/media/44eda1de-b348-4421-9c51-0355b51f4a90.gif "44eda1de-b348-4421-9c51-0355b51f4a90")</span><span class="sxs-lookup"><span data-stu-id="29c1d-151">![Rename the entity](../../adapters-and-accelerators/adapter-siebel/media/44eda1de-b348-4421-9c51-0355b51f4a90.gif "44eda1de-b348-4421-9c51-0355b51f4a90")</span></span>  
  
### <a name="specify-user-name-and-password-headers-for-methods"></a><span data-ttu-id="29c1d-152">メソッドのユーザー名とパスワードのヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-152">Specify User Name and Password Headers for Methods</span></span>  
 <span data-ttu-id="29c1d-153">ユーザー名とパスワードのヘッダーを指定したエンドポイント動作の構成の一部として、Siebel システムでを選択したビジネス コンポーネント操作のための WCF サービスを作成する場合 ([手順 1: Siebel ビジネス コンポーネント操作の公開WCF サービスとして](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md))。</span><span class="sxs-lookup"><span data-stu-id="29c1d-153">When creating a WCF service for the selected business component operations in the Siebel system, you specified user name and password headers as part of the endpoint behavior configuration ([Step 1: Publish the Siebel Business Component Operations as a WCF Service](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)).</span></span> <span data-ttu-id="29c1d-154">メソッドのプロパティの同じ値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29c1d-154">You must specify the same values for the method properties.</span></span>  
  
##### <a name="to-specify-user-name-and-password-headers-for-the-query-method"></a><span data-ttu-id="29c1d-155">クエリ メソッドのユーザー名とパスワードのヘッダーを指定するには</span><span class="sxs-lookup"><span data-stu-id="29c1d-155">To specify user name and password headers for the Query method</span></span>  
  
1.  <span data-ttu-id="29c1d-156">メタデータ オブジェクト ペインで、展開、**アカウント** ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="29c1d-156">In the Metadata Objects pane, expand the **Account** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="29c1d-157">クリックして、**クエリ**ノード、プロパティ ペインでに対して省略記号 (...) ボタンをクリックし、**プロパティ**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-157">Click the **Query** node, and in the Properties pane click the ellipsis (…) button against the **Properties** field.</span></span>  
  
3.  <span data-ttu-id="29c1d-158">PropertyView コレクション エディター] ダイアログ ボックスで、[**追加**、プロパティ ウィンドウで、次のように入力します。`HttpHeaderUserName`の、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-158">In the PropertyView Collection Editor dialog box, click **Add**, and in the Properties pane, type `HttpHeaderUserName` for the **Name** field.</span></span> <span data-ttu-id="29c1d-159">同様に、入力`MyUserHeader`の**PropertyValue**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-159">Similarly, type `MyUserHeader` for the **PropertyValue** field.</span></span> <span data-ttu-id="29c1d-160">選択**System.String**の**型**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-160">Select **System.String** for the **Type** field.</span></span>  
  
     <span data-ttu-id="29c1d-161">![プロパティを追加](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")</span><span class="sxs-lookup"><span data-stu-id="29c1d-161">![Add a property](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")</span></span>  
  
4.  <span data-ttu-id="29c1d-162">PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ウィンドウで、次のように入力します。`HttpHeaderPassword`の、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-162">In the PropertyView Collection Editor window, click **Add**, and in the Properties pane, type `HttpHeaderPassword` for the **Name** field.</span></span> <span data-ttu-id="29c1d-163">同様に、入力`MyPassHeader`の**PropertyValue**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-163">Similarly, type `MyPassHeader` for the **PropertyValue** field.</span></span> <span data-ttu-id="29c1d-164">選択**System.String**の**型**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-164">Select **System.String** for the **Type** field.</span></span>  
  
5.  <span data-ttu-id="29c1d-165">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29c1d-165">Click **OK**.</span></span>  
  
### <a name="set-up-single-sign-on-for-connecting-to-a-siebel-system"></a><span data-ttu-id="29c1d-166">Siebel システムに接続するためのシングル サインオンを設定します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-166">Set up Single Sign-On for Connecting to a Siebel System</span></span>  
 <span data-ttu-id="29c1d-167">このトピックのすべてのプロシージャの実行が完了したら後、は、アプリケーション定義、SharePoint アプリケーションにインポートできる XML が作成されます。</span><span class="sxs-lookup"><span data-stu-id="29c1d-167">After you have finished performing all the procedures in this topic, you will have created an application definition XML that can be imported into a SharePoint application.</span></span> <span data-ttu-id="29c1d-168">アプリケーションからは、Siebel システムの関連するデータを取得する (Web メソッドとして公開) Siebel ビジネス コンポーネント操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-168">From the application, you will invoke the Siebel business component operations (exposed as Web methods) to retrieve relevant data from the Siebel system.</span></span> <span data-ttu-id="29c1d-169">これを有効にするには、SharePoint アプリケーションで Siebel システムのユーザーとユーザー間のマッピングを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29c1d-169">To enable this, you must create a mapping between a user in the Siebel system and the user in the SharePoint application.</span></span> <span data-ttu-id="29c1d-170">アプリケーション定義の XML をインポートした後は、SharePoint サーバーの全体管理 Web サイトでこのマッピングを作成します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-170">You create this mapping in SharePoint Central Administration Web site after you have imported the application definition XML.</span></span>  
  
 <span data-ttu-id="29c1d-171">ただし、マッピングを作成する必要がありますプロパティを設定する**SecondarySsoApplicationId**ビジネス データ カタログ定義エディターにします。</span><span class="sxs-lookup"><span data-stu-id="29c1d-171">However, to create the mapping you must set a property **SecondarySsoApplicationId** in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-set-the-secondaryssoapplicationid-property"></a><span data-ttu-id="29c1d-172">SecondarySsoApplicationId のプロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="29c1d-172">To set the SecondarySsoApplicationId property</span></span>  
  
1.  <span data-ttu-id="29c1d-173">メタデータ オブジェクト ペインで、展開、 **Siebel_Account**  ノードの順に展開し、**インスタンス**ノード。</span><span class="sxs-lookup"><span data-stu-id="29c1d-173">In the Metadata Objects pane, expand the **Siebel_Account** node, and then expand the **Instances** node.</span></span>  
  
2.  <span data-ttu-id="29c1d-174">をクリックして**Siebel_Account_Instance**プロパティ ペインでに対して省略記号 (...) ボタンをクリックし、**プロパティ**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-174">Click **Siebel_Account_Instance** and in the Properties pane click the ellipsis (…) button against the **Properties** field.</span></span>  
  
3.  <span data-ttu-id="29c1d-175">PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ウィンドウで、次のように入力します。 **SecondarySsoApplicationId**の、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-175">In the PropertyView Collection Editor window, click **Add**, and in the Properties pane, type **SecondarySsoApplicationId** for the **Name** field.</span></span> <span data-ttu-id="29c1d-176">同様に、入力**SiebelSSO**の**PropertyValue**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-176">Similarly, type **SiebelSSO** for the **PropertyValue** field.</span></span> <span data-ttu-id="29c1d-177">選択**System.String**の**型**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-177">Select **System.String** for the **Type** field.</span></span>  
  
     <span data-ttu-id="29c1d-178">![SSO プロパティの追加](../../adapters-and-accelerators/adapter-siebel/media/59ce70eb-498f-406b-965d-c273c2d6ed14.gif "59ce70eb-498f-406b-965d-c273c2d6ed14")</span><span class="sxs-lookup"><span data-stu-id="29c1d-178">![Add the SSO property](../../adapters-and-accelerators/adapter-siebel/media/59ce70eb-498f-406b-965d-c273c2d6ed14.gif "59ce70eb-498f-406b-965d-c273c2d6ed14")</span></span>  
  
4.  <span data-ttu-id="29c1d-179">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29c1d-179">Click **OK**.</span></span>  
  
### <a name="requirement-perform-a-query-operation-on-the-account-business-component"></a><span data-ttu-id="29c1d-180">アカウントのビジネス コンポーネントでクエリ操作を実行する要件。</span><span class="sxs-lookup"><span data-stu-id="29c1d-180">Requirement: Perform a Query Operation on the Account Business Component</span></span>  
 <span data-ttu-id="29c1d-181">この例の最初の要件では、アカウントのビジネス コンポーネントでクエリ操作の実行に使用できるアプリケーション定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-181">The first requirement of this example is to create an application definition that can be used to perform a Query operation on the Account business component.</span></span> <span data-ttu-id="29c1d-182">この要件を達成するのには、次の一連のタスクを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="29c1d-182">To achieve this requirement, you must perform the following set of tasks:</span></span>  
  
-   <span data-ttu-id="29c1d-183">メソッドでは、クエリ、フィルターを作成して、クエリ操作が実行されるパラメーターにマップします。</span><span class="sxs-lookup"><span data-stu-id="29c1d-183">In the Query method, create a filter, and map it to the parameter on which the Query operation is performed.</span></span> <span data-ttu-id="29c1d-184">アカウント ビジネス コンポーネントを使用してクエリを実行は、 **SearchExpr**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="29c1d-184">For the Account business component, you will perform a query using the **SearchExpr** parameter.</span></span> <span data-ttu-id="29c1d-185">そのため、フィルターをマップする、 **SearchExpr**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="29c1d-185">So, you will map the filter to the **SearchExpr** parameter.</span></span>  
  
-   <span data-ttu-id="29c1d-186">クエリ メソッドの Finder メソッド インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-186">Create a Finder method instance for the Query method.</span></span> <span data-ttu-id="29c1d-187">Finder メソッドは、フィルターに基づくレコードの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-187">A Finder method retrieves a list of records based on a filter.</span></span>  
  
##### <a name="to-create-a-filter-and-map-it-to-the-searchexpr-parameter"></a><span data-ttu-id="29c1d-188">フィルターを作成して、SearchExpr パラメーターにマップするには</span><span class="sxs-lookup"><span data-stu-id="29c1d-188">To create a filter, and map it to the SearchExpr parameter</span></span>  
  
1.  <span data-ttu-id="29c1d-189">クエリ メソッドにフィルターを作成します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-189">Create a filter for the Query method.</span></span>  
  
    1.  <span data-ttu-id="29c1d-190">メタデータ オブジェクト ペインで、展開、**アカウント** ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="29c1d-190">In the Metadata Objects pane, expand the **Account** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="29c1d-191">クエリ メソッドを展開しを右クリックして**フィルター**、クリックして**フィルターの追加**です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-191">Expand the Query method, right-click **Filters**, and then click **Add Filter**.</span></span>  
  
         <span data-ttu-id="29c1d-192">![メソッドにフィルターを追加](../../adapters-and-accelerators/adapter-siebel/media/9cf7ccfd-6da0-44b7-b522-df327a74e7a2.gif "9cf7ccfd-6da0-44b7-b522-df327a74e7a2")</span><span class="sxs-lookup"><span data-stu-id="29c1d-192">![Add filter to a method](../../adapters-and-accelerators/adapter-siebel/media/9cf7ccfd-6da0-44b7-b522-df327a74e7a2.gif "9cf7ccfd-6da0-44b7-b522-df327a74e7a2")</span></span>  
  
    3.  <span data-ttu-id="29c1d-193">プロパティ ウィンドウで、次のように入力します。`SearchExpression`の、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-193">In the Properties pane, type `SearchExpression` for the **Name** field.</span></span>  
  
    4.  <span data-ttu-id="29c1d-194">**FilterType**プロパティで、 **Equals**です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-194">For the **FilterType** property, select **Equals**.</span></span>  
  
         <span data-ttu-id="29c1d-195">![フィルターの名前と種類の指定](../../adapters-and-accelerators/adapter-siebel/media/9faa18e1-4d27-4ee4-960a-458f978812a7.gif "9faa18e1-4d27-4ee4-960a-458f978812a7")</span><span class="sxs-lookup"><span data-stu-id="29c1d-195">![Specify a filter name and type](../../adapters-and-accelerators/adapter-siebel/media/9faa18e1-4d27-4ee4-960a-458f978812a7.gif "9faa18e1-4d27-4ee4-960a-458f978812a7")</span></span>  
  
2.  <span data-ttu-id="29c1d-196">マップをフィルター、 **SearchExpr**クエリ メソッドのパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-196">Map the filter to the **SearchExpr** parameter in the Query method.</span></span>  
  
    1.  <span data-ttu-id="29c1d-197">メタデータ オブジェクト ペインで、展開、**アカウント** ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="29c1d-197">In the Metadata Objects pane, expand the **Account** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="29c1d-198">クエリ メソッドを展開し、展開、**パラメーター**ノード。</span><span class="sxs-lookup"><span data-stu-id="29c1d-198">Expand the Query method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="29c1d-199">展開、 **AccountQueryInputRecord**ノード、2 番目の順に展開および**AccountQueryInputRecord**ノード。</span><span class="sxs-lookup"><span data-stu-id="29c1d-199">Expand the **AccountQueryInputRecord** node, and then expand the second **AccountQueryInputRecord** node.</span></span>  
  
    4.  <span data-ttu-id="29c1d-200">をクリックして、 **SearchExpr**ノードのプロパティ ウィンドウで選択および**SearchExpression**から、 **FilterDescriptor** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-200">Click the **SearchExpr** node and in the Properties pane, select **SearchExpression** from the **FilterDescriptor**list.</span></span>  
  
         <span data-ttu-id="29c1d-201">![フィルターにパラメーターをマップ](../../adapters-and-accelerators/adapter-siebel/media/199c8ba7-d0e8-4fb4-9d73-9cf548512498.gif "199c8ba7-d0e8-4fb4-9d73-9cf548512498")</span><span class="sxs-lookup"><span data-stu-id="29c1d-201">![Map a parameter to a filter](../../adapters-and-accelerators/adapter-siebel/media/199c8ba7-d0e8-4fb4-9d73-9cf548512498.gif "199c8ba7-d0e8-4fb4-9d73-9cf548512498")</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="29c1d-202">**AccountQueryInputRecord**も含まれています、 **QueryFields** 、ノードが含まれています、**項目**ノード。</span><span class="sxs-lookup"><span data-stu-id="29c1d-202">The **AccountQueryInputRecord** also contains a **QueryFields** node, which in turn contains an **Item** node.</span></span> <span data-ttu-id="29c1d-203">削除する必要があります、**項目**ノード、それ以外の場合、アカウントのビジネス コンポーネントでクエリ操作が得られない、目的の結果。</span><span class="sxs-lookup"><span data-stu-id="29c1d-203">You must delete the **Item** node, otherwise the Query operation on the Account business component might not give the desired results.</span></span> <span data-ttu-id="29c1d-204">削除する、**項目**ノード、ノードを右クリックし、**削除**です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-204">To delete the **Item** node, right-click the node, and then select **Delete**.</span></span>  
  
##### <a name="to-create-a-finder-method-instance-for-query-method"></a><span data-ttu-id="29c1d-205">クエリ メソッドの Finder メソッド インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="29c1d-205">To create a Finder method instance for Query method</span></span>  
  
1.  <span data-ttu-id="29c1d-206">メタデータ オブジェクト ペインで、展開、**アカウント** ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="29c1d-206">In the Metadata Objects pane, expand the **Account** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="29c1d-207">展開、**クエリ** ノードを右クリックして**インスタンス**、順にクリック**メソッド インスタンスの追加**メソッド インスタンスの作成 ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="29c1d-207">Expand the **Query** node, right-click **Instances**, and then click **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="29c1d-208">![Finder メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-siebel/media/c90e7784-4fb7-4eb5-baf5-efbefba4bb1f.gif "c90e7784-4fb7-4eb5-baf5-efbefba4bb1f")</span><span class="sxs-lookup"><span data-stu-id="29c1d-208">![Add a Finder method instance](../../adapters-and-accelerators/adapter-siebel/media/c90e7784-4fb7-4eb5-baf5-efbefba4bb1f.gif "c90e7784-4fb7-4eb5-baf5-efbefba4bb1f")</span></span>  
  
3.  <span data-ttu-id="29c1d-209">メソッド インスタンスの作成 ウィンドウで、をクリックして**Finder**の**メソッド インスタンスの型**です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-209">In the Create Method Instance window, click **Finder** for the **Method Instance Type**.</span></span>  
  
4.  <span data-ttu-id="29c1d-210">をクリックして**返す**から**戻り値の TypeDescriptor**セクションです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-210">Click **Return** from **Return TypeDescriptor** section.</span></span>  
  
     <span data-ttu-id="29c1d-211">![Finder メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-siebel/media/e8343988-d7c1-4b04-85b0-ca7d07097490.gif "e8343988-d7c1-4b04-85b0-ca7d07097490")</span><span class="sxs-lookup"><span data-stu-id="29c1d-211">![Add a Finder method instance](../../adapters-and-accelerators/adapter-siebel/media/e8343988-d7c1-4b04-85b0-ca7d07097490.gif "e8343988-d7c1-4b04-85b0-ca7d07097490")</span></span>  
  
5.  <span data-ttu-id="29c1d-212">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29c1d-212">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="29c1d-213">プロパティ ウィンドウで、次のように入力します。`QueryAccount`の、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-213">In the Properties pane, type `QueryAccount` for the **Name** field.</span></span>  
  
     <span data-ttu-id="29c1d-214">![メソッド インスタンスの名前を指定](../../adapters-and-accelerators/adapter-siebel/media/401223f3-806f-4010-8646-d5ac0c0e9f67.gif "401223f3-806f-4010-8646-d5ac0c0e9f67")</span><span class="sxs-lookup"><span data-stu-id="29c1d-214">![Specify a name for the method instance](../../adapters-and-accelerators/adapter-siebel/media/401223f3-806f-4010-8646-d5ac0c0e9f67.gif "401223f3-806f-4010-8646-d5ac0c0e9f67")</span></span>  
  
### <a name="remove-the-parameters-of-systemnullable-type"></a><span data-ttu-id="29c1d-215">'System.nullable(of 型のパラメーターを削除します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-215">Remove the Parameters of System.Nullable Type</span></span>  
 <span data-ttu-id="29c1d-216">クエリ関数の戻り値パラメーターは 'system.nullable(of 型のパラメーターを含めることがあります。</span><span class="sxs-lookup"><span data-stu-id="29c1d-216">The return parameters for Query function may contain parameters that are of System.Nullable type.</span></span> <span data-ttu-id="29c1d-217">アプリケーション定義でこれらのパラメーターが存在する、ため SharePoint ポータル上で Siebel データの表示中にエラーが発生した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="29c1d-217">Due to the presence of these parameters in the application definition, you might get an error while presenting Siebel data on a SharePoint portal.</span></span> <span data-ttu-id="29c1d-218">そのため、アプリケーションの定義から 'system.nullable(of 型のパラメーターを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29c1d-218">So, you must remove the parameters of System.Nullable type from the application definition.</span></span>  
  
 <span data-ttu-id="29c1d-219">また、'system.nullable(of 型の各パラメーターのビジネス データ カタログ定義エディターは System.Boolean 型の別のパラメーターを作成し、パラメーター名に"Specified"を追加します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-219">Also, for each parameter of System.Nullable type, the Business Data Catalog Definition Editor creates another parameter of System.Boolean type, and appends “Specified” to the parameter name.</span></span> <span data-ttu-id="29c1d-220">たとえば、パラメーター AccountRole は 'system.nullable(of 型です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-220">For example, the parameter AccountRole is of System.Nullable type.</span></span> <span data-ttu-id="29c1d-221">そのため、ビジネス データ カタログ定義エディターは、パラメーターの一覧に AccountRoleSpecified パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-221">So, the Business Data Catalog Definition Editor adds an AccountRoleSpecified parameter to the list of parameters.</span></span> <span data-ttu-id="29c1d-222">同様に、このようなパラメーターを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29c1d-222">You must remove such parameters as well.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29c1d-223">ビジネス データ カタログ定義エディターで、パラメーターを選択しの値を入力パラメーターを参照することができます、 **TypeName**プロパティ ペインでプロパティです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-223">You can see the parameter type by selecting the parameter in the Business Data Catalog Definition Editor, and looking at the value for the **TypeName** property in the Properties pane.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29c1d-224">アプリケーションに 'system.nullable(of 型のパラメーターが含まれていない場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="29c1d-224">You can skip this step if the application does not contain any parameters of System.Nullable type.</span></span>  
  
##### <a name="to-remove-the-parameters-of-systemnullable-type-for-the-query-method"></a><span data-ttu-id="29c1d-225">'System.nullable(of メソッドの型をクエリのパラメーターを削除する</span><span class="sxs-lookup"><span data-stu-id="29c1d-225">To remove the parameters of System.Nullable type for the Query method</span></span>  
  
1.  <span data-ttu-id="29c1d-226">メタデータ オブジェクト ペインで、展開、**アカウント** ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="29c1d-226">In the Metadata Objects pane, expand the **Account** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="29c1d-227">展開、**クエリ** ノードの順に展開し、**パラメーター**ノード。</span><span class="sxs-lookup"><span data-stu-id="29c1d-227">Expand the **Query** node, and then expand the **Parameters** node.</span></span>  
  
3.  <span data-ttu-id="29c1d-228">展開、**返す**ノード、2 番目の順に展開し、**返す**ノード。</span><span class="sxs-lookup"><span data-stu-id="29c1d-228">Expand the **Return** node, and then expand the second **Return** node.</span></span>  
  
4.  <span data-ttu-id="29c1d-229">クリックして、削除するパラメーターを右クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-229">Right-click the parameter you want to delete, and then select **Delete**.</span></span>  
  
5.  <span data-ttu-id="29c1d-230">ダイアログ ボックスで、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-230">In the dialog box, click **OK**.</span></span>  
  
### <a name="export-the-application-definition-to-a-file"></a><span data-ttu-id="29c1d-231">アプリケーション定義をファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="29c1d-231">Export the Application Definition to a File</span></span>  
 <span data-ttu-id="29c1d-232">Siebel システムのインスタンスのメタデータを含んでいるアプリケーション定義が作成されました。</span><span class="sxs-lookup"><span data-stu-id="29c1d-232">You have now created an application definition that contains the Siebel system instance metadata.</span></span> <span data-ttu-id="29c1d-233">Microsoft Office SharePoint Server にインポートできる XML ファイルにこの定義をエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29c1d-233">You must export this definition to an XML file, which can be imported into Microsoft Office SharePoint Server.</span></span>  
  
##### <a name="to-export-the-application-definition-to-a-file"></a><span data-ttu-id="29c1d-234">アプリケーション定義をファイルにエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="29c1d-234">To export the application definition to a file</span></span>  
  
1.  <span data-ttu-id="29c1d-235">右クリックし、 **Siebel_Account**ノードをクリックしてメタデータ オブジェクト ウィンドウで**エクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-235">Right-click the **Siebel_Account** node in the Metadata Objects pane, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="29c1d-236">Siebel_Account.xml としてファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-236">Save the file as Siebel_Account.xml.</span></span>  
  
### <a name="modify-the-application-definition-file-to-include-specific-parameters"></a><span data-ttu-id="29c1d-237">特定のパラメーターを含めるアプリケーション定義ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-237">Modify the Application Definition File to Include Specific Parameters</span></span>  
 <span data-ttu-id="29c1d-238">前述したこのトピックの前に、ビジネス データ カタログ定義エディター ツールは、列挙データ型を処理しません。</span><span class="sxs-lookup"><span data-stu-id="29c1d-238">As mentioned earlier in this topic, the Business Data Catalog Definition Editor tool does not handle enumerated data types.</span></span> <span data-ttu-id="29c1d-239">ビジネス データ カタログ定義エディター ツールは、その列挙型を検出し、その他のフィールドを無視するまでに、フィールドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="29c1d-239">The Business Data Catalog Definition Editor tool imports the fields till it encounters an enumerated data type and ignores the remaining fields.</span></span> <span data-ttu-id="29c1d-240">そのため、アプリケーションで使用する特定のフィールドを省略する場合があります。</span><span class="sxs-lookup"><span data-stu-id="29c1d-240">So, certain fields that you want in your application might be omitted.</span></span> <span data-ttu-id="29c1d-241">これらのフィールドを含めるアプリケーション定義ファイルを手動で編集することができます。</span><span class="sxs-lookup"><span data-stu-id="29c1d-241">You can manually edit the application definition file to include those fields.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29c1d-242">追加するパラメーターがの WCF アダプター サービス開発ウィザードによって生成された .cs ファイルに存在する必要があります[手順 1: WCF サービスとしての Siebel ビジネス コンポーネント操作の公開](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)です。</span><span class="sxs-lookup"><span data-stu-id="29c1d-242">You must make sure the parameters you are adding are present in the .cs file generated by the WCF Adapter Service Development Wizard in [Step 1: Publish the Siebel Business Component Operations as a WCF Service](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md).</span></span>  
  
 <span data-ttu-id="29c1d-243">このアプリケーション定義ファイルにする、追加または削除の戻り値パラメーター、 **QueryAccount**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-243">In this application definition file, you will add or remove return parameters for the **QueryAccount** method.</span></span>  
  
##### <a name="to-modify-the-application-definition-file"></a><span data-ttu-id="29c1d-244">アプリケーション定義ファイルを変更するには</span><span class="sxs-lookup"><span data-stu-id="29c1d-244">To modify the application definition file</span></span>  
  
1.  <span data-ttu-id="29c1d-245">使用して、Siebel_Account.xml、アプリケーション定義ファイルを開く[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]またはその他の任意のエディターです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-245">Open the application definition file, Siebel_Account.xml, by using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or any other editor.</span></span>  
  
2.  <span data-ttu-id="29c1d-246">パラメーターを置き換えるアプリケーション定義ファイルの変更、 **QueryAccount**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="29c1d-246">Modify the application definition file to replace the parameters for the **QueryAccount** method.</span></span>  
  
    1.  <span data-ttu-id="29c1d-247">アプリケーション定義ファイル内では、次を検索します。</span><span class="sxs-lookup"><span data-stu-id="29c1d-247">Within the application definition file, search for the following:</span></span>  
  
        ```  
        <TypeDescriptor TypeName="BDC.AccountQueryRecord,Siebel_Account" Name="Item">  
        ```  
  
    2.  <span data-ttu-id="29c1d-248">内で、`<TypeDescriptors>`タグ、既存の置換`<TypeDescriptor>`を次の要素。</span><span class="sxs-lookup"><span data-stu-id="29c1d-248">Within the `<TypeDescriptors>` tag, replace the existing `<TypeDescriptor>` elements with the following:</span></span>  
  
        ```  
  
        <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Id" />  
        <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Country" />  
        <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Name" />  
        <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Location" />  
        ```  
  
    3.  <span data-ttu-id="29c1d-249">ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="29c1d-249">Save and close the file.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="29c1d-250">新しく追加されたフィールドを表示するビジネス データ カタログ定義エディター ツールに戻り、更新されたアプリケーション定義ファイルをインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="29c1d-250">You can import the updated application definition file back in the Business Data Catalog Definition Editor tool to see the newly added fields.</span></span> <span data-ttu-id="29c1d-251">ただし、インポートする前に、ビジネス データ カタログ定義エディター ツールから既存の"Siebel_Account"アプリケーションを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29c1d-251">However, before importing you will have to remove the existing “Siebel_Account” application from the Business Data Catalog Definition Editor tool.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="29c1d-252">次の手順</span><span class="sxs-lookup"><span data-stu-id="29c1d-252">Next Steps</span></span>  
 <span data-ttu-id="29c1d-253">Siebel システムからデータを取得する SharePoint アプリケーションを作成する必要がありますようになりました。</span><span class="sxs-lookup"><span data-stu-id="29c1d-253">You must now create a SharePoint application to retrieve data from a Siebel system.</span></span> <span data-ttu-id="29c1d-254">参照してください[手順 3: Siebel からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)手順についてはします。</span><span class="sxs-lookup"><span data-stu-id="29c1d-254">See [Step 3: Create a SharePoint Application to Retrieve Data from Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md) for instructions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29c1d-255">参照</span><span class="sxs-lookup"><span data-stu-id="29c1d-255">See Also</span></span>  
 [<span data-ttu-id="29c1d-256">チュートリアル 1: SharePoint サイト上の Siebel システムからのデータの表示</span><span class="sxs-lookup"><span data-stu-id="29c1d-256">Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)