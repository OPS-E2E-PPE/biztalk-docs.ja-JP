---
title: 公開済み非 Visual Studio コンピューター上の Web サービスの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- deploying, Web services
- Web services, planning
- Web services, deploying
ms.assetid: e9f8e801-21f3-4458-b05c-206b72868916
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e7ccca1ad7e5b3d480e7075c059f11f51c28738
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389551"
---
# <a name="deploying-published-web-services-on-a-non-visual-studio-computer"></a><span data-ttu-id="d6f61-102">Visual Studio がインストールされていないコンピューターへの公開済み Web サービスの展開</span><span class="sxs-lookup"><span data-stu-id="d6f61-102">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>
<span data-ttu-id="d6f61-103">ないコンピューターで、公開済み Web サービスをデプロイする[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]Web セットアップ プロジェクトの作成、Web セットアップ パッケージ (.msi ファイル) の配布、以外に、パッケージをインストールする必要があります、インストールされている[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コンピューター、および、インストールされている構成Web サービスです。</span><span class="sxs-lookup"><span data-stu-id="d6f61-103">To deploy your published Web service on a computer that does not have [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] installed, you need to create a Web setup project, distribute the Web setup package (.msi file), install the package on the non-[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] computer, and configure the installed Web service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6f61-104">公開された Web サービス プロジェクトを含む BizTalk アプリケーションをパッケージ化する MSI ファイルを作成するのに BizTalk Server 管理コンソールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d6f61-104">You can also use BizTalk Server Administration Console to create MSI files packaging BizTalk Applications containing the published Web service projects.</span></span> <span data-ttu-id="d6f61-105">この MSI ファイルは、以外の Web サービス プロジェクトを展開できます[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="d6f61-105">This MSI files can be used to deploy the Web service projects on a Non [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Computer.</span></span> <span data-ttu-id="d6f61-106">BizTalk Server 管理コンソールを使用して MSI ファイルを作成する方法の詳細については、次を参照してください。 [BizTalk アプリケーションのエクスポート方法](../core/how-to-export-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="d6f61-106">For more information about how to create MSI files using BizTalk Server Administration console, see [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d6f61-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d6f61-107">In This Section</span></span>  
  
-   [<span data-ttu-id="d6f61-108">公開する Web サービスの Web セットアップを作成する方法</span><span class="sxs-lookup"><span data-stu-id="d6f61-108">How to Create a Web Setup for Your Published Web Service</span></span>](../core/how-to-create-a-web-setup-for-your-published-web-service.md)  
  
-   [<span data-ttu-id="d6f61-109">Web セットアップ パッケージを配布する方法</span><span class="sxs-lookup"><span data-stu-id="d6f61-109">How to Distribute the Web Setup Package</span></span>](../core/how-to-distribute-the-web-setup-package.md)  
  
-   [<span data-ttu-id="d6f61-110">Web セットアップ パッケージをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="d6f61-110">How to Install the Web Setup Package</span></span>](../core/how-to-install-the-web-setup-package.md)  
  
-   [<span data-ttu-id="d6f61-111">インストールされている Web サービスを構成する方法</span><span class="sxs-lookup"><span data-stu-id="d6f61-111">How to Configure the Installed Web Service</span></span>](../core/how-to-configure-the-installed-web-service.md)  
  
## <a name="see-also"></a><span data-ttu-id="d6f61-112">参照</span><span class="sxs-lookup"><span data-stu-id="d6f61-112">See Also</span></span>  
 [<span data-ttu-id="d6f61-113">BizTalk アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="d6f61-113">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)