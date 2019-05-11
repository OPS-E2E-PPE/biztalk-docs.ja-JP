---
title: 手順 3:トリガー イベント (メッセージ) スキーマの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc4a67d9-9582-4f2b-9bc9-18fbff823d29
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c395a5dd68686b04d47af790f733174787b5a4b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288891"
---
# <a name="step-3-add-a-trigger-event-message-schema"></a><span data-ttu-id="014b2-102">手順 3:トリガー イベント (メッセージ) スキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="014b2-102">Step 3: Add a Trigger Event (Message) Schema</span></span>
<span data-ttu-id="014b2-103">この手順で、空に基づく新しいプロジェクトを作成する[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]プロジェクト テンプレート。</span><span class="sxs-lookup"><span data-stu-id="014b2-103">In this step, you create a new project based on the Empty [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Project template.</span></span> <span data-ttu-id="014b2-104">このプロジェクトにスキーマを追加する[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信バッチ内のメッセージの検証に使用されます (ADT ^ A03)。</span><span class="sxs-lookup"><span data-stu-id="014b2-104">To this project, you add the schema that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will use to validate the messages in the incoming batch (ADT^A03).</span></span> <span data-ttu-id="014b2-105">V2.3.1 の一般的なスキーマを含むプロジェクトへの参照を追加し、プロジェクトに厳密な名前を割り当て、プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="014b2-105">You add a reference to the project containing the v2.3.1 common schemas, assign the strong name to the project, and then deploy the project.</span></span>  

### <a name="to-add-the-project-containing-the-message-schema"></a><span data-ttu-id="014b2-106">メッセージ スキーマを含むプロジェクトに追加するには</span><span class="sxs-lookup"><span data-stu-id="014b2-106">To add the project containing the message schema</span></span>  

1. <span data-ttu-id="014b2-107">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="014b2-107">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  

2. <span data-ttu-id="014b2-108">新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**します。</span><span class="sxs-lookup"><span data-stu-id="014b2-108">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  

3. <span data-ttu-id="014b2-109">**テンプレート**セクションで、 **BTAHL7 の空のプロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="014b2-109">In the **Templates** section, select **Empty BTAHL7 Project**.</span></span>  

4. <span data-ttu-id="014b2-110">**名前**ボックスに、入力**BTAHL7V231Body**プロジェクト名として。</span><span class="sxs-lookup"><span data-stu-id="014b2-110">In the **Name** box, enter **BTAHL7V231Body** as the project name.</span></span>  

5. <span data-ttu-id="014b2-111">**ソリューション**ボックスで、**ソリューションに追加**します。</span><span class="sxs-lookup"><span data-stu-id="014b2-111">In the **Solution** box, select **Add to Solution**.</span></span>  

6. <span data-ttu-id="014b2-112">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="014b2-112">Click **OK**.</span></span>  

7. <span data-ttu-id="014b2-113">ソリューション エクスプ ローラーで、新しいプロジェクトのノードで右クリック**参照**、 をクリックし、**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="014b2-113">In Solution Explorer, under the node for your new project, right-click **References**, and then click **Add Reference**.</span></span>  

8. <span data-ttu-id="014b2-114">参照の追加 ダイアログ ボックスで、上、**プロジェクト** タブで  **BTAHL7V231Common プロジェクト**で、**プロジェクト名**列、 をクリックして**追加**、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="014b2-114">In the Add Reference dialog box, on the **Projects** tab, click **BTAHL7V231Common Project** in the **Project Name** column, click **Add**, and then click **OK**.</span></span>  

### <a name="to-add-the-schema-to-the-project"></a><span data-ttu-id="014b2-115">スキーマをプロジェクトに追加するには</span><span class="sxs-lookup"><span data-stu-id="014b2-115">To add the schema to the project</span></span>  

1. <span data-ttu-id="014b2-116">ソリューション エクスプ ローラーで右クリック**BTAHL7V231Body**、 をポイント**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="014b2-116">In Solution Explorer, right-click **BTAHL7V231Body**, point to **Add**, and then click **New Item**.</span></span>  

2. <span data-ttu-id="014b2-117">新しい項目の追加 ダイアログ ボックスで、 **BizTalk プロジェクトの項目**、 をクリックし、 **BTAHL7 スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="014b2-117">In the Add New Item dialog box, expand **BizTalk Project Items**, and then click **BTAHL7 Schemas**.</span></span> <span data-ttu-id="014b2-118">**テンプレート**ウィンドウで、をクリックして**BTAHL7 スキーマ**、 をクリックし、**追加**。</span><span class="sxs-lookup"><span data-stu-id="014b2-118">In the **Templates** pane, click **BTAHL7 Schemas**, and then click **Add**.</span></span>  

3. <span data-ttu-id="014b2-119">**HL7 スキーマの選択** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="014b2-119">In the **HL7 Schema Selector** dialog box, do the following:</span></span>  


   |     <span data-ttu-id="014b2-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="014b2-120">Use this</span></span>      |         <span data-ttu-id="014b2-121">目的</span><span class="sxs-lookup"><span data-stu-id="014b2-121">To do this</span></span>         |
   |-------------------|----------------------------|
   | <span data-ttu-id="014b2-122">**Message クラス**</span><span class="sxs-lookup"><span data-stu-id="014b2-122">**Message Class**</span></span> | <span data-ttu-id="014b2-123">保持**V2.X**として選択します。</span><span class="sxs-lookup"><span data-stu-id="014b2-123">Keep **V2.X** as selected.</span></span> |
   |    <span data-ttu-id="014b2-124">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="014b2-124">**Version**</span></span>    |     <span data-ttu-id="014b2-125">選択**2.3.1**します。</span><span class="sxs-lookup"><span data-stu-id="014b2-125">Select **2.3.1**.</span></span>      |
   | <span data-ttu-id="014b2-126">**メッセージの種類**</span><span class="sxs-lookup"><span data-stu-id="014b2-126">**Message Type**</span></span>  |      <span data-ttu-id="014b2-127">選択**ADT**します。</span><span class="sxs-lookup"><span data-stu-id="014b2-127">Select **ADT**.</span></span>       |
   | <span data-ttu-id="014b2-128">**トリガー イベント**</span><span class="sxs-lookup"><span data-stu-id="014b2-128">**Trigger Event**</span></span> |      <span data-ttu-id="014b2-129">選択**A03**します。</span><span class="sxs-lookup"><span data-stu-id="014b2-129">Select **A03**.</span></span>       |


4. <span data-ttu-id="014b2-130">をクリックして**作成**をプロジェクトにスキーマを追加する をクリックし、**キャンセル**ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="014b2-130">Click **Create** to add the schema to the project, then click **Cancel** to close the dialog box.</span></span> <span data-ttu-id="014b2-131">注その BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) が BTAHL7V231Body プロジェクトに ADT_A03_231_GLO_DEF.xsd スキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="014b2-131">Note that BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) has added the ADT_A03_231_GLO_DEF.xsd schema to the BTAHL7V231Body project.</span></span>  

### <a name="to-assign-a-strong-key-and-deploy"></a><span data-ttu-id="014b2-132">強力なキーの割り当てをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="014b2-132">To assign a strong key and deploy</span></span>  

1. <span data-ttu-id="014b2-133">ソリューション エクスプ ローラーで右クリックして**BTAHL7V231Body**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="014b2-133">In Solution Explorer, right-click **BTAHL7V231Body**, and then click **Properties**.</span></span>  

2. <span data-ttu-id="014b2-134">BTAHL7V231Body プロパティ ページ] ダイアログ ボックスで、[**署名**します。</span><span class="sxs-lookup"><span data-stu-id="014b2-134">In the BTAHL7V231Body Property Page dialog box, click **Signing**.</span></span>  

3. <span data-ttu-id="014b2-135">確認**アセンブリに署名**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="014b2-135">Check **Sign the assembly** check box.</span></span>  

4. <span data-ttu-id="014b2-136">**厳密な名前キー ファイルを選択して**一覧選択ドロップダウン**\<を参照しています.\>.**</span><span class="sxs-lookup"><span data-stu-id="014b2-136">In **Choose a strong name key file** drop down list select **\<Browse…\>.**</span></span>  

5. <span data-ttu-id="014b2-137">参照 **\<*ドライブ*\>: \Batching チュートリアル**を選択します**key.snk**、 をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="014b2-137">Browse to **\<*drive*\>:\Batching Tutorial**, select **key.snk**, and then click **Open**.</span></span>  

6. <span data-ttu-id="014b2-138">ソリューション エクスプ ローラーで右クリックして**BTAHL7V231Body**、 をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="014b2-138">In Solution Explorer, right-click **BTAHL7V231Body**, and then click **Deploy**.</span></span> <span data-ttu-id="014b2-139">成功メッセージが出力ウィンドウに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="014b2-139">Ensure that a success message appears in the output window.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="014b2-140">Successful-deploy メッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマのトラブルシューティングを行う。</span><span class="sxs-lookup"><span data-stu-id="014b2-140">If a successful-deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  

   <span data-ttu-id="014b2-141">続行する[手順 4。作成、受信ポートのバッチ メッセージを受け入れる](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md)します。</span><span class="sxs-lookup"><span data-stu-id="014b2-141">Proceed to [Step 4: Create a Receive Port for Accepting the Batch Message](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md).</span></span>