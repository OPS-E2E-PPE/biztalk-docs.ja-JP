---
title: ホスト インスタンスの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98ba10a6-c5e7-4dec-98f1-4e6ba44c2851
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c95dc019d1d6ed885d195f0c871fd91178b9a58a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006819"
---
# <a name="add-a-host-instance"></a><span data-ttu-id="82dbb-102">ホスト インスタンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="82dbb-102">Add a Host Instance</span></span>

## <a name="overview"></a><span data-ttu-id="82dbb-103">概要</span><span class="sxs-lookup"><span data-stu-id="82dbb-103">Overview</span></span>
<span data-ttu-id="82dbb-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールまたは Windows Management Instrumentation (WMI) を使用すると、ホスト インスタンスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="82dbb-104">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console or Windows Management Instrumentation (WMI) to add host instances.</span></span> <span data-ttu-id="82dbb-105">しかし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では一度に 1 つのサーバーにしかホスト インスタンスを追加できません。</span><span class="sxs-lookup"><span data-stu-id="82dbb-105">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] you can only add a host instance to one server at a time.</span></span> <span data-ttu-id="82dbb-106">ホスト インスタンスの詳細については、次を参照してください。[ホスト インスタンス](../core/host-instances.md)します。</span><span class="sxs-lookup"><span data-stu-id="82dbb-106">For more information about host instances, see [Host Instances](../core/host-instances.md).</span></span> <span data-ttu-id="82dbb-107">WMI を使用して、ホスト インスタンスを追加する方法については、次を参照してください。 **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="82dbb-107">For information about using WMI to add a host instance, see **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="82dbb-108">ホスト インスタンスを追加すると、そのホストのインスタンスは BizTalk Server のインスタンスにマップされます。</span><span class="sxs-lookup"><span data-stu-id="82dbb-108">Adding a host instance maps the instance of a given host to an instance of BizTalk Server.</span></span> <span data-ttu-id="82dbb-109">既存のホスト インスタンスを修復する必要がある場合は、ホスト インスタンスのプロパティを更新できます。</span><span class="sxs-lookup"><span data-stu-id="82dbb-109">If you have an existing host instance that you must repair, you can update the host instance properties.</span></span> <span data-ttu-id="82dbb-110">既存のホスト インスタンスを再度追加するには、インスタンスを停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82dbb-110">You must stop an existing host instance before you can add it again.</span></span> <span data-ttu-id="82dbb-111">ホスト インスタンスの停止については、次を参照してください。[ホスト インスタンスを停止する方法](../core/how-to-stop-a-host-instance.md)します。</span><span class="sxs-lookup"><span data-stu-id="82dbb-111">For information about stopping a host instance, see [How to Stop a Host Instance](../core/how-to-stop-a-host-instance.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82dbb-112">サポート技術情報資料 184802「User32.dll または Kernel32.dll の初期化に失敗」で利用可能な手順が従う必要があります詳細 26 のホスト インスタンスを作成する場合は、 [ http://go.microsoft.com/fwlink/?LinkId=26176](http://go.microsoft.com/fwlink/?LinkId=26176)します。</span><span class="sxs-lookup"><span data-stu-id="82dbb-112">If you want to create more that 26 host instances, you must follow the instructions in Knowledge Base article 184802, "User32.dll or Kernel32.dll Fails to Initialize," which is available at [http://go.microsoft.com/fwlink/?LinkId=26176](http://go.microsoft.com/fwlink/?LinkId=26176).</span></span> <span data-ttu-id="82dbb-113">このサポート技術情報の資料に記載されている内容を反映した後で、ホスト インスタンスを追加する必要がある場合は、BTSNTSvc サービスの各インスタンスに割り当てるメモリ量を減らしてみてください。</span><span class="sxs-lookup"><span data-stu-id="82dbb-113">If you require additional host instances after you apply the recommendations in this Knowledge Base article, you can try reducing the amount of memory available for each instance of the BTSNTSvc service.</span></span> <span data-ttu-id="82dbb-114">メモリ量を減らすことによって、追加のインスタンスを作成するのに必要なメモリを提供できます。</span><span class="sxs-lookup"><span data-stu-id="82dbb-114">This will provide additional memory necessary to create more instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82dbb-115">サービス アカウントには、ホスト インスタンスのインストール先サーバーに対する "サービスとしてログオン" アクセス許可が自動的に与えられます。</span><span class="sxs-lookup"><span data-stu-id="82dbb-115">The service account will automatically be granted log on as service permissions on the server where the host instance is installed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="82dbb-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="82dbb-116">Prerequisites</span></span>  
 <span data-ttu-id="82dbb-117">ここで示す手順を実行するには、管理者グループのメンバーおよび BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="82dbb-117">To perform this procedure, you must be logged on as a member of the Administrators group and the BizTalk Server Administrators group.</span></span>  
  
 <span data-ttu-id="82dbb-118">また、次のデータベースが置かれているサーバーにおいて、db_securityadmin SQL Server データベース ロールおよび securityadmin SQL Server ロールのメンバーであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="82dbb-118">In addition, you must also be a member of the db_securityadmin SQL Server Database role and the securityadmin SQL Server Role on the server(s) where the following databases are:</span></span>  
  
-   <span data-ttu-id="82dbb-119">BAM プライマリ インポート (BAMPrimaryImport)</span><span class="sxs-lookup"><span data-stu-id="82dbb-119">BAM Primary Import (BAMPrimaryImport)</span></span>  
  
-   <span data-ttu-id="82dbb-120">BizTalk 管理 (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="82dbb-120">BizTalk Management (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="82dbb-121">BizTalk メッセージ ボックス (BizTalkMsgBoxDb) (すべて)</span><span class="sxs-lookup"><span data-stu-id="82dbb-121">BizTalk MessageBox (BizTalkMsgBoxDb) (all)</span></span>  
  
-   <span data-ttu-id="82dbb-122">BizTalk 追跡 (BizTalk DTADb)</span><span class="sxs-lookup"><span data-stu-id="82dbb-122">BizTalk Tracking (BizTalk DTADb)</span></span>  
  
-   <span data-ttu-id="82dbb-123">ルール エンジン (BizTalkRuleEngineDb)</span><span class="sxs-lookup"><span data-stu-id="82dbb-123">Rule Engine (BizTalkRuleEngineDb)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="82dbb-124">ホスト インスタンスのアカウント情報は、BizTalk Server 管理コンソールまたは Windows Management Instrumentation (WMI) スクリプトを使用して更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="82dbb-124">We recommend that you update account information for host instances by using the BizTalk Server Administration Console or a Windows Management Instrumentation (WMI) script.</span></span> <span data-ttu-id="82dbb-125">これにより、BizTalk Server が BizTalk Server データベースのアカウント情報を更新し、データベースとホスト インスタンス間でセキュリティ構成が同期された状態を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="82dbb-125">This ensures that BizTalk Server can update the account information in the BizTalk Server databases and keep the security configuration between the databases and host instance synchronized.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="82dbb-126">手順</span><span class="sxs-lookup"><span data-stu-id="82dbb-126">Steps</span></span>
  
1. <span data-ttu-id="82dbb-127">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="82dbb-127">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="82dbb-128">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]BizTalk グループを展開し、クリックして**プラットフォームの設定**します。</span><span class="sxs-lookup"><span data-stu-id="82dbb-128">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, and then click **Platform Settings**.</span></span>  
  
3. <span data-ttu-id="82dbb-129">右クリック**ホスト インスタンス**、 をクリックして**新規**、 をクリックし、**ホスト インスタンス**します。</span><span class="sxs-lookup"><span data-stu-id="82dbb-129">Right-click **Host Instances**, click **New**, and then click **Host Instance**.</span></span>  
  
4. <span data-ttu-id="82dbb-130">**ホスト インスタンスのプロパティ** ダイアログ ボックスで、次の操作をクリックして**OK**:</span><span class="sxs-lookup"><span data-stu-id="82dbb-130">In the **Host Instance Properties** dialog box, do the following, and then click **OK**:</span></span>  
  
   |<span data-ttu-id="82dbb-131">プロパティ</span><span class="sxs-lookup"><span data-stu-id="82dbb-131">Use this</span></span>|<span data-ttu-id="82dbb-132">目的</span><span class="sxs-lookup"><span data-stu-id="82dbb-132">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="82dbb-133">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="82dbb-133">**Host name**</span></span>|<span data-ttu-id="82dbb-134">選択したサーバーに関連付けられているホストの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="82dbb-134">Displays the name of the host associated with the selected server.</span></span>|  
   |<span data-ttu-id="82dbb-135">**[サーバー]**</span><span class="sxs-lookup"><span data-stu-id="82dbb-135">**Server**</span></span>|<span data-ttu-id="82dbb-136">選択したホストに関連付けられているサーバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="82dbb-136">Displays the server associated with the selected host.</span></span>|  
   |<span data-ttu-id="82dbb-137">**ログオン**</span><span class="sxs-lookup"><span data-stu-id="82dbb-137">**Logon**</span></span>|<span data-ttu-id="82dbb-138">ホスト インスタンスを実行する、新しいサービス アカウントのアカウント名を表示します。</span><span class="sxs-lookup"><span data-stu-id="82dbb-138">Displays the account name of the new service account under which the host instance will run.</span></span>|  
   |<span data-ttu-id="82dbb-139">**構成**</span><span class="sxs-lookup"><span data-stu-id="82dbb-139">**Configure**</span></span>|<span data-ttu-id="82dbb-140">表示するをクリックして、**ログオン資格情報**] ダイアログ ボックスの [アカウント名とホスト インスタンスを実行するアカウントのパスワードを入力できます。</span><span class="sxs-lookup"><span data-stu-id="82dbb-140">Click to display the **Logon Credentials** dialog box, where you can enter the account name and password of the account under which the host instance will run.</span></span>|  
   |<span data-ttu-id="82dbb-141">**ホスト インスタンスの開始を無効にします。**</span><span class="sxs-lookup"><span data-stu-id="82dbb-141">**Disable host instance from starting**</span></span>|<span data-ttu-id="82dbb-142">選択したホストの状態を有効から無効に変更する場合、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="82dbb-142">Select this check box to change the status of the selected host from enabled to disabled.</span></span> <span data-ttu-id="82dbb-143">ホスト インスタンスを開始せずに設定を保持する場合は、インスタンスを無効にすると便利です。</span><span class="sxs-lookup"><span data-stu-id="82dbb-143">Disabling a host instance is useful if you do not want the host instance to start, but you do want to preserve its settings.</span></span>|  
  
   <span data-ttu-id="82dbb-144">ホスト インスタンスをインストールしたら、インスタンスを再起動して、メッセージがメッセージ ボックス データベースにルーティングされるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="82dbb-144">After you install a host instance, you must start it so that it can route messages to the MessageBox databases.</span></span> <span data-ttu-id="82dbb-145">ホスト インスタンスの開始方法の詳細については、次を参照してください。[ホスト インスタンスを開始する方法](../core/how-to-start-a-host-instance.md)します。</span><span class="sxs-lookup"><span data-stu-id="82dbb-145">For information about starting a host instance, see [How to Start a Host Instance](../core/how-to-start-a-host-instance.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="82dbb-146">既知の問題</span><span class="sxs-lookup"><span data-stu-id="82dbb-146">Known Issues</span></span>  
  
#### <a name="a-biztalk-host-instance-is-created-with-a-status-of-uninstall-failed-if-the-designated-biztalk-server-runtime-computer-is-not-available-during-host-instance-creation"></a><span data-ttu-id="82dbb-147">BizTalk ホスト インスタンスの作成時に、指定した BizTalk Server ランタイム コンピューターを利用できない場合、状態が "アンインストールの失敗" のホスト インスタンスが作成される</span><span class="sxs-lookup"><span data-stu-id="82dbb-147">A BizTalk Host instance is created with a status of "Uninstall failed" if the designated BizTalk Server runtime computer is not available during host instance creation</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="82dbb-148">問題</span><span class="sxs-lookup"><span data-stu-id="82dbb-148">Problem</span></span>  
 <span data-ttu-id="82dbb-149">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンピューターとは別のリモート コンピューター上に BizTalk 管理コンソールがインストールされている場合、このリモート [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターが利用できない状態にあっても、この [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューター上にホスト インスタンスの作成を試みることが可能です。</span><span class="sxs-lookup"><span data-stu-id="82dbb-149">If the BizTalk Administration Console is installed on a machine that is remote to a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computer, it is possible to attempt to create a host instance on the remote [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer even if the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer is unavailable.</span></span>  
  
 <span data-ttu-id="82dbb-150">利用できない [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューター上に BizTalk ホストのインスタンスを作成しようとすると、次のエラー メッセージを示すダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82dbb-150">If you attempt to create an instance of a BizTalk host on a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer that is unavailable, a dialog box with the following error message is displayed:</span></span>  
  
 <span data-ttu-id="82dbb-151">ホストのインスタンスのインストール\<*ホスト名*\>サーバー \<*サーバー名*\>できませんでした。</span><span class="sxs-lookup"><span data-stu-id="82dbb-151">Installation of instace of host \<*host name*\> on server \<*server name*\> failed.</span></span>  
  
 <span data-ttu-id="82dbb-152">追加情報:</span><span class="sxs-lookup"><span data-stu-id="82dbb-152">Additional information:</span></span>  
  
 <span data-ttu-id="82dbb-153">RPC サーバーを利用できません。</span><span class="sxs-lookup"><span data-stu-id="82dbb-153">The RPC server is unavailable.</span></span> <span data-ttu-id="82dbb-154">(WinMgmt)。</span><span class="sxs-lookup"><span data-stu-id="82dbb-154">(WinMgmt)</span></span>  
  
 <span data-ttu-id="82dbb-155">[OK] をクリックしてダイアログ ボックスを消すと、次のエラー メッセージを示すダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82dbb-155">When you click OK to dismiss the dialog box, a dialog box with the following error message is displayed:</span></span>  
  
 <span data-ttu-id="82dbb-156">中止されたホストのインストールをクリーンアップする\<*ホスト名*\>サーバー \<*サーバー名*\>できませんでした。</span><span class="sxs-lookup"><span data-stu-id="82dbb-156">Cleaning up aborted installation of host \<*host name*\> on server \<*server name*\> failed.</span></span>  
  
 <span data-ttu-id="82dbb-157">追加情報:</span><span class="sxs-lookup"><span data-stu-id="82dbb-157">Additional information:</span></span>  
  
 <span data-ttu-id="82dbb-158">Windows NT サービス BTSSvc を削除するときにエラーが発生しました {*\<GUID\>*}。</span><span class="sxs-lookup"><span data-stu-id="82dbb-158">A failure occurred when deleting the Windows NT service BTSSvc{*\<GUID\>*}.</span></span> <span data-ttu-id="82dbb-159">(WinMgmt)。</span><span class="sxs-lookup"><span data-stu-id="82dbb-159">(WinMgmt)</span></span>  
  
 <span data-ttu-id="82dbb-160">クリックすると**OK**をこのダイアログ ボックスを閉じるには、BizTalk ホストのインスタンスは、BizTalk 管理コンソールに表示されます、**状態**の**アンインストールに失敗しました**.</span><span class="sxs-lookup"><span data-stu-id="82dbb-160">When you click **OK** to dismiss this dialog box, the instance of the BizTalk host will be visible in the BizTalk Administration Console with a **Status** of **Uninstall failed**.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="82dbb-161">原因</span><span class="sxs-lookup"><span data-stu-id="82dbb-161">Cause</span></span>  
 <span data-ttu-id="82dbb-162">ホスト インスタンスの作成時には、指定した [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューター上にホスト インスタンスがインストールされる前に、BizTalk 管理データベースにエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="82dbb-162">When a host instance is created, an entry is made in the BizTalk Management database before the host instance is installed onto the designated [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer.</span></span> <span data-ttu-id="82dbb-163">指定した [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューター上へのホスト インスタンスのインストールに失敗すると、BizTalk 管理プログラムは、そのホスト インスタンスのアンインストールを試みます。しかし、指定した [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターが利用できないため、アンインストールにも失敗します。</span><span class="sxs-lookup"><span data-stu-id="82dbb-163">If the installation of the host instance onto the designated [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer fails, the BizTalk Administration program will attempt to uninstall the host instance but since the designated [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer is unavailable the uninstall fails as well.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="82dbb-164">解決策</span><span class="sxs-lookup"><span data-stu-id="82dbb-164">Resolution</span></span>  
 <span data-ttu-id="82dbb-165">BizTalk ホスト インスタンスが BizTalk 管理コンソールの状態で作成された場合**アンインストールに失敗しました**、ホスト インスタンスを削除し、ホスト インスタンスを再作成後、指定した BizTalk Server コンピューターが使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="82dbb-165">If a BizTalk host instance is created in the BizTalk Admininstration Console with a status of **Uninstall failed**, delete the host instance and recreate the host instance after the designated BizTalk Server computer becomes available.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82dbb-166">BizTalk 管理コンソールで、BizTalk ホスト インスタンスが作成されたかどうか、**状態**の**アンインストールに失敗しました**ホスト インスタンスは、指定した後でもは機能できません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターが再び使用可能です。</span><span class="sxs-lookup"><span data-stu-id="82dbb-166">If a BizTalk host instance is created in the BizTalk Administration Console with a **Status** of **Uninstall failed** the host instance will not be functional even after the designated [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer becomes available again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82dbb-167">参照</span><span class="sxs-lookup"><span data-stu-id="82dbb-167">See Also</span></span>  
 <span data-ttu-id="82dbb-168">[BizTalk ホストとホスト インスタンスの管理](../core/managing-biztalk-hosts-and-host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="82dbb-168">[Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md) </span></span>  
 <span data-ttu-id="82dbb-169">[ホスト インスタンスを開始します。](../core/how-to-start-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="82dbb-169">[Start a Host Instance](../core/how-to-start-a-host-instance.md) </span></span>  
 <span data-ttu-id="82dbb-170">[ホスト インスタンスを停止します。](../core/how-to-stop-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="82dbb-170">[Stop a Host Instance](../core/how-to-stop-a-host-instance.md) </span></span>  
 <span data-ttu-id="82dbb-171">[ホスト インスタンスを削除します。](../core/how-to-delete-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="82dbb-171">[Delete a Host Instance](../core/how-to-delete-a-host-instance.md) </span></span>  
 [<span data-ttu-id="82dbb-172">ホスト インスタンスのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="82dbb-172">Modify Host Instance Properties</span></span>](../core/how-to-modify-host-instance-properties.md)