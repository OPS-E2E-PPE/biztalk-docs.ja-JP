---
title: データベース コマンド |Microsoft ドキュメント
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
ms.openlocfilehash: 2232602ec5a91768f4b9dbde5f6c63a79de0c332
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971368"
---
# <a name="database-commands"></a><span data-ttu-id="7fcc8-102">データベース コマンド</span><span class="sxs-lookup"><span data-stu-id="7fcc8-102">Database Commands</span></span>
<span data-ttu-id="7fcc8-103">BAM 管理ユーティリティのデータベース コマンドを使用すると、BAM データベースを操作することができます。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-103">The BAM Management utility database commands allow you to work with the BAM databases:</span></span>  
  
-   <span data-ttu-id="7fcc8-104">データベースのセットアップ: BAM 固有のデータベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-104">setup-databases: Creates the BAM-specific databases.</span></span>  
  
-   <span data-ttu-id="7fcc8-105">移行 sql: から BAM データベースを移行します。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-105">migrate-sql: Migrates your BAM databases from:</span></span>  
  
    -   <span data-ttu-id="7fcc8-106">Microsoft SQL Server 2000 から Microsoft SQL Server 2008 へ</span><span class="sxs-lookup"><span data-stu-id="7fcc8-106">Microsoft SQL Server 2000 to Microsoft SQL Server 2008</span></span>  
  
    -   <span data-ttu-id="7fcc8-107">Microsoft SQL Server 2008 への Microsoft SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="7fcc8-107">Microsoft SQL Server 2005 to Microsoft SQL Server 2008</span></span>  
  
-   <span data-ttu-id="7fcc8-108">参照を有効にする: 分散 BAM プライマリ インポート データベースへの参照を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-108">enable-reference: Enables a reference to a distributed BAM Primary Import database.</span></span>  
  
-   <span data-ttu-id="7fcc8-109">get 参照: 分散 BAM プライマリ インポート データベースへの参照の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-109">get-references: Gets a list of references to distributed BAM Primary Import databases.</span></span>  
  
-   <span data-ttu-id="7fcc8-110">参照を無効にする: BAM プライマリ インポート データベースへの参照を無効にします。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-110">disable-reference: Disables a reference to a BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fcc8-111">含めることで任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: で &#124;オフ**パラメーター スイッチ。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-111">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="7fcc8-112">Trace スイッチを使用すると、構成ファイルのトレース設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-112">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="7fcc8-113">このスイッチは、通常の BM コマンドと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-113">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fcc8-114">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-114">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="setup-databases-command"></a><span data-ttu-id="7fcc8-115">setup-databases コマンド</span><span class="sxs-lookup"><span data-stu-id="7fcc8-115">setup-databases Command</span></span>  
 <span data-ttu-id="7fcc8-116">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-116">**Usage**</span></span>  
  
 <span data-ttu-id="7fcc8-117">**bm.exe のセットアップ-データベース-ConfigFile:\<構成ファイル\>[- NSUser:\<通知サービスのユーザー名\>] [- NSUserPassword:\<通知サービスのユーザー パスワード\> ]**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-117">**bm.exe setup-databases-ConfigFile:\<configuration file\>[ -NSUser:\<notifications service user name\> ][ -NSUserPassword:\<notifications service user password\> ]**</span></span>  
  
 <span data-ttu-id="7fcc8-118">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-118">**Parameters**</span></span>  
  
|<span data-ttu-id="7fcc8-119">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7fcc8-119">Parameter</span></span>|<span data-ttu-id="7fcc8-120">Description</span><span class="sxs-lookup"><span data-stu-id="7fcc8-120">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7fcc8-121">ConfigFile:\<構成ファイル\></span><span class="sxs-lookup"><span data-stu-id="7fcc8-121">ConfigFile:\<configuration file\></span></span>|<span data-ttu-id="7fcc8-122">データベースの作成に使用する BAM 構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-122">The BAM configuration file from which to create the database.</span></span>|  
|<span data-ttu-id="7fcc8-123">NSUser:\<通知サービスのユーザー名\></span><span class="sxs-lookup"><span data-stu-id="7fcc8-123">NSUser:\<notifications service user name\></span></span>|<span data-ttu-id="7fcc8-124">省略可能: データベースを作成する権限を持つ notification services ユーザーのユーザー ID。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-124">Optional: The user ID of a notifications services user with permissions to create databases.</span></span>|  
|<span data-ttu-id="7fcc8-125">NSUserPassword</span><span class="sxs-lookup"><span data-stu-id="7fcc8-125">NSUserPassword</span></span>|<span data-ttu-id="7fcc8-126">省略可能: 指定された通知サービスのユーザーのパスワードです。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-126">Optional: The password for the specified notifications services user.</span></span>|  
  
 <span data-ttu-id="7fcc8-127">構成ファイルに指定されたデータベース (BAM プライマリ インポート、BAM スター スキーマ、BAM アーカイブ、BAM 分析、警告の各データベース) が存在しない場合は作成します。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-127">Creates the databases described in the configuration file (BAM Primary Import, BAM Star Schema, BAM Archive, BAM Analysis, and alerts) if they do not already exist.</span></span> <span data-ttu-id="7fcc8-128">データベースの作成後、関連する BAM メタデータ テーブルとストアド プロシージャが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-128">Once the databases are created, the command creates the associated BAM metadata tables and stored procedures.</span></span>  
  
 <span data-ttu-id="7fcc8-129">BAM 警告を設定する場合、NSUser パラメーターおよび NSUserPassword パラメーターは省略できません。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-129">The NSUser and NSUserPassword parameters are required if you are setting up BAM alerts.</span></span> <span data-ttu-id="7fcc8-130">コマンド ラインで NSUserPassword を指定しなかった場合、bm.exe により、パスワードの入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-130">If the NSUserPassword is not specified on the command line, bm.exe prompts you for the password.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fcc8-131">コマンドの実行後、トレース ログを見ると、AlertModule によって、次のような例外が出力されていることがあります。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-131">After the completion of the command, you may note an exception from the AlertModule in the trace log:</span></span>  
>   
>  <span data-ttu-id="7fcc8-132">"指定したアカウントはデータベース所有者です。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-132">"The specified account is the Database Owner.</span></span> <span data-ttu-id="7fcc8-133">データベース所有者は常にビューへのアクセス権限を持っており、ビューに追加したり、ビューから削除することはできません。"</span><span class="sxs-lookup"><span data-stu-id="7fcc8-133">The Database owner always has access to the view and cannot be added to or removed from the view."</span></span>  
>   
>  <span data-ttu-id="7fcc8-134">さらに、NotificationServices #19001 により、イベントの警告が出力されていることがあります。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-134">In addition, you may see a warning in the event from NotificationServices #19001.</span></span>  
>   
>  <span data-ttu-id="7fcc8-135">コマンドの実行中にエラーが報告されなければ、これらのメッセージは無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-135">If no errors were reported during the execution of the command, you can safely disregard these notices.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7fcc8-136">既に BAM 警告が構成されているとき、警告セクションを含まない BAM 構成ファイルを使って setup-database コマンドを実行すると、今後、警告が生成されないよう、bm.exe により構成が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-136">If you execute a setup-database command, using a BAM configuration file that does not contain an alerts section, and you have already configured BAM Alerts, bm.exe will overwrite the configuration such that alerts will no longer function.</span></span>  
  
 <span data-ttu-id="7fcc8-137">BAM データベースをセットアップするには、BAMPrimaryImport データベース、BAMStarSchema データベース、および BAMArchive データベースをホストする Microsoft SQL Server に対する管理者権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-137">To set up the BAM databases you must have administrator permissions on the Microsoft SQL server hosting the BAMPrimaryImport, BAMStarSchema, and BAMArchive databases.</span></span> <span data-ttu-id="7fcc8-138">SQL Notification Services データベースを設定するには、管理者権限を持っており、ローカルの Administrators グループのメンバーであることが必要です。また、追加で構成された他の管理者グループ (BTS Admins グループなど) のメンバーであることも必要です。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-138">To set up SQL Notification Services databases, you must have administrator permissions and be a member of the local administrators group, as well as be a member of any other additional administrative groups that have been configured, such as the BTS Admins group.</span></span>  
  
 <span data-ttu-id="7fcc8-139">**使用例**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-139">**Examples**</span></span>  
  
```  
bm.exe setup-databases -ConfigFile:BamConfiguration.xml  
bm.exe setup-databases -ConfigFile:cfg.xml -NSUser:domain\user1  
```  
  
## <a name="migrate-sql-command"></a><span data-ttu-id="7fcc8-140">migrate-sql コマンド</span><span class="sxs-lookup"><span data-stu-id="7fcc8-140">migrate-sql Command</span></span>  
 <span data-ttu-id="7fcc8-141">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-141">**Usage**</span></span>  
  
 <span data-ttu-id="7fcc8-142">**bm.exe-から: sql2000-を: sql2008 [- NSUser:\<通知サービスのユーザー名\>] [- NSUserPassword:\<通知サービスのユーザー パスワード\>] [-サーバー:\<サーバー\> ][-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-142">**bm.exe migrate-sql -From:sql2000 -To:sql2008 [ -NSUser:\<notifications service user name\> ][ -NSUserPassword:\<notifications service user password\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="7fcc8-143">\- または -</span><span class="sxs-lookup"><span data-stu-id="7fcc8-143">\- Or -</span></span>  
  
 <span data-ttu-id="7fcc8-144">**bm.exe-から: sql2005-を: sql2008 [- NSUser:\<通知サービスのユーザー名\>] [- NSUserPassword:\<通知サービスのユーザー パスワード\>] [-サーバー:\<サーバー\> ][-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-144">**bm.exe migrate-sql -From:sql2005 -To:sql2008 [ -NSUser:\<notifications service user name\> ][ -NSUserPassword:\<notifications service user password\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="7fcc8-145">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-145">**Parameters**</span></span>  
  
|<span data-ttu-id="7fcc8-146">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7fcc8-146">Parameter</span></span>|<span data-ttu-id="7fcc8-147">Description</span><span class="sxs-lookup"><span data-stu-id="7fcc8-147">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7fcc8-148">: Sql2000</span><span class="sxs-lookup"><span data-stu-id="7fcc8-148">From: sql2000</span></span>|<span data-ttu-id="7fcc8-149">Microsoft SQL Server 2000 データベースからの変換であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-149">Specifies that you are converting from a Microsoft SQL Server 2000 database.</span></span>|  
|<span data-ttu-id="7fcc8-150">To:sql2008</span><span class="sxs-lookup"><span data-stu-id="7fcc8-150">To:sql2008</span></span>|<span data-ttu-id="7fcc8-151">Microsoft SQL Server 2008 データベースに変換することを指定します。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-151">Specifies that you are converting to a Microsoft SQL Server 2008 database.</span></span>|  
|<span data-ttu-id="7fcc8-152">: Sql2005</span><span class="sxs-lookup"><span data-stu-id="7fcc8-152">From: sql2005</span></span>|<span data-ttu-id="7fcc8-153">Microsoft SQL Server 2005 データベースから変換であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-153">Specifies that you are converting from a Microsoft SQL Server 2005 database.</span></span>|  
|<span data-ttu-id="7fcc8-154">To:sql2008</span><span class="sxs-lookup"><span data-stu-id="7fcc8-154">To:sql2008</span></span>|<span data-ttu-id="7fcc8-155">Microsoft SQL Server 2008 データベースに変換することを指定します。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-155">Specifies that you are converting to a Microsoft SQL Server 2008 database.</span></span>|  
|<span data-ttu-id="7fcc8-156">NSUser:\<通知サービスのユーザー名\></span><span class="sxs-lookup"><span data-stu-id="7fcc8-156">NSUser:\<notifications service user name\></span></span>|<span data-ttu-id="7fcc8-157">省略可能: データベースを作成する権限を持つ Notification Services ユーザーのユーザー ID。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-157">Optional: The user ID of a Notifications Services user with permissions to create databases.</span></span>|  
|<span data-ttu-id="7fcc8-158">NSUserPassword</span><span class="sxs-lookup"><span data-stu-id="7fcc8-158">NSUserPassword</span></span>|<span data-ttu-id="7fcc8-159">省略可能: 指定した Notification Services ユーザーのパスワードです。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-159">Optional: The password for the specified Notifications Services user.</span></span>|  
|<span data-ttu-id="7fcc8-160">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="7fcc8-160">Server:\<server\></span></span>|<span data-ttu-id="7fcc8-161">省略可能: 変換後のデータベースが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-161">Optional: The name of the server on which the converted database will reside.</span></span> <span data-ttu-id="7fcc8-162">サーバーは、Microsoft SQL Server 2008 データベースをホストするコンピューターと同じドメインにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-162">The server must be in the same domain as the computer hosting the Microsoft SQL Server 2008 database.</span></span> <span data-ttu-id="7fcc8-163">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-163">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="7fcc8-164">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="7fcc8-164">Database:\<database\></span></span>|<span data-ttu-id="7fcc8-165">省略可能: 名前の変換後のデータベースです。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-165">Optional: Then name of the converted database.</span></span> <span data-ttu-id="7fcc8-166">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-166">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="7fcc8-167">Microsoft SQL Server 2000 または Microsoft SQL Server 2005 から BAM インフラストラクチャを Microsoft SQL Server 2008 に移行します。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-167">Migrates the BAM infrastructure from Microsoft SQL Server 2000 or Microsoft SQL Server 2005 to Microsoft SQL Server 2008.</span></span> <span data-ttu-id="7fcc8-168">Microsoft SQL Server 2000 または Microsoft SQL Server 2005 から Microsoft SQL Server 2008 に、データベース サーバーおよび分析サーバーをアップグレードした後は、このコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-168">Use this command after you upgrade your database server and Analysis server from Microsoft SQL Server 2000 or Microsoft SQL Server 2005 to Microsoft SQL Server 2008.</span></span>  
  
 <span data-ttu-id="7fcc8-169">BAM 警告を構成した場合、NSUser パラメーターおよび NSUserPassword パラメーターは省略できません。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-169">The NSUser and NSUserPassword parameters are required if BAM alerts are configured.</span></span> <span data-ttu-id="7fcc8-170">コマンド ラインで NSUserPassword を指定しなかった場合、bm.exe により、パスワードの入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-170">If the NSUserPassword is not specified on the command line, bm.exe prompts you for the password.</span></span>  
  
 <span data-ttu-id="7fcc8-171">SQL Server Notification Services データベースを移行するには、管理者権限を持っており、ローカルの Administrators グループのメンバーであることが必要です。また、追加で構成された他の管理者グループ (BTS Admins グループなど) のメンバーであることも必要です。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-171">To migrate the SQL Server Notification Services databases, you must have administrator permissions and be a member of the local administrators group, as well as be a member of any other additional administrative groups that have been configured, such as the BTS Admins group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fcc8-172">エラー メッセージを受け取る場合は、"エラー: コンピューターで NS$ BAMAlerts サービスを開始できません '\<コンピューター名\>' です。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-172">If you receive the error message "ERROR: Cannot start service NS$BAMAlerts on computer '\<computer name\>'.</span></span> <span data-ttu-id="7fcc8-173">サービスは適切な時間内に開始要求または制御要求に応答しませんでした。」が表示される場合は、サービスを手動で開始してみます。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-173">The service did not respond to the start or control request in a timely fashion.", try restarting the service manually.</span></span> <span data-ttu-id="7fcc8-174">移行時など、SQL Server が極端なビジー状態の場合は、サービスを再開できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-174">If the SQL Server is extremely busy during a migration, the service may not restart.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fcc8-175">Notification Services がインストールされているコンピューターで migrate-sql コマンドを実行するには、そのコンピューターのローカル管理者グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-175">To run the migrate-sql command on the computer where Notification Services is installed, you must belong to the Local Administrators group on that computer.</span></span>  
  
 <span data-ttu-id="7fcc8-176">**使用例**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-176">**Examples**</span></span>  
  
```  
bm.exe migrate-sql -From:sql2000 -To:sql2008 -NSUser:domain\user1  
bm.exe migrate-sql -From:sql2000 -To:sql2008 -Server:MyServer -Database:db1  
```  
  
```  
bm.exe migrate-sql -From:sql2005 -To:sql2008 -NSUser:domain\user1  
bm.exe migrate-sql -From:sql2005 -To:sql2008 -Server:MyServer -Database:db1  
```  
  
## <a name="enable-reference-command"></a><span data-ttu-id="7fcc8-177">enable-reference コマンド</span><span class="sxs-lookup"><span data-stu-id="7fcc8-177">enable-reference Command</span></span>  
 <span data-ttu-id="7fcc8-178">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-178">**Usage**</span></span>  
  
 <span data-ttu-id="7fcc8-179">**bm.exe 参照を有効にする TargetServer:\<ターゲット サーバー\> - TargetDatabase:\<ターゲット データベース\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\> ]**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-179">**bm.exe enable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="7fcc8-180">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-180">**Parameters**</span></span>  
  
|<span data-ttu-id="7fcc8-181">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7fcc8-181">Parameter</span></span>|<span data-ttu-id="7fcc8-182">Description</span><span class="sxs-lookup"><span data-stu-id="7fcc8-182">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7fcc8-183">TargetServer:\<ターゲット サーバー\></span><span class="sxs-lookup"><span data-stu-id="7fcc8-183">TargetServer:\<target server\></span></span>|<span data-ttu-id="7fcc8-184">参照を有効にするサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-184">The name of the server to which the reference is enabled.</span></span> <span data-ttu-id="7fcc8-185">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-185">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="7fcc8-186">TargetDatabase:\<ターゲット データベース\></span><span class="sxs-lookup"><span data-stu-id="7fcc8-186">TargetDatabase:\<target database\></span></span>|<span data-ttu-id="7fcc8-187">参照を有効にするデータベースの名前です。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-187">The name of the database to which the reference is enabled.</span></span>|  
|<span data-ttu-id="7fcc8-188">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="7fcc8-188">Server:\<server\></span></span>|<span data-ttu-id="7fcc8-189">省略可能: への参照を有効になっている対象サーバーとデータベースを持つサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-189">Optional: The name of the server which will have a reference enabled to the target server and database.</span></span> <span data-ttu-id="7fcc8-190">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-190">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="7fcc8-191">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="7fcc8-191">Database:\<database\></span></span>|<span data-ttu-id="7fcc8-192">省略可能: への参照を有効になっている対象サーバーとデータベースを持つデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-192">Optional: The name of the database which will have a reference enabled to the target server and database.</span></span> <span data-ttu-id="7fcc8-193">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-193">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="7fcc8-194">分散されている別の BAM プライマリ インポート データベースへの参照を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-194">Enables a reference to another distributed BAM Primary Import database.</span></span> <span data-ttu-id="7fcc8-195">対象となる BAM プライマリ インポート データベース上のビューやアクティビティのメタデータを、現在のデータベースからサブスクライブできます。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-195">This allows subscriptions from the current database to the view and activity metadata on the target BAM Primary Import database.</span></span> <span data-ttu-id="7fcc8-196">分散アクティビティを表示できるようにしたい場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-196">You use this to enable navigation of the distributed activities.</span></span>  
  
 <span data-ttu-id="7fcc8-197">対象サーバーを SQL Server のインスタンスとして指定できます (例 : 'mymachine2\myinstance')。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-197">You can specify the target server as an instance of SQL Server, for example, 'mymachine2\myinstance'.</span></span>  
  
 <span data-ttu-id="7fcc8-198">**使用例**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-198">**Examples**</span></span>  
  
```  
bm.exe enable-reference -TargetServer:MySrv -TargetDatabase:BamPrimaryImport  
bm.exe enable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="get-references-command"></a><span data-ttu-id="7fcc8-199">get-references コマンド</span><span class="sxs-lookup"><span data-stu-id="7fcc8-199">get-references Command</span></span>  
 <span data-ttu-id="7fcc8-200">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-200">**Usage**</span></span>  
  
 <span data-ttu-id="7fcc8-201">**bm.exe get 参照 [-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-201">**bm.exe get-references [ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="7fcc8-202">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-202">**Parameters**</span></span>  
  
|<span data-ttu-id="7fcc8-203">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7fcc8-203">Parameter</span></span>|<span data-ttu-id="7fcc8-204">Description</span><span class="sxs-lookup"><span data-stu-id="7fcc8-204">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7fcc8-205">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="7fcc8-205">Server:\<server\></span></span>|<span data-ttu-id="7fcc8-206">省略可能: 参照の一覧を取得するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-206">Optional: The name of the server on which to get a list of references.</span></span> <span data-ttu-id="7fcc8-207">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-207">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="7fcc8-208">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-208">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="7fcc8-209">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="7fcc8-209">Database:\<database\></span></span>|<span data-ttu-id="7fcc8-210">省略可能: 参照の一覧を取得する対象のデータベースの名前です。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-210">Optional: The name of the database on which to get a list of references.</span></span> <span data-ttu-id="7fcc8-211">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-211">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="7fcc8-212">コマンドを実行するコンピューターで有効にされている参照を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-212">Lists the references enabled on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="7fcc8-213">**使用例**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-213">**Examples**</span></span>  
  
```  
bm.exe get-references  
bm.exe get-references -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="disable-reference-command"></a><span data-ttu-id="7fcc8-214">disable-reference コマンド</span><span class="sxs-lookup"><span data-stu-id="7fcc8-214">disable-reference Command</span></span>  
 <span data-ttu-id="7fcc8-215">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-215">**Usage**</span></span>  
  
 <span data-ttu-id="7fcc8-216">**bm.exe 無効参照 TargetServer:\<ターゲット サーバー\> - TargetDatabase:\<ターゲット データベース\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\> ]**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-216">**bm.exe disable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="7fcc8-217">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-217">**Parameters**</span></span>  
  
|<span data-ttu-id="7fcc8-218">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7fcc8-218">Parameter</span></span>|<span data-ttu-id="7fcc8-219">Description</span><span class="sxs-lookup"><span data-stu-id="7fcc8-219">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7fcc8-220">TargetServer:\<ターゲット サーバー\></span><span class="sxs-lookup"><span data-stu-id="7fcc8-220">TargetServer:\<target server\></span></span>|<span data-ttu-id="7fcc8-221">参照を無効にするサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-221">The name of the server on which to disable the references.</span></span> <span data-ttu-id="7fcc8-222">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-222">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="7fcc8-223">TargetDatabase:\<ターゲット データベース\></span><span class="sxs-lookup"><span data-stu-id="7fcc8-223">TargetDatabase:\<target database\></span></span>|<span data-ttu-id="7fcc8-224">参照を無効にするデータベースの名前です。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-224">The name of the database on which to disable the references.</span></span>|  
|<span data-ttu-id="7fcc8-225">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="7fcc8-225">Server:\<server\></span></span>|<span data-ttu-id="7fcc8-226">省略可能: ターゲット参照をサーバーとデータベースが無効にするサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-226">Optional: The name of the server on which references to the target server and database are to be disabled.</span></span> <span data-ttu-id="7fcc8-227">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-227">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="7fcc8-228">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-228">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="7fcc8-229">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="7fcc8-229">Database:\<database\></span></span>|<span data-ttu-id="7fcc8-230">省略可能: を無効にするのには、参照を対象サーバー上のデータベースとデータベースの名前です。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-230">Optional: The name of the database on which references to the target server and database are to be disabled.</span></span> <span data-ttu-id="7fcc8-231">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-231">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="7fcc8-232">対象サーバー上の別の分散 BAM プライマリ インポート データベースへの参照を無効にします。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-232">Disables a reference to another distributed BAM Primary Import database on the target server.</span></span>  
  
 <span data-ttu-id="7fcc8-233">対象サーバーを SQL Server のインスタンスとして指定できます (例 : 'mymachine2\myinstance')。</span><span class="sxs-lookup"><span data-stu-id="7fcc8-233">You can specify the target server as an instance of SQL Server, for example, 'mymachine2\myinstance'.</span></span>  
  
 <span data-ttu-id="7fcc8-234">**使用例**</span><span class="sxs-lookup"><span data-stu-id="7fcc8-234">**Examples**</span></span>  
  
```  
bm.exe disable-reference -TargetServer:MySrv -TargetDatabase:BamPI  
bm.exe disable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="see-also"></a><span data-ttu-id="7fcc8-235">参照</span><span class="sxs-lookup"><span data-stu-id="7fcc8-235">See Also</span></span>  
 [<span data-ttu-id="7fcc8-236">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="7fcc8-236">BAM Management Utility</span></span>](../core/bam-management-utility.md)