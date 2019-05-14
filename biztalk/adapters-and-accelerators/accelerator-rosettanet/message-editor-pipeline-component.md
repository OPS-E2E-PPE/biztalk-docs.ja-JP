---
title: メッセージ エディタ パイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, Message Editor Pipeline Component
- Message Editor Pipeline Component
- messages, editing
- pipelines, Message Editor Pipeline Component
ms.assetid: f2b22dea-54e8-410b-868f-2978139f438b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8b010f9f1e8a1217e2928ef4cfd147b56bf7043
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283211"
---
# <a name="message-editor-pipeline-component"></a><span data-ttu-id="3b0c5-102">メッセージ エディタ パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3b0c5-102">Message Editor Pipeline Component</span></span>
<span data-ttu-id="3b0c5-103">このコンポーネントでは、受信パイプラインまたは送信内のマルチパート メッセージの一部を自動的に編集することができます。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-103">This component lets you edit automatically any part of a multipart message within a send or receive pipeline.</span></span> <span data-ttu-id="3b0c5-104">このコンポーネントを通常の処理の一部として置換を設定する既存のパイプラインに追加します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-104">You add this component to an existing pipeline to set up the replacement as part of typical processing.</span></span>  
  
## <a name="building-the-message-editor-pipeline-component-into-an-existing-pipeline"></a><span data-ttu-id="3b0c5-105">メッセージ エディタ パイプライン コンポーネントを既存のパイプラインに組み込む</span><span class="sxs-lookup"><span data-stu-id="3b0c5-105">Building the Message Editor Pipeline Component into an Existing Pipeline</span></span>  
 <span data-ttu-id="3b0c5-106">メッセージ エディタ パイプライン コンポーネントを使用するには、既存のパイプラインにコンポーネントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-106">To use the Message Editor Pipeline Component, you have to add the component to an existing pipeline.</span></span> <span data-ttu-id="3b0c5-107">詳細については、」を作成するパイプライン「パイプライン デザイナーで BizTalk Server のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-107">For more information, see "Creating Pipelines with Pipeline Designer" in BizTalk Server Help.</span></span>  
  
#### <a name="to-add-the-message-editor-pipeline-component-to-an-existing-pipeline"></a><span data-ttu-id="3b0c5-108">メッセージ エディタ パイプライン コンポーネントを既存のパイプラインに追加するには</span><span class="sxs-lookup"><span data-stu-id="3b0c5-108">To add the Message Editor Pipeline Component to an existing pipeline</span></span>  
  
1. <span data-ttu-id="3b0c5-109">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-109">Start Visual Studio.</span></span>  
  
2. <span data-ttu-id="3b0c5-110">**ファイル**メニューで、**オープン**、 をクリックし、**プロジェクト**。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-110">On the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="3b0c5-111">C:\Program Files (x86) \microsoft BizTalk 移動\<バージョン\>Accelerator for rosettanet \sdk\message Editor Pipeline Component では、選択 **[messageeditor.csproj]**、順にクリックします**開く**.</span><span class="sxs-lookup"><span data-stu-id="3b0c5-111">Move to C:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Message Editor Pipeline Component, select **MessageEditor.csproj**, and then click **Open**.</span></span>  
  
4. <span data-ttu-id="3b0c5-112">Visual Studio コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-112">Start Visual Studio command prompt.</span></span>  
  
5. <span data-ttu-id="3b0c5-113">コマンド プロンプトで C:\Program Files (x86) \microsoft BizTalk 移動\<バージョン\>Accelerator for rosettanet \sdk\message Editor Pipeline component \obj\debug します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-113">At the command prompt, move to C:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Message Editor Pipeline Component\obj\debug.</span></span>  
  
6. <span data-ttu-id="3b0c5-114">コマンド プロンプトで「 **sn-k MessageEditor.snk**キーを作成し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-114">At the command prompt, type **sn -k MessageEditor.snk** to create a key, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="3b0c5-115">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで右クリックして **[messageeditor]**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-115">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click **MessageEditor**, and then click **Properties**.</span></span>  
  
8. <span data-ttu-id="3b0c5-116">**MessageEditor プロパティ** ページで **署名** タブをクリックして**アセンブリに署名**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-116">In the **MessageEditor Property** page, click **Signing** tab, and then click **Sign the assembly** checkbox.</span></span>  
  
9. <span data-ttu-id="3b0c5-117">**厳密な名前キー ファイルを選択して**ドロップダウンで、C:\Program Files (x86) \microsoft BizTalk\<バージョン\>アクセラレータを選択してください Editor Pipeline component \obj\debug**MessageEditor.snk**し**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-117">In **Choose a strong name key file** drop-down, browse to C:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\ SDK\Message Editor Pipeline Component\obj\debug and select **MessageEditor.snk** and then click **Open**.</span></span>  
  
10. <span data-ttu-id="3b0c5-118">ソリューション エクスプ ローラーで右クリックして**messageeditor**、 をクリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-118">In Solution Explorer, right-click **MessageEditor**, and then click **Build**.</span></span> <span data-ttu-id="3b0c5-119">[出力] ウィンドウで、ビルドが成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-119">Verify in the Output pane that the build succeeded.</span></span>  
  
11. <span data-ttu-id="3b0c5-120">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**アクセサリ**、順にクリックします**Windows エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-120">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
12. <span data-ttu-id="3b0c5-121">[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーには、C:\Program files \microsoft BizTalk 2013 Accelerator for rosettanet \sdk\message Editor Pipeline component \obj\debug の移動を右クリックして **[microsoft.solutions.btarn.sdk.messageeditor.dll]**、クリックして**コピー**します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-121">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to C:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\Message Editor Pipeline Component\obj\debug, right-click **Microsoft.Solutions.BTARN.SDK.MessageEditor.dll**, and then click **Copy**.</span></span>  
  
13. <span data-ttu-id="3b0c5-122">2013\Pipeline コンポーネントを C:\Program files \microsoft BizTalk Server に移動、右クリックして**パイプライン コンポーネント**、 をクリックし、**貼り付け**します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-122">Move to C:\Program Files\Microsoft BizTalk Server 2013\Pipeline Components, right-click **Pipeline Components**, and then click **Paste**.</span></span>  
  
14. <span data-ttu-id="3b0c5-123">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル** メニューのをポイント**開く**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-123">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
15. <span data-ttu-id="3b0c5-124">エディターを追加するパイプラインを含んでいるプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-124">Open the project that contains the pipeline to which you want to add the editor.</span></span>  
  
16. <span data-ttu-id="3b0c5-125">ソリューション エクスプ ローラーでは、パイプライン デザイナーでパイプラインを開くパイプライン名をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-125">In Solution Explorer, double-click the pipeline name to open the pipeline in Pipeline Designer.</span></span>  
  
17. <span data-ttu-id="3b0c5-126">ツールボックス ウィンドウの BizTalk パイプライン コンポーネント ペインで右クリックし をクリックし、**アイテムの追加/削除**します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-126">Right-click in the BizTalk Pipeline Components pane of the Toolbox pane, and then click **Add/Remove Items**.</span></span>  
  
18. <span data-ttu-id="3b0c5-127">**ツールボックスのカスタマイズ** ダイアログ ボックスで、 **BizTalk パイプライン コンポーネント** タブで  **BTARN Message Editor Component**、順にクリックします**ok**.</span><span class="sxs-lookup"><span data-stu-id="3b0c5-127">In the **Customize Toolbox** dialog box, on the **BizTalk Pipeline Components** tab, select **BTARN Message Editor Component**, and then click **OK**.</span></span>  
  
19. <span data-ttu-id="3b0c5-128">[ツールボックス] ウィンドウの [BizTalk パイプライン コンポーネント] ウィンドウで、クリックして押したまま**BTARN Message Editor Component**、コンポーネントをパイプライン内の目的の位置にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-128">In the BizTalk Pipeline Components pane of the Toolbox pane, click and hold **BTARN Message Editor Component**, and then drag the component to the position that you want in the pipeline.</span></span>  
  
20. <span data-ttu-id="3b0c5-129">[ツールボックス] ウィンドウの [BizTalk パイプライン コンポーネント] ウィンドウで、クリックして押したまま**BTARN Message Editor Component**、コンポーネントをパイプライン内の目的の位置にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-129">In the BizTalk Pipeline Components pane of the Toolbox pane, click and hold **BTARN Message Editor Component**, and then drag the component to the position that you want in the pipeline.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3b0c5-130">メッセージ エディタ パイプライン コンポーネントは、逆アセンブル ステージでは、受信パイプライン コンポーネント、または送信パイプライン コンポーネントのプリアセンブル ステージの後に追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-130">It is recommended that you add the Message Editor Pipeline Component after the Disassemble stage in the receive pipeline component or in the Pre-Assemble stage of the send pipeline component.</span></span>  
  
21. <span data-ttu-id="3b0c5-131">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、パイプライン デザイナーで、選択、 **BTARN Message Editor Component**図形。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-131">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in Pipeline Designer, select the **BTARN Message Editor Component** shape.</span></span>  
  
22. <span data-ttu-id="3b0c5-132">関連付けられているテキスト ボックスに、プロパティ ペインで**XPath クエリ**値を変更する XPath 要素の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-132">In the Properties pane, in the text box associated with **XPath Query**, type the name of the XPath element for which you want to change the value.</span></span>  
  
23. <span data-ttu-id="3b0c5-133">関連付けられているテキスト ボックスに**XPath 値**、XPath 要素を設定する値を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-133">In the text box associated with **XPath Value**, type the value to which you want to set the XPath element.</span></span>  
  
24. <span data-ttu-id="3b0c5-134">ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-134">In Solutions Explorer, right-click the project name, and then click **Build**.</span></span> <span data-ttu-id="3b0c5-135">ビルドが成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-135">Verify that the build succeeds.</span></span>  
  
25. <span data-ttu-id="3b0c5-136">ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-136">In Solutions Explorer, right-click the project name, and then click **Deploy**.</span></span> <span data-ttu-id="3b0c5-137">デプロイが成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-137">Verify that the deployment succeeds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b0c5-138">例</span><span class="sxs-lookup"><span data-stu-id="3b0c5-138">Example</span></span>  
 <span data-ttu-id="3b0c5-139">要素の値を変更する`ProprietaryDocumentIdentifier`0c1 で PIP スキーマでは、メッセージ エディタ パイプライン コンポーネントの XPath クエリ プロパティに次のコード セクションに示すように XPath クエリを追加します。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-139">To change the value of the element `ProprietaryDocumentIdentifier` in the 0C1 PIP Schema, add the XPath Query shown in the following Code section to the XPath Query property of the Message Editor Pipeline Component.</span></span>  
  
```  
/*[local-name()='Pip0C1AsynchronousTestNotification' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']/*[local-name()='thisDocumentIdentifier' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']/*[local-name()='ProprietaryDocumentIdentifier' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']  
```  
  
 <span data-ttu-id="3b0c5-140">完全な XPath クエリを取得するスキーマを BizTalk エディターで開くしから Xpath をコピーし、`Instance XPath`プロパティ ウィンドウの下のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-140">To obtain a complete XPath Query, open the schema in BizTalk Editor, and then copy the Xpath from the `Instance XPath` property under the Properties window.</span></span> <span data-ttu-id="3b0c5-141">指定した XPath クエリでその名前空間のすべての参照が必要です。</span><span class="sxs-lookup"><span data-stu-id="3b0c5-141">The XPath Query that you provide should have all the namespace references in it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b0c5-142">参照</span><span class="sxs-lookup"><span data-stu-id="3b0c5-142">See Also</span></span>  
 [<span data-ttu-id="3b0c5-143">ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="3b0c5-143">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
