---
title: BizTalk Server に関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1aa5fb60-e8db-4cd2-88be-3c71b7b1d44d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4f933555f4643fb293d6fad882950eaf2f15ac6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330567"
---
# <a name="known-issues-with-biztalk-server"></a><span data-ttu-id="83a40-102">BizTalk Server に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="83a40-102">Known Issues with BizTalk Server</span></span>
<span data-ttu-id="83a40-103">このトピックでは、いくつかの既知の問題を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="83a40-103">This topic lists some known issues with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="dtc-firewall-rules"></a><span data-ttu-id="83a40-104">DTC ファイアウォール規則</span><span class="sxs-lookup"><span data-stu-id="83a40-104">DTC Firewall Rules</span></span>  
 <span data-ttu-id="83a40-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] および [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] が別のコンピューターにインストールされている場合、Distributed Transaction Coordinator (MS DTC) がコンピューター間のトランザクションを処理します。</span><span class="sxs-lookup"><span data-stu-id="83a40-105">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are installed on separate computers, Distributed Transaction Coordinator (MS DTC) handles the transactions between the computers.</span></span> <span data-ttu-id="83a40-106">その結果でファイアウォールの規則で DTC ポートを有効にする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="83a40-106">As a result, enable the DTC ports within your firewall rules on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computers.</span></span>  
  
 <span data-ttu-id="83a40-107">構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ファイアウォールで DTC ポートが有効でない場合、次のエラーが発生する可能性が。</span><span class="sxs-lookup"><span data-stu-id="83a40-107">When configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the following errors can occur when the DTC ports are not enabled in the firewall:</span></span>  
  
 <span data-ttu-id="83a40-108">**データベースの作成時に WMI エラーが発生しましたロールバックを試行し、部分的に作成されたデータベース 'SQLServerName\BizTalkMsgBoxDb' を削除**</span><span class="sxs-lookup"><span data-stu-id="83a40-108">**WMI Error occurred during database creation; attempt to rollback and delete the partially created database'SQLServerName\BizTalkMsgBoxDb'**</span></span>  
  
 <span data-ttu-id="83a40-109">**WMI エラーの説明が生成されます。'System.enterpriseservices.transactionproxyexception' 型の例外がスローされました。**</span><span class="sxs-lookup"><span data-stu-id="83a40-109">**WMI error description is generated: Exception of type 'System.EnterpriseServices.TransactionProxyException' was thrown.**</span></span>  
  
 <span data-ttu-id="83a40-110">次のリンクの詳細情報します。</span><span class="sxs-lookup"><span data-stu-id="83a40-110">The following links provide more information:</span></span>  
  
 [<span data-ttu-id="83a40-111">管理サーバーのポート</span><span class="sxs-lookup"><span data-stu-id="83a40-111">Ports for the Administration Server</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=275568)  
  
 [<span data-ttu-id="83a40-112">BizTalk Server 2013 および 2013 R2 のインストール後の手順</span><span class="sxs-lookup"><span data-stu-id="83a40-112">Post-installation Steps for BizTalk Server 2013 and 2013 R2</span></span>](../install-and-config-guides/post-installation-steps-for-biztalk-server-2013-and-2013-r2.md)  
  
##  <a name="BKMK_BAM"></a> <span data-ttu-id="83a40-113">ビジネス アクティビティの監視</span><span class="sxs-lookup"><span data-stu-id="83a40-113">Business Activity Monitoring</span></span>  
 <span data-ttu-id="83a40-114">このセクションでは、ビジネス アクティビティ監視 (BAM) モジュールでは、既知の問題が一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="83a40-114">This section lists the known issues with the Business Activity Monitoring (BAM) module.</span></span>  
  
### <a name="bam-definition-deployment-fails-due-to-a-sql-login-error"></a><span data-ttu-id="83a40-115">SQL ログイン エラーのため失敗した BAM 定義の展開</span><span class="sxs-lookup"><span data-stu-id="83a40-115">BAM definition deployment fails due to a SQL login error</span></span>  
 <span data-ttu-id="83a40-116">BAM 定義をデプロイするときに、操作がエラー コード 42000 のログイン エラーのため失敗します。</span><span class="sxs-lookup"><span data-stu-id="83a40-116">While deploying BAM definition, the operation might fail due to a login error with error code 42000.</span></span>  
  
```  
...  
Deploying Activity... Done.   
Deploying View... ERROR: The BAM deployment failed.   
Server: The current operation was cancelled because another operation in the transaction failed.   
OLE DB error: OLE DB or ODBC error: Login failed for user <username>.; 42000.   
…  
```  
  
 <span data-ttu-id="83a40-117">この問題を修正するには、SQL Analysis サービス ログオン アカウントは、BAM に関連するすべてのデータベースに対する権限を持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="83a40-117">To fix this issue, make sure the SQL Analysis Service logon account has permissions on all databases related to BAM.</span></span>  
  
### <a name="bam-configuration-might-result-in-warnings-related-to-the-bam-analysis-logon-account"></a><span data-ttu-id="83a40-118">BAM の構成は、BAM Analysis のログイン アカウントに関連する警告を可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83a40-118">BAM configuration might result in warnings related to the BAM Analysis logon account</span></span>  
 <span data-ttu-id="83a40-119">BAM 構成では、それらにアクセスできる BAM に関連するすべてのデータベースで BAM Analysis ログイン アカウントのアクセス許可を追加します。</span><span class="sxs-lookup"><span data-stu-id="83a40-119">BAM configuration adds the permissions for BAM Analysis logon account in all the databases related to BAM to be able to access them.</span></span> <span data-ttu-id="83a40-120">ただし、構成が失敗するようにし、次の前提条件のいずれかが満たされない場合に警告を提供します。</span><span class="sxs-lookup"><span data-stu-id="83a40-120">However, the configuration might fail to do so and give a warning if any of the following prerequisites is not met:</span></span>  
  
- <span data-ttu-id="83a40-121">BAM 構成を実行するユーザーは、Analysis Service がインストールされているコンピューターの管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="83a40-121">The user under which the BAM configuration is run should be an administrator on the computer where Analysis Service is installed.</span></span>  
  
- <span data-ttu-id="83a40-122">そのコンピューターでは、ファイアウォール経由のリモート管理を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83a40-122">Remote administration through firewall must be allowed on that computer.</span></span>  
  
- <span data-ttu-id="83a40-123">BAM Analysis のログイン アカウントが BAM に関連するデータベースがインストールされている SQL Server の管理者である場合は、警告を取得することも可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83a40-123">You might also get a warning if the BAM Analysis logon account is an administrator for the SQL Server where the BAM-related databases are installed.</span></span> <span data-ttu-id="83a40-124">警告を無視して進むことができます。</span><span class="sxs-lookup"><span data-stu-id="83a40-124">You can ignore the warning and move ahead.</span></span>  
  
  <span data-ttu-id="83a40-125">**回避策**– BAM に関連するすべてのデータベースで BAM Analysis のログイン アカウントに対するアクセス許可を手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83a40-125">**Workaround** – You must manually add the permission for the BAM Analysis logon account on all databases related to BAM.</span></span>  
  
### <a name="bam-portal-compatibility-with-internet-explorer-10"></a><span data-ttu-id="83a40-126">Internet Explorer 10 で BAM ポータルの互換性</span><span class="sxs-lookup"><span data-stu-id="83a40-126">BAM Portal Compatibility with Internet Explorer 10</span></span>  
 <span data-ttu-id="83a40-127">Internet Explorer 10 では、BAM ポータルを使用するには、常に互換モードでブラウザーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83a40-127">To use the BAM Portal with Internet Explorer 10, you must always use the browser in Compatibility mode.</span></span>  
  
### <a name="receiving-notification-e-mails-even-after-the-alert-host-service-is-stopped"></a><span data-ttu-id="83a40-128">Alert Host 後も通知の電子メールを受信するサービスが停止しました</span><span class="sxs-lookup"><span data-stu-id="83a40-128">Receiving notification e-mails even after the Alert Host service is stopped</span></span>  
 <span data-ttu-id="83a40-129">使用する場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]、BAM 警告を使用する場合は、SQL Server でデータベース メール機能を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83a40-129">If you use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)], you must configure the Database Mail feature in SQL Server if you want to use BAM Alerts.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="83a40-130">データベース メール機能と組み合わせて、Alert Host サービスを使用して、アラートの通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="83a40-130">uses an Alert Host service in conjunction with the Database Mail feature to send notification alerts.</span></span> <span data-ttu-id="83a40-131">Alert Host サービス、通知の処理後に通知のワークロードに渡します SQL server データベース メール コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="83a40-131">The Alert Host service, after processing the notifications, passes on the notification workload to the Database Mail component in SQL Server.</span></span> <span data-ttu-id="83a40-132">そう、Alert Host サービスを停止する場合でも、データベース メール コンポーネントではありませんが、Alert Host サービスによって処理されたイベントのいくつかの通知をする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83a40-132">So, even if you stop the Alert Host service, you might still get a few notifications for events that were processed by the Alert Host service but not by the Database Mail component.</span></span>  
  
### <a name="configuring-tracing-for-bam-alerts"></a><span data-ttu-id="83a40-133">BAM 警告のトレースの構成</span><span class="sxs-lookup"><span data-stu-id="83a40-133">Configuring tracing for BAM Alerts</span></span>  
 <span data-ttu-id="83a40-134">使用する場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]、BAM 警告の診断トレースを有効にしては、BAM 警告のホストの構成ファイルを作成して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="83a40-134">If you are using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)], and you want to enable diagnostic tracing for BAM Alerts, you must do so by creating a config file for the BAM Alerts host.</span></span> <span data-ttu-id="83a40-135">としてファイルに名前を付けて**BAMAlerts.exe.config** 、EXE と同じ場所にコピー (**BAMAlerts.exe**)、\Program Files\Microsoft BizTalk Server\Tracking にある\\。</span><span class="sxs-lookup"><span data-stu-id="83a40-135">You must name the file as **BAMAlerts.exe.config** and copy it to the same location as the EXE (**BAMAlerts.exe**), which is at \Program Files\Microsoft BizTalk Server\Tracking\\.</span></span>  
  
 <span data-ttu-id="83a40-136">構成ファイルのサンプルは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="83a40-136">A sample config file looks like the following.</span></span> <span data-ttu-id="83a40-137">このファイルに記録**情報**レベルのイベント ビューアーに詳細情報。</span><span class="sxs-lookup"><span data-stu-id="83a40-137">This file logs **Information** level details to the Event Viewer.</span></span>  
  
```  
<configuration>  
  <system.diagnostics>  
    <switches>  
      <add name="LogEventProvider" value="Info"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
##  <a name="BKMK_Upgrade"></a> <span data-ttu-id="83a40-138">SQL Server 2012 で BizTalk Server を使用中の問題</span><span class="sxs-lookup"><span data-stu-id="83a40-138">Issues While Using BizTalk Server with SQL Server 2012</span></span>  
 <span data-ttu-id="83a40-139">使用中に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]を設定することができます、 **Remote Login Timeout** 20 秒に SQL Server での値。</span><span class="sxs-lookup"><span data-stu-id="83a40-139">While using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] you can set the **Remote Login Timeout** value in SQL Server to 20 seconds.</span></span> <span data-ttu-id="83a40-140">そうしな場合ストレス条件でエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83a40-140">If you don’t do so, you might encounter errors in stress conditions.</span></span> <span data-ttu-id="83a40-141">リモート ログイン タイムアウト値を設定する方法については[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]を参照してください [http://msdn.microsoft.com/library/ms175136.aspx](http://msdn.microsoft.com/library/ms175136.aspx)</span><span class="sxs-lookup"><span data-stu-id="83a40-141">For instructions on how to set the Remote Login Timeout value in [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)], see [http://msdn.microsoft.com/library/ms175136.aspx](http://msdn.microsoft.com/library/ms175136.aspx)</span></span>  
  
##  <a name="BKMK_Adapters"></a> <span data-ttu-id="83a40-142">アダプターの問題</span><span class="sxs-lookup"><span data-stu-id="83a40-142">Issues with Adapters</span></span>  
 <span data-ttu-id="83a40-143">このセクションの既知の問題を一覧表示、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプター。</span><span class="sxs-lookup"><span data-stu-id="83a40-143">This section lists the known issues with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapters.</span></span>  
  
### <a name="dynamic-port-may-fail-while-using-the-windows-sharepoint-services-wss-adapter"></a><span data-ttu-id="83a40-144">Windows SharePoint Services (WSS) アダプターを使用しているときに動的なポートが失敗します。</span><span class="sxs-lookup"><span data-stu-id="83a40-144">Dynamic port may fail while using the Windows SharePoint Services (WSS) adapter</span></span>  
 <span data-ttu-id="83a40-145">WSS アダプターを使用して動的なポートは、次のエラーで失敗します。</span><span class="sxs-lookup"><span data-stu-id="83a40-145">A dynamic port using the WSS adapter may fail with the following error:</span></span>  
  
```  
Error details: The Windows SharePoint Services site was not found. The URL "http://server:443/site" points to a SharePoint object for which there is no Windows SharePoint Services site.  
```  
  
 <span data-ttu-id="83a40-146">**回避策**:</span><span class="sxs-lookup"><span data-stu-id="83a40-146">**Workarounds**:</span></span>  
  
-   <span data-ttu-id="83a40-147">ポートの構成で、サイトの URL のポート番号も含まれます。</span><span class="sxs-lookup"><span data-stu-id="83a40-147">In the port configuration, for the site URL, include the port number as well.</span></span> <span data-ttu-id="83a40-148">たとえば、`http://server:80/site` のようにします。</span><span class="sxs-lookup"><span data-stu-id="83a40-148">For example, `http://server:80/site`.</span></span>  
  
-   <span data-ttu-id="83a40-149">有効にする、 **Windows Identity Foundation 3.5**機能します。</span><span class="sxs-lookup"><span data-stu-id="83a40-149">Enable the **Windows Identity Foundation 3.5** feature.</span></span>  
  
-   <span data-ttu-id="83a40-150">BizTalk ホストを実行しているアカウントが SharePoint へのアクセスを確認します。</span><span class="sxs-lookup"><span data-stu-id="83a40-150">Confirm the account running the BizTalk host has access to SharePoint.</span></span>  
  
### <a name="adapters-available-with-biztalk-adapter-pack-cannot-be-administered-on-a-computer-that-only-has-biztalk-server-administration-component-installed"></a><span data-ttu-id="83a40-151">BizTalk Server 管理コンポーネントがインストールされているコンピューターで BizTalk Adapter Pack で使用できるアダプターを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="83a40-151">Adapters available with BizTalk Adapter Pack cannot be administered on a computer that only has BizTalk Server Administration component installed</span></span>  
 <span data-ttu-id="83a40-152">BizTalk Adapter Pack ののみされているコンピューターにインストールされているかどうかがある、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールがインストールされている、BizTalk Adapter Pack の一部としてインストールされているアダプターを利用できません送信ポートを作成するか、受信場所。</span><span class="sxs-lookup"><span data-stu-id="83a40-152">If you have BizTalk Adapter Pack installed on a computer that only has the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console installed, the adapters installed as part of the BizTalk Adapter Pack are not available when you create a send port or receive location.</span></span> <span data-ttu-id="83a40-153">これらのアダプターが同じコンピューターにインストールされる BizTalk ランタイムで依存関係を持つためにです。</span><span class="sxs-lookup"><span data-stu-id="83a40-153">This is because these adapters have a dependency on the BizTalk Runtime to be installed on the same computer.</span></span>  
  
 <span data-ttu-id="83a40-154">回避策 – Adapter Pack と BizTalk Server 管理コンポーネントをインストールしたコンピューター上の BizTalk Server ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="83a40-154">Workaround – Install the BizTalk Server runtime on the computer that has the Adapter Pack and the BizTalk Server Administration component installed.</span></span> <span data-ttu-id="83a40-155">コンピューターに BizTalk Server を構成する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="83a40-155">You need not configure BizTalk Server on that computer.</span></span>  
  
## <a name="other-issues"></a><span data-ttu-id="83a40-156">その他の問題</span><span class="sxs-lookup"><span data-stu-id="83a40-156">Other Issues</span></span>  
  
### <a name="setupbat-for-biztalk-server-samples-runs-with-a-32-bit-command-prompt"></a><span data-ttu-id="83a40-157">BizTalk Server の Setup.bat サンプルの 32 ビット コマンド プロンプトで実行します。</span><span class="sxs-lookup"><span data-stu-id="83a40-157">Setup.bat for BizTalk Server Samples Runs with a 32-bit Command Prompt</span></span>  
 <span data-ttu-id="83a40-158">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]このリリースに付属のサンプル、32 ビット コマンド プロンプトからのみ付随する setup.bat ファイルを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83a40-158">For the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] samples shipped with this release, you must run the accompanying setup.bat files only from a 32-bit command prompt.</span></span> <span data-ttu-id="83a40-159">64 ビット コマンド プロンプトからバッチ ファイルを実行するいると、失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83a40-159">Running the batch files from a 64-bit command prompt might result in a failure.</span></span>  
  
### <a name="run-setup-as-administrator"></a><span data-ttu-id="83a40-160">セットアップを管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="83a40-160">Run setup as Administrator</span></span>  
 <span data-ttu-id="83a40-161">インストールするときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用して、**管理者として実行**オプション。</span><span class="sxs-lookup"><span data-stu-id="83a40-161">When installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], use the **Run as Administrator** option.</span></span> <span data-ttu-id="83a40-162">それ以外の場合、次のエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83a40-162">Otherwise, the following errors may occur:</span></span>  
  
 <span data-ttu-id="83a40-163">内部エラー 2761 です。</span><span class="sxs-lookup"><span data-stu-id="83a40-163">Internal Error 2761.</span></span> <span data-ttu-id="83a40-164">コードが返されます。1</span><span class="sxs-lookup"><span data-stu-id="83a40-164">Return Code: 1</span></span>  
  
 <span data-ttu-id="83a40-165">MSI のインストールには、1603 - インストール中に致命的なエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="83a40-165">MSI installation returned 1603 - Fatal error during installation.</span></span>  
  
### <a name="using-certificates-with-1024-key-for-encoding-and-signing-results-in-failure-of-mime-smime-decoding"></a><span data-ttu-id="83a40-166">1024 キーのエンコードと、MIME-SMIME デコードの失敗の結果を署名証明書の使用</span><span class="sxs-lookup"><span data-stu-id="83a40-166">Using certificates with 1024 key for encoding and signing results in failure of MIME-SMIME decoding</span></span>  
 <span data-ttu-id="83a40-167">Windows 8 の場合、メッセージが暗号化され、1024 キーを持つ証明書を使用して署名したときに、MIME-SMIME デコードでメッセージの認証が失敗します。</span><span class="sxs-lookup"><span data-stu-id="83a40-167">On Windows 8, when a message is encrypted and signed using certificates with 1024 key, MIME-SMIME decoding fails in authenticating the message.</span></span> <span data-ttu-id="83a40-168">この問題を回避するには、2048 キーを持つ証明書を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="83a40-168">To avoid this issue, you can use certificates with 2048 key.</span></span>  
  
### <a name="uddi-resolver-with-esb-toolkit-gives-a-serialization-error"></a><span data-ttu-id="83a40-169">ESB Toolkit を使用した UDDI リゾルバーでシリアル化エラー</span><span class="sxs-lookup"><span data-stu-id="83a40-169">UDDI resolver with ESB Toolkit gives a Serialization error</span></span>  
 <span data-ttu-id="83a40-170">UDDI を使用して、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]バインディングの詳細の検索時に XML シリアル化エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83a40-170">While using UDDI with the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] you might encounter an XML serialization error when looking up the binding details.</span></span> <span data-ttu-id="83a40-171">このエラーは、バインド キーが指定されていない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="83a40-171">This error occurs if the binding key is not specified.</span></span>  
  
### <a name="the-itinerary-designer-for-esb-toolkit"></a><span data-ttu-id="83a40-172">ESB Toolkit の itinerary designer</span><span class="sxs-lookup"><span data-stu-id="83a40-172">The itinerary designer for ESB Toolkit</span></span>  
 <span data-ttu-id="83a40-173">Itinerary designer、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]の一部になりましたが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール メディア。</span><span class="sxs-lookup"><span data-stu-id="83a40-173">The itinerary designer for the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] is now part of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation media.</span></span> <span data-ttu-id="83a40-174">Itinerary designer で、メディアのルート フォルダーを見つけることができ、名前を持つ`Microsoft.Practices.Services.Itinerary.DslPackage.vsix`します。</span><span class="sxs-lookup"><span data-stu-id="83a40-174">You can find the itinerary designer at the root folder of the media and has the name `Microsoft.Practices.Services.Itinerary.DslPackage.vsix`.</span></span> <span data-ttu-id="83a40-175">以前では、このファイルが使用可能なインストールする場所に、 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]、通常は \Program Files\Microsoft[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="83a40-175">Earlier, this file was available at the location where you install the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)], which typically is \Program Files\Microsoft [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].</span></span>  
  
### <a name="edi"></a><span data-ttu-id="83a40-176">EDI </span><span class="sxs-lookup"><span data-stu-id="83a40-176">EDI</span></span>  
 <span data-ttu-id="83a40-177">EDI バッチ処理が使用されています。</span><span class="sxs-lookup"><span data-stu-id="83a40-177">EDI Batching is being used.</span></span> <span data-ttu-id="83a40-178">アラビア語のカレンダーまたはローカル設定を使用する場合、オーケストレーションを次のエラーで中断します。</span><span class="sxs-lookup"><span data-stu-id="83a40-178">When using an Arabic calendar or Arabic local settings, the orchestration suspends with the following error:</span></span>  
  
 <span data-ttu-id="83a40-179">**エラー コード:0xC0C01B52 (オーケストレーション エンジン エラー) エラーの説明:退避中に永続化エラーにより中断されました。**</span><span class="sxs-lookup"><span data-stu-id="83a40-179">**Error Code: 0xC0C01B52 (Orchestration Engine Error)Error Description: Suspend due to persistence failure during dehydration.**</span></span> <span data-ttu-id="83a40-180">アラビア語のグレゴリオ暦の日付をサポートしている*04/30/1900 00.00.00*に*2029 13/05/23時 59分: 59*します。</span><span class="sxs-lookup"><span data-stu-id="83a40-180">Arabic Gregorian supports dates from *04/30/1900 00.00.00* to *05/13/2029 23:59:59*.</span></span>  
  
 <span data-ttu-id="83a40-181">この問題を解決するには、有効なアラビア語の終了日を入力します。</span><span class="sxs-lookup"><span data-stu-id="83a40-181">To resolve this behavior, enter a valid Arabic end date.</span></span>  
  
### <a name="enterprise-single-sign-on"></a><span data-ttu-id="83a40-182">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="83a40-182">Enterprise Single Sign-On</span></span>  
 <span data-ttu-id="83a40-183">エンタープライズ シングル サインオン (ESSO) をインストールするとき、または ESSO サービスを再起動するときは、イベント ビューアーにログインして、次のエラー表示があります。</span><span class="sxs-lookup"><span data-stu-id="83a40-183">When you install Enterprise Single Sign-On (ESSO) or when you restart the ESSO service you might see the following error logged in the Event Viewer.</span></span>  
  
 <span data-ttu-id="83a40-184">**\Program Files\Common \enterprise シングル サインオン \ssopsserver.dll エラー コードの読み込みに失敗しました。0x8007007E、指定したモジュールが見つかりませんでした。**</span><span class="sxs-lookup"><span data-stu-id="83a40-184">**Failed to load \Program Files\Common Files\Enterprise Single Sign-On\SSOPSServer.dll Error code: 0x8007007E, The specified module could not be found.**</span></span> <span data-ttu-id="83a40-185">このエラーを無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="83a40-185">You can safely ignore this error.</span></span>