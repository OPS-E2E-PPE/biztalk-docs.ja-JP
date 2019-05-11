---
title: サービスを再起動またはシャット ダウンする手順 |Microsoft Docs
description: 開始、停止、一時停止、再開、または BizTalk Server の再起動のサービスまたは BizTalk Server コンピューターをシャット ダウン
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d6449ba-2892-49c6-a697-847608d10ec5
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85e8c353e4a8fa157352aa62238b107a07831465
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333987"
---
# <a name="restart-biztalk-services-or-shut-down-the-biztalk-server"></a><span data-ttu-id="ecc7b-103">、BizTalk サービスを再起動またはシャット ダウン、BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ecc7b-103">Restart BizTalk services, or shut down the BizTalk Server</span></span>

<span data-ttu-id="ecc7b-104">次の表に、ユーザーが開始、停止、一時停止、再開、または再起動できる BizTalk Server サービスを示します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-104">The following table lists the BizTalk Server services that you can start, stop, pause, resume, or restart:</span></span>  
  
|<span data-ttu-id="ecc7b-105">名前</span><span class="sxs-lookup"><span data-stu-id="ecc7b-105">Name</span></span>|<span data-ttu-id="ecc7b-106">説明</span><span class="sxs-lookup"><span data-stu-id="ecc7b-106">Description</span></span>|<span data-ttu-id="ecc7b-107">スタートアップの種類</span><span class="sxs-lookup"><span data-stu-id="ecc7b-107">Startup Type</span></span>|<span data-ttu-id="ecc7b-108">依存関係</span><span class="sxs-lookup"><span data-stu-id="ecc7b-108">Dependencies</span></span>|  
|----------|-----------------|------------------|------------------|  
|<span data-ttu-id="ecc7b-109">BizTalk Service BizTalk Group:*\<BizTalkServerApplication\>*</span><span class="sxs-lookup"><span data-stu-id="ecc7b-109">BizTalk Service BizTalk Group: *\<BizTalkServerApplication\>*</span></span>|<span data-ttu-id="ecc7b-110">BizTalk Server アプリケーション サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-110">Provides the BizTalk Server application service.</span></span>|<span data-ttu-id="ecc7b-111">自動</span><span class="sxs-lookup"><span data-stu-id="ecc7b-111">Automatic</span></span>|<span data-ttu-id="ecc7b-112">エンタープライズ シングル サインオン (SSO) サービス</span><span class="sxs-lookup"><span data-stu-id="ecc7b-112">-   Enterprise Single Sign-On (SSO) Service</span></span><br /><span data-ttu-id="ecc7b-113">イベント ログ</span><span class="sxs-lookup"><span data-stu-id="ecc7b-113">-   Event Log</span></span><br /><span data-ttu-id="ecc7b-114">-リモート プロシージャ コール (RPC)</span><span class="sxs-lookup"><span data-stu-id="ecc7b-114">-   Remote Procedure Call (RPC)</span></span>|  
|<span data-ttu-id="ecc7b-115">エンタープライズ シングル サインオン サービス</span><span class="sxs-lookup"><span data-stu-id="ecc7b-115">Enterprise Single Sign-On Service</span></span>|<span data-ttu-id="ecc7b-116">エンタープライズ アプリケーションにシングル サインオン サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-116">Provides single sign-on services to enterprise applications.</span></span>|<span data-ttu-id="ecc7b-117">自動</span><span class="sxs-lookup"><span data-stu-id="ecc7b-117">Automatic</span></span>|<span data-ttu-id="ecc7b-118">ローカルにインストールされる SQL Server の場合</span><span class="sxs-lookup"><span data-stu-id="ecc7b-118">With SQL Server installed locally:</span></span><br /><br /> <span data-ttu-id="ecc7b-119">-COM + システム アプリケーション</span><span class="sxs-lookup"><span data-stu-id="ecc7b-119">-   COM+ System Application</span></span><br /><span data-ttu-id="ecc7b-120">-リモート プロシージャ コール (RPC)</span><span class="sxs-lookup"><span data-stu-id="ecc7b-120">-   Remote Procedure Call (RPC)</span></span><br /><span data-ttu-id="ecc7b-121">SQL Server (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="ecc7b-121">-   SQL Server (MSSQLSERVER)</span></span><br /><br /> <span data-ttu-id="ecc7b-122">リモートにインストールされる SQL Server の場合</span><span class="sxs-lookup"><span data-stu-id="ecc7b-122">With SQL Server installed remotely:</span></span><br /><br /> <span data-ttu-id="ecc7b-123">-COM + システム アプリケーション</span><span class="sxs-lookup"><span data-stu-id="ecc7b-123">-   COM+ System Application</span></span><br /><span data-ttu-id="ecc7b-124">-リモート プロシージャ コール (RPC) なし</span><span class="sxs-lookup"><span data-stu-id="ecc7b-124">-   Remote Procedure Call (RPC)None</span></span>|  
|<span data-ttu-id="ecc7b-125">ルール エンジン更新サービス</span><span class="sxs-lookup"><span data-stu-id="ecc7b-125">Rule Engine Update Service</span></span>|<span data-ttu-id="ecc7b-126">ポリシーの展開または展開解除について、ユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-126">Notifies users about the deployment or undeployment of policies.</span></span>|<span data-ttu-id="ecc7b-127">Automatic</span><span class="sxs-lookup"><span data-stu-id="ecc7b-127">Automatic</span></span>|<span data-ttu-id="ecc7b-128">なし</span><span class="sxs-lookup"><span data-stu-id="ecc7b-128">None</span></span>|  
  
 
## <a name="start-stop-pause-resume-or-restart-a-biztalk-server-service"></a><span data-ttu-id="ecc7b-129">開始、停止、一時停止、再開、または BizTalk Server サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-129">Start, stop, pause, resume, or restart a BizTalk Server service</span></span>  
 <span data-ttu-id="ecc7b-130">ことができます開始、停止、一時停止、再開、または Services.msc、またはコマンド プロンプトを使用して、BizTalk Server サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-130">You can start, stop, pause, resume, or restart a BizTalk Server service by using Services.msc, or using the command prompt.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="ecc7b-131">前提条件</span><span class="sxs-lookup"><span data-stu-id="ecc7b-131">Prerequisites</span></span>  
 <span data-ttu-id="ecc7b-132">ここで示す手順を実行するには、ローカル コンピューターの Administrators グループに属しているか、適切な権限を委任されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-132">To perform this procedure, you must be a member of the Administrators group on the local computer, or you must have been delegated the appropriate authority.</span></span> <span data-ttu-id="ecc7b-133">コンピューターがドメインに参加している場合は、Domain Admins グループのメンバーがここで示す手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-133">If the computer is joined to a domain, members of the Domain Admins group might be able to perform this procedure.</span></span> <span data-ttu-id="ecc7b-134">セキュリティを高めるために、実行時アカウントを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-134">As a security best practice, consider using Run as to perform this procedure.</span></span> 
  
### <a name="use-services-in-control-panel"></a><span data-ttu-id="ecc7b-135">コントロール パネルの サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-135">Use Services in Control Panel</span></span>  
  
1.  <span data-ttu-id="ecc7b-136">[サービス] を開きます。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-136">Open Services.</span></span> <span data-ttu-id="ecc7b-137">をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-137">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
2.  <span data-ttu-id="ecc7b-138">適切な BizTalk Server サービスを右クリックし、をクリックし、**開始**、**停止**、**一時停止**、**再開**、または**再起動**します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-138">Right-click the appropriate BizTalk Server service and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
### <a name="use-a-command-prompt"></a><span data-ttu-id="ecc7b-139">コマンド プロンプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-139">Use a command prompt</span></span>  
  
1.  <span data-ttu-id="ecc7b-140">[スタート] メニューを右クリックして**コマンド プロンプト**を選択します**詳細**、選び**管理者として実行**</span><span class="sxs-lookup"><span data-stu-id="ecc7b-140">From the start menu, right-click **Command prompt**, select **More**, and select **Run as Administrator**</span></span>
  
2.  <span data-ttu-id="ecc7b-141">次のいずれかを入力、 *ServiceName*開始、停止、一時停止、または再開する BizTalk Server サービスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-141">Type one of the following, where *ServiceName* is the name of the BizTalk Server service you want to start, stop, pause, or resume:</span></span>  
  
    -   <span data-ttu-id="ecc7b-142">サービスを開始するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-142">To start a service, type:</span></span>  
  
         <span data-ttu-id="ecc7b-143">**net start** *ServiceName*</span><span class="sxs-lookup"><span data-stu-id="ecc7b-143">**net start** *ServiceName*</span></span>  
  
    -   <span data-ttu-id="ecc7b-144">サービスを停止するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-144">To stop a service, type:</span></span>  
  
         <span data-ttu-id="ecc7b-145">**net stop** *ServiceName*</span><span class="sxs-lookup"><span data-stu-id="ecc7b-145">**net stop** *ServiceName*</span></span>  
  
    -   <span data-ttu-id="ecc7b-146">サービスを一時停止するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-146">To pause a service, type:</span></span>  
  
         <span data-ttu-id="ecc7b-147">**net pause** *ServiceName*</span><span class="sxs-lookup"><span data-stu-id="ecc7b-147">**net pause** *ServiceName*</span></span>  
  
    -   <span data-ttu-id="ecc7b-148">サービスを再開するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-148">To resume a service, type:</span></span>  
  
         <span data-ttu-id="ecc7b-149">**net 続行** *ServiceName*</span><span class="sxs-lookup"><span data-stu-id="ecc7b-149">**net continue** *ServiceName*</span></span>  

    |<span data-ttu-id="ecc7b-150">BizTalk サービス</span><span class="sxs-lookup"><span data-stu-id="ecc7b-150">BizTalk service</span></span>|<span data-ttu-id="ecc7b-151">ServiceName</span><span class="sxs-lookup"><span data-stu-id="ecc7b-151">ServiceName</span></span>|  
    |---|---|  
    |<span data-ttu-id="ecc7b-152">BizTalk Service BizTalk Group:BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="ecc7b-152">BizTalk Service BizTalk Group: BizTalkServerApplication</span></span>|<span data-ttu-id="ecc7b-153">btssvc$biztalkserverapplication</span><span class="sxs-lookup"><span data-stu-id="ecc7b-153">btssvc$biztalkserverapplication</span></span>|  
    |<span data-ttu-id="ecc7b-154">エンタープライズ シングル サインオン サービス</span><span class="sxs-lookup"><span data-stu-id="ecc7b-154">Enterprise Single Sign-On Service</span></span>|<span data-ttu-id="ecc7b-155">Entsso</span><span class="sxs-lookup"><span data-stu-id="ecc7b-155">Entsso</span></span>|  
    |<span data-ttu-id="ecc7b-156">ルール エンジン更新サービス</span><span class="sxs-lookup"><span data-stu-id="ecc7b-156">Rule Engine Update Service</span></span>|<span data-ttu-id="ecc7b-157">ruleengineupdateservice</span><span class="sxs-lookup"><span data-stu-id="ecc7b-157">ruleengineupdateservice</span></span>|
  
## <a name="shut-down-biztalk-server"></a><span data-ttu-id="ecc7b-158">BizTalk Server をシャット ダウンします。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-158">Shut down BizTalk Server</span></span>  

### <a name="prerequisites"></a><span data-ttu-id="ecc7b-159">前提条件</span><span class="sxs-lookup"><span data-stu-id="ecc7b-159">Prerequisites</span></span>  
-   <span data-ttu-id="ecc7b-160">シャット ダウンする BizTalk server のローカルの administrators グループのメンバーであるアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-160">Sign in with an account that is a member of the local administrators group on the BizTalk server that you want to shut down.</span></span> <span data-ttu-id="ecc7b-161">これはサービスを停止するために必要です。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-161">This is necessary so you can stop services.</span></span>  
-   <span data-ttu-id="ecc7b-162">BizTalk Server 管理者グループまたは BizTalk Server Operators グループのメンバーであるアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-162">Sign in with an account that is a member of the BizTalk Server Administrators group or BizTalk Server Operators group.</span></span> 

### <a name="task-overview"></a><span data-ttu-id="ecc7b-163">タスクの概要</span><span class="sxs-lookup"><span data-stu-id="ecc7b-163">Task overview</span></span>
1. <span data-ttu-id="ecc7b-164">受信場所を無効にし、アクティブな各アプリケーションの部分停止を実行することによってオーケストレーションと送信ポートを停止します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-164">Disable receive locations, and stop orchestrations and send ports by performing a partial stop on every active application.</span></span> <span data-ttu-id="ecc7b-165">アプリケーションの削除または再展開を行う場合は、完全停止を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-165">You should perform a full stop only if you intend to remove or redeploy an application.</span></span> <span data-ttu-id="ecc7b-166">詳細については、次を参照してください。 [BizTalk アプリケーション開始および停止方法](../core/how-to-start-and-stop-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-166">For more information, see [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
2. <span data-ttu-id="ecc7b-167">ホスト インスタンスを停止します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-167">Stop host instances.</span></span> <span data-ttu-id="ecc7b-168">詳細については、次を参照してください。[ホスト インスタンスを停止する方法](../core/how-to-stop-a-host-instance.md)します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-168">For more information, see [How to Stop a Host Instance](../core/how-to-stop-a-host-instance.md).</span></span>  
  
3. <span data-ttu-id="ecc7b-169">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-169">Shut down [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="ecc7b-170">参照してください**開始、停止、一時停止、再開、または BizTalk Server サービスを再起動する方法**(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-170">See **How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services** (in this topic).</span></span>
  
4. <span data-ttu-id="ecc7b-171">インターネット インフォメーション サービス (IIS) をシャットダウンするか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーション プールと Web サイトを停止します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-171">Shut down Internet Information Services (IIS), or stop [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application pools and Web sites.</span></span> <span data-ttu-id="ecc7b-172">サーバーを完全にシャットダウンする場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-172">If you are going to shut down the server entirely you can skip this step.</span></span> <span data-ttu-id="ecc7b-173">メンテナンスまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションの展開または再展開のために [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を停止する場合は、この手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-173">If you are stopping [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for maintenance or to deploy or undeploy a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, you should perform this step.</span></span> <span data-ttu-id="ecc7b-174">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に関連付けられた Web サイトおよびアプリケーション プールのみを停止した場合、他の IIS 関連プロセスは引き続き実行されます。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-174">When you stop only the Web sites and application pools associated with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], other IIS-related processes will continue to run.</span></span>  
  
    <span data-ttu-id="ecc7b-175">この手順の進め方は、使用している IIS のバージョンにより若干異なります。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-175">How you proceed with this step depends to some extent on which version of IIS you are using.</span></span> <span data-ttu-id="ecc7b-176">IIS 6 では、アプリケーション プールと Web サイトを停止できます。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-176">IIS 6 permits you to stop application pools and Web sites.</span></span> <span data-ttu-id="ecc7b-177">IIS 6 では、IIS Admin Service を停止して、アプリケーション プールと Web サイトを含むすべての IIS アクティビティをシャットダウンすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-177">With IIS 6 you can also stop the IIS Admin Service to shut down all IIS activity including application pools and Web sites.</span></span> <span data-ttu-id="ecc7b-178">IIS 7.0 は IIS 6.0 よりもモジュール化が進んでおり、1 つのスイッチですべての IIS 7.0 アクティビティを停止することはできないので、Web サイトとアプリケーション プールを個別に停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-178">IIS 7.0 is more modular than IIS 6.0, and there is no single switch you can use to stop all IIS 7.0 activities, so you will need to stop Web sites and application pools separately.</span></span>  
  
    <span data-ttu-id="ecc7b-179">アプリケーション プールおよび仮想アプリケーション (Web サイトおよび Web サービス) BizTalk Server で使用されるの一覧は、次を参照してください。 [BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-179">For a list of application pools and virtual applications (Web sites and Web services) used by BizTalk Server, see [Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span></span>  
  
   <span data-ttu-id="ecc7b-180">開始して、IIS アプリケーション プールを停止しています。 詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=140513](http://go.microsoft.com/fwlink/?LinkID=140513)します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-180">For information about starting and stopping application pools in IIS, see [http://go.microsoft.com/fwlink/?LinkID=140513](http://go.microsoft.com/fwlink/?LinkID=140513).</span></span>  
  
   <span data-ttu-id="ecc7b-181">開始して、IIS で Web サーバーを停止する方法については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=140695](http://go.microsoft.com/fwlink/?LinkId=140695)します。</span><span class="sxs-lookup"><span data-stu-id="ecc7b-181">For information about starting and stopping the Web Server in IIS, see [http://go.microsoft.com/fwlink/?LinkId=140695](http://go.microsoft.com/fwlink/?LinkId=140695).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecc7b-182">参照</span><span class="sxs-lookup"><span data-stu-id="ecc7b-182">See Also</span></span>  
 <span data-ttu-id="ecc7b-183">[BizTalk アプリケーション開始および停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="ecc7b-183">[How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="ecc7b-184">ホスト インスタンスを停止する方法</span><span class="sxs-lookup"><span data-stu-id="ecc7b-184">How to Stop a Host Instance</span></span>](../core/how-to-stop-a-host-instance.md)   