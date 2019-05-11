---
title: ポリシーの管理 |Microsoft Docs
description: リンクをインポートするには、発行、追加、デプロイ、削除、または BizTalk Server でのポリシーのエクスポート
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7b3bf92-8868-4c35-953f-61a7f2edff9c
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99c3dbc60bde3fdf82dc44a68e34345d3225b92c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380276"
---
# <a name="manage-policies"></a><span data-ttu-id="0a122-103">ポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="0a122-103">Manage policies</span></span>

## <a name="overview"></a><span data-ttu-id="0a122-104">概要</span><span class="sxs-lookup"><span data-stu-id="0a122-104">Overview</span></span>
<span data-ttu-id="0a122-105">このセクションのトピックでは、BizTalk Server 管理コンソールまたは BTSTask コマンド ライン ツールを使用して、ポリシーの管理について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a122-105">The topics in this section provide instructions on using the BizTalk Server Administration console or the BTSTask command-line tool to manage policies.</span></span> <span data-ttu-id="0a122-106">ポリシーは、ビジネス ルールの論理的なグループです。</span><span class="sxs-lookup"><span data-stu-id="0a122-106">A policy is a logical grouping of business rules.</span></span> <span data-ttu-id="0a122-107">バック グラウンド ポリシーについては、次を参照してください。[ポリシー](../core/policies.md)します。</span><span class="sxs-lookup"><span data-stu-id="0a122-107">For background information on policies, see [Policies](../core/policies.md).</span></span>  
  
## <a name="import-publish-deploy-and-remove-policies"></a><span data-ttu-id="0a122-108">インポート、公開、展開、およびポリシーの削除</span><span class="sxs-lookup"><span data-stu-id="0a122-108">Import, publish, deploy, and remove policies</span></span>
 <span data-ttu-id="0a122-109">ソリューション開発者が作成および」の説明に従って、ビジネス ルール作成ツールを使用してポリシーの表示[ビジネス ルール作成ツールを使用して作成するビジネス ルール](../core/creating-business-rules-using-the-business-rule-composer.md)します。</span><span class="sxs-lookup"><span data-stu-id="0a122-109">Solution developers can create and view policies by using the Business Rule Composer, as described in [Creating Business Rules Using the Business Rule Composer](../core/creating-business-rules-using-the-business-rule-composer.md).</span></span> <span data-ttu-id="0a122-110">開発者と IT 管理者、BizTalk グループおよびアプリケーションでポリシーを展開および管理、このセクションのトピックで説明されている次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0a122-110">Developers and IT administrators can then perform the following tasks, which are described in the topics in this section, to deploy and manage policies in a BizTalk group and application:</span></span>  
  
-   <span data-ttu-id="0a122-111">**BizTalk グループにポリシーをインポートします。**</span><span class="sxs-lookup"><span data-stu-id="0a122-111">**Import the policy into a BizTalk group.**</span></span> <span data-ttu-id="0a122-112">これを行うときにポリシーは、グループのルール エンジン データベースに追加され、BizTalk Server 管理コンソールに表示されます、\<すべての成果物\>BizTalk グループのノード。</span><span class="sxs-lookup"><span data-stu-id="0a122-112">When you do this, the policy is added to the Rule Engine database for the group and displays in the BizTalk Server Administration console in the \<All Artifacts\> node for the BizTalk group.</span></span> <span data-ttu-id="0a122-113">ポリシーを配置、特定のアプリケーションに対して有効にこれはありません。</span><span class="sxs-lookup"><span data-stu-id="0a122-113">This does not put the policy into effect for any particular application.</span></span> <span data-ttu-id="0a122-114">まず、ポリシーを発行、アプリケーションに追加、およびこのセクションの他のトピックで説明されているように配置し、する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a122-114">You must first publish the policy, add it to an application, and then deploy it, as described in other topics in this section.</span></span> <span data-ttu-id="0a122-115">ルール エンジン データベースは、すべての BizTalk グループにポリシーを含むデータベースです。</span><span class="sxs-lookup"><span data-stu-id="0a122-115">The Rule Engine database is a database that contains all of the policies in a BizTalk group.</span></span>  
  
-   <span data-ttu-id="0a122-116">**ポリシーを公開します。**</span><span class="sxs-lookup"><span data-stu-id="0a122-116">**Publish a policy.**</span></span> <span data-ttu-id="0a122-117">BizTalk アプリケーションで使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="0a122-117">This makes it available to use in a BizTalk application.</span></span>  
  
-   <span data-ttu-id="0a122-118">**BizTalk アプリケーションにポリシーを追加します。**</span><span class="sxs-lookup"><span data-stu-id="0a122-118">**Add a policy to a BizTalk application.**</span></span> <span data-ttu-id="0a122-119">これにより、アプリケーションは、ポリシーを使用するが、有効に、ポリシーを配置しません。</span><span class="sxs-lookup"><span data-stu-id="0a122-119">This allows the application to use the policy, but does not put the policy into effect.</span></span> <span data-ttu-id="0a122-120">展開されているときに、ポリシーを反映します。</span><span class="sxs-lookup"><span data-stu-id="0a122-120">The policy takes effect when it is deployed.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="0a122-121">複数のアプリケーションでポリシーを共有するには、ポリシーを格納する独立したアプリケーションを作成した後、そのポリシーを使用する別のアプリケーションからポリシーを格納するアプリケーションへの参照を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a122-121">If a policy is shared across two or more applications, you should create a separate application to contain the policy and then create references from the applications that use the policy to the application containing the policy.</span></span> <span data-ttu-id="0a122-122">これは、ポリシーを含むアプリケーションを停止すると、ポリシーが自動的に展開解除され、ポリシーを使用するアプリケーションで機能しなくなるためです。</span><span class="sxs-lookup"><span data-stu-id="0a122-122">This is because if you stop an application that contains a policy, the policy is automatically undeployed and no longer functions for any of the applications that use it.</span></span>  
  
-   <span data-ttu-id="0a122-123">**ポリシーを展開します。**</span><span class="sxs-lookup"><span data-stu-id="0a122-123">**Deploy a policy.**</span></span> <span data-ttu-id="0a122-124">これを行うと、操作に配置します。</span><span class="sxs-lookup"><span data-stu-id="0a122-124">Doing this puts it into operation.</span></span> <span data-ttu-id="0a122-125">(これは、オーケストレーションの開始に似ています) です。展開し、ポリシーを手動で展開解除できます。</span><span class="sxs-lookup"><span data-stu-id="0a122-125">(This is similar to starting an orchestration.) You can deploy and undeploy a policy manually.</span></span> <span data-ttu-id="0a122-126">さらに、アプリケーションが開始されると、そのポリシーが自動的に展開、およびアプリケーションが停止したら、そのポリシーを自動的に展開されません。</span><span class="sxs-lookup"><span data-stu-id="0a122-126">In addition, when an application is started, its policies are automatically deployed, and when an application is stopped, its policies are automatically undeployed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0a122-127">ポリシーをデプロイするとそれを変更できなくできます。</span><span class="sxs-lookup"><span data-stu-id="0a122-127">Once a policy is deployed, it can no longer be modified.</span></span> <span data-ttu-id="0a122-128">展開済みのポリシーを変更する場合は、いずれか、展開解除またはビジネス ルール作成ツールを使用して再作成して新しいバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="0a122-128">If you want to modify a deployed policy, you must either undeploy it, or recreate it by using the Business Rule Composer and give it a new version number.</span></span>  
  
-   <span data-ttu-id="0a122-129">**BizTalk アプリケーションと BizTalk グループからポリシーを削除します。**</span><span class="sxs-lookup"><span data-stu-id="0a122-129">**Remove a policy from a BizTalk application and the BizTalk group.**</span></span> <span data-ttu-id="0a122-130">これは、ポリシーを展開解除され、アプリケーションだけでなく、グループのルール エンジン データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="0a122-130">This undeploys the policy and removes it from the application as well as the Rule Engine database for the group.</span></span>  
  
-   <span data-ttu-id="0a122-131">**ポリシーをエクスポートします。**</span><span class="sxs-lookup"><span data-stu-id="0a122-131">**Export the policy.**</span></span> <span data-ttu-id="0a122-132">使用する別の BizTalk グループに、インポートできます。</span><span class="sxs-lookup"><span data-stu-id="0a122-132">You can then import it into a different BizTalk group to use there.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a122-133">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="0a122-133">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="0a122-134">WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0a122-134">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="0a122-135">次のステップ</span><span class="sxs-lookup"><span data-stu-id="0a122-135">Next steps</span></span>
  
-   [<span data-ttu-id="0a122-136">ポリシーのインポート</span><span class="sxs-lookup"><span data-stu-id="0a122-136">Import a Policy</span></span>](../core/how-to-import-a-policy.md)  
  
-   [<span data-ttu-id="0a122-137">ポリシーの公開</span><span class="sxs-lookup"><span data-stu-id="0a122-137">Publish a Policy</span></span>](../core/how-to-publish-a-policy.md)  
  
-   [<span data-ttu-id="0a122-138">ポリシーをアプリケーションに追加する</span><span class="sxs-lookup"><span data-stu-id="0a122-138">Add a Policy to an Application</span></span>](../core/how-to-add-a-policy-to-an-application.md)  
  
-   [<span data-ttu-id="0a122-139">ポリシーを展開または展開解除する</span><span class="sxs-lookup"><span data-stu-id="0a122-139">Deploy or Undeploy a Policy</span></span>](../core/how-to-deploy-or-undeploy-a-policy.md)  
  
-   [<span data-ttu-id="0a122-140">ポリシーの追跡を構成する</span><span class="sxs-lookup"><span data-stu-id="0a122-140">Configure Tracking for a Policy</span></span>](../core/how-to-configure-tracking-for-a-policy.md)  
  
-   [<span data-ttu-id="0a122-141">アプリケーションおよび BizTalk グループからポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="0a122-141">Remove a Policy from an Application and the BizTalk Group</span></span>](../core/how-to-remove-a-policy-from-an-application-and-the-biztalk-group.md)  
  
-   [<span data-ttu-id="0a122-142">ポリシーをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="0a122-142">Export a Policy</span></span>](../core/how-to-export-a-policy.md)