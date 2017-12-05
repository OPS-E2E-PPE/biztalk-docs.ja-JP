---
title: "ソリューション ビルド構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c48791d26842b7224bb950334d6b184452a54d6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="solution-build-configurations"></a><span data-ttu-id="12178-102">ソリューション ビルドの構成</span><span class="sxs-lookup"><span data-stu-id="12178-102">Solution Build Configurations</span></span>
<span data-ttu-id="12178-103">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でビルドする他のプロジェクトと同様に、構成マネージャーを使用して、ソリューション ビルドの構成を指定できます。</span><span class="sxs-lookup"><span data-stu-id="12178-103">As with other projects that you build in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], you can use Configuration Manager to specify solution build configurations.</span></span> <span data-ttu-id="12178-104">ソリューション ビルド構成を使用すると、ソリューションのビルドでどのプロジェクトに含めると、それを展開するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="12178-104">Solution build configurations enable you to determine which projects to include in builds of a solution and if they will be deployed.</span></span> <span data-ttu-id="12178-105">BizTalk Server では、両方がサポート**デバッグ**と**リリース**の構成をビルドします。</span><span class="sxs-lookup"><span data-stu-id="12178-105">BizTalk Server supports both **Debug** and **Release** build configurations.</span></span>  
  
 <span data-ttu-id="12178-106">ソリューション ビルド構成のチェック マークと、**ビルド**列を使用するソリューションを構築してが完了したら、アセンブリを生成します。</span><span class="sxs-lookup"><span data-stu-id="12178-106">A solution build configuration with a check mark in the **Build** column enables you to build a solution and to generate an assembly when you are finished.</span></span> <span data-ttu-id="12178-107">チェック マークはでもある場合、**展開**プロジェクト デザイナーでの展開設定に基づいて、列からアプリケーションが展開されます。</span><span class="sxs-lookup"><span data-stu-id="12178-107">If a check mark is also present in the **Deploy** column, then the application will be deployed based on deployment settings in the Project Designer.</span></span>  
  
 <span data-ttu-id="12178-108">Configuration Manager と構成の完全なリファレンス [オプション] ダイアログ ボックスでボックスにある次のリファレンス リンク提供: [http://go.microsoft.com/fwlink/?LinkId=125365](http://go.microsoft.com/fwlink/?LinkId=125365)です。</span><span class="sxs-lookup"><span data-stu-id="12178-108">A complete reference to Configuration Manager and the configuration options provided by the dialog box can be found at the following reference link: [http://go.microsoft.com/fwlink/?LinkId=125365](http://go.microsoft.com/fwlink/?LinkId=125365).</span></span>  
  
### <a name="to-configure-build-properties-in-configuration-manager"></a><span data-ttu-id="12178-109">構成マネージャーでビルド プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="12178-109">To configure build properties in Configuration Manager</span></span>  
  
1.  <span data-ttu-id="12178-110">**[ビルド]** メニューの **[構成マネージャー]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12178-110">On the **Build** menu, click **Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="12178-111">**Configuration Manager**ダイアログ ボックスで、ビルド プロパティを構成するには次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="12178-111">In the **Configuration Manager** dialog box, select one of following to configure the build properties.</span></span>  
  
    |<span data-ttu-id="12178-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="12178-112">Use this</span></span>|<span data-ttu-id="12178-113">目的</span><span class="sxs-lookup"><span data-stu-id="12178-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="12178-114">**Configuration**</span><span class="sxs-lookup"><span data-stu-id="12178-114">**Configuration**</span></span>|<span data-ttu-id="12178-115">選択**リリース**または**デバッグ**プロジェクトの構成。</span><span class="sxs-lookup"><span data-stu-id="12178-115">Choose from **Release** or **Debug** configurations for the project.</span></span> <span data-ttu-id="12178-116">または、新しい構成を作成するか、既存の構成を編集します。</span><span class="sxs-lookup"><span data-stu-id="12178-116">Alternatively, create a new configuration or edit an existing one.</span></span>|  
    |<span data-ttu-id="12178-117">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="12178-117">**Platform**</span></span>|<span data-ttu-id="12178-118">コンパイルしたアセンブリの CPU アーキテクチャを表す、プロジェクトのプラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="12178-118">Choose a platform for the project representing the CPU architecture of the compiled assembly.</span></span> <span data-ttu-id="12178-119">または、新しいプラットフォームを作成するか、既存のプラットフォームを編集します。</span><span class="sxs-lookup"><span data-stu-id="12178-119">Alternatively, create a new platform or edit an existing one.</span></span>|  
    |<span data-ttu-id="12178-120">**ビルド**</span><span class="sxs-lookup"><span data-stu-id="12178-120">**Build**</span></span>|<span data-ttu-id="12178-121">プロジェクトをビルドするか、ソリューションのビルド コマンドに対応してリビルドするには、プロジェクトのこの列のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="12178-121">Check the box in this column for a project to have the project built or rebuilt in response to a build command for the solution.</span></span>|  
    |<span data-ttu-id="12178-122">**配置**</span><span class="sxs-lookup"><span data-stu-id="12178-122">**Deploy**</span></span>|<span data-ttu-id="12178-123">ソリューションまたはプロジェクトに対してビルド コマンドが実行されたときにプロジェクトを展開設定に基づいて展開するには、この列のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="12178-123">Check the box in this column to have the project deployed based on deployment settings when a build command is issued for the solution or project.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="12178-124">参照</span><span class="sxs-lookup"><span data-stu-id="12178-124">See Also</span></span>  
 <span data-ttu-id="12178-125">[Visual Studio から BizTalk アセンブリを展開する方法](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="12178-125">[How to Deploy a BizTalk Assembly from Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span></span>  
 [<span data-ttu-id="12178-126">BizTalk プロジェクトを作成する方法</span><span class="sxs-lookup"><span data-stu-id="12178-126">How to Create BizTalk Projects</span></span>](../core/how-to-create-biztalk-projects.md)