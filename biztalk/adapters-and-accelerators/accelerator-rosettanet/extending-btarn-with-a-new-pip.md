---
title: "新しい PIP による BTARN の拡張 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BTARN, extending functionality
- PIPs, extending BTARN
- BTARN, PIPs
ms.assetid: 3db5cd5c-031f-4451-9be5-4b5d6163c3b1
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbf18261b1b6b30ab43816f4052022c652cec687
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="extending-btarn-with-a-new-pip"></a><span data-ttu-id="0fe68-102">新しい PIP による BTARN の拡張</span><span class="sxs-lookup"><span data-stu-id="0fe68-102">Extending BTARN with a New PIP</span></span>
<span data-ttu-id="0fe68-103">このトピックを拡張する方法について説明[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]新しいプロセス PIP (Partner Interface) スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="0fe68-103">This topic describes how to extend [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] with a new Partner Interface Process (PIP) schema.</span></span> <span data-ttu-id="0fe68-104">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を拡張すると、RosettaNet PIP が BTARN セットアップ プログラムによってインストールされるどのスキーマとも関連付けられていない場合に、その PIP に基づくスキーマを追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0fe68-104">This lets you add a schema based on a RosettaNet PIP when that PIP is not associated with any of the schemas installed by the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program.</span></span>  
  
 <span data-ttu-id="0fe68-105">新しい PIP で [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を拡張するには、新しいスキーマを独自のアセンブリで展開します。</span><span class="sxs-lookup"><span data-stu-id="0fe68-105">When you extend [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] with a new PIP, you deploy the new schema in its own assembly.</span></span> <span data-ttu-id="0fe68-106">また、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RNPIP アセンブリ内に展開された既存のスキーマを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="0fe68-106">You can also modify an existing schema that is deployed within the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RNPIPs assembly.</span></span> <span data-ttu-id="0fe68-107">詳細については、次を参照してください。 [Rnpip の既存の PIP 変更](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-107">For more information, see [Modifying an Existing PIP in RNPIPs](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md).</span></span>  
  
### <a name="to-extend-btarn-with-a-new-pip"></a><span data-ttu-id="0fe68-108">BTARN を新しい PIP で拡張するには</span><span class="sxs-lookup"><span data-stu-id="0fe68-108">To extend BTARN with a new PIP</span></span>  
  
1.  <span data-ttu-id="0fe68-109">をクリックして**開始**、をクリックして**実行**、型**cmd**、順にクリック**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-109">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="0fe68-110">コマンド プロンプトでに移動\<*ドライブ*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk 2013 Accelerator for rosettanet \sdk\utilities\schema Generator です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-110">At the command prompt, move to \<*drive*>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk 2013 Accelerator for RosettaNet\SDK\Utilities\Schema Generator.</span></span>  
  
3.  <span data-ttu-id="0fe68-111">コマンド プロンプトで次のように入力します。 **CScript InstallDTD.vbs**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-111">At the command prompt, type **CScript InstallDTD.vbs**, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0fe68-112">[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] をインストールした後は、手順 1. ～ 3. のみを実行します。</span><span class="sxs-lookup"><span data-stu-id="0fe68-112">You will only have to perform steps 1 through 3 once after you install [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].</span></span>  
  
4.  <span data-ttu-id="0fe68-113">[!INCLUDE[vs2012](../../includes/vs2012-md.md)]を起動します。</span><span class="sxs-lookup"><span data-stu-id="0fe68-113">Start [!INCLUDE[vs2012](../../includes/vs2012-md.md)].</span></span>  
  
5.  <span data-ttu-id="0fe68-114">**[ファイル]** メニューの **[新規作成]**をポイントし、 **[プロジェクト]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0fe68-114">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
6.  <span data-ttu-id="0fe68-115">新しいプロジェクト ダイアログ ボックスで、次のように選択します。 **BizTalk プロジェクト**をクリックして、左側のウィンドウ**空の BizTalk Server プロジェクト**右側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="0fe68-115">In the New Project dialog box, select **BizTalk Projects** in the left pane, and then click **Empty BizTalk Server Project** in the right pane.</span></span>  
  
7.  <span data-ttu-id="0fe68-116">をクリックして**参照**プロジェクトを保存するディレクトリをポイントします。</span><span class="sxs-lookup"><span data-stu-id="0fe68-116">Click **Browse** and point to the directory where you want to save your project.</span></span>  
  
8.  <span data-ttu-id="0fe68-117">**名**ボックスで、プロジェクト名を入力します。 **MyCustomPIP**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-117">In the **Name** box, type a project name, such as **MyCustomPIP**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="0fe68-118">開始[!INCLUDE[vs2012](../../includes/vs2012-md.md)]コマンド プロンプトです。</span><span class="sxs-lookup"><span data-stu-id="0fe68-118">Start [!INCLUDE[vs2012](../../includes/vs2012-md.md)] command prompt.</span></span>  
  
10. <span data-ttu-id="0fe68-119">コマンド プロンプトでは、手順 7. の種類で入力した場所に移動**sn-k\<プロジェクト name.snk >**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-119">At the command prompt, move to the location entered in step 7, type **sn -k \<project name.snk>**, and then press **Enter**.</span></span>  
  
11. <span data-ttu-id="0fe68-120">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-120">In Solutions Explorer, right-click the project name, and then click **Properties**.</span></span>  
  
12. <span data-ttu-id="0fe68-121">**プロパティ ページ**ダイアログ ボックスで、をクリックして**アセンブリ****共通プロパティ**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="0fe68-121">In the **Property Pages** dialog box, click **Assembly** under **Common Properties** in the left pane.</span></span>  
  
13. <span data-ttu-id="0fe68-122">右側のペインで下にスクロール**厳密名**、をクリックして**アセンブリ キー ファイル**、右側のウィンドウで、省略記号ボタン (...) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0fe68-122">In the right pane, scroll down to **Strong Name**, click **Assembly Key File**, and then click the ellipsis button (...) in the right pane.</span></span> <span data-ttu-id="0fe68-123">手順 7. で入力した場所に移動し、手順 10. で作成した .snk ファイルの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="0fe68-123">Move to the location entered in step 7, and select the name of the .snk file created in step 10.</span></span>  
  
14. <span data-ttu-id="0fe68-124">プロパティ ページ ダイアログ ボックスで、展開**構成プロパティ**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-124">In the Property Pages dialog box, expand **Configuration Properties**, and then click **Deployment**.</span></span> <span data-ttu-id="0fe68-125">右側のウィンドウでをクリックして**再展開**を選択`True`、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-125">In the right pane, click **Redeploy**, select `True`, and then click **OK**.</span></span>  
  
15. <span data-ttu-id="0fe68-126">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、 **追加** 、クリックして**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="0fe68-126">In Solution Explorer, right-click the project name, point to **Add**, and then click **Existing Item**.</span></span>  
  
16. <span data-ttu-id="0fe68-127">**既存項目の追加** ダイアログ ボックスに移動\<*ドライブ*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk 2013 Accelerator for rosettanet \sdk\schemas、の選択**xml.xsd**をクリックし、**追加**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-127">In the **Add Existing Item** dialog box, move to \<*drive*>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk 2013 Accelerator for RosettaNet\SDK\Schemas, select **xml.xsd**, then click **Add**.</span></span>  
  
17. <span data-ttu-id="0fe68-128">RNPIP の拡張に使用する PIP を RosettaNet.org からダウンロードします。詳細については、次を参照してください。[新しい Partner Interface Process の組み込み](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-128">Download the PIP that you are going to extend RNPIPs with RosettaNet.org. For more information, see [Incorporating a New Partner Interface Process](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md).</span></span>  
  
18. <span data-ttu-id="0fe68-129">ソリューション エクスプ ローラーでプロジェクト名を展開しを右クリックして**参照**、クリックして**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-129">In Solution Explorer, expand the project name, right-click **Reference**, and then click **Add Reference**.</span></span>  
  
19. <span data-ttu-id="0fe68-130">**参照の追加**ダイアログ ボックスで、をクリックして**参照**に移動する\<*ドライブ*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk 2013Accelerator for rosettanet \bin、クリック**Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-130">In the **Add Reference** dialog box, click **Browse**, and move to \<*drive*>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk 2013 Accelerator for RosettaNet\Bin, and then select **Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll**.</span></span> <span data-ttu-id="0fe68-131">をクリックして**開く**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-131">Click **Open**, and then click **OK**.</span></span>  
  
20. <span data-ttu-id="0fe68-132">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-132">In Solution Explorer, right-click the project name, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
21. <span data-ttu-id="0fe68-133">**生成した項目の追加** ダイアログ ボックスで、**カテゴリ** ウィンドウで、をクリックして**スキーマの生成**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-133">In the **Add Generated Items** dialog box, in the **Categories** pane, click **Generate Schemas**.</span></span> <span data-ttu-id="0fe68-134">**テンプレート** ウィンドウで、をクリックして**スキーマの生成**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-134">In the **Templates** pane, click **Generate Schemas**, and then click **Add**.</span></span>  
  
22. <span data-ttu-id="0fe68-135">[スキーマの生成] ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0fe68-135">In the Generate Schemas dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="0fe68-136">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0fe68-136">Use this</span></span>|<span data-ttu-id="0fe68-137">目的</span><span class="sxs-lookup"><span data-stu-id="0fe68-137">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="0fe68-138">**ドキュメントの種類**</span><span class="sxs-lookup"><span data-stu-id="0fe68-138">**Document type**</span></span>|<span data-ttu-id="0fe68-139">選択**DTD スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-139">Select **DTD Schema**.</span></span>|  
    |<span data-ttu-id="0fe68-140">**入力ファイル**</span><span class="sxs-lookup"><span data-stu-id="0fe68-140">**Input File**</span></span>|<span data-ttu-id="0fe68-141">をクリックして**参照**を RosettaNet.org から DTD ファイルが含まれているフォルダーに移動し、をクリックし、DTD ファイルを選択**開く**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-141">Click **Browse**, move to the folder that contains the DTD file from RosettaNet.org, select the DTD file that you want, and then click **Open**.</span></span>|  
  
23. <span data-ttu-id="0fe68-142">[スキーマの生成] ダイアログ ボックスで、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-142">In the Generate Schemas dialog box, click **OK**.</span></span>  
  
24. <span data-ttu-id="0fe68-143">ソリューション エクスプローラーで、インポートした .xsd ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="0fe68-143">In Solution Explorer, double-click the .xsd file that you just imported.</span></span>  
  
25. <span data-ttu-id="0fe68-144">BizTalk エディターで、選択、 \<*スキーマ*> ノード。</span><span class="sxs-lookup"><span data-stu-id="0fe68-144">In BizTalk Editor, select the \<*Schema*> node.</span></span>  
  
26. <span data-ttu-id="0fe68-145">[プロパティ] ウィンドウでスクロールして**ドキュメントの種類**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-145">In the Properties window, scroll down to **Document Type**.</span></span> <span data-ttu-id="0fe68-146">**ドキュメントの種類**ボックスで、 **PIP**\<*3 桁のコード*> など、 **PIP3A2**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-146">In the **Document Type** box, **PIP**\<*three-digit code*>, for example, **PIP3A2**.</span></span> <span data-ttu-id="0fe68-147">**ドキュメント バージョン**ボックスに、入力**v**\<*xx.xx*> または**R**\<*xx.xx*> など、 **R01.02**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-147">In the **Document Version** box, type **v**\<*xx.xx*> or **R**\<*xx.xx*>, for example, **R01.02**.</span></span> <span data-ttu-id="0fe68-148">このバージョン番号は、RosettaNet PIP 仕様に記載されています。</span><span class="sxs-lookup"><span data-stu-id="0fe68-148">This version should be as documented in the RosettaNet PIP specification.</span></span>  
  
27. <span data-ttu-id="0fe68-149">[プロパティ] ウィンドウでスクロールして**ルート参照**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-149">In the Properties window, scroll down to **Root Reference**.</span></span> <span data-ttu-id="0fe68-150">をクリックして**ルート参照**、ドロップダウン リストから、スキーマ、たとえば、select のルート ノードを選択して**[pip3c5billingstatementnotification]**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-150">Click **Root Reference**, and from the drop-down list, select the root node of the schema, for example, select **Pip3C5BillingStatementNotification**.</span></span>  
  
28. <span data-ttu-id="0fe68-151">[プロパティ] ウィンドウで、スクロールまで**Target Namespace**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-151">In the Properties window, scroll up to **Target Namespace**.</span></span> <span data-ttu-id="0fe68-152">**Target Namespace**、型**http://schemas.microsoft.com/biztalk/btarn/2004/\<DTD ファイル名 > .dtd**DTD ファイル名はたとえば、 **3C5_MS_R01_00_BillingStatementNotification.dtd**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-152">For **Target Namespace**, type **http://schemas.microsoft.com/biztalk/btarn/2004/\<DTD file name>.dtd**, where the DTD file name is, for example, **3C5_MS_R01_00_BillingStatementNotification.dtd**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0fe68-153">BTARN では、ターゲットの名前空間にこの命名規則を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fe68-153">This naming convention for the target namespace is required for BTARN.</span></span> <span data-ttu-id="0fe68-154">別の名前空間規則を使用する場合[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]PIP ドキュメントのスキーマ検証を処理しません。</span><span class="sxs-lookup"><span data-stu-id="0fe68-154">If you use another namespace convention, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] will not process PIP documents for schema validation.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0fe68-155">ターゲットの名前空間プロパティの DTD ファイル名には、PIP のバージョン番号が使用されています。</span><span class="sxs-lookup"><span data-stu-id="0fe68-155">The DTD file name in the target namespace property includes the version number of the PIP.</span></span> <span data-ttu-id="0fe68-156">そのため、同じ PIP コードの複数のバージョンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0fe68-156">This lets you use multiple versions of the same PIP code.</span></span>  
  
29. <span data-ttu-id="0fe68-157">[プロパティ] ウィンドウで、スクロールまで**Imports**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-157">In the Properties window, scroll up to **Imports**.</span></span> <span data-ttu-id="0fe68-158">横にある省略記号ボタン (...) をクリックして**Imports**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-158">Click the ellipsis button (...) next to **Imports**, and then click **Add**.</span></span>  
  
30. <span data-ttu-id="0fe68-159">**BizTalk 型の選択**] ダイアログ ボックスで、展開\<*プロジェクト名*>、展開**参照**、展開**Microsoft.Solutions.BTARN.Schemas.RNPIPs**、展開**スキーマ**[ **Microsoft.Solutions.BTARN.Schemas.RNPIPs.BaseDataTypes**をクリックして**[ok]**、クリックして**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-159">In the **BizTalk Type Picker** dialog box, expand \<*Project Name*>, expand **References**, expand **Microsoft.Solutions.BTARN.Schemas.RNPIPs**, expand **Schemas**, select **Microsoft.Solutions.BTARN.Schemas.RNPIPs.BaseDataTypes**, click **OK**, and then click **OK** again.</span></span>  
  
31. <span data-ttu-id="0fe68-160">プロジェクト名を右クリックし、をクリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-160">Right-click the project name, and then click **Deploy**.</span></span>  
  
32. <span data-ttu-id="0fe68-161">をクリックして**開始**、をポイント**すべてのプログラム**、をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-161">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
33. <span data-ttu-id="0fe68-162">BizTalk 管理コンソールで、展開**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(ローカル)**の順に展開および**ホスト**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-162">In BizTalk Administration Console, expand **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**, and then expand **Hosts**.</span></span> <span data-ttu-id="0fe68-163">**ホスト**をクリックして**BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-163">Under **Host**, click **BizTalkServerApplication**.</span></span>  
  
34. <span data-ttu-id="0fe68-164">右側のウィンドウで、ホストの名前を右クリックし、をクリックして**再起動**です。</span><span class="sxs-lookup"><span data-stu-id="0fe68-164">In the right pane, right-click the name of the host, and then click **Restart**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0fe68-165">新しくインポートした PIP で RNPIP を拡張したら、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールでその PIP を使用して、正しい PIP 設定とアグリーメントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fe68-165">After extending RNPIPs with a newly imported PIP, you must create the correct PIP configuration, and an agreement using that PIP, in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fe68-166">参照</span><span class="sxs-lookup"><span data-stu-id="0fe68-166">See Also</span></span>  
 <span data-ttu-id="0fe68-167">[新しい Partner Interface Process の組み込み](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md) </span><span class="sxs-lookup"><span data-stu-id="0fe68-167">[Incorporating a New Partner Interface Process](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md) </span></span>  
 <span data-ttu-id="0fe68-168">[Pip の操作](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md) </span><span class="sxs-lookup"><span data-stu-id="0fe68-168">[Working with PIPs](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md) </span></span>  
 [<span data-ttu-id="0fe68-169">Rnpip の既存の PIP の変更</span><span class="sxs-lookup"><span data-stu-id="0fe68-169">Modifying an Existing PIP in RNPIPs</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)