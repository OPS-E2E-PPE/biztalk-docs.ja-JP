---
title: "ポリシーの管理 |Microsoft ドキュメント"
description: "リンクをインポートするには、発行、追加、配置、削除、または BizTalk Server でポリシーをエクスポート"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7b3bf92-8868-4c35-953f-61a7f2edff9c
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dd482c2f7a226a15fe730d2b75b470a54ff27e9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="manage-policies"></a><span data-ttu-id="39270-103">ポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="39270-103">Manage policies</span></span>

## <a name="overview"></a><span data-ttu-id="39270-104">概要</span><span class="sxs-lookup"><span data-stu-id="39270-104">Overview</span></span>
<span data-ttu-id="39270-105">このセクションのトピックでは、BizTalk Server 管理コンソールまたは BTSTask コマンド ライン ツールを使用してポリシーを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="39270-105">The topics in this section provide instructions on using the BizTalk Server Administration console or the BTSTask command-line tool to manage policies.</span></span> <span data-ttu-id="39270-106">ポリシーは、ビジネス ルールの論理グループです。</span><span class="sxs-lookup"><span data-stu-id="39270-106">A policy is a logical grouping of business rules.</span></span> <span data-ttu-id="39270-107">ポリシーの基礎知識については、次を参照してください。[ポリシー](../core/policies.md)です。</span><span class="sxs-lookup"><span data-stu-id="39270-107">For background information on policies, see [Policies](../core/policies.md).</span></span>  
  
## <a name="import-publish-deploy-and-remove-policies"></a><span data-ttu-id="39270-108">インポート、公開、展開、およびポリシーの削除</span><span class="sxs-lookup"><span data-stu-id="39270-108">Import, publish, deploy, and remove policies</span></span>
 <span data-ttu-id="39270-109">ソリューション開発者が作成および」の説明に従って、ビジネス ルール作成ツールを使用して、ポリシーの表示[ビジネス ルール作成ツールを使用して作成するビジネス ルール](../core/creating-business-rules-using-the-business-rule-composer.md)です。</span><span class="sxs-lookup"><span data-stu-id="39270-109">Solution developers can create and view policies by using the Business Rule Composer, as described in [Creating Business Rules Using the Business Rule Composer](../core/creating-business-rules-using-the-business-rule-composer.md).</span></span> <span data-ttu-id="39270-110">開発者と IT 管理者は、BizTalk グループおよびアプリケーションでポリシーを展開して管理するために、このセクションのトピックで説明する次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="39270-110">Developers and IT administrators can then perform the following tasks, which are described in the topics in this section, to deploy and manage policies in a BizTalk group and application:</span></span>  
  
-   <span data-ttu-id="39270-111">**BizTalk グループにポリシーをインポートします。**</span><span class="sxs-lookup"><span data-stu-id="39270-111">**Import the policy into a BizTalk group.**</span></span> <span data-ttu-id="39270-112">これを行うと、ポリシーがグループのルール エンジン データベースに追加され、BizTalk Server 管理コンソールでに表示されます、\<すべての成果物\>BizTalk グループのノードです。</span><span class="sxs-lookup"><span data-stu-id="39270-112">When you do this, the policy is added to the Rule Engine database for the group and displays in the BizTalk Server Administration console in the \<All Artifacts\> node for the BizTalk group.</span></span> <span data-ttu-id="39270-113">これによって、ポリシーが特定のアプリケーションで有効になるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="39270-113">This does not put the policy into effect for any particular application.</span></span> <span data-ttu-id="39270-114">このセクションの他のトピックで説明するように、最初にポリシーを公開し、アプリケーションに追加してから展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39270-114">You must first publish the policy, add it to an application, and then deploy it, as described in other topics in this section.</span></span> <span data-ttu-id="39270-115">ルール エンジン データベースは、BizTalk グループ内のすべてのポリシーを含むデータベースです。</span><span class="sxs-lookup"><span data-stu-id="39270-115">The Rule Engine database is a database that contains all of the policies in a BizTalk group.</span></span>  
  
-   <span data-ttu-id="39270-116">**ポリシーを公開します。**</span><span class="sxs-lookup"><span data-stu-id="39270-116">**Publish a policy.**</span></span> <span data-ttu-id="39270-117">これにより、ポリシーを BizTalk アプリケーション内で使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="39270-117">This makes it available to use in a BizTalk application.</span></span>  
  
-   <span data-ttu-id="39270-118">**ポリシーを BizTalk アプリケーションを追加します。**</span><span class="sxs-lookup"><span data-stu-id="39270-118">**Add a policy to a BizTalk application.**</span></span> <span data-ttu-id="39270-119">これにより、アプリケーションからポリシーを使用できますが、ポリシーが有効になるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="39270-119">This allows the application to use the policy, but does not put the policy into effect.</span></span> <span data-ttu-id="39270-120">ポリシーは、展開された後で有効になります。</span><span class="sxs-lookup"><span data-stu-id="39270-120">The policy takes effect when it is deployed.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="39270-121">複数のアプリケーションでポリシーを共有するには、ポリシーを格納する独立したアプリケーションを作成した後、そのポリシーを使用する別のアプリケーションからポリシーを格納するアプリケーションへの参照を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39270-121">If a policy is shared across two or more applications, you should create a separate application to contain the policy and then create references from the applications that use the policy to the application containing the policy.</span></span> <span data-ttu-id="39270-122">これは、ポリシーを含むアプリケーションを停止すると、ポリシーが自動的に展開解除され、ポリシーを使用するアプリケーションで機能しなくなるためです。</span><span class="sxs-lookup"><span data-stu-id="39270-122">This is because if you stop an application that contains a policy, the policy is automatically undeployed and no longer functions for any of the applications that use it.</span></span>  
  
-   <span data-ttu-id="39270-123">**ポリシーを展開します。**</span><span class="sxs-lookup"><span data-stu-id="39270-123">**Deploy a policy.**</span></span> <span data-ttu-id="39270-124">これにより、ポリシーの運用が開始されます</span><span class="sxs-lookup"><span data-stu-id="39270-124">Doing this puts it into operation.</span></span> <span data-ttu-id="39270-125">(これは、オーケストレーションを開始するのと同様です。)ポリシーは手動で展開および展開解除できます。</span><span class="sxs-lookup"><span data-stu-id="39270-125">(This is similar to starting an orchestration.) You can deploy and undeploy a policy manually.</span></span> <span data-ttu-id="39270-126">また、アプリケーションを開始すると、そのポリシーが自動的に展開され、アプリケーションを停止すると自動的に展開解除されます。</span><span class="sxs-lookup"><span data-stu-id="39270-126">In addition, when an application is started, its policies are automatically deployed, and when an application is stopped, its policies are automatically undeployed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="39270-127">ポリシーを展開した後で、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="39270-127">Once a policy is deployed, it can no longer be modified.</span></span> <span data-ttu-id="39270-128">展開済みのポリシーを変更するには、展開解除するか、ビジネス ルール作成ツールで再作成して新しいバージョン番号を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39270-128">If you want to modify a deployed policy, you must either undeploy it, or recreate it by using the Business Rule Composer and give it a new version number.</span></span>  
  
-   <span data-ttu-id="39270-129">**BizTalk アプリケーションと BizTalk グループからポリシーを削除します。**</span><span class="sxs-lookup"><span data-stu-id="39270-129">**Remove a policy from a BizTalk application and the BizTalk group.**</span></span> <span data-ttu-id="39270-130">これにより、ポリシーが展開解除され、アプリケーションからだけでなくグループのルール エンジン データベースからも削除されます。</span><span class="sxs-lookup"><span data-stu-id="39270-130">This undeploys the policy and removes it from the application as well as the Rule Engine database for the group.</span></span>  
  
-   <span data-ttu-id="39270-131">**ポリシーをエクスポートします。**</span><span class="sxs-lookup"><span data-stu-id="39270-131">**Export the policy.**</span></span> <span data-ttu-id="39270-132">その後、ポリシーを別の BizTalk グループにインポートして使用できます。</span><span class="sxs-lookup"><span data-stu-id="39270-132">You can then import it into a different BizTalk group to use there.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39270-133">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="39270-133">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="39270-134">WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="39270-134">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="39270-135">次の手順</span><span class="sxs-lookup"><span data-stu-id="39270-135">Next steps</span></span>
  
-   [<span data-ttu-id="39270-136">ポリシーのインポート</span><span class="sxs-lookup"><span data-stu-id="39270-136">Import a Policy</span></span>](../core/how-to-import-a-policy.md)  
  
-   [<span data-ttu-id="39270-137">ポリシーの公開</span><span class="sxs-lookup"><span data-stu-id="39270-137">Publish a Policy</span></span>](../core/how-to-publish-a-policy.md)  
  
-   [<span data-ttu-id="39270-138">ポリシーをアプリケーションに追加する</span><span class="sxs-lookup"><span data-stu-id="39270-138">Add a Policy to an Application</span></span>](../core/how-to-add-a-policy-to-an-application.md)  
  
-   [<span data-ttu-id="39270-139">ポリシーを展開または展開解除する</span><span class="sxs-lookup"><span data-stu-id="39270-139">Deploy or Undeploy a Policy</span></span>](../core/how-to-deploy-or-undeploy-a-policy.md)  
  
-   [<span data-ttu-id="39270-140">ポリシーの追跡を構成する</span><span class="sxs-lookup"><span data-stu-id="39270-140">Configure Tracking for a Policy</span></span>](../core/how-to-configure-tracking-for-a-policy.md)  
  
-   [<span data-ttu-id="39270-141">アプリケーションおよび BizTalk グループからポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="39270-141">Remove a Policy from an Application and the BizTalk Group</span></span>](../core/how-to-remove-a-policy-from-an-application-and-the-biztalk-group.md)  
  
-   [<span data-ttu-id="39270-142">ポリシーをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="39270-142">Export a Policy</span></span>](../core/how-to-export-a-policy.md)