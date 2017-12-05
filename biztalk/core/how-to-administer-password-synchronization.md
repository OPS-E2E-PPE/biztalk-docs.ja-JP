---
title: "パスワード同期を管理する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddd696da8b4cab24a8de6a4b5d8ac8f26856f7e1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-administer-password-synchronization"></a><span data-ttu-id="62012-102">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="62012-102">How to Administer Password Synchronization</span></span>
<span data-ttu-id="62012-103">パスワード同期は、MMC スナップインまたはコマンド ラインを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="62012-103">You can administer Password Synchronization through either the MMC Snap-In or the command line.</span></span>  
  
 <span data-ttu-id="62012-104">MMC スナップインでは、アダプタとそのプロパティの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="62012-104">The MMC Snap-In displays a list of adapters and their properties.</span></span> <span data-ttu-id="62012-105">アダプタを右クリックしてメニューを使用すると、次のようなコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="62012-105">You can right-click an adapter and use the menu to perform the following commands:</span></span>  
  
-   <span data-ttu-id="62012-106">アダプタの作成</span><span class="sxs-lookup"><span data-stu-id="62012-106">Create adapters</span></span>  
  
-   <span data-ttu-id="62012-107">プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="62012-107">Set properties</span></span>  
  
-   <span data-ttu-id="62012-108">Update</span><span class="sxs-lookup"><span data-stu-id="62012-108">Update</span></span>  
  
-   <span data-ttu-id="62012-109">DELETE</span><span class="sxs-lookup"><span data-stu-id="62012-109">Delete</span></span>  
  
-   <span data-ttu-id="62012-110">[有効化]</span><span class="sxs-lookup"><span data-stu-id="62012-110">Enable</span></span>  
  
-   <span data-ttu-id="62012-111">Disable</span><span class="sxs-lookup"><span data-stu-id="62012-111">Disable</span></span>  
  
-   <span data-ttu-id="62012-112">アダプタへのアプリケーションの追加</span><span class="sxs-lookup"><span data-stu-id="62012-112">Add applications to an adapter</span></span>  
  
-   <span data-ttu-id="62012-113">アダプタからのアプリケーションの削除</span><span class="sxs-lookup"><span data-stu-id="62012-113">Delete applications from an adapter</span></span>  
  
-   <span data-ttu-id="62012-114">通知の再設定</span><span class="sxs-lookup"><span data-stu-id="62012-114">Reset notification</span></span>  
  
-   <span data-ttu-id="62012-115">アダプタ グループへのアダプタの追加</span><span class="sxs-lookup"><span data-stu-id="62012-115">Add an adapter to an adapter group</span></span>  
  
-   <span data-ttu-id="62012-116">アダプタ グループからのアダプタの削除</span><span class="sxs-lookup"><span data-stu-id="62012-116">Delete an adapter from an adapter group</span></span>  
  
 <span data-ttu-id="62012-117">また、パスワード同期の管理に SSOPS コマンド ライン ユーティリティを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="62012-117">You can also use the SSOPS command line utility to administer your password synchronization.</span></span> <span data-ttu-id="62012-118">このセクションで説明する大半のコマンドは、管理者だけが使用できます。</span><span class="sxs-lookup"><span data-stu-id="62012-118">Most of commands in this section are intended for use by an administrator only.</span></span>  
  
 <span data-ttu-id="62012-119">多くのコマンドでは、コマンド出力が画面上に 2 列で表示されます。</span><span class="sxs-lookup"><span data-stu-id="62012-119">For many commands, the command output is displayed on the screen in two columns.</span></span> <span data-ttu-id="62012-120">画面設定によってはデータが切り捨てられるため、画面バッファのサイズまたはウィンドウのサイズを 120 文字に変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="62012-120">As certain screen settings may cause truncation of data, for best results you should change the screen buffer size/Windows size to 120 characters.</span></span>  
  
 <span data-ttu-id="62012-121">SSOPS コマンドを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="62012-121">The SSOPS commands are listed in the following table.</span></span> <span data-ttu-id="62012-122">手順と詳細については、このトピックの後半で説明します。</span><span class="sxs-lookup"><span data-stu-id="62012-122">Procedures and further explanation are located throughout the rest of this topic.</span></span>  
  
|<span data-ttu-id="62012-123">Command</span><span class="sxs-lookup"><span data-stu-id="62012-123">Command</span></span>|<span data-ttu-id="62012-124">関数</span><span class="sxs-lookup"><span data-stu-id="62012-124">Function</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="62012-125">-list</span><span class="sxs-lookup"><span data-stu-id="62012-125">-list</span></span>|<span data-ttu-id="62012-126">既存のアダプタを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="62012-126">Lists existing adapters</span></span>|  
|<span data-ttu-id="62012-127">-display</span><span class="sxs-lookup"><span data-stu-id="62012-127">-display</span></span>|<span data-ttu-id="62012-128">アダプタの情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="62012-128">Displays adapter information</span></span>|  
|<span data-ttu-id="62012-129">-create</span><span class="sxs-lookup"><span data-stu-id="62012-129">-create</span></span>|<span data-ttu-id="62012-130">新しいアダプタを作成します。</span><span class="sxs-lookup"><span data-stu-id="62012-130">Creates new adapter(s)</span></span>|  
|<span data-ttu-id="62012-131">-setprops</span><span class="sxs-lookup"><span data-stu-id="62012-131">-setprops</span></span>|<span data-ttu-id="62012-132">アダプタのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="62012-132">Sets properties for adapter</span></span>|  
|<span data-ttu-id="62012-133">-update</span><span class="sxs-lookup"><span data-stu-id="62012-133">-update</span></span>|<span data-ttu-id="62012-134">既存のアダプタを更新します。</span><span class="sxs-lookup"><span data-stu-id="62012-134">Updates existing adapter(s)</span></span>|  
|<span data-ttu-id="62012-135">-delete</span><span class="sxs-lookup"><span data-stu-id="62012-135">-delete</span></span>|<span data-ttu-id="62012-136">既存のアダプタを削除します。</span><span class="sxs-lookup"><span data-stu-id="62012-136">Deletes an existing adapter</span></span>|  
|<span data-ttu-id="62012-137">-enable</span><span class="sxs-lookup"><span data-stu-id="62012-137">-enable</span></span>|<span data-ttu-id="62012-138">アダプタを有効にします。</span><span class="sxs-lookup"><span data-stu-id="62012-138">Enables adapter</span></span>|  
|<span data-ttu-id="62012-139">-disable</span><span class="sxs-lookup"><span data-stu-id="62012-139">-disable</span></span>|<span data-ttu-id="62012-140">アダプタを無効にします。</span><span class="sxs-lookup"><span data-stu-id="62012-140">Disables adapter</span></span>|  
|<span data-ttu-id="62012-141">-addapp</span><span class="sxs-lookup"><span data-stu-id="62012-141">-addapp</span></span>|<span data-ttu-id="62012-142">アダプタのアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="62012-142">Adds application for adapter</span></span>|  
|<span data-ttu-id="62012-143">-deleteapp</span><span class="sxs-lookup"><span data-stu-id="62012-143">-deleteapp</span></span>|<span data-ttu-id="62012-144">アダプタのアプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="62012-144">Deletes application for adapter</span></span>|  
|<span data-ttu-id="62012-145">-reset</span><span class="sxs-lookup"><span data-stu-id="62012-145">-reset</span></span>|<span data-ttu-id="62012-146">通知キューまたは抑制キューを再設定します。</span><span class="sxs-lookup"><span data-stu-id="62012-146">Resets notification or damping queues</span></span>|  
|<span data-ttu-id="62012-147">-addtogroup</span><span class="sxs-lookup"><span data-stu-id="62012-147">-addtogroup</span></span>|<span data-ttu-id="62012-148">アダプタ グループにアダプタを追加します。</span><span class="sxs-lookup"><span data-stu-id="62012-148">Adds adapter to adapter group</span></span>|  
|<span data-ttu-id="62012-149">-deletefromgroup</span><span class="sxs-lookup"><span data-stu-id="62012-149">-deletefromgroup</span></span>|<span data-ttu-id="62012-150">アダプタ グループからアダプタを削除します。</span><span class="sxs-lookup"><span data-stu-id="62012-150">Deletes adapter from adapter group</span></span>|  
  
### <a name="to-list-existing-adapters"></a><span data-ttu-id="62012-151">既存のアダプタを一覧表示するには</span><span class="sxs-lookup"><span data-stu-id="62012-151">To list existing adapters</span></span>  
  
1.  <span data-ttu-id="62012-152">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62012-152">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="62012-153">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="62012-153">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="62012-154">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="62012-154">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="62012-155">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="62012-155">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="62012-156">型**ssops-リスト**Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="62012-156">Type **ssops -list** and press Enter.</span></span>  
  
     <span data-ttu-id="62012-157">アダプターと説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="62012-157">Adapters and descriptions will be listed.</span></span> <span data-ttu-id="62012-158">(E) はアダプタが有効であることを表し、(D) はアダプタが無効であることを表します。</span><span class="sxs-lookup"><span data-stu-id="62012-158">(E) denotes that the adapter is enabled, (D) denotes that it is disabled.</span></span>  
  
### <a name="to-display-adapter-information"></a><span data-ttu-id="62012-159">アダプタの情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="62012-159">To display adapter information</span></span>  
  
1.  <span data-ttu-id="62012-160">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62012-160">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="62012-161">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="62012-161">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="62012-162">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="62012-162">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="62012-163">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="62012-163">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="62012-164">型**ssops-表示\<アダプター名\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="62012-164">Type **ssops -display \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="62012-165">画面出力により、指定したアダプタの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="62012-165">The screen output will display information for the specified adapter.</span></span>  
  
     <span data-ttu-id="62012-166">名前、種類、説明、コンピュータ、およびアカウントに加え、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="62012-166">In addition to name, type, description, computer, and accounts, the following information is displayed.</span></span>  
  
    |<span data-ttu-id="62012-167">アダプタ フラグ</span><span class="sxs-lookup"><span data-stu-id="62012-167">Adapter Flag</span></span>|<span data-ttu-id="62012-168">詳細</span><span class="sxs-lookup"><span data-stu-id="62012-168">Details</span></span>|  
    |------------------|-------------|  
    |<span data-ttu-id="62012-169">[アダプタは有効]</span><span class="sxs-lookup"><span data-stu-id="62012-169">Adapter enabled</span></span>|<span data-ttu-id="62012-170">アダプタが有効かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="62012-170">Determines whether or not the adapter is enabled.</span></span><br /><br /> <span data-ttu-id="62012-171">フラグ: SSO_FLAG_ENABLED</span><span class="sxs-lookup"><span data-stu-id="62012-171">Flag: SSO_FLAG_ENABLED</span></span><br /><br /> <span data-ttu-id="62012-172">属性名: enableApp</span><span class="sxs-lookup"><span data-stu-id="62012-172">Attribute Name: enableApp</span></span><br /><br /> <span data-ttu-id="62012-173">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="62012-173">Default: No</span></span>|  
    |<span data-ttu-id="62012-174">[ローカル アカウントを許可]</span><span class="sxs-lookup"><span data-stu-id="62012-174">Allow local accounts</span></span>|<span data-ttu-id="62012-175">アプリケーション管理アカウントまたはアプリケーション ユーザー アカウントにローカル アカウントを指定できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="62012-175">Determines whether or not the App Admin or App Users accounts can be local accounts.</span></span><br /><br /> <span data-ttu-id="62012-176">フラグ: SSO_FLAG_APP_ALLOW_LOCAL</span><span class="sxs-lookup"><span data-stu-id="62012-176">Flag: SSO_FLAG_APP_ALLOW_LOCAL</span></span><br /><br /> <span data-ttu-id="62012-177">属性名: allowLocalAccounts</span><span class="sxs-lookup"><span data-stu-id="62012-177">Attribute Name: allowLocalAccounts</span></span><br /><br /> <span data-ttu-id="62012-178">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="62012-178">Default: No</span></span>|  
    |<span data-ttu-id="62012-179">[アダプタからパスワードの変更を受信]</span><span class="sxs-lookup"><span data-stu-id="62012-179">Receive password changes from adapter</span></span>|<span data-ttu-id="62012-180">アダプタで外部パスワード変更を受け取ることを許可するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="62012-180">Determines whether or not the adapter is allowed to receive external password changes.</span></span><br /><br /> <span data-ttu-id="62012-181">フラグ: する SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB</span><span class="sxs-lookup"><span data-stu-id="62012-181">Flag: SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB</span></span><br /><br /> <span data-ttu-id="62012-182">属性名: syncFromAdapter</span><span class="sxs-lookup"><span data-stu-id="62012-182">Attribute Name: syncFromAdapter</span></span><br /><br /> <span data-ttu-id="62012-183">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="62012-183">Default: No</span></span>|  
    |<span data-ttu-id="62012-184">[以前のパスワードを確認]</span><span class="sxs-lookup"><span data-stu-id="62012-184">Verify old password</span></span>|<span data-ttu-id="62012-185">アダプタで外部パスワード変更を受け取ったときに、以前のパスワードを確認するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="62012-185">Determines whether the adapter will verify the old password when an external password change is received.</span></span> <span data-ttu-id="62012-186">このフラグが設定されている場合、外部パスワード変更時に外部アダプタでは、新しい外部パスワードだけでなく以前の外部パスワードも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62012-186">If this flag is set then with an external password change the external adapter must supply the old external password as well as the new external password.</span></span> <span data-ttu-id="62012-187">以前の外部パスワードは、外部アカウントの SSO データベース内の既存の外部パスワードと比較されます。</span><span class="sxs-lookup"><span data-stu-id="62012-187">The old external password is then compared with the existing external password in the SSO database for that external account.</span></span> <span data-ttu-id="62012-188">両方のパスワードが一致する場合はパスワードの変更が認められ、</span><span class="sxs-lookup"><span data-stu-id="62012-188">If they match, the password change is accepted.</span></span> <span data-ttu-id="62012-189">一致しない場合は拒否されます。</span><span class="sxs-lookup"><span data-stu-id="62012-189">If they do not match, the password change is rejected.</span></span><br /><br /> <span data-ttu-id="62012-190">フラグ: SSO_FLAG_SYNC_VERIFY_EXTERNAL_CREDS</span><span class="sxs-lookup"><span data-stu-id="62012-190">Flag: SSO_FLAG_SYNC_VERIFY_EXTERNAL_CREDS</span></span><br /><br /> <span data-ttu-id="62012-191">属性名: verifyOldPassword</span><span class="sxs-lookup"><span data-stu-id="62012-191">Attribute Name: verifyOldPassword</span></span><br /><br /> <span data-ttu-id="62012-192">既定値: はい</span><span class="sxs-lookup"><span data-stu-id="62012-192">Default: Yes</span></span>|  
    |<span data-ttu-id="62012-193">[Windows パスワードの変更]</span><span class="sxs-lookup"><span data-stu-id="62012-193">Change Windows password</span></span>|<span data-ttu-id="62012-194">外部パスワード変更を受け取ったときに、Windows パスワードも変更するかどうかを指定します (完全同期)。</span><span class="sxs-lookup"><span data-stu-id="62012-194">Determines whether or not the Windows password will also be changed when an external password change is received (full sync).</span></span> <span data-ttu-id="62012-195">ENTSSO は、常に、SSO データベースに格納されている以前の Windows パスワードを使用して、Windows パスワードを新しい値に変更します (Windows では、ユーザーのパスワードを変更する際に、以前のパスワードと新しいパスワードの両方が必要です)。そのため、Windows パスワードの変更を正常に完了するには、以前のパスワードを初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62012-195">ENTSSO always uses the old Windows password stored in the SSO database to change the Windows password to the new value (Windows requires both the old and new password to change a users password), so this must be initialized before the Windows password change can succeed.</span></span> <span data-ttu-id="62012-196">パスワード同期が特定のマッピングに対して構成されている場合、管理ツール (ssomanage または ssoclient-setcredentials) を使用して外部資格情報を設定すると、SSO データベースに格納されている Windows パスワードも設定されます。フラグ: SSO_FLAG_FULL_SYNC_FROM_EXTERNAL_TO_WINDOWS</span><span class="sxs-lookup"><span data-stu-id="62012-196">If password sync is configured for a particular mapping, then when the external credentials are set via administrative tools (ssomanage or ssoclient -setcredentials) the Windows password stored in the SSO database will also be set.Flag: SSO_FLAG_FULL_SYNC_FROM_EXTERNAL_TO_WINDOWS</span></span><br /><br /> <span data-ttu-id="62012-197">属性名: changeWindowsPassword</span><span class="sxs-lookup"><span data-stu-id="62012-197">Attribute Name: changeWindowsPassword</span></span><br /><br /> <span data-ttu-id="62012-198">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="62012-198">Default: No</span></span>|  
    |<span data-ttu-id="62012-199">[Windows パスワードの変更をアダプタに送信]</span><span class="sxs-lookup"><span data-stu-id="62012-199">Send Windows password changes to adapter</span></span>|<span data-ttu-id="62012-200">Windows パスワード変更を外部アダプタに送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="62012-200">Determines whether or not Windows password changes will be sent to the external adapter.</span></span><br /><br /> <span data-ttu-id="62012-201">フラグ: SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL</span><span class="sxs-lookup"><span data-stu-id="62012-201">Flag: SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL</span></span><br /><br /> <span data-ttu-id="62012-202">属性名: syncToAdapter</span><span class="sxs-lookup"><span data-stu-id="62012-202">Attribute Name: syncToAdapter</span></span><br /><br /> <span data-ttu-id="62012-203">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="62012-203">Default: No</span></span>|  
    |<span data-ttu-id="62012-204">[以前のパスワードをアダプタに送信]</span><span class="sxs-lookup"><span data-stu-id="62012-204">Send old password to adapter</span></span>|<span data-ttu-id="62012-205">[はい] を指定すると、新しいパスワードの値と共に、SSO データベースに格納されている以前のパスワードの値も外部アダプタに送信されます。</span><span class="sxs-lookup"><span data-stu-id="62012-205">If Yes, the old password value (from the SSO database) will also be sent to the external adapter as well as the new password value.</span></span> <span data-ttu-id="62012-206">いくつかの外部システムでは、パスワード変更に、以前のパスワードの値と新しいパスワードの値の両方が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="62012-206">Some external systems might require both the old and new password values to change the password.</span></span><br /><br /> <span data-ttu-id="62012-207">フラグ: SSO_FLAG_SYNC_PROVIDE_OLD_EXTERNAL_CREDS</span><span class="sxs-lookup"><span data-stu-id="62012-207">Flag: SSO_FLAG_SYNC_PROVIDE_OLD_EXTERNAL_CREDS</span></span><br /><br /> <span data-ttu-id="62012-208">属性名: sendOldPassword</span><span class="sxs-lookup"><span data-stu-id="62012-208">Attribute Name: sendOldPassword</span></span><br /><br /> <span data-ttu-id="62012-209">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="62012-209">Default: No</span></span>|  
    |<span data-ttu-id="62012-210">[マッピングの競合を許可]</span><span class="sxs-lookup"><span data-stu-id="62012-210">Allow mapping conflicts</span></span>|<span data-ttu-id="62012-211">アダプタでマッピングの競合を許可するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="62012-211">Determines whether or not the adapter will allow mapping conflicts.</span></span><br /><br /> <span data-ttu-id="62012-212">マッピングの競合は、マッピングが一意でないときに発生します。</span><span class="sxs-lookup"><span data-stu-id="62012-212">A mapping conflict occurs when mappings are not unique.</span></span> <span data-ttu-id="62012-213">1 つの SSO 単独アプリケーションでのマッピングは、常に 1 対 1: Windows アカウントが 1 つの外部アカウントに、その逆にマップされているいずれか。</span><span class="sxs-lookup"><span data-stu-id="62012-213">In a single SSO Individual application, mappings are always one-to-one: one Windows account is mapped to exactly one external account and vice versa.</span></span><br /><br /> <span data-ttu-id="62012-214">ただし、複数のアプリケーションを 1 つのアダプタに割り当てることは可能です。</span><span class="sxs-lookup"><span data-stu-id="62012-214">However, it is possible to assign more than one application to an adapter.</span></span> <span data-ttu-id="62012-215">したがって、あるアプリケーション内のマッピングが別のアプリケーション内のマッピングと競合する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="62012-215">Thus, it is possible to have a mapping in one application that conflicts with a mapping in the other.</span></span><br /><br /> <span data-ttu-id="62012-216">このフラグの目的は、マッピングの競合の発生を防ぐことです。</span><span class="sxs-lookup"><span data-stu-id="62012-216">This purpose of this flag is to prevent this from occurring.</span></span> <span data-ttu-id="62012-217">具体的で十分な理由がない限り、マッピングの競合を許可しないようにする方がより安全です。</span><span class="sxs-lookup"><span data-stu-id="62012-217">It is more secure to not allow mapping conflicts unless there is a specific, well understood requirement for this behavior.</span></span><br /><br /> <span data-ttu-id="62012-218">フラグ: SSO_FLAG_SYNC_ALLOW_MAPPING_CONFLICTS</span><span class="sxs-lookup"><span data-stu-id="62012-218">Flag: SSO_FLAG_SYNC_ALLOW_MAPPING_CONFLICTS</span></span><br /><br /> <span data-ttu-id="62012-219">属性名: allowMappingConflicts</span><span class="sxs-lookup"><span data-stu-id="62012-219">Attribute Name: allowMappingConflicts</span></span><br /><br /> <span data-ttu-id="62012-220">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="62012-220">Default: No</span></span>|  
  
    |<span data-ttu-id="62012-221">アダプタの説明</span><span class="sxs-lookup"><span data-stu-id="62012-221">Adapter Description</span></span>|<span data-ttu-id="62012-222">詳細</span><span class="sxs-lookup"><span data-stu-id="62012-222">Details</span></span>|  
    |-------------------------|-------------|  
    |<span data-ttu-id="62012-223">通知の再試行回数</span><span class="sxs-lookup"><span data-stu-id="62012-223">Notification retry count</span></span>|<span data-ttu-id="62012-224">既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="62012-224">Default is 1.</span></span>|  
    |<span data-ttu-id="62012-225">通知の再試行間隔 (分)</span><span class="sxs-lookup"><span data-stu-id="62012-225">Notification retry delay (in mins)</span></span>|<span data-ttu-id="62012-226">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="62012-226">Default is 5.</span></span>|  
    |<span data-ttu-id="62012-227">通知の最大保留数</span><span class="sxs-lookup"><span data-stu-id="62012-227">Maximum pending notifications</span></span>|<span data-ttu-id="62012-228">既定値は 8 です。</span><span class="sxs-lookup"><span data-stu-id="62012-228">Default is 8.</span></span>|  
    |<span data-ttu-id="62012-229">通知の格納 (オフライン時)</span><span class="sxs-lookup"><span data-stu-id="62012-229">Store notifications (when offline)</span></span>|<span data-ttu-id="62012-230">True または False です。</span><span class="sxs-lookup"><span data-stu-id="62012-230">True/False.</span></span>|  
    |<span data-ttu-id="62012-231">サーバー名</span><span class="sxs-lookup"><span data-stu-id="62012-231">Server name</span></span>|<span data-ttu-id="62012-232">サーバー名。</span><span class="sxs-lookup"><span data-stu-id="62012-232">Server name.</span></span>|  
    |<span data-ttu-id="62012-233">[ポート番号]</span><span class="sxs-lookup"><span data-stu-id="62012-233">Port number</span></span>|<span data-ttu-id="62012-234">ポート番号です。</span><span class="sxs-lookup"><span data-stu-id="62012-234">Port number.</span></span>|  
    |<span data-ttu-id="62012-235">このアダプタのアプリケーション</span><span class="sxs-lookup"><span data-stu-id="62012-235">Applications for this adapter</span></span>|<span data-ttu-id="62012-236">現在アダプタに割り当てられているアプリケーションの一覧です。</span><span class="sxs-lookup"><span data-stu-id="62012-236">List of applications currently assigned to the adapter.</span></span>|  
  
### <a name="to-create-new-adapters"></a><span data-ttu-id="62012-237">新しいアダプタを作成するには</span><span class="sxs-lookup"><span data-stu-id="62012-237">To create new adapters</span></span>  
  
1.  <span data-ttu-id="62012-238">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62012-238">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="62012-239">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="62012-239">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="62012-240">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="62012-240">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="62012-241">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="62012-241">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="62012-242">型**ssops-作成\<アダプター ファイル\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="62012-242">Type **ssops -create \<adapter file\>** and press Enter.</span></span>  
  
     <span data-ttu-id="62012-243">画面出力により、新しく作成されたアダプタの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="62012-243">The screen output will display information for the newly created adapter.</span></span>  
  
### <a name="to-set-properties-for-an-adapter"></a><span data-ttu-id="62012-244">アダプタのプロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="62012-244">To set properties for an adapter</span></span>  
  
1.  <span data-ttu-id="62012-245">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62012-245">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="62012-246">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="62012-246">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="62012-247">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="62012-247">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="62012-248">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="62012-248">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="62012-249">型**ssops-setprops」\<アダプター名\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="62012-249">Type **ssops -setprops \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="62012-250">画面出力により、指定したアダプタのプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="62012-250">The screen output will display the properties for the specified adapter.</span></span> <span data-ttu-id="62012-251">これらのプロパティは必要に応じて編集できますが、新しい値は検証されません。</span><span class="sxs-lookup"><span data-stu-id="62012-251">You can edit them if necessary, but new values are not validated.</span></span>  
  
### <a name="to-update-existing-adapters"></a><span data-ttu-id="62012-252">既存のアダプタを更新するには</span><span class="sxs-lookup"><span data-stu-id="62012-252">To update existing adapters</span></span>  
  
1.  <span data-ttu-id="62012-253">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62012-253">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="62012-254">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="62012-254">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="62012-255">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="62012-255">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="62012-256">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="62012-256">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="62012-257">型**ssops-更新\<アダプター ファイル\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="62012-257">Type **ssops -update \<adapter file\>** and press Enter.</span></span>  
  
     <span data-ttu-id="62012-258">このコマンドを使用して、指定したアダプタの設定およびフラグを更新します。</span><span class="sxs-lookup"><span data-stu-id="62012-258">Use this command to update the settings and flags for a specified adapter.</span></span> <span data-ttu-id="62012-259">プロパティを設定する場合には、このコマンドは使用せず、代わりに -setprops コマンドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="62012-259">Do not use this command to set properties; use instead the -setprops command.</span></span>  
  
### <a name="to-delete-an-existing-adapter"></a><span data-ttu-id="62012-260">既存のアダプタを削除するには</span><span class="sxs-lookup"><span data-stu-id="62012-260">To delete an existing adapter</span></span>  
  
1.  <span data-ttu-id="62012-261">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62012-261">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="62012-262">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="62012-262">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="62012-263">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="62012-263">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="62012-264">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="62012-264">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="62012-265">型**ssops-削除\<アダプター名\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="62012-265">Type **ssops -delete \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="62012-266">指定したアダプタが削除されます。</span><span class="sxs-lookup"><span data-stu-id="62012-266">The specified adapter will be deleted.</span></span>  
  
### <a name="to-enable-an-adapter"></a><span data-ttu-id="62012-267">アダプタを有効にするには</span><span class="sxs-lookup"><span data-stu-id="62012-267">To enable an adapter</span></span>  
  
1.  <span data-ttu-id="62012-268">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62012-268">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="62012-269">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="62012-269">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="62012-270">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="62012-270">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="62012-271">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="62012-271">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="62012-272">型**ssops-有効にする\<アダプター名\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="62012-272">Type **ssops -enable \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="62012-273">指定したアダプタが有効になります。</span><span class="sxs-lookup"><span data-stu-id="62012-273">The specified adapter will be enabled.</span></span>  
  
### <a name="to-disable-an-adapter"></a><span data-ttu-id="62012-274">アダプタを無効にするには</span><span class="sxs-lookup"><span data-stu-id="62012-274">To disable an adapter</span></span>  
  
1.  <span data-ttu-id="62012-275">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62012-275">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="62012-276">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="62012-276">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="62012-277">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="62012-277">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="62012-278">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="62012-278">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="62012-279">型**ssops-無効\<アダプター名\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="62012-279">Type **ssops -disable \<adapter name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="62012-280">指定したアダプタが無効になります。</span><span class="sxs-lookup"><span data-stu-id="62012-280">The specified adapter will be disabled.</span></span>  
  
### <a name="to-add-an-application-to-an-adapter"></a><span data-ttu-id="62012-281">アダプタにアプリケーションを追加するには</span><span class="sxs-lookup"><span data-stu-id="62012-281">To add an application to an adapter</span></span>  
  
1.  <span data-ttu-id="62012-282">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62012-282">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="62012-283">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="62012-283">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="62012-284">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="62012-284">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="62012-285">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="62012-285">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="62012-286">型**ssops-addapp\<アダプター名\>\<アプリケーション名\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="62012-286">Type **ssops -addapp \<adapter name\> \<application name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="62012-287">指定した SSO アプリケーションが、指定したアダプタに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="62012-287">The specified SSO application will be assigned to the specified adapter.</span></span> <span data-ttu-id="62012-288">つまり、そのアプリケーションでのマッピング用のパスワードは、このアダプタを使用して同期されます。</span><span class="sxs-lookup"><span data-stu-id="62012-288">This means that the passwords for the mappings in that application will now be synchronized using this adapter.</span></span>  
  
     <span data-ttu-id="62012-289">複数のアプリケーションを 1 つのアダプタに割り当てることができますが、特定のアプリケーションは 1 つのアダプタにしか割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="62012-289">While multiple applications can be assigned to one adapter, any given application can only be assigned to one adapter.</span></span>  
  
### <a name="to-delete-an-application-from-an-adapter"></a><span data-ttu-id="62012-290">アダプタからアプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="62012-290">To delete an application from an adapter</span></span>  
  
1.  <span data-ttu-id="62012-291">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62012-291">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="62012-292">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="62012-292">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="62012-293">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="62012-293">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="62012-294">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="62012-294">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="62012-295">型**ssops-deleteapp\<アプリケーション名\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="62012-295">Type **ssops -deleteapp \<application name\>** and press Enter.</span></span>  
  
     <span data-ttu-id="62012-296">指定した SSO アプリケーションはアダプターから削除されます </span><span class="sxs-lookup"><span data-stu-id="62012-296">The specified SSO application will be removed from an adapter.</span></span> <span data-ttu-id="62012-297">(アプリケーションは 1 つのアダプタにしか割り当てることができないので、アダプタ名を指定する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="62012-297">(Since an application can only be assigned to one adapter, it is not necessary to specify the adapter name.)</span></span>  
  
### <a name="to-reset-notification"></a><span data-ttu-id="62012-298">通知を再設定するには</span><span class="sxs-lookup"><span data-stu-id="62012-298">To reset notification</span></span>  
  
1.  <span data-ttu-id="62012-299">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62012-299">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="62012-300">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="62012-300">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="62012-301">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="62012-301">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="62012-302">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="62012-302">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="62012-303">型**ssops-リセット\<アダプター名 &#124; すべて &#124; 減衰\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="62012-303">Type **ssops -reset \<adapter name &#124; all &#124; damping\>** and press Enter.</span></span>  
  
     <span data-ttu-id="62012-304">このコマンドにより、1 つのアダプタまたはすべてのアダプタの抑制テーブルや通知キューが指定したとおりにクリアされます。</span><span class="sxs-lookup"><span data-stu-id="62012-304">This command clears the damping table and/or notification queues for a single adapter or all adapters, as specified.</span></span> <span data-ttu-id="62012-305">抑制テーブルには、パスワード変更の履歴が 10 分間格納されます。</span><span class="sxs-lookup"><span data-stu-id="62012-305">The damping table stores a 10-minute history of password changes.</span></span> <span data-ttu-id="62012-306">エンタープライズ SSO システムは、パスワード変更の受信または送信を行う前に、抑制テーブルを確認して、同じ変更が最近行われたかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="62012-306">Before the Enterprise SSO system accepts or sends a password change, it checks the damping table to see if it has performed the same change recently.</span></span> <span data-ttu-id="62012-307">同じ変更が行われていた場合は、新しい変更が破棄されます。</span><span class="sxs-lookup"><span data-stu-id="62012-307">If it has, the new change is discarded.</span></span>  
  
### <a name="to-add-an-adapter-to-an-adapter-group"></a><span data-ttu-id="62012-308">アダプタ グループにアダプタを追加するには</span><span class="sxs-lookup"><span data-stu-id="62012-308">To add an adapter to an adapter group</span></span>  
  
1.  <span data-ttu-id="62012-309">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62012-309">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="62012-310">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="62012-310">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="62012-311">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="62012-311">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="62012-312">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="62012-312">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="62012-313">型**ssops-addtogroup\<アダプター名\>\<アダプター グループ\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="62012-313">Type **ssops -addtogroup \<adapter name\> \<adapter group\>** and press Enter.</span></span>  
  
     <span data-ttu-id="62012-314">このコマンドにより、指定したアダプタが、指定したアダプタ グループに追加されます。</span><span class="sxs-lookup"><span data-stu-id="62012-314">This command adds the specified adapter to the specified adapter group.</span></span> <span data-ttu-id="62012-315">アダプタは 1 つのアダプタ グループにしか属すことができませんが、アダプタ グループには、複数のアダプタを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="62012-315">While an adapter can belong to only one adapter group, an adapter group can contain multiple adapters.</span></span>  
  
### <a name="to-delete-an-adapter-from-an-adapter-group"></a><span data-ttu-id="62012-316">アダプタ グループからアダプタを削除するには</span><span class="sxs-lookup"><span data-stu-id="62012-316">To delete an adapter from an adapter group</span></span>  
  
1.  <span data-ttu-id="62012-317">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62012-317">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="62012-318">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="62012-318">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="62012-319">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="62012-319">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="62012-320">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="62012-320">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="62012-321">型**ssops-deletefromgroup\<アダプター名\>\<アダプター グループ\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="62012-321">Type **ssops -deletefromgroup \<adapter name\> \<adapter group\>** and press Enter.</span></span>  
  
     <span data-ttu-id="62012-322">このコマンドにより、指定したアダプタが、指定したアダプタ グループから削除されます。</span><span class="sxs-lookup"><span data-stu-id="62012-322">This command deletes the specified adapter from the specified adapter group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62012-323">参照</span><span class="sxs-lookup"><span data-stu-id="62012-323">See Also</span></span>  
 [<span data-ttu-id="62012-324">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="62012-324">Password Synchronization</span></span>](../core/password-synchronization2.md)