---
title: "手順 2: 更新し、チュートリアルのソリューションを展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d03adfdd-1160-4e8c-a564-3acb2ecd0476
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca9f035eb97190c5a8999f73138d371e7dfddf98
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-update-and-deploy-the-tutorial-solution"></a><span data-ttu-id="69a05-102">手順 2: 更新し、チュートリアルのソリューションを展開</span><span class="sxs-lookup"><span data-stu-id="69a05-102">Step 2: Update and Deploy the Tutorial Solution</span></span>
<span data-ttu-id="69a05-103">![手順 2 の 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")</span><span class="sxs-lookup"><span data-stu-id="69a05-103">![Step 2 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")</span></span>  
  
 <span data-ttu-id="69a05-104">このステップでは、このチュートリアルのために用意されたソリューションを更新し、チュートリアルのアセンブリをビルドして展開します。</span><span class="sxs-lookup"><span data-stu-id="69a05-104">In this step you update the solution provided for this tutorial, and then build and deploy the tutorial assembly.</span></span> <span data-ttu-id="69a05-105">このチュートリアルで使用できるように、必要なスキーマ、カスタム送信パイプライン、およびマップは既に作成されています。</span><span class="sxs-lookup"><span data-stu-id="69a05-105">For the purposes of this tutorial, the necessary schema, custom send pipeline, and map have already been created.</span></span> <span data-ttu-id="69a05-106">マップは、850 の EDI データを注文システムで必要な形式に変換するために使用します。</span><span class="sxs-lookup"><span data-stu-id="69a05-106">The map is used to convert the 850 EDI data into the format required by your Order System.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="69a05-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="69a05-107">Prerequisites</span></span>  
 <span data-ttu-id="69a05-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="69a05-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-enable-the-edi-inbound-processing-solution-to-be-built-in-visual-studio"></a><span data-ttu-id="69a05-109">EDI 受信処理ソリューションを Visual Studio でビルドできるようにするには</span><span class="sxs-lookup"><span data-stu-id="69a05-109">To enable the EDI Inbound Processing solution to be built in Visual Studio</span></span>  
  
1.  <span data-ttu-id="69a05-110">開始**Microsoft Visual Studio**を管理者として。</span><span class="sxs-lookup"><span data-stu-id="69a05-110">Start **Microsoft Visual Studio** as an administrator.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="69a05-111">管理者特権を使用して Visual Studio を起動しないと、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にソリューションを展開しているときにエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69a05-111">If you do not start Visual Studio with administrator privileges, you will get an error while deploying the solution to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="69a05-112">Visual Studio で、[**ファイル**、] をポイント**開く**、順にクリック**プロジェクト/ソリューション**です。</span><span class="sxs-lookup"><span data-stu-id="69a05-112">In Visual Studio, click **File**, point to **Open**, and then click **Project/Solution**.</span></span> <span data-ttu-id="69a05-113">移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer Tutorial、select **EDI Inbound Processing.sln**、順にクリック**開く**です。</span><span class="sxs-lookup"><span data-stu-id="69a05-113">Move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial, select **EDI Inbound Processing.sln**, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="69a05-114">このトピックは、EDI スキーマ、パイプライン、およびオーケストレーションを含む BizTalk EDI アプリケーションに別のアプリケーションから参照を既に追加していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="69a05-114">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="69a05-115">いない場合を参照してください。[を BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)です。</span><span class="sxs-lookup"><span data-stu-id="69a05-115">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
3.  <span data-ttu-id="69a05-116">右クリックし、 **Inbound_EDI**ソリューション エクスプ ローラーでプロジェクトをクリックし **プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="69a05-116">Right-click the **Inbound_EDI** project in the Solution Explorer, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="69a05-117">コンソール ツリーで、 **Inbound_EDI プロパティ ページ**ダイアログ ボックスで、**展開**し、、**サーバー**フィールドでは、コンピューター名を入力することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="69a05-117">In the console tree of the **Inbound_EDI Property Pages** dialog box, select  **Deployment** and in the **Server** field ensure that your computer name is entered.</span></span>  
  
5.  <span data-ttu-id="69a05-118">コンソール ツリーでクリックして**署名**し、**アセンブリに署名**です。</span><span class="sxs-lookup"><span data-stu-id="69a05-118">In the console tree, click **Signing** and then select **Sign the assembly**.</span></span> <span data-ttu-id="69a05-119">**強力なキー名ファイルを選択して** \<**新規しています.**> を入力および**keyfile.snk**として、**キー ファイル名**です。</span><span class="sxs-lookup"><span data-stu-id="69a05-119">For **Choose a strong key name file**, select \<**New…**> and enter  **keyfile.snk** as the **Key file name**.</span></span> <span data-ttu-id="69a05-120">クリア**キーファイルをパスワードで保護する**順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="69a05-120">Clear **Protect my key file with a password** and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="69a05-121">閉じる、 **Inbound_EDI プロパティ ページ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="69a05-121">Close the **Inbound_EDI Property Pages** dialog box.</span></span>  
  
### <a name="to-deploy-the-project"></a><span data-ttu-id="69a05-122">プロジェクトを展開するには</span><span class="sxs-lookup"><span data-stu-id="69a05-122">To deploy the project</span></span>  
  
1.  <span data-ttu-id="69a05-123">ソリューション エクスプ ローラーで、 **X12_00401_850.xsd**スキーマです。</span><span class="sxs-lookup"><span data-stu-id="69a05-123">In Solution Explorer, double-click the **X12_00401_850.xsd** schema.</span></span> <span data-ttu-id="69a05-124">これが開くことを確認します。</span><span class="sxs-lookup"><span data-stu-id="69a05-124">Confirm that it opens.</span></span>  
  
2.  <span data-ttu-id="69a05-125">ソリューション エクスプ ローラーで、 **Inbound4010850_to_OrderFile.btm**マップします。</span><span class="sxs-lookup"><span data-stu-id="69a05-125">In Solution Explorer, double-click the **Inbound4010850_to_OrderFile.btm** map.</span></span> <span data-ttu-id="69a05-126">これが開くことを確認します。</span><span class="sxs-lookup"><span data-stu-id="69a05-126">Confirm that it opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="69a05-127">プロジェクトの Inbound4010850_to_OrderFile.btm マップにより、受信する 850 のテスト メッセージのデータが、OrderSystem フォルダー (\toOrderSystem) 宛ての送信 XML ファイルにマップされます。</span><span class="sxs-lookup"><span data-stu-id="69a05-127">The Inbound4010850_to_OrderFile.btm map in the project maps the data in the inbound 850 test message to the outbound XML file delivered to the OrderSystem folder (\toOrderSystem).</span></span>  
  
3.  <span data-ttu-id="69a05-128">ソリューション エクスプ ローラーで右クリックし、 **Inbound_EDI**プロジェクトを選択**ビルド**プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="69a05-128">In Solution Explorer, right-click the **Inbound_EDI** project and select **Build** to build the project.</span></span>  
  
4.  <span data-ttu-id="69a05-129">ソリューション エクスプ ローラーで右クリックし、 **Inbound_EDI**プロジェクトを選択**展開**プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="69a05-129">In Solution Explorer, right-click the **Inbound_EDI** project and select **Deploy** to deploy the project.</span></span>  
  
5.  <span data-ttu-id="69a05-130">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理コンソール**、 **BizTalk グループ**、**アプリケーション**、 \< **すべての成果物**> し、**リソース**です。</span><span class="sxs-lookup"><span data-stu-id="69a05-130">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, \<**All Artifacts**> and then select **Resources**.</span></span> <span data-ttu-id="69a05-131">いることを確認、 **Inbound_EDI**アセンブリが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="69a05-131">Verify that the **Inbound_EDI** assembly is listed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="69a05-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="69a05-132">Next Steps</span></span>  
 <span data-ttu-id="69a05-133">組織のパーティとビジネス プロファイルを構成する (**OrderSystem**)」の説明に従って、[手順 3: 組織のパーティとビジネス プロファイルを構成します。](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)</span><span class="sxs-lookup"><span data-stu-id="69a05-133">You configure a party and business profile for your organization (**OrderSystem**), as described in [Step 3: Configure a Party and Business Profile for Your Organization](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69a05-134">参照</span><span class="sxs-lookup"><span data-stu-id="69a05-134">See Also</span></span>  
 [<span data-ttu-id="69a05-135">手順 1: EDI インターフェイス開発チュートリアルの準備します。</span><span class="sxs-lookup"><span data-stu-id="69a05-135">Step 1: Prepare for the EDI Interface Developer Tutorial</span></span>](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)