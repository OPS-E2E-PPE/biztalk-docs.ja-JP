---
title: "プロジェクト デザイナー: [展開] タブ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties, Configuration database [BizTalk Server]
- Redeploy property
- configuration properties [deployment], Server property
- Server property
- configuration properties [deployment], Install to Global Assembly Cache (GAC) property
- properties, Management database
- Install to Global Assembly Cache (GAC) property
- Configuration database [BizTalk Server], properties
- Management database, properties
- Administration Group property
- configuration properties [deployment], Redeploy property
- configuration properties [deployment], Management database property
- configuration properties [deployment], Administration Group property
ms.assetid: 5b64f99c-4ec6-4ed3-8590-46420e2f75b8
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 972f3956a19d66d47238ee8170584b4faf6ba886
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="project-designer-deployment-tab"></a><span data-ttu-id="f757b-102">プロジェクト デザイナー: [展開] タブ</span><span class="sxs-lookup"><span data-stu-id="f757b-102">Project Designer: Deployment Tab</span></span>
<span data-ttu-id="f757b-103">**展開**プロジェクト デザイナーの [プロパティ] タブでは、BizTalk プロジェクトの配置の属性を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="f757b-103">The **Deployment** property tab of the Project Designer allows you to configure the deployment attributes for the BizTalk project.</span></span> <span data-ttu-id="f757b-104">両方を構成する必要があります、**サーバー**と**構成データベース**(BizTalk 管理データベースとも呼ばれます) 展開を成功させるのに設定されるプロパティです。</span><span class="sxs-lookup"><span data-stu-id="f757b-104">You must configure both the **Server** and the **Configuration Database** (also known as the BizTalk Management database) properties as a set for deployment to be successful.</span></span>  
  
## <a name="application-name"></a><span data-ttu-id="f757b-105">Application Name</span><span class="sxs-lookup"><span data-stu-id="f757b-105">Application Name</span></span>  
 <span data-ttu-id="f757b-106">アセンブリの展開先となる BizTalk アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="f757b-106">Specify the BizTalk application in which to deploy the assembly.</span></span> <span data-ttu-id="f757b-107">このフィールドを空にした場合、このプロジェクトは既定のアプリケーションに展開されます。</span><span class="sxs-lookup"><span data-stu-id="f757b-107">If this is empty, the project will be deployed into the default application.</span></span>  
  
## <a name="configuration-database"></a><span data-ttu-id="f757b-108">構成データベース</span><span class="sxs-lookup"><span data-stu-id="f757b-108">Configuration Database</span></span>  
 <span data-ttu-id="f757b-109">このフィールドでは、展開されたアセンブリに対して使用する BizTalk 構成データベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f757b-109">You use this field to specify the name of the BizTalk Configuration database for the deployed assembly.</span></span> <span data-ttu-id="f757b-110">BizTalk プロジェクトを展開プロジェクトとして構成した場合に必要となります。</span><span class="sxs-lookup"><span data-stu-id="f757b-110">This applies if you have configured the BizTalk project as a deployment project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f757b-111">BizTalk 構成データベースは BizTalk 管理データベースとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f757b-111">The BizTalk Configuration database is also referred to as the BizTalk Management database.</span></span>  
  
 <span data-ttu-id="f757b-112">既定の構成データベース名は、BizTalkMgmtDb です。</span><span class="sxs-lookup"><span data-stu-id="f757b-112">The default Configuration database name is BizTalkMgmtDb.</span></span>  
  
## <a name="server"></a><span data-ttu-id="f757b-113">[サーバー]</span><span class="sxs-lookup"><span data-stu-id="f757b-113">Server</span></span>  
 <span data-ttu-id="f757b-114">ここには、[構成] リポジトリ (BizTalk 管理データベースまたは構成データベース) が配置されているサーバーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f757b-114">This is the name of the server where the Configuration repository (also known as the BizTalk Management or Configuration database) is located.</span></span> <span data-ttu-id="f757b-115">BizTalk プロジェクトを "展開" として構成した場合、BizTalk プロジェクトをこのサーバーに展開します。</span><span class="sxs-lookup"><span data-stu-id="f757b-115">You deploy the BizTalk project to this server if you configure the BizTalk project as "Deployment."</span></span>  
  
## <a name="redeploy"></a><span data-ttu-id="f757b-116">再配置します。</span><span class="sxs-lookup"><span data-stu-id="f757b-116">Redeploy</span></span>  
 <span data-ttu-id="f757b-117">使用する、**再展開**プロパティを既存の構成を削除して、アセンブリを配置するたびに、構成を再作成するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="f757b-117">You use the **Redeploy** property to determine whether to delete the existing configuration and re-create the configuration each time you deploy the assembly.</span></span> <span data-ttu-id="f757b-118">既定値は`True`します。</span><span class="sxs-lookup"><span data-stu-id="f757b-118">The default value is `True`.</span></span>  
  
## <a name="install-to-global-assembly-cache"></a><span data-ttu-id="f757b-119">[グローバル アセンブリ キャッシュにインストール]</span><span class="sxs-lookup"><span data-stu-id="f757b-119">Install to Global Assembly Cache</span></span>  
 <span data-ttu-id="f757b-120">使用する、**グローバル アセンブリ キャッシュにインストール**プロパティを指定する場合を[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f757b-120">You use the **Install to Global Assembly Cache** property to indicate if [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] needs to install the BizTalk assembly to the global assembly cache (GAC).</span></span>  
  
## <a name="restart-host-instances"></a><span data-ttu-id="f757b-121">ホスト インスタンスを再起動します</span><span class="sxs-lookup"><span data-stu-id="f757b-121">Restart Host Instances</span></span>  
 <span data-ttu-id="f757b-122">設定した場合**ホスト インスタンスを再起動します**に**True**、によって、プロジェクトを配置するときに、ローカル コンピューター上のホスト インスタンスが再起動されます[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f757b-122">If you set **Restart Host Instances** to **True**, the host instances on the local computer will be restarted when the project is deployed by [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="f757b-123">この設定は、開発サイクルで、変更を行う場合や頻繁に再展開を実行する場合に役立ちます。この設定を使用すると、関連するホスト インスタンスを手動で再起動する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="f757b-123">This is useful during the development cycle when you are making changes and frequently redeploying; you will not have to manually restart related host instances.</span></span>  
  
 <span data-ttu-id="f757b-124">関連するホスト インスタンスを再起動しない場合、BizTalk アプリケーションに最新の変更が反映されないことがあります。これは、変更前の内容がキャッシュに残っている可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="f757b-124">If you do not restart related host instances, your latest changes may not be reflected in your BizTalk application because the old version may still be cached.</span></span> <span data-ttu-id="f757b-125">ホスト インスタンスを再起動すると、キャッシュされたアセンブリは削除されます。</span><span class="sxs-lookup"><span data-stu-id="f757b-125">Restarting the host instance purges cached assemblies.</span></span>  
  
## <a name="enable-unit-testing"></a><span data-ttu-id="f757b-126">単体テストを有効にする</span><span class="sxs-lookup"><span data-stu-id="f757b-126">Enable Unit Testing</span></span>  
 <span data-ttu-id="f757b-127">プロジェクトの単体テストを有効にするかどうかを指定しました。</span><span class="sxs-lookup"><span data-stu-id="f757b-127">Specified whether to enable unit testing for the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f757b-128">参照</span><span class="sxs-lookup"><span data-stu-id="f757b-128">See Also</span></span>  
 <span data-ttu-id="f757b-129">[Visual Studio から BizTalk アセンブリを展開する方法](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="f757b-129">[How to Deploy a BizTalk Assembly from Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span></span>  
 [<span data-ttu-id="f757b-130">BizTalk プロジェクトのプロパティ ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="f757b-130">BizTalk Project Properties Window</span></span>](../core/biztalk-project-properties-window.md)