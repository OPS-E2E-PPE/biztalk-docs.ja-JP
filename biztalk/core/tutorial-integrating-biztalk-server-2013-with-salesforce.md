---
title: "チュートリアル: BizTalk Server 2013 を統合すると Salesforce |Microsoft ドキュメント"
description: "Service Bus と BIzTalk Server を使用して Salesforce を統合するには"
ms.custom: 
ms.date: 12/07/2015
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 06c9ae51-3f48-4086-883b-ab4d5b6e62e3
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8af013bc97ae9618dc19cab57d52fcb4829f0842
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-integrating-biztalk-server-2013-with-salesforce"></a><span data-ttu-id="075d6-103">チュートリアル: Salesforce との BizTalk Server 2013 の統合</span><span class="sxs-lookup"><span data-stu-id="075d6-103">Tutorial: Integrating BizTalk Server 2013 with Salesforce</span></span>
<span data-ttu-id="075d6-104">校閲者: [Nick Hauenstein](http://social.msdn.microsoft.com/profile/nick.hauenstein/)、 [Steef-jan Wiggers](http://social.msdn.microsoft.com/profile/steef-jan%20wiggers)</span><span class="sxs-lookup"><span data-stu-id="075d6-104">Reviewers: [Nick Hauenstein](http://social.msdn.microsoft.com/profile/nick.hauenstein/), [Steef-Jan Wiggers](http://social.msdn.microsoft.com/profile/steef-jan%20wiggers)</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="075d6-105">新たなアダプターのハイブリッド シナリオの多くを構成すると、オンプレミスと Azure テクノロジのようになりましたことに関連するが導入されています。</span><span class="sxs-lookup"><span data-stu-id="075d6-105"> introduces some new adapters that make a lot of hybrid scenarios, involving on-premises and Azure technologies now possible.</span></span> <span data-ttu-id="075d6-106">このチュートリアルでは、Salesforce を社内の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に統合するように、一部の新しいアダプターと [!INCLUDE[winazure](../includes/winazure-md.md)] を使用して、純粋にクラウドのエンティティを統合する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="075d6-106">In this tutorial, we see how to integrate a purely cloud entity like Salesforce integrate with an on-premises [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] using some of the new adapters and [!INCLUDE[winazure](../includes/winazure-md.md)].</span></span> <span data-ttu-id="075d6-107">開始する前に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と Salesforce を統合することで達成しようとするビジネス上の目的を理解しましょう。</span><span class="sxs-lookup"><span data-stu-id="075d6-107">Before we start, let’s understand the business objective we try to achieve by integrating [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with Salesforce.</span></span>  
  
 <span data-ttu-id="075d6-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と Salesforce に以前のバージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を加えたハイブリッド ソリューションを作成することもできますが、Web サービス (SOAP) を利用して Salesforce を統合すると、ソリューションがより複雑になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="075d6-108">We could also create hybrid solutions involving [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and Salesforce with previous version of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], however the solution would be much more complex involving interaction with Salesforce by consuming a Web service (SOAP).</span></span> <span data-ttu-id="075d6-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と新しいアダプターを使用すると、ソリューションがより簡単になります。</span><span class="sxs-lookup"><span data-stu-id="075d6-109">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the new adapters, the solution is that much easier.</span></span>  
  
## <a name="business-scenario"></a><span data-ttu-id="075d6-110">ビジネス シナリオ</span><span class="sxs-lookup"><span data-stu-id="075d6-110">Business Scenario</span></span>  
 <span data-ttu-id="075d6-111">Northwind は販売パイプラインを通じた顧客の追跡のためのソリューションに Salesforce オンライン CRM システムを利用しています。</span><span class="sxs-lookup"><span data-stu-id="075d6-111">Northwind uses the Salesforce online CRM system as their solution for tracking customers through the sales pipeline.</span></span> <span data-ttu-id="075d6-112">Salesforce システムで販売機会が作成されるたびに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] などの社内システムに通知を受けることで、他のダウンストリーム システムがそのデータを取得して他の関連するプロセスを開始できるようにしたいと Northwind は考えています。</span><span class="sxs-lookup"><span data-stu-id="075d6-112">Every time a sales opportunity is created in the Salesforce system, Northwind wants its on-premise systems, such as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], to be notified so that other down-stream systems can pick up that data and start other relevant processes.</span></span> <span data-ttu-id="075d6-113">Northwind は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で利用できる新しいアダプターを使用し、[!INCLUDE[winazure](../includes/winazure-md.md)] の一部のコンポーネントを含むこのソリューションの導入を計画しています。</span><span class="sxs-lookup"><span data-stu-id="075d6-113">Northwind plans to implement this solution using the new adapters available with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and also by including some components of [!INCLUDE[winazure](../includes/winazure-md.md)].</span></span> <span data-ttu-id="075d6-114">このソリューションにおけるエンド ツー エンドのデータ フローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="075d6-114">This is how the end-to-end data flow looks like for the solution:</span></span>  
  
-   <span data-ttu-id="075d6-115">営業担当者が Salesforce システムで "営業案件" を作成します。</span><span class="sxs-lookup"><span data-stu-id="075d6-115">A sales representative creates an “opportunity” in the Salesforce system.</span></span>  
  
-   <span data-ttu-id="075d6-116">営業案件の状態が “Closed Won” に設定されると、[!INCLUDE[winazure](../includes/winazure-md.md)] 上にホストされるリレー エンドポイントに通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="075d6-116">When the status of the opportunity is set to “Closed Won”, a notification is sent to a relay endpoint hosted on [!INCLUDE[winazure](../includes/winazure-md.md)].</span></span>  
  
-   <span data-ttu-id="075d6-117">新しい WCF-BasicHttpRelay アダプターを使用して、通知情報が社内の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] システムに渡されます。</span><span class="sxs-lookup"><span data-stu-id="075d6-117">Using the new WCF-BasicHttpRelay adapter, the notification information is passed on to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system housed on-premise.</span></span>  
  
-   <span data-ttu-id="075d6-118">通知の一部として受け取った情報を使用し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は新しい WCF-WebHttp アダプターを使用して Salesforce 内の REST エンドポイントを起動し、営業案件に関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="075d6-118">Using the information received as part of the notification, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] invokes a REST endpoint in Salesforce, using the new WCF-WebHttp adapter, to get more information about the opportunity.</span></span>  
  
-   <span data-ttu-id="075d6-119">最後に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は Salesforce から受け取った情報を使用して、社内の SQL Server データベース テーブルに発注エントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="075d6-119">Finally, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the information received from Salesforce to create a purchase order entry in an in-house SQL Server database table.</span></span>  
  
 <span data-ttu-id="075d6-120">このソリューションで説明する統合の意図を達成するには、これらの一連の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="075d6-120">These are the set of steps that you must perform to achieve the integration objective outlined in this solution.</span></span> <span data-ttu-id="075d6-121">これらの手順のそれぞれに、ソリューションの作成を続けていく中で見ることになる、広範なアクティビティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="075d6-121">Each of these steps involves broad set of activities that we’ll look at as we proceed with creating the solution.</span></span>  
  
 <span data-ttu-id="075d6-122">次の図では、エンド ツー エンドの統合ソリューションを説明しています。</span><span class="sxs-lookup"><span data-stu-id="075d6-122">Here’s an illustration that describes the end-to-end integration solution:</span></span>  
  
 <span data-ttu-id="075d6-123">![BizTalk Server と Salesforce の統合シナリオ](../core/media/bts-sf-scenario.gif "BTS_SF_Scenario")</span><span class="sxs-lookup"><span data-stu-id="075d6-123">![BizTalk Server and Salesforce integration scenario](../core/media/bts-sf-scenario.gif "BTS_SF_Scenario")</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="075d6-124">前提条件</span><span class="sxs-lookup"><span data-stu-id="075d6-124">Prerequisites</span></span>  
 <span data-ttu-id="075d6-125">このソリューションをセットアップするコンピューターには次のソフトウェアをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="075d6-125">You must have the following software installed on the computer where you set up this solution:</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]  
  
-   [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]  
  
-   [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]  
  
 <span data-ttu-id="075d6-126">次のサービスのサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="075d6-126">You must have the following service subscriptions:</span></span>  
  
-   <span data-ttu-id="075d6-127">[!INCLUDE[winazure](../includes/winazure-md.md)] サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="075d6-127">A [!INCLUDE[winazure](../includes/winazure-md.md)] subscription</span></span>  
  
-   <span data-ttu-id="075d6-128">Salesforce Developer Edition アカウント</span><span class="sxs-lookup"><span data-stu-id="075d6-128">Salesforce Developer Edition account</span></span>  
  
## <a name="more-resources"></a><span data-ttu-id="075d6-129">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="075d6-129">More Resources</span></span>  
 <span data-ttu-id="075d6-130">に加えて、このチュートリアルでは、検索することも統合の詳細については、次のリソースを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]とで導入された新しいアダプターを使用して Salesforce[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="075d6-130">In addition to this tutorial, you can also look at the following resources to understand more about integrating [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with Salesforce using the new adapters introduced in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="075d6-131">仮想ラボのデモンストレーション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で Salesforce の統合は[http://go.microsoft.com/fwlink/?LinkId=290930](http://go.microsoft.com/fwlink/?LinkId=290930)です。</span><span class="sxs-lookup"><span data-stu-id="075d6-131">A virtual lab demonstrating [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and Salesforce integration is available at [http://go.microsoft.com/fwlink/?LinkId=290930](http://go.microsoft.com/fwlink/?LinkId=290930).</span></span>  
  
-   <span data-ttu-id="075d6-132">このチュートリアルに基づくサンプルをダウンロード[http://go.microsoft.com/fwlink/?LinkId=290932](http://go.microsoft.com/fwlink/?LinkId=290932)です。</span><span class="sxs-lookup"><span data-stu-id="075d6-132">A sample based on this tutorial is available for download at [http://go.microsoft.com/fwlink/?LinkId=290932](http://go.microsoft.com/fwlink/?LinkId=290932).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="075d6-133">次の手順</span><span class="sxs-lookup"><span data-stu-id="075d6-133">Next steps</span></span>
  
-   [<span data-ttu-id="075d6-134">手順 1: サービス バスの Namespace を作成します。</span><span class="sxs-lookup"><span data-stu-id="075d6-134">Step 1: Create a Service Bus Namespace</span></span>](../core/step-1-create-a-service-bus-namespace.md)  
  
-   [<span data-ttu-id="075d6-135">手順 2: Salesforce システムをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="075d6-135">Step 2: Set up the Salesforce System</span></span>](../core/step-2-set-up-the-salesforce-system.md)  
  
-   [<span data-ttu-id="075d6-136">手順 3: Visual Studio での BizTalk Server ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="075d6-136">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)  
  
-   [<span data-ttu-id="075d6-137">手順 4: BizTalk Server ソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="075d6-137">Step 4: Configure the BizTalk Server Solution</span></span>](../core/step-4-configure-the-biztalk-server-solution.md)  
  
-   [<span data-ttu-id="075d6-138">手順 5: ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="075d6-138">Step 5: Test the Solution</span></span>](../core/step-5-test-the-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="075d6-139">参照</span><span class="sxs-lookup"><span data-stu-id="075d6-139">See Also</span></span>  
 [<span data-ttu-id="075d6-140">BizTalk Server チュートリアル</span><span class="sxs-lookup"><span data-stu-id="075d6-140">BizTalk Server Tutorials</span></span>](../core/biztalk-server-tutorials.md)