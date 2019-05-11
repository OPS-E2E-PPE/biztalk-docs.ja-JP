---
title: 手順 2:更新し、チュートリアルのソリューションの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d03adfdd-1160-4e8c-a564-3acb2ecd0476
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89dff2034e747374c5fdb08763e5d5fbd9d604a7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392705"
---
# <a name="step-2-update-and-deploy-the-tutorial-solution"></a><span data-ttu-id="9e398-102">手順 2:更新し、チュートリアルのソリューションの展開</span><span class="sxs-lookup"><span data-stu-id="9e398-102">Step 2: Update and Deploy the Tutorial Solution</span></span>
<span data-ttu-id="9e398-103">![手順 2 の 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")</span><span class="sxs-lookup"><span data-stu-id="9e398-103">![Step 2 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")</span></span>  
  
 <span data-ttu-id="9e398-104">このステップでは、このチュートリアルのために用意されたソリューションを更新し、チュートリアルのアセンブリをビルドして展開します。</span><span class="sxs-lookup"><span data-stu-id="9e398-104">In this step you update the solution provided for this tutorial, and then build and deploy the tutorial assembly.</span></span> <span data-ttu-id="9e398-105">このチュートリアルで使用できるように、必要なスキーマ、カスタム送信パイプライン、およびマップは既に作成されています。</span><span class="sxs-lookup"><span data-stu-id="9e398-105">For the purposes of this tutorial, the necessary schema, custom send pipeline, and map have already been created.</span></span> <span data-ttu-id="9e398-106">マップは、850 の EDI データを注文システムで必要な形式に変換するために使用します。</span><span class="sxs-lookup"><span data-stu-id="9e398-106">The map is used to convert the 850 EDI data into the format required by your Order System.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9e398-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="9e398-107">Prerequisites</span></span>  
 <span data-ttu-id="9e398-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e398-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-enable-the-edi-inbound-processing-solution-to-be-built-in-visual-studio"></a><span data-ttu-id="9e398-109">EDI 受信処理ソリューションを Visual Studio でビルドできるようにするには</span><span class="sxs-lookup"><span data-stu-id="9e398-109">To enable the EDI Inbound Processing solution to be built in Visual Studio</span></span>  
  
1. <span data-ttu-id="9e398-110">開始**Microsoft Visual Studio**に管理者として。</span><span class="sxs-lookup"><span data-stu-id="9e398-110">Start **Microsoft Visual Studio** as an administrator.</span></span>  
  
   > [!CAUTION]
   >  <span data-ttu-id="9e398-111">管理者特権を使用して Visual Studio を起動しないと、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にソリューションを展開しているときにエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e398-111">If you do not start Visual Studio with administrator privileges, you will get an error while deploying the solution to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="9e398-112">Visual Studio で、次のようにクリックします。**ファイル**、 をポイント**オープン**、 をクリックし、**プロジェクト/ソリューション**します。</span><span class="sxs-lookup"><span data-stu-id="9e398-112">In Visual Studio, click **File**, point to **Open**, and then click **Project/Solution**.</span></span> <span data-ttu-id="9e398-113">移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer Tutorial 選択**EDI Inbound Processing.sln**、順にクリックします**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="9e398-113">Move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial, select **EDI Inbound Processing.sln**, and then click **Open**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9e398-114">このトピックは、EDI スキーマ、パイプライン、およびオーケストレーションを含む BizTalk EDI アプリケーションに別のアプリケーションから参照を既に追加していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="9e398-114">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="9e398-115">そうでない場合は、次を参照してください。 [、BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)します。</span><span class="sxs-lookup"><span data-stu-id="9e398-115">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
3. <span data-ttu-id="9e398-116">右クリックし、 **Inbound_EDI**ソリューション エクスプ ローラーでプロジェクトを選び**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="9e398-116">Right-click the **Inbound_EDI** project in the Solution Explorer, and then select **Properties**.</span></span>  
  
4. <span data-ttu-id="9e398-117">コンソール ツリーで、 **Inbound_EDI プロパティ ページ**ダイアログ ボックスで、**展開**し、 **Server**フィールドは、コンピューター名が入力されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9e398-117">In the console tree of the **Inbound_EDI Property Pages** dialog box, select  **Deployment** and in the **Server** field ensure that your computer name is entered.</span></span>  
  
5. <span data-ttu-id="9e398-118">コンソール ツリーで、クリックして**署名**選び**アセンブリに署名**します。</span><span class="sxs-lookup"><span data-stu-id="9e398-118">In the console tree, click **Signing** and then select **Sign the assembly**.</span></span> <span data-ttu-id="9e398-119">**厳密なキー名のファイルを選択して**を選択します\<**新規.** \>入力**keyfile.snk**として、**キー ファイル名**します。</span><span class="sxs-lookup"><span data-stu-id="9e398-119">For **Choose a strong key name file**, select \<**New…**\> and enter  **keyfile.snk** as the **Key file name**.</span></span> <span data-ttu-id="9e398-120">クリア**キーファイルをパスワードで保護する**順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="9e398-120">Clear **Protect my key file with a password** and then click **OK**.</span></span>  
  
6. <span data-ttu-id="9e398-121">閉じる、 **Inbound_EDI プロパティ ページ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="9e398-121">Close the **Inbound_EDI Property Pages** dialog box.</span></span>  
  
### <a name="to-deploy-the-project"></a><span data-ttu-id="9e398-122">プロジェクトを展開するには</span><span class="sxs-lookup"><span data-stu-id="9e398-122">To deploy the project</span></span>  
  
1. <span data-ttu-id="9e398-123">ソリューション エクスプ ローラーで、 **X12_00401_850.xsd**スキーマ。</span><span class="sxs-lookup"><span data-stu-id="9e398-123">In Solution Explorer, double-click the **X12_00401_850.xsd** schema.</span></span> <span data-ttu-id="9e398-124">これが開くことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9e398-124">Confirm that it opens.</span></span>  
  
2. <span data-ttu-id="9e398-125">ソリューション エクスプ ローラーで、 **Inbound4010850_to_OrderFile.btm**マップします。</span><span class="sxs-lookup"><span data-stu-id="9e398-125">In Solution Explorer, double-click the **Inbound4010850_to_OrderFile.btm** map.</span></span> <span data-ttu-id="9e398-126">これが開くことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9e398-126">Confirm that it opens.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9e398-127">プロジェクトの Inbound4010850_to_OrderFile.btm マップにより、受信する 850 のテスト メッセージのデータが、OrderSystem フォルダー (\toOrderSystem) 宛ての送信 XML ファイルにマップされます。</span><span class="sxs-lookup"><span data-stu-id="9e398-127">The Inbound4010850_to_OrderFile.btm map in the project maps the data in the inbound 850 test message to the outbound XML file delivered to the OrderSystem folder (\toOrderSystem).</span></span>  
  
3. <span data-ttu-id="9e398-128">ソリューション エクスプ ローラーで右クリックし、 **Inbound_EDI**順に選択して**ビルド**プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="9e398-128">In Solution Explorer, right-click the **Inbound_EDI** project and select **Build** to build the project.</span></span>  
  
4. <span data-ttu-id="9e398-129">ソリューション エクスプ ローラーで右クリックし、 **Inbound_EDI**順に選択して**デプロイ**プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="9e398-129">In Solution Explorer, right-click the **Inbound_EDI** project and select **Deploy** to deploy the project.</span></span>  
  
5. <span data-ttu-id="9e398-130">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理**、 **BizTalk グループ**、**アプリケーション**、 \< **すべての成果物**\>選び**リソース**します。</span><span class="sxs-lookup"><span data-stu-id="9e398-130">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, \<**All Artifacts**\> and then select **Resources**.</span></span> <span data-ttu-id="9e398-131">いることを確認、 **Inbound_EDI**アセンブリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e398-131">Verify that the **Inbound_EDI** assembly is listed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9e398-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="9e398-132">Next Steps</span></span>  
 <span data-ttu-id="9e398-133">組織のパーティとビジネス プロファイルを構成する (**OrderSystem**)」の説明に従って、[手順 3。組織のパーティとビジネス プロファイルを構成します。](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)</span><span class="sxs-lookup"><span data-stu-id="9e398-133">You configure a party and business profile for your organization (**OrderSystem**), as described in [Step 3: Configure a Party and Business Profile for Your Organization](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e398-134">参照</span><span class="sxs-lookup"><span data-stu-id="9e398-134">See Also</span></span>  
 [<span data-ttu-id="9e398-135">ステップ 1: EDI インターフェイス開発チュートリアルを準備します。</span><span class="sxs-lookup"><span data-stu-id="9e398-135">Step 1: Prepare for the EDI Interface Developer Tutorial</span></span>](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)