---
title: シナリオ:新しいアプリケーションの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, applications
- applications, deploying
- deploying [applications], examples
- applications, examples
- examples, deploying
ms.assetid: 6d34a626-9fd4-4c33-a067-b66333eec01f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 932f8e8692b3f0d2061550bebbc7faf7a8175b2e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308575"
---
# <a name="scenario-deploying-a-new-application"></a><span data-ttu-id="bc712-102">シナリオ:新しいアプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="bc712-102">Scenario: Deploying a New Application</span></span>
<span data-ttu-id="bc712-103">このトピックでは、どこに展開されていない; の前に、新しい環境にアプリケーションのデプロイのシナリオを説明しますたとえば、運用環境にステージング環境で構成されているアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="bc712-103">This topic describes the scenario of deploying an application into a new environment where it has not been deployed before; for example, deploying an application that has been configured in a staging environment into a production environment.</span></span>  
  
 <span data-ttu-id="bc712-104">」の説明に従って[、アプリケーションの展開プロセス](../core/the-application-deployment-process.md)する間、1 つの環境からアプリケーションを移動する場合は、.msi ファイルにアプリケーションをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="bc712-104">As described in [The Application Deployment Process](../core/the-application-deployment-process.md), when you want to move an application from one environment to another, you export the application into an .msi file.</span></span> <span data-ttu-id="bc712-105">.Msi ファイルをインポートするには、新しい環境での BizTalk グループにします。</span><span class="sxs-lookup"><span data-stu-id="bc712-105">You then import the .msi file into the BizTalk group in the new environment.</span></span> <span data-ttu-id="bc712-106">また、アプリケーションをインストールするには、アプリケーションを実行しているそのグループ内のコンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="bc712-106">You also install the application on the computers in that group that will run the application.</span></span> <span data-ttu-id="bc712-107">機能する、前に実行され、アプリケーションを起動する各コンピューターにアプリケーションをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc712-107">Before it can begin functioning, you must install the application on each computer that will run it and also start the application.</span></span>  
  
 <span data-ttu-id="bc712-108">次の図では、Application1 は BizTalk グループ B にインポートを .msi ファイルからは、</span><span class="sxs-lookup"><span data-stu-id="bc712-108">In the following diagram, Application1 is imported from an .msi file into BizTalk Group B.</span></span>  
  
 <span data-ttu-id="bc712-109">![BizTalk アプリケーション展開](../core/media/deployapplication.gif "DeployApplication")</span><span class="sxs-lookup"><span data-stu-id="bc712-109">![Deploying a BizTalk application](../core/media/deployapplication.gif "DeployApplication")</span></span>  
  
 <span data-ttu-id="bc712-110">とおり: さまざまな BizTalk Server データベースにアイテムをインポートこれ</span><span class="sxs-lookup"><span data-stu-id="bc712-110">This imports artifacts into the various BizTalk Server databases as follows:</span></span>  
  
- <span data-ttu-id="bc712-111">BizTalk アセンブリ、.NET アセンブリ、バインド、バインド ファイル、BAM テンプレート、COM コンポーネント、証明書、およびテキスト ファイルはすべて BizTalk 管理データベースに追加します。</span><span class="sxs-lookup"><span data-stu-id="bc712-111">The BizTalk assembly, .NET assembly, bindings, binding file, BAM template, COM component, certificate, and text file are all added to the BizTalk Management database.</span></span>  
  
- <span data-ttu-id="bc712-112">ポリシーとボキャブラリは、ルール エンジン データベースに追加されます。</span><span class="sxs-lookup"><span data-stu-id="bc712-112">The policy and vocabulary are added to the Rule Engine database.</span></span>  
  
- <span data-ttu-id="bc712-113">BAM テンプレートと BAM 定義ファイル、BAM プライマリ インポート データベースに追加されます。</span><span class="sxs-lookup"><span data-stu-id="bc712-113">The BAM template and BAM definition file are both added to the BAM Primary Import database.</span></span>  
  
  <span data-ttu-id="bc712-114">これらの各アイテムも Application1 BizTalk 管理データベースに関連付けします。</span><span class="sxs-lookup"><span data-stu-id="bc712-114">Each of these artifacts is also associated with Application1 in the BizTalk Management database.</span></span>  
  
  <span data-ttu-id="bc712-115">アプリケーションは、.msi ファイルからローカル コンピューターにもインストールされます。</span><span class="sxs-lookup"><span data-stu-id="bc712-115">The application is also installed on a local computer from the .msi file.</span></span> <span data-ttu-id="bc712-116">これには、次のように、.msi ファイルに含まれるさまざまな成果物がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="bc712-116">This installs various artifacts that are included in the .msi file, as follows:</span></span>  
  
- <span data-ttu-id="bc712-117">VirtualDirectory という名前の仮想ディレクトリは、インターネット インフォメーション サービス (IIS) メタベースに作成されます。</span><span class="sxs-lookup"><span data-stu-id="bc712-117">The virtual directory, named VirtualDirectory, is created in the Internet Information Services (IIS) metabase.</span></span>  
  
- <span data-ttu-id="bc712-118">証明書は、ローカル証明書ストアに追加されます。</span><span class="sxs-lookup"><span data-stu-id="bc712-118">The certificate is added to the local certificate store.</span></span>  
  
- <span data-ttu-id="bc712-119">テキスト ファイルと COM コンポーネントは、ローカル ファイル システムにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="bc712-119">The text file and COM component are copied to the local file system.</span></span>  
  
- <span data-ttu-id="bc712-120">この展開オプションは、それらの選択した場合、BizTalk アセンブリと .NET アセンブリがグローバル アセンブリ キャッシュ (GAC) に追加されます。</span><span class="sxs-lookup"><span data-stu-id="bc712-120">The BizTalk assembly and .NET assembly are added to the global assembly cache (GAC), if this deployment option was selected for them.</span></span>  
  
- <span data-ttu-id="bc712-121">.NET アセンブリと COM コンポーネントは、それらの配置オプションを選択した場合、Windows レジストリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="bc712-121">The .NET assembly and COM component are added to the Windows registry, if that deployment option was selected for them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc712-122">参照</span><span class="sxs-lookup"><span data-stu-id="bc712-122">See Also</span></span>  
 <span data-ttu-id="bc712-123">[アプリケーションの展開と管理のシナリオ](../core/application-deployment-and-management-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="bc712-123">[Application Deployment and Management Scenarios](../core/application-deployment-and-management-scenarios.md) </span></span>  
 [<span data-ttu-id="bc712-124">BizTalk アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="bc712-124">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)