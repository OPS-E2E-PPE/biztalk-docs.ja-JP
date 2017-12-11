---
title: "SQL Server のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f6707c5-7c6e-4375-bfa6-9b1a86ec5e81
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 632ca1c46a3df313e3aac4e144cad1647eb2360f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshooting-sql-server"></a><span data-ttu-id="aaf1b-102">SQL Server のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="aaf1b-102">Troubleshooting SQL Server</span></span>
<span data-ttu-id="aaf1b-103">Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] に影響を与える Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の問題の大部分は、次のカテゴリのいずれかに分類されます。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-103">The majority of Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] issues that affect Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] fall into one of the following categories:</span></span>  
  
-   <span data-ttu-id="aaf1b-104">接続に関連した問題</span><span class="sxs-lookup"><span data-stu-id="aaf1b-104">Connectivity-related problems</span></span>  
  
-   <span data-ttu-id="aaf1b-105">アクセス許可関連の問題</span><span class="sxs-lookup"><span data-stu-id="aaf1b-105">Permissions-related problems</span></span>  
  
-   <span data-ttu-id="aaf1b-106">データベース サイズの問題</span><span class="sxs-lookup"><span data-stu-id="aaf1b-106">Database-sizing problems</span></span>  
  
 <span data-ttu-id="aaf1b-107">このトピックでは、これらのカテゴリそれぞれについて、および関連する問題を解決するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-107">This topic discusses each of these categories and steps that you can take to resolve the associated problems.</span></span>  
  
## <a name="connectivity-related-problems"></a><span data-ttu-id="aaf1b-108">接続関連の問題</span><span class="sxs-lookup"><span data-stu-id="aaf1b-108">Connectivity-Related Problems</span></span>  
 <span data-ttu-id="aaf1b-109">次の問題は、一般的に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターと、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] データベースがある [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターの間の接続の問題に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-109">The following issues are most commonly associated with connectivity problems between the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer and the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer that houses the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
#### <a name="errors-related-to-failed-transactions-or-communication-with-the-underlying-transaction-manager-errors-are-written-to-the-biztalk-server-application-log"></a><span data-ttu-id="aaf1b-110">失敗したトランザクションに関連するエラー、または基になるトランザクション マネージャーとの通信の失敗を示すエラーが BizTalk Server アプリケーションのログに書き込まれる</span><span class="sxs-lookup"><span data-stu-id="aaf1b-110">Errors related to failed transactions or "Communication with the underlying transaction manager" errors are written to the BizTalk Server Application log</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="aaf1b-111">問題</span><span class="sxs-lookup"><span data-stu-id="aaf1b-111">Problem</span></span>  
 <span data-ttu-id="aaf1b-112">MSDTC トランザクションの失敗または基になるトランザクション マネージャーとの通信の失敗を示すエラーが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションのログに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-112">Errors indicating an MSDTC transaction failure or a failure to communicate with the underlying transaction manager are written to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application log.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="aaf1b-113">原因</span><span class="sxs-lookup"><span data-stu-id="aaf1b-113">Cause</span></span>  
 <span data-ttu-id="aaf1b-114">間の MSDTC 接続[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-114">MSDTC connectivity between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]and[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] has failed.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="aaf1b-115">解決策</span><span class="sxs-lookup"><span data-stu-id="aaf1b-115">Resolution</span></span>  
 <span data-ttu-id="aaf1b-116">間の MSDTC 接続のトラブルシューティングについては、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターおよび[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納しているコンピューター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを参照してください[MSDTC の問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)です。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-116">For information about troubleshooting MSDTC connectivity between the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer and the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer that houses the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>  
  
#### <a name="error-a-connection-was-successfully-established-with-the-server-but-then-an-error-occurred-during-the-pre-login-handshake-occurs-when-connecting-to-remote-sql-server-databases-on-sql-server-2008"></a><span data-ttu-id="aaf1b-117">SQL Server 2008 上のリモート SQL Server データベースに接続するときに、サーバーとの接続は正常に確立されたが、ログイン前のハンドシェイク時にエラーが発生したことを示すエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="aaf1b-117">Error "A connection was successfully established with the server, but then an error occurred during the pre-login handshake" occurs when connecting to remote SQL Server databases on SQL Server 2008</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="aaf1b-118">問題</span><span class="sxs-lookup"><span data-stu-id="aaf1b-118">Problem</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="aaf1b-119"> が、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] データベースのあるリモート [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターとの接続を失い、エラー メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-119"> loses connectivity with a remote [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer that houses the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases and an error message is generated:</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="aaf1b-120">原因</span><span class="sxs-lookup"><span data-stu-id="aaf1b-120">Cause</span></span>  
 <span data-ttu-id="aaf1b-121">この問題は、次の条件の 1 つ以上が当てはまるときに発生します。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-121">This problem may occur if one or more of the following conditions is true:</span></span>  
  
-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]<span data-ttu-id="aaf1b-122"> がリモート接続を受け入れるように構成されていません。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-122"> is not configured to accept remote connections.</span></span>  
  
-   <span data-ttu-id="aaf1b-123">[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] に必要なプロトコルが、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] コンピューター、または [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を実行している [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] クライアント コンピューターで有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-123">The necessary protocols for [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are not enabled on either the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer or the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] client computer that is running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="aaf1b-124">解決策</span><span class="sxs-lookup"><span data-stu-id="aaf1b-124">Resolution</span></span>  
 <span data-ttu-id="aaf1b-125">この問題を解決するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-125">Follow these steps to resolve this problem:</span></span>  
  
-   <span data-ttu-id="aaf1b-126">**SQL Server セキュリティ構成**ツールは SQL Server 2008 では使用できません。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-126">The **SQL Server Surface Area Configuration** tool is not available on SQL Server 2008.</span></span> <span data-ttu-id="aaf1b-127">SQL Server 2008 コンピューターで [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] のリモート接続を有効にするには、SQL Server 2008 オンライン ヘルプの説明に従ってください。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-127">To enable remote connections for [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] on a SQL Server 2008 computer follow the instructions in the SQL Server 2008 online help.</span></span>  
  
-   <span data-ttu-id="aaf1b-128">使用して、 **SQL Server 構成マネージャー**を有効にするツール、 **TCP/IP**と**名前付きパイプ**のプロトコル、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-128">Use the **SQL Server Configuration Manager** tool to enable the **TCP/IP** and/or the **Named Pipes** protocols on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
    1.  <span data-ttu-id="aaf1b-129">をクリックして**開始**、 をポイント**すべてのプログラム**、 をクリック**SQL Server 構成マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-129">Click **Start**, point to **All Programs**, and click **SQL Server Configuration Manager**.</span></span>  
  
    2.  <span data-ttu-id="aaf1b-130">クリックして展開**SQL Server ネットワーク構成** をクリックし、 **MSSQLSERVER のプロトコル**です。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-130">Click to expand **SQL Server Network Configuration** and then click **Protocols for MSSQLSERVER**.</span></span>  
  
    3.  <span data-ttu-id="aaf1b-131">右クリックし、 **TCP/IP**プロトコルをクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-131">Right-click the **TCP/IP** protocol and then click **Enable**.</span></span>  
  
    4.  <span data-ttu-id="aaf1b-132">右クリックし、**名前付きパイプ**プロトコルをクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-132">Right-click the **Named Pipes** protocol and then click **Enable**.</span></span>  
  
    5.  <span data-ttu-id="aaf1b-133">閉じる、 **SQL Server 構成マネージャー**ツールです。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-133">Close the **SQL Server Configuration Manager** tool.</span></span>  
  
-   <span data-ttu-id="aaf1b-134">使用して、 **SQL Server 構成マネージャー**を有効にするツール、 **TCP/IP**と**名前付きパイプ**のプロトコル、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を実行しているクライアントコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aaf1b-134">Use the **SQL Server Configuration Manager** tool to enable the **TCP/IP** and/or the **Named Pipes** protocols on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] client computer that is running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    1.  <span data-ttu-id="aaf1b-135">をクリックして**開始**、 をポイント**すべてのプログラム**、 をクリック**SQL Server 構成マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-135">Click **Start**, point to **All Programs**, and click **SQL Server Configuration Manager**.</span></span>  
  
    2.  <span data-ttu-id="aaf1b-136">クリックして展開**SQL Server ネットワーク構成** をクリックし、 **ClientProtocols**です。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-136">Click to expand **SQL Server Network Configuration** and then click **ClientProtocols**.</span></span>  
  
    3.  <span data-ttu-id="aaf1b-137">右クリックし、 **TCP/IP**プロトコルをクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-137">Right-click the **TCP/IP** protocol and then click **Enable**.</span></span>  
  
    4.  <span data-ttu-id="aaf1b-138">右クリックし、**名前付きパイプ**プロトコルをクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-138">Right-click the **Named Pipes** protocol and then click **Enable**.</span></span>  
  
    5.  <span data-ttu-id="aaf1b-139">閉じる、 **SQL Server 構成マネージャー**ツールです。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-139">Close the **SQL Server Configuration Manager** tool.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aaf1b-140">[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を実行している [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] クライアント コンピューターにおけるプロトコルの少なくとも 1 つが、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] コンピューターで有効になっているプロトコルに一致することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-140">Ensure that at least one of the protocols on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] client computer that is running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] matches the protocols enabled on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
#### <a name="a-biztalk-host-instance-fails-and-a-general-network-error-is-written-to-the-application-log-when-the-biztalk-server-based-server-processes-a-high-volume-of-documents"></a><span data-ttu-id="aaf1b-141">BizTalk Server ベースのサーバーで大量のドキュメントを処理するときに、BizTalk ホスト インスタンスが失敗して、"一般的なネットワーク" エラーがアプリケーション ログに書き込まれる</span><span class="sxs-lookup"><span data-stu-id="aaf1b-141">A BizTalk host instance fails and a "General Network" error is written to the Application log when the BizTalk Server-based server processes a high volume of documents</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="aaf1b-142">問題</span><span class="sxs-lookup"><span data-stu-id="aaf1b-142">Problem</span></span>  
 <span data-ttu-id="aaf1b-143">大量のドキュメントを処理するときに、BizTalk ホスト インスタンスが失敗し、"一般的なネットワーク" エラーがアプリケーション ログに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-143">When processing a high volume of documents, a BizTalk host instance fails, and a "General Network" error is written to the Application log.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="aaf1b-144">原因</span><span class="sxs-lookup"><span data-stu-id="aaf1b-144">Cause</span></span>  
 <span data-ttu-id="aaf1b-145">この問題は、Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] に実装されているセキュリティ機能により、サーバーへの同時 TCP/IP 接続のためのキューのサイズが減らされるために発生します。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-145">This issue occurs because Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] implements a security feature that reduces the size of the queue for concurrent TCP/IP connections to the server.</span></span> <span data-ttu-id="aaf1b-146">この機能は、サービス拒否攻撃の回避に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-146">This feature helps prevent denial of service attacks.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="aaf1b-147">解決策</span><span class="sxs-lookup"><span data-stu-id="aaf1b-147">Resolution</span></span>  
 <span data-ttu-id="aaf1b-148">この問題の解決の詳細については、次を参照してください。 [DBNETLIB 例外の回避](../core/avoiding-dbnetlib-exceptions.md)です。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-148">For more information about resolving this issue, see [Avoiding DBNETLIB Exceptions](../core/avoiding-dbnetlib-exceptions.md).</span></span>  
  
## <a name="permissions-related-problems"></a><span data-ttu-id="aaf1b-149">アクセス許可に関連した問題</span><span class="sxs-lookup"><span data-stu-id="aaf1b-149">Permissions-Related Problems</span></span>  
  
#### <a name="biztalk-server-run-time-or-design-time-operations-fail-and-a-cannot-open-database-requested-in-login-database-error-is-written-to-the-application-log-of-the-biztalk-server-or-sql-server-computer"></a><span data-ttu-id="aaf1b-150">BizTalk Server が実行時またはデザイン時の操作が失敗して、"ログインで要求されたデータベースを開くことができません\<データベース\>"エラーが BizTalk Server または SQL Server コンピューターのアプリケーション ログに書き込まれます</span><span class="sxs-lookup"><span data-stu-id="aaf1b-150">BizTalk Server run-time or design-time operations fail and a "cannot open database requested in login \<database\>" error is written to the Application log of the BizTalk Server or SQL Server computer</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="aaf1b-151">問題</span><span class="sxs-lookup"><span data-stu-id="aaf1b-151">Problem</span></span>  
 <span data-ttu-id="aaf1b-152">実行時またはデザイン時の操作が失敗し、次のようなエラーが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] または [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] コンピューターのアプリケーション ログに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-152">A run-time or design-time operation fails and an error similar to the following is written to the application log of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer:</span></span>  
  
 <span data-ttu-id="aaf1b-153">ログインで要求されたデータベースを開くことができません\<*データベース*\>です。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-153">Cannot open database requested in login \<*database*\>.</span></span> <span data-ttu-id="aaf1b-154">ログインに失敗しました.</span><span class="sxs-lookup"><span data-stu-id="aaf1b-154">Login fails.</span></span>   
<span data-ttu-id="aaf1b-155">ユーザーはログインできませんでした\< *username*\>です。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-155">Login failed for user \<*username*\>.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="aaf1b-156">原因</span><span class="sxs-lookup"><span data-stu-id="aaf1b-156">Cause</span></span>  
 <span data-ttu-id="aaf1b-157">このエラーは、指定したアカウントが適切な Windows グループまたは [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] ロールに属していない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-157">This error can occur if the specified account does not belong to the appropriate Windows group or [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] role.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="aaf1b-158">解決策</span><span class="sxs-lookup"><span data-stu-id="aaf1b-158">Resolution</span></span>  
 <span data-ttu-id="aaf1b-159">指定したアカウントが適切な Windows グループまたは [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] ロールのメンバーであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-159">Ensure that the specified account is a member of the appropriate Windows group or [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] role.</span></span> <span data-ttu-id="aaf1b-160">適切なメンバーシップの詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-160">For more information about the appropriate memberships, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
## <a name="database-sizing-problems"></a><span data-ttu-id="aaf1b-161">データベース サイズに関連した問題</span><span class="sxs-lookup"><span data-stu-id="aaf1b-161">Database-Sizing Problems</span></span>  
 <span data-ttu-id="aaf1b-162">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースがチェックされない状態で肥大する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境のパフォーマンスが悪影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-162">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases grow unchecked then the performance of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment will be adversely affected.</span></span> <span data-ttu-id="aaf1b-163">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースの肥大を制御するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-163">Follow the steps below to manage the growth of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
#### <a name="the-biztalk-server-messagebox-database-is-growing-unchecked-and-impacting-overall-performance"></a><span data-ttu-id="aaf1b-164">BizTalk Server メッセージ ボックス データベースがチェックされない状態で肥大しており、パフォーマンス全体に影響を与えている</span><span class="sxs-lookup"><span data-stu-id="aaf1b-164">The BizTalk Server MessageBox database is growing unchecked and impacting overall performance</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="aaf1b-165">問題</span><span class="sxs-lookup"><span data-stu-id="aaf1b-165">Problem</span></span>  
 <span data-ttu-id="aaf1b-166">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージ ボックス データベースの肥大によって [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境のパフォーマンスに悪影響が及んでいます。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-166">Growth of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox database is adversely affecting performance of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="aaf1b-167">原因</span><span class="sxs-lookup"><span data-stu-id="aaf1b-167">Cause</span></span>  
 <span data-ttu-id="aaf1b-168">この問題は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースを管理している SQL エージェント ジョブが実行されていない場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-168">This problem can occur if the SQL Agent jobs that maintain the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are not running.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="aaf1b-169">解決策</span><span class="sxs-lookup"><span data-stu-id="aaf1b-169">Resolution</span></span>  
 <span data-ttu-id="aaf1b-170">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースを管理している SQL エージェント ジョブが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-170">Ensure that the SQL Agent jobs that maintain the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are running.</span></span> <span data-ttu-id="aaf1b-171">参照してください[データベース構造とジョブ](../core/database-structure-and-jobs.md)と一緒にインストールされている SQL エージェント ジョブの完全な一覧について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-171">See [Database Structure and Jobs](../core/database-structure-and-jobs.md) for a complete list of the SQL Agent jobs that are installed with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
#### <a name="the-biztalk-server-tracking-database-is-growing-unchecked-and-impacting-overall-performance"></a><span data-ttu-id="aaf1b-172">BizTalk Server 追跡データベースがチェックされない状態で肥大しており、パフォーマンス全体に影響を与えている</span><span class="sxs-lookup"><span data-stu-id="aaf1b-172">The BizTalk Server tracking database is growing unchecked and impacting overall performance</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="aaf1b-173">問題</span><span class="sxs-lookup"><span data-stu-id="aaf1b-173">Problem</span></span>  
 <span data-ttu-id="aaf1b-174">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 追跡データベースがチェックされない状態で肥大しており、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境のパフォーマンス全体に悪影響を及ぼしています。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-174">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tracking database is growing unchecked and is adversely affecting the overall performance of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="aaf1b-175">原因</span><span class="sxs-lookup"><span data-stu-id="aaf1b-175">Cause</span></span>  
 <span data-ttu-id="aaf1b-176">この問題は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 追跡データベースを削除およびアーカイブするための手順が実行されていない場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-176">This problem can occur if steps are not taken to purge and archive the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tracking database.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="aaf1b-177">解決策</span><span class="sxs-lookup"><span data-stu-id="aaf1b-177">Resolution</span></span>  
 <span data-ttu-id="aaf1b-178">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 追跡データベースを削除およびアーカイブするための手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-178">Steps should be taken to purge and archive the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tracking database.</span></span> <span data-ttu-id="aaf1b-179">参照してください[アーカイブ化および BizTalk 追跡データベースを削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="aaf1b-179">See [Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md) for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaf1b-180">参照</span><span class="sxs-lookup"><span data-stu-id="aaf1b-180">See Also</span></span>  
 [<span data-ttu-id="aaf1b-181">SQL Server のアクセス許可の問題を解決するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="aaf1b-181">Guidelines for Resolving SQL Server Permissions Problems</span></span>](../core/guidelines-for-resolving-sql-server-permissions-problems.md)