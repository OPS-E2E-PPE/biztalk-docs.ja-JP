---
title: データベース コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60c54131-0793-45a9-822a-554cd4fc05a2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5bb9d25db876fb7d48900b1ee47f187544a4b87
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389772"
---
# <a name="database-commands"></a><span data-ttu-id="0fa9a-102">データベース コマンド</span><span class="sxs-lookup"><span data-stu-id="0fa9a-102">Database Commands</span></span>
<span data-ttu-id="0fa9a-103">BAM 管理ユーティリティのデータベース コマンドを使用して、BAM データベースを操作できます。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-103">The BAM Management utility database commands allow you to work with the BAM databases:</span></span>  
  
-   <span data-ttu-id="0fa9a-104">セットアップ-データベース:特定の BAM データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-104">setup-databases: Creates the BAM-specific databases.</span></span>  
  
-   <span data-ttu-id="0fa9a-105">移行-sql:BAM データベースを移行します。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-105">migrate-sql: Migrates your BAM databases from:</span></span>  
  
    -   <span data-ttu-id="0fa9a-106">Microsoft SQL Server 2008 への Microsoft SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="0fa9a-106">Microsoft SQL Server 2000 to Microsoft SQL Server 2008</span></span>  
  
    -   <span data-ttu-id="0fa9a-107">Microsoft SQL Server 2008 への Microsoft SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="0fa9a-107">Microsoft SQL Server 2005 to Microsoft SQL Server 2008</span></span>  
  
-   <span data-ttu-id="0fa9a-108">参照の有効化:分散 BAM プライマリ インポート データベースへの参照を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-108">enable-reference: Enables a reference to a distributed BAM Primary Import database.</span></span>  
  
-   <span data-ttu-id="0fa9a-109">get 参照:分散 BAM プライマリ インポート データベースへの参照の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-109">get-references: Gets a list of references to distributed BAM Primary Import databases.</span></span>  
  
-   <span data-ttu-id="0fa9a-110">参照の無効化:BAM プライマリ インポート データベースへの参照を無効にします。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-110">disable-reference: Disables a reference to a BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fa9a-111">含めることによって任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: &#124;オフ**パラメーター スイッチ。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-111">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="0fa9a-112">トレース スイッチを使用するには、構成ファイルのトレース設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-112">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="0fa9a-113">スイッチは、通常の BM コマンドと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-113">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fa9a-114">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-114">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="setup-databases-command"></a><span data-ttu-id="0fa9a-115">setup-databases コマンド</span><span class="sxs-lookup"><span data-stu-id="0fa9a-115">setup-databases Command</span></span>  
 <span data-ttu-id="0fa9a-116">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-116">**Usage**</span></span>  
  
 <span data-ttu-id="0fa9a-117">**bm.exe setup-databases-ConfigFile:\<configuration file\>[ -NSUser:\<notifications service user name\> ][ -NSUserPassword:\<notifications service user password\> ]**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-117">**bm.exe setup-databases-ConfigFile:\<configuration file\>[ -NSUser:\<notifications service user name\> ][ -NSUserPassword:\<notifications service user password\> ]**</span></span>  
  
 <span data-ttu-id="0fa9a-118">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-118">**Parameters**</span></span>  
  
|<span data-ttu-id="0fa9a-119">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0fa9a-119">Parameter</span></span>|<span data-ttu-id="0fa9a-120">説明</span><span class="sxs-lookup"><span data-stu-id="0fa9a-120">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0fa9a-121">ConfigFile:\<構成ファイル\></span><span class="sxs-lookup"><span data-stu-id="0fa9a-121">ConfigFile:\<configuration file\></span></span>|<span data-ttu-id="0fa9a-122">データベースを作成するための BAM 構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-122">The BAM configuration file from which to create the database.</span></span>|  
|<span data-ttu-id="0fa9a-123">NSUser:\<通知サービスのユーザー名\></span><span class="sxs-lookup"><span data-stu-id="0fa9a-123">NSUser:\<notifications service user name\></span></span>|<span data-ttu-id="0fa9a-124">省略可能:データベースを作成するアクセス許可を持つ notification services ユーザーのユーザー ID。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-124">Optional: The user ID of a notifications services user with permissions to create databases.</span></span>|  
|<span data-ttu-id="0fa9a-125">NSUserPassword</span><span class="sxs-lookup"><span data-stu-id="0fa9a-125">NSUserPassword</span></span>|<span data-ttu-id="0fa9a-126">省略可能:指定した通知サービスのユーザーのパスワード。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-126">Optional: The password for the specified notifications services user.</span></span>|  
  
 <span data-ttu-id="0fa9a-127">まだ存在しない場合、構成ファイル (BAM プライマリ インポート、BAM スター スキーマ、BAM アーカイブ、BAM 分析、およびアラート) で説明されているデータベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-127">Creates the databases described in the configuration file (BAM Primary Import, BAM Star Schema, BAM Archive, BAM Analysis, and alerts) if they do not already exist.</span></span> <span data-ttu-id="0fa9a-128">データベースが作成されると、コマンドは、関連する BAM メタデータ テーブルおよびストアド プロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-128">Once the databases are created, the command creates the associated BAM metadata tables and stored procedures.</span></span>  
  
 <span data-ttu-id="0fa9a-129">BAM 警告を設定している場合、NSUser および NSUserPassword パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-129">The NSUser and NSUserPassword parameters are required if you are setting up BAM alerts.</span></span> <span data-ttu-id="0fa9a-130">コマンドラインで NSUserPassword を指定しない場合は、bm.exe はパスワードを求めます。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-130">If the NSUserPassword is not specified on the command line, bm.exe prompts you for the password.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fa9a-131">コマンドの完了後に、トレース ログに alertmodule によって、例外を確認してください可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-131">After the completion of the command, you may note an exception from the AlertModule in the trace log:</span></span>  
>   
>  <span data-ttu-id="0fa9a-132">"指定されたアカウントは、データベース所有者です。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-132">"The specified account is the Database Owner.</span></span> <span data-ttu-id="0fa9a-133">データベース所有者常にビューにアクセスして追加をまたはできませんビューから削除します。"</span><span class="sxs-lookup"><span data-stu-id="0fa9a-133">The Database owner always has access to the view and cannot be added to or removed from the view."</span></span>  
>   
>  <span data-ttu-id="0fa9a-134">さらに、#19001 により #19001 からのイベントで警告が表示することがあります。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-134">In addition, you may see a warning in the event from NotificationServices #19001.</span></span>  
>   
>  <span data-ttu-id="0fa9a-135">コマンドの実行中にエラーが報告されていない場合は、これらの通知を安全に無視できます。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-135">If no errors were reported during the execution of the command, you can safely disregard these notices.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0fa9a-136">セットアップ データベース コマンドを実行する、[アラート] セクションを含まない BAM 構成ファイルを使用して BAM 警告を構成済みである場合は、アラートが機能しなくなりますように bm.exe は構成を上書きします。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-136">If you execute a setup-database command, using a BAM configuration file that does not contain an alerts section, and you have already configured BAM Alerts, bm.exe will overwrite the configuration such that alerts will no longer function.</span></span>  
  
 <span data-ttu-id="0fa9a-137">BAM データベースを設定するには、BAMPrimaryImport、bamstarschema データベース、および BAMArchive データベースをホストする Microsoft SQL server の管理者のアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-137">To set up the BAM databases you must have administrator permissions on the Microsoft SQL server hosting the BAMPrimaryImport, BAMStarSchema, and BAMArchive databases.</span></span> <span data-ttu-id="0fa9a-138">SQL Notification Services データベースを設定するにする必要があります管理者権限し、ローカルの administrators グループのメンバーであるだけでなく、他の管理者グループ、BTS Admins グループなど、構成されているのメンバーであります。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-138">To set up SQL Notification Services databases, you must have administrator permissions and be a member of the local administrators group, as well as be a member of any other additional administrative groups that have been configured, such as the BTS Admins group.</span></span>  
  
 <span data-ttu-id="0fa9a-139">**使用例**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-139">**Examples**</span></span>  
  
```  
bm.exe setup-databases -ConfigFile:BamConfiguration.xml  
bm.exe setup-databases -ConfigFile:cfg.xml -NSUser:domain\user1  
```  
  
## <a name="migrate-sql-command"></a><span data-ttu-id="0fa9a-140">migrate-sql コマンド</span><span class="sxs-lookup"><span data-stu-id="0fa9a-140">migrate-sql Command</span></span>  
 <span data-ttu-id="0fa9a-141">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-141">**Usage**</span></span>  
  
 <span data-ttu-id="0fa9a-142">**bm.exe-から: sql2000-を: sql2008 [- NSUser:\<通知サービスのユーザー名\>] [- NSUserPassword:\<通知サービスのユーザー パスワード\>] [-サーバー:\<server\>] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-142">**bm.exe migrate-sql -From:sql2000 -To:sql2008 [ -NSUser:\<notifications service user name\> ][ -NSUserPassword:\<notifications service user password\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="0fa9a-143">\- または -</span><span class="sxs-lookup"><span data-stu-id="0fa9a-143">\- Or -</span></span>  
  
 <span data-ttu-id="0fa9a-144">**bm.exe-から: sql2005-を: sql2008 [- NSUser:\<通知サービスのユーザー名\>] [- NSUserPassword:\<通知サービスのユーザー パスワード\>] [-サーバー:\<server\>] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-144">**bm.exe migrate-sql -From:sql2005 -To:sql2008 [ -NSUser:\<notifications service user name\> ][ -NSUserPassword:\<notifications service user password\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="0fa9a-145">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-145">**Parameters**</span></span>  
  
|<span data-ttu-id="0fa9a-146">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0fa9a-146">Parameter</span></span>|<span data-ttu-id="0fa9a-147">説明</span><span class="sxs-lookup"><span data-stu-id="0fa9a-147">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0fa9a-148">: Sql2000</span><span class="sxs-lookup"><span data-stu-id="0fa9a-148">From: sql2000</span></span>|<span data-ttu-id="0fa9a-149">Microsoft SQL Server 2000 データベースから変換することを指定します。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-149">Specifies that you are converting from a Microsoft SQL Server 2000 database.</span></span>|  
|<span data-ttu-id="0fa9a-150">: Sql2008</span><span class="sxs-lookup"><span data-stu-id="0fa9a-150">To:sql2008</span></span>|<span data-ttu-id="0fa9a-151">Microsoft SQL Server 2008 データベースに変換することを指定します。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-151">Specifies that you are converting to a Microsoft SQL Server 2008 database.</span></span>|  
|<span data-ttu-id="0fa9a-152">: Sql2005</span><span class="sxs-lookup"><span data-stu-id="0fa9a-152">From: sql2005</span></span>|<span data-ttu-id="0fa9a-153">Microsoft SQL Server 2005 データベースから変換することを指定します。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-153">Specifies that you are converting from a Microsoft SQL Server 2005 database.</span></span>|  
|<span data-ttu-id="0fa9a-154">: Sql2008</span><span class="sxs-lookup"><span data-stu-id="0fa9a-154">To:sql2008</span></span>|<span data-ttu-id="0fa9a-155">Microsoft SQL Server 2008 データベースに変換することを指定します。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-155">Specifies that you are converting to a Microsoft SQL Server 2008 database.</span></span>|  
|<span data-ttu-id="0fa9a-156">NSUser:\<通知サービスのユーザー名\></span><span class="sxs-lookup"><span data-stu-id="0fa9a-156">NSUser:\<notifications service user name\></span></span>|<span data-ttu-id="0fa9a-157">省略可能:データベースを作成する権限を持つ Notification Services ユーザーのユーザー ID。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-157">Optional: The user ID of a Notifications Services user with permissions to create databases.</span></span>|  
|<span data-ttu-id="0fa9a-158">NSUserPassword</span><span class="sxs-lookup"><span data-stu-id="0fa9a-158">NSUserPassword</span></span>|<span data-ttu-id="0fa9a-159">省略可能:指定した Notification Services ユーザーのパスワードです。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-159">Optional: The password for the specified Notifications Services user.</span></span>|  
|<span data-ttu-id="0fa9a-160">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="0fa9a-160">Server:\<server\></span></span>|<span data-ttu-id="0fa9a-161">省略可能:変換されたデータベースが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-161">Optional: The name of the server on which the converted database will reside.</span></span> <span data-ttu-id="0fa9a-162">Microsoft SQL Server 2008 データベースをホストするコンピューターと同じドメイン内、サーバーがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-162">The server must be in the same domain as the computer hosting the Microsoft SQL Server 2008 database.</span></span> <span data-ttu-id="0fa9a-163">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-163">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="0fa9a-164">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="0fa9a-164">Database:\<database\></span></span>|<span data-ttu-id="0fa9a-165">省略可能:クリックし、変換されたデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-165">Optional: Then name of the converted database.</span></span> <span data-ttu-id="0fa9a-166">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-166">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="0fa9a-167">Microsoft SQL Server 2000 または Microsoft SQL Server 2005 から BAM インフラストラクチャを Microsoft SQL Server 2008 に移行します。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-167">Migrates the BAM infrastructure from Microsoft SQL Server 2000 or Microsoft SQL Server 2005 to Microsoft SQL Server 2008.</span></span> <span data-ttu-id="0fa9a-168">Microsoft SQL Server 2000 または Microsoft SQL Server 2005 から Microsoft SQL Server 2008 に、データベース サーバーおよび分析サーバーをアップグレードした後は、このコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-168">Use this command after you upgrade your database server and Analysis server from Microsoft SQL Server 2000 or Microsoft SQL Server 2005 to Microsoft SQL Server 2008.</span></span>  
  
 <span data-ttu-id="0fa9a-169">BAM 警告が構成されている場合、NSUser および NSUserPassword パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-169">The NSUser and NSUserPassword parameters are required if BAM alerts are configured.</span></span> <span data-ttu-id="0fa9a-170">コマンドラインで NSUserPassword を指定しない場合は、bm.exe はパスワードを求めます。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-170">If the NSUserPassword is not specified on the command line, bm.exe prompts you for the password.</span></span>  
  
 <span data-ttu-id="0fa9a-171">SQL Server Notification Services データベースを移行する必要があります管理者権限し、ローカルの administrators グループのメンバーであるだけでなく、他の管理者グループ、BTS など、構成されているのメンバーであります。管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-171">To migrate the SQL Server Notification Services databases, you must have administrator permissions and be a member of the local administrators group, as well as be a member of any other additional administrative groups that have been configured, such as the BTS Admins group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fa9a-172">エラー メッセージを受信する場合は、"エラー。コンピューターで NS$ BAMAlerts サービスを開始できません '\<コンピューター名\>'。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-172">If you receive the error message "ERROR: Cannot start service NS$BAMAlerts on computer '\<computer name\>'.</span></span> <span data-ttu-id="0fa9a-173">サービスが適切な方法で開始または制御要求に応答しませんでした"、サービスを手動で再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-173">The service did not respond to the start or control request in a timely fashion.", try restarting the service manually.</span></span> <span data-ttu-id="0fa9a-174">SQL サーバーが移行中に極端なビジー状態である場合、サービスが再起動しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-174">If the SQL Server is extremely busy during a migration, the service may not restart.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fa9a-175">Notification Services がインストールされているコンピューターで migrate-sql コマンドを実行する方法には、そのコンピューターのローカルの Administrators グループに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-175">To run the migrate-sql command on the computer where Notification Services is installed, you must belong to the Local Administrators group on that computer.</span></span>  
  
 <span data-ttu-id="0fa9a-176">**使用例**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-176">**Examples**</span></span>  
  
```  
bm.exe migrate-sql -From:sql2000 -To:sql2008 -NSUser:domain\user1  
bm.exe migrate-sql -From:sql2000 -To:sql2008 -Server:MyServer -Database:db1  
```  
  
```  
bm.exe migrate-sql -From:sql2005 -To:sql2008 -NSUser:domain\user1  
bm.exe migrate-sql -From:sql2005 -To:sql2008 -Server:MyServer -Database:db1  
```  
  
## <a name="enable-reference-command"></a><span data-ttu-id="0fa9a-177">enable-reference コマンド</span><span class="sxs-lookup"><span data-stu-id="0fa9a-177">enable-reference Command</span></span>  
 <span data-ttu-id="0fa9a-178">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-178">**Usage**</span></span>  
  
 <span data-ttu-id="0fa9a-179">**bm.exe enable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-179">**bm.exe enable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="0fa9a-180">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-180">**Parameters**</span></span>  
  
|<span data-ttu-id="0fa9a-181">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0fa9a-181">Parameter</span></span>|<span data-ttu-id="0fa9a-182">説明</span><span class="sxs-lookup"><span data-stu-id="0fa9a-182">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0fa9a-183">TargetServer:\<ターゲット サーバー\></span><span class="sxs-lookup"><span data-stu-id="0fa9a-183">TargetServer:\<target server\></span></span>|<span data-ttu-id="0fa9a-184">参照を有効にするサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-184">The name of the server to which the reference is enabled.</span></span> <span data-ttu-id="0fa9a-185">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-185">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="0fa9a-186">TargetDatabase:\<ターゲット データベース\></span><span class="sxs-lookup"><span data-stu-id="0fa9a-186">TargetDatabase:\<target database\></span></span>|<span data-ttu-id="0fa9a-187">参照を有効にするデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-187">The name of the database to which the reference is enabled.</span></span>|  
|<span data-ttu-id="0fa9a-188">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="0fa9a-188">Server:\<server\></span></span>|<span data-ttu-id="0fa9a-189">省略可能:ターゲット サーバーとデータベースへの参照を有効にする必要がありますサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-189">Optional: The name of the server which will have a reference enabled to the target server and database.</span></span> <span data-ttu-id="0fa9a-190">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-190">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="0fa9a-191">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="0fa9a-191">Database:\<database\></span></span>|<span data-ttu-id="0fa9a-192">省略可能:ターゲット サーバーとデータベースへの参照を有効にする必要がありますデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-192">Optional: The name of the database which will have a reference enabled to the target server and database.</span></span> <span data-ttu-id="0fa9a-193">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-193">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="0fa9a-194">別の分散 BAM プライマリ インポート データベースへの参照を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-194">Enables a reference to another distributed BAM Primary Import database.</span></span> <span data-ttu-id="0fa9a-195">これにより、ビューやアクティビティのメタデータを現在のデータベースからのサブスクリプションが、ターゲットの BAM プライマリ インポート データベースにできます。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-195">This allows subscriptions from the current database to the view and activity metadata on the target BAM Primary Import database.</span></span> <span data-ttu-id="0fa9a-196">これを使用するには分散アクティビティのナビゲーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-196">You use this to enable navigation of the distributed activities.</span></span>  
  
 <span data-ttu-id="0fa9a-197">ターゲット サーバーは、SQL Server、たとえば、'mymachine2\myinstance' のインスタンスとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-197">You can specify the target server as an instance of SQL Server, for example, 'mymachine2\myinstance'.</span></span>  
  
 <span data-ttu-id="0fa9a-198">**使用例**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-198">**Examples**</span></span>  
  
```  
bm.exe enable-reference -TargetServer:MySrv -TargetDatabase:BamPrimaryImport  
bm.exe enable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="get-references-command"></a><span data-ttu-id="0fa9a-199">get-references コマンド</span><span class="sxs-lookup"><span data-stu-id="0fa9a-199">get-references Command</span></span>  
 <span data-ttu-id="0fa9a-200">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-200">**Usage**</span></span>  
  
 <span data-ttu-id="0fa9a-201">**bm.exe の get 参照 [-サーバー:\<server\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-201">**bm.exe get-references [ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="0fa9a-202">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-202">**Parameters**</span></span>  
  
|<span data-ttu-id="0fa9a-203">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0fa9a-203">Parameter</span></span>|<span data-ttu-id="0fa9a-204">説明</span><span class="sxs-lookup"><span data-stu-id="0fa9a-204">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0fa9a-205">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="0fa9a-205">Server:\<server\></span></span>|<span data-ttu-id="0fa9a-206">省略可能:参照の一覧を取得するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-206">Optional: The name of the server on which to get a list of references.</span></span> <span data-ttu-id="0fa9a-207">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-207">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="0fa9a-208">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-208">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="0fa9a-209">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="0fa9a-209">Database:\<database\></span></span>|<span data-ttu-id="0fa9a-210">省略可能:参照の一覧を取得する対象のデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-210">Optional: The name of the database on which to get a list of references.</span></span> <span data-ttu-id="0fa9a-211">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-211">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="0fa9a-212">コマンドを実行するコンピューターで有効になっている参照を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-212">Lists the references enabled on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="0fa9a-213">**使用例**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-213">**Examples**</span></span>  
  
```  
bm.exe get-references  
bm.exe get-references -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="disable-reference-command"></a><span data-ttu-id="0fa9a-214">disable-reference コマンド</span><span class="sxs-lookup"><span data-stu-id="0fa9a-214">disable-reference Command</span></span>  
 <span data-ttu-id="0fa9a-215">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-215">**Usage**</span></span>  
  
 <span data-ttu-id="0fa9a-216">**bm.exe disable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-216">**bm.exe disable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="0fa9a-217">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-217">**Parameters**</span></span>  
  
|<span data-ttu-id="0fa9a-218">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0fa9a-218">Parameter</span></span>|<span data-ttu-id="0fa9a-219">説明</span><span class="sxs-lookup"><span data-stu-id="0fa9a-219">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0fa9a-220">TargetServer:\<ターゲット サーバー\></span><span class="sxs-lookup"><span data-stu-id="0fa9a-220">TargetServer:\<target server\></span></span>|<span data-ttu-id="0fa9a-221">参照を無効にするサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-221">The name of the server on which to disable the references.</span></span> <span data-ttu-id="0fa9a-222">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-222">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="0fa9a-223">TargetDatabase:\<ターゲット データベース\></span><span class="sxs-lookup"><span data-stu-id="0fa9a-223">TargetDatabase:\<target database\></span></span>|<span data-ttu-id="0fa9a-224">参照を無効にするデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-224">The name of the database on which to disable the references.</span></span>|  
|<span data-ttu-id="0fa9a-225">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="0fa9a-225">Server:\<server\></span></span>|<span data-ttu-id="0fa9a-226">省略可能:サーバーとデータベースで無効にするが、ターゲットへの参照、サーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-226">Optional: The name of the server on which references to the target server and database are to be disabled.</span></span> <span data-ttu-id="0fa9a-227">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-227">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="0fa9a-228">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-228">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="0fa9a-229">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="0fa9a-229">Database:\<database\></span></span>|<span data-ttu-id="0fa9a-230">省略可能:サーバーとデータベースで無効にするが、ターゲットへの参照データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-230">Optional: The name of the database on which references to the target server and database are to be disabled.</span></span> <span data-ttu-id="0fa9a-231">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-231">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="0fa9a-232">ターゲット サーバー上の別の分散 BAM プライマリ インポート データベースへの参照を無効にします。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-232">Disables a reference to another distributed BAM Primary Import database on the target server.</span></span>  
  
 <span data-ttu-id="0fa9a-233">ターゲット サーバーは、SQL Server、たとえば、'mymachine2\myinstance' のインスタンスとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="0fa9a-233">You can specify the target server as an instance of SQL Server, for example, 'mymachine2\myinstance'.</span></span>  
  
 <span data-ttu-id="0fa9a-234">**使用例**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-234">**Examples**</span></span>  
  
```  
bm.exe disable-reference -TargetServer:MySrv -TargetDatabase:BamPI  
bm.exe disable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="see-also"></a><span data-ttu-id="0fa9a-235">参照</span><span class="sxs-lookup"><span data-stu-id="0fa9a-235">See Also</span></span>  
 [<span data-ttu-id="0fa9a-236">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="0fa9a-236">BAM Management Utility</span></span>](../core/bam-management-utility.md)