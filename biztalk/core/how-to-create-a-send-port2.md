---
title: "送信 Port2 を作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.admin.procedure.createsendport
helpviewer_keywords:
- managing [send ports], creating
- creating, send ports
- send ports, creating
ms.assetid: 7f0d07b8-1ac5-4032-bb08-2f7e05185f86
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 796ba5da53257d0f198e4b8bf13ee81835efcf4e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-send-port"></a><span data-ttu-id="052f9-102">送信ポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="052f9-102">How to Create a Send Port</span></span>
<span data-ttu-id="052f9-103">このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="052f9-103">This topic describes how to use the BizTalk Server Administration console to create a send port.</span></span> <span data-ttu-id="052f9-104">送信ポートを作成する場合、次のような送信ポートの種類を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="052f9-104">When creating a send port, you must select the type of send port to create, as follows:</span></span>  
  
-   <span data-ttu-id="052f9-105">静的な一方向 : 送信のみのポート。</span><span class="sxs-lookup"><span data-stu-id="052f9-105">Static one-way — a send-only port.</span></span>  
  
-   <span data-ttu-id="052f9-106">静的な送信請求 - 応答 : 送信先からの応答を待つ送信ポート。</span><span class="sxs-lookup"><span data-stu-id="052f9-106">Static solicit-response — a send port that waits for a reply from the destination.</span></span>  
  
-   <span data-ttu-id="052f9-107">動的な一方向 : 実行時にメッセージ プロパティに基づいてプロトコルおよび場所にバインドできる送信のみのポート。</span><span class="sxs-lookup"><span data-stu-id="052f9-107">Dynamic one-way — a send-only port that can be bound to a protocol and location at runtime based on message properties.</span></span>  
  
-   <span data-ttu-id="052f9-108">動的な送信請求 - 応答 : 応答を待つ送信ポート。実行時にメッセージ プロパティに基づいてプロトコルおよび場所にバインドできます。</span><span class="sxs-lookup"><span data-stu-id="052f9-108">Dynamic solicit-response — a send port that waits for a reply and can be bound to a protocol and location at runtime based on message properties.</span></span>  
  
 <span data-ttu-id="052f9-109">送信ポートを作成した後で、次の追加のステップを実行することにより構成を完了できます。</span><span class="sxs-lookup"><span data-stu-id="052f9-109">After you create a send port, you can perform the following additional steps to complete the configuration:</span></span>  
  
-   <span data-ttu-id="052f9-110">構成の詳細」の説明に従って、メッセージのエラーや、ポートのサービス ウィンドウ スケジュールでのメッセージの送信を再試行する回数などのトランスポート オプション[トランスポート高度なオプションの構成、送信ポートの方法](../core/how-to-configure-transport-advanced-options-for-a-send-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="052f9-110">Configure advanced transport options, such as the number of times to retry sending messages on message failure and the service window schedule for the port, as described in [How to Configure Transport Advanced Options for a Send Port](../core/how-to-configure-transport-advanced-options-for-a-send-port.md).</span></span>  
  
-   <span data-ttu-id="052f9-111">バックアップ トランスポートを構成する」の説明に従って、機能するために、主要なトランスポートが失敗した場合に備えて[送信ポートに対してバックアップ トランスポートのオプションを構成する方法](../core/how-to-configure-backup-transport-options-for-a-send-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="052f9-111">Configure a backup transport, in the event the primary transport fails to function, as described in [How to Configure Backup Transport Options for a Send Port](../core/how-to-configure-backup-transport-options-for-a-send-port.md).</span></span>  
  
-   <span data-ttu-id="052f9-112">」の説明に従って、メッセージ ボックスから、この送信ポートにルーティングするメッセージを決定するフィルターを構成する[送信ポートのフィルターを構成する方法](../core/how-to-configure-filters-for-a-send-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="052f9-112">Configure filters to determine which messages are routed to this send port from the message box, as described in [How to Configure Filters for a Send Port](../core/how-to-configure-filters-for-a-send-port.md).</span></span>  
  
-   <span data-ttu-id="052f9-113">セキュリティ証明書を暗号化または」の説明に従って、送信ポートによって処理されるドキュメントに署名する送信ポートに割り当てる[送信ポートに証明書を割り当てる方法](../core/how-to-assign-a-certificate-to-a-send-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="052f9-113">Assign a security certificate to the send port to encrypt or sign documents handled by the send port, as described in [How to Assign a Certificate to a Send Port](../core/how-to-assign-a-certificate-to-a-send-port.md).</span></span>  
  
-   <span data-ttu-id="052f9-114">送信ポートによって処理されるメッセージの追跡オプションを構成する」の説明に従って[送信ポートの追跡を構成する方法](../core/how-to-configure-tracking-for-a-send-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="052f9-114">Configure tracking options for messages handled by the send port, as described in [How to Configure Tracking for a Send Port](../core/how-to-configure-tracking-for-a-send-port.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="052f9-115">前提条件</span><span class="sxs-lookup"><span data-stu-id="052f9-115">Prerequisites</span></span>  
 <span data-ttu-id="052f9-116">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="052f9-116">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="052f9-117">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="052f9-117">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span> <span data-ttu-id="052f9-118">さらに、エンタープライズ シングル サインオン (SSO) データベースに対して SSO 関連の管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="052f9-118">In addition, you need to have SSO affiliate administrator permissions on the Enterprise Single Sign-On (SSO) database.</span></span> <span data-ttu-id="052f9-119">詳細については、次を参照してください。 [SSO ユーザー グループ](../core/sso-user-groups.md)です。</span><span class="sxs-lookup"><span data-stu-id="052f9-119">For more information, see [SSO User Groups](../core/sso-user-groups.md).</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="052f9-120">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="052f9-120">To create a send port</span></span>  
  
1.  <span data-ttu-id="052f9-121">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="052f9-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="052f9-122">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="052f9-122">In the console tree, expand the BizTalk group and the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="052f9-123">右クリック**送信ポート**、 をポイント**新規**、しを作成するポートの種類をクリックします。</span><span class="sxs-lookup"><span data-stu-id="052f9-123">Right-click **Send Ports**, point to **New**, and then click the type of port to create.</span></span>  
  
4.  <span data-ttu-id="052f9-124">**送信ポート プロパティ** ウィンドウで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="052f9-124">In the **Send Ports Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="052f9-125">プロパティ</span><span class="sxs-lookup"><span data-stu-id="052f9-125">Use this</span></span>|<span data-ttu-id="052f9-126">目的</span><span class="sxs-lookup"><span data-stu-id="052f9-126">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="052f9-127">**名前**</span><span class="sxs-lookup"><span data-stu-id="052f9-127">**Name**</span></span>|<span data-ttu-id="052f9-128">新しい送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="052f9-128">Type the name of the new send port.</span></span> <span data-ttu-id="052f9-129">この名前は、BizTalk グループ内で一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="052f9-129">This name must be unique in the BizTalk group.</span></span>|  
    |<span data-ttu-id="052f9-130">**トランスポートの種類**</span><span class="sxs-lookup"><span data-stu-id="052f9-130">**Transport Type**</span></span>|<span data-ttu-id="052f9-131">ドロップダウン リストから、適切なトランスポートの種類またはトランスポート プロトコルを選択します。</span><span class="sxs-lookup"><span data-stu-id="052f9-131">From the drop-down list, select the appropriate transport type, or transport protocol.</span></span> <span data-ttu-id="052f9-132">送信請求 - 応答のポートの場合、ドロップダウン リストでは、送信請求 - 応答をサポートするアダプターのみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="052f9-132">If the port is a solicit-response port, only transport types that support solicit-response are available in the list.</span></span> <span data-ttu-id="052f9-133">このプロパティは、静的ポートに対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="052f9-133">This property is visible only for static ports.</span></span>|  
    |<span data-ttu-id="052f9-134">**構成**</span><span class="sxs-lookup"><span data-stu-id="052f9-134">**Configure**</span></span>|<span data-ttu-id="052f9-135">トランスポートの種類を選択してクリックして**構成**を表示する、**トランスポートのプロパティ** ダイアログ ボックスは、トランスポート固有の構成オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="052f9-135">After you select the transport type, click **Configure** to display the **Transport Properties** dialog box, which provides transport-specific configuration options.</span></span> <span data-ttu-id="052f9-136">このプロパティは、静的ポートに対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="052f9-136">This property is visible only for static ports.</span></span> <span data-ttu-id="052f9-137">をクリックして**ヘルプ**の構成手順のダイアログ ボックスでします。</span><span class="sxs-lookup"><span data-stu-id="052f9-137">Click **Help** in the dialog box for configuration instructions.</span></span>|  
    |<span data-ttu-id="052f9-138">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="052f9-138">**Send handler**</span></span>|<span data-ttu-id="052f9-139">ドロップダウン リストから、送信アダプターが動作しているホスト インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="052f9-139">From the drop-down list, select the host instance on which the send adapter is running.</span></span> <span data-ttu-id="052f9-140">このプロパティは、静的ポートに対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="052f9-140">This property is visible only for static ports.</span></span>|  
    |<span data-ttu-id="052f9-141">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="052f9-141">**Send pipeline**</span></span>|<span data-ttu-id="052f9-142">ドロップダウン リストから、このポートの送信メッセージを処理するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="052f9-142">From the drop-down list, select the pipeline that processes the messages sent through this port.</span></span> <span data-ttu-id="052f9-143">パイプラインを選択した後、横の省略記号をクリックすることができます (**.**) を表示するボタン、**パイプラインの構成**ダイアログ ボックスで、この特定のポートのインスタンスごとのパイプライン プロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="052f9-143">After you select the pipeline, you can click the adjacent ellipsis (**…**) button to display the **Configure Pipeline** dialog box, where you configure per-instance pipeline properties for this specific port.</span></span> <span data-ttu-id="052f9-144">をクリックして**ヘルプ**の構成手順のダイアログ ボックスでします。</span><span class="sxs-lookup"><span data-stu-id="052f9-144">Click **Help** in the dialog box for configuration instructions.</span></span>|  
    |<span data-ttu-id="052f9-145">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="052f9-145">**Receive pipeline**</span></span>|<span data-ttu-id="052f9-146">ドロップダウン リストから、このポートの受信メッセージを処理するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="052f9-146">From the drop-down list, select the pipeline that processes messages received through this port.</span></span> <span data-ttu-id="052f9-147">このパイプラインでは、このパイプラインの受信メッセージに対する応答も送信されます。</span><span class="sxs-lookup"><span data-stu-id="052f9-147">Responses to messages received through this pipeline will also be sent through this pipeline.</span></span> <span data-ttu-id="052f9-148">パイプラインを選択した後、横の省略記号をクリックすることができます (**.**) を表示するボタン、**パイプラインの構成**ダイアログ ボックスで、この特定のポートのインスタンスごとのパイプライン プロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="052f9-148">After you select the pipeline, you can click the adjacent ellipsis (**…**) button to display the **Configure Pipeline** dialog box, where you configure per-instance pipeline properties for this specific port.</span></span> <span data-ttu-id="052f9-149">このプロパティは、送信請求 - 応答のポートに対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="052f9-149">This property is visible only for Solicit-Response ports.</span></span>|  
  
5.  <span data-ttu-id="052f9-150">左側のウィンドウで、送信請求-応答送信ポートを作成する場合にクリックして**受信マップ**とは、次の必要なかどうかを追加する複数のマップを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="052f9-150">If you are creating a solicit-response send port, in the left pane, click **Inbound Maps** and do the following, repeating as necessary if you want to add multiple maps:</span></span>  
  
    |<span data-ttu-id="052f9-151">プロパティ</span><span class="sxs-lookup"><span data-stu-id="052f9-151">Use this</span></span>|<span data-ttu-id="052f9-152">目的</span><span class="sxs-lookup"><span data-stu-id="052f9-152">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="052f9-153">**ソース ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="052f9-153">**Source Document**</span></span>|<span data-ttu-id="052f9-154">ドロップダウン リストから、受信マップの送信元ドキュメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="052f9-154">From the drop-down list, select the source document for the inbound map.</span></span> <span data-ttu-id="052f9-155">送信ポートには複数のマップを指定できますが、各マップには一意の送信元ドキュメントが必要です。</span><span class="sxs-lookup"><span data-stu-id="052f9-155">A send port may have more than one map, but each map should have a unique source document.</span></span>|  
    |<span data-ttu-id="052f9-156">**マップ**</span><span class="sxs-lookup"><span data-stu-id="052f9-156">**Map**</span></span>|<span data-ttu-id="052f9-157">ドロップダウン リストから、送信元ドキュメントと送信先ドキュメントに関連付けられているマップを選択します。</span><span class="sxs-lookup"><span data-stu-id="052f9-157">From the drop-down list, select the map to associate with the source and target documents.</span></span>|  
    |<span data-ttu-id="052f9-158">**対象のドキュメント**</span><span class="sxs-lookup"><span data-stu-id="052f9-158">**Target Document**</span></span>|<span data-ttu-id="052f9-159">ドロップダウン リストから、受信マップの送信先ドキュメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="052f9-159">From the drop-down list, select the target document for the inbound map.</span></span>|  
  
6.  <span data-ttu-id="052f9-160">左側のウィンドウでをクリックして**送信マップ**とは、次の必要なかどうかを追加する複数のマップを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="052f9-160">In the left pane, click **Outbound Maps** and do the following, repeating as necessary if you want to add multiple maps:</span></span>  
  
    |<span data-ttu-id="052f9-161">プロパティ</span><span class="sxs-lookup"><span data-stu-id="052f9-161">Use this</span></span>|<span data-ttu-id="052f9-162">目的</span><span class="sxs-lookup"><span data-stu-id="052f9-162">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="052f9-163">**ソース ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="052f9-163">**Source Document**</span></span>|<span data-ttu-id="052f9-164">ドロップダウン リストから、送信マップの送信元ドキュメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="052f9-164">From the drop-down list, select the source document for the outbound map.</span></span>|  
    |<span data-ttu-id="052f9-165">**マップ**</span><span class="sxs-lookup"><span data-stu-id="052f9-165">**Map**</span></span>|<span data-ttu-id="052f9-166">ドロップダウン リストから、送信元ドキュメントと送信先ドキュメントに関連付けられているマップを選択します。</span><span class="sxs-lookup"><span data-stu-id="052f9-166">From the drop-down list, select the map to associate with the source and target documents.</span></span>|  
    |<span data-ttu-id="052f9-167">**対象のドキュメント**</span><span class="sxs-lookup"><span data-stu-id="052f9-167">**Target Document**</span></span>|<span data-ttu-id="052f9-168">ドロップダウン リストから、送信マップの送信先ドキュメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="052f9-168">From the drop-down list, select the target document for the outbound map.</span></span>|  
  
7.  <span data-ttu-id="052f9-169">送信ポートの構成が完了、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="052f9-169">When finished configuring the send port, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="052f9-170">参照</span><span class="sxs-lookup"><span data-stu-id="052f9-170">See Also</span></span>  
 <span data-ttu-id="052f9-171">[作成して、送信ポートの構成](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="052f9-171">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 <span data-ttu-id="052f9-172">[パイプラインの管理](../core/managing-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="052f9-172">[Managing Pipelines](../core/managing-pipelines.md) </span></span>  
 [<span data-ttu-id="052f9-173">マップを管理します。</span><span class="sxs-lookup"><span data-stu-id="052f9-173">Managing Maps</span></span>](../core/managing-maps.md)