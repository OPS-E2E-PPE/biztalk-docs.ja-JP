---
title: 手順 3 e:ビルドし、BizTalk Server ソリューションの配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbfc382b-ed4a-4401-9343-be1bffd747c9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ab07af6e0937ff015acc4acdd4e0ad116ea72a8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392591"
---
# <a name="step-3e-build-and-deploy-the-biztalk-server-solution"></a><span data-ttu-id="47181-102">手順 3 e:BizTalk Server ソリューション ビルドしてデプロイ</span><span class="sxs-lookup"><span data-stu-id="47181-102">Step 3e: Build and Deploy the BizTalk Server Solution</span></span>
<span data-ttu-id="47181-103">このトピックでは、2 つをデプロイする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト (**BtsSalesforceIntegration**と**CustomPipeline**)、前の手順で作成しました。</span><span class="sxs-lookup"><span data-stu-id="47181-103">In this topic, we’ll deploy the two [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] projects (**BtsSalesforceIntegration** and **CustomPipeline**) that we created in the earlier steps.</span></span>  
  
### <a name="to-build-and-deploy-the-biztalk-server-projects"></a><span data-ttu-id="47181-104">構築および BizTalk Server プロジェクトをデプロイするには</span><span class="sxs-lookup"><span data-stu-id="47181-104">To build and deploy the BizTalk Server projects</span></span>  
  
1. <span data-ttu-id="47181-105">ソリューション エクスプ ローラーで右クリックし、 **BtsSalesforceIntegration** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトをクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="47181-105">In the Solution Explorer, right-click the **BtsSalesforceIntegration**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="47181-106">**展開** タブの**アプリケーション名**、入力**SalesforceIntegration**します。</span><span class="sxs-lookup"><span data-stu-id="47181-106">In the **Deployment** tab, for **Application Name**, enter **SalesforceIntegration**.</span></span> <span data-ttu-id="47181-107">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47181-107">Click **Save**.</span></span>  
  
3. <span data-ttu-id="47181-108">同様に、右クリックし、 **CustomPipeline** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトで、をクリックして**プロパティ**、し、**展開** タブの**アプリケーション名前**プロパティ、入力**SalesforceIntegration**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="47181-108">Similarly, right-click the **CustomPipeline**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, click **Properties**, and in the **Deployment** tab, for the **Application Name** property, enter **SalesforceIntegration** again.</span></span> <span data-ttu-id="47181-109">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47181-109">Click **Save**.</span></span> <span data-ttu-id="47181-110">これにより、カスタム パイプライン コンポーネントが同じアプリケーションとしてデプロイされる、 **BtsSalesforceIntegration**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="47181-110">This ensures that the custom pipeline component is deployed to the same application as the **BtsSalesforceIntegration** project.</span></span>  
  
4. <span data-ttu-id="47181-111">ソリューション エクスプ ローラーでソリューション名を右クリックし、をクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="47181-111">Right-click the solution name in the Solution Explorer, and click **Properties**.</span></span> <span data-ttu-id="47181-112">[ソリューション プロパティ ページ] ダイアログ ボックスで、**構成プロパティ**、ことを確認します、**ビルド**と**デプロイ**チェック ボックスがオンの両方**BtsSalesforceIntegration**と**CustomPipeline**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="47181-112">In the Solution Property Pages dialog box, click **Configuration Properties**, and verify that the **Build** and **Deploy** check boxes are selected both for **BtsSalesforceIntegration** and **CustomPipeline** projects.</span></span>  
  
5. <span data-ttu-id="47181-113">ソリューション エクスプ ローラーでソリューション名を右クリックし、をクリックし、**ソリューションのビルド**します。</span><span class="sxs-lookup"><span data-stu-id="47181-113">Right-click the solution name in the Solution Explorer and then click **Build Solution**.</span></span> <span data-ttu-id="47181-114">ソリューション名を右クリックし、もう一度、ソリューションが正常にビルド、クリックして**ソリューションの配置**します。</span><span class="sxs-lookup"><span data-stu-id="47181-114">After the solution builds successfully, right-click the solution name again, and then click **Deploy Solution**.</span></span> <span data-ttu-id="47181-115">ソリューションをデプロイ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="47181-115">The solution is deployed to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47181-116">参照</span><span class="sxs-lookup"><span data-stu-id="47181-116">See Also</span></span>  
 [<span data-ttu-id="47181-117">ステップ 3:Visual Studio で BizTalk Server ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="47181-117">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)