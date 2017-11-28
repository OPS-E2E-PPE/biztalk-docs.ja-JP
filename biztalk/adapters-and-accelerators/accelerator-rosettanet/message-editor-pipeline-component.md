---
title: "メッセージ エディタ パイプライン コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, Message Editor Pipeline Component
- Message Editor Pipeline Component
- messages, editing
- pipelines, Message Editor Pipeline Component
ms.assetid: f2b22dea-54e8-410b-868f-2978139f438b
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56d22e5ff6003dad9767c57eecac626a6c16e243
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-editor-pipeline-component"></a><span data-ttu-id="806fa-102">メッセージ エディター パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="806fa-102">Message Editor Pipeline Component</span></span>
<span data-ttu-id="806fa-103">このコンポーネントにより、送信または受信パイプライン内のマルチパート メッセージの一部を自動的に編集できます。</span><span class="sxs-lookup"><span data-stu-id="806fa-103">This component lets you edit automatically any part of a multipart message within a send or receive pipeline.</span></span> <span data-ttu-id="806fa-104">このコンポーネントは既存のパイプラインに追加して、通常の処理の一部として置換のためのパイプラインを設定します。</span><span class="sxs-lookup"><span data-stu-id="806fa-104">You add this component to an existing pipeline to set up the replacement as part of typical processing.</span></span>  
  
## <a name="building-the-message-editor-pipeline-component-into-an-existing-pipeline"></a><span data-ttu-id="806fa-105">既存のパイプラインへのメッセージ エディタ パイプライン コンポーネントの構築</span><span class="sxs-lookup"><span data-stu-id="806fa-105">Building the Message Editor Pipeline Component into an Existing Pipeline</span></span>  
 <span data-ttu-id="806fa-106">メッセージ エディタ パイプライン コンポーネントを使用するには、既存のパイプラインにコンポーネントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="806fa-106">To use the Message Editor Pipeline Component, you have to add the component to an existing pipeline.</span></span> <span data-ttu-id="806fa-107">詳細については、[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ヘルプの「パイプライン デザイナーでのパイプラインの作成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="806fa-107">For more information, see "Creating Pipelines with Pipeline Designer" in [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
#### <a name="to-add-the-message-editor-pipeline-component-to-an-existing-pipeline"></a><span data-ttu-id="806fa-108">メッセージ エディタ パイプライン コンポーネントを既存のパイプラインに追加するには</span><span class="sxs-lookup"><span data-stu-id="806fa-108">To add the Message Editor Pipeline Component to an existing pipeline</span></span>  
  
1.  <span data-ttu-id="806fa-109">[!INCLUDE[vs2012](../../includes/vs2012-md.md)]を起動します。</span><span class="sxs-lookup"><span data-stu-id="806fa-109">Start [!INCLUDE[vs2012](../../includes/vs2012-md.md)].</span></span>  
  
2.  <span data-ttu-id="806fa-110">**ファイル**メニューのをポイント**開く**、順にクリック**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="806fa-110">On the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="806fa-111">C:\Program files \microsoft BizTalk 2013 Accelerator for rosettanet \sdk\message Editor Pipeline Component、選択移動**[messageeditor.csproj]**、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="806fa-111">Move to C:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\Message Editor Pipeline Component, select **MessageEditor.csproj**, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="806fa-112">開始[!INCLUDE[vs2012](../../includes/vs2012-md.md)]コマンド プロンプトです。</span><span class="sxs-lookup"><span data-stu-id="806fa-112">Start [!INCLUDE[vs2012](../../includes/vs2012-md.md)] command prompt.</span></span>  
  
5.  <span data-ttu-id="806fa-113">コマンド プロンプトで、C:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\Message Editor Pipeline Component\obj\debug に移動します。</span><span class="sxs-lookup"><span data-stu-id="806fa-113">At the command prompt, move to C:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\Message Editor Pipeline Component\obj\debug.</span></span>  
  
6.  <span data-ttu-id="806fa-114">コマンド プロンプトで次のように入力します。 **sn-k MessageEditor.snk**キーを作成し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="806fa-114">At the command prompt, type **sn -k MessageEditor.snk** to create a key, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="806fa-115">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで右クリック**MessageEditor**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="806fa-115">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click **MessageEditor**, and then click **Properties**.</span></span>  
  
8.  <span data-ttu-id="806fa-116">**MessageEditor プロパティ** ページで **署名** タブをクリックして**アセンブリに署名**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="806fa-116">In the **MessageEditor Property** page, click **Signing** tab, and then click **Sign the assembly** checkbox.</span></span>  
  
9. <span data-ttu-id="806fa-117">**厳密な名前キー ファイルを選択して**ドロップダウン、C:\Program files \microsoft BizTalk 2013 Accelerator for rosettanet \sdk\message Editor Pipeline component \obj\debug 参照および選択**MessageEditor.snk**  をクリックし、**開く**です。</span><span class="sxs-lookup"><span data-stu-id="806fa-117">In **Choose a strong name key file** drop-down, browse to C:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\ SDK\Message Editor Pipeline Component\obj\debug and select **MessageEditor.snk** and then click **Open**.</span></span>  
  
10. <span data-ttu-id="806fa-118">ソリューション エクスプ ローラーで右クリック**MessageEditor**、クリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="806fa-118">In Solution Explorer, right-click **MessageEditor**, and then click **Build**.</span></span> <span data-ttu-id="806fa-119">出力ペインで、ビルドが成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="806fa-119">Verify in the Output pane that the build succeeded.</span></span>  
  
11. <span data-ttu-id="806fa-120">をクリックして**開始**、をポイント**すべてのプログラム**、をポイント**アクセサリ**、順にクリック**Windows エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="806fa-120">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
12. <span data-ttu-id="806fa-121">[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、C:\Program files \microsoft BizTalk 2013 Accelerator for rosettanet \sdk\message Editor Pipeline component \obj\debug 移動を右クリックして**[microsoft.solutions.btarn.sdk.messageeditor.dll]**、クリックして**コピー**です。</span><span class="sxs-lookup"><span data-stu-id="806fa-121">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to C:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\Message Editor Pipeline Component\obj\debug, right-click **Microsoft.Solutions.BTARN.SDK.MessageEditor.dll**, and then click **Copy**.</span></span>  
  
13. <span data-ttu-id="806fa-122">C:\Program files \microsoft BizTalk Server 2013\Pipeline コンポーネントに移動、右クリック**パイプライン コンポーネント**、順にクリック**貼り付け**です。</span><span class="sxs-lookup"><span data-stu-id="806fa-122">Move to C:\Program Files\Microsoft BizTalk Server 2013\Pipeline Components, right-click **Pipeline Components**, and then click **Paste**.</span></span>  
  
14. <span data-ttu-id="806fa-123">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル**メニューのをポイント**開く**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="806fa-123">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
15. <span data-ttu-id="806fa-124">エディターを追加するパイプラインを含んでいるプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="806fa-124">Open the project that contains the pipeline to which you want to add the editor.</span></span>  
  
16. <span data-ttu-id="806fa-125">ソリューション エクスプローラーで、パイプライン名をクリックし、パイプライン デザイナーでパイプラインを開きます。</span><span class="sxs-lookup"><span data-stu-id="806fa-125">In Solution Explorer, double-click the pipeline name to open the pipeline in Pipeline Designer.</span></span>  
  
17. <span data-ttu-id="806fa-126">ツールボックス ペインの BizTalk パイプライン コンポーネント ペイン内を右クリックし、をクリックして**アイテムの追加/削除**です。</span><span class="sxs-lookup"><span data-stu-id="806fa-126">Right-click in the BizTalk Pipeline Components pane of the Toolbox pane, and then click **Add/Remove Items**.</span></span>  
  
18. <span data-ttu-id="806fa-127">**ツールボックスのカスタマイズ** ダイアログ ボックスで、 **BizTalk パイプライン コンポーネント** タブで  **BTARN Message Editor Component**、順にクリック**ok**.</span><span class="sxs-lookup"><span data-stu-id="806fa-127">In the **Customize Toolbox** dialog box, on the **BizTalk Pipeline Components** tab, select **BTARN Message Editor Component**, and then click **OK**.</span></span>  
  
19. <span data-ttu-id="806fa-128">BizTalk パイプライン コンポーネント ペインで、[ツールボックス] ウィンドウをクリックして押した**BTARN Message Editor Component**、コンポーネントをパイプライン内の目的の位置にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="806fa-128">In the BizTalk Pipeline Components pane of the Toolbox pane, click and hold **BTARN Message Editor Component**, and then drag the component to the position that you want in the pipeline.</span></span>  
  
20. <span data-ttu-id="806fa-129">BizTalk パイプライン コンポーネント ペインで、[ツールボックス] ウィンドウをクリックして押した**BTARN Message Editor Component**、コンポーネントをパイプライン内の目的の位置にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="806fa-129">In the BizTalk Pipeline Components pane of the Toolbox pane, click and hold **BTARN Message Editor Component**, and then drag the component to the position that you want in the pipeline.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="806fa-130">メッセージ エディター パイプライン コンポーネントは、受信パイプライン コンポーネントの逆アセンブル ステージ、または送信パイプライン コンポーネントのプリアセンブル ステージの後で追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="806fa-130">It is recommended that you add the Message Editor Pipeline Component after the Disassemble stage in the receive pipeline component or in the Pre-Assemble stage of the send pipeline component.</span></span>  
  
21. <span data-ttu-id="806fa-131">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、パイプライン デザイナーで、選択、 **BTARN Message Editor Component**図形です。</span><span class="sxs-lookup"><span data-stu-id="806fa-131">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in Pipeline Designer, select the **BTARN Message Editor Component** shape.</span></span>  
  
22. <span data-ttu-id="806fa-132">関連付けられているテキスト ボックスに、プロパティ ペインで**XPath クエリ**値を変更する XPath 要素の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="806fa-132">In the Properties pane, in the text box associated with **XPath Query**, type the name of the XPath element for which you want to change the value.</span></span>  
  
23. <span data-ttu-id="806fa-133">関連付けられているテキスト ボックスに**XPath 値**、XPath 要素を設定する値を入力します。</span><span class="sxs-lookup"><span data-stu-id="806fa-133">In the text box associated with **XPath Value**, type the value to which you want to set the XPath element.</span></span>  
  
24. <span data-ttu-id="806fa-134">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="806fa-134">In Solutions Explorer, right-click the project name, and then click **Build**.</span></span> <span data-ttu-id="806fa-135">ビルドが成功することを確認します。</span><span class="sxs-lookup"><span data-stu-id="806fa-135">Verify that the build succeeds.</span></span>  
  
25. <span data-ttu-id="806fa-136">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="806fa-136">In Solutions Explorer, right-click the project name, and then click **Deploy**.</span></span> <span data-ttu-id="806fa-137">展開が成功することを確認します。</span><span class="sxs-lookup"><span data-stu-id="806fa-137">Verify that the deployment succeeds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="806fa-138">例</span><span class="sxs-lookup"><span data-stu-id="806fa-138">Example</span></span>  
 <span data-ttu-id="806fa-139">0C1 PIP スキーマで `ProprietaryDocumentIdentifier` 要素の値を変更するには、次のコード セクションに示された XPath クエリをメッセージ エディタ パイプライン コンポーネントの XPath クエリ プロパティに追加します。</span><span class="sxs-lookup"><span data-stu-id="806fa-139">To change the value of the element `ProprietaryDocumentIdentifier` in the 0C1 PIP Schema, add the XPath Query shown in the following Code section to the XPath Query property of the Message Editor Pipeline Component.</span></span>  
  
```  
/*[local-name()='Pip0C1AsynchronousTestNotification' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']/*[local-name()='thisDocumentIdentifier' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']/*[local-name()='ProprietaryDocumentIdentifier' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']  
```  
  
 <span data-ttu-id="806fa-140">完全な XPath クエリを取得するには、BizTalk エディターでスキーマを開き、プロパティ ウィンドウの `Instance XPath` プロパティから Xpath をコピーします。</span><span class="sxs-lookup"><span data-stu-id="806fa-140">To obtain a complete XPath Query, open the schema in BizTalk Editor, and then copy the Xpath from the `Instance XPath` property under the Properties window.</span></span> <span data-ttu-id="806fa-141">指定する XPath クエリには、すべての名前空間参照が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="806fa-141">The XPath Query that you provide should have all the namespace references in it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="806fa-142">参照</span><span class="sxs-lookup"><span data-stu-id="806fa-142">See Also</span></span>  
 [<span data-ttu-id="806fa-143">ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="806fa-143">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)