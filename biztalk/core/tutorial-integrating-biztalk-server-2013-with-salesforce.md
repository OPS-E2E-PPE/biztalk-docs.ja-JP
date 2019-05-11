---
title: チュートリアル:BizTalk Server 2013 を Salesforce と統合する |Microsoft Docs
description: Service Bus および BIzTalk Server を使用する Salesforce と統合するには
ms.custom: ''
ms.date: 12/07/2015
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06c9ae51-3f48-4086-883b-ab4d5b6e62e3
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2757c2a36c86bb302859f0174e8c53b5bb397025
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399169"
---
# <a name="tutorial-integrating-biztalk-server-2013-with-salesforce"></a><span data-ttu-id="ecaca-103">チュートリアル:BizTalk Server 2013 を Salesforce と統合します。</span><span class="sxs-lookup"><span data-stu-id="ecaca-103">Tutorial: Integrating BizTalk Server 2013 with Salesforce</span></span>
<span data-ttu-id="ecaca-104">校閲者:[Nick Hauenstein](http://social.msdn.microsoft.com/profile/nick.hauenstein/)、 [Steef-jan Wiggers](http://social.msdn.microsoft.com/profile/steef-jan%20wiggers)</span><span class="sxs-lookup"><span data-stu-id="ecaca-104">Reviewers: [Nick Hauenstein](http://social.msdn.microsoft.com/profile/nick.hauenstein/), [Steef-Jan Wiggers](http://social.msdn.microsoft.com/profile/steef-jan%20wiggers)</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ecaca-105">新たなアダプターのハイブリッドなシナリオの多くを構成する、オンプレミスと Azure のテクノロジが可能になりましたに関連するについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ecaca-105">introduces some new adapters that make a lot of hybrid scenarios, involving on-premises and Azure technologies now possible.</span></span> <span data-ttu-id="ecaca-106">ここでは、このチュートリアルでは、純粋なクラウド エンティティをオンプレミスと Salesforce の統合などを統合する方法を参照してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]いくつかの新しいアダプターを使用して、[!INCLUDE[winazure](../includes/winazure-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ecaca-106">In this tutorial, we see how to integrate a purely cloud entity like Salesforce integrate with an on-premises [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] using some of the new adapters and [!INCLUDE[winazure](../includes/winazure-md.md)].</span></span> <span data-ttu-id="ecaca-107">を始める前に統合することで実現するビジネス目標を理解しましょう[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Salesforce とします。</span><span class="sxs-lookup"><span data-stu-id="ecaca-107">Before we start, let’s understand the business objective we try to achieve by integrating [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with Salesforce.</span></span>  
  
 <span data-ttu-id="ecaca-108">でしたも作成ハイブリッド ソリューションに関する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と Salesforce の以前のバージョンに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションは Web サービス (SOAP) を使用する Salesforce との対話に関連するはるかに複雑になりますが、します。</span><span class="sxs-lookup"><span data-stu-id="ecaca-108">We could also create hybrid solutions involving [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and Salesforce with previous version of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], however the solution would be much more complex involving interaction with Salesforce by consuming a Web service (SOAP).</span></span> <span data-ttu-id="ecaca-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]し、新しいアダプターをソリューションがより容易にします。</span><span class="sxs-lookup"><span data-stu-id="ecaca-109">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the new adapters, the solution is that much easier.</span></span>  
  
## <a name="business-scenario"></a><span data-ttu-id="ecaca-110">ビジネス シナリオ</span><span class="sxs-lookup"><span data-stu-id="ecaca-110">Business Scenario</span></span>  
 <span data-ttu-id="ecaca-111">Northwind は、販売パイプラインを使用して顧客を追跡するためのソリューションとしての Salesforce オンライン CRM システムを使用します。</span><span class="sxs-lookup"><span data-stu-id="ecaca-111">Northwind uses the Salesforce online CRM system as their solution for tracking customers through the sales pipeline.</span></span> <span data-ttu-id="ecaca-112">Northwind がなどのオンプレミス システムを希望するたびに、Salesforce で営業案件が作成される[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通知を受ける他のダウン ストリーム システムがそのデータを選択し、関連するその他のプロセスを開始できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ecaca-112">Every time a sales opportunity is created in the Salesforce system, Northwind wants its on-premise systems, such as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], to be notified so that other down-stream systems can pick up that data and start other relevant processes.</span></span> <span data-ttu-id="ecaca-113">使用可能な新しいアダプターを使用して、このソリューションを実装する計画を Northwind[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の一部のコンポーネントを含めることでも[!INCLUDE[winazure](../includes/winazure-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ecaca-113">Northwind plans to implement this solution using the new adapters available with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and also by including some components of [!INCLUDE[winazure](../includes/winazure-md.md)].</span></span> <span data-ttu-id="ecaca-114">これは、ようなソリューションが、エンド ツー エンドのデータ フローの検索です。</span><span class="sxs-lookup"><span data-stu-id="ecaca-114">This is how the end-to-end data flow looks like for the solution:</span></span>  
  
- <span data-ttu-id="ecaca-115">営業担当者は、Salesforce システムで、"opportunity"を作成します。</span><span class="sxs-lookup"><span data-stu-id="ecaca-115">A sales representative creates an “opportunity” in the Salesforce system.</span></span>  
  
- <span data-ttu-id="ecaca-116">ホストされているリレー エンドポイントに通知が送信された営業案件の状態が"Closed Won"に設定されている場合[!INCLUDE[winazure](../includes/winazure-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ecaca-116">When the status of the opportunity is set to “Closed Won”, a notification is sent to a relay endpoint hosted on [!INCLUDE[winazure](../includes/winazure-md.md)].</span></span>  
  
- <span data-ttu-id="ecaca-117">新しい Wcf-basichttprelay アダプターを使用して、通知情報が上に渡される[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オンプレミスがシステムに格納されています。</span><span class="sxs-lookup"><span data-stu-id="ecaca-117">Using the new WCF-BasicHttpRelay adapter, the notification information is passed on to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system housed on-premise.</span></span>  
  
- <span data-ttu-id="ecaca-118">通知の一部として受け取った情報を使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は営業案件に関する詳細を取得する、新しい Wcf-webhttp アダプターを使用して、Salesforce で REST エンドポイントを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ecaca-118">Using the information received as part of the notification, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] invokes a REST endpoint in Salesforce, using the new WCF-WebHttp adapter, to get more information about the opportunity.</span></span>  
  
- <span data-ttu-id="ecaca-119">最後に、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Salesforce から受信した情報を使用して、社内の SQL Server データベース テーブルで、発注エントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="ecaca-119">Finally, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the information received from Salesforce to create a purchase order entry in an in-house SQL Server database table.</span></span>  
  
  <span data-ttu-id="ecaca-120">これらは、このソリューションで説明されている統合目標を達成するために必要な手順のセットです。</span><span class="sxs-lookup"><span data-stu-id="ecaca-120">These are the set of steps that you must perform to achieve the integration objective outlined in this solution.</span></span> <span data-ttu-id="ecaca-121">これらの各手順には、見てソリューションの作成に進むとアクティビティの広範なセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ecaca-121">Each of these steps involves broad set of activities that we’ll look at as we proceed with creating the solution.</span></span>  
  
  <span data-ttu-id="ecaca-122">エンド ツー エンドの統合ソリューションを説明する図を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ecaca-122">Here’s an illustration that describes the end-to-end integration solution:</span></span>  
  
  <span data-ttu-id="ecaca-123">![BizTalk Server と Salesforce の統合シナリオ](../core/media/bts-sf-scenario.gif "BTS_SF_Scenario")</span><span class="sxs-lookup"><span data-stu-id="ecaca-123">![BizTalk Server and Salesforce integration scenario](../core/media/bts-sf-scenario.gif "BTS_SF_Scenario")</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ecaca-124">前提条件</span><span class="sxs-lookup"><span data-stu-id="ecaca-124">Prerequisites</span></span>  
 <span data-ttu-id="ecaca-125">このソリューションを設定するコンピューターにインストールされている、次のソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="ecaca-125">You must have the following software installed on the computer where you set up this solution:</span></span>  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]  
  
- [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]  
  
- [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]  
  
  <span data-ttu-id="ecaca-126">次のサービスのサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="ecaca-126">You must have the following service subscriptions:</span></span>  
  
- <span data-ttu-id="ecaca-127">A[!INCLUDE[winazure](../includes/winazure-md.md)]サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="ecaca-127">A [!INCLUDE[winazure](../includes/winazure-md.md)] subscription</span></span>  
  
- <span data-ttu-id="ecaca-128">Salesforce の Developer Edition アカウント</span><span class="sxs-lookup"><span data-stu-id="ecaca-128">Salesforce Developer Edition account</span></span>  
  
## <a name="more-resources"></a><span data-ttu-id="ecaca-129">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="ecaca-129">More Resources</span></span>  
 <span data-ttu-id="ecaca-130">このチュートリアルでは、だけでなく参照することできますも統合の詳細については、次のリソース[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で導入された新しいアダプターを使用して、Salesforce で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ecaca-130">In addition to this tutorial, you can also look at the following resources to understand more about integrating [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with Salesforce using the new adapters introduced in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="ecaca-131">バーチャル ラボ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で Salesforce との統合は[ http://go.microsoft.com/fwlink/?LinkId=290930](http://go.microsoft.com/fwlink/?LinkId=290930)します。</span><span class="sxs-lookup"><span data-stu-id="ecaca-131">A virtual lab demonstrating [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and Salesforce integration is available at [http://go.microsoft.com/fwlink/?LinkId=290930](http://go.microsoft.com/fwlink/?LinkId=290930).</span></span>  
  
- <span data-ttu-id="ecaca-132">このチュートリアルに基づいてサンプルをダウンロードできる[ http://go.microsoft.com/fwlink/?LinkId=290932](http://go.microsoft.com/fwlink/?LinkId=290932)します。</span><span class="sxs-lookup"><span data-stu-id="ecaca-132">A sample based on this tutorial is available for download at [http://go.microsoft.com/fwlink/?LinkId=290932](http://go.microsoft.com/fwlink/?LinkId=290932).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ecaca-133">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ecaca-133">Next steps</span></span>
  
-   [<span data-ttu-id="ecaca-134">ステップ 1: Service Bus の Namespace を作成します。</span><span class="sxs-lookup"><span data-stu-id="ecaca-134">Step 1: Create a Service Bus Namespace</span></span>](../core/step-1-create-a-service-bus-namespace.md)  
  
-   [<span data-ttu-id="ecaca-135">手順 2:Salesforce システムを設定します。</span><span class="sxs-lookup"><span data-stu-id="ecaca-135">Step 2: Set up the Salesforce System</span></span>](../core/step-2-set-up-the-salesforce-system.md)  
  
-   [<span data-ttu-id="ecaca-136">ステップ 3:Visual Studio で BizTalk Server ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ecaca-136">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)  
  
-   [<span data-ttu-id="ecaca-137">手順 4:BizTalk Server ソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="ecaca-137">Step 4: Configure the BizTalk Server Solution</span></span>](../core/step-4-configure-the-biztalk-server-solution.md)  
  
-   [<span data-ttu-id="ecaca-138">手順 5:ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="ecaca-138">Step 5: Test the Solution</span></span>](../core/step-5-test-the-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="ecaca-139">参照</span><span class="sxs-lookup"><span data-stu-id="ecaca-139">See Also</span></span>  
 [<span data-ttu-id="ecaca-140">BizTalk Server チュートリアル</span><span class="sxs-lookup"><span data-stu-id="ecaca-140">BizTalk Server Tutorials</span></span>](../core/biztalk-server-tutorials.md)