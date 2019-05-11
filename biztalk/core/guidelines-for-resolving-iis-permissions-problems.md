---
title: IIS のアクセス許可の問題を解決するためのガイドライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: d9793a90-3aa3-46ab-a317-6d1e0fbfc1ef
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5473ef63655b7b135de1ea830cff0d41efe625e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344857"
---
# <a name="guidelines-for-resolving-iis-permissions-problems"></a><span data-ttu-id="8092b-102">IIS のアクセス許可の問題を解決するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="8092b-102">Guidelines for Resolving IIS Permissions Problems</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="8092b-103">で広範な使用の Microsoft インターネット インフォメーション サービス (IIS) Web サービスのサポート、HTTP、SOAP、および Windows SharePoint Services アダプターで使用します。</span><span class="sxs-lookup"><span data-stu-id="8092b-103">makes extensive use of Microsoft Internet Information Services (IIS) for Web services support and for use with the HTTP, SOAP, and Windows SharePoint Services adapters.</span></span>  
  
 <span data-ttu-id="8092b-104">IIS が IIS のアクセス許可の問題をトラブルシューティングする前にアプリケーションの分離を実装する方法を理解することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8092b-104">It is helpful to understand how IIS implements application isolation before troubleshooting IIS permissions problems.</span></span>  
  
 <span data-ttu-id="8092b-105">IIS は、独自のメモリ空間で実行される個別のホスト プロセスとして IIS アプリケーションを作成するための機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="8092b-105">IIS provides functionality for creating IIS applications as distinct host processes that are run in their own memory space.</span></span> <span data-ttu-id="8092b-106">IIS アプリケーション ホストを作成すると、必要があります 2 つのセットを定義、IIS アプリケーション ホストのアクセス許可**プロセス id**と IIS アプリケーション ホスト**ユーザー アクセス権**します。</span><span class="sxs-lookup"><span data-stu-id="8092b-106">Once you create an IIS application host, then you must define two sets of permissions, the IIS application host **process identity** and the IIS application host **user access rights**.</span></span> <span data-ttu-id="8092b-107">IIS のアクセス許可の問題のトラブルシューティングを行うとき、それぞれのアクセス許可セットを調べる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8092b-107">You should examine each of these permissions sets when troubleshooting IIS permissions problems.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8092b-108">**プロセス id**と**ユーザー アクセス権**として別名、**セキュリティ コンテキスト**IIS アプリケーション ホスト プロセスの。</span><span class="sxs-lookup"><span data-stu-id="8092b-108">The **process identity** and **user access rights** are also referred to as the **security context** of the IIS application host process.</span></span>  
  
 <span data-ttu-id="8092b-109">このトピックでは、設定する方法を説明します**プロセス id**と**ユーザー アクセス権**IIS アプリケーション ホスト プロセスのおよび IIS のアクセス許可の問題を解決するための一般的なガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="8092b-109">This topic describes how to set **process identity** and **user access rights** for an IIS application host process and gives some general guidelines for resolving IIS permissions problems.</span></span>  
  
## <a name="setting-iis-application-host-process-identity"></a><span data-ttu-id="8092b-110">IIS アプリケーション ホスト プロセス Id の設定</span><span class="sxs-lookup"><span data-stu-id="8092b-110">Setting IIS Application Host Process Identity</span></span>  
 <span data-ttu-id="8092b-111">IIS アプリケーション ホスト プロセスの構成については、ホスト プロセスによって提供される機能のレベルによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8092b-111">Configuration of an IIS application host process can vary depending on the level of functionality being served by the host process.</span></span> <span data-ttu-id="8092b-112">たとえば、静的な HTML ページのみを処理する IIS アプリケーション ホスト プロセスは ASP ページや ASP.NET アプリケーション、IIS アプリケーション ホスト プロセスとは異なる構成通常します。</span><span class="sxs-lookup"><span data-stu-id="8092b-112">For example, an IIS application host process that only serves static HTML pages is typically configured differently than an IIS application host process that serves ASP pages or ASP.NET applications.</span></span>  
  
 <span data-ttu-id="8092b-113">IIS アプリケーション ホスト プロセスの構成は、アプリケーションをホストする IIS のバージョンによっても異なります。</span><span class="sxs-lookup"><span data-stu-id="8092b-113">Configuration of an IIS application host process also varies depending on the version of IIS that is hosting the application.</span></span> <span data-ttu-id="8092b-114">Windows Server 2008 (IIS 7.0) で実行されるアプリケーションのホスト プロセス id は、アプリケーションに関連付けられているアプリケーション プールの id によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="8092b-114">The host process identity of applications running on Windows Server 2008 (IIS 7.0) is governed by the identity of the application pool associated with the application.</span></span>  
  
### <a name="setting-iis-process-identity-for-iis-70-on-windows-server-2008-or-windows-vista"></a><span data-ttu-id="8092b-115">Windows Server 2008 で IIS 7.0 の IIS プロセス Id または Windows Vista の設定</span><span class="sxs-lookup"><span data-stu-id="8092b-115">Setting IIS Process Identity for IIS 7.0 on Windows Server 2008 or Windows Vista</span></span>  
  
1.  <span data-ttu-id="8092b-116">クリックして**開始**、し**すべてのプログラム**、 をクリック**インターネット インフォメーション サービス (IIS) 7 マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="8092b-116">Click **Start**, then **All Programs**, and click **Internet Information Services (IIS) 7 Manager**.</span></span>  
  
2.  <span data-ttu-id="8092b-117">インターネット インフォメーション サービス (IIS) マネージャーで、展開*\<コンピューター名\>\*\*\*(User account)*\* をクリックして**アプリケーション プール**します。</span><span class="sxs-lookup"><span data-stu-id="8092b-117">In Internet Information Services (IIS) Manager, expand *\<computer name\>\*\*\*(User account)*\* and click **Application Pools**.</span></span>  
  
3.  <span data-ttu-id="8092b-118">アプリケーション プールを右クリックし、をクリックして**アプリケーションの表示**にアプリケーション プールに関連付けられているアプリケーションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8092b-118">Right-click an application pool and click **View Applications** to see the applications associated with the application pool.</span></span>  
  
4.  <span data-ttu-id="8092b-119">アプリケーション プールを右クリックし、をクリックして**詳細設定**アプリケーション プールの詳細設定 ダイアログを表示します。</span><span class="sxs-lookup"><span data-stu-id="8092b-119">Right-click an application pool and click **Advanced Settings** to display the Advanced Settings dialog for the application pool.</span></span>  
  
5.  <span data-ttu-id="8092b-120">横にある省略記号 (...) ボタンをクリックして、アプリケーション プールの id を変更**Identity**下、**プロセス モデル**のセクション、**詳細設定**ダイアログボックス。</span><span class="sxs-lookup"><span data-stu-id="8092b-120">Modify the identity for the application pool by clicking the ellipsis (…) button next to **Identity** under the **Process Model** section of the **Advanced Settings** dialog box.</span></span>  
  
## <a name="setting-user-access-rights-for-the-iis-server"></a><span data-ttu-id="8092b-121">IIS サーバーのユーザー アクセス許可の設定</span><span class="sxs-lookup"><span data-stu-id="8092b-121">Setting User Access Rights for the IIS Server</span></span>  
 <span data-ttu-id="8092b-122">プロセス id は、IIS アプリケーション ホスト プロセスの実行に使用できるセキュリティ コンテキストを制御します、ユーザーのアクセス許可は、実際に提供される web ページにアクセスしているアカウントのセキュリティ コンテキストを制御します。</span><span class="sxs-lookup"><span data-stu-id="8092b-122">While process identity governs the security context available to the running IIS application host process, user access permissions govern the security context for the account that is actually accessing the Web page(s) being served.</span></span> <span data-ttu-id="8092b-123">アクセス許可のエラーを回避するために両方のセキュリティ コンテキストのアクセス許可を適切に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8092b-123">Permissions must be set appropriately for both security contexts to avoid permissions errors.</span></span>  
  
 <span data-ttu-id="8092b-124">IIS 7.0 には、次のユーザーの認証方法がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8092b-124">IIS 7.0 supports the following user authentication methods:</span></span>  
  
-   <span data-ttu-id="8092b-125">**匿名アクセス:** 匿名接続を確立することができます。</span><span class="sxs-lookup"><span data-stu-id="8092b-125">**Anonymous access:** Allows users to establish an anonymous connection.</span></span> <span data-ttu-id="8092b-126">IIS サーバーは、指定したゲスト アカウントでユーザーに記録します。</span><span class="sxs-lookup"><span data-stu-id="8092b-126">The IIS server logs on the user with the specified guest account.</span></span>  
  
-   <span data-ttu-id="8092b-127">**ASP.NET の偽装**により、アプリケーションが 2 つの異なるコンテキストのいずれかで実行する: IIS で認証されたユーザーとして、または任意のアカウントを設定することとして、いずれか。</span><span class="sxs-lookup"><span data-stu-id="8092b-127">**ASP.NET Impersonation** Allows an application to run in one of two different contexts: either as the user authenticated by IIS or as an arbitrary account that you set up.</span></span>  
  
-   <span data-ttu-id="8092b-128">**基本認証:** パスワードをプレーン テキストで、暗号化されていない形式でネットワーク経由で送信されます。</span><span class="sxs-lookup"><span data-stu-id="8092b-128">**Basic authentication:** Transmits passwords across the network in plaintext, an unencrypted form.</span></span>  
  
-   <span data-ttu-id="8092b-129">**ダイジェスト認証:** ハッシュ値をプレーン テキスト パスワードではなく、ネットワーク経由で送信する、Active Directory アカウントでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="8092b-129">**Digest authentication:** Works only with Active Directory accounts, sending a hash value over the network, rather than a plaintext password.</span></span> <span data-ttu-id="8092b-130">ダイジェスト認証は、プロキシ サーバーおよびその他のファイアウォールおよび Web Distributed Authoring and Versioning (WebDAV) ディレクトリに収録されています。</span><span class="sxs-lookup"><span data-stu-id="8092b-130">Digest authentication works across proxy servers and other firewalls and is available on Web Distributed Authoring and Versioning (WebDAV) directories.</span></span> <span data-ttu-id="8092b-131">ダイジェスト認証の使用は、匿名認証が最初に無効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8092b-131">Use of Digest authentication requires that Anonymous authentication is disabled first.</span></span>  
  
-   <span data-ttu-id="8092b-132">**フォーム認証**の認証トラフィックの多いサイトまたは公開サーバー上のアプリケーションに対応します。</span><span class="sxs-lookup"><span data-stu-id="8092b-132">**Forms Authentication** Accommodates authentication for high-traffic sites or applications on public servers.</span></span> <span data-ttu-id="8092b-133">フォーム認証を使用して、クライアントの登録と、オペレーティング システムによって提供される認証メカニズムではなく、アプリケーション レベルでの認証を管理できます。</span><span class="sxs-lookup"><span data-stu-id="8092b-133">Forms authentication lets you manage client registration and authentication at the application level, instead of relying on the authentication mechanisms provided by the operating system.</span></span>  
  
-   <span data-ttu-id="8092b-134">**Windows 認証:** Windows ドメインで認証を使用すると、クライアント接続を認証します。</span><span class="sxs-lookup"><span data-stu-id="8092b-134">**Windows authentication:** Uses authentication on your Windows domain to authenticate client connections.</span></span>  
  
#### <a name="to-set-user-access-rights-for-a-virtual-directory-in-iis-70"></a><span data-ttu-id="8092b-135">IIS 7.0 で仮想ディレクトリのユーザー アクセス権を設定するには</span><span class="sxs-lookup"><span data-stu-id="8092b-135">To set user access rights for a virtual directory in IIS 7.0</span></span>  
  
1.  <span data-ttu-id="8092b-136">インターネット インフォメーション サービス (IIS) マネージャーで、展開*\<コンピューター名\>*、**サイト**、および**既定の Web サイト**で**接続**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="8092b-136">In the Internet Information Services (IIS) Manager, expand *\<computer name\>*, **Sites**, and **Default Web Site** in the **Connections** pane.</span></span>  
  
2.  <span data-ttu-id="8092b-137">クリックして仮想ディレクトリを選択し、をクリックして、**機能ビュー**を仮想ディレクトリの構成可能な機能を一覧表示 [ワークスペース] ウィンドウの下部にあります。</span><span class="sxs-lookup"><span data-stu-id="8092b-137">Click to select the virtual directory and click the **Features View** at the bottom of the Workspace pane to list the configurable features for the virtual directory.</span></span>  
  
3.  <span data-ttu-id="8092b-138">ダブルクリック、**認証**を仮想ディレクトリに対して有効になっている認証方法を一覧表示 [ワークスペース] ウィンドウで機能します。</span><span class="sxs-lookup"><span data-stu-id="8092b-138">Double-click the **Authentication** feature in the Workspace pane to list the authentication methods that are enabled for the virtual directory.</span></span>  
  
4.  <span data-ttu-id="8092b-139">クリックを有効または無効にし、いずれかをクリックする認証方法を選択する**を無効にする**または**を有効にする**で、**アクション**IIS マネージャーのウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="8092b-139">Click to select the authentication method that you would like to enable or disable and click either **Disable** or **Enable** in the **Actions** pane of the IIS Manager.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8092b-140">場合**への匿名アクセスを有効にする**が有効にすると、IIS はユーザー アクセス権を設定として構成されている匿名ユーザー id の認証方法を有効になっている、他のユーザー アクセス権を設定する前にします。</span><span class="sxs-lookup"><span data-stu-id="8092b-140">If **Enable anonymous access** is enabled, IIS will set user access rights as the configured Anonymous user identity before setting user access rights with any other enabled authentication methods.</span></span>  
    >   
    >  <span data-ttu-id="8092b-141">匿名ユーザー id を構成するを右クリックし、**匿名認証**メソッドとクリック**編集**を表示する、**匿名認証資格情報の編集**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="8092b-141">To configure the Anonymous user identity, right-click the **Anonymous Authentication** method and click **Edit** to display the **Edit Anonymous Authentication Credentials** dialog.</span></span>  
  
## <a name="general-guidelines-for-resolving-iis-permissions-problems"></a><span data-ttu-id="8092b-142">IIS のアクセス許可の問題を解決するための一般的なガイドライン</span><span class="sxs-lookup"><span data-stu-id="8092b-142">General Guidelines for Resolving IIS Permissions Problems</span></span>  
 <span data-ttu-id="8092b-143">IIS のアクセス許可のトラブルシューティングを行うこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8092b-143">Follow these steps to troubleshoot IIS permissions:</span></span>  
  
1.  <span data-ttu-id="8092b-144">エラーの IIS サーバー コンピューターのアプリケーション ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="8092b-144">Check the application log of the IIS Server computer for errors.</span></span>  
  
2.  <span data-ttu-id="8092b-145">次の手順では、 [IIS 7.0。IIS 7.0 で失敗した要求のトレースの構成](http://go.microsoft.com/fwlink/?LinkId=130600)IIS 7.0 コンピューターに対する権限の問題のトラブルシューティングを行う。</span><span class="sxs-lookup"><span data-stu-id="8092b-145">Follow the steps in [IIS 7.0: Configuring Tracing for Failed Requests in IIS 7.0](http://go.microsoft.com/fwlink/?LinkId=130600) to troubleshoot permissions problems on IIS 7.0 computers.</span></span>  
  
3.  <span data-ttu-id="8092b-146">HTTP 401 エラーの IIS サーバーの IIS ログ ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="8092b-146">Check the IIS log files of the IIS server for HTTP 401 errors.</span></span>  
  
     <span data-ttu-id="8092b-147">既定では、IIS は、Windows Server 2008 または Windows Vista を実行するコンピューターでログ ファイルは、次のディレクトリに配置されます。</span><span class="sxs-lookup"><span data-stu-id="8092b-147">By default the IIS log files on a computer running Windows Server 2008 or Windows Vista are located in the following directory:</span></span>  
  
     <span data-ttu-id="8092b-148">C:\inetpub\logs\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="8092b-148">C:\inetpub\logs\LogFiles\W3SVC1\\</span></span>  
  
    -   <span data-ttu-id="8092b-149">IIS ログ ファイルに、IIS 7.0 コンピューターには、HTTP 401 エラーが含まれていますサポート技術情報の資料 943891「での手順に従って、場合「HTTP ステータス コードを IIS 7.0」でご利用いただけます[ http://support.microsoft.com/kb/943891 ](http://support.microsoft.com/kb/943891)サブステータス コードを確認し状態コードに基づいてアクセス許可の問題のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="8092b-149">If the IIS log file for an IIS 7.0 computer contains HTTP 401 errors, follow the steps in Microsoft Knowledge Base article 943891, "The HTTP status codes in IIS 7.0" available at [http://support.microsoft.com/kb/943891](http://support.microsoft.com/kb/943891) to determine the substatus code and to troubleshoot the permissions problem based on the status code.</span></span>  
  
    -   <span data-ttu-id="8092b-150">値を確認、 **cs-username** HTTP 401 エラーに関連付けられているフィールドです。</span><span class="sxs-lookup"><span data-stu-id="8092b-150">Check the value of the **cs-username** field associated with the HTTP 401 error.</span></span> <span data-ttu-id="8092b-151">このフィールドには、IIS サーバーにアクセスした認証されたユーザーの名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8092b-151">This field contains the name of the authenticated user who accessed the IIS server.</span></span> <span data-ttu-id="8092b-152">匿名ユーザー アカウントは、このフィールドにハイフン (-) で表されます。</span><span class="sxs-lookup"><span data-stu-id="8092b-152">The anonymous user account is represented by a hyphen (-) in this field.</span></span> <span data-ttu-id="8092b-153">このアカウントが適切なリソースのアクセス許可を持つことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8092b-153">Ensure that this account has permissions on the appropriate resources.</span></span>  
  
4.  <span data-ttu-id="8092b-154">IIS アプリケーション ホスト プロセスで使用されるプロセス id の資格情報が正しく設定されていると、アカウントが適切なアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="8092b-154">Verify that the process identity credentials used by the IIS application host process are set correctly and that the account has the appropriate permissions.</span></span> <span data-ttu-id="8092b-155">プロセス id に使用されるアカウントの場合のアクセス許可し、アカウントを変更またはアカウントに適切なアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="8092b-155">If the account used for the process identity has insufficient permissions then either change the account or grant the account the appropriate permissions.</span></span>  
  
5.  <span data-ttu-id="8092b-156">説明されている RegMon および FileMon ユーティリティを使用して[トラブルシューティングのために使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)ファイルまたはレジストリのアクセス許可に関する問題を診断します。</span><span class="sxs-lookup"><span data-stu-id="8092b-156">Use the RegMon and FileMon utilities described in [Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) to diagnose file or registry access permissions problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8092b-157">参照</span><span class="sxs-lookup"><span data-stu-id="8092b-157">See Also</span></span>  
 <span data-ttu-id="8092b-158">[BizTalk Server のアクセス許可のトラブルシューティング](../core/troubleshooting-biztalk-server-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="8092b-158">[Troubleshooting BizTalk Server Permissions](../core/troubleshooting-biztalk-server-permissions.md) </span></span>  
 [<span data-ttu-id="8092b-159">IIS 7.0:IIS 7.0 での認証の構成</span><span class="sxs-lookup"><span data-stu-id="8092b-159">IIS 7.0: Configuring Authentication in IIS 7.0</span></span>](http://go.microsoft.com/fwlink/?LinkId=129909)