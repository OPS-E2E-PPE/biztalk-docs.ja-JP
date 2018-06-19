---
title: '手順 1: 既存の Contoso ソリューションへの既存の BizTalk プロジェクトの追加 |Microsoft ドキュメント'
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
ms.openlocfilehash: 343bdf83d90d38a6fc0c626a65353c0185c43f6c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963952"
---
# <a name="step-1-adding-an-existing-biztalk-project-to-the-existing-contoso-solution"></a><span data-ttu-id="ed7c9-102">手順 1: 既存の Contoso ソリューションへの既存の BizTalk プロジェクトの追加</span><span class="sxs-lookup"><span data-stu-id="ed7c9-102">Step 1: Adding an Existing BizTalk Project to the Existing Contoso Solution</span></span>
<span data-ttu-id="ed7c9-103">[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK には、独自のプライベート プロセスをカスタマイズする際の適切な開始点として機能するプライベート プロセス オーケストレーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ed7c9-103">The [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK contains a private process orchestration that serves as a good starting point when customizing your own private process.</span></span> <span data-ttu-id="ed7c9-104">ここでは、ソリューションにこのオーケストレーションを追加し、アセンブリ名を変更して、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] インストールでインストールされた PrivateResponder オーケストレーションとの競合を回避します。</span><span class="sxs-lookup"><span data-stu-id="ed7c9-104">In this step, you add that orchestration to your solution and change the assembly name to avoid conflict with the PrivateResponder orchestration installed during the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] installation.</span></span> <span data-ttu-id="ed7c9-105">開始する前にで作成した Contoso ソリューションを開く[手順 1: Contoso Price and Availability Request の新しい BizTalk ソリューションの作成](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-new-biztalk-solution-for-contoso-price-and-availability-request.md)です。</span><span class="sxs-lookup"><span data-stu-id="ed7c9-105">Before you start, open the Contoso solution you created in [Step 1: Creating a New BizTalk Solution for the Contoso Price and Availability Request](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-new-biztalk-solution-for-contoso-price-and-availability-request.md).</span></span>  
  
### <a name="to-add-the-privateresponder-project-to-the-contoso-solution"></a><span data-ttu-id="ed7c9-106">PrivateResponder プロジェクトを Contoso ソリューションに追加するには</span><span class="sxs-lookup"><span data-stu-id="ed7c9-106">To add the PrivateResponder project to the Contoso solution</span></span>  
  
1.  <span data-ttu-id="ed7c9-107">Contoso ソリューションのフォルダーに PrivateResponder SDK サンプルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="ed7c9-107">Copy the PrivateResponder SDK sample to your Contoso solution folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ed7c9-108">既定では、PrivateResponder SDK サンプルは C:\Program files \microsoft BizTalk に格納\<バージョン\>Accelerator for rosettanet \sdk\privateresponder フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="ed7c9-108">By default, the PrivateResponder SDK sample is located in the C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\PrivateResponder folder.</span></span>  
  
2.  <span data-ttu-id="ed7c9-109">Visual Studio で、[**ファイル**、] をポイント**追加**、クリックして**既存のプロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="ed7c9-109">In Visual Studio, click **File**, point to **Add**, and then click **Existing Project**.</span></span>  
  
3.  <span data-ttu-id="ed7c9-110">既存のプロジェクトの追加 ダイアログ ボックスで、ソリューションのフォルダーに移動、 **PrivateResponder.btproj**プロジェクト ファイル、およびをクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="ed7c9-110">In the Add Existing Project dialog box, locate the folder for your solution, select the **PrivateResponder.btproj** project file, and then click **Open**.</span></span>  
  
### <a name="to-change-the-privateresponder-assembly-name-and-default-namespace"></a><span data-ttu-id="ed7c9-111">PrivateResponder アセンブリ名および既定の名前空間を変更するには</span><span class="sxs-lookup"><span data-stu-id="ed7c9-111">To change the PrivateResponder assembly name and default namespace</span></span>  
  
1.  <span data-ttu-id="ed7c9-112">ソリューション エクスプ ローラーで右クリックし、 **PrivateResponder**プロジェクトをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="ed7c9-112">In Solution Explorer, right click the **PrivateResponder** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ed7c9-113">[PrivateResponder プロパティ ページ] ダイアログ ボックスのコンソール ツリーで、**全般**です。</span><span class="sxs-lookup"><span data-stu-id="ed7c9-113">In the PrivateResponder Property Pages dialog box, in the console tree, click **General**.</span></span> <span data-ttu-id="ed7c9-114">詳細ウィンドウでの**アセンブリ名**ボックスに、入力**ContosoPriceAndAvailability.PrivateResponder**です。</span><span class="sxs-lookup"><span data-stu-id="ed7c9-114">In the details pane, in the **Assembly Name** box, type **ContosoPriceAndAvailability.PrivateResponder**.</span></span>  
  
3.  <span data-ttu-id="ed7c9-115">**Default Namespace**ボックスに、入力**ContosoPriceAndAvailability**です。</span><span class="sxs-lookup"><span data-stu-id="ed7c9-115">In the **Default Namespace** box, type **ContosoPriceAndAvailability**.</span></span>  
  
4.  <span data-ttu-id="ed7c9-116">をクリックして**OK** PrivateResponder プロパティ ページ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ed7c9-116">Click **OK** to close the PrivateResponder Property Pages dialog box.</span></span>  
  
5.  <span data-ttu-id="ed7c9-117">ソリューション エクスプ ローラーで、 **PrivateResponder.odx**です。</span><span class="sxs-lookup"><span data-stu-id="ed7c9-117">In Solution Explorer, double-click **PrivateResponder.odx**.</span></span>  
  
6.  <span data-ttu-id="ed7c9-118">**オーケストレーション**ウィンドウで、いることを確認**オーケストレーションのプロパティ**( **PrivateResponderProcess**) が選択されています。</span><span class="sxs-lookup"><span data-stu-id="ed7c9-118">In the **Orchestration View** window, ensure that **Orchestration Properties** (under **PrivateResponderProcess**) is selected.</span></span>  
  
7.  <span data-ttu-id="ed7c9-119">**プロパティ**ウィンドウで、 **Namespace**フィールドに「 **ContosoPriceAndAvailability**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="ed7c9-119">In the **Properties** window, in the **Namespace** field, type **ContosoPriceAndAvailability**, and then press **Enter**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed7c9-120">参照</span><span class="sxs-lookup"><span data-stu-id="ed7c9-120">See Also</span></span>  
 [<span data-ttu-id="ed7c9-121">手順 2: Contoso 用のボキャブラリの定義と公開</span><span class="sxs-lookup"><span data-stu-id="ed7c9-121">Step 2: Defining and Publishing the Vocabulary for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-defining-and-publishing-the-vocabulary-for-contoso.md)