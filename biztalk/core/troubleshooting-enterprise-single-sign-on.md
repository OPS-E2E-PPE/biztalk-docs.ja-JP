---
title: "エンタープライズ シングル サインオンのトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cb54af9f-a6ef-46c1-b987-2019cff3f837
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 952db36f794d36bd98af6e5bc31eee78adcc8a35
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-enterprise-single-sign-on"></a><span data-ttu-id="fd990-102">エンタープライズ シングル サインオンのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="fd990-102">Troubleshooting Enterprise Single Sign-On</span></span>
<span data-ttu-id="fd990-103">このトピックでは、エンタープライズ シングル サインオン (SSO) の使用中に発生する可能性のある一般的な問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="fd990-103">This topic describes information about common problems you may encounter while using Enterprise Single Sign-On (SSO).</span></span>  
  
 <span data-ttu-id="fd990-104">SSO 環境のトラブルシューティングを開始する際には、次の表の項目について順に実行し、すべてのコンポーネントが正常に動作していることを確認すると役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="fd990-104">As you begin to troubleshoot your SSO environment, it may be useful to walk through the items in the following table to ensure all components are working as expected:</span></span>  
  
|<span data-ttu-id="fd990-105">質問</span><span class="sxs-lookup"><span data-stu-id="fd990-105">Question</span></span>|<span data-ttu-id="fd990-106">コメント</span><span class="sxs-lookup"><span data-stu-id="fd990-106">Comments</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="fd990-107">アプリケーション イベント ログに SSO システムからのメッセージが記録されていないか。</span><span class="sxs-lookup"><span data-stu-id="fd990-107">Is there anything in the Application event log from the SSO system?</span></span>|<span data-ttu-id="fd990-108">イベント ログ内の SSO のメッセージは、SSO システムの問題を絞り込むのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fd990-108">The SSO messages in the event log can help you narrow down the problem in the SSO system.</span></span> <span data-ttu-id="fd990-109">SSO システムからのメッセージのソースは ENTSSO です。</span><span class="sxs-lookup"><span data-stu-id="fd990-109">The source of the messages from the SSO system is ENTSSO.</span></span> <span data-ttu-id="fd990-110">**重要:**エラーではなく、イベント ログに警告として表示 SSO エラーやイベントの多くです。</span><span class="sxs-lookup"><span data-stu-id="fd990-110">**Important:**  Many of the SSO errors and events appear as Warnings in the event log, not as Errors.</span></span> <span data-ttu-id="fd990-111">SSO システムでは、SSO サービスの単一クライアントにのみ影響する問題を警告として、SSO システム全体 (すべてのクライアント) に影響する問題をエラーとして生成します。</span><span class="sxs-lookup"><span data-stu-id="fd990-111">The SSO system generates a Warning when the problem affects a single client of the SSO service, whereas it generates Errors when the problem affects the entire SSO system (all clients).</span></span>|  
|<span data-ttu-id="fd990-112">SSO サービスが正常にインストールされているか。</span><span class="sxs-lookup"><span data-stu-id="fd990-112">Is the SSO service installed correctly?</span></span><br /><br /> <span data-ttu-id="fd990-113">正常に起動されるか。</span><span class="sxs-lookup"><span data-stu-id="fd990-113">Does it start as expected?</span></span><br /><br /> <span data-ttu-id="fd990-114">どのサービス アカウントが SSO サービスを実行しているか。</span><span class="sxs-lookup"><span data-stu-id="fd990-114">Under which service account is the SSO service running?</span></span>|<span data-ttu-id="fd990-115">SSO サービスが正常にインストールされていることと、SSO サービスのサービス アカウントが SSO 管理者グループのメンバーであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd990-115">Ensure the SSO service is correctly installed, and that the service account is member of the SSO administrators group.</span></span>|  
|<span data-ttu-id="fd990-116">SSO データベースはどこにあるか。</span><span class="sxs-lookup"><span data-stu-id="fd990-116">Where is the SSO database?</span></span>|<span data-ttu-id="fd990-117">コマンド ライン **ssoconfig -showdb**を使用してください。</span><span class="sxs-lookup"><span data-stu-id="fd990-117">Use the command line **ssoconfig -showdb**.</span></span> <span data-ttu-id="fd990-118">このコマンドの詳細については、次を参照してください。 [SSO データベース情報を表示する方法](../core/how-to-display-the-sso-database-information.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd990-118">For more information about this command, see [How to Display the SSO Database Information](../core/how-to-display-the-sso-database-information.md).</span></span>|  
|<span data-ttu-id="fd990-119">どの SSO サーバーが使用されているか。</span><span class="sxs-lookup"><span data-stu-id="fd990-119">Which SSO server is being used?</span></span>|<span data-ttu-id="fd990-120">コマンド ライン **ssomanage -showserver**を使用してください。</span><span class="sxs-lookup"><span data-stu-id="fd990-120">Use the command line **ssomanage -showserver**.</span></span> <span data-ttu-id="fd990-121">このコマンドの詳細については、次を参照してください。 [SSO サーバーを設定する方法](../core/how-to-set-the-sso-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd990-121">For more information about this command, see [How to Set the SSO Server](../core/how-to-set-the-sso-server.md).</span></span>|  
|<span data-ttu-id="fd990-122">SSO 管理者アカウントは何か。</span><span class="sxs-lookup"><span data-stu-id="fd990-122">What is the SSO Administrator account?</span></span>|<span data-ttu-id="fd990-123">コマンド ライン **ssomanage –displaydb**を使用してください。</span><span class="sxs-lookup"><span data-stu-id="fd990-123">Use the command line **ssomanage –displaydb**.</span></span> <span data-ttu-id="fd990-124">このコマンドの詳細については、次を参照してください。 [SSO データベース情報を表示する方法](../core/how-to-display-the-sso-database-information.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd990-124">For more information about this command, see [How to Display the SSO Database Information](../core/how-to-display-the-sso-database-information.md).</span></span>|  
|<span data-ttu-id="fd990-125">すべてが正しく有効化されているか。</span><span class="sxs-lookup"><span data-stu-id="fd990-125">Is everything correctly enabled?</span></span>|<span data-ttu-id="fd990-126">コマンド ライン **ssomanage –displaydb**を使用してください。</span><span class="sxs-lookup"><span data-stu-id="fd990-126">Use the command line **ssomanage –displaydb**.</span></span> <span data-ttu-id="fd990-127">このコマンドの詳細については、次を参照してください。 [SSO データベース情報を表示する方法](../core/how-to-display-the-sso-database-information.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd990-127">For more information about this command, see [How to Display the SSO Database Information](../core/how-to-display-the-sso-database-information.md).</span></span>|  
|<span data-ttu-id="fd990-128">関連アプリケーションはあるか。</span><span class="sxs-lookup"><span data-stu-id="fd990-128">Do the affiliate applications exist?</span></span>|<span data-ttu-id="fd990-129">コマンド ライン **ssomanage –listapps all**を使用してください。</span><span class="sxs-lookup"><span data-stu-id="fd990-129">Use the command line **ssomanage –listapps all**.</span></span> <span data-ttu-id="fd990-130">このコマンドの詳細については、次を参照してください。[関連アプリケーションの一覧を方法](../core/how-to-list-affiliate-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd990-130">For more information about this command, see [How to List Affiliate Applications](../core/how-to-list-affiliate-applications.md).</span></span>|  
|<span data-ttu-id="fd990-131">特定の関連アプリケーションが正常に実行されているか。</span><span class="sxs-lookup"><span data-stu-id="fd990-131">Does the specific affiliate application look correct?</span></span><br /><br /> <span data-ttu-id="fd990-132">どのアカウントがこの関連アプリケーションを使用しているか。</span><span class="sxs-lookup"><span data-stu-id="fd990-132">What accounts are using this affiliate application?</span></span>|<span data-ttu-id="fd990-133">コマンドラインを使用して**ssomanage – displayapp***\<アプリケーション名 >*です。</span><span class="sxs-lookup"><span data-stu-id="fd990-133">Use the command line **ssomanage –displayapp***\<application name>*.</span></span> <span data-ttu-id="fd990-134">このコマンドの詳細については、次を参照してください。[関連アプリケーションのプロパティを一覧表示する方法](../core/how-to-list-the-properties-of-an-affiliate-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd990-134">For more information about this command, see [How to List the Properties of an Affiliate Application](../core/how-to-list-the-properties-of-an-affiliate-application.md).</span></span>|  
|<span data-ttu-id="fd990-135">この関連アプリケーションにマッピングがあるか。</span><span class="sxs-lookup"><span data-stu-id="fd990-135">Are there any mappings for this affiliate application?</span></span>|<span data-ttu-id="fd990-136">コマンドラインを使用して**ssomanage – listmappings***\<アプリケーション名 >*です。</span><span class="sxs-lookup"><span data-stu-id="fd990-136">Use the command line **ssomanage –listmappings***\<application name>*.</span></span> <span data-ttu-id="fd990-137">このコマンドの詳細については、次を参照してください。[一覧のユーザーのマッピング方法](../core/how-to-list-user-mappings.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd990-137">For more information about this command, see [How to List User Mappings](../core/how-to-list-user-mappings.md).</span></span>|  
|<span data-ttu-id="fd990-138">どのアカウントが SSO グループのメンバーか。</span><span class="sxs-lookup"><span data-stu-id="fd990-138">What accounts are members of the SSO groups?</span></span>|<span data-ttu-id="fd990-139">すべての SSO グループとアカウントについてグループのメンバーシップを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd990-139">Verify the group membership for all SSO groups and accounts.</span></span>|  
|<span data-ttu-id="fd990-140">SSO サーバーの COM+ アプリケーションは正常に動作しているか。</span><span class="sxs-lookup"><span data-stu-id="fd990-140">Is the COM+ application for the SSO server running as expected?</span></span>|<span data-ttu-id="fd990-141">SSO サーバーの COM+ アプリケーションを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd990-141">Verify the COM+ application SSO server.</span></span> <span data-ttu-id="fd990-142">**注:**イベント メッセージと警告メッセージなど、詳細な情報についてイベント ログを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="fd990-142">**Note:**  You can also check the event log for detailed information, such as event and warning messages.</span></span>|  
  
## <a name="known-issues"></a><span data-ttu-id="fd990-143">既知の問題</span><span class="sxs-lookup"><span data-stu-id="fd990-143">Known Issues</span></span>  
  
#### <a name="entsso-service-fails-to-start"></a><span data-ttu-id="fd990-144">ENTSSO サービスを開始できない</span><span class="sxs-lookup"><span data-stu-id="fd990-144">ENTSSO Service Fails to Start</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="fd990-145">問題</span><span class="sxs-lookup"><span data-stu-id="fd990-145">Problem</span></span>  
 <span data-ttu-id="fd990-146">ENTSSO サービスを開始できません。</span><span class="sxs-lookup"><span data-stu-id="fd990-146">The ENTSSO service fails to start.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="fd990-147">原因</span><span class="sxs-lookup"><span data-stu-id="fd990-147">Cause</span></span>  
 <span data-ttu-id="fd990-148">ENTSSO サービスが有効な SSO 管理者アカウントで実行されていない場合、サービスを開始できません。</span><span class="sxs-lookup"><span data-stu-id="fd990-148">If the ENTSSO service is not running under a valid SSO Administrator account, it will fail to start.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="fd990-149">解決策</span><span class="sxs-lookup"><span data-stu-id="fd990-149">Resolution</span></span>  
 <span data-ttu-id="fd990-150">有効な SSO 管理者アカウントを ENTSSO サービスに指定して、サービス コントロール マネージャー (SCM) スナップインからサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="fd990-150">Specify a valid SSO administrator account for the ENTSSO Service and restart the service from Services Control Manager (SCM) snap-in.</span></span>  
  
#### <a name="biztalk-services-dependent-on-the-enterprise-single-sign-on-service-entsso-fail-to-start-after-a-reboot"></a><span data-ttu-id="fd990-151">エンタープライズ シングル サインオン (ENTSSO) サービスに依存する BizTalk サービスが、再起動後に起動しない</span><span class="sxs-lookup"><span data-stu-id="fd990-151">BizTalk Services Dependent on the Enterprise Single Sign-On Service (ENTSSO) fail to start after a reboot</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="fd990-152">問題</span><span class="sxs-lookup"><span data-stu-id="fd990-152">Problem</span></span>  
 <span data-ttu-id="fd990-153">BTSSvc$BizTalkServerApplication はエンタープライズ シングル サインオン サービス (ENTSSO) と依存関係があり、リブート後の起動中にタイムアウトすることがあります。</span><span class="sxs-lookup"><span data-stu-id="fd990-153">BTSSvc$BizTalkServerApplication has a dependency on the Enterprise Single Sign-On Service (ENTSSO) and may timeout during start up after a reboot.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="fd990-154">原因</span><span class="sxs-lookup"><span data-stu-id="fd990-154">Cause</span></span>  
 <span data-ttu-id="fd990-155">エンタープライズ シングル サインオン サービスは、起動に約 3 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fd990-155">The Enterprise Single Sign-On Service may take around 3 minutes to start.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="fd990-156">解決策</span><span class="sxs-lookup"><span data-stu-id="fd990-156">Resolution</span></span>  
 <span data-ttu-id="fd990-157">"BizTalk Service BizTalk グループ: BizTalkServerApplication" サービスを、スタートアップ オプションの種類を [自動 (遅延スタート)] として構成します。</span><span class="sxs-lookup"><span data-stu-id="fd990-157">Configure the “BizTalk Service BizTalk Group: BizTalkServerApplication” service with the Automatic (Delayed Start) startup type option.</span></span> <span data-ttu-id="fd990-158">これにより、すべての自動サービスのスタートアップ ルーチン完了後に、このサービスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="fd990-158">This will initiate the start of the service after all Automatic services have completed their startup routines.</span></span>  
  
#### <a name="cannot-access-an-affiliate-application"></a><span data-ttu-id="fd990-159">関連アプリケーションにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="fd990-159">Cannot Access an Affiliate Application</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="fd990-160">問題</span><span class="sxs-lookup"><span data-stu-id="fd990-160">Problem</span></span>  
 <span data-ttu-id="fd990-161">関連するアプリケーションの管理者アカウントが有効でない場合、エンタープライズ シングル サインオン サービスはこの関連アプリケーションを無効にします。</span><span class="sxs-lookup"><span data-stu-id="fd990-161">The Enterprise Single Sign-On service disables an affiliate application if the application administrator account associated with it is not valid.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="fd990-162">原因</span><span class="sxs-lookup"><span data-stu-id="fd990-162">Cause</span></span>  
 <span data-ttu-id="fd990-163">SSO アプリケーションの管理者アカウントが無効です。</span><span class="sxs-lookup"><span data-stu-id="fd990-163">The SSO application administrator account is not valid.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="fd990-164">解決策</span><span class="sxs-lookup"><span data-stu-id="fd990-164">Resolution</span></span>  
 <span data-ttu-id="fd990-165">関連アプリケーションを作成する前に、SSO アプリケーションの管理者アカウントが有効なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd990-165">Ensure that the SSO application administrator account is valid before you create an affiliate application.</span></span> <span data-ttu-id="fd990-166">関連アプリケーションを使用するには、そのアプリケーションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd990-166">You must then enable the affiliate application to use the application.</span></span>  
  
#### <a name="rpc-error-occurs-when-connecting-to-a-client-computer"></a><span data-ttu-id="fd990-167">クライアント コンピューターへの接続時に RPC エラーが発生する</span><span class="sxs-lookup"><span data-stu-id="fd990-167">RPC Error Occurs When Connecting to a Client Computer</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="fd990-168">問題</span><span class="sxs-lookup"><span data-stu-id="fd990-168">Problem</span></span>  
 <span data-ttu-id="fd990-169">ときにコマンドを実行するユーザーなど**ssomanage-displayapp***\<applicationname >*コンピューター、情報を取得するリモート SSO サーバーに接続しようとしましたここで、受信します。。次のエラー: エラー: 0x800706BA: RPC サーバーは使用できません。</span><span class="sxs-lookup"><span data-stu-id="fd990-169">When a user runs a command such as **ssomanage -displayapp***\<applicationname>*, where the computer attempt to connect to a remote SSO Server to retrieve the information, they receive the following error: ERROR: 0x800706BA: The RPC server is unavailable.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="fd990-170">原因</span><span class="sxs-lookup"><span data-stu-id="fd990-170">Cause</span></span>  
 <span data-ttu-id="fd990-171">このエラーは、ユーザーが間違ったサーバー情報を指定した場合、またはリモート サーバーで SSO サービスを利用できない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="fd990-171">This error occurs when the user specifies the wrong server information, or when the SSO Service is not available on the remote server.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="fd990-172">解決策</span><span class="sxs-lookup"><span data-stu-id="fd990-172">Resolution</span></span>  
  
-   <span data-ttu-id="fd990-173">手順に従います[SSO サーバーを設定する方法](../core/how-to-set-the-sso-server.md)正しい SSO サーバーに接続しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd990-173">Follow the steps in [How to Set the SSO Server](../core/how-to-set-the-sso-server.md) to make sure you are connected to the correct SSO Server.</span></span>  
  
-   <span data-ttu-id="fd990-174">接続先の SSO サーバーで SSO サービスが有効になっており、実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd990-174">Make sure the SSO Service is enabled and running in the SSO Server to which you are connecting.</span></span>  
  
#### <a name="master-secret-is-missing-or-corrupt"></a><span data-ttu-id="fd990-175">マスター シークレットがない、または破損している</span><span class="sxs-lookup"><span data-stu-id="fd990-175">Master Secret Is Missing or Corrupt</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="fd990-176">問題</span><span class="sxs-lookup"><span data-stu-id="fd990-176">Problem</span></span>  
 <span data-ttu-id="fd990-177">マスター シークレットがない、または破損しています。</span><span class="sxs-lookup"><span data-stu-id="fd990-177">The master secret is missing or corrupt.</span></span> <span data-ttu-id="fd990-178">この問題は、主に構成中に発生します。</span><span class="sxs-lookup"><span data-stu-id="fd990-178">It normally generates during configuration.</span></span> <span data-ttu-id="fd990-179">シークレットがない場合、エンタープライズ シングル サインオン サービスが開始されるときに、以下のいずれかのメッセージがイベント ログに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd990-179">If the secret is missing, one of the following messages will display in the event log as the Enterprise Single Sign-On service starts.</span></span>  
  
 <span data-ttu-id="fd990-180">MessageId=10520</span><span class="sxs-lookup"><span data-stu-id="fd990-180">MessageId=10520</span></span>  
  
 <span data-ttu-id="fd990-181">Severity=Warning</span><span class="sxs-lookup"><span data-stu-id="fd990-181">Severity=Warning</span></span>  
  
 <span data-ttu-id="fd990-182">SSO_WARN_NO_SECRETS</span><span class="sxs-lookup"><span data-stu-id="fd990-182">SSO_WARN_NO_SECRETS</span></span>  
  
 <span data-ttu-id="fd990-183">MessageId=10565</span><span class="sxs-lookup"><span data-stu-id="fd990-183">MessageId=10565</span></span>  
  
 <span data-ttu-id="fd990-184">Severity=Error</span><span class="sxs-lookup"><span data-stu-id="fd990-184">Severity=Error</span></span>  
  
 <span data-ttu-id="fd990-185">SSO_ERROR_SECRET_VALIDATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="fd990-185">SSO_ERROR_SECRET_VALIDATE_FAILED</span></span>  
  
 <span data-ttu-id="fd990-186">MessageId=10521</span><span class="sxs-lookup"><span data-stu-id="fd990-186">MessageId=10521</span></span>  
  
 <span data-ttu-id="fd990-187">Severity=Error</span><span class="sxs-lookup"><span data-stu-id="fd990-187">Severity=Error</span></span>  
  
 <span data-ttu-id="fd990-188">SSO_ERROR_SECRETS_NOT_LOADED</span><span class="sxs-lookup"><span data-stu-id="fd990-188">SSO_ERROR_SECRETS_NOT_LOADED</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="fd990-189">原因</span><span class="sxs-lookup"><span data-stu-id="fd990-189">Cause</span></span>  
 <span data-ttu-id="fd990-190">この問題は、あるサービス アカウントでエンタープライズ シングル サインオン サービス (SSO) を実行中にシークレットを生成した後で、サービス アカウントが変更された場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fd990-190">This problem can occur if a secret is generated while the Enterprise Single Sign-On service (SSO) was running under one service account, and then the service account was changed.</span></span> <span data-ttu-id="fd990-191">シークレットは、暗号化された形式でレジストリに保存されます。暗号化には、(ENTSSO を実行する) サービス アカウントの ID を基にしたキーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="fd990-191">The secret is stored in the registry in encrypted form, and is encrypted using a key based on the identity of the service account (which ENTSSO runs under).</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="fd990-192">解決策</span><span class="sxs-lookup"><span data-stu-id="fd990-192">Resolution</span></span>  
 <span data-ttu-id="fd990-193">ENTSSO を実行しているサービス アカウントを、マスター シークレット作成時の元のサービス アカウントに変更します。</span><span class="sxs-lookup"><span data-stu-id="fd990-193">Change the service account ENTSSO is running under to the original service account when the master secret was created.</span></span>  
  
 <span data-ttu-id="fd990-194">ENTSSO サービス アカウントを変更するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fd990-194">To change the ENTSSO service account:</span></span>  
  
1.  <span data-ttu-id="fd990-195">マスター シークレットをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="fd990-195">Back up the master secret.</span></span> <span data-ttu-id="fd990-196">詳細については、次を参照してください。[バックアップ マスター シークレットを方法](../core/how-to-back-up-the-master-secret.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd990-196">For more information, see [How to Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md).</span></span>  
  
2.  <span data-ttu-id="fd990-197">エンタープライズ シングル サインオン サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="fd990-197">Stop Enterprise Single Sign-On Services.</span></span>  
  
3.  <span data-ttu-id="fd990-198">サービス アカウントを変更します。</span><span class="sxs-lookup"><span data-stu-id="fd990-198">Change the service account.</span></span>  
  
4.  <span data-ttu-id="fd990-199">SSO を再起動します。破損したシークレットに関するイベント ログのエラーは一切無視します。</span><span class="sxs-lookup"><span data-stu-id="fd990-199">Restart SSO and ignore any event log errors about a corrupted secret.</span></span>  
  
5.  <span data-ttu-id="fd990-200">マスター シークレットを復元します。</span><span class="sxs-lookup"><span data-stu-id="fd990-200">Restore the master secret.</span></span> <span data-ttu-id="fd990-201">詳細については、次を参照してください。[マスター シークレットを復元する方法](../core/how-to-restore-the-master-secret.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd990-201">For more information, see [How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd990-202">参照</span><span class="sxs-lookup"><span data-stu-id="fd990-202">See Also</span></span>  
 [<span data-ttu-id="fd990-203">エンタープライズ シングル サインオンを実装します。</span><span class="sxs-lookup"><span data-stu-id="fd990-203">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)