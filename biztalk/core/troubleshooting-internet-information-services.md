---
title: インターネット インフォメーション サービスのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f77084f1-5797-42ab-bbf6-fe815144232e
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f7ca928aa2e47b5c62548aba02834b96d6a3baf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006659"
---
# <a name="troubleshooting-internet-information-services"></a><span data-ttu-id="0fe2b-102">インターネット インフォメーション サービスのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0fe2b-102">Troubleshooting Internet Information Services</span></span>
<span data-ttu-id="0fe2b-103">Microsoft インターネット インフォメーション サービス (IIS) は、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] において、HTTP アダプター、SOAP アダプター、Windows SharePoint Services アダプターなど、さまざまな機能に幅広く使用されます。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-103">Microsoft Internet Information Services (IIS) is used extensively by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for various functionality including the HTTP, SOAP, and Windows SharePoint Services adapters.</span></span> <span data-ttu-id="0fe2b-104">このトピックでは、IIS で発生する可能性がある既知の問題とその解決策について説明します。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-104">This topic describes some known issues that you may encounter with IIS and possible resolutions to these issues.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="0fe2b-105">既知の問題</span><span class="sxs-lookup"><span data-stu-id="0fe2b-105">Known Issues</span></span>  
 <span data-ttu-id="0fe2b-106">このトピックに記載されているエラーは、HTTP エラー メッセージの簡易表示を無効にするよう Internet Explorer を構成していない場合は、表示されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-106">The errors documented in this topic may not be displayed unless you configure Internet Explorer to disable friendly HTTP error messages.</span></span>  
  
#### <a name="to-configure-internet-explorer-to-disable-friendly-http-error-messages"></a><span data-ttu-id="0fe2b-107">HTTP エラー メッセージの簡易表示を無効にするよう Internet Explorer を構成するには</span><span class="sxs-lookup"><span data-stu-id="0fe2b-107">To configure Internet Explorer to disable friendly HTTP error messages</span></span>  
  
1.  <span data-ttu-id="0fe2b-108">**ツール** メニューのをクリックして**インターネット オプション**します。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-108">On the **Tools** menu, click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="0fe2b-109">**詳細設定**  タブで、**ブラウズ** セクションで、クリア、**フレンドリ HTTP エラー メッセージを表示する**チェック ボックスをオンにし**ok**。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-109">On the **Advanced** tab, in the **Browsing** section, clear the **Show friendly HTTP error messages** check box, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="0fe2b-110">Internet Explorer を閉じます。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-110">Close Internet Explorer.</span></span>  
  
#### <a name="http-404---file-not-found-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="0fe2b-111">IIS サーバー上の Web ページにアクセスすると "HTTP 404 - ファイルが見つかりません" エラーが発生する</span><span class="sxs-lookup"><span data-stu-id="0fe2b-111">"HTTP 404 - File not found" error occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="0fe2b-112">問題</span><span class="sxs-lookup"><span data-stu-id="0fe2b-112">Problem</span></span>  
 <span data-ttu-id="0fe2b-113">IIS サーバー上の Web ページにアクセスしようとすると、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-113">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="0fe2b-114">"ページが見つかりません。"</span><span class="sxs-lookup"><span data-stu-id="0fe2b-114">Page Cannot Be Found</span></span>  
  
 <span data-ttu-id="0fe2b-115">\- または -</span><span class="sxs-lookup"><span data-stu-id="0fe2b-115">\- or -</span></span>  
  
 <span data-ttu-id="0fe2b-116">“HTTP 404 - ファイルが見つかりません”</span><span class="sxs-lookup"><span data-stu-id="0fe2b-116">HTTP 404 - File not found</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="0fe2b-117">原因</span><span class="sxs-lookup"><span data-stu-id="0fe2b-117">Cause</span></span>  
 <span data-ttu-id="0fe2b-118">このエラーは次のような理由で発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-118">This error may occur for the following reasons:</span></span>  
  
-   <span data-ttu-id="0fe2b-119">要求されたファイルの名前が変更されている。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-119">The requested file has been renamed.</span></span>  
  
-   <span data-ttu-id="0fe2b-120">要求されたファイルが別の場所に移動されたか、削除されている。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-120">The requested file has been moved to another location or deleted.</span></span>  
  
-   <span data-ttu-id="0fe2b-121">保守、アップグレード、その他の理由により、要求されたファイルが一時的に使用できない。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-121">The requested file is temporarily unavailable due to maintenance, upgrades, or other unknown causes.</span></span>  
  
-   <span data-ttu-id="0fe2b-122">要求されたファイルが存在しない。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-122">The requested file does not exist.</span></span>  
  
-   <span data-ttu-id="0fe2b-123">IIS 6.0: 適切な Web サービスの拡張機能または MIME の種類が有効になっていない。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-123">IIS 6.0: The appropriate Web service extension or MIME type is not enabled.</span></span>  
  
-   <span data-ttu-id="0fe2b-124">仮想ディレクトリは、別のサーバー上のドライブのルートにマップされます。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-124">A virtual directory is mapped to the root of a drive on another server.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="0fe2b-125">解決策</span><span class="sxs-lookup"><span data-stu-id="0fe2b-125">Resolution</span></span>  
 <span data-ttu-id="0fe2b-126">マイクロソフト サポート技術情報資料 248033、"一般的な理由の IIS サーバーには、「HTTP 404 - ファイルが見つかりません」エラーが返されます。"解決方法」の手順で使用可能な[ http://support.microsoft.com/kb/248033](http://support.microsoft.com/kb/248033)します。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-126">Follow the steps in the RESOLUTION section of Microsoft Knowledge Base article 248033, "Common reasons IIS Server returns "HTTP 404 - File not found" error" available at [http://support.microsoft.com/kb/248033](http://support.microsoft.com/kb/248033).</span></span>  
  
#### <a name="cannot-find-server-or-dns-error-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="0fe2b-127">IIS サーバー上の Web ページへのアクセス時に "ページを表示できません。サーバーが見つからないか、DNS エラーです。" エラーが発生する</span><span class="sxs-lookup"><span data-stu-id="0fe2b-127">"Cannot find server or DNS Error error" occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="0fe2b-128">問題</span><span class="sxs-lookup"><span data-stu-id="0fe2b-128">Problem</span></span>  
 <span data-ttu-id="0fe2b-129">IIS サーバー上の Web ページにアクセスしようとすると、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-129">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="0fe2b-130">"ページを表示できません。"</span><span class="sxs-lookup"><span data-stu-id="0fe2b-130">The Page Cannot Be Displayed</span></span>  
  
 <span data-ttu-id="0fe2b-131">\- または -</span><span class="sxs-lookup"><span data-stu-id="0fe2b-131">\- or -</span></span>  
  
 <span data-ttu-id="0fe2b-132">"Cannot find server or DNS Error"</span><span class="sxs-lookup"><span data-stu-id="0fe2b-132">Cannot find server or DNS Error</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="0fe2b-133">原因</span><span class="sxs-lookup"><span data-stu-id="0fe2b-133">Cause</span></span>  
 <span data-ttu-id="0fe2b-134">このエラーは次のような理由で発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-134">This error may occur for the following reasons:</span></span>  
  
-   <span data-ttu-id="0fe2b-135">Internet Explorer の接続設定が正しくない。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-135">Your Internet Explorer connection settings are incorrect.</span></span>  
  
-   <span data-ttu-id="0fe2b-136">構成が正しくないか、構成されていないか、互換性のないファイアウォールまたはプロキシ ソフトウェアがインストールされている。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-136">Incorrectly configured, non-functioning, or incompatible firewall or proxy software has been installed.</span></span>  
  
-   <span data-ttu-id="0fe2b-137">ホスト ファイルに正しくないエントリがある。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-137">There is an incorrect entry in a Hosts file.</span></span>  
  
-   <span data-ttu-id="0fe2b-138">ネットワーク アダプターが正しく機能していないか、互換性のないネットワーク アダプター ドライバーがインストールされている。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-138">Your network adapter is not functioning correctly or you have incompatible network adapter drivers installed.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="0fe2b-139">解決策</span><span class="sxs-lookup"><span data-stu-id="0fe2b-139">Resolution</span></span>  
 <span data-ttu-id="0fe2b-140">マイクロソフト サポート技術情報の資料 326155 の解決方法」の手順に従って"Internet Explorer で Web サイトにアクセスしようとすると、エラー メッセージ:「ページを表示できません」"でご利用いただけます[ http://support.microsoft.com/kb/326155](http://support.microsoft.com/kb/326155)します。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-140">Follow the steps in the RESOLUTION section of Microsoft Knowledge Base article 326155, "Error message when you try to access a Web site in Internet Explorer: "Page Cannot Be Displayed"" available at [http://support.microsoft.com/kb/326155](http://support.microsoft.com/kb/326155).</span></span>  
  
#### <a name="401---access-denied-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="0fe2b-141">IIS サーバー上の Web ページへのアクセス時に "401 - アクセスが拒否されました" エラーが発生する</span><span class="sxs-lookup"><span data-stu-id="0fe2b-141">"401 - Access denied" error occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="0fe2b-142">問題</span><span class="sxs-lookup"><span data-stu-id="0fe2b-142">Problem</span></span>  
 <span data-ttu-id="0fe2b-143">IIS サーバー上の Web ページにアクセスしようとすると、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-143">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="0fe2b-144">“401 - アクセスが拒否されました”</span><span class="sxs-lookup"><span data-stu-id="0fe2b-144">401 - Access denied</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="0fe2b-145">原因</span><span class="sxs-lookup"><span data-stu-id="0fe2b-145">Cause</span></span>  
 <span data-ttu-id="0fe2b-146">IIS では、エラーの原因をより具体的に示すいくつかの 401 エラーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-146">IIS defines several different 401 errors that indicate a more specific cause of the error.</span></span> <span data-ttu-id="0fe2b-147">これらの限定的なエラー コードは、ブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-147">These specific error codes are displayed in the browser:</span></span>  
  
- <span data-ttu-id="0fe2b-148">“401.1 - 資格情報が無効のため、アクセスが拒否されました。”</span><span class="sxs-lookup"><span data-stu-id="0fe2b-148">401.1 - Logon failed.</span></span>  
  
- <span data-ttu-id="0fe2b-149">“401.2 – サーバーの構成によりアクセスが拒否されました。”</span><span class="sxs-lookup"><span data-stu-id="0fe2b-149">401.2 - Logon failed due to server configuration.</span></span>  
  
- <span data-ttu-id="0fe2b-150">“401.3 – 要求したリソースに設定された ACL によりアクセスが拒否されました。”</span><span class="sxs-lookup"><span data-stu-id="0fe2b-150">401.3 - Unauthorized due to ACL on resource.</span></span>  
  
- <span data-ttu-id="0fe2b-151">“401.4 – Web サーバーにインストールされたフィルターによって、認証が失敗しました。”</span><span class="sxs-lookup"><span data-stu-id="0fe2b-151">401.4 - Authorization failed by filter.</span></span>  
  
- <span data-ttu-id="0fe2b-152">“401.5 – ISAPI または CGI アプリケーションによって、認証が失敗しました。”</span><span class="sxs-lookup"><span data-stu-id="0fe2b-152">401.5 - Authorization failed by ISAPI/CGI application.</span></span>  
  
- <span data-ttu-id="0fe2b-153">“401.7 – Web サーバーの URL 承認ポリシーにより、アクセスが拒否されました。”</span><span class="sxs-lookup"><span data-stu-id="0fe2b-153">401.7 – Access denied by URL authorization policy on the Web server.</span></span> <span data-ttu-id="0fe2b-154">これは、IIS 6.0 固有のエラー コードです。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-154">This error code is specific to IIS 6.0.</span></span>  
  
  <span data-ttu-id="0fe2b-155">IIS 7.0 の状態コードの一覧は、マイクロソフト サポート技術情報の資料 943891「、「IIS 7.0 の HTTP 状態コード」を参照してください。 いただけます[ http://support.microsoft.com/kb/943891](http://support.microsoft.com/kb/943891)します。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-155">For a complete list of the IIS 7.0 status codes, see Microsoft Knowledge Base article 943891, "The HTTP status codes in IIS 7.0" available at [http://support.microsoft.com/kb/943891](http://support.microsoft.com/kb/943891).</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="0fe2b-156">解決策</span><span class="sxs-lookup"><span data-stu-id="0fe2b-156">Resolution</span></span>  
 <span data-ttu-id="0fe2b-157">次の手順では、 [IIS アクセス許可の問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)IIS のアクセス許可の問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-157">Follow the steps in [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md) to resolve IIS permissions problems.</span></span>  
  
#### <a name="500---internal-server-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="0fe2b-158">IIS サーバー上の Web ページにアクセスすると "500 - 内部サーバー エラー" が発生する</span><span class="sxs-lookup"><span data-stu-id="0fe2b-158">"500 - Internal server error" occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="0fe2b-159">問題</span><span class="sxs-lookup"><span data-stu-id="0fe2b-159">Problem</span></span>  
 <span data-ttu-id="0fe2b-160">IIS サーバー上の Web ページにアクセスしようとすると、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-160">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="0fe2b-161">“500 - 内部サーバー エラー”</span><span class="sxs-lookup"><span data-stu-id="0fe2b-161">500 - Internal server error</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="0fe2b-162">原因</span><span class="sxs-lookup"><span data-stu-id="0fe2b-162">Cause</span></span>  
 <span data-ttu-id="0fe2b-163">このエラー メッセージは、サーバー側のさまざまな問題が原因で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-163">This error message can be caused by a wide variety of server-side problems.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="0fe2b-164">解決策</span><span class="sxs-lookup"><span data-stu-id="0fe2b-164">Resolution</span></span>  
 <span data-ttu-id="0fe2b-165">この問題を解決するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-165">To resolve the issue, do the following:</span></span>  
  
- <span data-ttu-id="0fe2b-166">IIS サーバーのアプリケーション ログで、このエラーが発生する理由に関する情報がないか調べます。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-166">Review the Application log of the IIS server for information about why this error occurs.</span></span>  
  
- <span data-ttu-id="0fe2b-167">IIS ログ ファイルまたは HTTPERR ログ ファイルで、エラー原因の特定に役立つ可能性のある情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-167">Review the IIS log files or HTTPERR log files for information that may be helpful for determining the cause of the error.</span></span> <span data-ttu-id="0fe2b-168">既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] オペレーティング システムが稼働しているコンピューターの IIS ログ ファイルは、次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-168">By default the IIS log files on a computer running [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] operating systems are located in the following directory:</span></span>  
  
   <span data-ttu-id="0fe2b-169"><em>%Windir%\\</em>system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="0fe2b-169"><em>%WinDir%\\</em>system32\LogFiles\W3SVC1\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="0fe2b-170">*%Windir%* IIS サーバー上の Windows ディレクトリの場所のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-170">*%WinDir%* is a placeholder for the location of the Windows directory on the IIS server.</span></span>  
  
   <span data-ttu-id="0fe2b-171">既定では、Windows Server 2008 コンピューターまたは Windows Vista コンピューターの IIS ログ ファイルは、次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-171">By default the IIS log files on a computer running Windows Server 2008 or Windows Vista are located in the following directory:</span></span>  
  
   <span data-ttu-id="0fe2b-172">C:\inetpub\logs\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="0fe2b-172">C:\inetpub\logs\LogFiles\W3SVC1\\</span></span>  
  
   <span data-ttu-id="0fe2b-173">既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] の HTTPERR ログ ファイルは、次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-173">By default the HTTPERR log files on [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] are located in the following directory:</span></span>  
  
   <span data-ttu-id="0fe2b-174"><em>%Windir%</em>system32LogFilesHTTPERR</span><span class="sxs-lookup"><span data-stu-id="0fe2b-174"><em>%WinDir%</em>system32LogFilesHTTPERR</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="0fe2b-175">HTTPERR ログ ファイルを使用できるのは、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] または Windows Vista のコンピューターだけです。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-175">The HTTPERR log file is only available on a [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], or Windows Vista computer.</span></span>  
  
#### <a name="service-unavailable-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="0fe2b-176">IIS サーバー上の Web ページにアクセスすると "サービスは利用できません" エラーが発生する</span><span class="sxs-lookup"><span data-stu-id="0fe2b-176">"Service Unavailable" error occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="0fe2b-177">問題</span><span class="sxs-lookup"><span data-stu-id="0fe2b-177">Problem</span></span>  
 <span data-ttu-id="0fe2b-178">IIS サーバー上の Web ページにアクセスしようとすると、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-178">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="0fe2b-179">“サービスは利用できません”</span><span class="sxs-lookup"><span data-stu-id="0fe2b-179">Service Unavailable</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="0fe2b-180">原因</span><span class="sxs-lookup"><span data-stu-id="0fe2b-180">Cause</span></span>  
 <span data-ttu-id="0fe2b-181">このエラーの最も一般的な原因は、Web ページのアプリケーション プール (IIS 6.0 および IIS 7.0) が停止していることです。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-181">The most common cause for this error is that the application pool (IIS 6.0 and IIS 7.0) for the Web page is stopped.</span></span> <span data-ttu-id="0fe2b-182">一般には、アプリケーション プールまたは COM+ アプリケーションを構成している ID に無効なユーザー名またはパスワードが指定されている場合にこのエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-182">This commonly occurs if the application pool or COM+ application is configured with an Identity for which the specified user name and or password is invalid.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="0fe2b-183">解決策</span><span class="sxs-lookup"><span data-stu-id="0fe2b-183">Resolution</span></span>  
 <span data-ttu-id="0fe2b-184">トピックの「IIS アプリケーション ホスト プロセス Id の設定」セクションの手順に従って[IIS アクセス許可問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)適切なホスト プロセス id を設定します。</span><span class="sxs-lookup"><span data-stu-id="0fe2b-184">Follow the steps in the "Setting IIS Application Host Process Identity" section of the topic [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md) to set the appropriate host process identity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fe2b-185">参照</span><span class="sxs-lookup"><span data-stu-id="0fe2b-185">See Also</span></span>  
 [<span data-ttu-id="0fe2b-186">IIS のアクセス許可の問題を解決するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="0fe2b-186">Guidelines for Resolving IIS Permissions Problems</span></span>](../core/guidelines-for-resolving-iis-permissions-problems.md)