---
title: スクリプトを使用してアプリケーションを展開する |Microsoft Docs
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
ms.openlocfilehash: b5e8c4018540562f92d80f8c2529deebedcc9753
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249312"
---
# <a name="using-scripts-to-deploy-applications"></a><span data-ttu-id="f4d24-102">スクリプトを使用してアプリケーションを展開するには</span><span class="sxs-lookup"><span data-stu-id="f4d24-102">Using Scripts to Deploy Applications</span></span>
<span data-ttu-id="f4d24-103">スクリプトを使用して、可能であれば、BizTalk アプリケーションをデプロイする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d24-103">You should use scripts to deploy BizTalk applications where possible.</span></span> <span data-ttu-id="f4d24-104">展開プロセス中に人的ミスのリスクを軽減するスクリプトします。</span><span class="sxs-lookup"><span data-stu-id="f4d24-104">Scripting reduces the risk of human error during the deployment process.</span></span> <span data-ttu-id="f4d24-105">展開手順の詳細も文書化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d24-105">You should also document your deployment procedures in depth.</span></span> <span data-ttu-id="f4d24-106">非常に詳細な手順をスクリプトのないものはすべて文書化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d24-106">You should document anything that you do not script with very detailed steps.</span></span> <span data-ttu-id="f4d24-107">これは、Microsoft 以外のコンポーネントの展開を外部システムに変更を文書化が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f4d24-107">This includes documenting any changes to external systems and to deployment of non-Microsoft components.</span></span>  
  
## <a name="using-btstask"></a><span data-ttu-id="f4d24-108">BTSTask を使用します。</span><span class="sxs-lookup"><span data-stu-id="f4d24-108">Using BTSTask</span></span>  
 <span data-ttu-id="f4d24-109">BTSTask.exe を使用するには、BizTalk アプリケーションにも、既存のインポートの作成をスクリプト化する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].msi パッケージ。</span><span class="sxs-lookup"><span data-stu-id="f4d24-109">You can use BTSTask.exe to script the creation of BizTalk applications, as well as to import existing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] .msi packages.</span></span> <span data-ttu-id="f4d24-110">アプリケーションの作成をスクリプト化すると、パッケージ作成できる場合に自動的にビルド サーバーで、自動化されたプロセスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="f4d24-110">If the creation of the applications is scripted, then the packages can be automatically built using an automated process on a build server.</span></span>  
  
 <span data-ttu-id="f4d24-111">BizTalk アプリケーションの展開をスクリプト作成の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4d24-111">See the following topics for more information about scripting BizTalk application deployments:</span></span>  
  
-   <span data-ttu-id="f4d24-112">[BizTalk アプリケーション展開、管理](http://go.microsoft.com/fwlink/?LinkId=154210)(http://go.microsoft.com/fwlink/?LinkId=154210)</span><span class="sxs-lookup"><span data-stu-id="f4d24-112">[Deploying and Managing BizTalk Applications](http://go.microsoft.com/fwlink/?LinkId=154210) (http://go.microsoft.com/fwlink/?LinkId=154210)</span></span>  
  
-   <span data-ttu-id="f4d24-113">[BizTalk Server アプリケーションの展開について](http://go.microsoft.com/fwlink/?LinkId=101599)(http://go.microsoft.com/fwlink/?LinkId=101599)</span><span class="sxs-lookup"><span data-stu-id="f4d24-113">[Understanding BizTalk Server Application Deployment](http://go.microsoft.com/fwlink/?LinkId=101599) (http://go.microsoft.com/fwlink/?LinkId=101599)</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f4d24-114">この後者の記事では、BizTalk Server にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="f4d24-114">This latter article also applies to BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4d24-115">参照</span><span class="sxs-lookup"><span data-stu-id="f4d24-115">See Also</span></span>  
 [<span data-ttu-id="f4d24-116">チェックリスト:BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="f4d24-116">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)