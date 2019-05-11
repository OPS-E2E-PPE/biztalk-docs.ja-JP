---
title: プロジェクト デザイナー:[展開] タブ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6cf82e112834dbacc021e3ce5564866a2e8cbbb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395616"
---
# <a name="project-designer-deployment-tab"></a><span data-ttu-id="f9b03-102">プロジェクト デザイナー:[展開] タブ</span><span class="sxs-lookup"><span data-stu-id="f9b03-102">Project Designer: Deployment Tab</span></span>
<span data-ttu-id="f9b03-103">**展開**プロジェクト デザイナーの [プロパティ] タブを使用する BizTalk プロジェクトの展開属性を構成できます。</span><span class="sxs-lookup"><span data-stu-id="f9b03-103">The **Deployment** property tab of the Project Designer allows you to configure the deployment attributes for the BizTalk project.</span></span> <span data-ttu-id="f9b03-104">両方を構成する必要があります、 **Server**と**構成データベース**(BizTalk 管理データベースとも呼ばれます) の展開を正常に行う一連のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="f9b03-104">You must configure both the **Server** and the **Configuration Database** (also known as the BizTalk Management database) properties as a set for deployment to be successful.</span></span>  
  
## <a name="application-name"></a><span data-ttu-id="f9b03-105">Application Name</span><span class="sxs-lookup"><span data-stu-id="f9b03-105">Application Name</span></span>  
 <span data-ttu-id="f9b03-106">アセンブリを展開する BizTalk アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="f9b03-106">Specify the BizTalk application in which to deploy the assembly.</span></span> <span data-ttu-id="f9b03-107">これが空の場合は、既定のアプリケーションに、プロジェクトに展開されています。</span><span class="sxs-lookup"><span data-stu-id="f9b03-107">If this is empty, the project will be deployed into the default application.</span></span>  
  
## <a name="configuration-database"></a><span data-ttu-id="f9b03-108">構成データベース</span><span class="sxs-lookup"><span data-stu-id="f9b03-108">Configuration Database</span></span>  
 <span data-ttu-id="f9b03-109">展開済みのアセンブリを BizTalk 構成データベースの名前を指定するのにには、このフィールドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9b03-109">You use this field to specify the name of the BizTalk Configuration database for the deployed assembly.</span></span> <span data-ttu-id="f9b03-110">これには、展開プロジェクトとして BizTalk プロジェクトを構成している場合は適用されます。</span><span class="sxs-lookup"><span data-stu-id="f9b03-110">This applies if you have configured the BizTalk project as a deployment project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9b03-111">BizTalk 構成データベースは、BizTalk 管理データベースとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f9b03-111">The BizTalk Configuration database is also referred to as the BizTalk Management database.</span></span>  
  
 <span data-ttu-id="f9b03-112">既定の構成データベース名には、BizTalkMgmtDb です。</span><span class="sxs-lookup"><span data-stu-id="f9b03-112">The default Configuration database name is BizTalkMgmtDb.</span></span>  
  
## <a name="server"></a><span data-ttu-id="f9b03-113">[サーバー]</span><span class="sxs-lookup"><span data-stu-id="f9b03-113">Server</span></span>  
 <span data-ttu-id="f9b03-114">これは、構成リポジトリ (BizTalk 管理または構成データベースとも呼ばれます) が配置されているサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="f9b03-114">This is the name of the server where the Configuration repository (also known as the BizTalk Management or Configuration database) is located.</span></span> <span data-ttu-id="f9b03-115">"Deployment"として BizTalk プロジェクトを構成する場合、このサーバーに BizTalk プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="f9b03-115">You deploy the BizTalk project to this server if you configure the BizTalk project as "Deployment."</span></span>  
  
## <a name="redeploy"></a><span data-ttu-id="f9b03-116">再デプロイする.</span><span class="sxs-lookup"><span data-stu-id="f9b03-116">Redeploy</span></span>  
 <span data-ttu-id="f9b03-117">使用する、**再デプロイ**プロパティを既存の構成を削除して、アセンブリを配置するたびに、構成を再作成するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="f9b03-117">You use the **Redeploy** property to determine whether to delete the existing configuration and re-create the configuration each time you deploy the assembly.</span></span> <span data-ttu-id="f9b03-118">既定値は `True` です。</span><span class="sxs-lookup"><span data-stu-id="f9b03-118">The default value is `True`.</span></span>  
  
## <a name="install-to-global-assembly-cache"></a><span data-ttu-id="f9b03-119">[グローバル アセンブリ キャッシュにインストール]</span><span class="sxs-lookup"><span data-stu-id="f9b03-119">Install to Global Assembly Cache</span></span>  
 <span data-ttu-id="f9b03-120">使用する、**グローバル アセンブリ キャッシュにインストール**プロパティを指定する場合を[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9b03-120">You use the **Install to Global Assembly Cache** property to indicate if [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] needs to install the BizTalk assembly to the global assembly cache (GAC).</span></span>  
  
## <a name="restart-host-instances"></a><span data-ttu-id="f9b03-121">ホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f9b03-121">Restart Host Instances</span></span>  
 <span data-ttu-id="f9b03-122">設定した場合**ホスト インスタンスを再起動**に**True**、によって、プロジェクトが配置されると、ローカル コンピューター上のホスト インスタンスが再起動されます[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f9b03-122">If you set **Restart Host Instances** to **True**, the host instances on the local computer will be restarted when the project is deployed by [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="f9b03-123">これは変更を加えると、頻繁に再展開; するは、開発サイクル中に便利です。関連するホスト インスタンスを手動で再起動することはありません。</span><span class="sxs-lookup"><span data-stu-id="f9b03-123">This is useful during the development cycle when you are making changes and frequently redeploying; you will not have to manually restart related host instances.</span></span>  
  
 <span data-ttu-id="f9b03-124">関連するホスト インスタンスを再起動しないと場合、最新の変更可能性がありますが反映されません、BizTalk アプリケーションで、以前のバージョンがキャッシュに残っているため。</span><span class="sxs-lookup"><span data-stu-id="f9b03-124">If you do not restart related host instances, your latest changes may not be reflected in your BizTalk application because the old version may still be cached.</span></span> <span data-ttu-id="f9b03-125">キャッシュされたアセンブリを削除するホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f9b03-125">Restarting the host instance purges cached assemblies.</span></span>  
  
## <a name="enable-unit-testing"></a><span data-ttu-id="f9b03-126">単体テストを有効にする</span><span class="sxs-lookup"><span data-stu-id="f9b03-126">Enable Unit Testing</span></span>  
 <span data-ttu-id="f9b03-127">プロジェクト用の単体テストを有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f9b03-127">Specified whether to enable unit testing for the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9b03-128">参照</span><span class="sxs-lookup"><span data-stu-id="f9b03-128">See Also</span></span>  
 <span data-ttu-id="f9b03-129">[Visual Studio から BizTalk アセンブリを展開する方法](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="f9b03-129">[How to Deploy a BizTalk Assembly from Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span></span>  
 [<span data-ttu-id="f9b03-130">BizTalk プロジェクトのプロパティ ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="f9b03-130">BizTalk Project Properties Window</span></span>](../core/biztalk-project-properties-window.md)