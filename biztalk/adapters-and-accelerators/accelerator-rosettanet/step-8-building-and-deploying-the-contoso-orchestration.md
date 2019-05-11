---
title: 手順 8:Contoso オーケストレーションのビルドと |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, building solutions
- private process tutorial, deploying solutions
ms.assetid: d350b87a-0e4e-4837-ad39-fb5b1fdc1532
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68708976c91d96b3729b1a39776981d9345eb519
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280650"
---
# <a name="step-8-building-and-deploying-the-contoso-orchestration"></a><span data-ttu-id="47fb7-102">手順 8:ビルドと Contoso オーケストレーションの展開</span><span class="sxs-lookup"><span data-stu-id="47fb7-102">Step 8: Building and Deploying the Contoso Orchestration</span></span>
<span data-ttu-id="47fb7-103">この手順では、オーケストレーション プロジェクトをビルドし、BizTalk 展開ウィザードを使用して展開します。</span><span class="sxs-lookup"><span data-stu-id="47fb7-103">In this step, you build the Orchestration project and deploy it using the BizTalk Deployment Wizard.</span></span> <span data-ttu-id="47fb7-104">これは構成データベースにアセンブリを追加し、アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールします。</span><span class="sxs-lookup"><span data-stu-id="47fb7-104">This adds the assembly to the Configuration database and installs the assembly in the Global Assembly Cache (GAC).</span></span>  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a><span data-ttu-id="47fb7-105">アセンブリに厳密な名前を割り当てる</span><span class="sxs-lookup"><span data-stu-id="47fb7-105">To assign a strong name to your assembly</span></span>  
  
1.  <span data-ttu-id="47fb7-106">ソリューション エクスプ ローラーで右クリックし、 **PrivateResponder**プロジェクトをクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="47fb7-106">In Solution Explorer, right-click the **PrivateResponder** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="47fb7-107">PrivateResponder プロパティ ページ] ダイアログ ボックスで、[**アセンブリ**左側のウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="47fb7-107">In the PrivateResponder Property Pages dialog box, select **Assembly** from the left pane.</span></span>  
  
3.  <span data-ttu-id="47fb7-108">右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして、**アセンブリ キー ファイル**、省略記号ボタンをクリックし、(**.**).</span><span class="sxs-lookup"><span data-stu-id="47fb7-108">In the right pane, scroll down to the **Strong name** section, click the field to the right of the **Assembly Key File**, and then click the ellipsis button (**…**).</span></span>  
  
4.  <span data-ttu-id="47fb7-109">プロジェクト フォルダーを見つけ、選択、 **FabConPriceAvail.snk**ファイルを開き、をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="47fb7-109">Locate your project folder, select the **FabConPriceAvail.snk** file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="47fb7-110">右側のウィンドウで次のように選択します。 **False**から、**アセンブリの遅延署名**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="47fb7-110">In the right pane, select **False** from the **Assembly Delay Sign** drop down list.</span></span>  
  
6.  <span data-ttu-id="47fb7-111">**[OK]** をクリックして変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="47fb7-111">Click **OK** to save the changes.</span></span>  
  
### <a name="to-build-and-deploy-the-orchestration-project"></a><span data-ttu-id="47fb7-112">構築して、オーケストレーション プロジェクトをデプロイするには</span><span class="sxs-lookup"><span data-stu-id="47fb7-112">To build and deploy the orchestration project</span></span>  
  
1.  <span data-ttu-id="47fb7-113">ソリューション エクスプ ローラーで右クリックし、 **PrivateResponder**プロジェクトをクリックして**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="47fb7-113">In Solution Explorer, right-click the **PrivateResponder** project, and then click **Build**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="47fb7-114">ビルド処理中に発生した警告を無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="47fb7-114">You can safely ignore any warnings that occur during the build process.</span></span>  
  
2.  <span data-ttu-id="47fb7-115">ビルドが完了すると、もう一度、プロジェクトを右クリックし、クリックして**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="47fb7-115">After the build has succeeded, right-click the project again, and then click **Deploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47fb7-116">参照</span><span class="sxs-lookup"><span data-stu-id="47fb7-116">See Also</span></span>  
 [<span data-ttu-id="47fb7-117">手順 9:Contoso オーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="47fb7-117">Step 9: Starting the Contoso Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-9-starting-the-contoso-orchestration.md)