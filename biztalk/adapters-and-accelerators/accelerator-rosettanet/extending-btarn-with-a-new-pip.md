---
title: 新しい PIP による BTARN の拡張 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTARN, extending functionality
- PIPs, extending BTARN
- BTARN, PIPs
ms.assetid: 3db5cd5c-031f-4451-9be5-4b5d6163c3b1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0904d6d427fb6c04ae911edf23edb653ba9cb734
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003651"
---
# <a name="extending-btarn-with-a-new-pip"></a><span data-ttu-id="ae8b4-102">新しい PIP による BTARN の拡張</span><span class="sxs-lookup"><span data-stu-id="ae8b4-102">Extending BTARN with a New PIP</span></span>
<span data-ttu-id="ae8b4-103">このトピックでは、Microsoft を拡張する方法を説明します。[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]新しいパートナー インターフェイス Process (PIP) スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-103">This topic describes how to extend Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] with a new Partner Interface Process (PIP) schema.</span></span> <span data-ttu-id="ae8b4-104">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を拡張すると、RosettaNet PIP が BTARN セットアップ プログラムによってインストールされるどのスキーマとも関連付けられていない場合に、その PIP に基づくスキーマを追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-104">This lets you add a schema based on a RosettaNet PIP when that PIP is not associated with any of the schemas installed by the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program.</span></span>  

 <span data-ttu-id="ae8b4-105">新しい PIP で [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を拡張するには、新しいスキーマを独自のアセンブリで展開します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-105">When you extend [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] with a new PIP, you deploy the new schema in its own assembly.</span></span> <span data-ttu-id="ae8b4-106">また、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RNPIP アセンブリ内に展開された既存のスキーマを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-106">You can also modify an existing schema that is deployed within the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RNPIPs assembly.</span></span> <span data-ttu-id="ae8b4-107">詳細については、[Rnpip の既存の PIP 変更](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-107">For more information, see [Modifying an Existing PIP in RNPIPs](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md).</span></span>  

### <a name="to-extend-btarn-with-a-new-pip"></a><span data-ttu-id="ae8b4-108">BTARN を新しい PIP で拡張するには</span><span class="sxs-lookup"><span data-stu-id="ae8b4-108">To extend BTARN with a new PIP</span></span>  

1. <span data-ttu-id="ae8b4-109">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-109">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  

2. <span data-ttu-id="ae8b4-110">コマンド プロンプトに移動します。 \<*ドライブ*\>: \Program Files\\Microsoft の BizTalk 2013 Accelerator for rosettanet \sdk\utilities\schema Generator します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-110">At the command prompt, move to \<*drive*\>:\Program Files\\Microsoft  BizTalk 2013 Accelerator for RosettaNet\SDK\Utilities\Schema Generator.</span></span>  

3. <span data-ttu-id="ae8b4-111">コマンド プロンプトで「 **CScript InstallDTD.vbs**キー押しますと **」と入力**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-111">At the command prompt, type **CScript InstallDTD.vbs**, and then press **Enter**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ae8b4-112">BizTalk Server をインストールした後、手順 1 ~ 3 を 1 回実行する必要がありますのみです。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-112">You will only have to perform steps 1 through 3 once after you install BizTalk Server.</span></span>  

4. <span data-ttu-id="ae8b4-113">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-113">Start Visual Studio.</span></span>  

5. <span data-ttu-id="ae8b4-114">**[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-114">On the **File** menu, point to **New**, and then click **Project**.</span></span>  

6. <span data-ttu-id="ae8b4-115">新しいプロジェクト ダイアログ ボックスで、次のように選択します。 **BizTalk プロジェクト**で、左側のウィンドウとクリック**空の BizTalk Server プロジェクト**右側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-115">In the New Project dialog box, select **BizTalk Projects** in the left pane, and then click **Empty BizTalk Server Project** in the right pane.</span></span>  

7. <span data-ttu-id="ae8b4-116">クリックして**参照**プロジェクトを保存するディレクトリをポイントするとします。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-116">Click **Browse** and point to the directory where you want to save your project.</span></span>  

8. <span data-ttu-id="ae8b4-117">**名前**ボックスに、プロジェクト名を入力します。 **MyCustomPIP**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-117">In the **Name** box, type a project name, such as **MyCustomPIP**, and then click **OK**.</span></span>  

9. <span data-ttu-id="ae8b4-118">Visual Studio コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-118">Start Visual Studio command prompt.</span></span>  

10. <span data-ttu-id="ae8b4-119">コマンド プロンプトで、7 種類の手順で入力した場所に移動します。 **sn-k \<name.snk プロジェクト\>**、およびキーを押します **」と入力**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-119">At the command prompt, move to the location entered in step 7, type **sn -k \<project name.snk\>**, and then press **Enter**.</span></span>  

11. <span data-ttu-id="ae8b4-120">ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-120">In Solutions Explorer, right-click the project name, and then click **Properties**.</span></span>  

12. <span data-ttu-id="ae8b4-121">**プロパティ ページ**ダイアログ ボックスで、をクリックして**アセンブリ\*\*\*\*共通プロパティ**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-121">In the **Property Pages** dialog box, click **Assembly** under **Common Properties** in the left pane.</span></span>  

13. <span data-ttu-id="ae8b4-122">右側のペインでスクロールして**厳密な名前**、 をクリックして**アセンブリ キー ファイル**、右側のウィンドウで省略記号ボタン (…) を順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-122">In the right pane, scroll down to **Strong Name**, click **Assembly Key File**, and then click the ellipsis button (...) in the right pane.</span></span> <span data-ttu-id="ae8b4-123">手順 7. で入力した場所に移動し、手順 10. で作成した .snk ファイルの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-123">Move to the location entered in step 7, and select the name of the .snk file created in step 10.</span></span>  

14. <span data-ttu-id="ae8b4-124">プロパティ ページ ダイアログ ボックスで、**構成プロパティ**、 をクリックし、**展開**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-124">In the Property Pages dialog box, expand **Configuration Properties**, and then click **Deployment**.</span></span> <span data-ttu-id="ae8b4-125">右側のウィンドウで次のようにクリックします。**再デプロイ**を選択します`True`、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-125">In the right pane, click **Redeploy**, select `True`, and then click **OK**.</span></span>  

15. <span data-ttu-id="ae8b4-126">ソリューション エクスプ ローラーでプロジェクト名を右クリックして**追加**、 をクリックし、**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-126">In Solution Explorer, right-click the project name, point to **Add**, and then click **Existing Item**.</span></span>  

16. <span data-ttu-id="ae8b4-127">**既存項目の追加** ダイアログ ボックスに移動\<*ドライブ*\>: \Program Files\\Microsoft の BizTalk 2013 Accelerator for rosettanet \sdk\schemas を選択します**xml.xsd**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-127">In the **Add Existing Item** dialog box, move to \<*drive*\>:\Program Files\\Microsoft  BizTalk 2013 Accelerator for RosettaNet\SDK\Schemas, select **xml.xsd**, then click **Add**.</span></span>  

17. <span data-ttu-id="ae8b4-128">RNPIP の拡張に使用する PIP を RosettaNet.org からダウンロードします。詳細については、[新しい Partner Interface Process の組み込み](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-128">Download the PIP that you are going to extend RNPIPs with RosettaNet.org. For more information, see [Incorporating a New Partner Interface Process](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md).</span></span>  

18. <span data-ttu-id="ae8b4-129">ソリューション エクスプ ローラーでプロジェクト名を展開し、右クリックして**参照**、 をクリックし、**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-129">In Solution Explorer, expand the project name, right-click **Reference**, and then click **Add Reference**.</span></span>  

19. <span data-ttu-id="ae8b4-130">**参照の追加**ダイアログ ボックスで、をクリックして**参照**に移動し、 \<*ドライブ*\>: \Program Files\\Microsoft BizTalk 2013Accelerator for rosettanet \bin を選択し**Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-130">In the **Add Reference** dialog box, click **Browse**, and move to \<*drive*\>:\Program Files\\Microsoft  BizTalk 2013 Accelerator for RosettaNet\Bin, and then select **Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll**.</span></span> <span data-ttu-id="ae8b4-131">をクリックして**オープン**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-131">Click **Open**, and then click **OK**.</span></span>  

20. <span data-ttu-id="ae8b4-132">ソリューション エクスプ ローラーでプロジェクト名を右クリックして**追加**、 をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-132">In Solution Explorer, right-click the project name, point to **Add**, and then click **Add Generated Items**.</span></span>  

21. <span data-ttu-id="ae8b4-133">**生成した項目の追加** ダイアログ ボックスで、**カテゴリ**ウィンドウで、をクリックして**スキーマの生成**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-133">In the **Add Generated Items** dialog box, in the **Categories** pane, click **Generate Schemas**.</span></span> <span data-ttu-id="ae8b4-134">**テンプレート**ウィンドウで、をクリックして**スキーマの生成**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-134">In the **Templates** pane, click **Generate Schemas**, and then click **Add**.</span></span>  

22. <span data-ttu-id="ae8b4-135">[スキーマの生成] ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-135">In the Generate Schemas dialog box, do the following:</span></span>  


    |     <span data-ttu-id="ae8b4-136">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ae8b4-136">Use this</span></span>      |                                                                    <span data-ttu-id="ae8b4-137">目的</span><span class="sxs-lookup"><span data-stu-id="ae8b4-137">To do this</span></span>                                                                    |
    |-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
    | <span data-ttu-id="ae8b4-138">**ドキュメントの種類**</span><span class="sxs-lookup"><span data-stu-id="ae8b4-138">**Document type**</span></span> |                                                              <span data-ttu-id="ae8b4-139">選択**DTD スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-139">Select **DTD Schema**.</span></span>                                                              |
    |  <span data-ttu-id="ae8b4-140">**入力ファイル**</span><span class="sxs-lookup"><span data-stu-id="ae8b4-140">**Input File**</span></span>   | <span data-ttu-id="ae8b4-141">クリックして**参照**RosettaNet.org からダウンロードした DTD ファイルが含まれているフォルダーに移動し、をクリックし、DTD ファイルを選択して、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-141">Click **Browse**, move to the folder that contains the DTD file from RosettaNet.org, select the DTD file that you want, and then click **Open**.</span></span> |


23. <span data-ttu-id="ae8b4-142">スキーマの生成] ダイアログ ボックスで、[ **OK**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-142">In the Generate Schemas dialog box, click **OK**.</span></span>  

24. <span data-ttu-id="ae8b4-143">ソリューション エクスプローラーで、インポートした .xsd ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-143">In Solution Explorer, double-click the .xsd file that you just imported.</span></span>  

25. <span data-ttu-id="ae8b4-144">BizTalk エディターで、選択、 \<*スキーマ*\>ノード。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-144">In BizTalk Editor, select the \<*Schema*\> node.</span></span>  

26. <span data-ttu-id="ae8b4-145">[プロパティ] ウィンドウでスクロールして**ドキュメントの種類**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-145">In the Properties window, scroll down to **Document Type**.</span></span> <span data-ttu-id="ae8b4-146">**ドキュメントの種類**ボックスで、 **PIP**\<*3 桁のコード*\>、たとえば、 **PIP3A2**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-146">In the **Document Type** box, **PIP**\<*three-digit code*\>, for example, **PIP3A2**.</span></span> <span data-ttu-id="ae8b4-147">**ドキュメント バージョン**ボックスに「 **v**\<*xx.xx* \>または**R** \< *xx.xx*\>、たとえば、 **R01.02**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-147">In the **Document Version** box, type **v**\<*xx.xx*\> or **R**\<*xx.xx*\>, for example, **R01.02**.</span></span> <span data-ttu-id="ae8b4-148">このバージョン番号は、RosettaNet PIP 仕様に記載されています。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-148">This version should be as documented in the RosettaNet PIP specification.</span></span>  

27. <span data-ttu-id="ae8b4-149">[プロパティ] ウィンドウでスクロールして**ルート参照**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-149">In the Properties window, scroll down to **Root Reference**.</span></span> <span data-ttu-id="ae8b4-150">クリックして**ルート参照**、ドロップダウン リストから、スキーマ、たとえば、select のルート ノードを選択します。 **[pip3c5billingstatementnotification]** します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-150">Click **Root Reference**, and from the drop-down list, select the root node of the schema, for example, select **Pip3C5BillingStatementNotification**.</span></span>  

28. <span data-ttu-id="ae8b4-151">最大スクロール プロパティ ウィンドウで**Target Namespace**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-151">In the Properties window, scroll up to **Target Namespace**.</span></span> <span data-ttu-id="ae8b4-152">**Target Namespace**、型<strong>http://schemas.microsoft.com/biztalk/btarn/2004/\<DTDファイル名\>.dtd</strong>など、DTD ファイル名がある場合、 **3C5_MS_R01_00_BillingStatementNotification.dtd**.</span><span class="sxs-lookup"><span data-stu-id="ae8b4-152">For **Target Namespace**, type <strong>http://schemas.microsoft.com/biztalk/btarn/2004/\<DTD file name\>.dtd</strong>, where the DTD file name is, for example, **3C5_MS_R01_00_BillingStatementNotification.dtd**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="ae8b4-153">BTARN では、ターゲットの名前空間にこの命名規則を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-153">This naming convention for the target namespace is required for BTARN.</span></span> <span data-ttu-id="ae8b4-154">名前空間の別の規則を使用する場合[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]PIP ドキュメントのスキーマ検証を処理しません。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-154">If you use another namespace convention, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] will not process PIP documents for schema validation.</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="ae8b4-155">ターゲットの名前空間プロパティの DTD ファイル名には、PIP のバージョン番号が使用されています。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-155">The DTD file name in the target namespace property includes the version number of the PIP.</span></span> <span data-ttu-id="ae8b4-156">そのため、同じ PIP コードの複数のバージョンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-156">This lets you use multiple versions of the same PIP code.</span></span>  

29. <span data-ttu-id="ae8b4-157">最大スクロール プロパティ ウィンドウで**Imports**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-157">In the Properties window, scroll up to **Imports**.</span></span> <span data-ttu-id="ae8b4-158">横にある省略記号ボタン (…) をクリックします。 **Imports**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-158">Click the ellipsis button (...) next to **Imports**, and then click **Add**.</span></span>  

30. <span data-ttu-id="ae8b4-159">**BizTalk 型の選択** ダイアログ ボックスで、展開\<*プロジェクト名*\>、展開**参照**、展開**Microsoft.solutions.btarn.schemas.rnpips**、展開**スキーマ**、 **Microsoft.Solutions.BTARN.Schemas.RNPIPs.BaseDataTypes**、 をクリックして**OK**、 をクリックし、 **OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-159">In the **BizTalk Type Picker** dialog box, expand \<*Project Name*\>, expand **References**, expand **Microsoft.Solutions.BTARN.Schemas.RNPIPs**, expand **Schemas**, select **Microsoft.Solutions.BTARN.Schemas.RNPIPs.BaseDataTypes**, click **OK**, and then click **OK** again.</span></span>  

31. <span data-ttu-id="ae8b4-160">プロジェクト名を右クリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-160">Right-click the project name, and then click **Deploy**.</span></span>  

32. <span data-ttu-id="ae8b4-161">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-161">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

33. <span data-ttu-id="ae8b4-162">BizTalk 管理コンソールで  **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**、順に展開**ホスト**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-162">In BizTalk Administration Console, expand **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**, and then expand **Hosts**.</span></span> <span data-ttu-id="ae8b4-163">[**ホスト**、] をクリックして**BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-163">Under **Host**, click **BizTalkServerApplication**.</span></span>  

34. <span data-ttu-id="ae8b4-164">右側のウィンドウで、ホストの名前を右クリックし をクリックし、**再起動**します。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-164">In the right pane, right-click the name of the host, and then click **Restart**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="ae8b4-165">新しくインポートした PIP で RNPIP を拡張したら、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールでその PIP を使用して、正しい PIP 設定とアグリーメントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae8b4-165">After extending RNPIPs with a newly imported PIP, you must create the correct PIP configuration, and an agreement using that PIP, in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console.</span></span>  

## <a name="see-also"></a><span data-ttu-id="ae8b4-166">参照</span><span class="sxs-lookup"><span data-stu-id="ae8b4-166">See Also</span></span>  
 <span data-ttu-id="ae8b4-167">[新しい Partner Interface Process の組み込み](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md) </span><span class="sxs-lookup"><span data-stu-id="ae8b4-167">[Incorporating a New Partner Interface Process](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md) </span></span>  
 <span data-ttu-id="ae8b4-168">[Pip の操作](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md) </span><span class="sxs-lookup"><span data-stu-id="ae8b4-168">[Working with PIPs](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md) </span></span>  
 [<span data-ttu-id="ae8b4-169">RNPIP の既存の PIP の変更</span><span class="sxs-lookup"><span data-stu-id="ae8b4-169">Modifying an Existing PIP in RNPIPs</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)