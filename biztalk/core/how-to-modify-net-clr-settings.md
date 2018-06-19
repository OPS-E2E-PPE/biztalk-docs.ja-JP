---
title: .NET CLR 設定を変更する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Bts10.settings.HostInstanceCLR
ms.assetid: 085743d8-27a6-4d8b-98c7-bb5b5c75848c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d134faf06aebbb24cafd716722d63172a5ceb68b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254298"
---
# <a name="how-to-modify-net-clr-settings"></a><span data-ttu-id="b3826-102">.NET CLR の設定を変更する方法</span><span class="sxs-lookup"><span data-stu-id="b3826-102">How to Modify .NET CLR Settings</span></span>
<span data-ttu-id="b3826-103">BizTalk ホストのインスタンスに関連付けられた .NET スレッド プールで使用できる Windows スレッド数を更新するには、BizTalk 設定ダッシュボードを使用して、CLR (共通ランタイム言語) Hosting の値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b3826-103">To update the number of Windows threads available in the .NET thread pool associated with an instance of a BizTalk host, you can modify the appropriate Common Runtime Language (CLR) Hosting values using the BizTalk Settings Dashboard.</span></span> <span data-ttu-id="b3826-104">このトピックでは、これらの設定を変更する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="b3826-104">This topic provides the step-by-step procedure to modify these settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b3826-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="b3826-105">Prerequisites</span></span>  
 <span data-ttu-id="b3826-106">ここで示す操作を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3826-106">To perform this operation, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-modify-the-net-clr-settings-of-a-host-instance"></a><span data-ttu-id="b3826-107">ホスト インスタンスの .NET CLR 設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="b3826-107">To modify the .NET CLR settings of a host instance</span></span>  
  
1.  <span data-ttu-id="b3826-108">**BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、クリックして**設定**です。</span><span class="sxs-lookup"><span data-stu-id="b3826-108">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
2.  <span data-ttu-id="b3826-109">**BizTalk 設定ダッシュ ボード**ダイアログ ボックスの**ホスト インスタンス**タブをクリックし、 **.NET CLR**タブです。</span><span class="sxs-lookup"><span data-stu-id="b3826-109">In the **BizTalk Settings Dashboard** dialog box, on the **Host Instance** tab, click the **.NET CLR** tab.</span></span>  
  
3.  <span data-ttu-id="b3826-110">次の操作を**適用**を変更を適用し、別のタブに進みます。をクリックしてまたは**OK**を変更を適用し、設定ダッシュ ボードを終了します。</span><span class="sxs-lookup"><span data-stu-id="b3826-110">Do the following and click **Apply** to apply the modifications and proceed to another tab. Or click **OK** to apply the modifications and exit the Settings Dashboard.</span></span>  
  
    |<span data-ttu-id="b3826-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b3826-111">Use this</span></span>|<span data-ttu-id="b3826-112">目的</span><span class="sxs-lookup"><span data-stu-id="b3826-112">To do this</span></span>|<span data-ttu-id="b3826-113">境界値</span><span class="sxs-lookup"><span data-stu-id="b3826-113">Boundary values</span></span>|<span data-ttu-id="b3826-114">既定値</span><span class="sxs-lookup"><span data-stu-id="b3826-114">Default value</span></span>|<span data-ttu-id="b3826-115">アップグレード ロジック</span><span class="sxs-lookup"><span data-stu-id="b3826-115">Upgrade logic</span></span>|  
    |--------------|----------------|---------------------|-------------------|-------------------|  
    |<span data-ttu-id="b3826-116">**ホスト インスタンス**</span><span class="sxs-lookup"><span data-stu-id="b3826-116">**Host Instance**</span></span>|<span data-ttu-id="b3826-117">ドロップダウン ボックスから、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンピューター上のホストで実行中のインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="b3826-117">From the drop-down box, select the running instance of a host on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime machine.</span></span>|-|-|-|  
  
     <span data-ttu-id="b3826-118">**スレッドの設定**</span><span class="sxs-lookup"><span data-stu-id="b3826-118">**Threading Settings**</span></span>  
  
    |<span data-ttu-id="b3826-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b3826-119">Use this</span></span>|<span data-ttu-id="b3826-120">目的</span><span class="sxs-lookup"><span data-stu-id="b3826-120">To do this</span></span>|<span data-ttu-id="b3826-121">境界値</span><span class="sxs-lookup"><span data-stu-id="b3826-121">Boundary values</span></span>|<span data-ttu-id="b3826-122">既定値</span><span class="sxs-lookup"><span data-stu-id="b3826-122">Default value</span></span>|<span data-ttu-id="b3826-123">アップグレード ロジック</span><span class="sxs-lookup"><span data-stu-id="b3826-123">Upgrade logic</span></span>|  
    |--------------|----------------|---------------------|-------------------|-------------------|  
    |<span data-ttu-id="b3826-124">**最大値。ワーカー スレッド**</span><span class="sxs-lookup"><span data-stu-id="b3826-124">**Max. worker threads**</span></span>|<span data-ttu-id="b3826-125">.NET CLR ワーカー スレッドの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3826-125">Specify the maximum number of .NET CLR worker threads.</span></span>|<span data-ttu-id="b3826-126">[最小ワーカー スレッド数、500]</span><span class="sxs-lookup"><span data-stu-id="b3826-126">[Min worker threads, 500]</span></span>|<span data-ttu-id="b3826-127">25</span><span class="sxs-lookup"><span data-stu-id="b3826-127">25</span></span>|<span data-ttu-id="b3826-128">ホスト インスタンスのレジストリ設定をホスト インスタンスの設定に移行し、Version、Flavor、Flags、および MinCompletionPortThreads を無視します。</span><span class="sxs-lookup"><span data-stu-id="b3826-128">Migrate the host instance registry settings to host instance settings, ignore Version, Flavor, Flags, and MinCompletionPortThreads.</span></span>|  
    |<span data-ttu-id="b3826-129">**最小ワーカー スレッド数**</span><span class="sxs-lookup"><span data-stu-id="b3826-129">**Min. worker threads**</span></span>|<span data-ttu-id="b3826-130">.NET CLR ワーカー スレッドの最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3826-130">Specify the minimum number of .NET CLR worker threads.</span></span>|<span data-ttu-id="b3826-131">[0, 500]</span><span class="sxs-lookup"><span data-stu-id="b3826-131">[0, 500]</span></span>|<span data-ttu-id="b3826-132">5</span><span class="sxs-lookup"><span data-stu-id="b3826-132">5</span></span>|<span data-ttu-id="b3826-133">ホスト インスタンスのレジストリ設定をホスト インスタンスの設定に移行し、Version、Flavor、Flags、および MinCompletionPortThreads を無視します。</span><span class="sxs-lookup"><span data-stu-id="b3826-133">Migrate the host instance registry settings to host instance settings, ignore Version, Flavor, Flags, and MinCompletionPortThreads.</span></span>|  
    |<span data-ttu-id="b3826-134">**最大値。IO スレッド数**</span><span class="sxs-lookup"><span data-stu-id="b3826-134">**Max. IO threads**</span></span>|<span data-ttu-id="b3826-135">IO スレッドの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3826-135">Specify the maximum number of IO threads.</span></span>|<span data-ttu-id="b3826-136">[最小 IO スレッド数、1000]</span><span class="sxs-lookup"><span data-stu-id="b3826-136">[Min IO threads, 1000]</span></span>|<span data-ttu-id="b3826-137">250</span><span class="sxs-lookup"><span data-stu-id="b3826-137">250</span></span>|<span data-ttu-id="b3826-138">ホスト インスタンスのレジストリ設定をホスト インスタンスの設定に移行し、Version、Flavor、Flags、および MinCompletionPortThreads を無視します。</span><span class="sxs-lookup"><span data-stu-id="b3826-138">Migrate the host instance registry settings to host instance settings, ignore Version, Flavor, Flags, and MinCompletionPortThreads.</span></span>|  
    |<span data-ttu-id="b3826-139">**最小値。IO スレッド数**</span><span class="sxs-lookup"><span data-stu-id="b3826-139">**Min. IO threads**</span></span>|<span data-ttu-id="b3826-140">IO スレッドの最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3826-140">Specify the minimum number of IO threads.</span></span>|<span data-ttu-id="b3826-141">[0, 1000]</span><span class="sxs-lookup"><span data-stu-id="b3826-141">[0, 1000]</span></span>|<span data-ttu-id="b3826-142">25</span><span class="sxs-lookup"><span data-stu-id="b3826-142">25</span></span>|<span data-ttu-id="b3826-143">ホスト インスタンスのレジストリ設定をホスト インスタンスの設定に移行し、Version、Flavor、Flags、および MinCompletionPortThreads を無視します。</span><span class="sxs-lookup"><span data-stu-id="b3826-143">Migrate the host instance registry settings to host instance settings, ignore Version, Flavor, Flags, and MinCompletionPortThreads.</span></span>|  
  
     <span data-ttu-id="b3826-144">.NET CLR 設定は、コア CPU ごとに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b3826-144">.NET CLR Settings are per-core CPU.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b3826-145">既定の設定を復元する をクリックして**既定値に戻す**です。</span><span class="sxs-lookup"><span data-stu-id="b3826-145">To restore the default settings, click **Restore Defaults**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b3826-146">**ワーカー スレッド**キューに置かれた作業項目の処理に使用して**I/O スレッド**専用のコールバック スレッドが完了した非同期 I/O 要求を処理する I/O 完了ポートに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="b3826-146">**Worker threads** are used to handle queued work items and **I/O threads** are dedicated callback threads associated with an I/O completion port to handle a completed asynchronous I/O request.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b3826-147">BizTalk が、hkey_local_machine \system\currentcontrolset\services\btssvc$ 内の値、以前のバージョンからアップグレードした場合*hostname*\CLR Hosting レジストリ キーを設定ダッシュ ボードに設定されます。</span><span class="sxs-lookup"><span data-stu-id="b3826-147">If BizTalk is upgraded from a previous version, the values in the HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc$*hostname*\CLR Hosting registry key will be set in Settings Dashboard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3826-148">参照</span><span class="sxs-lookup"><span data-stu-id="b3826-148">See Also</span></span>  
 [<span data-ttu-id="b3826-149">ホスト インスタンスの設定を変更する方法</span><span class="sxs-lookup"><span data-stu-id="b3826-149">How to Modify Host Instance Settings</span></span>](../core/how-to-modify-host-instance-settings.md)