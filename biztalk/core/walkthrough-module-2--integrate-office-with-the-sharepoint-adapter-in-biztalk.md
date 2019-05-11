---
title: 'チュートリアル: モジュール 2 - Office の統合、Windows sharepoint Services アダプター |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters, InfoPath forms
- InfoPath forms, creating
- InfoPath forms, Windows SharePoint Services adapters
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapter tutorials, integrating Microsoft Office
- Windows SharePoint Services, document libraries
ms.assetid: 2f81a712-bb20-4c32-bbac-fb438deded38
caps.latest.revision: 48
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72496ab6b61de15cba1eee201b9a9dfb058810b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395318"
---
# <a name="walkthrough-module-2---integrating-office-with-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="04182-102">チュートリアル: モジュール 2 - Windows SharePoint Services アダプターと Office の統合</span><span class="sxs-lookup"><span data-stu-id="04182-102">Walkthrough: Module 2 - Integrating Office with the Windows SharePoint Services Adapter</span></span>
<span data-ttu-id="04182-103">このチュートリアルの続きでは、[チュートリアル。モジュール 1 - Windows SharePoint Services アダプターでメッセージを送受信する](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)Microsoft Office と統合する方法と、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンテンツ ベース ルーティング (CBR) アプリケーションを使用する作成しました。</span><span class="sxs-lookup"><span data-stu-id="04182-103">This walkthrough is a continuation of [Walkthrough: Module 1 - Sending and Receiving Messages with the Windows SharePoint Services Adapter](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md) and shows you how to integrate Microsoft Office with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] content-based routing (CBR) application you created.</span></span> <span data-ttu-id="04182-104">Windows SharePoint Services アダプターの概要についてを参照してください。 [、Windows SharePoint Services アダプターとは何ですか?](../core/what-is-the-windows-sharepoint-services-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="04182-104">For an introduction to the Windows SharePoint Services adapter see [What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="04182-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="04182-105">Prerequisites</span></span>  
 <span data-ttu-id="04182-106">このトピックの手順を実行するための前提条件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="04182-106">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
- <span data-ttu-id="04182-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が完全インストールされたシングル サーバー展開が必要です。</span><span class="sxs-lookup"><span data-stu-id="04182-107">You must have a single-server deployment with a complete installation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="04182-108">次のチュートリアルを完了する必要があります。[チュートリアル: モジュール 1 - Windows SharePoint Services アダプターでメッセージを送受信します。](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)</span><span class="sxs-lookup"><span data-stu-id="04182-108">You must complete the following walkthrough: [Walkthrough: Module 1 - Sending and Receiving Messages with the Windows SharePoint Services Adapter](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)</span></span>  
  
  <span data-ttu-id="04182-109">マルチ サーバー展開で、Windows SharePoint Services アダプターを使用する方法の詳細については、次を参照してください。[設定と、Windows SharePoint Services アダプターを展開する](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="04182-109">For information about using the Windows SharePoint Services Adapter in a multiserver deployment, see [Setting Up and Deploying the Windows SharePoint Services Adapter](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="create-a-biztalk-project"></a><span data-ttu-id="04182-110">BizTalk プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="04182-110">Create a BizTalk project</span></span>  
 <span data-ttu-id="04182-111">ここでは、BizTalk エディターを使用して、空の BizTalk プロジェクトとスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="04182-111">In this procedure you create an empty BizTalk project and a schema using the BizTalk Editor.</span></span> <span data-ttu-id="04182-112">これは、後で使用する InfoPath フォームのスキーマを作成するために必要な手順です。</span><span class="sxs-lookup"><span data-stu-id="04182-112">This procedure is required to create the schema for the InfoPath form that is used later.</span></span>  
  
#### <a name="create-a-strong-name-key-file"></a><span data-ttu-id="04182-113">厳密な名前のキー ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="04182-113">Create a strong name key file</span></span>  
  
1.  <span data-ttu-id="04182-114">開始**Visual Studio コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="04182-114">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="04182-115">型`sn -k C:\WSSAdapterWalkthrough\OrderProcess.snk`、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="04182-115">Type `sn -k C:\WSSAdapterWalkthrough\OrderProcess.snk`, and then press **Enter**.</span></span> <span data-ttu-id="04182-116">キー ペアが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="04182-116">The key pair will be written.</span></span>  
  
3.  <span data-ttu-id="04182-117">コマンド プロンプトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="04182-117">Close the command prompt.</span></span>  
  
#### <a name="create-an-empty-biztalk-project"></a><span data-ttu-id="04182-118">空の BizTalk プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="04182-118">Create an empty BizTalk project</span></span>  
  
1.  <span data-ttu-id="04182-119">開始**Microsoft Visual Studio**します。</span><span class="sxs-lookup"><span data-stu-id="04182-119">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="04182-120">クリックして**ファイル**、**新規**、 をクリックし、**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="04182-120">Click **File**, **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="04182-121">**プロジェクトの種類**、 **BizTalk プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="04182-121">Under **Project types**, select **BizTalk Projects**.</span></span>  
  
4.  <span data-ttu-id="04182-122">**テンプレート**、**空の BizTalk Server プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="04182-122">Under **Templates**, select **Empty BizTalk Server Project**.</span></span>  
  
5.  <span data-ttu-id="04182-123">型`OrderProcess`で、**名前**フィールド。</span><span class="sxs-lookup"><span data-stu-id="04182-123">Type `OrderProcess` in the **Name** field.</span></span>  
  
6.  <span data-ttu-id="04182-124">作業ディレクトリにファイル パスを入力、**場所**フィールド。</span><span class="sxs-lookup"><span data-stu-id="04182-124">Type the file path to your working directory in the **Location** field.</span></span> <span data-ttu-id="04182-125">たとえば、 `C:\WSSAdapterWalkthrough\`のようにします。</span><span class="sxs-lookup"><span data-stu-id="04182-125">For example, `C:\WSSAdapterWalkthrough\`.</span></span>  
  
7.  <span data-ttu-id="04182-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04182-126">Click **OK**.</span></span>  
  
#### <a name="associate-the-key-file-with-the-assembly"></a><span data-ttu-id="04182-127">アセンブリとキー ファイルの関連付け</span><span class="sxs-lookup"><span data-stu-id="04182-127">Associate the key file with the assembly</span></span>  
  
1.  <span data-ttu-id="04182-128">ソリューション エクスプ ローラーで右クリックし、`OrderProcess`プロジェクトをクリックして**プロパティ**プロジェクト デザイナーを起動します。</span><span class="sxs-lookup"><span data-stu-id="04182-128">In Solution Explorer, right-click the `OrderProcess` project, and then click **Properties** to launch the Project Designer.</span></span>  
  
2.  <span data-ttu-id="04182-129">**[署名]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="04182-129">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="04182-130">**[アセンブリの署名]** オプションを選択し、 **[厳密な名前のキー ファイルを選択してください]** オプションのドロップダウン リストをクリックして、 **[参照]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04182-130">Select **Sign the assembly** option, click drop-down list for the **Choose a strong name key file** option, and then click **Browse**.</span></span>  
  
4.  <span data-ttu-id="04182-131">「`C:\WSSAdapterWalkthrough\OrderProcess.snk`.</span><span class="sxs-lookup"><span data-stu-id="04182-131">Type `C:\WSSAdapterWalkthrough\OrderProcess.snk`.</span></span>  
  
5.  <span data-ttu-id="04182-132">**[開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04182-132">Click **Open**.</span></span>  
  
#### <a name="create-an-xsd-schema-by-using-the-biztalk-editor"></a><span data-ttu-id="04182-133">BizTalk エディタを使用した XSD スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="04182-133">Create an XSD schema by using the BizTalk Editor</span></span>  
  
1. <span data-ttu-id="04182-134">ソリューション エクスプ ローラーで右クリックし、`OrderProcess`プロジェクトで、をクリックして**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="04182-134">In Solution Explorer, right-click the `OrderProcess` project, click **Add**, and then click **New Item**.</span></span>  
  
2. <span data-ttu-id="04182-135">[**カテゴリ**、] をクリックして**スキーマ ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="04182-135">Under **Categories**, click **Schema Files**.</span></span>  
  
3. <span data-ttu-id="04182-136">[**テンプレート**、] をクリックして**スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="04182-136">Under **Templates**, click **Schema**.</span></span>  
  
4. <span data-ttu-id="04182-137">型`OrderProcessSchema`で、**名前**フィールドをクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="04182-137">Type `OrderProcessSchema` in the **Name** field, and then click **Add**.</span></span>  
  
5. <span data-ttu-id="04182-138">[プロパティ] ウィンドウで`OrderProcessSchema`、`Qualified`の**Element FormDefault**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="04182-138">In the Properties Window for `OrderProcessSchema`, select `Qualified` for the **Element FormDefault** property.</span></span>  
  
6. <span data-ttu-id="04182-139">[プロパティ] ウィンドウで`OrderProcessSchema`、型`http://OrderProcess.PurchaseOrder`で、 **Target Namespace**フィールド。</span><span class="sxs-lookup"><span data-stu-id="04182-139">In the Properties Window for `OrderProcessSchema`, type `http://OrderProcess.PurchaseOrder` in the **Target Namespace** field.</span></span>  
  
7. <span data-ttu-id="04182-140">**BizTalk エディター**、右クリックして`Root`、 をクリックして**の名前を変更**、し、入力`PurchaseOrder`します。</span><span class="sxs-lookup"><span data-stu-id="04182-140">In the **BizTalk Editor**, right-click `Root`, click **Rename**, and then type `PurchaseOrder`.</span></span>  
  
8. <span data-ttu-id="04182-141">右クリックし、 **PurchaseOrder**ノード、をクリックして**スキーマ ノードの挿入**、 をクリックし、**子フィールド要素**。</span><span class="sxs-lookup"><span data-stu-id="04182-141">Right-click the **PurchaseOrder** node, click **Insert Schema Node**, then click **Child Field Element**.</span></span>  
  
9. <span data-ttu-id="04182-142">「`PurchaseOrderID`」という名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="04182-142">Name it `PurchaseOrderID`.</span></span>  
  
10. <span data-ttu-id="04182-143">別の子フィールド要素を作成し、「`BillTo`」という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="04182-143">Create another child field element and name it `BillTo`.</span></span>  
  
11. <span data-ttu-id="04182-144">別の子フィールド要素を作成し、「`Amount`」という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="04182-144">Create another child field element and name it `Amount`.</span></span>  
  
12. <span data-ttu-id="04182-145">[プロパティ] ウィンドウで次のように設定します。、**データ型**プロパティ`Amount`[xs:unsignedint] にします。</span><span class="sxs-lookup"><span data-stu-id="04182-145">In the Properties Window, set the **Data Type** property for `Amount` to xs:unsignedInt.</span></span>  
  
13. <span data-ttu-id="04182-146">別の子フィールド要素を作成し、「`PurchaseOrderDate`」という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="04182-146">Create another child field element and name it `PurchaseOrderDate`.</span></span>  
  
14. <span data-ttu-id="04182-147">[プロパティ] ウィンドウで次のように設定します。、**データ型**プロパティ`PurchaseOrderDate`xs:dateTime にします。</span><span class="sxs-lookup"><span data-stu-id="04182-147">In the Properties Window, set the **Data Type** property for `PurchaseOrderDate` to xs:dateTime.</span></span>  
  
15. <span data-ttu-id="04182-148">をクリックして**ファイル**、クリックして**すべてを保存**です。</span><span class="sxs-lookup"><span data-stu-id="04182-148">Click **File**, and then click **Save All**.</span></span>  
  
16. <span data-ttu-id="04182-149">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を終了します。</span><span class="sxs-lookup"><span data-stu-id="04182-149">Close [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="create-an-infopath-form"></a><span data-ttu-id="04182-150">InfoPath フォームの作成</span><span class="sxs-lookup"><span data-stu-id="04182-150">Create an InfoPath form</span></span>  
 <span data-ttu-id="04182-151">ここでは、既に作成したスキーマを基に、別のドキュメント ライブラリと InfoPath フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="04182-151">In this procedure you create another document library and an InfoPath form based on the schema you created in the last procedure.</span></span> <span data-ttu-id="04182-152">ドキュメントを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信するときは、この InfoPath フォームが使用されます。</span><span class="sxs-lookup"><span data-stu-id="04182-152">This InfoPath form will be used to submit a document to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04182-153">このチュートリアルでは Microsoft Office InfoPath 2007 が必要です</span><span class="sxs-lookup"><span data-stu-id="04182-153">This walkthrough requires Microsoft Office InfoPath 2007</span></span>  
  
#### <a name="create-a-new-document-library"></a><span data-ttu-id="04182-154">新しいドキュメント ライブラリの作成</span><span class="sxs-lookup"><span data-stu-id="04182-154">Create a new document library</span></span>  
  
1.  <span data-ttu-id="04182-155">Web ブラウザを開き、作成したサイトの URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="04182-155">Open a Web browser and navigate to the URL of the site you created.</span></span> <span data-ttu-id="04182-156">たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。</span><span class="sxs-lookup"><span data-stu-id="04182-156">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2.  <span data-ttu-id="04182-157">上部のナビゲーション バーでクリックして**作成**です。</span><span class="sxs-lookup"><span data-stu-id="04182-157">On the top navigation bar, click **Create**.</span></span>  
  
3.  <span data-ttu-id="04182-158">[**ドキュメント ライブラリ**、] をクリックして**ドキュメント ライブラリ**します。</span><span class="sxs-lookup"><span data-stu-id="04182-158">Under **Document Libraries**, click **Document Library**.</span></span>  
  
4.  <span data-ttu-id="04182-159">**名前と説明**セクションで、入力`InfoPathSolutions`で、**名前フィールド**します。</span><span class="sxs-lookup"><span data-stu-id="04182-159">In the **Name and Description** section, type `InfoPathSolutions` in the **Name field**.</span></span>  
  
5.  <span data-ttu-id="04182-160">**ナビゲーション**セクションで、**はい**このフォーム ライブラリをクイック起動バーに表示します。</span><span class="sxs-lookup"><span data-stu-id="04182-160">In the **Navigation** section, select **Yes** to display this form library on the Quick Launch bar.</span></span>  
  
6.  <span data-ttu-id="04182-161">**ドキュメント テンプレート**セクションで、`None`の**ドキュメント テンプレート**します。</span><span class="sxs-lookup"><span data-stu-id="04182-161">In the **Document Template** section, select `None` for the **Document Template**.</span></span>  
  
7.  <span data-ttu-id="04182-162">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04182-162">Click **Create**.</span></span> <span data-ttu-id="04182-163">作成した空のライブラリにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="04182-163">You will be redirected to the empty library you just created.</span></span>  
  
8.  <span data-ttu-id="04182-164">左側にある クリックして**設定の変更と列**します。</span><span class="sxs-lookup"><span data-stu-id="04182-164">On the left side, click **Modify Settings and Columns**.</span></span>  
  
9. <span data-ttu-id="04182-165">[**列**、] をクリックして**新しい列を追加**します。</span><span class="sxs-lookup"><span data-stu-id="04182-165">Under **Columns**, click **Add a New Column**.</span></span>  
  
10. <span data-ttu-id="04182-166">**名前と種類**、型`Namespace`で、**名前**フィールド。</span><span class="sxs-lookup"><span data-stu-id="04182-166">Under **Name and Type**, type `Namespace` in the **Name** field.</span></span>  
  
11. <span data-ttu-id="04182-167">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04182-167">Click **OK**.</span></span>  
  
12. <span data-ttu-id="04182-168">`WSSAdapterWalkthrough` Web サイトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="04182-168">Close the `WSSAdapterWalkthrough` Web site.</span></span>  
  
#### <a name="create-an-infopath-form-based-on-the-orderprocessschema-schema-file"></a><span data-ttu-id="04182-169">OrderProcessSchema スキーマ ファイルを基にした InfoPath フォームの作成</span><span class="sxs-lookup"><span data-stu-id="04182-169">Create an InfoPath form based on the OrderProcessSchema schema file</span></span>  
  
1.  <span data-ttu-id="04182-170">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office**、順にクリックします**Microsoft Office InfoPath 2007**します。</span><span class="sxs-lookup"><span data-stu-id="04182-170">Click **Start**, point to **All Programs**, point to **Microsoft Office**, and then click **Microsoft Office InfoPath 2007**.</span></span>  
  
2.  <span data-ttu-id="04182-171">**フォームの入力**ダイアログ ボックスで、**フォームをデザインします。**</span><span class="sxs-lookup"><span data-stu-id="04182-171">In the **Fill Out a Form** dialog box, select **Design a Form.**</span></span>  
  
3.  <span data-ttu-id="04182-172">**フォームをデザイン**タスク ウィンドウで、 **XML ドキュメントまたはスキーマから新規**します。</span><span class="sxs-lookup"><span data-stu-id="04182-172">In the **Design a Form** task pane, select **New from XML Document or Schema**.</span></span>  
  
4.  <span data-ttu-id="04182-173">**データ ソース ウィザード**、 をクリックして**参照**最後の手順で作成したスキーマ ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="04182-173">In the **Data Source Wizard**, click **Browse** and select the schema file you created in the last procedure.</span></span> <span data-ttu-id="04182-174">たとえば、 `C:\WSSAdapterWalkthrough\OrderProcess\OrderProcess\OrderProcessSchema.xsd`のようにします。</span><span class="sxs-lookup"><span data-stu-id="04182-174">For example, `C:\WSSAdapterWalkthrough\OrderProcess\OrderProcess\OrderProcessSchema.xsd`.</span></span>  
  
5.  <span data-ttu-id="04182-175">**[次へ]** をクリックし、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04182-175">Click **Next**, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="04182-176">**データ ソース**タスク ウィンドウで、右クリックし、 **PurchaseOrder**ノード、およびクリック**コントロール付きセクション**。</span><span class="sxs-lookup"><span data-stu-id="04182-176">In the **Data Source** task pane, right-click the **PurchaseOrder** node, and then click **Section with Controls**.</span></span> <span data-ttu-id="04182-177">テンプレートにフォームが作成されます。</span><span class="sxs-lookup"><span data-stu-id="04182-177">This will create the form on the template.</span></span>  
  
7.  <span data-ttu-id="04182-178">クリックして**ファイル**、 をクリックして**保存**、順にクリックします**保存**します。</span><span class="sxs-lookup"><span data-stu-id="04182-178">Click **File**, click **Save**, and then click **Save**.</span></span>  
  
8.  <span data-ttu-id="04182-179">**名前を付けて保存**ダイアログ ボックスに「`PurchaseOrder.xsn`で、**ファイル名**フィールドをクリックして**保存**します。</span><span class="sxs-lookup"><span data-stu-id="04182-179">In the **Save As** dialog box, type `PurchaseOrder.xsn` in the **File name** field, and then click **Save**.</span></span>  
  
9. <span data-ttu-id="04182-180">クリックして**ファイル**、 をクリックし、**発行**します。</span><span class="sxs-lookup"><span data-stu-id="04182-180">Click **File**, and then click **Publish**.</span></span>  
  
10. <span data-ttu-id="04182-181">**公開ウィザード**、 をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="04182-181">In the **Publishing Wizard**, click **Next**.</span></span>  
  
11. <span data-ttu-id="04182-182">選択**Web サーバーに**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="04182-182">Select **To a Web Server**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="04182-183">パスとファイル名を入力、`InfoPathSolutions`ドキュメント ライブラリ、およびクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="04182-183">Type the path and filename to your `InfoPathSolutions` document library, and then click **Next**.</span></span> <span data-ttu-id="04182-184">たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough/InfoPathSolutions/PurchaseOrder.xsn`のようにします。</span><span class="sxs-lookup"><span data-stu-id="04182-184">For example, `http://<server_name>/sites/WSSAdapterWalkthrough/InfoPathSolutions/PurchaseOrder.xsn`.</span></span>  
  
13. <span data-ttu-id="04182-185">クリックして**完了**、順にクリックします**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="04182-185">Click **Finish**, and then click **Close**.</span></span>  
  
14. <span data-ttu-id="04182-186">Microsoft InfoPath を終了します。</span><span class="sxs-lookup"><span data-stu-id="04182-186">Close Microsoft InfoPath.</span></span>  
  
## <a name="modify-the-sharepoint-document-libraries"></a><span data-ttu-id="04182-187">SharePoint ドキュメント ライブラリの変更</span><span class="sxs-lookup"><span data-stu-id="04182-187">Modify the SharePoint document libraries</span></span>  
 <span data-ttu-id="04182-188">ここでは、PurchaseOrder.xsn ファイルの名前空間プロパティを更新し、アップロード先のドキュメント ライブラリを変更します。</span><span class="sxs-lookup"><span data-stu-id="04182-188">In this procedure you will update the namespace property for the PurchaseOrder.xsn file and modify the Destination Document Library.</span></span> <span data-ttu-id="04182-189">この名前空間は、コンテンツ ベースのルーティング シナリオで、パブリッシュされたドキュメントのサブスクライバーを特定するときに変数として使用されます。</span><span class="sxs-lookup"><span data-stu-id="04182-189">This namespace is used as a variable when determining subscribers of published documents for content based routing scenarios.</span></span>  
  
#### <a name="update-the-namespace-for-purchaseorderxsn"></a><span data-ttu-id="04182-190">PurchaseOrder.xsn の名前空間の更新</span><span class="sxs-lookup"><span data-stu-id="04182-190">Update the namespace for PurchaseOrder.xsn</span></span>  
  
1.  <span data-ttu-id="04182-191">Web ブラウザを開き、作成したサイトの URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="04182-191">Open a Web browser and navigate to the URL of the site you created.</span></span> <span data-ttu-id="04182-192">たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。</span><span class="sxs-lookup"><span data-stu-id="04182-192">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2.  <span data-ttu-id="04182-193">左側にある [**ドキュメント**、] をクリック`InfoPathSolutions`します。</span><span class="sxs-lookup"><span data-stu-id="04182-193">On the left side, under **Documents**, click `InfoPathSolutions`.</span></span>  
  
3.  <span data-ttu-id="04182-194">ポインターを置く`PurchaseOrder.xsn`を右クリックし、クリックして**プロパティの編集**します。</span><span class="sxs-lookup"><span data-stu-id="04182-194">Move the pointer over `PurchaseOrder.xsn`, right-click it, and then click **Edit Properties**.</span></span>  
  
4.  <span data-ttu-id="04182-195">型`http://OrderProcess.PurchaseOrder`で、 **Namespace**フィールドをクリックして**を保存して閉じます**します。</span><span class="sxs-lookup"><span data-stu-id="04182-195">Type `http://OrderProcess.PurchaseOrder` in the **Namespace** field, and then click **Save and Close**.</span></span>  
  
#### <a name="modify-the-destination-document-library"></a><span data-ttu-id="04182-196">アップロード先のドキュメント ライブラリの変更</span><span class="sxs-lookup"><span data-stu-id="04182-196">Modify the Destination document library</span></span>  
  
1.  <span data-ttu-id="04182-197">上部のナビゲーション バーでクリックして**ドキュメントし、リスト**します。</span><span class="sxs-lookup"><span data-stu-id="04182-197">On the top navigation bar, click **Documents and Lists**.</span></span>  
  
2.  <span data-ttu-id="04182-198">[**ドキュメント ライブラリ**、] をクリックして**先**します。</span><span class="sxs-lookup"><span data-stu-id="04182-198">Under **Document Libraries**, click **Destination**.</span></span>  
  
3.  <span data-ttu-id="04182-199">左側にある クリックして**設定の変更と列**します。</span><span class="sxs-lookup"><span data-stu-id="04182-199">On the left side, click **Modify Settings and Columns**.</span></span>  
  
4.  <span data-ttu-id="04182-200">[**列**、] をクリックして**新しい列の追加**します。</span><span class="sxs-lookup"><span data-stu-id="04182-200">Under **Columns**, click **Add New Column**.</span></span>  
  
5.  <span data-ttu-id="04182-201">**名前と種類**、型`Partner Name`で、**列名**フィールド。</span><span class="sxs-lookup"><span data-stu-id="04182-201">Under **Name and Type**, type `Partner Name` in the **Column name** field.</span></span>  
  
6.  <span data-ttu-id="04182-202">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04182-202">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="04182-203">`WSSAdapterWalkthrough` Web サイトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="04182-203">Close the `WSSAdapterWalkthrough` Web site.</span></span>  
  
## <a name="modify-the-send-port-from-walkthrough-1"></a><span data-ttu-id="04182-204">チュートリアル 1 の送信ポートの変更</span><span class="sxs-lookup"><span data-stu-id="04182-204">Modify the send port from walkthrough 1</span></span>  
 <span data-ttu-id="04182-205">ここでは、チュートリアル 1 の送信ポートを変更します。</span><span class="sxs-lookup"><span data-stu-id="04182-205">In this procedure you modify the send port from walkthrough 1.</span></span> <span data-ttu-id="04182-206">このチュートリアルで処理したドキュメントを確実に送信ポートへとルーティングするために、この手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="04182-206">This procedure is required to ensure that the document processed in this walkthrough is correctly routed to the send port.</span></span>  
  
#### <a name="modify-the-send-port"></a><span data-ttu-id="04182-207">送信ポートの変更</span><span class="sxs-lookup"><span data-stu-id="04182-207">Modify the send port</span></span>  
  
1. <span data-ttu-id="04182-208">開いている**BizTalk Server 管理します。**</span><span class="sxs-lookup"><span data-stu-id="04182-208">Open **BizTalk Server Administration.**</span></span>  
  
2. <span data-ttu-id="04182-209">展開**Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリックし、**送信ポート**ノード。</span><span class="sxs-lookup"><span data-stu-id="04182-209">Expand **Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and then click the **Send Ports** node.</span></span>  
  
3. <span data-ttu-id="04182-210">右クリックして`SendToDestination`、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="04182-210">Right-click `SendToDestination`, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="04182-211">[**トランスポート**、] をクリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="04182-211">Under **Transport**, click **Configure**.</span></span>  
  
5. <span data-ttu-id="04182-212">**Filename**フィールドに「`PurchaseOrder2-%XPATH=//pons:PurchaseOrder/pons:PurchaseOrderID%.xml`します。</span><span class="sxs-lookup"><span data-stu-id="04182-212">In the **Filename** field, type `PurchaseOrder2-%XPATH=//pons:PurchaseOrder/pons:PurchaseOrderID%.xml`.</span></span>  
  
6. <span data-ttu-id="04182-213">**Namespace エイリアス**フィールドに「`pons="http://OrderProcess.PurchaseOrder"`します。</span><span class="sxs-lookup"><span data-stu-id="04182-213">In the **Namespace Aliases** field, type `pons="http://OrderProcess.PurchaseOrder"`.</span></span>  
  
7. <span data-ttu-id="04182-214">**テンプレート ドキュメント ライブラリ**、型`InfoPathSolutions`します。</span><span class="sxs-lookup"><span data-stu-id="04182-214">In the **Templates Document Library**, type `InfoPathSolutions`.</span></span>  
  
8. <span data-ttu-id="04182-215">**テンプレート Namespace 列**、型`Namespace`します。</span><span class="sxs-lookup"><span data-stu-id="04182-215">In the **Templates Namespace Column**, type `Namespace`.</span></span>  
  
9. <span data-ttu-id="04182-216">選択`Yes`の**Microsoft Office 統合**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="04182-216">Select `Yes` for the **Microsoft Office Integration** property.</span></span>  
  
10. <span data-ttu-id="04182-217">**Windows SharePoint Services の統合**、型`Partner Name`で、**列 01**フィールド。</span><span class="sxs-lookup"><span data-stu-id="04182-217">Under **Windows SharePoint Services Integration**, type `Partner Name` in the **Column 01** field.</span></span>  
  
11. <span data-ttu-id="04182-218">型`%XPATH=//pons:PurchaseOrder/pons:BillTo%`で、**列 01 の値**フィールドに、をクリックして **[ok]**、順にクリックします**OK**を終了するには、もう一度、**送信ポートのプロパティ**ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="04182-218">Type `%XPATH=//pons:PurchaseOrder/pons:BillTo%` in the **Column 01 Value** field, click **OK**, and then click **OK** again to exit the **Send Port Properties** dialog box.</span></span>  
  
#### <a name="restart-the-send-port"></a><span data-ttu-id="04182-219">送信ポートを再起動します。</span><span class="sxs-lookup"><span data-stu-id="04182-219">Restart the send port</span></span>  
  
1.  <span data-ttu-id="04182-220">**BizTalk 管理コンソール**、クリックして、**送信ポート**ノード。</span><span class="sxs-lookup"><span data-stu-id="04182-220">In the **BizTalk Administration Console**, click the **Send Ports** node.</span></span>  
  
2.  <span data-ttu-id="04182-221">右クリックして`SendToDestination`、 をクリックし、**参加解除**します。</span><span class="sxs-lookup"><span data-stu-id="04182-221">Right-click `SendToDestination`, and then click **Unenlist**.</span></span>  
  
3.  <span data-ttu-id="04182-222">右クリック`SendToDestination`、 をクリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="04182-222">Right-click `SendToDestination`, and then click **Start**.</span></span>  
  
4.  <span data-ttu-id="04182-223">閉じる、 **BizTalk 管理コンソール**します。</span><span class="sxs-lookup"><span data-stu-id="04182-223">Close the **BizTalk Administration Console**.</span></span>  
  
## <a name="send-a-message-through-the-system"></a><span data-ttu-id="04182-224">システムからのメッセージ送信</span><span class="sxs-lookup"><span data-stu-id="04182-224">Send a message through the system</span></span>  
 <span data-ttu-id="04182-225">ここでは、InfoPath フォームを作成し、Windows SharePoint Services Web サイトにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="04182-225">In this procedure you create an InfoPath form and upload it to the Windows SharePoint Services Web site.</span></span> <span data-ttu-id="04182-226">そのメッセージは Windows SharePoint Services アダプターによって取得され、アーカイブ ドキュメント ライブラリにアーカイブされた後、アップロード先のドキュメント ライブラリに送信されます。</span><span class="sxs-lookup"><span data-stu-id="04182-226">The Windows SharePoint Services adapter will take that message, archive it in the Archive document library, and then send it to the Destination document library.</span></span> <span data-ttu-id="04182-227">この手順は、Windows SharePoint Services アダプターを使用し、SharePoint Web サイトから、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を経由して SharePoint サービス Web サイトへと送信されるドキュメント フローを示しています。</span><span class="sxs-lookup"><span data-stu-id="04182-227">This procedure demonstrates how a document flows from a Sharepoint web site, through [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and to a Sharepoint Services Web site using the Windows Sharepoint Services adapter.</span></span>  
  
#### <a name="create-an-infopath-form-to-send-through-the-system"></a><span data-ttu-id="04182-228">システムから送信する InfoPath フォームの作成</span><span class="sxs-lookup"><span data-stu-id="04182-228">Create an InfoPath form to send through the system</span></span>  
  
1.  <span data-ttu-id="04182-229">Web ブラウザを開き、作成したサイトの URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="04182-229">Open a Web browser and navigate to the URL of the site you created.</span></span> <span data-ttu-id="04182-230">たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。</span><span class="sxs-lookup"><span data-stu-id="04182-230">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2.  <span data-ttu-id="04182-231">左側にある [**ドキュメント**、] をクリック`InfoPathSolutions`します。</span><span class="sxs-lookup"><span data-stu-id="04182-231">On the left side, under **Documents**, click `InfoPathSolutions`.</span></span>  
  
3.  <span data-ttu-id="04182-232">をクリックして、`PurchaseOrder`ファイルを表示する、**ファイルのダウンロード**クリックしてダイアログ ボックスで、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="04182-232">Click the `PurchaseOrder` file to display the **File Download** dialog box, and then click **Open**.</span></span> <span data-ttu-id="04182-233">フォームが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="04182-233">InfoPath will load the form.</span></span>  
  
4.  <span data-ttu-id="04182-234">**Purchase Order ID**フィールドに「`1002`します。</span><span class="sxs-lookup"><span data-stu-id="04182-234">In the **Purchase Order ID** field, type `1002`.</span></span>  
  
5.  <span data-ttu-id="04182-235">**請求先**フィールドに「`John Doe`します。</span><span class="sxs-lookup"><span data-stu-id="04182-235">In the **Bill To** field, type `John Doe`.</span></span>  
  
6.  <span data-ttu-id="04182-236">**量**フィールドに「`750`します。</span><span class="sxs-lookup"><span data-stu-id="04182-236">In the **Amount** field, type `750`.</span></span>  
  
7.  <span data-ttu-id="04182-237">**発注書日付**フィールドに「`1/2/2005`します。</span><span class="sxs-lookup"><span data-stu-id="04182-237">In the **Purchase Order Date** field, type `1/2/2005`.</span></span>  
  
8.  <span data-ttu-id="04182-238">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04182-238">Click **Save**.</span></span>  
  
9. <span data-ttu-id="04182-239">**名前を付けて保存**ダイアログ ボックスに「`http://<server_name>/sites/WSSAdapterWalkthrough/Source`で、**ファイル名**フィールドしし、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="04182-239">In the **Save As** dialog box, type `http://<server_name>/sites/WSSAdapterWalkthrough/Source`in the **file name** field, and then hit Enter.</span></span>  
  
10. <span data-ttu-id="04182-240">型`PurchaseOrder2.xml`で、**ファイル名**フィールドをクリックして**保存**します。</span><span class="sxs-lookup"><span data-stu-id="04182-240">Type `PurchaseOrder2.xml` in the **file name** field, and then click **Save**.</span></span>  
  
11. <span data-ttu-id="04182-241">Microsoft Office InfoPath を終了します。</span><span class="sxs-lookup"><span data-stu-id="04182-241">Close Microsoft Office InfoPath.</span></span>  
  
12. <span data-ttu-id="04182-242">上部のナビゲーション バーで、Web ブラウザーで次のようにクリックします。**ドキュメントとリスト**します。</span><span class="sxs-lookup"><span data-stu-id="04182-242">In the Web browser, on the top navigation bar, click **Documents and Lists**.</span></span>  
  
13. <span data-ttu-id="04182-243">[**ドキュメント ライブラリ**、] をクリックして**先**します。</span><span class="sxs-lookup"><span data-stu-id="04182-243">Under **Document Libraries**, click **Destination**.</span></span>  
  
14. <span data-ttu-id="04182-244">アップロード先のドキュメント ライブラリには、メッセージの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="04182-244">In the Destination document library, you will now see your message listed.</span></span> <span data-ttu-id="04182-245">アーカイブ ドキュメント ライブラリにアーカイブされたコピーも紹介します。</span><span class="sxs-lookup"><span data-stu-id="04182-245">You will also find a copy archived in the Archive document library.</span></span>  
  
15. <span data-ttu-id="04182-246">[アップロード先のドキュメント ライブラリ] で `PurchaseOrder1.xml` をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04182-246">In the Destination document library, click `PurchaseOrder1.xml`.</span></span> <span data-ttu-id="04182-247">この XML ファイルは Microsoft Internet Explorer で開かれます。</span><span class="sxs-lookup"><span data-stu-id="04182-247">Note that this XML file is opened in Microsoft Internet Explorer.</span></span>  
  
16. <span data-ttu-id="04182-248">[アップロード先のドキュメント ライブラリ] で `PurchaseOrder2.xml` をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04182-248">In the Destination document library, click `PurchaseOrder2.xml`.</span></span> <span data-ttu-id="04182-249">この XML ファイルは Microsoft Office InfoPath で開かれます。</span><span class="sxs-lookup"><span data-stu-id="04182-249">Note that this XML file is opened in Microsoft Office InfoPath.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04182-250">アップロード先のドキュメント ライブラリでは、PurchaseOrderID フィールドの値がファイル名列に、BillTo フィールドの値がパートナー名列に格納されます。</span><span class="sxs-lookup"><span data-stu-id="04182-250">In the Destination document library, the file name column should contain the value of the PurchaseOrderID field and the Partner Name column should contain the value of the BillTo field.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="04182-251">まとめ</span><span class="sxs-lookup"><span data-stu-id="04182-251">Summary</span></span>  
 <span data-ttu-id="04182-252">このチュートリアルでは、Windows SharePoint Services アダプターとコンテンツ ベースのルーティング (CBR) を使用して、Microsoft Office InfoPath とのより緊密な統合を実現する方法を確認しました。</span><span class="sxs-lookup"><span data-stu-id="04182-252">In this walkthrough you have seen how to add tighter integration with Microsoft InfoPath using the Windows SharePoint Services Adapter and content-based routing (CBR).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="04182-253">次の手順</span><span class="sxs-lookup"><span data-stu-id="04182-253">Next Steps</span></span>  
 <span data-ttu-id="04182-254">これで、このチュートリアルを完了すると、実行、[チュートリアル。モジュール 3 - オーケストレーションから SharePoint プロパティへのアクセス](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md)チュートリアルでは、このチュートリアルでは、行った作業の発展として、プロジェクトにオーケストレーションを統合し、内から SharePoint プロパティにアクセスする方法を示しますです。</span><span class="sxs-lookup"><span data-stu-id="04182-254">Now that you have completed this walkthrough, perform the [Walkthrough: Module 3 - Accessing SharePoint Properties from an Orchestration](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md) walkthrough which expands on the work you have done with this walkthrough, integrates an orchestration into the project, and shows you how to access SharePoint properties from within it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04182-255">参照</span><span class="sxs-lookup"><span data-stu-id="04182-255">See Also</span></span>  
 <span data-ttu-id="04182-256">[Windows SharePoint Services アダプターとは何ですか。](../core/what-is-the-windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="04182-256">[What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md) </span></span>  
 [<span data-ttu-id="04182-257">Windows SharePoint Services アダプターのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="04182-257">Windows SharePoint Services Adapter Walkthroughs</span></span>](../core/windows-sharepoint-services-adapter-walkthroughs.md)