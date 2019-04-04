---
title: '手順 2: 構成し、開始、Application1 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cb061ca-acf4-4de4-a634-b3bb98876989
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8edeb1cdb1f24774ec7c1e615377d81e4393c9dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024552"
---
# <a name="step-2-configure-and-start-the-application"></a><span data-ttu-id="f4b9f-102">手順 2: 構成し、アプリケーションを起動します</span><span class="sxs-lookup"><span data-stu-id="f4b9f-102">Step 2: Configure and Start the Application</span></span>
<span data-ttu-id="f4b9f-103">![ステップ 2/3](../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="f4b9f-103">![Step 2 of 3](../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="f4b9f-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="f4b9f-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="f4b9f-105">**目標:** では、この手順では、構成し、EAISolution アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-105">**Objective:** In this step, you configure and start the EAISolution application.</span></span>  
  
 <span data-ttu-id="f4b9f-106">**目的:** 構成は、バインドに関するほとんどの場合は。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-106">**Purpose:** The configuration is mostly about binding.</span></span>  <span data-ttu-id="f4b9f-107">バインディングは、オーケストレーション ポートなど、ロール リンクの論理エンドポイントとの送信などの物理的なエンドポイント間のマッピングを作成し、受信ポートまたはパーティします。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-107">A binding creates a mapping between a logical endpoint, such as an orchestration port or a role link, and a physical endpoint, such as a send and receive port or party.</span></span> <span data-ttu-id="f4b9f-108">これにより、BizTalk ビジネス ソリューションの複数のコンポーネント間で通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-108">This enables communication between different components of a BizTalk business solution.</span></span> <span data-ttu-id="f4b9f-109">バインドを作成するには BizTalk Server 管理コンソールを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-109">You can create bindings by using the BizTalk Server Administration console.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f4b9f-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="f4b9f-110">Prerequisites</span></span>  
 <span data-ttu-id="f4b9f-111">このステップを開始する前に、以下の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-111">Note the following requirements before you begin this step:</span></span>  
  
- <span data-ttu-id="f4b9f-112">この手順を開始する前に行う必要があります[手順 1: プロジェクトの配置](../core/step-1-deploy-the-projects.md)します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-112">Before you begin this step you must complete [Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md).</span></span>  
  
- <span data-ttu-id="f4b9f-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-113">You must log on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="f4b9f-114">手順</span><span class="sxs-lookup"><span data-stu-id="f4b9f-114">Procedures</span></span>  
 <span data-ttu-id="f4b9f-115">BizTalk アプリケーションは、BizTalk Server ビジネス ソリューションの展開、管理、およびトラブルシューティングをすばやく簡単に行えるようにする BizTalk Server の機能です。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-115">The BizTalk application is a feature of BizTalk Server that makes it quicker and easier to deploy, manage, and troubleshoot BizTalk Server business solutions.</span></span> <span data-ttu-id="f4b9f-116">BizTalk アプリケーションは、BizTalk Server ビジネス ソリューションで使用される "アイテム" の論理グループです。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-116">A BizTalk application is a logical grouping of the items, called "artifacts," used in a BizTalk Server business solution.</span></span>  <span data-ttu-id="f4b9f-117">詳細については、[BizTalk アプリケーションとは何ですか?](../core/what-is-a-biztalk-application.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-117">For more information, see [What Is a BizTalk Application?](../core/what-is-a-biztalk-application.md).</span></span>  <span data-ttu-id="f4b9f-118">[手順 1: プロジェクトの配置](../core/step-1-deploy-the-projects.md)、"EAISolution"に、プロジェクトを展開するアプリケーション名を構成します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-118">In [Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md), we configure the application name to be “EAISolution” before we deploy the projects.</span></span>  <span data-ttu-id="f4b9f-119">したがって、EAISolution アプリケーションには、オーケストレーション、2 つのスキーマおよびマップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-119">So the EAISolution application contains the orchestration, the two schema, and the map.</span></span>  
  
#### <a name="to-open-the-eaisolution-application-from-biztalk-server-administration-console"></a><span data-ttu-id="f4b9f-120">EAISolution アプリケーションを BizTalk Server 管理コンソールから開くには</span><span class="sxs-lookup"><span data-stu-id="f4b9f-120">To open the EAISolution application from BizTalk Server Administration Console</span></span>  
  
1. <span data-ttu-id="f4b9f-121">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-121">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2. <span data-ttu-id="f4b9f-122">左側にあるコンソール ツリーで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、 をクリックし、**更新**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-122">In the console tree on the left side of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Refresh**.</span></span>  
  
3. <span data-ttu-id="f4b9f-123">展開**BizTalk グループ**、展開**アプリケーション**、 をクリックし、 **EAISolution**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-123">Expand **BizTalk Group**, expand **Applications**, and then click **EAISolution**.</span></span>  
  
   <span data-ttu-id="f4b9f-124">[レッスン 2: ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)オーケストレーションを作成しました。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-124">In [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md), we created an orchestration.</span></span>  <span data-ttu-id="f4b9f-125">オーケストレーションでは、論理ポートを定義しました。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-125">In the orchestration, we defined the logical ports.</span></span>  <span data-ttu-id="f4b9f-126">次の手順では、物理ポートを定義して論理ポートにバインドします。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-126">In the following procedures, you will define the physical ports and bind the physical ports to the logical ports.</span></span>  
  
#### <a name="to-create-the-receiverequest-port"></a><span data-ttu-id="f4b9f-127">ReceiveRequest ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="f4b9f-127">To create the ReceiveRequest port</span></span>  
  
1.  <span data-ttu-id="f4b9f-128">BizTalk Server 管理コンソールから下、 **EAISolution**ノードを右クリックして**受信ポート**、 をポイント**新規**、順にクリックします**一方向受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-128">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="f4b9f-129">[全般] タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-129">On the General tab,  do the following:</span></span>  
  
    |<span data-ttu-id="f4b9f-130">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f4b9f-130">Use this</span></span>|<span data-ttu-id="f4b9f-131">目的</span><span class="sxs-lookup"><span data-stu-id="f4b9f-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f4b9f-132">**名前**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-132">**Name**</span></span>|<span data-ttu-id="f4b9f-133">型**EAISolutionReceiveRequestPort**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-133">Type **EAISolutionReceiveRequestPort**.</span></span>|  
    |<span data-ttu-id="f4b9f-134">**失敗したメッセージのルーティングを有効にします。**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-134">**Enable routing for failed messages**</span></span>|<span data-ttu-id="f4b9f-135">(選択解除)</span><span class="sxs-lookup"><span data-stu-id="f4b9f-135">(clear)</span></span>|  
  
3.  <span data-ttu-id="f4b9f-136">クリックして**受信場所**、 をクリックし、**新規**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-136">Click **Receive Locations**, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="f4b9f-137">[Receive Location1 - 受信場所のプロパティ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-137">From Receive Location1 – Receive Location Properties, do the following:</span></span>  
  
    |<span data-ttu-id="f4b9f-138">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f4b9f-138">Use this</span></span>|<span data-ttu-id="f4b9f-139">目的</span><span class="sxs-lookup"><span data-stu-id="f4b9f-139">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f4b9f-140">**名前**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-140">**Name**</span></span>|<span data-ttu-id="f4b9f-141">型**EAISolutionReceiveRequestLocation**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-141">Type **EAISolutionReceiveRequestLocation**.</span></span>|  
    |<span data-ttu-id="f4b9f-142">**型**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-142">**Type**</span></span>|<span data-ttu-id="f4b9f-143">選択**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-143">Select **File**.</span></span>|  
    |<span data-ttu-id="f4b9f-144">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-144">**Receive handler**</span></span>|<span data-ttu-id="f4b9f-145">**[BizTalkServerApplication]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-145">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="f4b9f-146">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-146">**Receive pipeline**</span></span>|<span data-ttu-id="f4b9f-147">選択**XMLReceive**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-147">Select **XMLReceive**.</span></span>|  
  
5.  <span data-ttu-id="f4b9f-148">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-148">Click **Configure**.</span></span>  
  
6.  <span data-ttu-id="f4b9f-149">[FILE トランスポートのプロパティ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-149">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="f4b9f-150">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f4b9f-150">Use this</span></span>|<span data-ttu-id="f4b9f-151">目的</span><span class="sxs-lookup"><span data-stu-id="f4b9f-151">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f4b9f-152">**受信フォルダー**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-152">**Receive folder**</span></span>|<span data-ttu-id="f4b9f-153">型**C:\BTSTutorials\WareHouse\Request**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-153">Type **C:\BTSTutorials\WareHouse\Request**.</span></span>|  
  
7.  <span data-ttu-id="f4b9f-154">クリックして**OK** 3 回です。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-154">Click **OK** three times.</span></span>  
  
#### <a name="to-create-the-senddecline-port"></a><span data-ttu-id="f4b9f-155">SendDecline ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="f4b9f-155">To create the SendDecline port</span></span>  
  
1.  <span data-ttu-id="f4b9f-156">BizTalk Server 管理コンソールから下、 **EAISolution**ノードを右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-156">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="f4b9f-157">[全般] タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-157">On the General tab, do the following:</span></span>  
  
    |<span data-ttu-id="f4b9f-158">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f4b9f-158">Use this</span></span>|<span data-ttu-id="f4b9f-159">目的</span><span class="sxs-lookup"><span data-stu-id="f4b9f-159">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f4b9f-160">**名前**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-160">**Name**</span></span>|<span data-ttu-id="f4b9f-161">型**EAISolutionSendDeclinePort**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-161">Type **EAISolutionSendDeclinePort**.</span></span>|  
    |<span data-ttu-id="f4b9f-162">**型**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-162">**Type**</span></span>|<span data-ttu-id="f4b9f-163">選択**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-163">Select **File**.</span></span>|  
    |<span data-ttu-id="f4b9f-164">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-164">**Send handler**</span></span>|<span data-ttu-id="f4b9f-165">選択**BizTAlkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-165">Select **BizTAlkServerApplication**.</span></span>|  
    |<span data-ttu-id="f4b9f-166">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-166">**Send pipeline**</span></span>|<span data-ttu-id="f4b9f-167">選択**XML Transmit**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-167">Select **XML Transmit**.</span></span>|  
  
3.  <span data-ttu-id="f4b9f-168">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-168">Click **Configure**.</span></span>  
  
4.  <span data-ttu-id="f4b9f-169">[FILE トランスポートのプロパティ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-169">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="f4b9f-170">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f4b9f-170">Use this</span></span>|<span data-ttu-id="f4b9f-171">目的</span><span class="sxs-lookup"><span data-stu-id="f4b9f-171">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f4b9f-172">**受信フォルダー**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-172">**Receive folder**</span></span>|<span data-ttu-id="f4b9f-173">型**C:\BTSTutorials\WareHouse\RequestDecline**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-173">Type **C:\BTSTutorials\WareHouse\RequestDecline**.</span></span>|  
    |<span data-ttu-id="f4b9f-174">**[ファイル名]**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-174">**File name**</span></span>|<span data-ttu-id="f4b9f-175">型**RequestDecline_%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-175">Type **RequestDecline_%MessageID%.xml**.</span></span>|  
  
5.  <span data-ttu-id="f4b9f-176">**[OK]** を 2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-176">Click **OK** twice.</span></span>  
  
#### <a name="to-create-the-sendtoerp-port"></a><span data-ttu-id="f4b9f-177">SendToERP ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="f4b9f-177">To create the SendToERP port</span></span>  
  
1.  <span data-ttu-id="f4b9f-178">BizTalk Server 管理コンソールから下、 **EAISolution**ノードを右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-178">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="f4b9f-179">[全般] タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-179">On the General tab, do the following:</span></span>  
  
    |<span data-ttu-id="f4b9f-180">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f4b9f-180">Use this</span></span>|<span data-ttu-id="f4b9f-181">目的</span><span class="sxs-lookup"><span data-stu-id="f4b9f-181">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f4b9f-182">**名前**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-182">**Name**</span></span>|<span data-ttu-id="f4b9f-183">型**EAISolutionSendToERPPort**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-183">Type **EAISolutionSendToERPPort**.</span></span>|  
    |<span data-ttu-id="f4b9f-184">**型**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-184">**Type**</span></span>|<span data-ttu-id="f4b9f-185">選択**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-185">Select **File**.</span></span>|  
    |<span data-ttu-id="f4b9f-186">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-186">**Send handler**</span></span>|<span data-ttu-id="f4b9f-187">選択**BizTAlkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-187">Select **BizTAlkServerApplication**.</span></span>|  
    |<span data-ttu-id="f4b9f-188">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-188">**Send pipeline**</span></span>|<span data-ttu-id="f4b9f-189">選択**XML Transmit**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-189">Select **XML Transmit**.</span></span>|  
  
3.  <span data-ttu-id="f4b9f-190">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-190">Click **Configure**.</span></span>  
  
4.  <span data-ttu-id="f4b9f-191">[FILE トランスポートのプロパティ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-191">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="f4b9f-192">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f4b9f-192">Use this</span></span>|<span data-ttu-id="f4b9f-193">目的</span><span class="sxs-lookup"><span data-stu-id="f4b9f-193">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f4b9f-194">**受信フォルダー**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-194">**Receive folder**</span></span>|<span data-ttu-id="f4b9f-195">型**C:\BTSTutorials\ERP\Request**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-195">Type **C:\BTSTutorials\ERP\Request**.</span></span>|  
    |<span data-ttu-id="f4b9f-196">**[ファイル名]**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-196">**File name**</span></span>|<span data-ttu-id="f4b9f-197">型**Request_%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-197">Type **Request_%MessageID%.xml**.</span></span>|  
  
5.  <span data-ttu-id="f4b9f-198">**[OK]** を 2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-198">Click **OK** twice.</span></span>  
  
#### <a name="to-bind-the-ports"></a><span data-ttu-id="f4b9f-199">ポートをバインドするには</span><span class="sxs-lookup"><span data-stu-id="f4b9f-199">To bind the ports</span></span>  
  
1.  <span data-ttu-id="f4b9f-200">BizTalk Server 管理コンソールの右クリック**EAISolution**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-200">From BizTalk Server Administration Console, right-click **EAISolution**, and then click **Configure**.</span></span>  
  
2.  <span data-ttu-id="f4b9f-201">アプリケーションの構成から左側のウィンドウでクリックして**EAIProcess**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-201">From Configure Application, in the left pane, click **EAIProcess**.</span></span>  <span data-ttu-id="f4b9f-202">これは前に作成したオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-202">This is the orchestration we created.</span></span>  
  
3.  <span data-ttu-id="f4b9f-203">右側のウィンドウから、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-203">From the right pane, do the following:</span></span>  
  
    |<span data-ttu-id="f4b9f-204">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f4b9f-204">Use this</span></span>|<span data-ttu-id="f4b9f-205">目的</span><span class="sxs-lookup"><span data-stu-id="f4b9f-205">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f4b9f-206">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-206">**Host**</span></span>|<span data-ttu-id="f4b9f-207">**[BizTalkServerApplication]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-207">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="f4b9f-208">**受信ポート**の**ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-208">**Receive Port** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="f4b9f-209">選択**EAISolutionReceiveReqeustPort**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-209">Select **EAISolutionReceiveReqeustPort**.</span></span>|  
    |<span data-ttu-id="f4b9f-210">**送信ポート/送信ポート グループ**の**ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-210">**Send PortsSend Port Groups** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="f4b9f-211">選択**EAISolutionSendDeclinePort**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-211">Select **EAISolutionSendDeclinePort**.</span></span>|  
    |<span data-ttu-id="f4b9f-212">**受信ポート**の**ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="f4b9f-212">**Receive Port** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="f4b9f-213">選択**EAISolutionSendToERPPort**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-213">Select **EAISolutionSendToERPPort**.</span></span>|  
  
4.  <span data-ttu-id="f4b9f-214">をクリックして**OK**構成を保存します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-214">Click **OK** to save the configuration.</span></span>  
  
#### <a name="to-start-the-application"></a><span data-ttu-id="f4b9f-215">アプリケーションを開始するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-215">To start the application</span></span>  
  
1.  <span data-ttu-id="f4b9f-216">BizTalk Server 管理コンソールの右クリック**EAISolution**、 をクリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-216">From BizTalk Server Administration Console, right-click **EAISolution**, and then click **Start**.</span></span>  
  
2.  <span data-ttu-id="f4b9f-217">ダイアログ ボックスで、次のようにクリックします。**開始**します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-217">From the dialog, click **Start**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="f4b9f-218">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-218">What did I just do?</span></span>  
 <span data-ttu-id="f4b9f-219">このステップでは、EAIApplication アプリケーションを構成し、開始しました。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-219">In this step, you configured and started the EAIApplication application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f4b9f-220">次の手順</span><span class="sxs-lookup"><span data-stu-id="f4b9f-220">Next Steps</span></span>  
 <span data-ttu-id="f4b9f-221">EAI ソリューションでメッセージを処理する方法をテストする[手順 3: ソリューションをテストする](../core/step-3-test-the-solution2.md)します。</span><span class="sxs-lookup"><span data-stu-id="f4b9f-221">You test how the EAI solution processes messages in [Step 3: Test the Solution](../core/step-3-test-the-solution2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4b9f-222">参照</span><span class="sxs-lookup"><span data-stu-id="f4b9f-222">See Also</span></span>  
 <span data-ttu-id="f4b9f-223">[手順 1: 配置プロジェクト](../core/step-1-deploy-the-projects.md) </span><span class="sxs-lookup"><span data-stu-id="f4b9f-223">[Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md) </span></span>  
 [<span data-ttu-id="f4b9f-224">手順 3: ソリューションのテスト</span><span class="sxs-lookup"><span data-stu-id="f4b9f-224">Step 3: Test the Solution</span></span>](../core/step-3-test-the-solution2.md)