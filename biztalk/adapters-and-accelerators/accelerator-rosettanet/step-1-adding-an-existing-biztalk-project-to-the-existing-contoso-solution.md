---
title: 手順 1:既存の Contoso ソリューションへの既存の BizTalk プロジェクトの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects, adding to solutions
- private process tutorial, adding projects to solutions
ms.assetid: 9e84d282-01aa-4611-8462-c1acef234042
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a735dbd582d309f5927f66fd55d70227c7e3ca89
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281739"
---
# <a name="step-1-adding-an-existing-biztalk-project-to-the-existing-contoso-solution"></a><span data-ttu-id="4f474-102">手順 1:既存の Contoso ソリューションへの既存の BizTalk プロジェクトの追加</span><span class="sxs-lookup"><span data-stu-id="4f474-102">Step 1: Adding an Existing BizTalk Project to the Existing Contoso Solution</span></span>
<span data-ttu-id="4f474-103">The Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK には、独自のプライベート プロセスをカスタマイズする際に、適切な開始点として機能するプライベート プロセス オーケストレーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f474-103">The Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK contains a private process orchestration that serves as a good starting point when customizing your own private process.</span></span> <span data-ttu-id="4f474-104">この手順でそのオーケストレーションをソリューションに追加して中にインストールされた PrivateResponder オーケストレーションとの競合を避けるためにアセンブリ名を変更、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="4f474-104">In this step, you add that orchestration to your solution and change the assembly name to avoid conflict with the PrivateResponder orchestration installed during the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] installation.</span></span> <span data-ttu-id="4f474-105">開始する前で作成した Contoso ソリューションを開きます[手順 1。Contoso Price and Availability Request の新しい BizTalk ソリューションの作成](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-new-biztalk-solution-for-contoso-price-and-availability-request.md)です。</span><span class="sxs-lookup"><span data-stu-id="4f474-105">Before you start, open the Contoso solution you created in [Step 1: Creating a New BizTalk Solution for the Contoso Price and Availability Request](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-new-biztalk-solution-for-contoso-price-and-availability-request.md).</span></span>  
  
### <a name="to-add-the-privateresponder-project-to-the-contoso-solution"></a><span data-ttu-id="4f474-106">Contoso ソリューションに PrivateResponder プロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="4f474-106">To add the PrivateResponder project to the Contoso solution</span></span>  
  
1.  <span data-ttu-id="4f474-107">Contoso ソリューション フォルダーに PrivateResponder SDK サンプルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="4f474-107">Copy the PrivateResponder SDK sample to your Contoso solution folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4f474-108">既定では、PrivateResponder SDK サンプルは C:\Program files \microsoft BizTalk に格納\<バージョン\>Accelerator for rosettanet \sdk\privateresponder フォルダー。</span><span class="sxs-lookup"><span data-stu-id="4f474-108">By default, the PrivateResponder SDK sample is located in the C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\PrivateResponder folder.</span></span>  
  
2.  <span data-ttu-id="4f474-109">Visual Studio で、次のようにクリックします。**ファイル**、 をポイント**追加**、 をクリックし、**既存のプロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="4f474-109">In Visual Studio, click **File**, point to **Add**, and then click **Existing Project**.</span></span>  
  
3.  <span data-ttu-id="4f474-110">既存プロジェクトの追加 ダイアログ ボックスで、ソリューション フォルダーを探します、 **PrivateResponder.btproj**プロジェクト ファイル、およびクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="4f474-110">In the Add Existing Project dialog box, locate the folder for your solution, select the **PrivateResponder.btproj** project file, and then click **Open**.</span></span>  
  
### <a name="to-change-the-privateresponder-assembly-name-and-default-namespace"></a><span data-ttu-id="4f474-111">PrivateResponder アセンブリ名を変更し、既定の名前空間</span><span class="sxs-lookup"><span data-stu-id="4f474-111">To change the PrivateResponder assembly name and default namespace</span></span>  
  
1.  <span data-ttu-id="4f474-112">ソリューション エクスプ ローラーで右クリックし、 **PrivateResponder**プロジェクトをクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="4f474-112">In Solution Explorer, right click the **PrivateResponder** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="4f474-113">[PrivateResponder プロパティ ページ] ダイアログ ボックスのコンソール ツリーで**全般**します。</span><span class="sxs-lookup"><span data-stu-id="4f474-113">In the PrivateResponder Property Pages dialog box, in the console tree, click **General**.</span></span> <span data-ttu-id="4f474-114">詳細ペインでの**アセンブリ名**ボックスに「 **ContosoPriceAndAvailability.PrivateResponder**します。</span><span class="sxs-lookup"><span data-stu-id="4f474-114">In the details pane, in the **Assembly Name** box, type **ContosoPriceAndAvailability.PrivateResponder**.</span></span>  
  
3.  <span data-ttu-id="4f474-115">**既定 Namespace**ボックスに「 **ContosoPriceAndAvailability**します。</span><span class="sxs-lookup"><span data-stu-id="4f474-115">In the **Default Namespace** box, type **ContosoPriceAndAvailability**.</span></span>  
  
4.  <span data-ttu-id="4f474-116">クリックして**OK** PrivateResponder プロパティ ページ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4f474-116">Click **OK** to close the PrivateResponder Property Pages dialog box.</span></span>  
  
5.  <span data-ttu-id="4f474-117">ソリューション エクスプ ローラーでダブルクリック**PrivateResponder.odx**します。</span><span class="sxs-lookup"><span data-stu-id="4f474-117">In Solution Explorer, double-click **PrivateResponder.odx**.</span></span>  
  
6.  <span data-ttu-id="4f474-118">**オーケストレーション**ウィンドウで、いることを確認**オーケストレーションのプロパティ**( **PrivateResponderProcess**) が選択されています。</span><span class="sxs-lookup"><span data-stu-id="4f474-118">In the **Orchestration View** window, ensure that **Orchestration Properties** (under **PrivateResponderProcess**) is selected.</span></span>  
  
7.  <span data-ttu-id="4f474-119">**プロパティ**ウィンドウで、 **Namespace**フィールドに「 **[contosopriceandavailability]**、およびキーを押します **」と入力**します。</span><span class="sxs-lookup"><span data-stu-id="4f474-119">In the **Properties** window, in the **Namespace** field, type **ContosoPriceAndAvailability**, and then press **Enter**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f474-120">参照</span><span class="sxs-lookup"><span data-stu-id="4f474-120">See Also</span></span>  
 [<span data-ttu-id="4f474-121">手順 2:Contoso 用のボキャブラリの定義と公開</span><span class="sxs-lookup"><span data-stu-id="4f474-121">Step 2: Defining and Publishing the Vocabulary for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-defining-and-publishing-the-vocabulary-for-contoso.md)