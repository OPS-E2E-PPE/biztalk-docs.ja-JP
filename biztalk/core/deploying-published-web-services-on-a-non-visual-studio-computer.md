---
title: "非 Visual Studio コンピューター上の Web サービス公開を展開する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- deploying, Web services
- Web services, planning
- Web services, deploying
ms.assetid: e9f8e801-21f3-4458-b05c-206b72868916
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad894c257bdd2eed6462b63c0e921f78ca13c17e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-published-web-services-on-a-non-visual-studio-computer"></a><span data-ttu-id="9bedb-102">Visual Studio がインストールされていないコンピューターへの公開済み Web サービスの展開</span><span class="sxs-lookup"><span data-stu-id="9bedb-102">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>
<span data-ttu-id="9bedb-103">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] がインストールされていないコンピュータに公開済み Web サービスを展開するには、Web セットアップ プロジェクトの作成、Web セットアップ パッケージ (.msi ファイル) の配布、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] がインストールされていないコンピュータへのパッケージのインストール、およびインストールした Web サービスの構成を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bedb-103">To deploy your published Web service on a computer that does not have [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] installed, you need to create a Web setup project, distribute the Web setup package (.msi file), install the package on the non-[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] computer, and configure the installed Web service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9bedb-104">BizTalk Server 管理コンソールを使用して、公開済み Web サービス プロジェクトを含む BizTalk アプリケーションをパッケージ化した MSI ファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="9bedb-104">You can also use BizTalk Server Administration Console to create MSI files packaging BizTalk Applications containing the published Web service projects.</span></span> <span data-ttu-id="9bedb-105">この MSI ファイルを使用して、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] がインストールされていないコンピューターに Web サービス プロジェクトを展開できます。</span><span class="sxs-lookup"><span data-stu-id="9bedb-105">This MSI files can be used to deploy the Web service projects on a Non [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Computer.</span></span> <span data-ttu-id="9bedb-106">BizTalk Server 管理コンソールを使用して MSI ファイルを作成する方法の詳細については、次を参照してください。[を BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="9bedb-106">For more information about how to create MSI files using BizTalk Server Administration console, see [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9bedb-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9bedb-107">In This Section</span></span>  
  
-   [<span data-ttu-id="9bedb-108">公開された Web サービスの Web 設定を作成する方法</span><span class="sxs-lookup"><span data-stu-id="9bedb-108">How to Create a Web Setup for Your Published Web Service</span></span>](../core/how-to-create-a-web-setup-for-your-published-web-service.md)  
  
-   [<span data-ttu-id="9bedb-109">Web セットアップ パッケージを配布する方法</span><span class="sxs-lookup"><span data-stu-id="9bedb-109">How to Distribute the Web Setup Package</span></span>](../core/how-to-distribute-the-web-setup-package.md)  
  
-   [<span data-ttu-id="9bedb-110">Web セットアップ パッケージをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="9bedb-110">How to Install the Web Setup Package</span></span>](../core/how-to-install-the-web-setup-package.md)  
  
-   [<span data-ttu-id="9bedb-111">インストールされている Web サービスを構成する方法</span><span class="sxs-lookup"><span data-stu-id="9bedb-111">How to Configure the Installed Web Service</span></span>](../core/how-to-configure-the-installed-web-service.md)  
  
## <a name="see-also"></a><span data-ttu-id="9bedb-112">参照</span><span class="sxs-lookup"><span data-stu-id="9bedb-112">See Also</span></span>  
 [<span data-ttu-id="9bedb-113">BizTalk アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="9bedb-113">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)