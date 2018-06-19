---
title: スクリプトを使用してアプリケーションを展開する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e683c5f-7576-4382-9952-d577cd00186c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bc96c3b591baf81806182b6c3e988a46dd208ba
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009675"
---
# <a name="using-scripts-to-deploy-applications"></a><span data-ttu-id="9de4d-102">スクリプトを使用してアプリケーションを展開するには</span><span class="sxs-lookup"><span data-stu-id="9de4d-102">Using Scripts to Deploy Applications</span></span>
<span data-ttu-id="9de4d-103">スクリプトを使用して、可能な場合は、BizTalk アプリケーションを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9de4d-103">You should use scripts to deploy BizTalk applications where possible.</span></span> <span data-ttu-id="9de4d-104">スクリプト、展開プロセス中に人的ミスのリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="9de4d-104">Scripting reduces the risk of human error during the deployment process.</span></span> <span data-ttu-id="9de4d-105">深さの展開手順も文書化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9de4d-105">You should also document your deployment procedures in depth.</span></span> <span data-ttu-id="9de4d-106">非常に詳細な手順とスクリプトのないものを文書化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9de4d-106">You should document anything that you do not script with very detailed steps.</span></span> <span data-ttu-id="9de4d-107">これには、外部システムと Microsoft 以外のコンポーネントの展開のすべての変更を文書化が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9de4d-107">This includes documenting any changes to external systems and to deployment of non-Microsoft components.</span></span>  
  
## <a name="using-btstask"></a><span data-ttu-id="9de4d-108">BTSTask の使用</span><span class="sxs-lookup"><span data-stu-id="9de4d-108">Using BTSTask</span></span>  
 <span data-ttu-id="9de4d-109">BTSTask.exe を使用するには、BizTalk アプリケーションにも既存のインポートについての作成をスクリプトに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].msi パッケージです。</span><span class="sxs-lookup"><span data-stu-id="9de4d-109">You can use BTSTask.exe to script the creation of BizTalk applications, as well as to import existing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] .msi packages.</span></span> <span data-ttu-id="9de4d-110">場合は、アプリケーションの作成をスクリプトに含めるし、パッケージに自動的に構築できますビルド サーバーで自動プロセスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="9de4d-110">If the creation of the applications is scripted, then the packages can be automatically built using an automated process on a build server.</span></span>  
  
 <span data-ttu-id="9de4d-111">BizTalk アプリケーションの展開をスクリプト作成の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9de4d-111">See the following topics for more information about scripting BizTalk application deployments:</span></span>  
  
-   <span data-ttu-id="9de4d-112">[展開して、BizTalk アプリケーションを管理する](http://go.microsoft.com/fwlink/?LinkId=154210)(http://go.microsoft.com/fwlink/?LinkId=154210)</span><span class="sxs-lookup"><span data-stu-id="9de4d-112">[Deploying and Managing BizTalk Applications](http://go.microsoft.com/fwlink/?LinkId=154210) (http://go.microsoft.com/fwlink/?LinkId=154210)</span></span>  
  
-   <span data-ttu-id="9de4d-113">[BizTalk Server アプリケーションの展開を理解する](http://go.microsoft.com/fwlink/?LinkId=101599)(http://go.microsoft.com/fwlink/?LinkId=101599)</span><span class="sxs-lookup"><span data-stu-id="9de4d-113">[Understanding BizTalk Server Application Deployment](http://go.microsoft.com/fwlink/?LinkId=101599) (http://go.microsoft.com/fwlink/?LinkId=101599)</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9de4d-114">この後者の記事は、BizTalk Server にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="9de4d-114">This latter article also applies to BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9de4d-115">参照</span><span class="sxs-lookup"><span data-stu-id="9de4d-115">See Also</span></span>  
 [<span data-ttu-id="9de4d-116">チェックリスト: BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="9de4d-116">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)