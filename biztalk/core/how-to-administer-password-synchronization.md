---
title: パスワード同期を管理する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Password Synchronization [SSO], applications
- Password Synchronization [SSO], notifications
- applications, Password Synchronization [SSO]
- SSOPS command line utility [SSO]
- administering, Password Synchronization [SSO]
- Password Synchronization [SSO], adapters
- Password Synchronization [SSO], administering
- notifications [SSO]
- Password Synchronization [SSO], SSOPS command line utility
ms.assetid: e5568cc2-7530-452c-9902-d7ffcad66088
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7c9b7485584c102b925b51d26ab11d37f4b8f6f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387215"
---
# <a name="how-to-administer-password-synchronization"></a><span data-ttu-id="32225-102">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="32225-102">How to Administer Password Synchronization</span></span>
<span data-ttu-id="32225-103">MMC スナップインまたはコマンドラインでパスワード同期を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="32225-103">You can administer Password Synchronization through either the MMC Snap-In or the command line.</span></span>  
  
 <span data-ttu-id="32225-104">MMC スナップインでは、アダプターとそのプロパティの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="32225-104">The MMC Snap-In displays a list of adapters and their properties.</span></span> <span data-ttu-id="32225-105">アダプターを右クリックし、メニューを使用して、次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="32225-105">You can right-click an adapter and use the menu to perform the following commands:</span></span>  
  
- <span data-ttu-id="32225-106">アダプターを作成します。</span><span class="sxs-lookup"><span data-stu-id="32225-106">Create adapters</span></span>  
  
- <span data-ttu-id="32225-107">プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="32225-107">Set properties</span></span>  
  
- <span data-ttu-id="32225-108">更新</span><span class="sxs-lookup"><span data-stu-id="32225-108">Update</span></span>  
  
- <span data-ttu-id="32225-109">DELETE</span><span class="sxs-lookup"><span data-stu-id="32225-109">Delete</span></span>  
  
- <span data-ttu-id="32225-110">[有効化]</span><span class="sxs-lookup"><span data-stu-id="32225-110">Enable</span></span>  
  
- <span data-ttu-id="32225-111">Disable</span><span class="sxs-lookup"><span data-stu-id="32225-111">Disable</span></span>  
  
- <span data-ttu-id="32225-112">アプリケーション アダプターを追加します。</span><span class="sxs-lookup"><span data-stu-id="32225-112">Add applications to an adapter</span></span>  
  
- <span data-ttu-id="32225-113">アダプターからアプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="32225-113">Delete applications from an adapter</span></span>  
  
- <span data-ttu-id="32225-114">通知をリセットします。</span><span class="sxs-lookup"><span data-stu-id="32225-114">Reset notification</span></span>  
  
- <span data-ttu-id="32225-115">アダプタ グループにアダプターを追加します。</span><span class="sxs-lookup"><span data-stu-id="32225-115">Add an adapter to an adapter group</span></span>  
  
- <span data-ttu-id="32225-116">アダプタ グループからアダプターを削除します。</span><span class="sxs-lookup"><span data-stu-id="32225-116">Delete an adapter from an adapter group</span></span>  
  
  <span data-ttu-id="32225-117">パスワード同期の管理に SSOPS コマンド ライン ユーティリティを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="32225-117">You can also use the SSOPS command line utility to administer your password synchronization.</span></span> <span data-ttu-id="32225-118">このセクションのコマンドのほとんどは、管理者のみ用に用意されています。</span><span class="sxs-lookup"><span data-stu-id="32225-118">Most of commands in this section are intended for use by an administrator only.</span></span>  
  
  <span data-ttu-id="32225-119">多くのコマンドでは、コマンドの出力は、2 つの列では、画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="32225-119">For many commands, the command output is displayed on the screen in two columns.</span></span> <span data-ttu-id="32225-120">画面設定によっては、データの切り捨てになる可能性があります、最良の結果をする必要がありますサイズを変更する画面バッファー サイズ/Windows 120 文字にします。</span><span class="sxs-lookup"><span data-stu-id="32225-120">As certain screen settings may cause truncation of data, for best results you should change the screen buffer size/Windows size to 120 characters.</span></span>  
  
  <span data-ttu-id="32225-121">SSOPS コマンドは、次の表に表示されます。</span><span class="sxs-lookup"><span data-stu-id="32225-121">The SSOPS commands are listed in the following table.</span></span> <span data-ttu-id="32225-122">プロシージャとさらに詳しい説明は、このトピックの残りの部分であります。</span><span class="sxs-lookup"><span data-stu-id="32225-122">Procedures and further explanation are located throughout the rest of this topic.</span></span>  
  
|<span data-ttu-id="32225-123">コマンド</span><span class="sxs-lookup"><span data-stu-id="32225-123">Command</span></span>|<span data-ttu-id="32225-124">関数</span><span class="sxs-lookup"><span data-stu-id="32225-124">Function</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="32225-125">-リスト</span><span class="sxs-lookup"><span data-stu-id="32225-125">-list</span></span>|<span data-ttu-id="32225-126">既存のアダプタの一覧</span><span class="sxs-lookup"><span data-stu-id="32225-126">Lists existing adapters</span></span>|  
|<span data-ttu-id="32225-127">表示</span><span class="sxs-lookup"><span data-stu-id="32225-127">-display</span></span>|<span data-ttu-id="32225-128">アダプターの情報を表示します</span><span class="sxs-lookup"><span data-stu-id="32225-128">Displays adapter information</span></span>|  
|<span data-ttu-id="32225-129">-作成</span><span class="sxs-lookup"><span data-stu-id="32225-129">-create</span></span>|<span data-ttu-id="32225-130">新しいアダプターを作成します。</span><span class="sxs-lookup"><span data-stu-id="32225-130">Creates new adapter(s)</span></span>|  
|<span data-ttu-id="32225-131">-setprops</span><span class="sxs-lookup"><span data-stu-id="32225-131">-setprops</span></span>|<span data-ttu-id="32225-132">アダプターのプロパティを設定します</span><span class="sxs-lookup"><span data-stu-id="32225-132">Sets properties for adapter</span></span>|  
|<span data-ttu-id="32225-133">-更新</span><span class="sxs-lookup"><span data-stu-id="32225-133">-update</span></span>|<span data-ttu-id="32225-134">アダプターの既存の更新</span><span class="sxs-lookup"><span data-stu-id="32225-134">Updates existing adapter(s)</span></span>|  
|<span data-ttu-id="32225-135">-削除</span><span class="sxs-lookup"><span data-stu-id="32225-135">-delete</span></span>|<span data-ttu-id="32225-136">既存のアダプターを削除します。</span><span class="sxs-lookup"><span data-stu-id="32225-136">Deletes an existing adapter</span></span>|  
|<span data-ttu-id="32225-137">-有効にします。</span><span class="sxs-lookup"><span data-stu-id="32225-137">-enable</span></span>|<span data-ttu-id="32225-138">アダプターを使用にします。</span><span class="sxs-lookup"><span data-stu-id="32225-138">Enables adapter</span></span>|  
|<span data-ttu-id="32225-139">-を無効にします。</span><span class="sxs-lookup"><span data-stu-id="32225-139">-disable</span></span>|<span data-ttu-id="32225-140">アダプターを無効にします。</span><span class="sxs-lookup"><span data-stu-id="32225-140">Disables adapter</span></span>|  
|<span data-ttu-id="32225-141">-addapp</span><span class="sxs-lookup"><span data-stu-id="32225-141">-addapp</span></span>|<span data-ttu-id="32225-142">アダプタのアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="32225-142">Adds application for adapter</span></span>|  
|<span data-ttu-id="32225-143">-deleteapp</span><span class="sxs-lookup"><span data-stu-id="32225-143">-deleteapp</span></span>|<span data-ttu-id="32225-144">アダプタのアプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="32225-144">Deletes application for adapter</span></span>|  
|<span data-ttu-id="32225-145">リセット</span><span class="sxs-lookup"><span data-stu-id="32225-145">-reset</span></span>|<span data-ttu-id="32225-146">リセットの通知キューまたは抑制キュー</span><span class="sxs-lookup"><span data-stu-id="32225-146">Resets notification or damping queues</span></span>|  
|<span data-ttu-id="32225-147">-addtogroup」</span><span class="sxs-lookup"><span data-stu-id="32225-147">-addtogroup</span></span>|<span data-ttu-id="32225-148">アダプターをアダプター グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="32225-148">Adds adapter to adapter group</span></span>|  
|<span data-ttu-id="32225-149">-deletefromgroup</span><span class="sxs-lookup"><span data-stu-id="32225-149">-deletefromgroup</span></span>|<span data-ttu-id="32225-150">アダプタ グループからアダプターを削除します。</span><span class="sxs-lookup"><span data-stu-id="32225-150">Deletes adapter from adapter group</span></span>|  
  
### <a name="to-list-existing-adapters"></a><span data-ttu-id="32225-151">既存のアダプタを一覧表示するには</span><span class="sxs-lookup"><span data-stu-id="32225-151">To list existing adapters</span></span>  
  
1.  <span data-ttu-id="32225-152">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32225-152">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="32225-153">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="32225-153">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="32225-154">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="32225-154">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="32225-155">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="32225-155">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="32225-156">型**ssops-一覧**Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="32225-156">Type **ssops -list** and press Enter.</span></span>  
  
     <span data-ttu-id="32225-157">アダプターと説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="32225-157">Adapters and descriptions will be listed.</span></span> <span data-ttu-id="32225-158">(E) アダプターが有効になっている、(D) を表しますが無効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="32225-158">(E) denotes that the adapter is enabled, (D) denotes that it is disabled.</span></span>  
  
### <a name="to-display-adapter-information"></a><span data-ttu-id="32225-159">アダプターの情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="32225-159">To display adapter information</span></span>  
  
1.  <span data-ttu-id="32225-160">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32225-160">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="32225-161">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="32225-161">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="32225-162">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="32225-162">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="32225-163">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="32225-163">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="32225-164">型**ssops-表示\<アダプター名\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="32225-164">Type **ssops -display \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="32225-165">指定したアダプタの情報は、画面出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="32225-165">The screen output will display information for the specified adapter.</span></span>  
  
     <span data-ttu-id="32225-166">名前、種類、説明、コンピューター、およびアカウント、だけでなく、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="32225-166">In addition to name, type, description, computer, and accounts, the following information is displayed.</span></span>  
  
    |<span data-ttu-id="32225-167">アダプタ フラグ</span><span class="sxs-lookup"><span data-stu-id="32225-167">Adapter Flag</span></span>|<span data-ttu-id="32225-168">詳細</span><span class="sxs-lookup"><span data-stu-id="32225-168">Details</span></span>|  
    |------------------|-------------|  
    |<span data-ttu-id="32225-169">アダプターが有効</span><span class="sxs-lookup"><span data-stu-id="32225-169">Adapter enabled</span></span>|<span data-ttu-id="32225-170">アダプターが有効になっているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="32225-170">Determines whether or not the adapter is enabled.</span></span><br /><br /> <span data-ttu-id="32225-171">フラグ:SSO_FLAG_ENABLED</span><span class="sxs-lookup"><span data-stu-id="32225-171">Flag: SSO_FLAG_ENABLED</span></span><br /><br /> <span data-ttu-id="32225-172">属性名: enableApp</span><span class="sxs-lookup"><span data-stu-id="32225-172">Attribute Name: enableApp</span></span><br /><br /> <span data-ttu-id="32225-173">既定値:いいえ</span><span class="sxs-lookup"><span data-stu-id="32225-173">Default: No</span></span>|  
    |<span data-ttu-id="32225-174">ローカル アカウントを許可します。</span><span class="sxs-lookup"><span data-stu-id="32225-174">Allow local accounts</span></span>|<span data-ttu-id="32225-175">アプリの管理者またはアプリのユーザー アカウントは、ローカル アカウントかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="32225-175">Determines whether or not the App Admin or App Users accounts can be local accounts.</span></span><br /><br /> <span data-ttu-id="32225-176">フラグ:SSO_FLAG_APP_ALLOW_LOCAL</span><span class="sxs-lookup"><span data-stu-id="32225-176">Flag: SSO_FLAG_APP_ALLOW_LOCAL</span></span><br /><br /> <span data-ttu-id="32225-177">属性名: allowLocalAccounts</span><span class="sxs-lookup"><span data-stu-id="32225-177">Attribute Name: allowLocalAccounts</span></span><br /><br /> <span data-ttu-id="32225-178">既定値:いいえ</span><span class="sxs-lookup"><span data-stu-id="32225-178">Default: No</span></span>|  
    |<span data-ttu-id="32225-179">アダプターからパスワード変更を受け取る</span><span class="sxs-lookup"><span data-stu-id="32225-179">Receive password changes from adapter</span></span>|<span data-ttu-id="32225-180">外部パスワード変更を受信アダプターが許可されているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="32225-180">Determines whether or not the adapter is allowed to receive external password changes.</span></span><br /><br /> <span data-ttu-id="32225-181">フラグ:SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB</span><span class="sxs-lookup"><span data-stu-id="32225-181">Flag: SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB</span></span><br /><br /> <span data-ttu-id="32225-182">属性名: syncFromAdapter</span><span class="sxs-lookup"><span data-stu-id="32225-182">Attribute Name: syncFromAdapter</span></span><br /><br /> <span data-ttu-id="32225-183">既定値:いいえ</span><span class="sxs-lookup"><span data-stu-id="32225-183">Default: No</span></span>|  
    |<span data-ttu-id="32225-184">古いパスワードを確認します。</span><span class="sxs-lookup"><span data-stu-id="32225-184">Verify old password</span></span>|<span data-ttu-id="32225-185">外部パスワード変更が受信したときに、アダプターが、古いパスワードを確認するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="32225-185">Determines whether the adapter will verify the old password when an external password change is received.</span></span> <span data-ttu-id="32225-186">このフラグが設定されている場合、外部パスワード変更を外部アダプターが必要以前の外部パスワードだけでなく、新しい外部パスワードです。</span><span class="sxs-lookup"><span data-stu-id="32225-186">If this flag is set then with an external password change the external adapter must supply the old external password as well as the new external password.</span></span> <span data-ttu-id="32225-187">以前の外部パスワードは、外部アカウントの SSO データベース内の既存の外部パスワードと比較されます。</span><span class="sxs-lookup"><span data-stu-id="32225-187">The old external password is then compared with the existing external password in the SSO database for that external account.</span></span> <span data-ttu-id="32225-188">一致すると、パスワードの変更が受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="32225-188">If they match, the password change is accepted.</span></span> <span data-ttu-id="32225-189">一致しない場合は、パスワードの変更が拒否されます。</span><span class="sxs-lookup"><span data-stu-id="32225-189">If they do not match, the password change is rejected.</span></span><br /><br /> <span data-ttu-id="32225-190">フラグ:SSO_FLAG_SYNC_VERIFY_EXTERNAL_CREDS</span><span class="sxs-lookup"><span data-stu-id="32225-190">Flag: SSO_FLAG_SYNC_VERIFY_EXTERNAL_CREDS</span></span><br /><br /> <span data-ttu-id="32225-191">属性名: verifyOldPassword</span><span class="sxs-lookup"><span data-stu-id="32225-191">Attribute Name: verifyOldPassword</span></span><br /><br /> <span data-ttu-id="32225-192">既定値:はい</span><span class="sxs-lookup"><span data-stu-id="32225-192">Default: Yes</span></span>|  
    |<span data-ttu-id="32225-193">Windows パスワードの変更</span><span class="sxs-lookup"><span data-stu-id="32225-193">Change Windows password</span></span>|<span data-ttu-id="32225-194">Windows のパスワードは、外部パスワード変更の場合も変更されますが (完全同期) を受信したかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="32225-194">Determines whether or not the Windows password will also be changed when an external password change is received (full sync).</span></span> <span data-ttu-id="32225-195">ENTSSO は常に新しい値に、Windows パスワードを変更する SSO データベースに格納されている古い Windows パスワードを使用 (Windows が必要、ユーザーがパスワードを変更する古いマスター_キーと新しいパスワードの両方)、ため、Windows パスワードの変更が正常に完了する前にこの初期化する必要があります.</span><span class="sxs-lookup"><span data-stu-id="32225-195">ENTSSO always uses the old Windows password stored in the SSO database to change the Windows password to the new value (Windows requires both the old and new password to change a users password), so this must be initialized before the Windows password change can succeed.</span></span> <span data-ttu-id="32225-196">特定のマッピングに対してパスワード同期を構成する場合、管理ツール (ssomanage または ssoclient-setcredentials) を使用して外部資格情報を設定すると、SSO データベースに格納されている Windows パスワードも設定されます。フラグ:SSO_FLAG_FULL_SYNC_FROM_EXTERNAL_TO_WINDOWS</span><span class="sxs-lookup"><span data-stu-id="32225-196">If password sync is configured for a particular mapping, then when the external credentials are set via administrative tools (ssomanage or ssoclient -setcredentials) the Windows password stored in the SSO database will also be set.Flag: SSO_FLAG_FULL_SYNC_FROM_EXTERNAL_TO_WINDOWS</span></span><br /><br /> <span data-ttu-id="32225-197">属性名: changeWindowsPassword</span><span class="sxs-lookup"><span data-stu-id="32225-197">Attribute Name: changeWindowsPassword</span></span><br /><br /> <span data-ttu-id="32225-198">既定値:いいえ</span><span class="sxs-lookup"><span data-stu-id="32225-198">Default: No</span></span>|  
    |<span data-ttu-id="32225-199">Windows パスワードの変更をアダプターに送信します。</span><span class="sxs-lookup"><span data-stu-id="32225-199">Send Windows password changes to adapter</span></span>|<span data-ttu-id="32225-200">Windows パスワードの変更を外部アダプターに送信するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="32225-200">Determines whether or not Windows password changes will be sent to the external adapter.</span></span><br /><br /> <span data-ttu-id="32225-201">フラグ:SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL</span><span class="sxs-lookup"><span data-stu-id="32225-201">Flag: SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL</span></span><br /><br /> <span data-ttu-id="32225-202">属性名: syncToAdapter</span><span class="sxs-lookup"><span data-stu-id="32225-202">Attribute Name: syncToAdapter</span></span><br /><br /> <span data-ttu-id="32225-203">既定値:いいえ</span><span class="sxs-lookup"><span data-stu-id="32225-203">Default: No</span></span>|  
    |<span data-ttu-id="32225-204">古いパスワードをアダプタに送信します。</span><span class="sxs-lookup"><span data-stu-id="32225-204">Send old password to adapter</span></span>|<span data-ttu-id="32225-205">場合は、(、SSO データベースから古いパスワードの値は、新しいパスワード値と同様に、外部アダプターにも送信されます。</span><span class="sxs-lookup"><span data-stu-id="32225-205">If Yes, the old password value (from the SSO database) will also be sent to the external adapter as well as the new password value.</span></span> <span data-ttu-id="32225-206">一部の外部システムには、パスワードを変更する古いマスター_キーと新しいパスワード値が必要です。</span><span class="sxs-lookup"><span data-stu-id="32225-206">Some external systems might require both the old and new password values to change the password.</span></span><br /><br /> <span data-ttu-id="32225-207">フラグ:SSO_FLAG_SYNC_PROVIDE_OLD_EXTERNAL_CREDS</span><span class="sxs-lookup"><span data-stu-id="32225-207">Flag: SSO_FLAG_SYNC_PROVIDE_OLD_EXTERNAL_CREDS</span></span><br /><br /> <span data-ttu-id="32225-208">属性名: sendOldPassword</span><span class="sxs-lookup"><span data-stu-id="32225-208">Attribute Name: sendOldPassword</span></span><br /><br /> <span data-ttu-id="32225-209">既定値:いいえ</span><span class="sxs-lookup"><span data-stu-id="32225-209">Default: No</span></span>|  
    |<span data-ttu-id="32225-210">マッピングの競合を許可します。</span><span class="sxs-lookup"><span data-stu-id="32225-210">Allow mapping conflicts</span></span>|<span data-ttu-id="32225-211">アダプターでマッピングの競合を許可するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="32225-211">Determines whether or not the adapter will allow mapping conflicts.</span></span><br /><br /> <span data-ttu-id="32225-212">マッピングの競合は、マッピングが一意でないときに発生します。</span><span class="sxs-lookup"><span data-stu-id="32225-212">A mapping conflict occurs when mappings are not unique.</span></span> <span data-ttu-id="32225-213">単一の SSO 単独アプリケーションでのマッピングは一対一、常に: いずれかの Windows アカウントが正確に 1 つの外部アカウントに、その逆にマップされます。</span><span class="sxs-lookup"><span data-stu-id="32225-213">In a single SSO Individual application, mappings are always one-to-one: one Windows account is mapped to exactly one external account and vice versa.</span></span><br /><br /> <span data-ttu-id="32225-214">ただしに、アダプターに 1 つ以上のアプリケーションを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="32225-214">However, it is possible to assign more than one application to an adapter.</span></span> <span data-ttu-id="32225-215">そのため、他のマッピングと競合する 1 つのアプリケーションでのマッピングを含めることは可能です。</span><span class="sxs-lookup"><span data-stu-id="32225-215">Thus, it is possible to have a mapping in one application that conflicts with a mapping in the other.</span></span><br /><br /> <span data-ttu-id="32225-216">このフラグの目的では、これを防ぐためです。</span><span class="sxs-lookup"><span data-stu-id="32225-216">This purpose of this flag is to prevent this from occurring.</span></span> <span data-ttu-id="32225-217">この動作をよく理解されている、特定の要件がない限り、マッピングの競合を許可しない方が安全です。</span><span class="sxs-lookup"><span data-stu-id="32225-217">It is more secure to not allow mapping conflicts unless there is a specific, well understood requirement for this behavior.</span></span><br /><br /> <span data-ttu-id="32225-218">フラグ:SSO_FLAG_SYNC_ALLOW_MAPPING_CONFLICTS</span><span class="sxs-lookup"><span data-stu-id="32225-218">Flag: SSO_FLAG_SYNC_ALLOW_MAPPING_CONFLICTS</span></span><br /><br /> <span data-ttu-id="32225-219">属性名: allowMappingConflicts</span><span class="sxs-lookup"><span data-stu-id="32225-219">Attribute Name: allowMappingConflicts</span></span><br /><br /> <span data-ttu-id="32225-220">既定値:いいえ</span><span class="sxs-lookup"><span data-stu-id="32225-220">Default: No</span></span>|  
  
    |<span data-ttu-id="32225-221">アダプターの説明</span><span class="sxs-lookup"><span data-stu-id="32225-221">Adapter Description</span></span>|<span data-ttu-id="32225-222">詳細</span><span class="sxs-lookup"><span data-stu-id="32225-222">Details</span></span>|  
    |-------------------------|-------------|  
    |<span data-ttu-id="32225-223">通知の再試行回数</span><span class="sxs-lookup"><span data-stu-id="32225-223">Notification retry count</span></span>|<span data-ttu-id="32225-224">既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="32225-224">Default is 1.</span></span>|  
    |<span data-ttu-id="32225-225">通知の再試行間隔 (分)</span><span class="sxs-lookup"><span data-stu-id="32225-225">Notification retry delay (in mins)</span></span>|<span data-ttu-id="32225-226">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="32225-226">Default is 5.</span></span>|  
    |<span data-ttu-id="32225-227">保留中の通知の最大数</span><span class="sxs-lookup"><span data-stu-id="32225-227">Maximum pending notifications</span></span>|<span data-ttu-id="32225-228">既定値は 8 です。</span><span class="sxs-lookup"><span data-stu-id="32225-228">Default is 8.</span></span>|  
    |<span data-ttu-id="32225-229">通知 (オフライン時) の格納します。</span><span class="sxs-lookup"><span data-stu-id="32225-229">Store notifications (when offline)</span></span>|<span data-ttu-id="32225-230">True または False。</span><span class="sxs-lookup"><span data-stu-id="32225-230">True/False.</span></span>|  
    |<span data-ttu-id="32225-231">サーバー名</span><span class="sxs-lookup"><span data-stu-id="32225-231">Server name</span></span>|<span data-ttu-id="32225-232">サーバー名。</span><span class="sxs-lookup"><span data-stu-id="32225-232">Server name.</span></span>|  
    |<span data-ttu-id="32225-233">[ポート番号]</span><span class="sxs-lookup"><span data-stu-id="32225-233">Port number</span></span>|<span data-ttu-id="32225-234">ポート番号。</span><span class="sxs-lookup"><span data-stu-id="32225-234">Port number.</span></span>|  
    |<span data-ttu-id="32225-235">このアダプタのアプリケーション</span><span class="sxs-lookup"><span data-stu-id="32225-235">Applications for this adapter</span></span>|<span data-ttu-id="32225-236">現在アダプターに割り当てられているアプリケーションの一覧です。</span><span class="sxs-lookup"><span data-stu-id="32225-236">List of applications currently assigned to the adapter.</span></span>|  
  
### <a name="to-create-new-adapters"></a><span data-ttu-id="32225-237">新しいアダプターを作成するには</span><span class="sxs-lookup"><span data-stu-id="32225-237">To create new adapters</span></span>  
  
1.  <span data-ttu-id="32225-238">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32225-238">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="32225-239">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="32225-239">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="32225-240">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="32225-240">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="32225-241">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="32225-241">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="32225-242">型**ssops-作成\<アダプター ファイル\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="32225-242">Type **ssops -create \<adapter file\>** and press Enter.</span></span>  
  
     <span data-ttu-id="32225-243">新しく作成されたアダプターの情報は、画面出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="32225-243">The screen output will display information for the newly created adapter.</span></span>  
  
### <a name="to-set-properties-for-an-adapter"></a><span data-ttu-id="32225-244">アダプターのプロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="32225-244">To set properties for an adapter</span></span>  
  
1.  <span data-ttu-id="32225-245">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32225-245">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="32225-246">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="32225-246">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="32225-247">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="32225-247">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="32225-248">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="32225-248">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="32225-249">型**ssops-setprops\<アダプター名\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="32225-249">Type **ssops -setprops \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="32225-250">指定したアダプタのプロパティは、画面出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="32225-250">The screen output will display the properties for the specified adapter.</span></span> <span data-ttu-id="32225-251">必要に応じて、それらを編集することができますが、新しい値は検証されません。</span><span class="sxs-lookup"><span data-stu-id="32225-251">You can edit them if necessary, but new values are not validated.</span></span>  
  
### <a name="to-update-existing-adapters"></a><span data-ttu-id="32225-252">既存のアダプタを更新するには</span><span class="sxs-lookup"><span data-stu-id="32225-252">To update existing adapters</span></span>  
  
1.  <span data-ttu-id="32225-253">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32225-253">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="32225-254">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="32225-254">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="32225-255">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="32225-255">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="32225-256">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="32225-256">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="32225-257">型**ssops-更新\<アダプター ファイル\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="32225-257">Type **ssops -update \<adapter file\>** and press Enter.</span></span>  
  
     <span data-ttu-id="32225-258">このコマンドを使用すると、設定と指定したアダプタのフラグを更新できます。</span><span class="sxs-lookup"><span data-stu-id="32225-258">Use this command to update the settings and flags for a specified adapter.</span></span> <span data-ttu-id="32225-259">プロパティを設定するのにはこのコマンドを使用しないでください。代わりに-setprops コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="32225-259">Do not use this command to set properties; use instead the -setprops command.</span></span>  
  
### <a name="to-delete-an-existing-adapter"></a><span data-ttu-id="32225-260">既存のアダプターを削除するには</span><span class="sxs-lookup"><span data-stu-id="32225-260">To delete an existing adapter</span></span>  
  
1.  <span data-ttu-id="32225-261">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32225-261">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="32225-262">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="32225-262">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="32225-263">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="32225-263">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="32225-264">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="32225-264">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="32225-265">型**ssops-削除\<アダプター名\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="32225-265">Type **ssops -delete \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="32225-266">指定されたアダプターは削除されます。</span><span class="sxs-lookup"><span data-stu-id="32225-266">The specified adapter will be deleted.</span></span>  
  
### <a name="to-enable-an-adapter"></a><span data-ttu-id="32225-267">アダプターを有効にするには</span><span class="sxs-lookup"><span data-stu-id="32225-267">To enable an adapter</span></span>  
  
1.  <span data-ttu-id="32225-268">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32225-268">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="32225-269">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="32225-269">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="32225-270">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="32225-270">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="32225-271">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="32225-271">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="32225-272">型**ssops-有効にする\<アダプター名\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="32225-272">Type **ssops -enable \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="32225-273">指定したアダプターを有効になります。</span><span class="sxs-lookup"><span data-stu-id="32225-273">The specified adapter will be enabled.</span></span>  
  
### <a name="to-disable-an-adapter"></a><span data-ttu-id="32225-274">アダプターを無効にするには</span><span class="sxs-lookup"><span data-stu-id="32225-274">To disable an adapter</span></span>  
  
1.  <span data-ttu-id="32225-275">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32225-275">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="32225-276">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="32225-276">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="32225-277">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="32225-277">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="32225-278">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="32225-278">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="32225-279">型**ssops-を無効にする\<アダプター名\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="32225-279">Type **ssops -disable \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="32225-280">指定したアダプタが無効になります。</span><span class="sxs-lookup"><span data-stu-id="32225-280">The specified adapter will be disabled.</span></span>  
  
### <a name="to-add-an-application-to-an-adapter"></a><span data-ttu-id="32225-281">アダプターにアプリケーションを追加するには</span><span class="sxs-lookup"><span data-stu-id="32225-281">To add an application to an adapter</span></span>  
  
1.  <span data-ttu-id="32225-282">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32225-282">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="32225-283">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="32225-283">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="32225-284">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="32225-284">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="32225-285">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="32225-285">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="32225-286">型**ssops-addapp\<アダプター名\>\<アプリケーション名\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="32225-286">Type **ssops -addapp \<adapter name\> \<application name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="32225-287">指定した SSO アプリケーションは、指定されたアダプターに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="32225-287">The specified SSO application will be assigned to the specified adapter.</span></span> <span data-ttu-id="32225-288">つまり、パスワードのマッピングのことで、アプリケーションはこのアダプターを使用して同期ようになりました。</span><span class="sxs-lookup"><span data-stu-id="32225-288">This means that the passwords for the mappings in that application will now be synchronized using this adapter.</span></span>  
  
     <span data-ttu-id="32225-289">複数のアプリケーションは、1 つのアダプターに割り当てることができます、任意のアプリケーションは 1 つのアダプターにのみ割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="32225-289">While multiple applications can be assigned to one adapter, any given application can only be assigned to one adapter.</span></span>  
  
### <a name="to-delete-an-application-from-an-adapter"></a><span data-ttu-id="32225-290">アダプターからアプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="32225-290">To delete an application from an adapter</span></span>  
  
1.  <span data-ttu-id="32225-291">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32225-291">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="32225-292">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="32225-292">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="32225-293">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="32225-293">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="32225-294">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="32225-294">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="32225-295">型**ssops-deleteapp\<アプリケーション名\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="32225-295">Type **ssops -deleteapp \<application name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="32225-296">指定した SSO アプリケーションは、アダプターから削除されます。</span><span class="sxs-lookup"><span data-stu-id="32225-296">The specified SSO application will be removed from an adapter.</span></span> <span data-ttu-id="32225-297">(アプリケーションは、1 つのアダプターにのみ割り当てることができます、ため必要はありませんアダプター名を指定します。)</span><span class="sxs-lookup"><span data-stu-id="32225-297">(Since an application can only be assigned to one adapter, it is not necessary to specify the adapter name.)</span></span>  
  
### <a name="to-reset-notification"></a><span data-ttu-id="32225-298">通知をリセットするには</span><span class="sxs-lookup"><span data-stu-id="32225-298">To reset notification</span></span>  
  
1.  <span data-ttu-id="32225-299">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32225-299">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="32225-300">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="32225-300">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="32225-301">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="32225-301">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="32225-302">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="32225-302">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="32225-303">型**ssops-リセット\<アダプター名&#124;すべて&#124;減衰\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="32225-303">Type **ssops -reset \<adapter name &#124; all &#124; damping\>** and press Enter.</span></span>  
  
     <span data-ttu-id="32225-304">このコマンドは、1 つのアダプターまたは指定されたすべてのアダプターの抑制テーブルや通知キューをクリアします。</span><span class="sxs-lookup"><span data-stu-id="32225-304">This command clears the damping table and/or notification queues for a single adapter or all adapters, as specified.</span></span> <span data-ttu-id="32225-305">抑制テーブルには、パスワードの変更の 10 分間の履歴が格納されます。</span><span class="sxs-lookup"><span data-stu-id="32225-305">The damping table stores a 10-minute history of password changes.</span></span> <span data-ttu-id="32225-306">エンタープライズ SSO システムを受け入れるか、パスワードの変更を送信する前に行われた同じ変更最近表示抑制テーブルを確認します。</span><span class="sxs-lookup"><span data-stu-id="32225-306">Before the Enterprise SSO system accepts or sends a password change, it checks the damping table to see if it has performed the same change recently.</span></span> <span data-ttu-id="32225-307">場合は、新しい変更は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="32225-307">If it has, the new change is discarded.</span></span>  
  
### <a name="to-add-an-adapter-to-an-adapter-group"></a><span data-ttu-id="32225-308">アダプタ グループにアダプターを追加するには</span><span class="sxs-lookup"><span data-stu-id="32225-308">To add an adapter to an adapter group</span></span>  
  
1.  <span data-ttu-id="32225-309">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32225-309">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="32225-310">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="32225-310">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="32225-311">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="32225-311">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="32225-312">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="32225-312">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="32225-313">型**ssops-addtogroup」\<アダプター名\>\<アダプター グループ\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="32225-313">Type **ssops -addtogroup \<adapter name\> \<adapter group\>** and press Enter.</span></span>  
  
     <span data-ttu-id="32225-314">このコマンドは、指定したアダプタ グループに指定したアダプターを追加します。</span><span class="sxs-lookup"><span data-stu-id="32225-314">This command adds the specified adapter to the specified adapter group.</span></span> <span data-ttu-id="32225-315">アダプターは、1 つだけのアダプタ グループに属することができます、中に、アダプター グループは、複数のアダプターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="32225-315">While an adapter can belong to only one adapter group, an adapter group can contain multiple adapters.</span></span>  
  
### <a name="to-delete-an-adapter-from-an-adapter-group"></a><span data-ttu-id="32225-316">アダプタ グループからアダプターを削除するには</span><span class="sxs-lookup"><span data-stu-id="32225-316">To delete an adapter from an adapter group</span></span>  
  
1.  <span data-ttu-id="32225-317">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32225-317">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="32225-318">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="32225-318">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="32225-319">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="32225-319">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="32225-320">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="32225-320">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="32225-321">型**ssops-deletefromgroup\<アダプター名\>\<アダプター グループ\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="32225-321">Type **ssops -deletefromgroup \<adapter name\> \<adapter group\>** and press Enter.</span></span>  
  
     <span data-ttu-id="32225-322">このコマンドは、指定したアダプタ グループから、指定されたアダプターを削除します。</span><span class="sxs-lookup"><span data-stu-id="32225-322">This command deletes the specified adapter from the specified adapter group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32225-323">参照</span><span class="sxs-lookup"><span data-stu-id="32225-323">See Also</span></span>  
 [<span data-ttu-id="32225-324">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="32225-324">Password Synchronization</span></span>](../core/password-synchronization2.md)