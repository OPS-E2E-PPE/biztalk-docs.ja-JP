---
title: Inspector パイプライン コンポーネントをメッセージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipelines, custom pipelines
- pipelines, Message Inspector Pipeline Component
- Message Inspector Pipeline Component
- pipelines, creating
ms.assetid: d9c00718-c8cd-4289-8f58-e4edc61b9a05
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb6b8a2d9bcd503b1b295110665827ead3e85ee6
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855621"
---
# <a name="message-inspector-pipeline-component"></a><span data-ttu-id="ffec0-102">Message Inspector パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ffec0-102">Message Inspector Pipeline Component</span></span>
<span data-ttu-id="ffec0-103">このパイプライン コンポーネントにより、マルチパート メッセージのすべての部分、およびメッセージ コンテキストを確認し、メッセージに問題があるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="ffec0-103">This pipeline component lets you examine all the parts of a multi-part message, and the message context, to determine whether there is a problem with the message.</span></span> <span data-ttu-id="ffec0-104">このコンポーネントはトラブルシューティングの目的で使用します。</span><span class="sxs-lookup"><span data-stu-id="ffec0-104">You use this component for troubleshooting purposes.</span></span>  
  
 <span data-ttu-id="ffec0-105">このパイプライン コンポーネントにより、XML ファイルは指定されたディレクトリにドロップされます。</span><span class="sxs-lookup"><span data-stu-id="ffec0-105">The pipeline component drops XML files into a directory that you designate.</span></span> <span data-ttu-id="ffec0-106">これらの各ファイルは、RNIFv2.0 メッセージの 4 つの部分 (Preamble Header、Delivery Header、Service Header、Service Content) のいずれか、または RNIFv1.1 メッセージの 3 つの部分 (Preamble Header、Service Header、Service Content) のいずれかを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="ffec0-106">Each of these files contains one of the four parts of an RNIFv2.0 message (Preamble Header, Delivery Header, Service Header, and Service Content) or the three parts of an RNIFv1.1 message (Preamble Header, Service Header, and Service Content).</span></span> <span data-ttu-id="ffec0-107">もう 1 つの XML ファイルは、メッセージ コンテキストを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="ffec0-107">Another XML file contains the message context.</span></span>  
  
 <span data-ttu-id="ffec0-108">このコンポーネントは、カスタム パイプラインに構築し、送信ポートに接続します。</span><span class="sxs-lookup"><span data-stu-id="ffec0-108">You build this component into a custom pipeline and attach it to a send port.</span></span> <span data-ttu-id="ffec0-109">送信ポートにフィルタを作成し、監視するメッセージをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="ffec0-109">You create a filter in the send port to subscribe to the messages that you want to monitor.</span></span> <span data-ttu-id="ffec0-110">このトラブルシューティングは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] が既に実行している標準の処理とは別に実行されます。</span><span class="sxs-lookup"><span data-stu-id="ffec0-110">This troubleshooting occurs in addition to the standard processing that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] already performs.</span></span>  
  
## <a name="building-a-custom-pipeline-using-the-message-inspector-pipeline-component"></a><span data-ttu-id="ffec0-111">Message Inspector パイプライン コンポーネントを使用したカスタム パイプラインの構築</span><span class="sxs-lookup"><span data-stu-id="ffec0-111">Building a Custom Pipeline Using the Message Inspector Pipeline Component</span></span>  
 <span data-ttu-id="ffec0-112">Message Inspector パイプライン コンポーネントを使用するには、このコンポーネントを含むカスタム パイプラインを構築し、展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffec0-112">To use the Message Inspector Pipeline Component, you have to build and deploy a custom pipeline that includes the component.</span></span> <span data-ttu-id="ffec0-113">詳細については、パイプラインとパイプライン デザイナーの作成」BizTalk Server ヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffec0-113">For more information, see "Creating Pipelines with Pipeline Designer" in BizTalk Server Help.</span></span>  
  
#### <a name="to-deploy-the-message-inspector-pipeline-component"></a><span data-ttu-id="ffec0-114">Message Inspector パイプライン コンポーネントを展開するには</span><span class="sxs-lookup"><span data-stu-id="ffec0-114">To deploy the Message Inspector Pipeline Component</span></span>  
  
1.  <span data-ttu-id="ffec0-115">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="ffec0-115">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="ffec0-116">**ファイル** メニューのをポイント**開く**、順にクリック**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-116">On the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="ffec0-117">C:\Program Files (x86) \Microsoft BizTalk に移動\<バージョン\>Accelerator for rosettanet \sdk\message Inspector Pipeline Component 選択 **[messageinspector.csproj]**、クリックして**開いている**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-117">Move to C:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Message Inspector Pipeline Component, select **MessageInspector.csproj**, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="ffec0-118">Visual Studio コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="ffec0-118">Open the Visual Studio command prompt.</span></span>  
  
5.  <span data-ttu-id="ffec0-119">コマンド プロンプトで C:\Program Files (x86) \Microsoft BizTalk に移動\<バージョン\>Accelerator for rosettanet \sdk\message Inspector Pipeline component \obj\debug です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-119">At the command prompt, move to C:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Message Inspector Pipeline Component\obj\debug.</span></span>  
  
6.  <span data-ttu-id="ffec0-120">コマンド プロンプトで次のように入力します。 **"sn-k MessageInspector.snk"** キーを作成し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ffec0-120">At the command prompt, type **"sn -k MessageInspector.snk"** to create a key, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="ffec0-121">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで右クリック**MessageInspector**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-121">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click **MessageInspector**, and then click **Properties**.</span></span>  
  
8.  <span data-ttu-id="ffec0-122">**MessageInspector プロパティ** ページで **署名** タブをクリックして**アセンブリに署名**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="ffec0-122">In the **MessageInspector Property**  page, click **Signing** tab, and then click **Sign the assembly** checkbox.</span></span>  
  
9. <span data-ttu-id="ffec0-123">**厳密な名前キー ファイルを選択して**ドロップダウン リストで、C:\Program Files (x86) \microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\message Inspector Pipeline component \obj\debug を選択**MessageInspector.snk**  をクリックし、**開く**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-123">In **Choose a strong name key file** drop-down, browse to C:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Message Inspector Pipeline Component\obj\debug and select **MessageInspector.snk** and then click **Open**.</span></span>  
  
10. <span data-ttu-id="ffec0-124">ソリューション エクスプ ローラーで右**MessageInspector**をクリックし、**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-124">In Solutions Explorer, right-click **MessageInspector**, and then click **Build**.</span></span> <span data-ttu-id="ffec0-125">出力ペインで、ビルドが成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ffec0-125">Verify in the Output pane that the build succeeded.</span></span>  
  
11. <span data-ttu-id="ffec0-126">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**アクセサリ**、順にクリック**Windows エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-126">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
12. <span data-ttu-id="ffec0-127">[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、C:\Program Files (x86) \Microsoft BizTalk への移行\<バージョン\>Accelerator for rosettanet \sdk\message Inspector Pipeline component \obj\debug を右クリックして **[Microsoft.solutions.btarn.sdk.messageinspector.dll]**、クリックして**コピー**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-127">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to C:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Message Inspector Pipeline Component\obj\debug, right-click **Microsoft.Solutions.BTARN.SDK.MessageInspector.dll**, and then click **Copy**.</span></span>  
  
13. <span data-ttu-id="ffec0-128">C:\Program Files (x86) \Microsoft BizTalk に移動\<バージョン\>Accelerator for rosettanet \pipeline Components を右クリックして**パイプライン コンポーネント**、クリックして**貼り付け**.</span><span class="sxs-lookup"><span data-stu-id="ffec0-128">Move to C:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\Pipeline Components, right-click **Pipeline Components**, and then click **Paste**.</span></span>  
  
14. <span data-ttu-id="ffec0-129">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="ffec0-129">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
15. <span data-ttu-id="ffec0-130">**新しいプロジェクト**ダイアログ ボックスで、テンプレート ペインで**空の BizTalk Server プロジェクト**で、**名前**ボックスで、プロジェクトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ffec0-130">In the **New Project** dialog box, in the Templates pane, select **Empty BizTalk Server Project**, in the **Name** box, type a name for the project.</span></span> <span data-ttu-id="ffec0-131">**場所**ボックスで、プロジェクトを保存するフォルダーに移動し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-131">In the **Location** box, move to the folder that you want to save the project in, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="ffec0-132">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、**追加**、クリックして**新しい項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-132">In Solution Explorer, right-click the project name, point to **Add**, and then click **Add New Item**.</span></span>  
  
17. <span data-ttu-id="ffec0-133">**新しい項目の追加**ダイアログ ボックスで、**送信パイプライン**で、**名前**ボックスで、カスタム パイプライン ファイルの名前を入力し、をクリックして**を開く**.</span><span class="sxs-lookup"><span data-stu-id="ffec0-133">In the **Add New Item** dialog box, select **Send Pipeline**, in the **Name** box, type a name for the custom pipeline file, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ffec0-134">Message Inspector パイプライン コンポーネントは、受信ポートではなく、送信ポートのみに追加します。</span><span class="sxs-lookup"><span data-stu-id="ffec0-134">Add the Message Inspector Pipeline Component only to send ports, not to receive ports.</span></span>  
  
18. <span data-ttu-id="ffec0-135">ツールボックス ペインの BizTalk パイプライン コンポーネント ペイン内を右クリックし、をクリックして**アイテムの追加/削除**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-135">Right-click within the BizTalk Pipeline Components pane of the Toolbox pane, and then click **Add/Remove Items**.</span></span>  
  
19. <span data-ttu-id="ffec0-136">**ツールボックスのカスタマイズ** ダイアログ ボックスで、 **BizTalk パイプライン コンポーネント** タブで  **BTARN Message Inspector Component**、順にクリック**ok**.</span><span class="sxs-lookup"><span data-stu-id="ffec0-136">In the **Customize Toolbox** dialog box, on the **BizTalk Pipeline Components** tab, select **BTARN Message Inspector Component**, and then click **OK**.</span></span>  
  
20. <span data-ttu-id="ffec0-137">BizTalk パイプライン コンポーネント ペインで、[ツールボックス] ウィンドウをクリックして押した**BTARN Message Inspector Component**のコンポーネントをドラッグし、**ここにドロップします。**</span><span class="sxs-lookup"><span data-stu-id="ffec0-137">In the BizTalk Pipeline Components pane of the Toolbox pane, click and hold **BTARN Message Inspector Component**, and then drag the component on a **Drop Here!**</span></span> <span data-ttu-id="ffec0-138">◆セグ ： 前の TU に含まれる◇</span><span class="sxs-lookup"><span data-stu-id="ffec0-138">box.</span></span>  
  
21. <span data-ttu-id="ffec0-139">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで、パイプライン プロジェクトの名前を右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-139">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click the name of the pipeline project, and then click **Properties**.</span></span>  
  
22. <span data-ttu-id="ffec0-140">**プロパティ ページ**ダイアログ ボックスで、をクリックして**共通プロパティ**、クリックして**アセンブリ**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-140">In the **Property Pages** dialog box, click **Common Properties**, and then click **Assembly**.</span></span>  
  
23. <span data-ttu-id="ffec0-141">関連付けられているテキスト ボックスに、右ペインで**アセンブリ キー ファイル**、省略記号ボタンをクリックして、C:\Program Files (x86) \microsoft BizTalk 移動\<バージョン\>Accelerator for rosettanet \sdk\message InspectorPipeline component \obj\debug、select **MessageInspector.snk**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-141">In the right pane, in the text box associated with **Assembly Key File**, click the ellipses, move to C:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Message Inspector Pipeline Component\obj\debug, select **MessageInspector.snk**, and then click **OK**.</span></span>  
  
24. <span data-ttu-id="ffec0-142">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]パイプライン デザイナー、select、 **BTARN Message Inspector Component**図形です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-142">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Pipeline Designer, select the **BTARN Message Inspector Component** shape.</span></span>  
  
25. <span data-ttu-id="ffec0-143">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、**ディレクトリ**ボックスに、XML ファイルをドロップするディレクトリの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ffec0-143">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Properties window, in the **Directory** box, type the name of the directory to which you want to drop the XML files.</span></span>  
  
26. <span data-ttu-id="ffec0-144">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-144">In Solution Explorer, right-click the project name, and then click **Build**.</span></span> <span data-ttu-id="ffec0-145">ビルドが成功することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ffec0-145">Verify that the build succeeds.</span></span>  
  
27. <span data-ttu-id="ffec0-146">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-146">In Solution Explorer, right-click the project name, and then click **Deploy**.</span></span> <span data-ttu-id="ffec0-147">展開が成功することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ffec0-147">Verify that the deployment succeeds.</span></span>  
  
28. <span data-ttu-id="ffec0-148">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ビュー** メニューのをクリックして**BizTalk エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-148">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **View** menu, click **BizTalk Explorer**.</span></span>  
  
29. <span data-ttu-id="ffec0-149">右クリック**送信ポート**、クリックして**送信ポートの追加**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-149">Right-click **Send Ports**, and then click **Add Send Port**.</span></span>  
  
30. <span data-ttu-id="ffec0-150">**新しい送信ポートを作成**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-150">In the **Create New Send Port** dialog box, click **OK**.</span></span>  
  
31. <span data-ttu-id="ffec0-151">**送信ポートのプロパティ** ダイアログ ボックスで、**名前**と送信ポートの名前を入力ボックスに、**プライマリ**をクリックして選択すると、左側のウィンドウで、**トランスポートの種類**クリックし、右側のペインで**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-151">In the **Send Port Properties** dialog box, in the **Name** box, type a name for the send port, with **Primary** selected in the left pane, click **Transport Type** in the right pane, and select **FILE**.</span></span>  
  
32. <span data-ttu-id="ffec0-152">**送信ポートのプロパティ** ダイアログ ボックスで、**アドレス (URI)** ボックスで、省略記号ボタンをクリックして (**.**).</span><span class="sxs-lookup"><span data-stu-id="ffec0-152">In the **Send Port Properties** dialog box, in the **Address (URI)** box, click the ellipsis button (**...**).</span></span>  
  
33. <span data-ttu-id="ffec0-153">**FILE トランスポートのプロパティ**ダイアログ ボックスで、型、**先**フォルダー名 をクリックして**送信**左側のウィンドウでし、 **送信パイプライン**右側のウィンドウで、先ほど作成したカスタム パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="ffec0-153">In the **FILE Transport Properties** dialog box, type the **Destination** folder name, click **Send** in the left pane, and then for the **Send Pipeline** in the right pane, select the custom pipeline that you have just created.</span></span>  
  
34. <span data-ttu-id="ffec0-154">をクリックして**フィルターし、マップ**をクリックして、左側のウィンドウ**フィルター**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-154">Click **Filters & Maps** in the left pane, and then click **Filters**.</span></span>  
  
35. <span data-ttu-id="ffec0-155">右側のペインにフィルター式を入力し、パイプラインで XML ファイルをドロップするファイルの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="ffec0-155">Enter a filter expression in the right pane, designating the type of files that you want the pipeline to drop XML files for.</span></span> <span data-ttu-id="ffec0-156">たとえばのすべての RNIF v1.1 メッセージ、ファイルを削除する場合**プロパティ**Microsoft.Solutions.BTARN.Schemas.RNIFv11.GlobalBusinessAction を選択および**演算子**と"Exists"を選択し、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-156">For example, if you want to drop files for all RNIF v1.1 messages, for **Property** you would select Microsoft.Solutions.BTARN.Schemas.RNIFv11.GlobalBusinessAction, and for **Operator** you would select "Exists", and then click **OK**.</span></span>  
  
36. <span data-ttu-id="ffec0-157">BizTalk エクスプローラで、先ほど作成した送信ポートを右クリックし、をクリックして**Enlist**送信ポートを再度右クリックし、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="ffec0-157">In BizTalk Explorer, right-click the send port that you just created, click **Enlist**, right-click the send port again, and then click **Start**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ffec0-158">コメント</span><span class="sxs-lookup"><span data-stu-id="ffec0-158">Remarks</span></span>  
 <span data-ttu-id="ffec0-159">通常の処理では、一度に確認できるのはメッセージの一部分 (オーケストレーションでメッセージの本文として指定した部分) のみです。</span><span class="sxs-lookup"><span data-stu-id="ffec0-159">In typical processing, you can only examine one of the message parts at a time (the part that you have designated as the message body in the orchestration).</span></span> <span data-ttu-id="ffec0-160">したがって、BizTalk 管理コンソールではメッセージの一部分しか確認できないため、トラブルシューティングの能力も限定されます。</span><span class="sxs-lookup"><span data-stu-id="ffec0-160">Therefore, you can only examine one of the parts in the BizTalk Administration Console, and your ability to troubleshoot is limited.</span></span> <span data-ttu-id="ffec0-161">Message Inspector パイプライン コンポーネントでは、この制限を克服するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ffec0-161">The Message Inspector Pipeline Component helps you to overcome this limitation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffec0-162">参照</span><span class="sxs-lookup"><span data-stu-id="ffec0-162">See Also</span></span>  
 [<span data-ttu-id="ffec0-163">ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="ffec0-163">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
