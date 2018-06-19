---
title: Windows SharePoint Services のトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9acf9a0d-2c92-4227-80f8-b2d0cca0c232
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51243216f2adb73454477252c7b54358df229610
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286994"
---
# <a name="troubleshooting-windows-sharepoint-services"></a><span data-ttu-id="ea3ca-102">Windows Sharepoint Services のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ea3ca-102">Troubleshooting Windows SharePoint Services</span></span>
<span data-ttu-id="ea3ca-103">Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] は Windows SharePoint Services アダプターによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-103">Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] is used by the Windows SharePoint Services adapter.</span></span> <span data-ttu-id="ea3ca-104">このトピックでは、Windows SharePoint Services で発生する可能性がある既知の問題点とその解決策について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-104">This topic describes some known issues that may be encountered with Windows SharePoint Services and possible resolutions to these issues.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="ea3ca-105">既知の問題</span><span class="sxs-lookup"><span data-stu-id="ea3ca-105">Known Issues</span></span>  
  
#### <a name="login-failed-for-user-nt-authoritynetwork-service-error-occurs-when-attempting-to-create-content-database"></a><span data-ttu-id="ea3ca-106">コンテンツ データベースを作成しようとすると、"ユーザー 'NT AUTHORITY\NETWORK SERVICE' のログインが失敗しました。" というエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="ea3ca-106">Login failed for user 'NT AUTHORITY\NETWORK SERVICE' error occurs when attempting to create content database</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="ea3ca-107">問題</span><span class="sxs-lookup"><span data-stu-id="ea3ca-107">Problem</span></span>  
 <span data-ttu-id="ea3ca-108">[SharePoint のサーバー管理] Web サイトを使用してコンテンツ データベースを作成しようとすると、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-108">When you attempt to create a content database using the SharePoint Central Administration Web site, an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="ea3ca-109">ユーザー 'NT AUTHORITY\NETWORK SERVICE' はログインできませんでした。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-109">Login failed for user 'NT AUTHORITY\NETWORK SERVICE'</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="ea3ca-110">原因</span><span class="sxs-lookup"><span data-stu-id="ea3ca-110">Cause</span></span>  
 <span data-ttu-id="ea3ca-111">この問題は、接続先データベースの所有者が、Windows SharePoint Services を実行しているアプリケーション プールの ID と異なっている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-111">This issue occurs when the database owner of the database that you are connecting to is different from the application pool identity that Windows SharePoint Services is running under.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="ea3ca-112">解決策</span><span class="sxs-lookup"><span data-stu-id="ea3ca-112">Resolution</span></span>  
 <span data-ttu-id="ea3ca-113">この問題を解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-113">To resolve this issue, do one of the following:</span></span>  
  
-   <span data-ttu-id="ea3ca-114">NETWORK SERVICE アカウントに、SQL Server での "データベース作成" 権限を与えます。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-114">Grant the NETWORK SERVICE account "Database Creation" rights in SQL Server.</span></span>  
  
-   <span data-ttu-id="ea3ca-115">アプリケーション プール ID アカウントを、SQL Server での "データベース作成" 権限を持つアカウントに変更します。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-115">Change the application pool identity account to an account that has "Database Creation" rights in SQL Server.</span></span>  
  
#### <a name="service-unavailable-error-occurs-when-accessing-the-sharepoint-central-administration-web-site"></a><span data-ttu-id="ea3ca-116">[SharePoint のサーバー管理] Web サイトにアクセスすると、"サービスは利用できません" というエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="ea3ca-116">"Service Unavailable" error occurs when accessing the SharePoint Central Administration Web site</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="ea3ca-117">問題</span><span class="sxs-lookup"><span data-stu-id="ea3ca-117">Problem</span></span>  
 <span data-ttu-id="ea3ca-118">[SharePoint のサーバー管理] Web サイトを開こうとすると、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-118">When you attempt to open the SharePoint Central Administration Web site, an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="ea3ca-119">“サービスは利用できません”</span><span class="sxs-lookup"><span data-stu-id="ea3ca-119">Service Unavailable</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="ea3ca-120">原因</span><span class="sxs-lookup"><span data-stu-id="ea3ca-120">Cause</span></span>  
 <span data-ttu-id="ea3ca-121">このエラーの最も一般的な原因は、[SharePoint のサーバー管理] Web サイトのアプリケーション プール (IIS 6.0 または IIS 7.0) またはホスト元 COM+ アプリケーション (IIS 5.x) が停止していることです。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-121">The most common cause for this error is that the application pool (IIS 6.0 or IIS 7.0) or hosting COM+ application (IIS 5.x) for the SharePoint Central Administration Web site is stopped.</span></span> <span data-ttu-id="ea3ca-122">これは、アプリケーション プールまたは COM + アプリケーションが構成されている id を使用する場合によく発生指定されたユーザー名またはパスワードが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-122">This commonly occurs if the application pool or COM+ application is configured with an identity for which the specified user name and/or password is invalid.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="ea3ca-123">解決策</span><span class="sxs-lookup"><span data-stu-id="ea3ca-123">Resolution</span></span>  
 <span data-ttu-id="ea3ca-124">"IIS アプリケーション ホスト プロセス Id の設定"」トピックの手順に従います[IIS アクセス許可の問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)を適切なホスト プロセス id を設定します。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-124">Follow the steps in the "Setting IIS Application Host Process Identity" section of the topic [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md) to set the appropriate host process identity.</span></span>  
  
#### <a name="cannot-connect-to-the-configuration-database-error-occurs-when-attempting-to-extend-and-create-a-content-database"></a><span data-ttu-id="ea3ca-125">コンテンツ データベースを拡張して作成しようとすると "構成データベースに接続できません" というエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="ea3ca-125">"Cannot connect to the configuration database" error occurs when attempting to extend and create a content database</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="ea3ca-126">問題</span><span class="sxs-lookup"><span data-stu-id="ea3ca-126">Problem</span></span>  
 <span data-ttu-id="ea3ca-127">[SharePoint のサーバー管理] Web サイトを使用してコンテンツ データベースを拡張して作成しようとすると、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-127">When you attempt to extend and create a content database using the SharePoint Central Administration Web site, an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="ea3ca-128">構成データベースに接続できません</span><span class="sxs-lookup"><span data-stu-id="ea3ca-128">Cannot connect to the configuration database</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="ea3ca-129">原因</span><span class="sxs-lookup"><span data-stu-id="ea3ca-129">Cause</span></span>  
 <span data-ttu-id="ea3ca-130">この問題は、[SharePoint のサーバー管理] Web サイトを実行しているアプリケーション プールが使用するアカウントに、SQL Server データベースに対する必要なアクセス許可がない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-130">This issue occurs when the account that is used by the application pool that is running the SharePoint Central Administration Web site does not have the required permissions to the SQL Server database.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="ea3ca-131">解決策</span><span class="sxs-lookup"><span data-stu-id="ea3ca-131">Resolution</span></span>  
 <span data-ttu-id="ea3ca-132">この問題を解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-132">To resolve this issue, do one of the following:</span></span>  
  
-   <span data-ttu-id="ea3ca-133">[SharePoint のサーバー管理] Web サイトのアプリケーション プールが使用するアカウントに、SQL Server での "データベース作成" 権限を与えます。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-133">Grant the account that is used by the application pool for the SharePoint Central Administration Web site "Database Creation" rights in SQL Server.</span></span>  
  
-   <span data-ttu-id="ea3ca-134">アプリケーション プール ID アカウントを、SQL Server での "データベース作成" 権限を持つアカウントに変更します。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-134">Change the application pool identity account to an account that has "Database Creation" rights in SQL Server.</span></span>  
  
#### <a name="the-sharepoint-timer-service-service-failed-to-start-error-is-generated-in-the-application-log-after-rebooting-server"></a><span data-ttu-id="ea3ca-135">サーバー再起動後にアプリケーション ログで、SharePoint Timer サービスを開始できませんでしたというエラーが生成される</span><span class="sxs-lookup"><span data-stu-id="ea3ca-135">"The SharePoint Timer Service service failed to start" error is generated in the Application log after rebooting server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="ea3ca-136">問題</span><span class="sxs-lookup"><span data-stu-id="ea3ca-136">Problem</span></span>  
 <span data-ttu-id="ea3ca-137">サーバーを再起動した後に、次のようなエラーがイベント ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-137">After restarting the server, you see the following error in the event logs:</span></span>  
  
 <span data-ttu-id="ea3ca-138">SharePoint Timer サービスを開始できませんでした</span><span class="sxs-lookup"><span data-stu-id="ea3ca-138">The SharePoint Timer Service service failed to start</span></span>  
  
 <span data-ttu-id="ea3ca-139">また、[SharePoint のサーバー管理] サイトを開いたときに次のようなエラーが表示される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-139">You may also see the following error when you open the SharePoint Central Administration site:</span></span>  
  
 <span data-ttu-id="ea3ca-140">WSS 構成データベースの STS_Config に接続できません。"</span><span class="sxs-lookup"><span data-stu-id="ea3ca-140">Unable to connect to the WSS configuration database STS_Config</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="ea3ca-141">原因</span><span class="sxs-lookup"><span data-stu-id="ea3ca-141">Cause</span></span>  
 <span data-ttu-id="ea3ca-142">このエラーは、再起動後に SharePoint Timer サービスが [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] データベースにアクセスできない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-142">This error occurs when the SharePoint Timer service fails to contact the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] database after rebooting.</span></span> <span data-ttu-id="ea3ca-143">SharePoint Timer サービスは、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] に対する通知の送信および予定されたタスクの実行を行うために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-143">The SharePoint Timer service is used to send notifications and perform scheduled tasks for [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span></span> <span data-ttu-id="ea3ca-144">SharePoint Timer サービスを開始できない最も一般的な理由は、サービスの実行に使用されるアカウントの ID に指定されているユーザー名またはパスワードが無効になっていることです。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-144">The most common reason that the SharePoint Timer service fails to start is that the account used to run the service is configured with an identity for which the user name and/or password are no longer valid.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="ea3ca-145">解決策</span><span class="sxs-lookup"><span data-stu-id="ea3ca-145">Resolution</span></span>  
 <span data-ttu-id="ea3ca-146">SharePoint Timer サービスのログオン アカウントに指定されているユーザー名とパスワードが正しいこと、およびこのサービスが開始されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-146">Ensure that the user name and password specified for the SharePoint Timer service logon account are correct and that the service has been started.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea3ca-147">参照</span><span class="sxs-lookup"><span data-stu-id="ea3ca-147">See Also</span></span>  
 <span data-ttu-id="ea3ca-148">[Windows SharePoint Services 仮想サーバーを構成する方法](http://support.microsoft.com/kb/832769) </span><span class="sxs-lookup"><span data-stu-id="ea3ca-148">[How to configure a Windows SharePoint Services virtual server](http://support.microsoft.com/kb/832769) </span></span>  
 <span data-ttu-id="ea3ca-149">[バックアップし、Microsoft SQL Server 2000 Desktop Engine (Windows) を使用している Windows SharePoint Services のインストールを復元する方法](http://support.microsoft.com/kb/833797) </span><span class="sxs-lookup"><span data-stu-id="ea3ca-149">[How to back up and restore installations of Windows SharePoint Services that use Microsoft SQL Server 2000 Desktop Engine (Windows)](http://support.microsoft.com/kb/833797) </span></span>  
 <span data-ttu-id="ea3ca-150">[Windows SharePoint Services Web サイトに接続するときに、「構成データベースに接続できません」エラー メッセージが表示されます。](http://support.microsoft.com/kb/823287) </span><span class="sxs-lookup"><span data-stu-id="ea3ca-150">[You receive a "Cannot connect to the configuration database" error message when you connect to your Windows SharePoint Services Web site](http://support.microsoft.com/kb/823287) </span></span>  
 <span data-ttu-id="ea3ca-151">[Windows SharePoint Services の Web サイトを参照すると、「サービスを利用できません」エラー メッセージが表示されます。](http://support.microsoft.com/kb/823552) </span><span class="sxs-lookup"><span data-stu-id="ea3ca-151">[You Receive a "Service Unavailable" Error Message When You Browse a Windows SharePoint Services Web Site](http://support.microsoft.com/kb/823552) </span></span>  
 [<span data-ttu-id="ea3ca-152">Windows SharePoint Services コンテンツ データベースを管理するときに、「Database < Database_Name > が既に存在する」エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea3ca-152">You receive a "Database <Database_Name> already exists" error message when you manage your Windows SharePoint Services content database</span></span>](http://support.microsoft.com/kb/828815)