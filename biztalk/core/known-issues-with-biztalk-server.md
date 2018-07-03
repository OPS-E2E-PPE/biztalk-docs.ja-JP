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
ms.openlocfilehash: 3ab3522254ea7cd965ed1b9172de2c382d214fb6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014459"
---
# <a name="known-issues-with-biztalk-server"></a><span data-ttu-id="24f63-102">BizTalk Server の既知の問題</span><span class="sxs-lookup"><span data-stu-id="24f63-102">Known Issues with BizTalk Server</span></span>
<span data-ttu-id="24f63-103">このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の既知の問題について取り上げます。</span><span class="sxs-lookup"><span data-stu-id="24f63-103">This topic lists some known issues with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="dtc-firewall-rules"></a><span data-ttu-id="24f63-104">DTC ファイアウォール規則</span><span class="sxs-lookup"><span data-stu-id="24f63-104">DTC Firewall Rules</span></span>  
 <span data-ttu-id="24f63-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] および [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] が別のコンピューターにインストールされている場合、Distributed Transaction Coordinator (MS DTC) がコンピューター間のトランザクションを処理します。</span><span class="sxs-lookup"><span data-stu-id="24f63-105">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are installed on separate computers, Distributed Transaction Coordinator (MS DTC) handles the transactions between the computers.</span></span> <span data-ttu-id="24f63-106">そのため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターと [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] コンピューターのファイアウォールの規則で DTC ポートを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="24f63-106">As a result, enable the DTC ports within your firewall rules on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computers.</span></span>  
  
 <span data-ttu-id="24f63-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成するときに、ファイアウォールで DTC ポートが有効になっていない場合、次のエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="24f63-107">When configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the following errors can occur when the DTC ports are not enabled in the firewall:</span></span>  
  
 <span data-ttu-id="24f63-108">**データベースの作成時に WMI エラーが発生しましたロールバックを試行し、部分的に作成されたデータベース 'SQLServerName\BizTalkMsgBoxDb' を削除**</span><span class="sxs-lookup"><span data-stu-id="24f63-108">**WMI Error occurred during database creation; attempt to rollback and delete the partially created database'SQLServerName\BizTalkMsgBoxDb'**</span></span>  
  
 <span data-ttu-id="24f63-109">**WMI エラーの説明が生成されます。 スローされた 'system.enterpriseservices.transactionproxyexception' 型の例外。**</span><span class="sxs-lookup"><span data-stu-id="24f63-109">**WMI error description is generated: Exception of type 'System.EnterpriseServices.TransactionProxyException' was thrown.**</span></span>  
  
 <span data-ttu-id="24f63-110">次のリンクの詳細情報します。</span><span class="sxs-lookup"><span data-stu-id="24f63-110">The following links provide more information:</span></span>  
  
 [<span data-ttu-id="24f63-111">管理サーバーのポート</span><span class="sxs-lookup"><span data-stu-id="24f63-111">Ports for the Administration Server</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=275568)  
  
 [<span data-ttu-id="24f63-112">BizTalk Server 2013 および 2013 R2 のインストール後の手順</span><span class="sxs-lookup"><span data-stu-id="24f63-112">Post-installation Steps for BizTalk Server 2013 and 2013 R2</span></span>](../install-and-config-guides/post-installation-steps-for-biztalk-server-2013-and-2013-r2.md)  
  
##  <a name="BKMK_BAM"></a> <span data-ttu-id="24f63-113">ビジネス アクティビティの監視</span><span class="sxs-lookup"><span data-stu-id="24f63-113">Business Activity Monitoring</span></span>  
 <span data-ttu-id="24f63-114">ここでは、ビジネス アクティビティの監視 (BAM) モジュールの既知の問題の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="24f63-114">This section lists the known issues with the Business Activity Monitoring (BAM) module.</span></span>  
  
### <a name="bam-definition-deployment-fails-due-to-a-sql-login-error"></a><span data-ttu-id="24f63-115">SQL ログイン エラーで BAM 定義の展開に失敗する</span><span class="sxs-lookup"><span data-stu-id="24f63-115">BAM definition deployment fails due to a SQL login error</span></span>  
 <span data-ttu-id="24f63-116">BAM 定義を展開する際、エラー コード 42000 のログイン エラーが原因で操作が失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="24f63-116">While deploying BAM definition, the operation might fail due to a login error with error code 42000.</span></span>  
  
```  
...  
Deploying Activity... Done.   
Deploying View... ERROR: The BAM deployment failed.   
Server: The current operation was cancelled because another operation in the transaction failed.   
OLE DB error: OLE DB or ODBC error: Login failed for user <username>.; 42000.   
…  
```  
  
 <span data-ttu-id="24f63-117">この問題を修正するには、SQL Analysis Service のログイン アカウントに、BAM に関するすべてのデータベースへのアクセス権があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="24f63-117">To fix this issue, make sure the SQL Analysis Service logon account has permissions on all databases related to BAM.</span></span>  
  
### <a name="bam-configuration-might-result-in-warnings-related-to-the-bam-analysis-logon-account"></a><span data-ttu-id="24f63-118">BAM 構成で BAM Analysis ログイン アカウントに関する警告が表示される</span><span class="sxs-lookup"><span data-stu-id="24f63-118">BAM configuration might result in warnings related to the BAM Analysis logon account</span></span>  
 <span data-ttu-id="24f63-119">BAM 構成では、それらにアクセスできる BAM に関連するすべてのデータベースで BAM Analysis ログイン アカウントのアクセス許可を追加します。</span><span class="sxs-lookup"><span data-stu-id="24f63-119">BAM configuration adds the permissions for BAM Analysis logon account in all the databases related to BAM to be able to access them.</span></span> <span data-ttu-id="24f63-120">ただし、次の前提条件を満たさなかった場合はアクセス権の付与に失敗し、警告が表示されます:</span><span class="sxs-lookup"><span data-stu-id="24f63-120">However, the configuration might fail to do so and give a warning if any of the following prerequisites is not met:</span></span>  
  
- <span data-ttu-id="24f63-121">BAM 構成を実行しているユーザーは、Analysis Service がインストールされているコンピューターの管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="24f63-121">The user under which the BAM configuration is run should be an administrator on the computer where Analysis Service is installed.</span></span>  
  
- <span data-ttu-id="24f63-122">そのコンピューターでは、ファイアウォール経由のリモート管理が許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="24f63-122">Remote administration through firewall must be allowed on that computer.</span></span>  
  
- <span data-ttu-id="24f63-123">BAM Analysis のログイン アカウントが、BAM に関するデータベースがインストールされている SQL Server の管理者である場合にも、警告が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="24f63-123">You might also get a warning if the BAM Analysis logon account is an administrator for the SQL Server where the BAM-related databases are installed.</span></span> <span data-ttu-id="24f63-124">警告を無視して次に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="24f63-124">You can ignore the warning and move ahead.</span></span>  
  
  <span data-ttu-id="24f63-125">**回避策**– BAM に関連するすべてのデータベースで BAM Analysis のログイン アカウントに対するアクセス許可を手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24f63-125">**Workaround** – You must manually add the permission for the BAM Analysis logon account on all databases related to BAM.</span></span>  
  
### <a name="bam-portal-compatibility-with-internet-explorer-10"></a><span data-ttu-id="24f63-126">BAM ポータルと Internet Explorer 10 の間の互換性</span><span class="sxs-lookup"><span data-stu-id="24f63-126">BAM Portal Compatibility with Internet Explorer 10</span></span>  
 <span data-ttu-id="24f63-127">Internet Explorer 10 で BAM ポータルを使用するには、常にブラウザーを互換モードで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24f63-127">To use the BAM Portal with Internet Explorer 10, you must always use the browser in Compatibility mode.</span></span>  
  
### <a name="receiving-notification-e-mails-even-after-the-alert-host-service-is-stopped"></a><span data-ttu-id="24f63-128">Alert Host サービスが停止した後であっても通知の電子メールを受信する</span><span class="sxs-lookup"><span data-stu-id="24f63-128">Receiving notification e-mails even after the Alert Host service is stopped</span></span>  
 <span data-ttu-id="24f63-129">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] を併用する場合、BAM 警告を使用する必要があれば、SQL Server でデータベース メール機能を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24f63-129">If you use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)], you must configure the Database Mail feature in SQL Server if you want to use BAM Alerts.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="24f63-130"> では、Alert Host サービスとデータベース メール機能を組み合わせて使用して、通知警告を送信します。</span><span class="sxs-lookup"><span data-stu-id="24f63-130"> uses an Alert Host service in conjunction with the Database Mail feature to send notification alerts.</span></span> <span data-ttu-id="24f63-131">Alert Host サービスは、通知を処理した後、SQL Server のデータベース メール コンポーネントに通知のワークロードを渡します。</span><span class="sxs-lookup"><span data-stu-id="24f63-131">The Alert Host service, after processing the notifications, passes on the notification workload to the Database Mail component in SQL Server.</span></span> <span data-ttu-id="24f63-132">そのため、Alert Host サービスを停止した場合であっても、Alert Host サービスによって処理されたがデータベース メール コンポーネントでは処理されていないイベントに関して、まだいくつかの通知を受け取ることがあります。</span><span class="sxs-lookup"><span data-stu-id="24f63-132">So, even if you stop the Alert Host service, you might still get a few notifications for events that were processed by the Alert Host service but not by the Database Mail component.</span></span>  
  
### <a name="configuring-tracing-for-bam-alerts"></a><span data-ttu-id="24f63-133">BAM 警告のトレースの構成</span><span class="sxs-lookup"><span data-stu-id="24f63-133">Configuring tracing for BAM Alerts</span></span>  
 <span data-ttu-id="24f63-134">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] を併用し、また BAM 警告の診断トレースを有効にする必要がある場合は、BAM 警告のホストに関する構成ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24f63-134">If you are using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)], and you want to enable diagnostic tracing for BAM Alerts, you must do so by creating a config file for the BAM Alerts host.</span></span> <span data-ttu-id="24f63-135">としてファイルに名前を付けて**BAMAlerts.exe.config** 、EXE と同じ場所にコピー (**BAMAlerts.exe**)、\Program Files\Microsoft BizTalk Server\Tracking にある\\。</span><span class="sxs-lookup"><span data-stu-id="24f63-135">You must name the file as **BAMAlerts.exe.config** and copy it to the same location as the EXE (**BAMAlerts.exe**), which is at \Program Files\Microsoft BizTalk Server\Tracking\\.</span></span>  
  
 <span data-ttu-id="24f63-136">構成ファイルのサンプルは以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="24f63-136">A sample config file looks like the following.</span></span> <span data-ttu-id="24f63-137">このファイルに記録**情報**レベルのイベント ビューアーに詳細情報。</span><span class="sxs-lookup"><span data-stu-id="24f63-137">This file logs **Information** level details to the Event Viewer.</span></span>  
  
```  
<configuration>  
  <system.diagnostics>  
    <switches>  
      <add name="LogEventProvider" value="Info"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
##  <a name="BKMK_Upgrade"></a> <span data-ttu-id="24f63-138">SQL Server 2012 で BizTalk Server を使用中の問題</span><span class="sxs-lookup"><span data-stu-id="24f63-138">Issues While Using BizTalk Server with SQL Server 2012</span></span>  
 <span data-ttu-id="24f63-139">使用中に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]を設定することができます、 **Remote Login Timeout** 20 秒に SQL Server での値。</span><span class="sxs-lookup"><span data-stu-id="24f63-139">While using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] you can set the **Remote Login Timeout** value in SQL Server to 20 seconds.</span></span> <span data-ttu-id="24f63-140">このように設定しないと、負荷が高い状況でエラーが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="24f63-140">If you don’t do so, you might encounter errors in stress conditions.</span></span> <span data-ttu-id="24f63-141">リモート ログイン タイムアウト値を設定する方法については[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]を参照してください [http://msdn.microsoft.com/library/ms175136.aspx](http://msdn.microsoft.com/library/ms175136.aspx)</span><span class="sxs-lookup"><span data-stu-id="24f63-141">For instructions on how to set the Remote Login Timeout value in [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)], see [http://msdn.microsoft.com/library/ms175136.aspx](http://msdn.microsoft.com/library/ms175136.aspx)</span></span>  
  
##  <a name="BKMK_Adapters"></a> <span data-ttu-id="24f63-142">アダプターの問題</span><span class="sxs-lookup"><span data-stu-id="24f63-142">Issues with Adapters</span></span>  
 <span data-ttu-id="24f63-143">ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のアダプターに関する既知の問題の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="24f63-143">This section lists the known issues with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapters.</span></span>  
  
### <a name="dynamic-port-may-fail-while-using-the-windows-sharepoint-services-wss-adapter"></a><span data-ttu-id="24f63-144">Windows SharePoint Services (WSS) アダプターを使用している場合に動的ポートでエラーが発生することがある</span><span class="sxs-lookup"><span data-stu-id="24f63-144">Dynamic port may fail while using the Windows SharePoint Services (WSS) adapter</span></span>  
 <span data-ttu-id="24f63-145">WSS アダプターを使用している動的ポートで障害が発生し、次のエラーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="24f63-145">A dynamic port using the WSS adapter may fail with the following error:</span></span>  
  
```  
Error details: The Windows SharePoint Services site was not found. The URL "http://server:443/site" points to a SharePoint object for which there is no Windows SharePoint Services site.  
```  
  
 <span data-ttu-id="24f63-146">**回避策**:</span><span class="sxs-lookup"><span data-stu-id="24f63-146">**Workarounds**:</span></span>  
  
-   <span data-ttu-id="24f63-147">ポートの構成で、サイトの URL にポート番号も含めます。</span><span class="sxs-lookup"><span data-stu-id="24f63-147">In the port configuration, for the site URL, include the port number as well.</span></span> <span data-ttu-id="24f63-148">たとえば、 `http://server:80/site`のようにします。</span><span class="sxs-lookup"><span data-stu-id="24f63-148">For example, `http://server:80/site`.</span></span>  
  
-   <span data-ttu-id="24f63-149">有効にする、 **Windows Identity Foundation 3.5**機能します。</span><span class="sxs-lookup"><span data-stu-id="24f63-149">Enable the **Windows Identity Foundation 3.5** feature.</span></span>  
  
-   <span data-ttu-id="24f63-150">BizTalk ホストを実行しているアカウントが SharePoint へのアクセスを確認します。</span><span class="sxs-lookup"><span data-stu-id="24f63-150">Confirm the account running the BizTalk host has access to SharePoint.</span></span>  
  
### <a name="adapters-available-with-biztalk-adapter-pack-cannot-be-administered-on-a-computer-that-only-has-biztalk-server-administration-component-installed"></a><span data-ttu-id="24f63-151">BizTalk Server 管理コンソールのみがインストールされているコンピューターでは、BizTalk Adapter Pack で使用できるアダプターを管理できない</span><span class="sxs-lookup"><span data-stu-id="24f63-151">Adapters available with BizTalk Adapter Pack cannot be administered on a computer that only has BizTalk Server Administration component installed</span></span>  
 <span data-ttu-id="24f63-152">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールのみがインストールされているコンピューターに BizTalk Adapter Pack をインストールした場合、送信ポートまたは受信場所を作成しても、BizTalk Adapter Pack の一部としてインストールされているアダプターを使用できません。</span><span class="sxs-lookup"><span data-stu-id="24f63-152">If you have BizTalk Adapter Pack installed on a computer that only has the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console installed, the adapters installed as part of the BizTalk Adapter Pack are not available when you create a send port or receive location.</span></span> <span data-ttu-id="24f63-153">これは、これらのアダプターは、同じコンピューターにインストールされている BizTalk ランタイムに依存するためです。</span><span class="sxs-lookup"><span data-stu-id="24f63-153">This is because these adapters have a dependency on the BizTalk Runtime to be installed on the same computer.</span></span>  
  
 <span data-ttu-id="24f63-154">回避策 – Adapter Pack と BizTalk Server 管理コンソールがインストールされているコンピューターに BizTalk Server ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="24f63-154">Workaround – Install the BizTalk Server runtime on the computer that has the Adapter Pack and the BizTalk Server Administration component installed.</span></span> <span data-ttu-id="24f63-155">そのコンピューターで BizTalk Server を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="24f63-155">You need not configure BizTalk Server on that computer.</span></span>  
  
## <a name="other-issues"></a><span data-ttu-id="24f63-156">その他の問題</span><span class="sxs-lookup"><span data-stu-id="24f63-156">Other Issues</span></span>  
  
### <a name="setupbat-for-biztalk-server-samples-runs-with-a-32-bit-command-prompt"></a><span data-ttu-id="24f63-157">BizTalk Server のサンプルの setup.bat が 32 ビットのコマンド プロンプトで実行される</span><span class="sxs-lookup"><span data-stu-id="24f63-157">Setup.bat for BizTalk Server Samples Runs with a 32-bit Command Prompt</span></span>  
 <span data-ttu-id="24f63-158">このリリースに付属する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のサンプルに関して、付随する setup.bat ファイルは、32 ビットのコマンド プロンプトからのみ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24f63-158">For the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] samples shipped with this release, you must run the accompanying setup.bat files only from a 32-bit command prompt.</span></span> <span data-ttu-id="24f63-159">64 ビットのコマンド プロンプトからバッチ ファイルを実行すると、エラーが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="24f63-159">Running the batch files from a 64-bit command prompt might result in a failure.</span></span>  
  
### <a name="run-setup-as-administrator"></a><span data-ttu-id="24f63-160">管理者としてセットアップを実行する</span><span class="sxs-lookup"><span data-stu-id="24f63-160">Run setup as Administrator</span></span>  
 <span data-ttu-id="24f63-161">インストールするときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用して、**管理者として実行**オプション。</span><span class="sxs-lookup"><span data-stu-id="24f63-161">When installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], use the **Run as Administrator** option.</span></span> <span data-ttu-id="24f63-162">このオプションを使用しない場合、次のエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="24f63-162">Otherwise, the following errors may occur:</span></span>  
  
 <span data-ttu-id="24f63-163">内部エラー 2761 です。</span><span class="sxs-lookup"><span data-stu-id="24f63-163">Internal Error 2761.</span></span> <span data-ttu-id="24f63-164">リターン コード: 1</span><span class="sxs-lookup"><span data-stu-id="24f63-164">Return Code: 1</span></span>  
  
 <span data-ttu-id="24f63-165">MSI のインストールには、1603 - インストール中に致命的なエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="24f63-165">MSI installation returned 1603 - Fatal error during installation.</span></span>  
  
### <a name="using-certificates-with-1024-key-for-encoding-and-signing-results-in-failure-of-mime-smime-decoding"></a><span data-ttu-id="24f63-166">1024 キーを含む証明書をエンコードと署名に使用すると、MIME-SMIME デコードでエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="24f63-166">Using certificates with 1024 key for encoding and signing results in failure of MIME-SMIME decoding</span></span>  
 <span data-ttu-id="24f63-167">Windows 8 では、1024 キーを含む証明書を使用してメッセージが暗号化および署名されている場合、メッセージの認証で MIME-SMIME デコードにエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="24f63-167">On Windows 8, when a message is encrypted and signed using certificates with 1024 key, MIME-SMIME decoding fails in authenticating the message.</span></span> <span data-ttu-id="24f63-168">この問題を回避するには、2048 キーを含む証明書を使用する方法があります。</span><span class="sxs-lookup"><span data-stu-id="24f63-168">To avoid this issue, you can use certificates with 2048 key.</span></span>  
  
### <a name="uddi-resolver-with-esb-toolkit-gives-a-serialization-error"></a><span data-ttu-id="24f63-169">ESB Toolkit を使用する UDDI リゾルバーでシリアル化エラーが発生する</span><span class="sxs-lookup"><span data-stu-id="24f63-169">UDDI resolver with ESB Toolkit gives a Serialization error</span></span>  
 <span data-ttu-id="24f63-170">[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] で UDDI を使用している場合、バインドの詳細を検索するときに、XML シリアル化エラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="24f63-170">While using UDDI with the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] you might encounter an XML serialization error when looking up the binding details.</span></span> <span data-ttu-id="24f63-171">このエラーは、バインドのキーが指定されていない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="24f63-171">This error occurs if the binding key is not specified.</span></span>  
  
### <a name="the-itinerary-designer-for-esb-toolkit"></a><span data-ttu-id="24f63-172">ESB Toolkit の Itinerary Designer</span><span class="sxs-lookup"><span data-stu-id="24f63-172">The itinerary designer for ESB Toolkit</span></span>  
 <span data-ttu-id="24f63-173">[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] の Itinerary Designer は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストール メディアの一部として収録されています。</span><span class="sxs-lookup"><span data-stu-id="24f63-173">The itinerary designer for the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] is now part of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation media.</span></span> <span data-ttu-id="24f63-174">Itinerary Designer はメディアのルート フォルダーにあり、名前は `Microsoft.Practices.Services.Itinerary.DslPackage.vsix` です。</span><span class="sxs-lookup"><span data-stu-id="24f63-174">You can find the itinerary designer at the root folder of the media and has the name `Microsoft.Practices.Services.Itinerary.DslPackage.vsix`.</span></span> <span data-ttu-id="24f63-175">以前は、このファイルは、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] のインストール場所 (通常は \Program Files\Microsoft [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]) にありました。</span><span class="sxs-lookup"><span data-stu-id="24f63-175">Earlier, this file was available at the location where you install the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)], which typically is \Program Files\Microsoft [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].</span></span>  
  
### <a name="edi"></a><span data-ttu-id="24f63-176">EDI </span><span class="sxs-lookup"><span data-stu-id="24f63-176">EDI</span></span>  
 <span data-ttu-id="24f63-177">EDI バッチ処理が使用されます。</span><span class="sxs-lookup"><span data-stu-id="24f63-177">EDI Batching is being used.</span></span> <span data-ttu-id="24f63-178">アラビア語のカレンダーまたはローカル設定を使用する場合、オーケストレーションが中断され、次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="24f63-178">When using an Arabic calendar or Arabic local settings, the orchestration suspends with the following error:</span></span>  
  
 <span data-ttu-id="24f63-179">**エラー コード: 0xC0C01B52 (オーケストレーション エンジン エラー) エラーの説明: 退避中に永続化エラーにより中断されました。**</span><span class="sxs-lookup"><span data-stu-id="24f63-179">**Error Code: 0xC0C01B52 (Orchestration Engine Error)Error Description: Suspend due to persistence failure during dehydration.**</span></span> <span data-ttu-id="24f63-180">アラビア語のグレゴリオ暦の日付をサポートしている*04/30/1900 00.00.00*に*2029 13/05/23時 59分: 59*します。</span><span class="sxs-lookup"><span data-stu-id="24f63-180">Arabic Gregorian supports dates from *04/30/1900 00.00.00* to *05/13/2029 23:59:59*.</span></span>  
  
 <span data-ttu-id="24f63-181">この現象を解決するには、有効なアラビア語の終了日を入力します。</span><span class="sxs-lookup"><span data-stu-id="24f63-181">To resolve this behavior, enter a valid Arabic end date.</span></span>  
  
### <a name="enterprise-single-sign-on"></a><span data-ttu-id="24f63-182">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="24f63-182">Enterprise Single Sign-On</span></span>  
 <span data-ttu-id="24f63-183">エンタープライズ シングル サインオン (ESSO) をインストールする際、または ESSO サービスを再起動する際は、イベント ビューアーに記録される次のエラーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="24f63-183">When you install Enterprise Single Sign-On (ESSO) or when you restart the ESSO service you might see the following error logged in the Event Viewer.</span></span>  
  
 <span data-ttu-id="24f63-184">**\Program Files\Common \enterprise シングル サインオン \ssopsserver.dll エラー コードの読み込みに失敗しました: 0x8007007E、指定されたモジュールは見つかりませんでした。**</span><span class="sxs-lookup"><span data-stu-id="24f63-184">**Failed to load \Program Files\Common Files\Enterprise Single Sign-On\SSOPSServer.dll Error code: 0x8007007E, The specified module could not be found.**</span></span> <span data-ttu-id="24f63-185">このエラーを無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="24f63-185">You can safely ignore this error.</span></span>