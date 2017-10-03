---
title: "リモート アクティビティの分散ナビゲーションを管理する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7cf6e0c2-ea72-4621-9ca7-fa43e404ec46
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bb21de97643d864a47d93a2ddd31e08bdd30532
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="managing-distributed-navigation-of-remote-activities"></a><span data-ttu-id="1ad63-102">リモート アクティビティの分散ナビゲーションの管理</span><span class="sxs-lookup"><span data-stu-id="1ad63-102">Managing Distributed Navigation of Remote Activities</span></span>
<span data-ttu-id="1ad63-103">リモート アクティビティの分散ナビゲーションは、ビジネス ユーザーが個別の BAM データベースに存在するアクティビティに移動してそれらのアクティビティを参照するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="1ad63-103">Distributed navigation of remote activities is the process by which a business user navigates to and views activities that exist in separate BAM databases.</span></span> <span data-ttu-id="1ad63-104">BAM インフラストラクチャを構成して分散ナビゲーションを提供する場合、BAM ポータル内のビジネス ユーザーがリモート アクティビティにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1ad63-104">When you configure the BAM infrastructure to provide distributed navigation, the remote activity is accessible to the business user in the BAM portal.</span></span> <span data-ttu-id="1ad63-105">ユーザーがアクティビティをクリックすると、そのアクティビティはリモートの BAM ポータルで開かれます。</span><span class="sxs-lookup"><span data-stu-id="1ad63-105">When the user clicks the activity, the activity is opened on the remote BAM portal.</span></span> <span data-ttu-id="1ad63-106">この時点でユーザーは意識する必要のないシームレスな手法でリモートの BAM ポータルに転送され、対象のアクティビティがユーザーのホーム データ ストアに存在していたかのようにアクティビティの検索、集計、および警告管理に移動できます。</span><span class="sxs-lookup"><span data-stu-id="1ad63-106">At this point the user has been transferred in a transparent and seamless manner to the remote BAM portal and can navigate to the activity search, aggregations, and alert management for the activity as if the activity existed on the user's home data store.</span></span>  
  
## <a name="why-use-distributed-navigation-of-activities-and-documents"></a><span data-ttu-id="1ad63-107">アクティビティとドキュメントの分散ナビゲーションを使用する理由</span><span class="sxs-lookup"><span data-stu-id="1ad63-107">Why Use Distributed Navigation of Activities and Documents?</span></span>  
 <span data-ttu-id="1ad63-108">分散ナビゲーションでアクティビティを 1 つの場所に同意しなくても部門別の BAM データベースの管理を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1ad63-108">Distributed navigation allows organizations to retain control of departmental BAM databases without having to agree on a single location for the activities.</span></span> <span data-ttu-id="1ad63-109">これも、環境全体でアクティビティのシステムの負荷を分散することで、BAM データベースからのパフォーマンスを向上させるためによりできます。</span><span class="sxs-lookup"><span data-stu-id="1ad63-109">This also allows for better performance from your BAM databases by distributing the system load of the activities throughout your environment.</span></span>  
  
 <span data-ttu-id="1ad63-110">次の図は、分散ナビゲーションによってビジネス ユーザーのニーズに対処し、企業内の別個の部門で管理されているアクティビティに簡単にアクセスできるようにするシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="1ad63-110">The following figure illustrates a scenario in which distributed navigation addresses the needs of the business user to have easy access to activities that are managed by separate departments in a company.</span></span> <span data-ttu-id="1ad63-111">これらの部門の管理者は、その部門に固有のビジネス プロセスの制御を維持します。</span><span class="sxs-lookup"><span data-stu-id="1ad63-111">The administrators in those departments maintain control of the business processes specific to that department.</span></span>  
  
 <span data-ttu-id="1ad63-112">このシナリオの関係者は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1ad63-112">In this scenario there are the following stakeholders:</span></span>  
  
-   <span data-ttu-id="1ad63-113">営業部門のインフラストラクチャを所有する管理者。</span><span class="sxs-lookup"><span data-stu-id="1ad63-113">An administrator who owns the infrastructure for the sales department.</span></span> <span data-ttu-id="1ad63-114">部門のデータの可用性とセキュリティのみについて担当します。</span><span class="sxs-lookup"><span data-stu-id="1ad63-114">The administrator is solely responsible for the availability and security of the department’s data.</span></span>  
  
-   <span data-ttu-id="1ad63-115">出荷部門のインフラストラクチャを所有する管理者。</span><span class="sxs-lookup"><span data-stu-id="1ad63-115">An administrator who owns the infrastructure for the shipping department.</span></span> <span data-ttu-id="1ad63-116">販売のニーズを満たす責任があります。</span><span class="sxs-lookup"><span data-stu-id="1ad63-116">He is responsible for meeting the needs of the sales.</span></span>  
  
-   <span data-ttu-id="1ad63-117">営業部門のビジネス ユーザー。</span><span class="sxs-lookup"><span data-stu-id="1ad63-117">A business user in the sales department.</span></span> <span data-ttu-id="1ad63-118">ビジネス ユーザーはユーザーが追加されているビューに含まれている売上データのサブセットを参照します。</span><span class="sxs-lookup"><span data-stu-id="1ad63-118">The business user sees subsets of the sales data that are included in the views to which the user has been added.</span></span> <span data-ttu-id="1ad63-119">そのビューは、ビジネス ユーザーにビューへのアクセス権を与える管理者が作成します。</span><span class="sxs-lookup"><span data-stu-id="1ad63-119">The views are created by the administrator who grants the business user access to the view.</span></span> <span data-ttu-id="1ad63-120">ビジネス ユーザーにとってのビジネスのプライマリ ビューは、そのユーザー自身が参加する発注アクティビティです。</span><span class="sxs-lookup"><span data-stu-id="1ad63-120">The business user's primary view of the business is the Purchase Order activity in which she participates.</span></span> <span data-ttu-id="1ad63-121">このユーザーは、営業部門の管理者が管理している BAM ポータルのホーム ページを表示できるように設定されています。</span><span class="sxs-lookup"><span data-stu-id="1ad63-121">This user is set up to view the home page of the BAM portal maintained by the administrator of the sales department.</span></span>  
  
 <span data-ttu-id="1ad63-122">**BAM での分散ナビゲーションの使用**</span><span class="sxs-lookup"><span data-stu-id="1ad63-122">**Using Distributed Navigation in BAM**</span></span>  
  
 <span data-ttu-id="1ad63-123">![分散ナビゲーション シナリオです。] (../core/media/bcd-distrbuted-nav-scenario.gif "bcd_distrbuted_nav_scenario")</span><span class="sxs-lookup"><span data-stu-id="1ad63-123">![Distrbuted navigation scenario.](../core/media/bcd-distrbuted-nav-scenario.gif "bcd_distrbuted_nav_scenario")</span></span>  
  
 <span data-ttu-id="1ad63-124">管理者は次に示すように、サーバーをできるだけ独立した状態で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ad63-124">The administrators want to configure their servers to be as independent as possible, as follows:</span></span>  
  
-   <span data-ttu-id="1ad63-125">営業部門の管理者には、停止する注文の受理や、営業部門のインフラストラクチャがダウンした場合にビジネス ユーザーが影響を受けるクエリ機能は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1ad63-125">The sales department administrator does not want the acceptance of the orders to stop or the query functionality for his business users to be affected if the shipping department infrastructure is down.</span></span>  
  
-   <span data-ttu-id="1ad63-126">出荷部門の管理者は、出荷部門が営業部門のパフォーマンス問題の影響を受けるのを避けたいと考えています。</span><span class="sxs-lookup"><span data-stu-id="1ad63-126">The shipping department administrator does not want his department to be affected by performance problems in the sales department.</span></span> <span data-ttu-id="1ad63-127">また、営業部門で出荷の進捗状況を入手できない場合でも、ビジネス ユーザーが出荷の進捗状況を把握できるようにすることも希望しています。</span><span class="sxs-lookup"><span data-stu-id="1ad63-127">He wants his business users to be able to follow the progress of the shipments, even if the sales department is unavailable.</span></span>  
  
 <span data-ttu-id="1ad63-128">分散ナビゲーションの目標は、ビジネス エンド ユーザーがアクセス許可を与えられているすべてのビューにアクセスできるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="1ad63-128">The goal of distributed navigation is to provide the business end user with access to every view to which they have permissions.</span></span>  
  
 <span data-ttu-id="1ad63-129">たとえば、ビュー A と B は sales データベースで定義されます。</span><span class="sxs-lookup"><span data-stu-id="1ad63-129">For example, views A and B are defined in the sales database.</span></span> <span data-ttu-id="1ad63-130">出荷部門には、ビュー C が定義されています。</span><span class="sxs-lookup"><span data-stu-id="1ad63-130">The shipping department has view C defined.</span></span> <span data-ttu-id="1ad63-131">ビジネス ユーザーはこれらすべてのビューを表示するアクセス許可を持っているので、営業部門固有の BAM ポータルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1ad63-131">The business user has permission to view all of these, and accesses the BAM portal specific to the sales department.</span></span> <span data-ttu-id="1ad63-132">ビジネス ユーザーが A、B、および C でのビューが表示できるように、**マイ ビュー** shipping データベースに sales データベースから少なくとも一方向の信頼を確立することによって、ポータルのフレームを実現します。</span><span class="sxs-lookup"><span data-stu-id="1ad63-132">Allowing the business user to see views A, B, and C in the **MyViews** frame of the portal is accomplished by establishing at least a one-way trust from the sales database to the shipping database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ad63-133">指定のデータを参照できるビジネス ユーザーのカテゴリに対するアクセス許可は、マネージャーやアナリストなどのパワー ビジネス ユーザーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="1ad63-133">The permissions for the category of business user that can see specified data are defined by the power business user, such as a manager or analyst.</span></span> <span data-ttu-id="1ad63-134">既存のグループまたは BAM ビューにユーザーを追加できるのは管理者だけです。</span><span class="sxs-lookup"><span data-stu-id="1ad63-134">The administrators only add users to existing groups or BAM views.</span></span>  
  
 <span data-ttu-id="1ad63-135">BAM アクティビティの分散ナビゲーションを使用すると、ユーザーは分散アクティビティ リレーションシップを参照してアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1ad63-135">Distributed navigation of BAM activities also allows the user to see and access distributed activity relationships.</span></span> <span data-ttu-id="1ad63-136">分散ナビゲーションを使用して相互に関連している 2 つの異なる BAM データベース上のアクティビティ インスタンスがある場合、リモートの関連するアクティビティは、ローカル アクティビティ インスタンスの動作状況の詳細に関連するアクティビティとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ad63-136">When there are activity instances on two different BAM databases that have been related to each other using distributed navigation, the remote related activity is displayed as a related activity in the activity details of the local activity instance.</span></span> <span data-ttu-id="1ad63-137">関連アクティビティをクリックすると、リモート ポータルでそのアクティビティのアクティビティ詳細ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="1ad63-137">Clicking the related activity opens the activity details page for the activity on the remote portal.</span></span> <span data-ttu-id="1ad63-138">関連するアクティビティに関する詳細についてを参照して、BAM ポータルでのアクティビティの検索結果ページの[関連アクティビティ](../core/related-activities.md)です。</span><span class="sxs-lookup"><span data-stu-id="1ad63-138">For more information about the related activities of the activity search results page in the BAM portal, a see [Related Activities](../core/related-activities.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1ad63-139">各コンピューターのユーザーが、別の BAM データベースの関連アクティビティを参照できるようにするには、すべての BAM データベース間で双方向の分散ナビゲーションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ad63-139">For users on each computer to see related activities located in different BAM databases, you must enable two-way distributed navigation between all the BAM databases.</span></span>  
  
 <span data-ttu-id="1ad63-140">分散ナビゲーションを構成するとき、2 つのプライマリ インポート データベース間に一方向の分散ナビゲーションを有効にすると、ユーザーはナビゲーション中に非対称的な動作を経験することになります。</span><span class="sxs-lookup"><span data-stu-id="1ad63-140">If you enable one-way distributed navigation between two Primary Import databases when you configure distributed navigation, users will have an asymmetrical experience during the navigation.</span></span>  
  
 <span data-ttu-id="1ad63-141">ユーザー エクスペリエンスはそのユーザーが別のアクティビティを参照するようになります。ただし、ユーザーがインスタンス レベルのデータにドリル ダウンすると、関連インスタンスが表示されるセクションが空になります。</span><span class="sxs-lookup"><span data-stu-id="1ad63-141">The user experience will be such that the user will see the different activities; however, when the user drills into the instance-level data, the section where related instances are displayed will be empty.</span></span> <span data-ttu-id="1ad63-142">この問題を解決するには、ユーザー用にホーム BAM ポータル サーバーに戻る分散ナビゲーション パスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ad63-142">To resolve this issue, you must configure the distributed navigation path back to the home BAM portal server for the user.</span></span>  
  
 <span data-ttu-id="1ad63-143">たとえば、次のシナリオを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="1ad63-143">For example, consider the following scenario:</span></span>  
  
-   <span data-ttu-id="1ad63-144">コンピューター 1 に発注というアクティビティと SalesManager というビューがあります。</span><span class="sxs-lookup"><span data-stu-id="1ad63-144">You have Computer 1 on which you have an activity called Purchase Order and a view called SalesManager.</span></span>  
  
-   <span data-ttu-id="1ad63-145">コンピューター 2 に出荷というアクティビティと SalesManager というビューがあります。</span><span class="sxs-lookup"><span data-stu-id="1ad63-145">You have Computer 2 on which you have an activity called Shipping Order and a view called SalesManager</span></span>  
  
-   <span data-ttu-id="1ad63-146">PO_1 というアクティビティをコンピューター 1 の発注アクティビティに追加します。</span><span class="sxs-lookup"><span data-stu-id="1ad63-146">You add an activity called PO_1 to Purchase Order on Computer 1</span></span>  
  
-   <span data-ttu-id="1ad63-147">SO_1 というアクティビティをコンピューター 2 の出荷アクティビティに追加します。</span><span class="sxs-lookup"><span data-stu-id="1ad63-147">You add an activity called SO_1 to Shipping Order on Computer 2</span></span>  
  
-   <span data-ttu-id="1ad63-148">コンピューター 2 で、SO_1 から PurchaseOrder PO_1 出荷アクティビティにリレーションシップを追加します。</span><span class="sxs-lookup"><span data-stu-id="1ad63-148">On Computer 2 you add the relationship,  SO_1 to the PurchaseOrder PO_1 Activity on Shipping Order</span></span>  
  
-   <span data-ttu-id="1ad63-149">ユーザーがコンピューター 1 から SO_1 アクティビティにドリル ダウンすると、SO_1 アクティビティを検出できます。</span><span class="sxs-lookup"><span data-stu-id="1ad63-149">When a user drills down into the SO_1 activity from Computer 1 the SO_1 activity is discoverable</span></span>  
  
-   <span data-ttu-id="1ad63-150">ユーザーがコンピューター 2 の SO_1 をドリル ダウンしても、PO_1 アクティビティは表示されません。</span><span class="sxs-lookup"><span data-stu-id="1ad63-150">If the user drills down the SO_1 on Computer 2, the PO_1 activity is not visible</span></span>  
  
 <span data-ttu-id="1ad63-151">この状況を是正するには、コンピューター 1 にリレーションシップを追加することが必要になります。</span><span class="sxs-lookup"><span data-stu-id="1ad63-151">To rectify this, you will need to add the relationship on Computer 1.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1ad63-152">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1ad63-152">In This Section</span></span>  
  
-   [<span data-ttu-id="1ad63-153">分散アクティビティ間のナビゲーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="1ad63-153">How to Configure Navigation Between Distributed Activities</span></span>](../core/how-to-configure-navigation-between-distributed-activities.md)  
  
## <a name="see-also"></a><span data-ttu-id="1ad63-154">参照</span><span class="sxs-lookup"><span data-stu-id="1ad63-154">See Also</span></span>  
 [<span data-ttu-id="1ad63-155">BAM の管理</span><span class="sxs-lookup"><span data-stu-id="1ad63-155">Managing BAM</span></span>](../core/managing-bam.md)