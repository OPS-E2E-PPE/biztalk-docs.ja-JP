---
title: SQL Server のアクセス許可の問題を解決するためのガイドライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60c24512-5f65-4363-b806-8dd52b22f179
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54d7a26d4c781ea27c2cefa19540025b0688e9b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344853"
---
# <a name="guidelines-for-resolving-sql-server-permissions-problems"></a><span data-ttu-id="757d2-102">SQL Server 権限の問題を解決するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="757d2-102">Guidelines for Resolving SQL Server Permissions Problems</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="757d2-103">Microsoft の広範に使用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]実行時の操作とそのデータベースが重要ですが、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]アクセス許可が正しく設定。</span><span class="sxs-lookup"><span data-stu-id="757d2-103">makes extensive use of Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases for run-time operations and as such, it is important that the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] permissions are set correctly.</span></span> <span data-ttu-id="757d2-104">このトピックでは、最小限に抑えるための一般的なガイドラインを提供します[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]アクセス許可の問題とトラブルシューティングに利用できる手順[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]アクセス許可の問題に影響を与える[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="757d2-104">This topic provides some general guidelines for minimizing [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] permissions problems and steps that you can follow to troubleshoot [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] permissions problems that affect [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="general-guidelines"></a><span data-ttu-id="757d2-105">一般的なガイドライン</span><span class="sxs-lookup"><span data-stu-id="757d2-105">General Guidelines</span></span>  
  
- <span data-ttu-id="757d2-106">**ドメイン ユーザーおよびグループを使用して、BizTalk Server の複数コンピューターのインストール**</span><span class="sxs-lookup"><span data-stu-id="757d2-106">**Use domain users and groups for a multicomputer installation of BizTalk Server**</span></span>  
  
   <span data-ttu-id="757d2-107">構成するときに、ドメイン ユーザー グループとアカウントを使用する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]など、複数コンピューター環境シナリオで実行する場所[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]別のコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="757d2-107">You must use domain user groups and accounts when configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to run in a multicomputer scenario, for example, where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are installed on separate computers.</span></span> <span data-ttu-id="757d2-108">構成または実行しないで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で、*パススルー*ドメイン グループおよびアカウントの使用を回避するには、各コンピューターに一致するユーザー名とパスワードのペアを作成するための認証シナリオ。</span><span class="sxs-lookup"><span data-stu-id="757d2-108">Do not attempt to configure or run [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a *pass-through* authentication scenario whereby matching pairs of usernames and passwords are created on each computer to avoid using domain groups and accounts.</span></span> <span data-ttu-id="757d2-109">これにより、このようなパススルー シナリオは、一部のシナリオで正常に機能に見える場合があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]他のシナリオで失敗して、サポートされる構成ではありません。</span><span class="sxs-lookup"><span data-stu-id="757d2-109">While such a pass-through scenario may appear to function correctly in some scenarios, this will cause [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to fail in other scenarios and is not a supported configuration.</span></span>  
  
   <span data-ttu-id="757d2-110">インストールと構成の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]複数コンピューター構成では、ダウンロード、インストール ガイド[関連する BizTalk Server 2013 インストール ガイド](http://go.microsoft.com/fwlink/p/?LinkID=269582)します。</span><span class="sxs-lookup"><span data-stu-id="757d2-110">For more information about installing and configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a multicomputer configuration, download the Installation Guide at [Installation Guides Related to BizTalk Server 2013](http://go.microsoft.com/fwlink/p/?LinkID=269582).</span></span>  
  
- <span data-ttu-id="757d2-111">**適切な Windows ユーザーとグループが適切な SQL Server ロールで定義されていることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="757d2-111">**Ensure that the appropriate Windows users and groups are defined in the appropriate SQL Server roles**</span></span>  
  
   <span data-ttu-id="757d2-112">正しいことを確認[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ロールのメンバーシップのトピックの表に示す[Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="757d2-112">Verify correct [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] role membership as listed in the table in the topic [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
- <span data-ttu-id="757d2-113">**ユーザーの SQL Server Profiler のアクセス許可の問題を診断するには**</span><span class="sxs-lookup"><span data-stu-id="757d2-113">**User SQL Server Profiler to diagnose permissions problems**</span></span>  
  
   <span data-ttu-id="757d2-114">設定する、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Profiler トレースを監視する、 **Audit Login Failed イベント**アクセス許可のエラーに関する詳細情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="757d2-114">Set up a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Profiler trace to monitor the **Audit Login Failed Event** to gather detailed information about permissions failures.</span></span> <span data-ttu-id="757d2-115">使用する方法については[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Profiler を参照してください、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="757d2-115">For information about how to use [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Profiler, see the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] documentation.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="757d2-116">既知の問題</span><span class="sxs-lookup"><span data-stu-id="757d2-116">Known Issues</span></span>  
  
#### <a name="the-sql-server-jobs-that-are-installed-with-biztalk-server-fail-to-execute"></a><span data-ttu-id="757d2-117">BizTalk Server と共にインストールされる SQL Server ジョブの実行失敗します。</span><span class="sxs-lookup"><span data-stu-id="757d2-117">The SQL Server jobs that are installed with BizTalk Server fail to execute</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="757d2-118">問題</span><span class="sxs-lookup"><span data-stu-id="757d2-118">Problem</span></span>  
 <span data-ttu-id="757d2-119">と共にインストールされる SQL Server ジョブ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で失敗して、次のようなエラーが生成される、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]アプリケーション ログ。</span><span class="sxs-lookup"><span data-stu-id="757d2-119">The SQL Server jobs that are installed with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] fail and errors similar to the following are generated in the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Application log:</span></span>  
  
 <span data-ttu-id="757d2-120">イベントの種類:警告</span><span class="sxs-lookup"><span data-stu-id="757d2-120">Event Type: Warning</span></span>  
  
 <span data-ttu-id="757d2-121">イベント ソース:SQLSERVERAGENT</span><span class="sxs-lookup"><span data-stu-id="757d2-121">Event Source: SQLSERVERAGENT</span></span>  
  
 <span data-ttu-id="757d2-122">イベント カテゴリ:ジョブ エンジン</span><span class="sxs-lookup"><span data-stu-id="757d2-122">Event Category: Job Engine</span></span>  
  
 <span data-ttu-id="757d2-123">イベント ID:208</span><span class="sxs-lookup"><span data-stu-id="757d2-123">Event ID: 208</span></span>  
  
 <span data-ttu-id="757d2-124">日付:6/29/2008</span><span class="sxs-lookup"><span data-stu-id="757d2-124">Date: 6/29/2008</span></span>  
  
 <span data-ttu-id="757d2-125">時間:午後 4時 45分: 01</span><span class="sxs-lookup"><span data-stu-id="757d2-125">Time: 4:45:01 PM</span></span>  
  
 <span data-ttu-id="757d2-126">ユーザー :なし</span><span class="sxs-lookup"><span data-stu-id="757d2-126">User: N/A</span></span>  
  
 <span data-ttu-id="757d2-127">コンピューター:*Sql Server*</span><span class="sxs-lookup"><span data-stu-id="757d2-127">Computer: *SQLServer*</span></span>  
  
 <span data-ttu-id="757d2-128">説明:</span><span class="sxs-lookup"><span data-stu-id="757d2-128">Description:</span></span>  
  
 <span data-ttu-id="757d2-129">SQL Server のスケジュールされたジョブ 'BizTalk Server のバックアップ'</span><span class="sxs-lookup"><span data-stu-id="757d2-129">SQL Server Scheduled Job 'Backup BizTalk Server'</span></span>  
  
 <span data-ttu-id="757d2-130">(0x4AC7C44A48541443927A56C5C6699ECF) - 状態。Failed-invoked on:2008-6-29 01: 13時 45分 - メッセージ。ジョブが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="757d2-130">(0x4AC7C44A48541443927A56C5C6699ECF) - Status: Failed - Invoked on: 2008-6-29 13:45:01 - Message: The job failed.</span></span>  <span data-ttu-id="757d2-131">By Schedule 305 (MarkAndBackupLogSched) ジョブが呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="757d2-131">The Job was invoked by Schedule 305 (MarkAndBackupLogSched).</span></span> <span data-ttu-id="757d2-132">最後の手順を実行するには、手順 1 (BackupFull) がでした。</span><span class="sxs-lookup"><span data-stu-id="757d2-132">The last step to run was step 1 (BackupFull).</span></span>  
  
 <span data-ttu-id="757d2-133">**- と -**</span><span class="sxs-lookup"><span data-stu-id="757d2-133">**- and -**</span></span>  
  
 <span data-ttu-id="757d2-134">イベントの種類:[情報]</span><span class="sxs-lookup"><span data-stu-id="757d2-134">Event Type: Information</span></span>  
  
 <span data-ttu-id="757d2-135">イベント ソース:MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="757d2-135">Event Source: MSSQLSERVER</span></span>  
  
 <span data-ttu-id="757d2-136">イベント カテゴリ:(4)</span><span class="sxs-lookup"><span data-stu-id="757d2-136">Event Category: (4)</span></span>  
  
 <span data-ttu-id="757d2-137">イベント ID:17055</span><span class="sxs-lookup"><span data-stu-id="757d2-137">Event ID: 17055</span></span>  
  
 <span data-ttu-id="757d2-138">日付:6/29/2008</span><span class="sxs-lookup"><span data-stu-id="757d2-138">Date: 6/29/2008</span></span>  
  
 <span data-ttu-id="757d2-139">時間:午後 4時 45分: 01</span><span class="sxs-lookup"><span data-stu-id="757d2-139">Time: 4:45:01 PM</span></span>  
  
 <span data-ttu-id="757d2-140">ユーザー :なし</span><span class="sxs-lookup"><span data-stu-id="757d2-140">User: N/A</span></span>  
  
 <span data-ttu-id="757d2-141">コンピューター:*Sql Server*</span><span class="sxs-lookup"><span data-stu-id="757d2-141">Computer: *SQLServer*</span></span>  
  
 <span data-ttu-id="757d2-142">説明:</span><span class="sxs-lookup"><span data-stu-id="757d2-142">Description:</span></span>  
  
 <span data-ttu-id="757d2-143">18456:ユーザー 'NT authority \system' はログインできませんでした。</span><span class="sxs-lookup"><span data-stu-id="757d2-143">18456: Login failed for user 'NT AUTHORITY\SYSTEM'.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="757d2-144">原因</span><span class="sxs-lookup"><span data-stu-id="757d2-144">Cause</span></span>  
 <span data-ttu-id="757d2-145">このエラーから builtin \administrators ログインが削除された場合に発生する可能性が[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="757d2-145">This error can occur if the BUILTIN\Administrators login has been removed from [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="757d2-146">Sqlmaint.exe にログオンできませんなります builtin \administrators ログインが削除された場合[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]SQL ジョブの実行ができなきます。</span><span class="sxs-lookup"><span data-stu-id="757d2-146">If the BUILTIN\Administrators login is deleted, sqlmaint.exe will be unable to logon to [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] which will prevent SQL jobs from running.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="757d2-147">解決策</span><span class="sxs-lookup"><span data-stu-id="757d2-147">Resolution</span></span>  
 <span data-ttu-id="757d2-148">この問題を解決するには、builtin \administrators ログインを再作成し、db_owner ロールに追加、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースとマスター データベース。</span><span class="sxs-lookup"><span data-stu-id="757d2-148">To resolve this issue, re-create the BUILTIN\Administrators Login and add it to the db_owner role for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases and the Master database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="757d2-149">参照</span><span class="sxs-lookup"><span data-stu-id="757d2-149">See Also</span></span>  
 <span data-ttu-id="757d2-150">[SQL Server のトラブルシューティング](../core/troubleshooting-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="757d2-150">[Troubleshooting SQL Server](../core/troubleshooting-sql-server.md) </span></span>  
 [<span data-ttu-id="757d2-151">BizTalk Server のアクセス許可のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="757d2-151">Troubleshooting BizTalk Server Permissions</span></span>](../core/troubleshooting-biztalk-server-permissions.md)