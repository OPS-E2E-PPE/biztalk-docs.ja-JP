---
title: IIS のアクセス許可の問題を解決するためのガイドライン |Microsoft ドキュメント
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
ms.openlocfilehash: eb91509ec3ad1c329190c848c25a60434f93499e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="guidelines-for-resolving-iis-permissions-problems"></a><span data-ttu-id="3352e-102">IIS のアクセス許可の問題を解決するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="3352e-102">Guidelines for Resolving IIS Permissions Problems</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3352e-103"> では、Web サービス サポートや HTTP、SOAP、Windows SharePoint Services の各アダプターで、Microsoft インターネット インフォメーション サービス (IIS) を広範に使用します。</span><span class="sxs-lookup"><span data-stu-id="3352e-103"> makes extensive use of Microsoft Internet Information Services (IIS) for Web services support and for use with the HTTP, SOAP, and Windows SharePoint Services adapters.</span></span>  
  
 <span data-ttu-id="3352e-104">IIS のアクセス許可に関する問題のトラブルシューティングを行う場合は、IIS でアプリケーション分離がどのように実装されるかを理解しておくと役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="3352e-104">It is helpful to understand how IIS implements application isolation before troubleshooting IIS permissions problems.</span></span>  
  
 <span data-ttu-id="3352e-105">IIS には、独自のメモリ領域で実行される個別のホスト プロセスとして IIS アプリケーションを作成するための機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="3352e-105">IIS provides functionality for creating IIS applications as distinct host processes that are run in their own memory space.</span></span> <span data-ttu-id="3352e-106">IIS アプリケーション ホストを作成すると、しする必要がありますを定義するアクセス許可、IIS アプリケーション ホストの 2 つのセット**プロセス id**と IIS アプリケーション ホスト**ユーザー アクセス権**です。</span><span class="sxs-lookup"><span data-stu-id="3352e-106">Once you create an IIS application host, then you must define two sets of permissions, the IIS application host **process identity** and the IIS application host **user access rights**.</span></span> <span data-ttu-id="3352e-107">IIS のアクセス許可に関する問題のトラブルシューティングでは、上記のアクセス許可セットをそれぞれ調べる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3352e-107">You should examine each of these permissions sets when troubleshooting IIS permissions problems.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3352e-108">**プロセス id**と**ユーザー アクセス権**とも呼びますが、**セキュリティ コンテキスト**IIS アプリケーション ホスト プロセスのです。</span><span class="sxs-lookup"><span data-stu-id="3352e-108">The **process identity** and **user access rights** are also referred to as the **security context** of the IIS application host process.</span></span>  
  
 <span data-ttu-id="3352e-109">設定する方法について説明**プロセス id**と**ユーザー アクセス権**IIS アプリケーション ホスト プロセスのおよび IIS のアクセス許可の問題を解決するための一般的なガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="3352e-109">This topic describes how to set **process identity** and **user access rights** for an IIS application host process and gives some general guidelines for resolving IIS permissions problems.</span></span>  
  
## <a name="setting-iis-application-host-process-identity"></a><span data-ttu-id="3352e-110">IIS アプリケーション ホストのプロセス ID の設定</span><span class="sxs-lookup"><span data-stu-id="3352e-110">Setting IIS Application Host Process Identity</span></span>  
 <span data-ttu-id="3352e-111">IIS アプリケーション ホスト プロセスの構成は、ホスト プロセスが提供する機能のレベルによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3352e-111">Configuration of an IIS application host process can vary depending on the level of functionality being served by the host process.</span></span> <span data-ttu-id="3352e-112">たとえば、静的な HTML ページのみを処理する IIS アプリケーション ホスト プロセスは ASP ページや ASP.NET アプリケーション、IIS アプリケーション ホスト プロセスとは異なる構成通常します。</span><span class="sxs-lookup"><span data-stu-id="3352e-112">For example, an IIS application host process that only serves static HTML pages is typically configured differently than an IIS application host process that serves ASP pages or ASP.NET applications.</span></span>  
  
 <span data-ttu-id="3352e-113">また、IIS アプリケーション ホスト プロセスの構成は、アプリケーションをホストする IIS のバージョンによっても異なります。</span><span class="sxs-lookup"><span data-stu-id="3352e-113">Configuration of an IIS application host process also varies depending on the version of IIS that is hosting the application.</span></span> <span data-ttu-id="3352e-114">Windows Server 2008 (IIS 7.0) で実行されているアプリケーションのホスト プロセス ID は、このアプリケーションに関連付けられているアプリケーション プールの ID によって決まります。</span><span class="sxs-lookup"><span data-stu-id="3352e-114">The host process identity of applications running on Windows Server 2008 (IIS 7.0) is governed by the identity of the application pool associated with the application.</span></span>  
  
### <a name="setting-iis-process-identity-for-iis-70-on-windows-server-2008-or-windows-vista"></a><span data-ttu-id="3352e-115">Windows Server 2008 または Windows Vista 上の IIS 7.0 の IIS プロセス ID の設定</span><span class="sxs-lookup"><span data-stu-id="3352e-115">Setting IIS Process Identity for IIS 7.0 on Windows Server 2008 or Windows Vista</span></span>  
  
1.  <span data-ttu-id="3352e-116">をクリックして**開始**、し**すべてのプログラム**、 をクリック**インターネット インフォメーション サービス (IIS) 7 マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="3352e-116">Click **Start**, then **All Programs**, and click **Internet Information Services (IIS) 7 Manager**.</span></span>  
  
2.  <span data-ttu-id="3352e-117">インターネット インフォメーション サービス (IIS) マネージャーでは、展開*\<コンピューター名\>***(ユーザー アカウント)**  をクリック**アプリケーション プール**です。</span><span class="sxs-lookup"><span data-stu-id="3352e-117">In Internet Information Services (IIS) Manager, expand *\<computer name\>***(User account)** and click **Application Pools**.</span></span>  
  
3.  <span data-ttu-id="3352e-118">アプリケーション プールを右クリックし、をクリックして**ビュー アプリケーション**にアプリケーション プールに関連付けられているアプリケーションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3352e-118">Right-click an application pool and click **View Applications** to see the applications associated with the application pool.</span></span>  
  
4.  <span data-ttu-id="3352e-119">アプリケーション プールを右クリックし、をクリックして**詳細設定**アプリケーション プールの詳細設定 ダイアログを表示します。</span><span class="sxs-lookup"><span data-stu-id="3352e-119">Right-click an application pool and click **Advanced Settings** to display the Advanced Settings dialog for the application pool.</span></span>  
  
5.  <span data-ttu-id="3352e-120">横に、省略記号 (...) ボタンをクリックして、アプリケーション プールの id を変更**Identity**下にある、**プロセス モデル**のセクションで、**詳細設定**ダイアログボックスです。</span><span class="sxs-lookup"><span data-stu-id="3352e-120">Modify the identity for the application pool by clicking the ellipsis (…) button next to **Identity** under the **Process Model** section of the **Advanced Settings** dialog box.</span></span>  
  
## <a name="setting-user-access-rights-for-the-iis-server"></a><span data-ttu-id="3352e-121">IIS サーバーのユーザー アクセス権の設定</span><span class="sxs-lookup"><span data-stu-id="3352e-121">Setting User Access Rights for the IIS Server</span></span>  
 <span data-ttu-id="3352e-122">プロセス ID では実行中の IIS アプリケーション ホスト プロセスで使用できるセキュリティ コンテキストを管理しますが、ユーザーのアクセス許可では、提供される Web ページに実際にアクセスしているアカウントのセキュリティ コンテキストを管理します。</span><span class="sxs-lookup"><span data-stu-id="3352e-122">While process identity governs the security context available to the running IIS application host process, user access permissions govern the security context for the account that is actually accessing the Web page(s) being served.</span></span> <span data-ttu-id="3352e-123">アクセス許可エラーを回避するには、両方のセキュリティ コンテキストに対してアクセス許可を適切に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3352e-123">Permissions must be set appropriately for both security contexts to avoid permissions errors.</span></span>  
  
 <span data-ttu-id="3352e-124">IIS 7.0 では、次のユーザー認証方式がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3352e-124">IIS 7.0 supports the following user authentication methods:</span></span>  
  
-   <span data-ttu-id="3352e-125">**匿名アクセス:**匿名接続を確立することができます。</span><span class="sxs-lookup"><span data-stu-id="3352e-125">**Anonymous access:** Allows users to establish an anonymous connection.</span></span> <span data-ttu-id="3352e-126">IIS サーバーは、指定された guest アカウントでユーザーをログオンさせます。</span><span class="sxs-lookup"><span data-stu-id="3352e-126">The IIS server logs on the user with the specified guest account.</span></span>  
  
-   <span data-ttu-id="3352e-127">**ASP.NET の偽装**により、2 つの異なるコンテキストのいずれかで実行するアプリケーション: または IIS で認証されたユーザーとして任意のアカウントを設定することです。</span><span class="sxs-lookup"><span data-stu-id="3352e-127">**ASP.NET Impersonation** Allows an application to run in one of two different contexts: either as the user authenticated by IIS or as an arbitrary account that you set up.</span></span>  
  
-   <span data-ttu-id="3352e-128">**基本認証:**パスワードをプレーン テキストで暗号化されていない形式でネットワーク経由で送信します。</span><span class="sxs-lookup"><span data-stu-id="3352e-128">**Basic authentication:** Transmits passwords across the network in plaintext, an unencrypted form.</span></span>  
  
-   <span data-ttu-id="3352e-129">**ダイジェスト認証:**はプレーン テキストのパスワードではなく、ネットワーク経由でハッシュ値を送信する、Active Directory アカウントでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="3352e-129">**Digest authentication:** Works only with Active Directory accounts, sending a hash value over the network, rather than a plaintext password.</span></span> <span data-ttu-id="3352e-130">ダイジェスト認証は、プロキシ サーバーやその他のファイアウォールの枠を越えて機能し、WebDAV (Web Distributed Authoring and Versioning) ディレクトリで使用できます。</span><span class="sxs-lookup"><span data-stu-id="3352e-130">Digest authentication works across proxy servers and other firewalls and is available on Web Distributed Authoring and Versioning (WebDAV) directories.</span></span> <span data-ttu-id="3352e-131">ダイジェスト認証を使用するには、まず匿名認証を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3352e-131">Use of Digest authentication requires that Anonymous authentication is disabled first.</span></span>  
  
-   <span data-ttu-id="3352e-132">**フォーム認証**認証トラフィック量が多いサイトやパブリック サーバー上のアプリケーションに対応します。</span><span class="sxs-lookup"><span data-stu-id="3352e-132">**Forms Authentication** Accommodates authentication for high-traffic sites or applications on public servers.</span></span> <span data-ttu-id="3352e-133">フォーム認証を使用すると、オペレーティング システムによって提供される認証メカニズムに依存することなく、クライアントの登録と認証をアプリケーション レベルで管理できます。</span><span class="sxs-lookup"><span data-stu-id="3352e-133">Forms authentication lets you manage client registration and authentication at the application level, instead of relying on the authentication mechanisms provided by the operating system.</span></span>  
  
-   <span data-ttu-id="3352e-134">**Windows 認証:**クライアント接続の認証に Windows ドメインで認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="3352e-134">**Windows authentication:** Uses authentication on your Windows domain to authenticate client connections.</span></span>  
  
#### <a name="to-set-user-access-rights-for-a-virtual-directory-in-iis-70"></a><span data-ttu-id="3352e-135">IIS 7.0 で仮想ディレクトリのユーザー アクセス権を設定するには</span><span class="sxs-lookup"><span data-stu-id="3352e-135">To set user access rights for a virtual directory in IIS 7.0</span></span>  
  
1.  <span data-ttu-id="3352e-136">インターネット インフォメーション サービス (IIS) マネージャーで、展開*\<コンピューター名\>*、**サイト**、および**Default Web Site** で**接続**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="3352e-136">In the Internet Information Services (IIS) Manager, expand *\<computer name\>*, **Sites**, and **Default Web Site** in the **Connections** pane.</span></span>  
  
2.  <span data-ttu-id="3352e-137">クリックして、仮想ディレクトリを選択し、をクリックして、**機能ビュー**を仮想ディレクトリの構成可能な機能を一覧表示 [ワークスペース] ウィンドウの下部にあります。</span><span class="sxs-lookup"><span data-stu-id="3352e-137">Click to select the virtual directory and click the **Features View** at the bottom of the Workspace pane to list the configurable features for the virtual directory.</span></span>  
  
3.  <span data-ttu-id="3352e-138">ダブルクリックして、**認証**を仮想ディレクトリを有効になっている認証方法を一覧表示 [ワークスペース] ウィンドウで機能します。</span><span class="sxs-lookup"><span data-stu-id="3352e-138">Double-click the **Authentication** feature in the Workspace pane to list the authentication methods that are enabled for the virtual directory.</span></span>  
  
4.  <span data-ttu-id="3352e-139">クリックして選択するには有効にするにまたは無効にし、いずれかをクリックする認証方法**を無効にする**または**を有効にする**で、**アクション**IIS マネージャーのウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="3352e-139">Click to select the authentication method that you would like to enable or disable and click either **Disable** or **Enable** in the **Actions** pane of the IIS Manager.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3352e-140">場合**への匿名アクセスを有効にする**は有効な場合、IIS では設定ユーザー アクセス権を匿名ユーザーとして構成されている id として認証方法を有効になっている、他のユーザー アクセス権を設定する前にします。</span><span class="sxs-lookup"><span data-stu-id="3352e-140">If **Enable anonymous access** is enabled, IIS will set user access rights as the configured Anonymous user identity before setting user access rights with any other enabled authentication methods.</span></span>  
    >   
    >  <span data-ttu-id="3352e-141">匿名ユーザー id を構成するを右クリックして、**匿名認証**メソッドとクリック**編集**を表示する、**匿名認証資格情報の編集**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="3352e-141">To configure the Anonymous user identity, right-click the **Anonymous Authentication** method and click **Edit** to display the **Edit Anonymous Authentication Credentials** dialog.</span></span>  
  
## <a name="general-guidelines-for-resolving-iis-permissions-problems"></a><span data-ttu-id="3352e-142">IIS のアクセス許可の問題を解決するための一般的なガイドライン</span><span class="sxs-lookup"><span data-stu-id="3352e-142">General Guidelines for Resolving IIS Permissions Problems</span></span>  
 <span data-ttu-id="3352e-143">IIS のアクセス許可に関するトラブルシューティングを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3352e-143">Follow these steps to troubleshoot IIS permissions:</span></span>  
  
1.  <span data-ttu-id="3352e-144">IIS サーバー コンピューターのアプリケーション ログでエラーの有無を確認します。</span><span class="sxs-lookup"><span data-stu-id="3352e-144">Check the application log of the IIS Server computer for errors.</span></span>  
  
2.  <span data-ttu-id="3352e-145">手順に従います[IIS 7.0: IIS 7.0 で失敗した要求のトレースを構成する](http://go.microsoft.com/fwlink/?LinkId=130600)IIS 7.0 コンピューターでアクセス許可の問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="3352e-145">Follow the steps in [IIS 7.0: Configuring Tracing for Failed Requests in IIS 7.0](http://go.microsoft.com/fwlink/?LinkId=130600) to troubleshoot permissions problems on IIS 7.0 computers.</span></span>  
  
3.  <span data-ttu-id="3352e-146">IIS サーバーの IIS ログ ファイルで HTTP 401 エラーの有無を確認します。</span><span class="sxs-lookup"><span data-stu-id="3352e-146">Check the IIS log files of the IIS server for HTTP 401 errors.</span></span>  
  
     <span data-ttu-id="3352e-147">既定では、Windows Server 2008 コンピューターまたは Windows Vista コンピューターの IIS ログ ファイルは、次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="3352e-147">By default the IIS log files on a computer running Windows Server 2008 or Windows Vista are located in the following directory:</span></span>  
  
     <span data-ttu-id="3352e-148">C:\inetpub\logs\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="3352e-148">C:\inetpub\logs\LogFiles\W3SVC1\\</span></span>  
  
    -   <span data-ttu-id="3352e-149">IIS ログ ファイルの IIS 7.0 コンピューターには、HTTP 401 エラーが含まれています手順をマイクロソフト サポート技術情報の記事 943891、"HTTP ステータス コード IIS 7.0 で"で使用可能な[http://support.microsoft.com/kb/943891](http://support.microsoft.com/kb/943891)を決定するには。副状態コードしステータス コードに基づいてアクセス許可の問題のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="3352e-149">If the IIS log file for an IIS 7.0 computer contains HTTP 401 errors, follow the steps in Microsoft Knowledge Base article 943891, "The HTTP status codes in IIS 7.0" available at [http://support.microsoft.com/kb/943891](http://support.microsoft.com/kb/943891) to determine the substatus code and to troubleshoot the permissions problem based on the status code.</span></span>  
  
    -   <span data-ttu-id="3352e-150">値を確認、 **cs-username** HTTP 401 エラーに関連付けられているフィールドです。</span><span class="sxs-lookup"><span data-stu-id="3352e-150">Check the value of the **cs-username** field associated with the HTTP 401 error.</span></span> <span data-ttu-id="3352e-151">このフィールドには、IIS サーバーにアクセスした認証ユーザーの名前が格納されています。</span><span class="sxs-lookup"><span data-stu-id="3352e-151">This field contains the name of the authenticated user who accessed the IIS server.</span></span> <span data-ttu-id="3352e-152">匿名ユーザー アカウントの場合、このフィールドの値はハイフン (-) になります。</span><span class="sxs-lookup"><span data-stu-id="3352e-152">The anonymous user account is represented by a hyphen (-) in this field.</span></span> <span data-ttu-id="3352e-153">このアカウントに、該当するリソースへのアクセス許可が付与されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3352e-153">Ensure that this account has permissions on the appropriate resources.</span></span>  
  
4.  <span data-ttu-id="3352e-154">IIS アプリケーションで使用するプロセス ID の資格情報が正しく設定されていること、およびアカウントに適切なアクセス許可が付与されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3352e-154">Verify that the process identity credentials used by the IIS application host process are set correctly and that the account has the appropriate permissions.</span></span> <span data-ttu-id="3352e-155">プロセス ID に使用されているアカウントに十分なアクセス許可がない場合は、アカウントを変更するか、アカウントに適切なアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="3352e-155">If the account used for the process identity has insufficient permissions then either change the account or grant the account the appropriate permissions.</span></span>  
  
5.  <span data-ttu-id="3352e-156">説明されている RegMon および FileMon ユーティリティを使用して[トラブルシューティングに使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)ファイルまたはレジストリのアクセス許可に関する問題を診断します。</span><span class="sxs-lookup"><span data-stu-id="3352e-156">Use the RegMon and FileMon utilities described in [Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) to diagnose file or registry access permissions problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3352e-157">参照</span><span class="sxs-lookup"><span data-stu-id="3352e-157">See Also</span></span>  
 <span data-ttu-id="3352e-158">[BizTalk Server のアクセス許可のトラブルシューティング](../core/troubleshooting-biztalk-server-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="3352e-158">[Troubleshooting BizTalk Server Permissions](../core/troubleshooting-biztalk-server-permissions.md) </span></span>  
 [<span data-ttu-id="3352e-159">IIS 7.0: IIS 7.0 での認証の構成</span><span class="sxs-lookup"><span data-stu-id="3352e-159">IIS 7.0: Configuring Authentication in IIS 7.0</span></span>](http://go.microsoft.com/fwlink/?LinkId=129909)