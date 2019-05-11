---
title: ソリューション ビルドの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Configuration Manager
- building, solutions
- building, Configuration Manager
- solutions, deploying
- deploying, building
- solutions, developing
- solutions, build configuration
ms.assetid: 6f2cce47-388d-4c93-9146-768f53b8207e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e67898e3e24b98f9efbe92494e0f7fbe28b2fba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244310"
---
# <a name="solution-build-configurations"></a><span data-ttu-id="1bee2-102">ソリューション ビルドの構成</span><span class="sxs-lookup"><span data-stu-id="1bee2-102">Solution Build Configurations</span></span>
<span data-ttu-id="1bee2-103">他のプロジェクトで作成すると同様[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューションのビルド構成を指定する Configuration Manager を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="1bee2-103">As with other projects that you build in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], you can use Configuration Manager to specify solution build configurations.</span></span> <span data-ttu-id="1bee2-104">ソリューション ビルドの構成に含めるには、どのプロジェクトがソリューションのビルドし、それを展開するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="1bee2-104">Solution build configurations enable you to determine which projects to include in builds of a solution and if they will be deployed.</span></span> <span data-ttu-id="1bee2-105">BizTalk Server は両方ともサポート**デバッグ**と**リリース**の構成をビルドします。</span><span class="sxs-lookup"><span data-stu-id="1bee2-105">BizTalk Server supports both **Debug** and **Release** build configurations.</span></span>  
  
 <span data-ttu-id="1bee2-106">ソリューション ビルド構成にあるチェック マークで、**ビルド**列を使用するソリューションを構築してが完了したら、アセンブリを生成します。</span><span class="sxs-lookup"><span data-stu-id="1bee2-106">A solution build configuration with a check mark in the **Build** column enables you to build a solution and to generate an assembly when you are finished.</span></span> <span data-ttu-id="1bee2-107">チェック ボックスもオンにする場合、**デプロイ**プロジェクト デザイナーでの展開設定に基づいて、列で、そのアプリケーションがデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="1bee2-107">If a check mark is also present in the **Deploy** column, then the application will be deployed based on deployment settings in the Project Designer.</span></span>  
  
 <span data-ttu-id="1bee2-108">Configuration Manager と、構成への参照を完全なオプション ダイアログ ボックスでボックスにある次の参照リンクの提供: [ http://go.microsoft.com/fwlink/?LinkId=125365](http://go.microsoft.com/fwlink/?LinkId=125365)します。</span><span class="sxs-lookup"><span data-stu-id="1bee2-108">A complete reference to Configuration Manager and the configuration options provided by the dialog box can be found at the following reference link: [http://go.microsoft.com/fwlink/?LinkId=125365](http://go.microsoft.com/fwlink/?LinkId=125365).</span></span>  
  
### <a name="to-configure-build-properties-in-configuration-manager"></a><span data-ttu-id="1bee2-109">Configuration Manager でのビルド プロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="1bee2-109">To configure build properties in Configuration Manager</span></span>  
  
1.  <span data-ttu-id="1bee2-110">**[ビルド]** メニューの **[構成マネージャー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1bee2-110">On the **Build** menu, click **Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="1bee2-111">**Configuration Manager**ダイアログ ボックスで、ビルド プロパティを構成するには次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="1bee2-111">In the **Configuration Manager** dialog box, select one of following to configure the build properties.</span></span>  
  
    |<span data-ttu-id="1bee2-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1bee2-112">Use this</span></span>|<span data-ttu-id="1bee2-113">目的</span><span class="sxs-lookup"><span data-stu-id="1bee2-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="1bee2-114">**Configuration**</span><span class="sxs-lookup"><span data-stu-id="1bee2-114">**Configuration**</span></span>|<span data-ttu-id="1bee2-115">選択**リリース**または**デバッグ**プロジェクトの構成。</span><span class="sxs-lookup"><span data-stu-id="1bee2-115">Choose from **Release** or **Debug** configurations for the project.</span></span> <span data-ttu-id="1bee2-116">新しい構成を作成または、既存のものを編集します。</span><span class="sxs-lookup"><span data-stu-id="1bee2-116">Alternatively, create a new configuration or edit an existing one.</span></span>|  
    |<span data-ttu-id="1bee2-117">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="1bee2-117">**Platform**</span></span>|<span data-ttu-id="1bee2-118">プロジェクトのコンパイル済みアセンブリの CPU アーキテクチャを表すためのプラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="1bee2-118">Choose a platform for the project representing the CPU architecture of the compiled assembly.</span></span> <span data-ttu-id="1bee2-119">新しいプラットフォームを作成または、既存のものを編集します。</span><span class="sxs-lookup"><span data-stu-id="1bee2-119">Alternatively, create a new platform or edit an existing one.</span></span>|  
    |<span data-ttu-id="1bee2-120">**ビルド**</span><span class="sxs-lookup"><span data-stu-id="1bee2-120">**Build**</span></span>|<span data-ttu-id="1bee2-121">プロジェクトのプロジェクトを作成またはソリューションのビルド コマンドへの応答で再作成するには、この列のボックスを確認します。</span><span class="sxs-lookup"><span data-stu-id="1bee2-121">Check the box in this column for a project to have the project built or rebuilt in response to a build command for the solution.</span></span>|  
    |<span data-ttu-id="1bee2-122">**配置**</span><span class="sxs-lookup"><span data-stu-id="1bee2-122">**Deploy**</span></span>|<span data-ttu-id="1bee2-123">デプロイ プロジェクトがある場合は、この列のボックスは、ソリューションまたはプロジェクトのビルド コマンドが発行されたときに展開の設定に基づく確認してください。</span><span class="sxs-lookup"><span data-stu-id="1bee2-123">Check the box in this column to have the project deployed based on deployment settings when a build command is issued for the solution or project.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1bee2-124">参照</span><span class="sxs-lookup"><span data-stu-id="1bee2-124">See Also</span></span>  
 <span data-ttu-id="1bee2-125">[Visual Studio から BizTalk アセンブリを展開する方法](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="1bee2-125">[How to Deploy a BizTalk Assembly from Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span></span>  
 [<span data-ttu-id="1bee2-126">BizTalk プロジェクトを作成する方法</span><span class="sxs-lookup"><span data-stu-id="1bee2-126">How to Create BizTalk Projects</span></span>](../core/how-to-create-biztalk-projects.md)