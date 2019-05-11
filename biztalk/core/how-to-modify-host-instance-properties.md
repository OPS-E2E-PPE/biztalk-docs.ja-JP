---
title: ホスト インスタンスのプロパティの変更 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a35ca0c8-89b3-483a-b2fc-c8f43a8864d1
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ba3afcb2c5879f43f15c515b468bb020c772560
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384572"
---
# <a name="update-host-instance-properties"></a><span data-ttu-id="7681b-102">ホスト インスタンスのプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="7681b-102">Update Host Instance Properties</span></span>

## <a name="overview"></a><span data-ttu-id="7681b-103">概要</span><span class="sxs-lookup"><span data-stu-id="7681b-103">Overview</span></span>
<span data-ttu-id="7681b-104">BizTalk Server 管理コンソールまたは Windows Management Instrumentation (WMI) を使用すると、ホスト インスタンスに変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="7681b-104">You can use the BizTalk Server Administration Console or Windows Management Instrumentation (WMI) to modify host instances.</span></span> <span data-ttu-id="7681b-105">ホスト インスタンスを実行しているサービス アカウントを変更したり、ホスト インスタンスを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="7681b-105">You can modify the service account running a host instance.</span></span> <span data-ttu-id="7681b-106">ホスト インスタンスを無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7681b-106">You can also disable a host instance.</span></span> <span data-ttu-id="7681b-107">たとえば、ホスト インスタンスの設定を維持する必要があるが、インスタンスを起動しないようにする必要がある場合は、インスタンスを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="7681b-107">For example, if you want to preserve the settings for a host instance and you do not want it to start, you can disable it.</span></span> <span data-ttu-id="7681b-108">ホスト インスタンスの詳細については、次を参照してください。[ホスト インスタンス](../core/host-instances.md)します。</span><span class="sxs-lookup"><span data-stu-id="7681b-108">For more information about host instances, see [Host Instances](../core/host-instances.md).</span></span>  
  
 <span data-ttu-id="7681b-109">信頼済みホストのホスト インスタンスと信頼されていないホストのホスト インスタンスで同じサービス アカウントを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7681b-109">Host instances of trusted hosts and host instances of non-trusted hosts cannot use the same service accounts.</span></span> <span data-ttu-id="7681b-110">ホスト インスタンスの信頼設定を変更し、ホスト インスタンスで他のホスト インスタンスが使用しているサービス アカウントを使用する必要がある場合は、次のいずれかを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7681b-110">If you want to change the trust setting of a host instance and the host instance uses a service account that other host instances use, you can do one of the following:</span></span>  
  
-   <span data-ttu-id="7681b-111">信頼設定を新しいサービス アカウントに変更するホスト インスタンスのサービス アカウントを変更できます。</span><span class="sxs-lookup"><span data-stu-id="7681b-111">You can change the service account of the host instance for which you want to change the trust settings to a new service account.</span></span>  
  
-   <span data-ttu-id="7681b-112">ホスト インスタンスのサービス アカウントを、同じ信頼設定の他のホスト インスタンスで使用する既存のサービス アカウントに変更できます。</span><span class="sxs-lookup"><span data-stu-id="7681b-112">You can change the service account of the host instance to an existing service account that other host instances with the same trust setting use.</span></span>  
  
-   <span data-ttu-id="7681b-113">ホスト インスタンスを削除し、別の信頼設定とサービス アカウントを使用するホスト インスタンスを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="7681b-113">You can delete the host instance, and re-create it with a different trust setting and service account.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="7681b-114">ホスト インスタンスのプロパティを更新して、ホスト インスタンスの資格情報を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7681b-114">You must change the credentials for a host instance by updating the properties of the host instance.</span></span> <span data-ttu-id="7681b-115">サービスに対応する資格情報を変更する場合、ホスト インスタンスに対して指定するサービス アカウントは、そのホスト上のグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7681b-115">If you change the credentials of the corresponding service, the service account you specify for the host instance must be a member of the group on the host.</span></span> <span data-ttu-id="7681b-116">サービス スナップインまたはコンピューターの管理コンソールを使用してホストの資格情報を変更してはいけません。ホスト インスタンスが正常に動作しなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="7681b-116">Do not use the Services snap-in or the Computer Management console to change the credentials of host instance, otherwise the host instance may not function properly.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="7681b-117">ホスト インスタンスの資格情報を変更する場合は、対応する SQL Server の資格情報も変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7681b-117">If you change the credentials of a host instance, you must also change the corresponding SQL Server credentials.</span></span> <span data-ttu-id="7681b-118">SQL Server の資格情報を更新しないと、ホスト インスタンスは正常に動作しません。</span><span class="sxs-lookup"><span data-stu-id="7681b-118">If you do not update the SQL Server credentials, the host instance will not function properly.</span></span>  
  
 <span data-ttu-id="7681b-119">WMI を使用して、ホスト インスタンスを変更する方法については、次を参照してください。 **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7681b-119">For information about using WMI to modify a host instance, see **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="7681b-120">前提条件</span><span class="sxs-lookup"><span data-stu-id="7681b-120">Prerequisites</span></span>  
 <span data-ttu-id="7681b-121">ここで示す手順を実行するには、管理者グループのメンバーおよび BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7681b-121">To perform this procedure, you must be logged on as a member of the Administrators group and the BizTalk Server Administrators group.</span></span>  
  
 <span data-ttu-id="7681b-122">また、次のデータベースが置かれているサーバーにおいて、db_securityadmin SQL Server データベース ロールおよび securityadmin SQL Server ロールのメンバーであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="7681b-122">In addition, you must also be a member of the db_securityadmin SQL Server Database role and the securityadmin SQL Server Role on the server(s) where the following databases are:</span></span>  
  
-   <span data-ttu-id="7681b-123">BAM プライマリ インポート (BAMPrimaryImport)</span><span class="sxs-lookup"><span data-stu-id="7681b-123">BAM Primary Import (BAMPrimaryImport)</span></span>  
  
-   <span data-ttu-id="7681b-124">BizTalk 管理 (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="7681b-124">BizTalk Management (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="7681b-125">BizTalk メッセージ ボックス (BizTalkMsgBoxDb) (すべて)</span><span class="sxs-lookup"><span data-stu-id="7681b-125">BizTalk MessageBox (BizTalkMsgBoxDb) (all)</span></span>  
  
-   <span data-ttu-id="7681b-126">BizTalk 追跡 (BizTalk DTADb)</span><span class="sxs-lookup"><span data-stu-id="7681b-126">BizTalk Tracking (BizTalk DTADb)</span></span>  
  
-   <span data-ttu-id="7681b-127">ルール エンジン (BizTalkRuleEngineDb)</span><span class="sxs-lookup"><span data-stu-id="7681b-127">Rule Engine (BizTalkRuleEngineDb)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="7681b-128">ホスト インスタンスのアカウント情報は、BizTalk Server 管理コンソールまたは Windows Management Instrumentation (WMI) スクリプトを使用して更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7681b-128">We recommend that you update account information for host instances by using the BizTalk Server Administration Console or a Windows Management Instrumentation (WMI) script.</span></span> <span data-ttu-id="7681b-129">これにより、BizTalk Server が BizTalk Server データベースのアカウント情報を更新し、データベースとホスト インスタンス間でセキュリティ構成が同期された状態を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="7681b-129">This ensures that BizTalk Server can update the account information in the BizTalk Server databases and keep the security configuration between the databases and host instance synchronized.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="7681b-130">手順</span><span class="sxs-lookup"><span data-stu-id="7681b-130">Steps</span></span>
  
1. <span data-ttu-id="7681b-131">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="7681b-131">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="7681b-132">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)][BizTalk グループ]、をクリックして**プラットフォームの設定**、 をクリックし、**ホスト インスタンス**します。</span><span class="sxs-lookup"><span data-stu-id="7681b-132">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
3. <span data-ttu-id="7681b-133">詳細ペインで、変更、およびクリックするホスト インスタンスを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="7681b-133">In the details pane, right-click the host instance you want to modify, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="7681b-134">**ホスト インスタンスのプロパティ**ダイアログ ボックスで、をクリックして**構成**サービス アカウント情報を変更します。</span><span class="sxs-lookup"><span data-stu-id="7681b-134">In the **Host Instance Properties** dialog box, click **Configure** to modify the service account information.</span></span>  
  
5. <span data-ttu-id="7681b-135">**ログオン資格情報** ダイアログ ボックスに、アカウント名と、ホスト インスタンスが実行、および順にクリックして、アカウントのパスワードを入力**OK**します。</span><span class="sxs-lookup"><span data-stu-id="7681b-135">In the **Logon Credentials** dialog box, enter the account name and password of the account under which the host instance will run, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="7681b-136">**ホスト インスタンスのプロパティ** ダイアログ ボックスで、次の操作をクリックして**OK**:</span><span class="sxs-lookup"><span data-stu-id="7681b-136">In the **Host Instance Properties** dialog box, do the following, and then click **OK**:</span></span>  
  
   |<span data-ttu-id="7681b-137">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7681b-137">Use this</span></span>|<span data-ttu-id="7681b-138">目的</span><span class="sxs-lookup"><span data-stu-id="7681b-138">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="7681b-139">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="7681b-139">**Host name**</span></span>|<span data-ttu-id="7681b-140">選択したサーバーに関連付けられているホストの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="7681b-140">Displays the name of the host associated with the selected server.</span></span>|  
   |<span data-ttu-id="7681b-141">**[サーバー]**</span><span class="sxs-lookup"><span data-stu-id="7681b-141">**Server**</span></span>|<span data-ttu-id="7681b-142">選択したホストに関連付けられているサーバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="7681b-142">Displays the server associated with the selected host.</span></span>|  
   |<span data-ttu-id="7681b-143">**ログオン**</span><span class="sxs-lookup"><span data-stu-id="7681b-143">**Logon**</span></span>|<span data-ttu-id="7681b-144">ホスト インスタンスを実行する、新しいサービス アカウントのアカウント名を表示します。</span><span class="sxs-lookup"><span data-stu-id="7681b-144">Displays the account name of the new service account under which the host instance will run.</span></span>|  
   |<span data-ttu-id="7681b-145">**構成**</span><span class="sxs-lookup"><span data-stu-id="7681b-145">**Configure**</span></span>|<span data-ttu-id="7681b-146">表示するをクリックして、**ログオン資格情報**] ダイアログ ボックスの [アカウント名とホスト インスタンスを実行するアカウントのパスワードを入力できます。</span><span class="sxs-lookup"><span data-stu-id="7681b-146">Click to display the **Logon Credentials** dialog box, where you can enter the account name and password of the account under which the host instance will run.</span></span>|  
   |<span data-ttu-id="7681b-147">**ホスト インスタンスの開始を無効にします。**</span><span class="sxs-lookup"><span data-stu-id="7681b-147">**Disable host instance from starting**</span></span>|<span data-ttu-id="7681b-148">選択したホストの状態を有効から無効に変更する場合、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7681b-148">Select this check box to change the status of the selected host from enabled to disabled.</span></span> <span data-ttu-id="7681b-149">ホスト インスタンスを開始せずに設定を保持する場合は、インスタンスを無効にすると便利です。</span><span class="sxs-lookup"><span data-stu-id="7681b-149">Disabling a host instance is useful if you do not want the host instance to start, but you do want to preserve its settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7681b-150">参照</span><span class="sxs-lookup"><span data-stu-id="7681b-150">See Also</span></span>  
 <span data-ttu-id="7681b-151">[BizTalk ホストとホスト インスタンスの管理](../core/managing-biztalk-hosts-and-host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="7681b-151">[Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md) </span></span>  
 <span data-ttu-id="7681b-152">[ホスト インスタンスを追加します。](../core/how-to-add-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="7681b-152">[Add a Host Instance](../core/how-to-add-a-host-instance.md) </span></span>  
 <span data-ttu-id="7681b-153">[ホスト インスタンスを開始します。](../core/how-to-start-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="7681b-153">[Start a Host Instance](../core/how-to-start-a-host-instance.md) </span></span>  
 <span data-ttu-id="7681b-154">[ホスト インスタンスを停止します。](../core/how-to-stop-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="7681b-154">[Stop a Host Instance](../core/how-to-stop-a-host-instance.md) </span></span>  
 [<span data-ttu-id="7681b-155">ホスト インスタンスの削除</span><span class="sxs-lookup"><span data-stu-id="7681b-155">Delete a Host Instance</span></span>](../core/how-to-delete-a-host-instance.md)