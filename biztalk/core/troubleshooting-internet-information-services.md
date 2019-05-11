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
ms.openlocfilehash: b2a099338dc882da6f5271cd28535a63edeb7302
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295703"
---
# <a name="troubleshooting-internet-information-services"></a><span data-ttu-id="74eca-102">インターネット インフォメーション サービスのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="74eca-102">Troubleshooting Internet Information Services</span></span>
<span data-ttu-id="74eca-103">Microsoft インターネット インフォメーション サービス (IIS) は Microsoft によって広く使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HTTP、SOAP、および Windows SharePoint Services アダプターのなどさまざまな機能です。</span><span class="sxs-lookup"><span data-stu-id="74eca-103">Microsoft Internet Information Services (IIS) is used extensively by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for various functionality including the HTTP, SOAP, and Windows SharePoint Services adapters.</span></span> <span data-ttu-id="74eca-104">このトピックでは、IIS とこれらの問題の解決方法で発生する既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="74eca-104">This topic describes some known issues that you may encounter with IIS and possible resolutions to these issues.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="74eca-105">既知の問題</span><span class="sxs-lookup"><span data-stu-id="74eca-105">Known Issues</span></span>  
 <span data-ttu-id="74eca-106">HTTP エラー メッセージの簡易表示を無効にする Internet Explorer を構成しない限り、このトピックに記載されているエラーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="74eca-106">The errors documented in this topic may not be displayed unless you configure Internet Explorer to disable friendly HTTP error messages.</span></span>  
  
#### <a name="to-configure-internet-explorer-to-disable-friendly-http-error-messages"></a><span data-ttu-id="74eca-107">HTTP エラー メッセージの簡易表示を無効にする Internet Explorer を構成するには</span><span class="sxs-lookup"><span data-stu-id="74eca-107">To configure Internet Explorer to disable friendly HTTP error messages</span></span>  
  
1.  <span data-ttu-id="74eca-108">**ツール** メニューのをクリックして**インターネット オプション**します。</span><span class="sxs-lookup"><span data-stu-id="74eca-108">On the **Tools** menu, click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="74eca-109">**詳細設定**  タブで、**ブラウズ** セクションで、クリア、**フレンドリ HTTP エラー メッセージを表示する**チェック ボックスをオンにし**ok**。</span><span class="sxs-lookup"><span data-stu-id="74eca-109">On the **Advanced** tab, in the **Browsing** section, clear the **Show friendly HTTP error messages** check box, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="74eca-110">Internet Explorer を閉じます。</span><span class="sxs-lookup"><span data-stu-id="74eca-110">Close Internet Explorer.</span></span>  
  
#### <a name="http-404---file-not-found-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="74eca-111">"HTTP 404 - ファイルが見つかりませんでした"エラーは、IIS サーバー上の Web ページにアクセスするときに発生します。</span><span class="sxs-lookup"><span data-stu-id="74eca-111">"HTTP 404 - File not found" error occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="74eca-112">問題</span><span class="sxs-lookup"><span data-stu-id="74eca-112">Problem</span></span>  
 <span data-ttu-id="74eca-113">IIS サーバー上の Web ページにアクセスしようとしたときに、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="74eca-113">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="74eca-114">ページが見つかりません</span><span class="sxs-lookup"><span data-stu-id="74eca-114">Page Cannot Be Found</span></span>  
  
 <span data-ttu-id="74eca-115">\- - または -</span><span class="sxs-lookup"><span data-stu-id="74eca-115">\- or -</span></span>  
  
 <span data-ttu-id="74eca-116">HTTP 404 - ファイルが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="74eca-116">HTTP 404 - File not found</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="74eca-117">原因</span><span class="sxs-lookup"><span data-stu-id="74eca-117">Cause</span></span>  
 <span data-ttu-id="74eca-118">このエラーは、次の理由で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="74eca-118">This error may occur for the following reasons:</span></span>  
  
-   <span data-ttu-id="74eca-119">要求されたファイルの名前が変更されています。</span><span class="sxs-lookup"><span data-stu-id="74eca-119">The requested file has been renamed.</span></span>  
  
-   <span data-ttu-id="74eca-120">要求されたファイルが別の場所に移動または削除されています。</span><span class="sxs-lookup"><span data-stu-id="74eca-120">The requested file has been moved to another location or deleted.</span></span>  
  
-   <span data-ttu-id="74eca-121">要求されたファイルは、メンテナンス、アップグレード、またはその他の不明なエラーの原因のため一時的にご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="74eca-121">The requested file is temporarily unavailable due to maintenance, upgrades, or other unknown causes.</span></span>  
  
-   <span data-ttu-id="74eca-122">要求されたファイルが存在しません。</span><span class="sxs-lookup"><span data-stu-id="74eca-122">The requested file does not exist.</span></span>  
  
-   <span data-ttu-id="74eca-123">IIS 6.0:適切な Web サービス拡張機能または MIME の種類が無効です。</span><span class="sxs-lookup"><span data-stu-id="74eca-123">IIS 6.0: The appropriate Web service extension or MIME type is not enabled.</span></span>  
  
-   <span data-ttu-id="74eca-124">仮想ディレクトリは、別のサーバー上のドライブのルートにマップされます。</span><span class="sxs-lookup"><span data-stu-id="74eca-124">A virtual directory is mapped to the root of a drive on another server.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="74eca-125">解決策</span><span class="sxs-lookup"><span data-stu-id="74eca-125">Resolution</span></span>  
 <span data-ttu-id="74eca-126">マイクロソフト サポート技術情報資料 248033、"一般的な理由の IIS サーバーには、「HTTP 404 - ファイルが見つかりません」エラーが返されます。"解決方法」の手順で使用可能な[ http://support.microsoft.com/kb/248033](http://support.microsoft.com/kb/248033)します。</span><span class="sxs-lookup"><span data-stu-id="74eca-126">Follow the steps in the RESOLUTION section of Microsoft Knowledge Base article 248033, "Common reasons IIS Server returns "HTTP 404 - File not found" error" available at [http://support.microsoft.com/kb/248033](http://support.microsoft.com/kb/248033).</span></span>  
  
#### <a name="cannot-find-server-or-dns-error-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="74eca-127">IIS サーバー上の Web ページにアクセスするときに発生する"cannot find server or DNS エラー"</span><span class="sxs-lookup"><span data-stu-id="74eca-127">"Cannot find server or DNS Error error" occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="74eca-128">問題</span><span class="sxs-lookup"><span data-stu-id="74eca-128">Problem</span></span>  
 <span data-ttu-id="74eca-129">IIS サーバー上の Web ページにアクセスしようとしたときに、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="74eca-129">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="74eca-130">ページを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="74eca-130">The Page Cannot Be Displayed</span></span>  
  
 <span data-ttu-id="74eca-131">\- - または -</span><span class="sxs-lookup"><span data-stu-id="74eca-131">\- or -</span></span>  
  
 <span data-ttu-id="74eca-132">サーバーまたは DNS エラーを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="74eca-132">Cannot find server or DNS Error</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="74eca-133">原因</span><span class="sxs-lookup"><span data-stu-id="74eca-133">Cause</span></span>  
 <span data-ttu-id="74eca-134">このエラーは、次の理由で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="74eca-134">This error may occur for the following reasons:</span></span>  
  
-   <span data-ttu-id="74eca-135">Internet Explorer の接続設定が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="74eca-135">Your Internet Explorer connection settings are incorrect.</span></span>  
  
-   <span data-ttu-id="74eca-136">正しく構成されている、機能していないまたは互換性のないファイアウォールまたはプロキシ ソフトウェアがインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="74eca-136">Incorrectly configured, non-functioning, or incompatible firewall or proxy software has been installed.</span></span>  
  
-   <span data-ttu-id="74eca-137">ホスト ファイルに正しくないエントリがあります。</span><span class="sxs-lookup"><span data-stu-id="74eca-137">There is an incorrect entry in a Hosts file.</span></span>  
  
-   <span data-ttu-id="74eca-138">ネットワーク アダプターが正しく機能していないまたは互換性のないネットワーク アダプター ドライバーがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="74eca-138">Your network adapter is not functioning correctly or you have incompatible network adapter drivers installed.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="74eca-139">解決策</span><span class="sxs-lookup"><span data-stu-id="74eca-139">Resolution</span></span>  
 <span data-ttu-id="74eca-140">マイクロソフト サポート技術情報の資料 326155 の解決方法」の手順に従って"Internet Explorer で Web サイトにアクセスしようとすると、エラー メッセージ。「ページを表示できません」"でご利用いただけます[ http://support.microsoft.com/kb/326155](http://support.microsoft.com/kb/326155)します。</span><span class="sxs-lookup"><span data-stu-id="74eca-140">Follow the steps in the RESOLUTION section of Microsoft Knowledge Base article 326155, "Error message when you try to access a Web site in Internet Explorer: "Page Cannot Be Displayed"" available at [http://support.microsoft.com/kb/326155](http://support.microsoft.com/kb/326155).</span></span>  
  
#### <a name="401---access-denied-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="74eca-141">「401-アクセスが拒否されました」エラーは、IIS サーバー上の Web ページにアクセスするときに発生します。</span><span class="sxs-lookup"><span data-stu-id="74eca-141">"401 - Access denied" error occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="74eca-142">問題</span><span class="sxs-lookup"><span data-stu-id="74eca-142">Problem</span></span>  
 <span data-ttu-id="74eca-143">IIS サーバー上の Web ページにアクセスしようとしたときに、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="74eca-143">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="74eca-144">401-アクセスが拒否されました</span><span class="sxs-lookup"><span data-stu-id="74eca-144">401 - Access denied</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="74eca-145">原因</span><span class="sxs-lookup"><span data-stu-id="74eca-145">Cause</span></span>  
 <span data-ttu-id="74eca-146">IIS では、エラーの原因をより具体的に示すいくつかのさまざまな 401 エラーを定義します。</span><span class="sxs-lookup"><span data-stu-id="74eca-146">IIS defines several different 401 errors that indicate a more specific cause of the error.</span></span> <span data-ttu-id="74eca-147">これらの特定のエラー コードは、ブラウザーで表示されます。</span><span class="sxs-lookup"><span data-stu-id="74eca-147">These specific error codes are displayed in the browser:</span></span>  
  
- <span data-ttu-id="74eca-148">401.1 - ログオンに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="74eca-148">401.1 - Logon failed.</span></span>  
  
- <span data-ttu-id="74eca-149">401.2 - サーバーの構成により、ログオンに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="74eca-149">401.2 - Logon failed due to server configuration.</span></span>  
  
- <span data-ttu-id="74eca-150">401.3 - ACL をリソースにします。</span><span class="sxs-lookup"><span data-stu-id="74eca-150">401.3 - Unauthorized due to ACL on resource.</span></span>  
  
- <span data-ttu-id="74eca-151">401.4 - 承認フィルターによって失敗しました。</span><span class="sxs-lookup"><span data-stu-id="74eca-151">401.4 - Authorization failed by filter.</span></span>  
  
- <span data-ttu-id="74eca-152">401.5 - 承認 ISAPI または CGI アプリケーションが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="74eca-152">401.5 - Authorization failed by ISAPI/CGI application.</span></span>  
  
- <span data-ttu-id="74eca-153">401.7 – Web サーバーの URL 承認ポリシーによって拒否されたアクセス。</span><span class="sxs-lookup"><span data-stu-id="74eca-153">401.7 – Access denied by URL authorization policy on the Web server.</span></span> <span data-ttu-id="74eca-154">このエラー コードは、IIS 6.0 に固有です。</span><span class="sxs-lookup"><span data-stu-id="74eca-154">This error code is specific to IIS 6.0.</span></span>  
  
  <span data-ttu-id="74eca-155">IIS 7.0 の状態コードの一覧は、マイクロソフト サポート技術情報の資料 943891「、「IIS 7.0 の HTTP 状態コード」を参照してください。 いただけます[ http://support.microsoft.com/kb/943891](http://support.microsoft.com/kb/943891)します。</span><span class="sxs-lookup"><span data-stu-id="74eca-155">For a complete list of the IIS 7.0 status codes, see Microsoft Knowledge Base article 943891, "The HTTP status codes in IIS 7.0" available at [http://support.microsoft.com/kb/943891](http://support.microsoft.com/kb/943891).</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="74eca-156">解決策</span><span class="sxs-lookup"><span data-stu-id="74eca-156">Resolution</span></span>  
 <span data-ttu-id="74eca-157">次の手順では、 [IIS アクセス許可の問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)IIS のアクセス許可の問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="74eca-157">Follow the steps in [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md) to resolve IIS permissions problems.</span></span>  
  
#### <a name="500---internal-server-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="74eca-158">「500-内部サーバー エラー」は、IIS サーバー上の Web ページにアクセスするときに発生します。</span><span class="sxs-lookup"><span data-stu-id="74eca-158">"500 - Internal server error" occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="74eca-159">問題</span><span class="sxs-lookup"><span data-stu-id="74eca-159">Problem</span></span>  
 <span data-ttu-id="74eca-160">IIS サーバー上の Web ページにアクセスしようとしたときに、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="74eca-160">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="74eca-161">500-内部サーバー エラー</span><span class="sxs-lookup"><span data-stu-id="74eca-161">500 - Internal server error</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="74eca-162">原因</span><span class="sxs-lookup"><span data-stu-id="74eca-162">Cause</span></span>  
 <span data-ttu-id="74eca-163">このエラー メッセージは、さまざまなサーバー側の問題によることができます。</span><span class="sxs-lookup"><span data-stu-id="74eca-163">This error message can be caused by a wide variety of server-side problems.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="74eca-164">解決策</span><span class="sxs-lookup"><span data-stu-id="74eca-164">Resolution</span></span>  
 <span data-ttu-id="74eca-165">問題を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="74eca-165">To resolve the issue, do the following:</span></span>  
  
- <span data-ttu-id="74eca-166">このエラーが発生した理由については、IIS サーバーのアプリケーション ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="74eca-166">Review the Application log of the IIS server for information about why this error occurs.</span></span>  
  
- <span data-ttu-id="74eca-167">IIS ログ ファイルまたは HTTPERR ログ ファイルでエラーの原因を特定するのに役立つ可能性がある情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="74eca-167">Review the IIS log files or HTTPERR log files for information that may be helpful for determining the cause of the error.</span></span> <span data-ttu-id="74eca-168">既定では、IIS が実行しているコンピューター上のファイルをログ[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]オペレーティング システムは、次のディレクトリに配置されます。</span><span class="sxs-lookup"><span data-stu-id="74eca-168">By default the IIS log files on a computer running [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] operating systems are located in the following directory:</span></span>  
  
   <span data-ttu-id="74eca-169"><em>%WinDir%\\</em>system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="74eca-169"><em>%WinDir%\\</em>system32\LogFiles\W3SVC1\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="74eca-170">*%Windir%* IIS サーバー上の Windows ディレクトリの場所のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="74eca-170">*%WinDir%* is a placeholder for the location of the Windows directory on the IIS server.</span></span>  
  
   <span data-ttu-id="74eca-171">既定では、IIS は、Windows Server 2008 または Windows Vista を実行するコンピューターでログ ファイルは、次のディレクトリに配置されます。</span><span class="sxs-lookup"><span data-stu-id="74eca-171">By default the IIS log files on a computer running Windows Server 2008 or Windows Vista are located in the following directory:</span></span>  
  
   <span data-ttu-id="74eca-172">C:\inetpub\logs\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="74eca-172">C:\inetpub\logs\LogFiles\W3SVC1\\</span></span>  
  
   <span data-ttu-id="74eca-173">既定では、HTTPERR ログ ファイル[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="74eca-173">By default the HTTPERR log files on [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] are located in the following directory:</span></span>  
  
   <span data-ttu-id="74eca-174"><em>%WinDir%</em>system32LogFilesHTTPERR</span><span class="sxs-lookup"><span data-stu-id="74eca-174"><em>%WinDir%</em>system32LogFilesHTTPERR</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="74eca-175">HTTPERR ログ ファイルで使用できるのみ、 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、または Windows Vista のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="74eca-175">The HTTPERR log file is only available on a [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], or Windows Vista computer.</span></span>  
  
#### <a name="service-unavailable-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="74eca-176">「サービスは利用できません」エラーは、IIS サーバー上の Web ページにアクセスするときに発生します。</span><span class="sxs-lookup"><span data-stu-id="74eca-176">"Service Unavailable" error occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="74eca-177">問題</span><span class="sxs-lookup"><span data-stu-id="74eca-177">Problem</span></span>  
 <span data-ttu-id="74eca-178">IIS サーバー上の Web ページにアクセスしようとしたときに、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="74eca-178">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="74eca-179">サービス利用不可</span><span class="sxs-lookup"><span data-stu-id="74eca-179">Service Unavailable</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="74eca-180">原因</span><span class="sxs-lookup"><span data-stu-id="74eca-180">Cause</span></span>  
 <span data-ttu-id="74eca-181">このエラーの最も一般的な原因は、Web ページのアプリケーション プール (IIS 6.0 および IIS 7.0) が停止していることです。</span><span class="sxs-lookup"><span data-stu-id="74eca-181">The most common cause for this error is that the application pool (IIS 6.0 and IIS 7.0) for the Web page is stopped.</span></span> <span data-ttu-id="74eca-182">これは、問題は発生アプリケーション プールまたは COM + アプリケーションが構成されている場合、Id を指定されたユーザー名またはパスワードが無効です。</span><span class="sxs-lookup"><span data-stu-id="74eca-182">This commonly occurs if the application pool or COM+ application is configured with an Identity for which the specified user name and or password is invalid.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="74eca-183">解決策</span><span class="sxs-lookup"><span data-stu-id="74eca-183">Resolution</span></span>  
 <span data-ttu-id="74eca-184">トピックの「IIS アプリケーション ホスト プロセス Id の設定」セクションの手順に従って[IIS アクセス許可問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)適切なホスト プロセス id を設定します。</span><span class="sxs-lookup"><span data-stu-id="74eca-184">Follow the steps in the "Setting IIS Application Host Process Identity" section of the topic [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md) to set the appropriate host process identity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74eca-185">参照</span><span class="sxs-lookup"><span data-stu-id="74eca-185">See Also</span></span>  
 [<span data-ttu-id="74eca-186">IIS のアクセス許可の問題を解決するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="74eca-186">Guidelines for Resolving IIS Permissions Problems</span></span>](../core/guidelines-for-resolving-iis-permissions-problems.md)