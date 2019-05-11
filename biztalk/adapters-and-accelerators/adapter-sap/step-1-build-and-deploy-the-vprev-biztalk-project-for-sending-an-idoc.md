---
title: 手順 1:ビルドおよび IDOC を送信するための vPrev BizTalk プロジェクトの配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, building and deploying previous version of BizTalk project for sending an IDOC
- migration
ms.assetid: 1982b318-45d1-464e-b7e4-65d459c439e3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0124195c3bd866ea16a2fd86f6aea16055ce86a2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372992"
---
# <a name="step-1-build-and-deploy-the-vprev-biztalk-project-for-sending-an-idoc"></a><span data-ttu-id="5b06b-102">手順 1:ビルドおよび IDOC を送信するための vPrev BizTalk プロジェクトの配置</span><span class="sxs-lookup"><span data-stu-id="5b06b-102">Step 1: Build and Deploy the vPrev BizTalk Project for Sending an IDOC</span></span>
<span data-ttu-id="5b06b-103">![ステップ 1/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="5b06b-103">![Step 1 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="5b06b-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="5b06b-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="5b06b-105">**目標:** この手順では、ビルドして、IDOC を SAP システムに送信する、既存の vPrev BizTalk プロジェクトの配置。</span><span class="sxs-lookup"><span data-stu-id="5b06b-105">**Objective:** In this step, you build and deploy your existing vPrev BizTalk project to send an IDOC to an SAP system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b06b-106">VPrev BizTalk プロジェクトに何も変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5b06b-106">You do not need to make any change to the vPrev BizTalk project.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5b06b-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="5b06b-107">Prerequisites</span></span>  
 <span data-ttu-id="5b06b-108">BOMDOC IDOC を SAP システムに送信する vPrev BizTalk プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="5b06b-108">You must have a vPrev BizTalk project to send a BOMDOC IDOC to an SAP system.</span></span>  
  
### <a name="to-build-and-deploy-the-vprev-biztalk-project"></a><span data-ttu-id="5b06b-109">ビルドおよび vPrev BizTalk プロジェクトを配置するには</span><span class="sxs-lookup"><span data-stu-id="5b06b-109">To build and deploy the vPrev BizTalk project</span></span>  
  
1.  <span data-ttu-id="5b06b-110">構築して、ソリューションをデプロイするために必要な厳密な名前キー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5b06b-110">Create a strong-name key file required to build and deploy the solution.</span></span> <span data-ttu-id="5b06b-111">厳密な名前キー ファイルを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5b06b-111">To create a strong-name key file, do the following:</span></span>  
  
    1.  <span data-ttu-id="5b06b-112">Visual Studio コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="5b06b-112">Start Visual Studio Command Prompt.</span></span>  
  
    2.  <span data-ttu-id="5b06b-113">コマンド プロンプトでは、キー ファイルを作成するフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="5b06b-113">At the command prompt navigate to the folder where you want to create the key file.</span></span> <span data-ttu-id="5b06b-114">たとえば、「 **cd C:\Sample**し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5b06b-114">For example, type **cd C:\Sample**, and then press ENTER.</span></span>  
  
    3.  <span data-ttu-id="5b06b-115">コマンド プロンプトで「 **sn-k\<キー ファイル名 > .snk**し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5b06b-115">At the command prompt, type **sn -k \<key file name>.snk**, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="5b06b-116">ソリューション エクスプ ローラーで、BizTalk ソリューション名を右クリックし、をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="5b06b-116">Right-click the BizTalk solution name in Solution Explorer, and then click **Properties**.</span></span> <span data-ttu-id="5b06b-117">**プロパティ ページ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5b06b-117">In the **Property Pages** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="5b06b-118">左側のウィンドウから構成プロパティをクリックし、チェック ボックスを**ビルド**と**デプロイ**列を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b06b-118">Click Configuration Properties from the left pane, and make sure the check boxes in the **Build** and **Deploy** columns are selected.</span></span>  
  
    2.  <span data-ttu-id="5b06b-119">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b06b-119">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="5b06b-120">ソリューション エクスプ ローラーで BizTalk プロジェクトを右クリックし、をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="5b06b-120">Right-click the BizTalk project in Solution Explorer, and then click **Properties**.</span></span> <span data-ttu-id="5b06b-121">**プロパティ ページ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5b06b-121">In the **Property Pages** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="5b06b-122">左側のウィンドウで展開**共通プロパティ**アセンブリを順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b06b-122">In the left pane, expand **Common Properties**, and then click Assembly.</span></span>  
  
    2.  <span data-ttu-id="5b06b-123">右側のウィンドウで 、**厳密な名前**カテゴリの**アセンブリ キー ファイル**プロパティ、先ほど作成したアセンブリ キー ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="5b06b-123">In the right pane, under the **Strong name** category, for the **Assembly Key File** property, provide the path to the assembly key file you created earlier.</span></span>  
  
    3.  <span data-ttu-id="5b06b-124">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b06b-124">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="5b06b-125">ソリューション エクスプ ローラーでソリューション名を右クリックし をクリックし、**ソリューションのビルド**します。</span><span class="sxs-lookup"><span data-stu-id="5b06b-125">In Solution Explorer, right-click the solution name, and then click **Build Solution**.</span></span>  
  
5.  <span data-ttu-id="5b06b-126">ソリューションが正常にビルドできたら、ソリューション名を右クリックし、**ソリューションの配置**します。</span><span class="sxs-lookup"><span data-stu-id="5b06b-126">After the solution successfully builds, right-click the solution name, and then click **Deploy Solution**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5b06b-127">次の手順</span><span class="sxs-lookup"><span data-stu-id="5b06b-127">Next Steps</span></span>  
 <span data-ttu-id="5b06b-128">作成、Wcf-custom 送信ポートを構成する WCF ベースを使用して SAP システムに Idoc を送信するように構成[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]」の説明に従って、[手順 2。Wcf-custom 一方向送信ポートを構成する](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-send-port.md)します。</span><span class="sxs-lookup"><span data-stu-id="5b06b-128">Create and configure a WCF-Custom send port and configure it to send IDOCs to an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], as described in [Step 2: Configure a WCF-Custom One-way Send Port](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b06b-129">参照</span><span class="sxs-lookup"><span data-stu-id="5b06b-129">See Also</span></span>  
 [<span data-ttu-id="5b06b-130">チュートリアル 3: SAP の IDOC 送信 BizTalk プロジェクトを移行する</span><span class="sxs-lookup"><span data-stu-id="5b06b-130">Tutorial 3: Migrating an SAP Send IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)