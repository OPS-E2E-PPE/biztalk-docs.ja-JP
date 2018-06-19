---
title: 'シナリオ: 新しいアプリケーションの展開 |Microsoft ドキュメント'
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
ms.openlocfilehash: 938767237d21b74829c786bdd5d57c7d9df15c2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269210"
---
# <a name="scenario-deploying-a-new-application"></a><span data-ttu-id="4f9eb-102">新しいアプリケーションの展開シナリオ。</span><span class="sxs-lookup"><span data-stu-id="4f9eb-102">Scenario: Deploying a New Application</span></span>
<span data-ttu-id="4f9eb-103">このトピックでは、これまで展開したことのない新しい環境にアプリケーションを展開するシナリオについて説明します。たとえば、ステージング環境で構成済みのアプリケーションを実稼働環境に展開する場合などです。</span><span class="sxs-lookup"><span data-stu-id="4f9eb-103">This topic describes the scenario of deploying an application into a new environment where it has not been deployed before; for example, deploying an application that has been configured in a staging environment into a production environment.</span></span>  
  
 <span data-ttu-id="4f9eb-104">」の説明に従って[、アプリケーションの展開プロセス](../core/the-application-deployment-process.md)間、1 つの環境からアプリケーションを移動するときに、アプリケーションの .msi ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="4f9eb-104">As described in [The Application Deployment Process](../core/the-application-deployment-process.md), when you want to move an application from one environment to another, you export the application into an .msi file.</span></span> <span data-ttu-id="4f9eb-105">その後、新しい環境で BizTalk グループに .msi ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="4f9eb-105">You then import the .msi file into the BizTalk group in the new environment.</span></span> <span data-ttu-id="4f9eb-106">また、アプリケーションを実行するグループ内のコンピューターに、アプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4f9eb-106">You also install the application on the computers in that group that will run the application.</span></span> <span data-ttu-id="4f9eb-107">アプリケーションが機能するためには、アプリケーションを実行する各コンピューターにインストールしてからアプリケーションを起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f9eb-107">Before it can begin functioning, you must install the application on each computer that will run it and also start the application.</span></span>  
  
 <span data-ttu-id="4f9eb-108">次の図では、アプリケーション 1 が .msi ファイルから BizTalk グループ B にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="4f9eb-108">In the following diagram, Application1 is imported from an .msi file into BizTalk Group B.</span></span>  
  
 <span data-ttu-id="4f9eb-109">![BizTalk アプリケーションを配置する](../core/media/deployapplication.gif "DeployApplication")</span><span class="sxs-lookup"><span data-stu-id="4f9eb-109">![Deploying a BizTalk application](../core/media/deployapplication.gif "DeployApplication")</span></span>  
  
 <span data-ttu-id="4f9eb-110">これにより、以下のようにアイテムがさまざまな BizTalk Server データベースにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="4f9eb-110">This imports artifacts into the various BizTalk Server databases as follows:</span></span>  
  
-   <span data-ttu-id="4f9eb-111">BizTalk アセンブリ、.NET アセンブリ、バインド、バインド ファイル、BAM テンプレート、COM コンポーネント、証明書、テキスト ファイルは、すべて BizTalk 管理データベースに追加されます。</span><span class="sxs-lookup"><span data-stu-id="4f9eb-111">The BizTalk assembly, .NET assembly, bindings, binding file, BAM template, COM component, certificate, and text file are all added to the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="4f9eb-112">ポリシーとボキャブラリは、ルール エンジン データベースに追加されます。</span><span class="sxs-lookup"><span data-stu-id="4f9eb-112">The policy and vocabulary are added to the Rule Engine database.</span></span>  
  
-   <span data-ttu-id="4f9eb-113">BAM テンプレートと BAM 定義ファイルは、どちらも BAM プライマリ インポート データベースに追加されます。</span><span class="sxs-lookup"><span data-stu-id="4f9eb-113">The BAM template and BAM definition file are both added to the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="4f9eb-114">また、これらの各アイテムは、BizTalk 管理データベース内でアプリケーション 1 に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="4f9eb-114">Each of these artifacts is also associated with Application1 in the BizTalk Management database.</span></span>  
  
 <span data-ttu-id="4f9eb-115">ローカル コンピューターにも、.msi ファイルからアプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4f9eb-115">The application is also installed on a local computer from the .msi file.</span></span> <span data-ttu-id="4f9eb-116">これにより、以下のように .msi ファイルに格納されているさまざまなアイテムがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4f9eb-116">This installs various artifacts that are included in the .msi file, as follows:</span></span>  
  
-   <span data-ttu-id="4f9eb-117">VirtualDirectory という名前の仮想ディレクトリが、インターネット インフォメーション サービス (IIS) メタベース内に作成されます。</span><span class="sxs-lookup"><span data-stu-id="4f9eb-117">The virtual directory, named VirtualDirectory, is created in the Internet Information Services (IIS) metabase.</span></span>  
  
-   <span data-ttu-id="4f9eb-118">証明書がローカル証明書ストアに追加されます。</span><span class="sxs-lookup"><span data-stu-id="4f9eb-118">The certificate is added to the local certificate store.</span></span>  
  
-   <span data-ttu-id="4f9eb-119">テキスト ファイルと COM コンポーネントが、ローカル ファイル システムにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="4f9eb-119">The text file and COM component are copied to the local file system.</span></span>  
  
-   <span data-ttu-id="4f9eb-120">BizTalk アセンブリと .NET アセンブリが、グローバル アセンブリ キャッシュ (GAC) に追加されます (この展開オプションが選択された場合)。</span><span class="sxs-lookup"><span data-stu-id="4f9eb-120">The BizTalk assembly and .NET assembly are added to the global assembly cache (GAC), if this deployment option was selected for them.</span></span>  
  
-   <span data-ttu-id="4f9eb-121">.NET アセンブリと COM コンポーネントが、Windows レジストリに追加されます (この展開オプションが選択された場合)。</span><span class="sxs-lookup"><span data-stu-id="4f9eb-121">The .NET assembly and COM component are added to the Windows registry, if that deployment option was selected for them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f9eb-122">参照</span><span class="sxs-lookup"><span data-stu-id="4f9eb-122">See Also</span></span>  
 <span data-ttu-id="4f9eb-123">[アプリケーションの展開と管理のシナリオ](../core/application-deployment-and-management-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="4f9eb-123">[Application Deployment and Management Scenarios](../core/application-deployment-and-management-scenarios.md) </span></span>  
 [<span data-ttu-id="4f9eb-124">BizTalk アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="4f9eb-124">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)