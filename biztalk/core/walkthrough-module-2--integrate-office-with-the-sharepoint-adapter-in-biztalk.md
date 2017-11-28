---
title: "チュートリアル: モジュール 2 - Windows SharePoint と Office の統合サービスのアダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters, InfoPath forms
- InfoPath forms, creating
- InfoPath forms, Windows SharePoint Services adapters
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapter tutorials, integrating Microsoft Office
- Windows SharePoint Services, document libraries
ms.assetid: 2f81a712-bb20-4c32-bbac-fb438deded38
caps.latest.revision: "48"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64e23cef8b362accba726c60945548a3345c9c45
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-module-2---integrating-office-with-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="26a94-102">チュートリアル: モジュール 2 - Windows SharePoint Services アダプターと Office の統合</span><span class="sxs-lookup"><span data-stu-id="26a94-102">Walkthrough: Module 2 - Integrating Office with the Windows SharePoint Services Adapter</span></span>
<span data-ttu-id="26a94-103">このチュートリアルでは、継続の[チュートリアル: モジュール 1 - Windows SharePoint Services アダプターでメッセージを送受信する](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)Microsoft Office と統合する方法を説明し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンテンツ ベースルーティング (CBR) アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="26a94-103">This walkthrough is a continuation of [Walkthrough: Module 1 - Sending and Receiving Messages with the Windows SharePoint Services Adapter](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md) and shows you how to integrate Microsoft Office with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] content-based routing (CBR) application you created.</span></span> <span data-ttu-id="26a94-104">概要については、Windows SharePoint Services アダプターを参照してください。 [Windows SharePoint Services アダプターは何ですか。](../core/what-is-the-windows-sharepoint-services-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="26a94-104">For an introduction to the Windows SharePoint Services adapter see [What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="26a94-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="26a94-105">Prerequisites</span></span>  
 <span data-ttu-id="26a94-106">このトピックの手順を実行するための前提条件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="26a94-106">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="26a94-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が完全インストールされたシングル サーバー展開が必要です。</span><span class="sxs-lookup"><span data-stu-id="26a94-107">You must have a single-server deployment with a complete installation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="26a94-108">次のチュートリアルを完了する必要があります:[チュートリアル: モジュール 1 - Windows SharePoint Services アダプターでメッセージを送受信します。](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)</span><span class="sxs-lookup"><span data-stu-id="26a94-108">You must complete the following walkthrough: [Walkthrough: Module 1 - Sending and Receiving Messages with the Windows SharePoint Services Adapter](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)</span></span>  
  
 <span data-ttu-id="26a94-109">マルチ サーバー展開で Windows SharePoint Services アダプターを使用する方法については、次を参照してください。[の設定と Windows SharePoint Services アダプターを展開する](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="26a94-109">For information about using the Windows SharePoint Services Adapter in a multiserver deployment, see [Setting Up and Deploying the Windows SharePoint Services Adapter](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="create-a-biztalk-project"></a><span data-ttu-id="26a94-110">BizTalk プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="26a94-110">Create a BizTalk project</span></span>  
 <span data-ttu-id="26a94-111">ここでは、BizTalk エディターを使用して、空の BizTalk プロジェクトとスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="26a94-111">In this procedure you create an empty BizTalk project and a schema using the BizTalk Editor.</span></span> <span data-ttu-id="26a94-112">これは、後で使用する InfoPath フォームのスキーマを作成するために必要な手順です。</span><span class="sxs-lookup"><span data-stu-id="26a94-112">This procedure is required to create the schema for the InfoPath form that is used later.</span></span>  
  
#### <a name="create-a-strong-name-key-file"></a><span data-ttu-id="26a94-113">厳密な名前のキー ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="26a94-113">Create a strong name key file</span></span>  
  
1.  <span data-ttu-id="26a94-114">開始**Visual Studio コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-114">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="26a94-115">型`sn -k C:\WSSAdapterWalkthrough\OrderProcess.snk`、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-115">Type `sn -k C:\WSSAdapterWalkthrough\OrderProcess.snk`, and then press **Enter**.</span></span> <span data-ttu-id="26a94-116">キー ペアが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="26a94-116">The key pair will be written.</span></span>  
  
3.  <span data-ttu-id="26a94-117">コマンド プロンプトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="26a94-117">Close the command prompt.</span></span>  
  
#### <a name="create-an-empty-biztalk-project"></a><span data-ttu-id="26a94-118">空の BizTalk プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="26a94-118">Create an empty BizTalk project</span></span>  
  
1.  <span data-ttu-id="26a94-119">開始**Microsoft Visual Studio**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-119">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="26a94-120">をクリックして**ファイル**、**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-120">Click **File**, **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="26a94-121">**プロジェクトの種類** **BizTalk プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-121">Under **Project types**, select **BizTalk Projects**.</span></span>  
  
4.  <span data-ttu-id="26a94-122">**テンプレート****空の BizTalk Server プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-122">Under **Templates**, select **Empty BizTalk Server Project**.</span></span>  
  
5.  <span data-ttu-id="26a94-123">型`OrderProcess`で、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="26a94-123">Type `OrderProcess` in the **Name** field.</span></span>  
  
6.  <span data-ttu-id="26a94-124">内の作業ディレクトリへのファイル パスを入力、**場所**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="26a94-124">Type the file path to your working directory in the **Location** field.</span></span> <span data-ttu-id="26a94-125">たとえば、 `C:\WSSAdapterWalkthrough\`のようにします。</span><span class="sxs-lookup"><span data-stu-id="26a94-125">For example, `C:\WSSAdapterWalkthrough\`.</span></span>  
  
7.  <span data-ttu-id="26a94-126">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26a94-126">Click **OK**.</span></span>  
  
#### <a name="associate-the-key-file-with-the-assembly"></a><span data-ttu-id="26a94-127">アセンブリとキー ファイルの関連付け</span><span class="sxs-lookup"><span data-stu-id="26a94-127">Associate the key file with the assembly</span></span>  
  
1.  <span data-ttu-id="26a94-128">ソリューション エクスプ ローラーで右クリックし、`OrderProcess`プロジェクトをクリックして**プロパティ**プロジェクト デザイナーを起動します。</span><span class="sxs-lookup"><span data-stu-id="26a94-128">In Solution Explorer, right-click the `OrderProcess` project, and then click **Properties** to launch the Project Designer.</span></span>  
  
2.  <span data-ttu-id="26a94-129">**[署名]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="26a94-129">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="26a94-130">**[アセンブリの署名]** オプションを選択し、 **[厳密な名前のキー ファイルを選択してください]** オプションのドロップダウン リストをクリックして、 **[参照]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26a94-130">Select **Sign the assembly** option, click drop-down list for the **Choose a strong name key file** option, and then click **Browse**.</span></span>  
  
4.  <span data-ttu-id="26a94-131">「`C:\WSSAdapterWalkthrough\OrderProcess.snk`.</span><span class="sxs-lookup"><span data-stu-id="26a94-131">Type `C:\WSSAdapterWalkthrough\OrderProcess.snk`.</span></span>  
  
5.  <span data-ttu-id="26a94-132">**[開く]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26a94-132">Click **Open**.</span></span>  
  
#### <a name="create-an-xsd-schema-by-using-the-biztalk-editor"></a><span data-ttu-id="26a94-133">BizTalk エディタを使用した XSD スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="26a94-133">Create an XSD schema by using the BizTalk Editor</span></span>  
  
1.  <span data-ttu-id="26a94-134">ソリューション エクスプ ローラーで右クリックし、`OrderProcess`プロジェクトで、をクリックして**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="26a94-134">In Solution Explorer, right-click the `OrderProcess` project, click **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="26a94-135">**カテゴリ**をクリックして**スキーマ ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-135">Under **Categories**, click **Schema Files**.</span></span>  
  
3.  <span data-ttu-id="26a94-136">**テンプレート**をクリックして**スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-136">Under **Templates**, click **Schema**.</span></span>  
  
4.  <span data-ttu-id="26a94-137">型`OrderProcessSchema`で、**名前**フィールドをクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-137">Type `OrderProcessSchema` in the **Name** field, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="26a94-138">プロパティ ウィンドウで`OrderProcessSchema``Qualified`の**Element FormDefault**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="26a94-138">In the Properties Window for `OrderProcessSchema`, select `Qualified` for the **Element FormDefault** property.</span></span>  
  
6.  <span data-ttu-id="26a94-139">[プロパティ] ウィンドウで`OrderProcessSchema`、型`http://OrderProcess.PurchaseOrder`で、 **Target Namespace**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="26a94-139">In the Properties Window for `OrderProcessSchema`, type `http://OrderProcess.PurchaseOrder` in the **Target Namespace** field.</span></span>  
  
7.  <span data-ttu-id="26a94-140">**BizTalk エディター**を右クリックして`Root`をクリックして**の名前を変更**、し、入力`PurchaseOrder`です。</span><span class="sxs-lookup"><span data-stu-id="26a94-140">In the **BizTalk Editor**, right-click `Root`, click **Rename**, and then type `PurchaseOrder`.</span></span>  
  
8.  <span data-ttu-id="26a94-141">右クリックし、 **PurchaseOrder**ノード、をクリックして**スキーマ ノードの挿入**、順にクリックして**子フィールド要素**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-141">Right-click the **PurchaseOrder** node, click **Insert Schema Node**, then click **Child Field Element**.</span></span>  
  
9. <span data-ttu-id="26a94-142">「`PurchaseOrderID`」という名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="26a94-142">Name it `PurchaseOrderID`.</span></span>  
  
10. <span data-ttu-id="26a94-143">別の子フィールド要素を作成し、「`BillTo`」という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="26a94-143">Create another child field element and name it `BillTo`.</span></span>  
  
11. <span data-ttu-id="26a94-144">別の子フィールド要素を作成し、「`Amount`」という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="26a94-144">Create another child field element and name it `Amount`.</span></span>  
  
12. <span data-ttu-id="26a94-145">[プロパティ] ウィンドウで、設定、**データ型**プロパティを`Amount`を xs:unsignedInt にします。</span><span class="sxs-lookup"><span data-stu-id="26a94-145">In the Properties Window, set the **Data Type** property for `Amount` to xs:unsignedInt.</span></span>  
  
13. <span data-ttu-id="26a94-146">別の子フィールド要素を作成し、「`PurchaseOrderDate`」という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="26a94-146">Create another child field element and name it `PurchaseOrderDate`.</span></span>  
  
14. <span data-ttu-id="26a94-147">[プロパティ] ウィンドウで、設定、**データ型**プロパティを`PurchaseOrderDate`xs:dateTime にします。</span><span class="sxs-lookup"><span data-stu-id="26a94-147">In the Properties Window, set the **Data Type** property for `PurchaseOrderDate` to xs:dateTime.</span></span>  
  
15. <span data-ttu-id="26a94-148">をクリックして**ファイル**、クリックして**すべてを保存**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-148">Click **File**, and then click **Save All**.</span></span>  
  
16. <span data-ttu-id="26a94-149">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を終了します。</span><span class="sxs-lookup"><span data-stu-id="26a94-149">Close [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="create-an-infopath-form"></a><span data-ttu-id="26a94-150">InfoPath フォームの作成</span><span class="sxs-lookup"><span data-stu-id="26a94-150">Create an InfoPath form</span></span>  
 <span data-ttu-id="26a94-151">ここでは、既に作成したスキーマを基に、別のドキュメント ライブラリと InfoPath フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="26a94-151">In this procedure you create another document library and an InfoPath form based on the schema you created in the last procedure.</span></span> <span data-ttu-id="26a94-152">ドキュメントを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信するときは、この InfoPath フォームが使用されます。</span><span class="sxs-lookup"><span data-stu-id="26a94-152">This InfoPath form will be used to submit a document to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26a94-153">このチュートリアルでは Microsoft Office InfoPath 2007 が必要です</span><span class="sxs-lookup"><span data-stu-id="26a94-153">This walkthrough requires Microsoft Office InfoPath 2007</span></span>  
  
#### <a name="create-a-new-document-library"></a><span data-ttu-id="26a94-154">新しいドキュメント ライブラリの作成</span><span class="sxs-lookup"><span data-stu-id="26a94-154">Create a new document library</span></span>  
  
1.  <span data-ttu-id="26a94-155">Web ブラウザを開き、作成したサイトの URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="26a94-155">Open a Web browser and navigate to the URL of the site you created.</span></span> <span data-ttu-id="26a94-156">たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。</span><span class="sxs-lookup"><span data-stu-id="26a94-156">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2.  <span data-ttu-id="26a94-157">上部のナビゲーション バーで、をクリックして**作成**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-157">On the top navigation bar, click **Create**.</span></span>  
  
3.  <span data-ttu-id="26a94-158">**ドキュメント ライブラリ**をクリックして**ドキュメント ライブラリ**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-158">Under **Document Libraries**, click **Document Library**.</span></span>  
  
4.  <span data-ttu-id="26a94-159">**名前と説明**セクションで、入力`InfoPathSolutions`で、 **Name フィールド**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-159">In the **Name and Description** section, type `InfoPathSolutions` in the **Name field**.</span></span>  
  
5.  <span data-ttu-id="26a94-160">**ナビゲーション**セクションで、**はい**クイック起動バーにこのフォーム ライブラリを表示します。</span><span class="sxs-lookup"><span data-stu-id="26a94-160">In the **Navigation** section, select **Yes** to display this form library on the Quick Launch bar.</span></span>  
  
6.  <span data-ttu-id="26a94-161">**ドキュメント テンプレート**セクションで、`None`の**ドキュメント テンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-161">In the **Document Template** section, select `None` for the **Document Template**.</span></span>  
  
7.  <span data-ttu-id="26a94-162">**[作成]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26a94-162">Click **Create**.</span></span> <span data-ttu-id="26a94-163">作成した空のライブラリにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="26a94-163">You will be redirected to the empty library you just created.</span></span>  
  
8.  <span data-ttu-id="26a94-164">左側にある、をクリックして**設定の変更と列**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-164">On the left side, click **Modify Settings and Columns**.</span></span>  
  
9. <span data-ttu-id="26a94-165">**列**をクリックして**新しい列を追加**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-165">Under **Columns**, click **Add a New Column**.</span></span>  
  
10. <span data-ttu-id="26a94-166">**名前と種類**、型`Namespace`で、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="26a94-166">Under **Name and Type**, type `Namespace` in the **Name** field.</span></span>  
  
11. <span data-ttu-id="26a94-167">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26a94-167">Click **OK**.</span></span>  
  
12. <span data-ttu-id="26a94-168">`WSSAdapterWalkthrough` Web サイトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="26a94-168">Close the `WSSAdapterWalkthrough` Web site.</span></span>  
  
#### <a name="create-an-infopath-form-based-on-the-orderprocessschema-schema-file"></a><span data-ttu-id="26a94-169">OrderProcessSchema スキーマ ファイルを基にした InfoPath フォームの作成</span><span class="sxs-lookup"><span data-stu-id="26a94-169">Create an InfoPath form based on the OrderProcessSchema schema file</span></span>  
  
1.  <span data-ttu-id="26a94-170">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office**、順にクリック**Microsoft Office InfoPath 2007**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-170">Click **Start**, point to **All Programs**, point to **Microsoft Office**, and then click **Microsoft Office InfoPath 2007**.</span></span>  
  
2.  <span data-ttu-id="26a94-171">**フォームの入力**ダイアログ ボックスで、**フォームをデザインします。**</span><span class="sxs-lookup"><span data-stu-id="26a94-171">In the **Fill Out a Form** dialog box, select **Design a Form.**</span></span>  
  
3.  <span data-ttu-id="26a94-172">**フォームをデザイン**作業ウィンドウで、 **XML ドキュメントまたはスキーマから新規**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-172">In the **Design a Form** task pane, select **New from XML Document or Schema**.</span></span>  
  
4.  <span data-ttu-id="26a94-173">**データ ソース ウィザード**、 をクリックして**参照**最後の手順で作成したスキーマ ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="26a94-173">In the **Data Source Wizard**, click **Browse** and select the schema file you created in the last procedure.</span></span> <span data-ttu-id="26a94-174">たとえば、 `C:\WSSAdapterWalkthrough\OrderProcess\OrderProcess\OrderProcessSchema.xsd`のようにします。</span><span class="sxs-lookup"><span data-stu-id="26a94-174">For example, `C:\WSSAdapterWalkthrough\OrderProcess\OrderProcess\OrderProcessSchema.xsd`.</span></span>  
  
5.  <span data-ttu-id="26a94-175">**[次へ]**をクリックし、 **[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26a94-175">Click **Next**, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="26a94-176">**データ ソース**タスク ウィンドウで、右クリックし、 **PurchaseOrder**ノードをクリックして**コントロール付きセクション**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-176">In the **Data Source** task pane, right-click the **PurchaseOrder** node, and then click **Section with Controls**.</span></span> <span data-ttu-id="26a94-177">テンプレートにフォームが作成されます。</span><span class="sxs-lookup"><span data-stu-id="26a94-177">This will create the form on the template.</span></span>  
  
7.  <span data-ttu-id="26a94-178">をクリックして**ファイル**、 をクリックして**保存**、順にクリック**保存**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-178">Click **File**, click **Save**, and then click **Save**.</span></span>  
  
8.  <span data-ttu-id="26a94-179">**名前を付けて保存** ダイアログ ボックスで、「`PurchaseOrder.xsn`で、**ファイル名**フィールドをクリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-179">In the **Save As** dialog box, type `PurchaseOrder.xsn` in the **File name** field, and then click **Save**.</span></span>  
  
9. <span data-ttu-id="26a94-180">をクリックして**ファイル**、クリックして**発行**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-180">Click **File**, and then click **Publish**.</span></span>  
  
10. <span data-ttu-id="26a94-181">**発行ウィザード**、 をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-181">In the **Publishing Wizard**, click **Next**.</span></span>  
  
11. <span data-ttu-id="26a94-182">選択**Web サーバーに**、クリックして**[次へ]**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-182">Select **To a Web Server**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="26a94-183">パスとファイル名を入力、`InfoPathSolutions`ドキュメント ライブラリをクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-183">Type the path and filename to your `InfoPathSolutions` document library, and then click **Next**.</span></span> <span data-ttu-id="26a94-184">たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough/InfoPathSolutions/PurchaseOrder.xsn`のようにします。</span><span class="sxs-lookup"><span data-stu-id="26a94-184">For example, `http://<server_name>/sites/WSSAdapterWalkthrough/InfoPathSolutions/PurchaseOrder.xsn`.</span></span>  
  
13. <span data-ttu-id="26a94-185">をクリックして**完了**、順にクリック**閉じる**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-185">Click **Finish**, and then click **Close**.</span></span>  
  
14. <span data-ttu-id="26a94-186">Microsoft InfoPath を終了します。</span><span class="sxs-lookup"><span data-stu-id="26a94-186">Close Microsoft InfoPath.</span></span>  
  
## <a name="modify-the-sharepoint-document-libraries"></a><span data-ttu-id="26a94-187">SharePoint ドキュメント ライブラリの変更</span><span class="sxs-lookup"><span data-stu-id="26a94-187">Modify the SharePoint document libraries</span></span>  
 <span data-ttu-id="26a94-188">ここでは、PurchaseOrder.xsn ファイルの名前空間プロパティを更新し、アップロード先のドキュメント ライブラリを変更します。</span><span class="sxs-lookup"><span data-stu-id="26a94-188">In this procedure you will update the namespace property for the PurchaseOrder.xsn file and modify the Destination Document Library.</span></span> <span data-ttu-id="26a94-189">この名前空間は、コンテンツ ベースのルーティング シナリオで、パブリッシュされたドキュメントのサブスクライバーを特定するときに変数として使用されます。</span><span class="sxs-lookup"><span data-stu-id="26a94-189">This namespace is used as a variable when determining subscribers of published documents for content based routing scenarios.</span></span>  
  
#### <a name="update-the-namespace-for-purchaseorderxsn"></a><span data-ttu-id="26a94-190">PurchaseOrder.xsn の名前空間の更新</span><span class="sxs-lookup"><span data-stu-id="26a94-190">Update the namespace for PurchaseOrder.xsn</span></span>  
  
1.  <span data-ttu-id="26a94-191">Web ブラウザを開き、作成したサイトの URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="26a94-191">Open a Web browser and navigate to the URL of the site you created.</span></span> <span data-ttu-id="26a94-192">たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。</span><span class="sxs-lookup"><span data-stu-id="26a94-192">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2.  <span data-ttu-id="26a94-193">左側にある、下にある**ドキュメント**をクリックして`InfoPathSolutions`です。</span><span class="sxs-lookup"><span data-stu-id="26a94-193">On the left side, under **Documents**, click `InfoPathSolutions`.</span></span>  
  
3.  <span data-ttu-id="26a94-194">ポインターを合わせる`PurchaseOrder.xsn`、右クリックし、をクリックして**プロパティの編集**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-194">Move the pointer over `PurchaseOrder.xsn`, right-click it, and then click **Edit Properties**.</span></span>  
  
4.  <span data-ttu-id="26a94-195">型`http://OrderProcess.PurchaseOrder`で、 **Namespace**フィールドをクリックして**を保存して閉じます**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-195">Type `http://OrderProcess.PurchaseOrder` in the **Namespace** field, and then click **Save and Close**.</span></span>  
  
#### <a name="modify-the-destination-document-library"></a><span data-ttu-id="26a94-196">アップロード先のドキュメント ライブラリの変更</span><span class="sxs-lookup"><span data-stu-id="26a94-196">Modify the Destination document library</span></span>  
  
1.  <span data-ttu-id="26a94-197">上部のナビゲーション バーで、をクリックして**ドキュメントし、リスト**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-197">On the top navigation bar, click **Documents and Lists**.</span></span>  
  
2.  <span data-ttu-id="26a94-198">**ドキュメント ライブラリ**をクリックして**先**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-198">Under **Document Libraries**, click **Destination**.</span></span>  
  
3.  <span data-ttu-id="26a94-199">左側にある、をクリックして**設定の変更と列**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-199">On the left side, click **Modify Settings and Columns**.</span></span>  
  
4.  <span data-ttu-id="26a94-200">**列**をクリックして**新しい列の追加**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-200">Under **Columns**, click **Add New Column**.</span></span>  
  
5.  <span data-ttu-id="26a94-201">**名前と種類**、型`Partner Name`で、**列名**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="26a94-201">Under **Name and Type**, type `Partner Name` in the **Column name** field.</span></span>  
  
6.  <span data-ttu-id="26a94-202">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26a94-202">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="26a94-203">`WSSAdapterWalkthrough` Web サイトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="26a94-203">Close the `WSSAdapterWalkthrough` Web site.</span></span>  
  
## <a name="modify-the-send-port-from-walkthrough-1"></a><span data-ttu-id="26a94-204">チュートリアル 1 の送信ポートの変更</span><span class="sxs-lookup"><span data-stu-id="26a94-204">Modify the send port from walkthrough 1</span></span>  
 <span data-ttu-id="26a94-205">ここでは、チュートリアル 1 の送信ポートを変更します。</span><span class="sxs-lookup"><span data-stu-id="26a94-205">In this procedure you modify the send port from walkthrough 1.</span></span> <span data-ttu-id="26a94-206">このチュートリアルで処理したドキュメントを確実に送信ポートへとルーティングするために、この手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="26a94-206">This procedure is required to ensure that the document processed in this walkthrough is correctly routed to the send port.</span></span>  
  
#### <a name="modify-the-send-port"></a><span data-ttu-id="26a94-207">送信ポートの変更</span><span class="sxs-lookup"><span data-stu-id="26a94-207">Modify the send port</span></span>  
  
1.  <span data-ttu-id="26a94-208">開いている**BizTalk Server 管理します。**</span><span class="sxs-lookup"><span data-stu-id="26a94-208">Open **BizTalk Server Administration.**</span></span>  
  
2.  <span data-ttu-id="26a94-209">展開**Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、をクリックし、**送信ポート**ノード。</span><span class="sxs-lookup"><span data-stu-id="26a94-209">Expand **Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and then click the **Send Ports** node.</span></span>  
  
3.  <span data-ttu-id="26a94-210">右クリック`SendToDestination`、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-210">Right-click `SendToDestination`, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="26a94-211">**トランスポート**をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-211">Under **Transport**, click **Configure**.</span></span>  
  
5.  <span data-ttu-id="26a94-212">**Filename**フィールドに「`PurchaseOrder2-%XPATH=//pons:PurchaseOrder/pons:PurchaseOrderID%.xml`です。</span><span class="sxs-lookup"><span data-stu-id="26a94-212">In the **Filename** field, type `PurchaseOrder2-%XPATH=//pons:PurchaseOrder/pons:PurchaseOrderID%.xml`.</span></span>  
  
6.  <span data-ttu-id="26a94-213">**Namespace エイリアス**フィールドに「`pons="http://OrderProcess.PurchaseOrder"`です。</span><span class="sxs-lookup"><span data-stu-id="26a94-213">In the **Namespace Aliases** field, type `pons="http://OrderProcess.PurchaseOrder"`.</span></span>  
  
7.  <span data-ttu-id="26a94-214">**テンプレート ドキュメント ライブラリ**、型`InfoPathSolutions`です。</span><span class="sxs-lookup"><span data-stu-id="26a94-214">In the **Templates Document Library**, type `InfoPathSolutions`.</span></span>  
  
8.  <span data-ttu-id="26a94-215">**テンプレート Namespace 列**、型`Namespace`です。</span><span class="sxs-lookup"><span data-stu-id="26a94-215">In the **Templates Namespace Column**, type `Namespace`.</span></span>  
  
9. <span data-ttu-id="26a94-216">選択`Yes`の**Microsoft Office 統合**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="26a94-216">Select `Yes` for the **Microsoft Office Integration** property.</span></span>  
  
10. <span data-ttu-id="26a94-217">**Windows SharePoint Services 統合**、型`Partner Name`で、**列 01**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="26a94-217">Under **Windows SharePoint Services Integration**, type `Partner Name` in the **Column 01** field.</span></span>  
  
11. <span data-ttu-id="26a94-218">型`%XPATH=//pons:PurchaseOrder/pons:BillTo%`で、**列 01 の値**フィールドで、をクリックして**OK**、順にクリック**[ok]**を終了するには、もう一度、**送信ポートのプロパティ**ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="26a94-218">Type `%XPATH=//pons:PurchaseOrder/pons:BillTo%` in the **Column 01 Value** field, click **OK**, and then click **OK** again to exit the **Send Port Properties** dialog box.</span></span>  
  
#### <a name="restart-the-send-port"></a><span data-ttu-id="26a94-219">送信ポートを再起動します。</span><span class="sxs-lookup"><span data-stu-id="26a94-219">Restart the send port</span></span>  
  
1.  <span data-ttu-id="26a94-220">**BizTalk 管理コンソール**をクリックして、**送信ポート**ノード。</span><span class="sxs-lookup"><span data-stu-id="26a94-220">In the **BizTalk Administration Console**, click the **Send Ports** node.</span></span>  
  
2.  <span data-ttu-id="26a94-221">右クリック`SendToDestination`、クリックして**参加解除**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-221">Right-click `SendToDestination`, and then click **Unenlist**.</span></span>  
  
3.  <span data-ttu-id="26a94-222">右クリック`SendToDestination`、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-222">Right-click `SendToDestination`, and then click **Start**.</span></span>  
  
4.  <span data-ttu-id="26a94-223">閉じる、 **BizTalk 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-223">Close the **BizTalk Administration Console**.</span></span>  
  
## <a name="send-a-message-through-the-system"></a><span data-ttu-id="26a94-224">システムからのメッセージ送信</span><span class="sxs-lookup"><span data-stu-id="26a94-224">Send a message through the system</span></span>  
 <span data-ttu-id="26a94-225">ここでは、InfoPath フォームを作成し、Windows SharePoint Services Web サイトにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="26a94-225">In this procedure you create an InfoPath form and upload it to the Windows SharePoint Services Web site.</span></span> <span data-ttu-id="26a94-226">そのメッセージは Windows SharePoint Services アダプターによって取得され、アーカイブ ドキュメント ライブラリにアーカイブされた後、アップロード先のドキュメント ライブラリに送信されます。</span><span class="sxs-lookup"><span data-stu-id="26a94-226">The Windows SharePoint Services adapter will take that message, archive it in the Archive document library, and then send it to the Destination document library.</span></span> <span data-ttu-id="26a94-227">この手順は、Windows SharePoint Services アダプターを使用し、SharePoint Web サイトから、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を経由して SharePoint サービス Web サイトへと送信されるドキュメント フローを示しています。</span><span class="sxs-lookup"><span data-stu-id="26a94-227">This procedure demonstrates how a document flows from a Sharepoint web site, through [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and to a Sharepoint Services Web site using the Windows Sharepoint Services adapter.</span></span>  
  
#### <a name="create-an-infopath-form-to-send-through-the-system"></a><span data-ttu-id="26a94-228">システムから送信する InfoPath フォームの作成</span><span class="sxs-lookup"><span data-stu-id="26a94-228">Create an InfoPath form to send through the system</span></span>  
  
1.  <span data-ttu-id="26a94-229">Web ブラウザを開き、作成したサイトの URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="26a94-229">Open a Web browser and navigate to the URL of the site you created.</span></span> <span data-ttu-id="26a94-230">たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。</span><span class="sxs-lookup"><span data-stu-id="26a94-230">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2.  <span data-ttu-id="26a94-231">左側にある、下にある**ドキュメント**をクリックして`InfoPathSolutions`です。</span><span class="sxs-lookup"><span data-stu-id="26a94-231">On the left side, under **Documents**, click `InfoPathSolutions`.</span></span>  
  
3.  <span data-ttu-id="26a94-232">クリックして、`PurchaseOrder`に表示されるファイル、**ファイルのダウンロード**クリックしてダイアログ ボックスで、**開く**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-232">Click the `PurchaseOrder` file to display the **File Download** dialog box, and then click **Open**.</span></span> <span data-ttu-id="26a94-233">フォームが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="26a94-233">InfoPath will load the form.</span></span>  
  
4.  <span data-ttu-id="26a94-234">**Purchase Order ID**フィールドに「`1002`です。</span><span class="sxs-lookup"><span data-stu-id="26a94-234">In the **Purchase Order ID** field, type `1002`.</span></span>  
  
5.  <span data-ttu-id="26a94-235">**請求先**フィールドに「`John Doe`です。</span><span class="sxs-lookup"><span data-stu-id="26a94-235">In the **Bill To** field, type `John Doe`.</span></span>  
  
6.  <span data-ttu-id="26a94-236">**量**フィールドに「`750`です。</span><span class="sxs-lookup"><span data-stu-id="26a94-236">In the **Amount** field, type `750`.</span></span>  
  
7.  <span data-ttu-id="26a94-237">**Purchase Order Date**フィールドに「`1/2/2005`です。</span><span class="sxs-lookup"><span data-stu-id="26a94-237">In the **Purchase Order Date** field, type `1/2/2005`.</span></span>  
  
8.  <span data-ttu-id="26a94-238">**[保存]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26a94-238">Click **Save**.</span></span>  
  
9. <span data-ttu-id="26a94-239">**名前を付けて保存** ダイアログ ボックスで、「`http://<server_name>/sites/WSSAdapterWalkthrough/Source`で、**ファイル名**フィールド、および enter キー押しです。</span><span class="sxs-lookup"><span data-stu-id="26a94-239">In the **Save As** dialog box, type `http://<server_name>/sites/WSSAdapterWalkthrough/Source`in the **file name** field, and then hit Enter.</span></span>  
  
10. <span data-ttu-id="26a94-240">型`PurchaseOrder2.xml`で、**ファイル名**フィールドをクリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-240">Type `PurchaseOrder2.xml` in the **file name** field, and then click **Save**.</span></span>  
  
11. <span data-ttu-id="26a94-241">Microsoft Office InfoPath を終了します。</span><span class="sxs-lookup"><span data-stu-id="26a94-241">Close Microsoft Office InfoPath.</span></span>  
  
12. <span data-ttu-id="26a94-242">上部のナビゲーション バーで、Web ブラウザーでをクリックして**ドキュメントし、リスト**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-242">In the Web browser, on the top navigation bar, click **Documents and Lists**.</span></span>  
  
13. <span data-ttu-id="26a94-243">**ドキュメント ライブラリ**をクリックして**先**です。</span><span class="sxs-lookup"><span data-stu-id="26a94-243">Under **Document Libraries**, click **Destination**.</span></span>  
  
14. <span data-ttu-id="26a94-244">アップロード先のドキュメント ライブラリには、メッセージの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="26a94-244">In the Destination document library, you will now see your message listed.</span></span> <span data-ttu-id="26a94-245">アーカイブ ドキュメント ライブラリにアーカイブされたコピーも紹介します。</span><span class="sxs-lookup"><span data-stu-id="26a94-245">You will also find a copy archived in the Archive document library.</span></span>  
  
15. <span data-ttu-id="26a94-246">[アップロード先のドキュメント ライブラリ] で `PurchaseOrder1.xml` をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26a94-246">In the Destination document library, click `PurchaseOrder1.xml`.</span></span> <span data-ttu-id="26a94-247">この XML ファイルは Microsoft Internet Explorer で開かれます。</span><span class="sxs-lookup"><span data-stu-id="26a94-247">Note that this XML file is opened in Microsoft Internet Explorer.</span></span>  
  
16. <span data-ttu-id="26a94-248">[アップロード先のドキュメント ライブラリ] で `PurchaseOrder2.xml` をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26a94-248">In the Destination document library, click `PurchaseOrder2.xml`.</span></span> <span data-ttu-id="26a94-249">この XML ファイルは Microsoft Office InfoPath で開かれます。</span><span class="sxs-lookup"><span data-stu-id="26a94-249">Note that this XML file is opened in Microsoft Office InfoPath.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26a94-250">アップロード先のドキュメント ライブラリでは、PurchaseOrderID フィールドの値がファイル名列に、BillTo フィールドの値がパートナー名列に格納されます。</span><span class="sxs-lookup"><span data-stu-id="26a94-250">In the Destination document library, the file name column should contain the value of the PurchaseOrderID field and the Partner Name column should contain the value of the BillTo field.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="26a94-251">概要</span><span class="sxs-lookup"><span data-stu-id="26a94-251">Summary</span></span>  
 <span data-ttu-id="26a94-252">このチュートリアルでは、Windows SharePoint Services アダプターとコンテンツ ベースのルーティング (CBR) を使用して、Microsoft Office InfoPath とのより緊密な統合を実現する方法を確認しました。</span><span class="sxs-lookup"><span data-stu-id="26a94-252">In this walkthrough you have seen how to add tighter integration with Microsoft InfoPath using the Windows SharePoint Services Adapter and content-based routing (CBR).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="26a94-253">次の手順</span><span class="sxs-lookup"><span data-stu-id="26a94-253">Next Steps</span></span>  
 <span data-ttu-id="26a94-254">これで、このチュートリアルを完了すると、実行、[チュートリアル: モジュール 3 - オーケストレーションからの SharePoint プロパティへのアクセス](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md)このチュートリアルを完了したら作業にまで拡張できるチュートリアルの統合、プロジェクトに、オーケストレーション内から SharePoint プロパティにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="26a94-254">Now that you have completed this walkthrough, perform the [Walkthrough: Module 3 - Accessing SharePoint Properties from an Orchestration](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md) walkthrough which expands on the work you have done with this walkthrough, integrates an orchestration into the project, and shows you how to access SharePoint properties from within it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26a94-255">参照</span><span class="sxs-lookup"><span data-stu-id="26a94-255">See Also</span></span>  
 <span data-ttu-id="26a94-256">[Windows SharePoint Services アダプターとは何ですか。](../core/what-is-the-windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="26a94-256">[What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md) </span></span>  
 [<span data-ttu-id="26a94-257">Windows SharePoint Services アダプタのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="26a94-257">Windows SharePoint Services Adapter Walkthroughs</span></span>](../core/windows-sharepoint-services-adapter-walkthroughs.md)