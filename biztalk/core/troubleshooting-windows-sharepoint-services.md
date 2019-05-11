---
title: Windows SharePoint Services のトラブルシューティング |Microsoft Docs
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
ms.openlocfilehash: 95d0b833028afdc3c2b560ed60802ff60d6d4046
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253614"
---
# <a name="troubleshooting-windows-sharepoint-services"></a><span data-ttu-id="65f39-102">Windows SharePoint Services のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="65f39-102">Troubleshooting Windows SharePoint Services</span></span>
<span data-ttu-id="65f39-103">Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Windows SharePoint Services アダプターによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="65f39-103">Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] is used by the Windows SharePoint Services adapter.</span></span> <span data-ttu-id="65f39-104">このトピックでは、Windows SharePoint Services およびこれらの問題の解決方法で発生する可能性がある既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="65f39-104">This topic describes some known issues that may be encountered with Windows SharePoint Services and possible resolutions to these issues.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="65f39-105">既知の問題</span><span class="sxs-lookup"><span data-stu-id="65f39-105">Known Issues</span></span>  
  
#### <a name="login-failed-for-user-nt-authoritynetwork-service-error-occurs-when-attempting-to-create-content-database"></a><span data-ttu-id="65f39-106">ログイン ユーザー ' NT authority \network SERVICE' エラーのエラーは、コンテンツ データベースを作成するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="65f39-106">Login failed for user 'NT AUTHORITY\NETWORK SERVICE' error occurs when attempting to create content database</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="65f39-107">問題</span><span class="sxs-lookup"><span data-stu-id="65f39-107">Problem</span></span>  
 <span data-ttu-id="65f39-108">SharePoint サーバーの全体管理 Web サイトを使用してコンテンツ データベースを作成しようとすると、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="65f39-108">When you attempt to create a content database using the SharePoint Central Administration Web site, an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="65f39-109">ユーザー ' NT authority \network SERVICE' はログインできませんでした。</span><span class="sxs-lookup"><span data-stu-id="65f39-109">Login failed for user 'NT AUTHORITY\NETWORK SERVICE'</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="65f39-110">原因</span><span class="sxs-lookup"><span data-stu-id="65f39-110">Cause</span></span>  
 <span data-ttu-id="65f39-111">この問題に接続しているデータベースのデータベース所有者が Windows SharePoint Services が実行されているアプリケーション プール id と異なる場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="65f39-111">This issue occurs when the database owner of the database that you are connecting to is different from the application pool identity that Windows SharePoint Services is running under.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="65f39-112">解決策</span><span class="sxs-lookup"><span data-stu-id="65f39-112">Resolution</span></span>  
 <span data-ttu-id="65f39-113">この問題を解決するには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="65f39-113">To resolve this issue, do one of the following:</span></span>  
  
-   <span data-ttu-id="65f39-114">ネットワーク サービス アカウントに SQL Server で「データベース作成」権限を付与します。</span><span class="sxs-lookup"><span data-stu-id="65f39-114">Grant the NETWORK SERVICE account "Database Creation" rights in SQL Server.</span></span>  
  
-   <span data-ttu-id="65f39-115">SQL Server の「データベース作成」権限を持っているアカウントには、アプリケーション プール id アカウントを変更します。</span><span class="sxs-lookup"><span data-stu-id="65f39-115">Change the application pool identity account to an account that has "Database Creation" rights in SQL Server.</span></span>  
  
#### <a name="service-unavailable-error-occurs-when-accessing-the-sharepoint-central-administration-web-site"></a><span data-ttu-id="65f39-116">「サービスは利用できません」エラーは、SharePoint サーバーの全体管理 Web サイトにアクセスするときに発生します。</span><span class="sxs-lookup"><span data-stu-id="65f39-116">"Service Unavailable" error occurs when accessing the SharePoint Central Administration Web site</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="65f39-117">問題</span><span class="sxs-lookup"><span data-stu-id="65f39-117">Problem</span></span>  
 <span data-ttu-id="65f39-118">SharePoint サーバーの全体管理 Web サイトを開こうとすると、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="65f39-118">When you attempt to open the SharePoint Central Administration Web site, an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="65f39-119">サービス利用不可</span><span class="sxs-lookup"><span data-stu-id="65f39-119">Service Unavailable</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="65f39-120">原因</span><span class="sxs-lookup"><span data-stu-id="65f39-120">Cause</span></span>  
 <span data-ttu-id="65f39-121">このエラーの最も一般的な原因は、アプリケーション プール (IIS 6.0 または IIS 7.0) または COM + アプリケーションをホストしている (IIS 5.x) for SharePoint サーバーの全体管理 Web サイトが停止しています。</span><span class="sxs-lookup"><span data-stu-id="65f39-121">The most common cause for this error is that the application pool (IIS 6.0 or IIS 7.0) or hosting COM+ application (IIS 5.x) for the SharePoint Central Administration Web site is stopped.</span></span> <span data-ttu-id="65f39-122">これは、問題は発生アプリケーション プールまたは COM + アプリケーションが構成されている場合、id を指定したユーザー名またはパスワードが無効です。</span><span class="sxs-lookup"><span data-stu-id="65f39-122">This commonly occurs if the application pool or COM+ application is configured with an identity for which the specified user name and/or password is invalid.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="65f39-123">解決策</span><span class="sxs-lookup"><span data-stu-id="65f39-123">Resolution</span></span>  
 <span data-ttu-id="65f39-124">トピックの「IIS アプリケーション ホスト プロセス Id の設定」セクションの手順に従って[IIS アクセス許可問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)適切なホスト プロセス id を設定します。</span><span class="sxs-lookup"><span data-stu-id="65f39-124">Follow the steps in the "Setting IIS Application Host Process Identity" section of the topic [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md) to set the appropriate host process identity.</span></span>  
  
#### <a name="cannot-connect-to-the-configuration-database-error-occurs-when-attempting-to-extend-and-create-a-content-database"></a><span data-ttu-id="65f39-125">「構成データベースに接続できません」エラーは、拡張し、コンテンツ データベースを作成しようとしています。 ときに発生します。</span><span class="sxs-lookup"><span data-stu-id="65f39-125">"Cannot connect to the configuration database" error occurs when attempting to extend and create a content database</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="65f39-126">問題</span><span class="sxs-lookup"><span data-stu-id="65f39-126">Problem</span></span>  
 <span data-ttu-id="65f39-127">拡張して、SharePoint サーバーの全体管理 Web サイトを使用してコンテンツ データベースを作成しようとすると、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="65f39-127">When you attempt to extend and create a content database using the SharePoint Central Administration Web site, an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="65f39-128">構成データベースに接続できません。</span><span class="sxs-lookup"><span data-stu-id="65f39-128">Cannot connect to the configuration database</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="65f39-129">原因</span><span class="sxs-lookup"><span data-stu-id="65f39-129">Cause</span></span>  
 <span data-ttu-id="65f39-130">この問題は、SharePoint サーバーの全体管理 Web サイトを実行しているアプリケーション プールで使用されるアカウントに SQL Server データベースに必要なアクセス許可があるない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="65f39-130">This issue occurs when the account that is used by the application pool that is running the SharePoint Central Administration Web site does not have the required permissions to the SQL Server database.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="65f39-131">解決策</span><span class="sxs-lookup"><span data-stu-id="65f39-131">Resolution</span></span>  
 <span data-ttu-id="65f39-132">この問題を解決するには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="65f39-132">To resolve this issue, do one of the following:</span></span>  
  
-   <span data-ttu-id="65f39-133">SQL Server での SharePoint サーバーの全体管理 Web サイト「データベース作成」権限をアプリケーション プールで使用されるアカウントに付与します。</span><span class="sxs-lookup"><span data-stu-id="65f39-133">Grant the account that is used by the application pool for the SharePoint Central Administration Web site "Database Creation" rights in SQL Server.</span></span>  
  
-   <span data-ttu-id="65f39-134">SQL Server の「データベース作成」権限を持っているアカウントには、アプリケーション プール id アカウントを変更します。</span><span class="sxs-lookup"><span data-stu-id="65f39-134">Change the application pool identity account to an account that has "Database Creation" rights in SQL Server.</span></span>  
  
#### <a name="the-sharepoint-timer-service-service-failed-to-start-error-is-generated-in-the-application-log-after-rebooting-server"></a><span data-ttu-id="65f39-135">サーバー再起動後に、アプリケーション ログに「SharePoint Timer サービスを開始できませんでした」エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="65f39-135">"The SharePoint Timer Service service failed to start" error is generated in the Application log after rebooting server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="65f39-136">問題</span><span class="sxs-lookup"><span data-stu-id="65f39-136">Problem</span></span>  
 <span data-ttu-id="65f39-137">サーバーの再起動後に、イベント ログに次のエラーでを参照してください。</span><span class="sxs-lookup"><span data-stu-id="65f39-137">After restarting the server, you see the following error in the event logs:</span></span>  
  
 <span data-ttu-id="65f39-138">SharePoint Timer サービスを開始できませんでした。</span><span class="sxs-lookup"><span data-stu-id="65f39-138">The SharePoint Timer Service service failed to start</span></span>  
  
 <span data-ttu-id="65f39-139">SharePoint サーバーの全体管理サイトを開く場合は、次のエラーを表示することがありますも。</span><span class="sxs-lookup"><span data-stu-id="65f39-139">You may also see the following error when you open the SharePoint Central Administration site:</span></span>  
  
 <span data-ttu-id="65f39-140">WSS 構成データベースの STS_Config に接続できません。</span><span class="sxs-lookup"><span data-stu-id="65f39-140">Unable to connect to the WSS configuration database STS_Config</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="65f39-141">原因</span><span class="sxs-lookup"><span data-stu-id="65f39-141">Cause</span></span>  
 <span data-ttu-id="65f39-142">このエラーは、SharePoint Timer サービスにアクセスできないときに発生します。、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]データベースの再起動後です。</span><span class="sxs-lookup"><span data-stu-id="65f39-142">This error occurs when the SharePoint Timer service fails to contact the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] database after rebooting.</span></span> <span data-ttu-id="65f39-143">通知を送信し、スケジュールされたタスクを実行する SharePoint Timer サービスが使用される[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="65f39-143">The SharePoint Timer service is used to send notifications and perform scheduled tasks for [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span></span> <span data-ttu-id="65f39-144">SharePoint Timer サービスを開始できない最も一般的な理由は、対象のユーザー名またはパスワードが無効になった id でサービスを実行するために使用するアカウントが構成されていることです。</span><span class="sxs-lookup"><span data-stu-id="65f39-144">The most common reason that the SharePoint Timer service fails to start is that the account used to run the service is configured with an identity for which the user name and/or password are no longer valid.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="65f39-145">解決策</span><span class="sxs-lookup"><span data-stu-id="65f39-145">Resolution</span></span>  
 <span data-ttu-id="65f39-146">ユーザー名と、SharePoint Timer サービス ログオン アカウントの指定したパスワードが正しいことと、サービスが開始されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="65f39-146">Ensure that the user name and password specified for the SharePoint Timer service logon account are correct and that the service has been started.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65f39-147">参照</span><span class="sxs-lookup"><span data-stu-id="65f39-147">See Also</span></span>  
 <span data-ttu-id="65f39-148">[Windows SharePoint Services 仮想サーバーを構成する方法](http://support.microsoft.com/kb/832769) </span><span class="sxs-lookup"><span data-stu-id="65f39-148">[How to configure a Windows SharePoint Services virtual server](http://support.microsoft.com/kb/832769) </span></span>  
 <span data-ttu-id="65f39-149">[バックアップし、Microsoft SQL Server 2000 Desktop Engine (Windows) を使用している Windows SharePoint Services のインストールを復元する方法](http://support.microsoft.com/kb/833797) </span><span class="sxs-lookup"><span data-stu-id="65f39-149">[How to back up and restore installations of Windows SharePoint Services that use Microsoft SQL Server 2000 Desktop Engine (Windows)](http://support.microsoft.com/kb/833797) </span></span>  
 <span data-ttu-id="65f39-150">[Windows SharePoint Services Web サイトに接続するときに、「構成データベースに接続できません」エラー メッセージが表示されます。](http://support.microsoft.com/kb/823287) </span><span class="sxs-lookup"><span data-stu-id="65f39-150">[You receive a "Cannot connect to the configuration database" error message when you connect to your Windows SharePoint Services Web site](http://support.microsoft.com/kb/823287) </span></span>  
 <span data-ttu-id="65f39-151">[Windows SharePoint Services の Web サイトを参照すると、「サービス利用不可」エラー メッセージが表示されます。](http://support.microsoft.com/kb/823552) </span><span class="sxs-lookup"><span data-stu-id="65f39-151">[You Receive a "Service Unavailable" Error Message When You Browse a Windows SharePoint Services Web Site](http://support.microsoft.com/kb/823552) </span></span>  
 [<span data-ttu-id="65f39-152">Windows SharePoint Services コンテンツ データベースを管理するときに「既に Database < Database_Name > が存在します」のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="65f39-152">You receive a "Database <Database_Name> already exists" error message when you manage your Windows SharePoint Services content database</span></span>](http://support.microsoft.com/kb/828815)