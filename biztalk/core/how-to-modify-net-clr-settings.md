---
title: .NET CLR 設定を変更する方法 |Microsoft Docs
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
ms.openlocfilehash: 512907afe143b92af3eafea2156efd42d97f4f75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384602"
---
# <a name="how-to-modify-net-clr-settings"></a><span data-ttu-id="d61be-102">.NET CLR 設定を変更する方法</span><span class="sxs-lookup"><span data-stu-id="d61be-102">How to Modify .NET CLR Settings</span></span>
<span data-ttu-id="d61be-103">BizTalk ホストのインスタンスに関連付けられた .NET スレッド プールで使用できる Windows スレッド数を更新するには、BizTalk 設定ダッシュ ボードを使用して、適切な共通ランタイム (CLR 言語) Hosting 値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="d61be-103">To update the number of Windows threads available in the .NET thread pool associated with an instance of a BizTalk host, you can modify the appropriate Common Runtime Language (CLR) Hosting values using the BizTalk Settings Dashboard.</span></span> <span data-ttu-id="d61be-104">このトピックでは、これらの設定を変更するための手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="d61be-104">This topic provides the step-by-step procedure to modify these settings.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="d61be-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="d61be-105">Prerequisites</span></span>  
 <span data-ttu-id="d61be-106">この操作を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d61be-106">To perform this operation, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  

### <a name="to-modify-the-net-clr-settings-of-a-host-instance"></a><span data-ttu-id="d61be-107">ホスト インスタンスの .NET CLR 設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="d61be-107">To modify the .NET CLR settings of a host instance</span></span>  

1. <span data-ttu-id="d61be-108">**BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、 をクリックし、**設定**します。</span><span class="sxs-lookup"><span data-stu-id="d61be-108">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  

2. <span data-ttu-id="d61be-109">**BizTalk 設定ダッシュ ボード**] ダイアログ ボックスの [、**ホスト インスタンス**タブをクリックし、 **.NET CLR**タブ。</span><span class="sxs-lookup"><span data-stu-id="d61be-109">In the **BizTalk Settings Dashboard** dialog box, on the **Host Instance** tab, click the **.NET CLR** tab.</span></span>  

3. <span data-ttu-id="d61be-110">以下を**適用**を変更を適用し、別のタブに進みます。をクリックしてまたは**OK**変更を適用し、設定ダッシュ ボードを終了します。</span><span class="sxs-lookup"><span data-stu-id="d61be-110">Do the following and click **Apply** to apply the modifications and proceed to another tab. Or click **OK** to apply the modifications and exit the Settings Dashboard.</span></span>  


   |     <span data-ttu-id="d61be-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d61be-111">Use this</span></span>      |                                                                                <span data-ttu-id="d61be-112">目的</span><span class="sxs-lookup"><span data-stu-id="d61be-112">To do this</span></span>                                                                                | <span data-ttu-id="d61be-113">境界値</span><span class="sxs-lookup"><span data-stu-id="d61be-113">Boundary values</span></span> | <span data-ttu-id="d61be-114">既定値</span><span class="sxs-lookup"><span data-stu-id="d61be-114">Default value</span></span> | <span data-ttu-id="d61be-115">アップグレード ロジック</span><span class="sxs-lookup"><span data-stu-id="d61be-115">Upgrade logic</span></span> |
   |-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|---------------|---------------|
   | <span data-ttu-id="d61be-116">**ホスト インスタンス**</span><span class="sxs-lookup"><span data-stu-id="d61be-116">**Host Instance**</span></span> | <span data-ttu-id="d61be-117">ホストの実行中のインスタンスを選択、ドロップダウン ボックスから、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューター。</span><span class="sxs-lookup"><span data-stu-id="d61be-117">From the drop-down box, select the running instance of a host on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime machine.</span></span> |        -        |       -       |       -       |

    <span data-ttu-id="d61be-118">**スレッドの設定**</span><span class="sxs-lookup"><span data-stu-id="d61be-118">**Threading Settings**</span></span>  

   |<span data-ttu-id="d61be-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d61be-119">Use this</span></span>|<span data-ttu-id="d61be-120">目的</span><span class="sxs-lookup"><span data-stu-id="d61be-120">To do this</span></span>|<span data-ttu-id="d61be-121">境界値</span><span class="sxs-lookup"><span data-stu-id="d61be-121">Boundary values</span></span>|<span data-ttu-id="d61be-122">既定値</span><span class="sxs-lookup"><span data-stu-id="d61be-122">Default value</span></span>|<span data-ttu-id="d61be-123">アップグレード ロジック</span><span class="sxs-lookup"><span data-stu-id="d61be-123">Upgrade logic</span></span>|  
   |--------------|----------------|---------------------|-------------------|-------------------|  
   |<span data-ttu-id="d61be-124">**最大値。ワーカー スレッド**</span><span class="sxs-lookup"><span data-stu-id="d61be-124">**Max. worker threads**</span></span>|<span data-ttu-id="d61be-125">.NET CLR ワーカー スレッドの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d61be-125">Specify the maximum number of .NET CLR worker threads.</span></span>|<span data-ttu-id="d61be-126">[最小ワーカー スレッド、500]</span><span class="sxs-lookup"><span data-stu-id="d61be-126">[Min worker threads, 500]</span></span>|<span data-ttu-id="d61be-127">25</span><span class="sxs-lookup"><span data-stu-id="d61be-127">25</span></span>|<span data-ttu-id="d61be-128">ホスト インスタンスの設定、バージョン、フレーバー、フラグ、および MinCompletionPortThreads を無視するホスト インスタンスのレジストリ設定を移行します。</span><span class="sxs-lookup"><span data-stu-id="d61be-128">Migrate the host instance registry settings to host instance settings, ignore Version, Flavor, Flags, and MinCompletionPortThreads.</span></span>|  
   |<span data-ttu-id="d61be-129">**最小ワーカー スレッド数**</span><span class="sxs-lookup"><span data-stu-id="d61be-129">**Min. worker threads**</span></span>|<span data-ttu-id="d61be-130">.NET CLR ワーカー スレッドの最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d61be-130">Specify the minimum number of .NET CLR worker threads.</span></span>|<span data-ttu-id="d61be-131">[0, 500]</span><span class="sxs-lookup"><span data-stu-id="d61be-131">[0, 500]</span></span>|<span data-ttu-id="d61be-132">5</span><span class="sxs-lookup"><span data-stu-id="d61be-132">5</span></span>|<span data-ttu-id="d61be-133">ホスト インスタンスの設定、バージョン、フレーバー、フラグ、および MinCompletionPortThreads を無視するホスト インスタンスのレジストリ設定を移行します。</span><span class="sxs-lookup"><span data-stu-id="d61be-133">Migrate the host instance registry settings to host instance settings, ignore Version, Flavor, Flags, and MinCompletionPortThreads.</span></span>|  
   |<span data-ttu-id="d61be-134">**最大値。IO スレッドの数**</span><span class="sxs-lookup"><span data-stu-id="d61be-134">**Max. IO threads**</span></span>|<span data-ttu-id="d61be-135">IO スレッドの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d61be-135">Specify the maximum number of IO threads.</span></span>|<span data-ttu-id="d61be-136">[最小 IO スレッド数、1000]</span><span class="sxs-lookup"><span data-stu-id="d61be-136">[Min IO threads, 1000]</span></span>|<span data-ttu-id="d61be-137">250</span><span class="sxs-lookup"><span data-stu-id="d61be-137">250</span></span>|<span data-ttu-id="d61be-138">ホスト インスタンスの設定、バージョン、フレーバー、フラグ、および MinCompletionPortThreads を無視するホスト インスタンスのレジストリ設定を移行します。</span><span class="sxs-lookup"><span data-stu-id="d61be-138">Migrate the host instance registry settings to host instance settings, ignore Version, Flavor, Flags, and MinCompletionPortThreads.</span></span>|  
   |<span data-ttu-id="d61be-139">**最小値。IO スレッドの数**</span><span class="sxs-lookup"><span data-stu-id="d61be-139">**Min. IO threads**</span></span>|<span data-ttu-id="d61be-140">IO スレッドの最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d61be-140">Specify the minimum number of IO threads.</span></span>|<span data-ttu-id="d61be-141">[0, 1000]</span><span class="sxs-lookup"><span data-stu-id="d61be-141">[0, 1000]</span></span>|<span data-ttu-id="d61be-142">25</span><span class="sxs-lookup"><span data-stu-id="d61be-142">25</span></span>|<span data-ttu-id="d61be-143">ホスト インスタンスの設定、バージョン、フレーバー、フラグ、および MinCompletionPortThreads を無視するホスト インスタンスのレジストリ設定を移行します。</span><span class="sxs-lookup"><span data-stu-id="d61be-143">Migrate the host instance registry settings to host instance settings, ignore Version, Flavor, Flags, and MinCompletionPortThreads.</span></span>|  

    <span data-ttu-id="d61be-144">.NET CLR 設定は、コア CPU ごとに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d61be-144">.NET CLR Settings are per-core CPU.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="d61be-145">既定の設定を復元するには、次のようにクリックします。**既定値に戻す**します。</span><span class="sxs-lookup"><span data-stu-id="d61be-145">To restore the default settings, click **Restore Defaults**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="d61be-146">**ワーカー スレッド**キューに置かれた作業項目の処理に使用し、 **I/O スレッド**専用のコールバック スレッドが完了した非同期 I/O 要求を処理するために、I/O 完了ポートに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="d61be-146">**Worker threads** are used to handle queued work items and **I/O threads** are dedicated callback threads associated with an I/O completion port to handle a completed asynchronous I/O request.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="d61be-147">BizTalk は、hkey_local_machine \system\currentcontrolset\services\btssvc$ 内の値を前のバージョンからアップグレードした場合は*hostname*\CLR Hosting レジストリ キーを設定ダッシュ ボードに設定されます。</span><span class="sxs-lookup"><span data-stu-id="d61be-147">If BizTalk is upgraded from a previous version, the values in the HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc$*hostname*\CLR Hosting registry key will be set in Settings Dashboard.</span></span>  

## <a name="see-also"></a><span data-ttu-id="d61be-148">参照</span><span class="sxs-lookup"><span data-stu-id="d61be-148">See Also</span></span>  
 [<span data-ttu-id="d61be-149">ホスト インスタンスの設定を変更する方法</span><span class="sxs-lookup"><span data-stu-id="d61be-149">How to Modify Host Instance Settings</span></span>](../core/how-to-modify-host-instance-settings.md)