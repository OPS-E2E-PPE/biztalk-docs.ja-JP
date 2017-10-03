---
title: "BAM 警告の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, alerts
- alerts, timeout values
- Notification Services, configuration tips
- alerts, configuring
- managing [BAM definitions], configuring alerts
ms.assetid: 29327466-c8e9-41e8-bc12-f3ac6b5d3096
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46ddba35a603217660df22668d548ca7c40eb5f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-bam-alerts"></a><span data-ttu-id="8ad56-102">BAM 警告の構成</span><span class="sxs-lookup"><span data-stu-id="8ad56-102">Configuring BAM Alerts</span></span>
<span data-ttu-id="8ad56-103">管理者は、BAM 警告フレームワークの特定の要素を変更できます。</span><span class="sxs-lookup"><span data-stu-id="8ad56-103">Administrators can modify certain elements of the BAM alert framework.</span></span> <span data-ttu-id="8ad56-104">このトピックでは、管理者が使用できる構成オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8ad56-104">This topic describes the configuration options available to administrators.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ad56-105">警告を作成するときは、時刻データが OLAP データベース、スター スキーマ データベース、および Notification Services データベースにローカル時刻形式で格納されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8ad56-105">When creating alerts you should be aware that time data is stored in a Local Time format on the OLAP, Star Schema, and Notification Services databases.</span></span> <span data-ttu-id="8ad56-106">また、これら 3 つのデータベースは同じタイム ゾーンに属していることが前提となります。</span><span class="sxs-lookup"><span data-stu-id="8ad56-106">It is also assumed that all three databases are in the same time zone.</span></span> <span data-ttu-id="8ad56-107">プライマリ インポート データベースには、情報が UTC 時刻形式で格納されます。このデータベースは必ずしも同じタイム ゾーンに属している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8ad56-107">On the Primary Import database, information is stored in the UTC time format and can be in the same or different time zone.</span></span>  
  
## <a name="changing-the-adf-configuration"></a><span data-ttu-id="8ad56-108">ADF 構成の変更</span><span class="sxs-lookup"><span data-stu-id="8ad56-108">Changing the ADF configuration</span></span>  
 <span data-ttu-id="8ad56-109">BAM 管理ユーティリティでは、bm.exe.config ファイルで指定された CommandTimeout の値を使用して、Notification Services アプリケーション定義ファイルを事前設定のビューを展開するときに\<EventRule >\\< ActionTimeout\>要素。</span><span class="sxs-lookup"><span data-stu-id="8ad56-109">When deploying a view the BAM Management utility uses the CommandTimeout value specified in the bm.exe.config file to populate Notification Services application definition file \<EventRule>\\<ActionTimeout\> element.</span></span>  
  
 <span data-ttu-id="8ad56-110">bm.exe.config の CommandTimeout の値を変更しても、変更前に展開したビューの CommandTimeout の値は変更されません。</span><span class="sxs-lookup"><span data-stu-id="8ad56-110">Changing the value of CommandTimeout in bm.exe.config does not change the CommandTimeout value for views deployed prior to the change.</span></span>  
  
 <span data-ttu-id="8ad56-111">次の手順では、ProcessBamNSFiles.vbs を使用して、構成と Notification Services アプリケーションの定義ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="8ad56-111">The procedure below uses the ProcessBamNSFiles.vbs to obtain the configuration and the Notification Services application definition file.</span></span> <span data-ttu-id="8ad56-112">スクリプトの詳細については、次を参照してください。 [Notification Services の構成ファイル用の BAM コマンド ライン スクリプト](../core/bam-command-line-script-for-notification-services-configuration-files.md)です。</span><span class="sxs-lookup"><span data-stu-id="8ad56-112">For more information on the script, see [BAM Command-Line Script for Notification Services Configuration Files](../core/bam-command-line-script-for-notification-services-configuration-files.md).</span></span>  
  
 <span data-ttu-id="8ad56-113">既に展開されているビューの NS の ActionTimeout を変更する方法</span><span class="sxs-lookup"><span data-stu-id="8ad56-113">How to change the ActionTimeout for NS for already deployed views:</span></span>  
  
#### <a name="to-change-the-command-timeout-value"></a><span data-ttu-id="8ad56-114">コマンドのタイムアウト値を変更するには</span><span class="sxs-lookup"><span data-stu-id="8ad56-114">To change the command timeout value</span></span>  
  
1.  <span data-ttu-id="8ad56-115">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="8ad56-115">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="8ad56-116">コマンド プロンプトで入力して、追跡フォルダーに移動**cd"C:\Program files \microsoft BizTalk Server\<バージョン > \Tracking"**または**cd"C:\Program Files (x86) \Microsoft BizTalk Server \<バージョン > \Tracking"** 64 ビット コンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="8ad56-116">Navigate to the tracking folder by typing at the command prompt **cd “C:\Program Files\Microsoft BizTalk Server \<version>\Tracking”** or **cd “C:\Program Files (x86)\Microsoft BizTalk Server \<version>\Tracking”** on a 64 bit computer.</span></span> <span data-ttu-id="8ad56-117">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8ad56-117">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="8ad56-118">ADF ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="8ad56-118">Retrieve the ADF file.</span></span> <span data-ttu-id="8ad56-119">型**cscript ProcessBamNSFiles.vbs-取得\<ConfigFilePath >\<構成ファイルのパス > \< PID サーバー > \< PID データベース >**です。</span><span class="sxs-lookup"><span data-stu-id="8ad56-119">Type **cscript ProcessBamNSFiles.vbs -Get \<ConfigFilePath> \<ADFFilePath> \< PID Server> \< PID database >**.</span></span> <span data-ttu-id="8ad56-120">構成ファイルのパス、ADF ファイルのパス、PID サーバー、および PID データベースは、インストール環境に適した値に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="8ad56-120">Replacing the ConfigFilePath, ADFFilePath, PID Server, and PID database with the appropriate values for your installation.</span></span>  
  
4.  <span data-ttu-id="8ad56-121">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8ad56-121">Press **ENTER**.</span></span>  
  
5.  <span data-ttu-id="8ad56-122">エディターで、ADF ファイルを開き、検索\<ActionTimeout > 目的の値に、&、この値は XML 期間でことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8ad56-122">Open the ADF file in an editor and search for \<ActionTimeout>, update with desired value & please note that this value is an XML duration.</span></span>  
  
6.  <span data-ttu-id="8ad56-123">ADF ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="8ad56-123">Save the ADF file.</span></span> <span data-ttu-id="8ad56-124">型**cscript ProcessBamNSFiles.vbs-更新\<ConfigFilePath >\<構成ファイルのパス > \< PID サーバー > \< PID データベース >**です。</span><span class="sxs-lookup"><span data-stu-id="8ad56-124">Type **cscript ProcessBamNSFiles.vbs -Update \<ConfigFilePath> \<ADFFilePath> \< PID Server> \< PID database >**.</span></span>  
  
7.  <span data-ttu-id="8ad56-125">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8ad56-125">Press **ENTER**.</span></span>  
  
### <a name="notification-service-configuration-tips"></a><span data-ttu-id="8ad56-126">Notification Service の構成に関するヒント</span><span class="sxs-lookup"><span data-stu-id="8ad56-126">Notification Service configuration tips</span></span>  
 <span data-ttu-id="8ad56-127">[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を実行しているリモート コンピューターに警告データベースを配置するように BAM 警告を構成する場合、SQL Server インスタンスに Notification Services データベース コンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ad56-127">If you configure BAM Alerts in such a way as to place the Alerts databases on a remote computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], then the Notification Services Database Components must be installed on the SQL Server instance.</span></span> <span data-ttu-id="8ad56-128">これらのコンポーネントが SQL インスタンス上に存在しない場合、BAM 警告の構成は失敗し、Notification Services 拡張ストアド プロシージャに権限を与えることができなかったことを示すエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="8ad56-128">If these components are not present on the SQL instance, then configuration of BAM Alerts will fail with an error indicating that permissions could not be granted to the Notification Services Extended Stored Procedures.</span></span> <span data-ttu-id="8ad56-129">Notification Services コンポーネントをインストールする方法の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=61999](http://go.microsoft.com/fwlink/?LinkId=61999)です。</span><span class="sxs-lookup"><span data-stu-id="8ad56-129">For more information on installing the Notification Services component, see [http://go.microsoft.com/fwlink/?LinkId=61999](http://go.microsoft.com/fwlink/?LinkId=61999).</span></span>  
  
 <span data-ttu-id="8ad56-130">BAM では Notification Services へのアクセスに使用されるアカウントを変更できます。</span><span class="sxs-lookup"><span data-stu-id="8ad56-130">BAM allows you to change the account that BAM uses to access the Notification Services.</span></span> <span data-ttu-id="8ad56-131">NSControl を実行する方法以外でこのアカウントを変更すると、アカウントの変更に NSControl を使用することを通知するエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ad56-131">If you change this account in any way other than running NSControl, you will receive an error informing you to use the NSControl to change the account.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ad56-132">Notification Services のインストールおよび構成には、LocalSystem アカウントと SYSTEM アカウントは使用できません。</span><span class="sxs-lookup"><span data-stu-id="8ad56-132">You cannot use the LocalSystem or SYSTEM accounts for installing and configuring Notification Services.</span></span> <span data-ttu-id="8ad56-133">これらのアカウントは、ログオンしたり、BAM 警告ユーザーにファイルや SQL Server へのアクセス許可を与えるのに使用したりすることができない特殊なアカウントです。</span><span class="sxs-lookup"><span data-stu-id="8ad56-133">These are special accounts that you cannot log on to and that you cannot use to grant file and SQL Server permissions to the BAM alerts user.</span></span>  
>   
>  <span data-ttu-id="8ad56-134">Notification Services をインストールおよび構成する場合は、ローカル コンピューターに新しいユーザー アカウントを作成して必要なアクセス許可を与えてから、このアカウントを Notification Services の構成に使用します。</span><span class="sxs-lookup"><span data-stu-id="8ad56-134">To install and configure Notification Services, create a new user account on the local computer, grant it all the requisite permissions, and then use it to configure Notification Services.</span></span>  
  
##### <a name="to-change-ns-user-account-for-bam"></a><span data-ttu-id="8ad56-135">BAM の NS ユーザー アカウントを変更するには</span><span class="sxs-lookup"><span data-stu-id="8ad56-135">To change NS user account for BAM</span></span>  
  
1.  <span data-ttu-id="8ad56-136">NSControl を使用してユーザー アカウントを更新します。</span><span class="sxs-lookup"><span data-stu-id="8ad56-136">Use NSControl to update the user account.</span></span>  
  
2.  <span data-ttu-id="8ad56-137">NS ユーザーに、共有される BAM 警告ファイルの場所に対する読み取り、書き込み、および変更のアクセス許可を与えます。</span><span class="sxs-lookup"><span data-stu-id="8ad56-137">Grant the NS user read, write, and change permissions to the BAM Alerts File Location share.</span></span>  
  
3.  <span data-ttu-id="8ad56-138">BAMAlerts インスタンス データベースとアプリケーション データベースの両方で、NS ユーザーを NSRunService ロールのメンバーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="8ad56-138">Add the NS user as a member of NSRunService role in both the BAMAlerts instance and application databases.</span></span>  
  
4.  <span data-ttu-id="8ad56-139">ドキュメントを使用してローカル コンピューターで NS ユーザー権限を与える[http://go.microsoft.com/fwlink/?LinkId=62005](http://go.microsoft.com/fwlink/?LinkId=62005)です。</span><span class="sxs-lookup"><span data-stu-id="8ad56-139">Grant the NS User rights on the local machine using the documentation at [http://go.microsoft.com/fwlink/?LinkId=62005](http://go.microsoft.com/fwlink/?LinkId=62005).</span></span>  
  
5.  <span data-ttu-id="8ad56-140">よるとデータベースの NS に対する権限を付与[http://go.microsoft.com/fwlink/?LinkId=62008](http://go.microsoft.com/fwlink/?LinkId=62008)です。</span><span class="sxs-lookup"><span data-stu-id="8ad56-140">Grant the NS rights to the NS database according to [http://go.microsoft.com/fwlink/?LinkId=62008](http://go.microsoft.com/fwlink/?LinkId=62008).</span></span>  
  
6.  <span data-ttu-id="8ad56-141">NS ユーザーに、SQL Server に対するログイン権限とプライマリ インポート データベースに対するデータベース アクセス権限を与えます。</span><span class="sxs-lookup"><span data-stu-id="8ad56-141">Grant the NS user login rights to SQL server and database access to the Primary Import database.</span></span>  
  
7.  <span data-ttu-id="8ad56-142">NS ユーザーを BAM_ManagmentNSReader SQL ロールに追加します。</span><span class="sxs-lookup"><span data-stu-id="8ad56-142">Add the NS user to the BAM_ManagmentNSReader SQL role.</span></span>  
  
8.  <span data-ttu-id="8ad56-143">NS ユーザーを BamAnalysis データベースの "BAM 警告" ロールに追加します。</span><span class="sxs-lookup"><span data-stu-id="8ad56-143">Add the NS user to the "BAM Alerts" role in BamAnalysis database.</span></span>  
  
 <span data-ttu-id="8ad56-144">ファイルで配信された警告のファイルの格納場所を変更した場合、</span><span class="sxs-lookup"><span data-stu-id="8ad56-144">If you modify the file drop location for alerts delivered by file.</span></span> <span data-ttu-id="8ad56-145">SQL Notifications Services を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ad56-145">You must restart the SQL Notifications Services.</span></span>  
  
 <span data-ttu-id="8ad56-146">NS サービスを再起動しなかった場合、警告は元のファイルの格納場所に配信され続けます。</span><span class="sxs-lookup"><span data-stu-id="8ad56-146">If the NS service is not restarted, alerts will continue being delivered to the original file drop location.</span></span>  
  
 <span data-ttu-id="8ad56-147">ファイルの格納場所は、BAM 構成ファイルの次の行を変更し、BAM 管理ユーティリティの update-config コマンドを使用することによって変更します。</span><span class="sxs-lookup"><span data-stu-id="8ad56-147">The file drop location is changed by modifying the following line of the BAM configuration file and using the BAM manangement utility update-config command.</span></span>  
  
 <span data-ttu-id="8ad56-148">\<プロパティ名 ="FileDropUNC">\\\\< コンピューター名\>\alerts\</Property ></span><span class="sxs-lookup"><span data-stu-id="8ad56-148">\<Property Name="FileDropUNC">\\\\<computer name\>\alerts\</Property></span></span>  
  
 <span data-ttu-id="8ad56-149">BAM 管理ユーティリティの詳細については、次を参照してください。 [BAM 管理ユーティリティ](../core/bam-management-utility.md)です。</span><span class="sxs-lookup"><span data-stu-id="8ad56-149">For more information on the BAM Management utility, see [BAM Management Utility](../core/bam-management-utility.md).</span></span>