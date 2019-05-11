---
title: 手順 2:構成および開始、Application1 |Microsoft Docs
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
ms.openlocfilehash: 07fbdba63325f44a803fe4e9c5e83fbd5d31240e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392772"
---
# <a name="step-2-configure-and-start-the-application"></a><span data-ttu-id="e7470-102">手順 2:構成し、アプリケーションを起動します</span><span class="sxs-lookup"><span data-stu-id="e7470-102">Step 2: Configure and Start the Application</span></span>
<span data-ttu-id="e7470-103">![ステップ 2/3](../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="e7470-103">![Step 2 of 3](../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="e7470-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="e7470-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="e7470-105">**目標:** この手順では、構成し、EAISolution アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="e7470-105">**Objective:** In this step, you configure and start the EAISolution application.</span></span>  
  
 <span data-ttu-id="e7470-106">**目的:** 構成は、バインドに関するほとんどの場合です。</span><span class="sxs-lookup"><span data-stu-id="e7470-106">**Purpose:** The configuration is mostly about binding.</span></span>  <span data-ttu-id="e7470-107">バインディングは、オーケストレーション ポートなど、ロール リンクの論理エンドポイントとの送信などの物理的なエンドポイント間のマッピングを作成し、受信ポートまたはパーティします。</span><span class="sxs-lookup"><span data-stu-id="e7470-107">A binding creates a mapping between a logical endpoint, such as an orchestration port or a role link, and a physical endpoint, such as a send and receive port or party.</span></span> <span data-ttu-id="e7470-108">これにより、BizTalk ビジネス ソリューションの複数のコンポーネント間で通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e7470-108">This enables communication between different components of a BizTalk business solution.</span></span> <span data-ttu-id="e7470-109">バインドを作成するには BizTalk Server 管理コンソールを使用します。</span><span class="sxs-lookup"><span data-stu-id="e7470-109">You can create bindings by using the BizTalk Server Administration console.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e7470-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="e7470-110">Prerequisites</span></span>  
 <span data-ttu-id="e7470-111">このステップを開始する前に、以下の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="e7470-111">Note the following requirements before you begin this step:</span></span>  
  
- <span data-ttu-id="e7470-112">この手順を開始する前に行う必要があります[手順 1。プロジェクトの配置](../core/step-1-deploy-the-projects.md)します。</span><span class="sxs-lookup"><span data-stu-id="e7470-112">Before you begin this step you must complete [Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md).</span></span>  
  
- <span data-ttu-id="e7470-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7470-113">You must log on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="e7470-114">手順</span><span class="sxs-lookup"><span data-stu-id="e7470-114">Procedures</span></span>  
 <span data-ttu-id="e7470-115">BizTalk アプリケーションは、BizTalk Server ビジネス ソリューションの展開、管理、およびトラブルシューティングをすばやく簡単に行えるようにする BizTalk Server の機能です。</span><span class="sxs-lookup"><span data-stu-id="e7470-115">The BizTalk application is a feature of BizTalk Server that makes it quicker and easier to deploy, manage, and troubleshoot BizTalk Server business solutions.</span></span> <span data-ttu-id="e7470-116">BizTalk アプリケーションは、BizTalk Server ビジネス ソリューションで使用される "アイテム" の論理グループです。</span><span class="sxs-lookup"><span data-stu-id="e7470-116">A BizTalk application is a logical grouping of the items, called "artifacts," used in a BizTalk Server business solution.</span></span>  <span data-ttu-id="e7470-117">詳細については、次を参照してください。 [BizTalk アプリケーションとは何ですか?](../core/what-is-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="e7470-117">For more information, see [What Is a BizTalk Application?](../core/what-is-a-biztalk-application.md).</span></span>  <span data-ttu-id="e7470-118">[手順 1。プロジェクトの配置](../core/step-1-deploy-the-projects.md)、"EAISolution"に、プロジェクトを展開するアプリケーション名を構成します。</span><span class="sxs-lookup"><span data-stu-id="e7470-118">In [Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md), we configure the application name to be “EAISolution” before we deploy the projects.</span></span>  <span data-ttu-id="e7470-119">したがって、EAISolution アプリケーションには、オーケストレーション、2 つのスキーマおよびマップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7470-119">So the EAISolution application contains the orchestration, the two schema, and the map.</span></span>  
  
#### <a name="to-open-the-eaisolution-application-from-biztalk-server-administration-console"></a><span data-ttu-id="e7470-120">EAISolution アプリケーションを BizTalk Server 管理コンソールから開くには</span><span class="sxs-lookup"><span data-stu-id="e7470-120">To open the EAISolution application from BizTalk Server Administration Console</span></span>  
  
1. <span data-ttu-id="e7470-121">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e7470-121">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2. <span data-ttu-id="e7470-122">左側にあるコンソール ツリーで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、 をクリックし、**更新**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-122">In the console tree on the left side of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Refresh**.</span></span>  
  
3. <span data-ttu-id="e7470-123">展開**BizTalk グループ**、展開**アプリケーション**、 をクリックし、 **EAISolution**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-123">Expand **BizTalk Group**, expand **Applications**, and then click **EAISolution**.</span></span>  
  
   <span data-ttu-id="e7470-124">「[レッスン 2: ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)オーケストレーションを作成しました。</span><span class="sxs-lookup"><span data-stu-id="e7470-124">In [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md), we created an orchestration.</span></span>  <span data-ttu-id="e7470-125">オーケストレーションでは、論理ポートを定義しました。</span><span class="sxs-lookup"><span data-stu-id="e7470-125">In the orchestration, we defined the logical ports.</span></span>  <span data-ttu-id="e7470-126">次の手順では、物理ポートを定義して論理ポートにバインドします。</span><span class="sxs-lookup"><span data-stu-id="e7470-126">In the following procedures, you will define the physical ports and bind the physical ports to the logical ports.</span></span>  
  
#### <a name="to-create-the-receiverequest-port"></a><span data-ttu-id="e7470-127">ReceiveRequest ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="e7470-127">To create the ReceiveRequest port</span></span>  
  
1.  <span data-ttu-id="e7470-128">BizTalk Server 管理コンソールから下、 **EAISolution**ノードを右クリックして**受信ポート**、 をポイント**新規**、順にクリックします**一方向受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-128">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="e7470-129">[全般] タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e7470-129">On the General tab,  do the following:</span></span>  
  
    |<span data-ttu-id="e7470-130">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e7470-130">Use this</span></span>|<span data-ttu-id="e7470-131">目的</span><span class="sxs-lookup"><span data-stu-id="e7470-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e7470-132">**名前**</span><span class="sxs-lookup"><span data-stu-id="e7470-132">**Name**</span></span>|<span data-ttu-id="e7470-133">型**EAISolutionReceiveRequestPort**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-133">Type **EAISolutionReceiveRequestPort**.</span></span>|  
    |<span data-ttu-id="e7470-134">**失敗したメッセージのルーティングを有効にします。**</span><span class="sxs-lookup"><span data-stu-id="e7470-134">**Enable routing for failed messages**</span></span>|<span data-ttu-id="e7470-135">(選択解除)</span><span class="sxs-lookup"><span data-stu-id="e7470-135">(clear)</span></span>|  
  
3.  <span data-ttu-id="e7470-136">クリックして**受信場所**、 をクリックし、**新規**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-136">Click **Receive Locations**, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="e7470-137">[Receive Location1 - 受信場所のプロパティ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e7470-137">From Receive Location1 – Receive Location Properties, do the following:</span></span>  
  
    |<span data-ttu-id="e7470-138">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e7470-138">Use this</span></span>|<span data-ttu-id="e7470-139">目的</span><span class="sxs-lookup"><span data-stu-id="e7470-139">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e7470-140">**名前**</span><span class="sxs-lookup"><span data-stu-id="e7470-140">**Name**</span></span>|<span data-ttu-id="e7470-141">型**EAISolutionReceiveRequestLocation**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-141">Type **EAISolutionReceiveRequestLocation**.</span></span>|  
    |<span data-ttu-id="e7470-142">**型**</span><span class="sxs-lookup"><span data-stu-id="e7470-142">**Type**</span></span>|<span data-ttu-id="e7470-143">選択**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-143">Select **File**.</span></span>|  
    |<span data-ttu-id="e7470-144">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="e7470-144">**Receive handler**</span></span>|<span data-ttu-id="e7470-145">**[BizTalkServerApplication]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7470-145">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="e7470-146">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="e7470-146">**Receive pipeline**</span></span>|<span data-ttu-id="e7470-147">選択**XMLReceive**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-147">Select **XMLReceive**.</span></span>|  
  
5.  <span data-ttu-id="e7470-148">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="e7470-148">Click **Configure**.</span></span>  
  
6.  <span data-ttu-id="e7470-149">[FILE トランスポートのプロパティ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e7470-149">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="e7470-150">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e7470-150">Use this</span></span>|<span data-ttu-id="e7470-151">目的</span><span class="sxs-lookup"><span data-stu-id="e7470-151">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e7470-152">**受信フォルダー**</span><span class="sxs-lookup"><span data-stu-id="e7470-152">**Receive folder**</span></span>|<span data-ttu-id="e7470-153">型**C:\BTSTutorials\WareHouse\Request**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-153">Type **C:\BTSTutorials\WareHouse\Request**.</span></span>|  
  
7.  <span data-ttu-id="e7470-154">クリックして**OK** 3 回です。</span><span class="sxs-lookup"><span data-stu-id="e7470-154">Click **OK** three times.</span></span>  
  
#### <a name="to-create-the-senddecline-port"></a><span data-ttu-id="e7470-155">SendDecline ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="e7470-155">To create the SendDecline port</span></span>  
  
1.  <span data-ttu-id="e7470-156">BizTalk Server 管理コンソールから下、 **EAISolution**ノードを右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-156">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="e7470-157">[全般] タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e7470-157">On the General tab, do the following:</span></span>  
  
    |<span data-ttu-id="e7470-158">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e7470-158">Use this</span></span>|<span data-ttu-id="e7470-159">目的</span><span class="sxs-lookup"><span data-stu-id="e7470-159">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e7470-160">**名前**</span><span class="sxs-lookup"><span data-stu-id="e7470-160">**Name**</span></span>|<span data-ttu-id="e7470-161">型**EAISolutionSendDeclinePort**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-161">Type **EAISolutionSendDeclinePort**.</span></span>|  
    |<span data-ttu-id="e7470-162">**型**</span><span class="sxs-lookup"><span data-stu-id="e7470-162">**Type**</span></span>|<span data-ttu-id="e7470-163">選択**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-163">Select **File**.</span></span>|  
    |<span data-ttu-id="e7470-164">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="e7470-164">**Send handler**</span></span>|<span data-ttu-id="e7470-165">選択**BizTAlkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-165">Select **BizTAlkServerApplication**.</span></span>|  
    |<span data-ttu-id="e7470-166">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="e7470-166">**Send pipeline**</span></span>|<span data-ttu-id="e7470-167">選択**XML Transmit**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-167">Select **XML Transmit**.</span></span>|  
  
3.  <span data-ttu-id="e7470-168">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="e7470-168">Click **Configure**.</span></span>  
  
4.  <span data-ttu-id="e7470-169">[FILE トランスポートのプロパティ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e7470-169">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="e7470-170">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e7470-170">Use this</span></span>|<span data-ttu-id="e7470-171">目的</span><span class="sxs-lookup"><span data-stu-id="e7470-171">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e7470-172">**受信フォルダー**</span><span class="sxs-lookup"><span data-stu-id="e7470-172">**Receive folder**</span></span>|<span data-ttu-id="e7470-173">型**C:\BTSTutorials\WareHouse\RequestDecline**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-173">Type **C:\BTSTutorials\WareHouse\RequestDecline**.</span></span>|  
    |<span data-ttu-id="e7470-174">**[ファイル名]**</span><span class="sxs-lookup"><span data-stu-id="e7470-174">**File name**</span></span>|<span data-ttu-id="e7470-175">型**RequestDecline_%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-175">Type **RequestDecline_%MessageID%.xml**.</span></span>|  
  
5.  <span data-ttu-id="e7470-176">**[OK]** を 2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="e7470-176">Click **OK** twice.</span></span>  
  
#### <a name="to-create-the-sendtoerp-port"></a><span data-ttu-id="e7470-177">SendToERP ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="e7470-177">To create the SendToERP port</span></span>  
  
1.  <span data-ttu-id="e7470-178">BizTalk Server 管理コンソールから下、 **EAISolution**ノードを右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-178">From BizTalk Server Administration Console, under the **EAISolution** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="e7470-179">[全般] タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e7470-179">On the General tab, do the following:</span></span>  
  
    |<span data-ttu-id="e7470-180">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e7470-180">Use this</span></span>|<span data-ttu-id="e7470-181">目的</span><span class="sxs-lookup"><span data-stu-id="e7470-181">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e7470-182">**名前**</span><span class="sxs-lookup"><span data-stu-id="e7470-182">**Name**</span></span>|<span data-ttu-id="e7470-183">型**EAISolutionSendToERPPort**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-183">Type **EAISolutionSendToERPPort**.</span></span>|  
    |<span data-ttu-id="e7470-184">**型**</span><span class="sxs-lookup"><span data-stu-id="e7470-184">**Type**</span></span>|<span data-ttu-id="e7470-185">選択**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-185">Select **File**.</span></span>|  
    |<span data-ttu-id="e7470-186">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="e7470-186">**Send handler**</span></span>|<span data-ttu-id="e7470-187">選択**BizTAlkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-187">Select **BizTAlkServerApplication**.</span></span>|  
    |<span data-ttu-id="e7470-188">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="e7470-188">**Send pipeline**</span></span>|<span data-ttu-id="e7470-189">選択**XML Transmit**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-189">Select **XML Transmit**.</span></span>|  
  
3.  <span data-ttu-id="e7470-190">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="e7470-190">Click **Configure**.</span></span>  
  
4.  <span data-ttu-id="e7470-191">[FILE トランスポートのプロパティ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e7470-191">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="e7470-192">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e7470-192">Use this</span></span>|<span data-ttu-id="e7470-193">目的</span><span class="sxs-lookup"><span data-stu-id="e7470-193">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e7470-194">**受信フォルダー**</span><span class="sxs-lookup"><span data-stu-id="e7470-194">**Receive folder**</span></span>|<span data-ttu-id="e7470-195">型**C:\BTSTutorials\ERP\Request**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-195">Type **C:\BTSTutorials\ERP\Request**.</span></span>|  
    |<span data-ttu-id="e7470-196">**[ファイル名]**</span><span class="sxs-lookup"><span data-stu-id="e7470-196">**File name**</span></span>|<span data-ttu-id="e7470-197">型**Request_%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-197">Type **Request_%MessageID%.xml**.</span></span>|  
  
5.  <span data-ttu-id="e7470-198">**[OK]** を 2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="e7470-198">Click **OK** twice.</span></span>  
  
#### <a name="to-bind-the-ports"></a><span data-ttu-id="e7470-199">ポートをバインドするには</span><span class="sxs-lookup"><span data-stu-id="e7470-199">To bind the ports</span></span>  
  
1.  <span data-ttu-id="e7470-200">BizTalk Server 管理コンソールの右クリック**EAISolution**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-200">From BizTalk Server Administration Console, right-click **EAISolution**, and then click **Configure**.</span></span>  
  
2.  <span data-ttu-id="e7470-201">アプリケーションの構成から左側のウィンドウでクリックして**EAIProcess**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-201">From Configure Application, in the left pane, click **EAIProcess**.</span></span>  <span data-ttu-id="e7470-202">これは前に作成したオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="e7470-202">This is the orchestration we created.</span></span>  
  
3.  <span data-ttu-id="e7470-203">右側のウィンドウから、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e7470-203">From the right pane, do the following:</span></span>  
  
    |<span data-ttu-id="e7470-204">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e7470-204">Use this</span></span>|<span data-ttu-id="e7470-205">目的</span><span class="sxs-lookup"><span data-stu-id="e7470-205">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e7470-206">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="e7470-206">**Host**</span></span>|<span data-ttu-id="e7470-207">**[BizTalkServerApplication]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7470-207">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="e7470-208">**受信ポート**の**ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="e7470-208">**Receive Port** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="e7470-209">選択**EAISolutionReceiveReqeustPort**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-209">Select **EAISolutionReceiveReqeustPort**.</span></span>|  
    |<span data-ttu-id="e7470-210">**送信ポート/送信ポート グループ**の**ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="e7470-210">**Send PortsSend Port Groups** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="e7470-211">選択**EAISolutionSendDeclinePort**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-211">Select **EAISolutionSendDeclinePort**.</span></span>|  
    |<span data-ttu-id="e7470-212">**受信ポート**の**ReceiveRequestPort**</span><span class="sxs-lookup"><span data-stu-id="e7470-212">**Receive Port** for **ReceiveRequestPort**</span></span>|<span data-ttu-id="e7470-213">選択**EAISolutionSendToERPPort**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-213">Select **EAISolutionSendToERPPort**.</span></span>|  
  
4.  <span data-ttu-id="e7470-214">をクリックして**OK**構成を保存します。</span><span class="sxs-lookup"><span data-stu-id="e7470-214">Click **OK** to save the configuration.</span></span>  
  
#### <a name="to-start-the-application"></a><span data-ttu-id="e7470-215">アプリケーションを開始するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e7470-215">To start the application</span></span>  
  
1.  <span data-ttu-id="e7470-216">BizTalk Server 管理コンソールの右クリック**EAISolution**、 をクリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-216">From BizTalk Server Administration Console, right-click **EAISolution**, and then click **Start**.</span></span>  
  
2.  <span data-ttu-id="e7470-217">ダイアログ ボックスで、次のようにクリックします。**開始**します。</span><span class="sxs-lookup"><span data-stu-id="e7470-217">From the dialog, click **Start**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="e7470-218">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="e7470-218">What did I just do?</span></span>  
 <span data-ttu-id="e7470-219">このステップでは、EAIApplication アプリケーションを構成し、開始しました。</span><span class="sxs-lookup"><span data-stu-id="e7470-219">In this step, you configured and started the EAIApplication application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e7470-220">次の手順</span><span class="sxs-lookup"><span data-stu-id="e7470-220">Next Steps</span></span>  
 <span data-ttu-id="e7470-221">EAI ソリューションでメッセージを処理する方法をテストする[手順 3。ソリューションをテストする](../core/step-3-test-the-solution2.md)します。</span><span class="sxs-lookup"><span data-stu-id="e7470-221">You test how the EAI solution processes messages in [Step 3: Test the Solution](../core/step-3-test-the-solution2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7470-222">参照</span><span class="sxs-lookup"><span data-stu-id="e7470-222">See Also</span></span>  
 <span data-ttu-id="e7470-223">[ステップ 1: プロジェクトを配置します。](../core/step-1-deploy-the-projects.md) </span><span class="sxs-lookup"><span data-stu-id="e7470-223">[Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md) </span></span>  
 [<span data-ttu-id="e7470-224">ステップ 3:ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="e7470-224">Step 3: Test the Solution</span></span>](../core/step-3-test-the-solution2.md)