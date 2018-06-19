---
title: '手順 8: ビルドと Contoso オーケストレーションの展開 |Microsoft ドキュメント'
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
ms.openlocfilehash: 706c5ab2b52d30aeedfba7b3e002dc637fcece93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209306"
---
# <a name="step-8-building-and-deploying-the-contoso-orchestration"></a><span data-ttu-id="019f3-102">手順 8: ビルドと Contoso オーケストレーションの展開</span><span class="sxs-lookup"><span data-stu-id="019f3-102">Step 8: Building and Deploying the Contoso Orchestration</span></span>
<span data-ttu-id="019f3-103">ここでは、オーケストレーション プロジェクトをビルドし、BizTalk 展開ウィザードを使用して展開します。</span><span class="sxs-lookup"><span data-stu-id="019f3-103">In this step, you build the Orchestration project and deploy it using the BizTalk Deployment Wizard.</span></span> <span data-ttu-id="019f3-104">これにより、アセンブリが構成データベースに追加され、グローバル アセンブリ キャッシュ (GAC) にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="019f3-104">This adds the assembly to the Configuration database and installs the assembly in the Global Assembly Cache (GAC).</span></span>  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a><span data-ttu-id="019f3-105">アセンブリに厳密な名前を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="019f3-105">To assign a strong name to your assembly</span></span>  
  
1.  <span data-ttu-id="019f3-106">ソリューション エクスプ ローラーで右クリックし、 **PrivateResponder**プロジェクトをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="019f3-106">In Solution Explorer, right-click the **PrivateResponder** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="019f3-107">PrivateResponder プロパティ ページ] ダイアログ ボックスで、[**アセンブリ**左側のペインからです。</span><span class="sxs-lookup"><span data-stu-id="019f3-107">In the PrivateResponder Property Pages dialog box, select **Assembly** from the left pane.</span></span>  
  
3.  <span data-ttu-id="019f3-108">右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして、**アセンブリ キー ファイル**、省略記号ボタンをクリックして (**.**).</span><span class="sxs-lookup"><span data-stu-id="019f3-108">In the right pane, scroll down to the **Strong name** section, click the field to the right of the **Assembly Key File**, and then click the ellipsis button (**…**).</span></span>  
  
4.  <span data-ttu-id="019f3-109">プロジェクト フォルダで、選択、 **FabConPriceAvail.snk**ファイルを開き、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="019f3-109">Locate your project folder, select the **FabConPriceAvail.snk** file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="019f3-110">右側のペインで選択**False**から、**アセンブリの遅延署名**ドロップ ダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="019f3-110">In the right pane, select **False** from the **Assembly Delay Sign** drop down list.</span></span>  
  
6.  <span data-ttu-id="019f3-111">をクリックして**OK**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="019f3-111">Click **OK** to save the changes.</span></span>  
  
### <a name="to-build-and-deploy-the-orchestration-project"></a><span data-ttu-id="019f3-112">オーケストレーション プロジェクトを構築および展開するには</span><span class="sxs-lookup"><span data-stu-id="019f3-112">To build and deploy the orchestration project</span></span>  
  
1.  <span data-ttu-id="019f3-113">ソリューション エクスプ ローラーで右クリックし、 **PrivateResponder**プロジェクトをクリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="019f3-113">In Solution Explorer, right-click the **PrivateResponder** project, and then click **Build**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="019f3-114">ビルド プロセス中に発生した警告は、すべて無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="019f3-114">You can safely ignore any warnings that occur during the build process.</span></span>  
  
2.  <span data-ttu-id="019f3-115">ビルドが完了すると、もう一度、プロジェクトを右クリックし、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="019f3-115">After the build has succeeded, right-click the project again, and then click **Deploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="019f3-116">参照</span><span class="sxs-lookup"><span data-stu-id="019f3-116">See Also</span></span>  
 [<span data-ttu-id="019f3-117">手順 9: Contoso オーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="019f3-117">Step 9: Starting the Contoso Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-9-starting-the-contoso-orchestration.md)