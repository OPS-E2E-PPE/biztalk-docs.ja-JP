---
title: "手順 1: 構築して、IDOC を受信するため vPrev BizTalk プロジェクトを配置 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- migration, building and deploying previous version of BizTalk project for receiving an IDOC
- migrating, building and deploying previous version of BizTalk project for receiving an IDOC
- migration
ms.assetid: ab6bdf9a-dca5-4acd-97b2-a9afe9792978
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f99971a421530e4901c8bbac6533809a0f2f273c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-build-and-deploy-the-vprev-biztalk-project-for-receiving-an-idoc"></a><span data-ttu-id="65fb0-102">手順 1: 構築して、IDOC を受信するため vPrev BizTalk プロジェクトを配置</span><span class="sxs-lookup"><span data-stu-id="65fb0-102">Step 1: Build and Deploy the vPrev BizTalk Project for Receiving an IDOC</span></span>
<span data-ttu-id="65fb0-103">![手順 1/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="65fb0-103">![Step 1 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="65fb0-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="65fb0-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="65fb0-105">**目標:**このステップでビルドして SAP システムから IDOC を受信する既存 vPrev BizTalk プロジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="65fb0-105">**Objective:** In this step, you build and deploy your existing vPrev BizTalk project to receive an IDOC from an SAP system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65fb0-106">VPrev BizTalk プロジェクトに変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="65fb0-106">You do not need to make any change to the vPrev BizTalk project.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="65fb0-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="65fb0-107">Prerequisites</span></span>  
 <span data-ttu-id="65fb0-108">SAP システムから ORDERS03 IDOC を受信する vPrev BizTalk プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="65fb0-108">You must have a vPrev BizTalk project to receive an ORDERS03 IDOC from an SAP system.</span></span>  
  
### <a name="to-build-and-deploy-the-vprev-biztalk-project"></a><span data-ttu-id="65fb0-109">ビルドして vPrev BizTalk プロジェクトを配置するには</span><span class="sxs-lookup"><span data-stu-id="65fb0-109">To build and deploy the vPrev BizTalk project</span></span>  
  
1.  <span data-ttu-id="65fb0-110">ビルドし、ソリューションの配置に必要な厳密な名前キー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="65fb0-110">Create a strong-name key file required to build and deploy the solution.</span></span> <span data-ttu-id="65fb0-111">厳密な名前キー ファイルを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="65fb0-111">To create a strong-name key file, do the following:</span></span>  
  
    1.  <span data-ttu-id="65fb0-112">Visual Studio コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="65fb0-112">Start Visual Studio Command Prompt.</span></span>  
  
    2.  <span data-ttu-id="65fb0-113">コマンド プロンプトで、キー ファイルを作成するフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="65fb0-113">At the command prompt navigate to the folder where you want to create the key file.</span></span> <span data-ttu-id="65fb0-114">たとえば、入力**cd C:\Sample**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="65fb0-114">For example, type **cd C:\Sample**, and then press ENTER.</span></span>  
  
    3.  <span data-ttu-id="65fb0-115">コマンド プロンプトで次のように入力します。 **sn-k\<キー ファイルの名前\>.snk**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="65fb0-115">At the command prompt, type **sn -k \<key file name\>.snk**, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="65fb0-116">ソリューション エクスプ ローラーで、BizTalk ソリューション名を右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="65fb0-116">Right-click the BizTalk solution name in Solution Explorer, and then click **Properties**.</span></span> <span data-ttu-id="65fb0-117">**プロパティ ページ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="65fb0-117">In the **Property Pages** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="65fb0-118">をクリックして**構成プロパティ**チェック ボックスを確認してください、左側のウィンドウから、**ビルド**と**展開**列を選択します。</span><span class="sxs-lookup"><span data-stu-id="65fb0-118">Click **Configuration Properties** from the left pane, and make sure the check boxes in the **Build** and **Deploy** columns are selected.</span></span>  
  
    2.  <span data-ttu-id="65fb0-119">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="65fb0-119">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="65fb0-120">ソリューション エクスプ ローラーで、BizTalk プロジェクトを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="65fb0-120">Right-click the BizTalk project in Solution Explorer, and then click **Properties**.</span></span> <span data-ttu-id="65fb0-121">**プロパティ ページ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="65fb0-121">In the **Property Pages** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="65fb0-122">左側のウィンドウで展開**共通プロパティ**アセンブリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="65fb0-122">In the left pane, expand **Common Properties**, and then click Assembly.</span></span>  
  
    2.  <span data-ttu-id="65fb0-123">右側のペインで下にある、**厳密な名前**カテゴリの**アセンブリ キー ファイル**プロパティ、先ほど作成したアセンブリ キー ファイルへのパスを提供します。</span><span class="sxs-lookup"><span data-stu-id="65fb0-123">In the right pane, under the **Strong name** category, for the **Assembly Key File** property, provide the path to the assembly key file you created earlier.</span></span>  
  
    3.  <span data-ttu-id="65fb0-124">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="65fb0-124">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="65fb0-125">ソリューション エクスプ ローラーでソリューション名を右クリックし、をクリックして**ソリューションのビルド**です。</span><span class="sxs-lookup"><span data-stu-id="65fb0-125">In Solution Explorer, right-click the solution name, and then click **Build Solution**.</span></span>  
  
5.  <span data-ttu-id="65fb0-126">正常にビルドできたら、ソリューション名を右クリックし、をクリックして**ソリューションの配置**です。</span><span class="sxs-lookup"><span data-stu-id="65fb0-126">After the solution successfully builds, right-click the solution name, and then click **Deploy Solution**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="65fb0-127">次の手順</span><span class="sxs-lookup"><span data-stu-id="65fb0-127">Next Steps</span></span>  
 <span data-ttu-id="65fb0-128">作成および構成する Wcf-custom 受信ポートと WCF ベースを使用して SAP システムから Idoc を受信するように構成[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]」の説明に従って、[手順 2: Wcf-custom 一方向受信ポートを構成](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="65fb0-128">Create and configure a WCF-Custom receive port and configure it to receive IDOCs from an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], as described in [Step 2: Configure a WCF-Custom One-way Receive Port](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65fb0-129">参照</span><span class="sxs-lookup"><span data-stu-id="65fb0-129">See Also</span></span>  
 [<span data-ttu-id="65fb0-130">チュートリアル 4: SAP の IDOC 受信 BizTalk プロジェクトを移行する</span><span class="sxs-lookup"><span data-stu-id="65fb0-130">Tutorial 4: Migrating an SAP Receive IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)