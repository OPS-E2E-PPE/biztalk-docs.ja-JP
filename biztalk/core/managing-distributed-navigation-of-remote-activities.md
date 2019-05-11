---
title: リモート アクティビティの分散ナビゲーションの管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7cf6e0c2-ea72-4621-9ca7-fa43e404ec46
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49922065cc0f388439f6d089eb043d221a702ba8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380304"
---
# <a name="managing-distributed-navigation-of-remote-activities"></a><span data-ttu-id="2efdd-102">リモート アクティビティの分散ナビゲーションの管理</span><span class="sxs-lookup"><span data-stu-id="2efdd-102">Managing Distributed Navigation of Remote Activities</span></span>
<span data-ttu-id="2efdd-103">リモート アクティビティの分散ナビゲーションは、ビジネス ユーザーに移動、別の BAM データベースに存在するアクティビティを表示するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="2efdd-103">Distributed navigation of remote activities is the process by which a business user navigates to and views activities that exist in separate BAM databases.</span></span> <span data-ttu-id="2efdd-104">分散ナビゲーションを提供する BAM インフラストラクチャを構成するときに、リモートのアクティビティは、BAM ポータルで、ビジネス ユーザーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2efdd-104">When you configure the BAM infrastructure to provide distributed navigation, the remote activity is accessible to the business user in the BAM portal.</span></span> <span data-ttu-id="2efdd-105">ユーザーは、アクティビティをクリックすると、リモートの BAM ポータルで、アクティビティが開かれます。</span><span class="sxs-lookup"><span data-stu-id="2efdd-105">When the user clicks the activity, the activity is opened on the remote BAM portal.</span></span> <span data-ttu-id="2efdd-106">この時点で、ユーザーは透過的でシームレスな方法で、リモートの BAM ポータルに転送され、アクティビティは、ユーザーのホーム データ ストアに存在していたかのように、アクティビティの検索、集計、およびアクティビティのアラートの管理に移動できます。</span><span class="sxs-lookup"><span data-stu-id="2efdd-106">At this point the user has been transferred in a transparent and seamless manner to the remote BAM portal and can navigate to the activity search, aggregations, and alert management for the activity as if the activity existed on the user's home data store.</span></span>  
  
## <a name="why-use-distributed-navigation-of-activities-and-documents"></a><span data-ttu-id="2efdd-107">アクティビティとドキュメントの分散ナビゲーションを使用する理由</span><span class="sxs-lookup"><span data-stu-id="2efdd-107">Why Use Distributed Navigation of Activities and Documents?</span></span>  
 <span data-ttu-id="2efdd-108">分散ナビゲーション活動の 1 つの場所で同意をしなくても部門別の BAM データベースの管理を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2efdd-108">Distributed navigation allows organizations to retain control of departmental BAM databases without having to agree on a single location for the activities.</span></span> <span data-ttu-id="2efdd-109">これも、環境全体でアクティビティのシステムの負荷を分散することによって BAM データベースからのパフォーマンスが向上できます。</span><span class="sxs-lookup"><span data-stu-id="2efdd-109">This also allows for better performance from your BAM databases by distributing the system load of the activities throughout your environment.</span></span>  
  
 <span data-ttu-id="2efdd-110">次の図は、会社内の別個の部門で管理されているアクティビティを簡単にアクセスするためのビジネス ユーザーのニーズに対応して分散ナビゲーションをシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="2efdd-110">The following figure illustrates a scenario in which distributed navigation addresses the needs of the business user to have easy access to activities that are managed by separate departments in a company.</span></span> <span data-ttu-id="2efdd-111">その部門の管理者は、その部門に固有のビジネス プロセスの制御を維持します。</span><span class="sxs-lookup"><span data-stu-id="2efdd-111">The administrators in those departments maintain control of the business processes specific to that department.</span></span>  
  
 <span data-ttu-id="2efdd-112">このシナリオでは、次の利害関係者があります。</span><span class="sxs-lookup"><span data-stu-id="2efdd-112">In this scenario there are the following stakeholders:</span></span>  
  
- <span data-ttu-id="2efdd-113">営業部門のインフラストラクチャを所有する管理者。</span><span class="sxs-lookup"><span data-stu-id="2efdd-113">An administrator who owns the infrastructure for the sales department.</span></span> <span data-ttu-id="2efdd-114">管理者は、可用性と部門のデータのセキュリティに責任を負うものです。</span><span class="sxs-lookup"><span data-stu-id="2efdd-114">The administrator is solely responsible for the availability and security of the department’s data.</span></span>  
  
- <span data-ttu-id="2efdd-115">出荷部門のインフラストラクチャを所有する管理者。</span><span class="sxs-lookup"><span data-stu-id="2efdd-115">An administrator who owns the infrastructure for the shipping department.</span></span> <span data-ttu-id="2efdd-116">販売のニーズを満たすために担当しています。</span><span class="sxs-lookup"><span data-stu-id="2efdd-116">He is responsible for meeting the needs of the sales.</span></span>  
  
- <span data-ttu-id="2efdd-117">営業部門のビジネス ユーザー。</span><span class="sxs-lookup"><span data-stu-id="2efdd-117">A business user in the sales department.</span></span> <span data-ttu-id="2efdd-118">ビジネス ユーザーには、ユーザーが追加されているビューに含まれている売上データのサブセットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2efdd-118">The business user sees subsets of the sales data that are included in the views to which the user has been added.</span></span> <span data-ttu-id="2efdd-119">ビューは、ビューをビジネス ユーザーのアクセス権を付与する管理者によって作成されます。</span><span class="sxs-lookup"><span data-stu-id="2efdd-119">The views are created by the administrator who grants the business user access to the view.</span></span> <span data-ttu-id="2efdd-120">ビジネスのビジネス ユーザーのプライマリ ビューは、彼女が参加する発注アクティビティです。</span><span class="sxs-lookup"><span data-stu-id="2efdd-120">The business user's primary view of the business is the Purchase Order activity in which she participates.</span></span> <span data-ttu-id="2efdd-121">このユーザーは、営業部門の管理者によって管理される BAM ポータルのホーム ページを表示する設定します。</span><span class="sxs-lookup"><span data-stu-id="2efdd-121">This user is set up to view the home page of the BAM portal maintained by the administrator of the sales department.</span></span>  
  
  <span data-ttu-id="2efdd-122">**BAM での分散ナビゲーションの使用**</span><span class="sxs-lookup"><span data-stu-id="2efdd-122">**Using Distributed Navigation in BAM**</span></span>  
  
  <span data-ttu-id="2efdd-123">![分散ナビゲーション シナリオ。](../core/media/bcd-distrbuted-nav-scenario.gif "bcd_distrbuted_nav_scenario")</span><span class="sxs-lookup"><span data-stu-id="2efdd-123">![Distrbuted navigation scenario.](../core/media/bcd-distrbuted-nav-scenario.gif "bcd_distrbuted_nav_scenario")</span></span>  
  
  <span data-ttu-id="2efdd-124">管理者は、相互に依存しない限り、次のように、サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2efdd-124">The administrators want to configure their servers to be as independent as possible, as follows:</span></span>  
  
- <span data-ttu-id="2efdd-125">営業部門の管理者は、停止する注文のクエリ機能は、営業部門のインフラストラクチャがダウンした場合に影響を受けてビジネス ユーザーの同意を望んでいません。</span><span class="sxs-lookup"><span data-stu-id="2efdd-125">The sales department administrator does not want the acceptance of the orders to stop or the query functionality for his business users to be affected if the shipping department infrastructure is down.</span></span>  
  
- <span data-ttu-id="2efdd-126">出荷部門の管理者では、営業部門のパフォーマンスの問題の影響を受けるには、その部門は望んでいません。</span><span class="sxs-lookup"><span data-stu-id="2efdd-126">The shipping department administrator does not want his department to be affected by performance problems in the sales department.</span></span> <span data-ttu-id="2efdd-127">彼には、営業部門が利用できる場合でも、出荷の進捗状況を把握できるビジネス ユーザーが希望しています。</span><span class="sxs-lookup"><span data-stu-id="2efdd-127">He wants his business users to be able to follow the progress of the shipments, even if the sales department is unavailable.</span></span>  
  
  <span data-ttu-id="2efdd-128">分散ナビゲーションの目的は、ビジネス エンドユーザーを提供するすべてのビューにアクセス許可を持っているアクセス権を持つです。</span><span class="sxs-lookup"><span data-stu-id="2efdd-128">The goal of distributed navigation is to provide the business end user with access to every view to which they have permissions.</span></span>  
  
  <span data-ttu-id="2efdd-129">たとえば、ビュー A と B は sales データベースで定義されます。</span><span class="sxs-lookup"><span data-stu-id="2efdd-129">For example, views A and B are defined in the sales database.</span></span> <span data-ttu-id="2efdd-130">出荷部門は、C が定義されています。</span><span class="sxs-lookup"><span data-stu-id="2efdd-130">The shipping department has view C defined.</span></span> <span data-ttu-id="2efdd-131">ビジネス ユーザーが、これらすべてを表示するアクセス許可し、営業部門に固有の BAM ポータルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2efdd-131">The business user has permission to view all of these, and accesses the BAM portal specific to the sales department.</span></span> <span data-ttu-id="2efdd-132">ビジネス ユーザーが A、B、および C でのビューが表示できるように、**マイ**shipping データベースに sales データベースから、少なくとも一方向の信頼を確立することにより、ポータルのフレームが実現されます。</span><span class="sxs-lookup"><span data-stu-id="2efdd-132">Allowing the business user to see views A, B, and C in the **MyViews** frame of the portal is accomplished by establishing at least a one-way trust from the sales database to the shipping database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2efdd-133">指定されたデータを表示できるビジネス ユーザーのカテゴリのアクセス許可は、パワー ビジネス ユーザーのマネージャーやアナリストなどによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="2efdd-133">The permissions for the category of business user that can see specified data are defined by the power business user, such as a manager or analyst.</span></span> <span data-ttu-id="2efdd-134">管理者は、既存のグループまたは BAM ビューにのみユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2efdd-134">The administrators only add users to existing groups or BAM views.</span></span>  
  
 <span data-ttu-id="2efdd-135">BAM アクティビティの分散ナビゲーションは、ユーザーに表示され、分散アクティビティ リレーションシップをアクセスもできます。</span><span class="sxs-lookup"><span data-stu-id="2efdd-135">Distributed navigation of BAM activities also allows the user to see and access distributed activity relationships.</span></span> <span data-ttu-id="2efdd-136">分散ナビゲーションを使用して相互に関連する別の BAM データベースが 2 つのアクティビティ インスタンスがある場合は、リモートの関連するアクティビティは、ローカル アクティビティ インスタンスのアクティビティの詳細に関連するアクティビティとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="2efdd-136">When there are activity instances on two different BAM databases that have been related to each other using distributed navigation, the remote related activity is displayed as a related activity in the activity details of the local activity instance.</span></span> <span data-ttu-id="2efdd-137">関連するアクティビティをクリックすると、リモート ポータル上のアクティビティのアクティビティの詳細ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="2efdd-137">Clicking the related activity opens the activity details page for the activity on the remote portal.</span></span> <span data-ttu-id="2efdd-138">詳細については、関連するアクティビティに関するアクティビティの検索結果ページを参照してください、BAM ポータルでの[関連アクティビティ](../core/related-activities.md)します。</span><span class="sxs-lookup"><span data-stu-id="2efdd-138">For more information about the related activities of the activity search results page in the BAM portal, a see [Related Activities](../core/related-activities.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2efdd-139">別の BAM データベースにある関連するアクティビティを表示する各コンピューター上のユーザー、すべての BAM データベース間の双方向の分散ナビゲーションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2efdd-139">For users on each computer to see related activities located in different BAM databases, you must enable two-way distributed navigation between all the BAM databases.</span></span>  
  
 <span data-ttu-id="2efdd-140">分散ナビゲーションを構成するときに、2 つのプライマリ インポート データベース間の一方向の分散ナビゲーションを有効にした場合、ユーザーは、ナビゲーション中に非対称のエクスペリエンスがあります。</span><span class="sxs-lookup"><span data-stu-id="2efdd-140">If you enable one-way distributed navigation between two Primary Import databases when you configure distributed navigation, users will have an asymmetrical experience during the navigation.</span></span>  
  
 <span data-ttu-id="2efdd-141">ユーザー エクスペリエンスは別のアクティビティが表示されるようになりますただし、ユーザーは、インスタンス レベルのデータにドリル、ときに、関連するインスタンスが表示されるセクションは空になります。</span><span class="sxs-lookup"><span data-stu-id="2efdd-141">The user experience will be such that the user will see the different activities; however, when the user drills into the instance-level data, the section where related instances are displayed will be empty.</span></span> <span data-ttu-id="2efdd-142">この問題を解決するには、ユーザーのホーム BAM ポータル サーバーに戻る分散ナビゲーション パスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2efdd-142">To resolve this issue, you must configure the distributed navigation path back to the home BAM portal server for the user.</span></span>  
  
 <span data-ttu-id="2efdd-143">たとえば、次のシナリオを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="2efdd-143">For example, consider the following scenario:</span></span>  
  
- <span data-ttu-id="2efdd-144">コンピューター 1 の発注というアクティビティと SalesManager というビューがある必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="2efdd-144">You have Computer 1 on which you have an activity called Purchase Order and a view called SalesManager.</span></span>  
  
- <span data-ttu-id="2efdd-145">コンピューター 2 の出荷というアクティビティと SalesManager というビューがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="2efdd-145">You have Computer 2 on which you have an activity called Shipping Order and a view called SalesManager</span></span>  
  
- <span data-ttu-id="2efdd-146">コンピューター 1 に発注書に PO_1 と呼ばれるアクティビティを追加します。</span><span class="sxs-lookup"><span data-stu-id="2efdd-146">You add an activity called PO_1 to Purchase Order on Computer 1</span></span>  
  
- <span data-ttu-id="2efdd-147">コンピューター 2 の so_1 から出荷指示と呼ばれるアクティビティを追加します。</span><span class="sxs-lookup"><span data-stu-id="2efdd-147">You add an activity called SO_1 to Shipping Order on Computer 2</span></span>  
  
- <span data-ttu-id="2efdd-148">コンピューター 2 の so_1 から PurchaseOrder PO_1 アクティビティは、出荷指示をリレーションシップを追加します。</span><span class="sxs-lookup"><span data-stu-id="2efdd-148">On Computer 2 you add the relationship,  SO_1 to the PurchaseOrder PO_1 Activity on Shipping Order</span></span>  
  
- <span data-ttu-id="2efdd-149">コンピューター 1 の SO_1 アクティビティから SO_1 アクティビティが検出可能なときに、ユーザーのドリル ダウン</span><span class="sxs-lookup"><span data-stu-id="2efdd-149">When a user drills down into the SO_1 activity from Computer 1 the SO_1 activity is discoverable</span></span>  
  
- <span data-ttu-id="2efdd-150">PO_1 アクティビティが表示されていない場合はコンピューター 2 の SO_1 にユーザーのドリル ダウン、</span><span class="sxs-lookup"><span data-stu-id="2efdd-150">If the user drills down the SO_1 on Computer 2, the PO_1 activity is not visible</span></span>  
  
  <span data-ttu-id="2efdd-151">この問題を解決するには、コンピューター 1 にリレーションシップを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2efdd-151">To rectify this, you will need to add the relationship on Computer 1.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2efdd-152">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2efdd-152">In This Section</span></span>  
  
-   [<span data-ttu-id="2efdd-153">分散アクティビティ間のナビゲーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="2efdd-153">How to Configure Navigation Between Distributed Activities</span></span>](../core/how-to-configure-navigation-between-distributed-activities.md)  
  
## <a name="see-also"></a><span data-ttu-id="2efdd-154">参照</span><span class="sxs-lookup"><span data-stu-id="2efdd-154">See Also</span></span>  
 [<span data-ttu-id="2efdd-155">BAM の管理</span><span class="sxs-lookup"><span data-stu-id="2efdd-155">Managing BAM</span></span>](../core/managing-bam.md)