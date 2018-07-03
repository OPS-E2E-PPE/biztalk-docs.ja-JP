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
# <a name="troubleshooting-internet-information-services"></a>インターネット インフォメーション サービスのトラブルシューティング
Microsoft インターネット インフォメーション サービス (IIS) は、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] において、HTTP アダプター、SOAP アダプター、Windows SharePoint Services アダプターなど、さまざまな機能に幅広く使用されます。 このトピックでは、IIS で発生する可能性がある既知の問題とその解決策について説明します。  
  
## <a name="known-issues"></a>既知の問題  
 このトピックに記載されているエラーは、HTTP エラー メッセージの簡易表示を無効にするよう Internet Explorer を構成していない場合は、表示されない可能性があります。  
  
#### <a name="to-configure-internet-explorer-to-disable-friendly-http-error-messages"></a>HTTP エラー メッセージの簡易表示を無効にするよう Internet Explorer を構成するには  
  
1.  **ツール** メニューのをクリックして**インターネット オプション**します。  
  
2.  **詳細設定**  タブで、**ブラウズ** セクションで、クリア、**フレンドリ HTTP エラー メッセージを表示する**チェック ボックスをオンにし**ok**。  
  
3.  Internet Explorer を閉じます。  
  
#### <a name="http-404---file-not-found-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>IIS サーバー上の Web ページにアクセスすると "HTTP 404 - ファイルが見つかりません" エラーが発生する  
  
##### <a name="problem"></a>問題  
 IIS サーバー上の Web ページにアクセスしようとすると、次のようなエラーが表示されます。  
  
 "ページが見つかりません。"  
  
 \- または -  
  
 “HTTP 404 - ファイルが見つかりません”  
  
##### <a name="cause"></a>原因  
 このエラーは次のような理由で発生することがあります。  
  
-   要求されたファイルの名前が変更されている。  
  
-   要求されたファイルが別の場所に移動されたか、削除されている。  
  
-   保守、アップグレード、その他の理由により、要求されたファイルが一時的に使用できない。  
  
-   要求されたファイルが存在しない。  
  
-   IIS 6.0: 適切な Web サービスの拡張機能または MIME の種類が有効になっていない。  
  
-   仮想ディレクトリは、別のサーバー上のドライブのルートにマップされます。  
  
##### <a name="resolution"></a>解決策  
 マイクロソフト サポート技術情報資料 248033、"一般的な理由の IIS サーバーには、「HTTP 404 - ファイルが見つかりません」エラーが返されます。"解決方法」の手順で使用可能な[ http://support.microsoft.com/kb/248033](http://support.microsoft.com/kb/248033)します。  
  
#### <a name="cannot-find-server-or-dns-error-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>IIS サーバー上の Web ページへのアクセス時に "ページを表示できません。サーバーが見つからないか、DNS エラーです。" エラーが発生する  
  
##### <a name="problem"></a>問題  
 IIS サーバー上の Web ページにアクセスしようとすると、次のようなエラーが表示されます。  
  
 "ページを表示できません。"  
  
 \- または -  
  
 "Cannot find server or DNS Error"  
  
##### <a name="cause"></a>原因  
 このエラーは次のような理由で発生することがあります。  
  
-   Internet Explorer の接続設定が正しくない。  
  
-   構成が正しくないか、構成されていないか、互換性のないファイアウォールまたはプロキシ ソフトウェアがインストールされている。  
  
-   ホスト ファイルに正しくないエントリがある。  
  
-   ネットワーク アダプターが正しく機能していないか、互換性のないネットワーク アダプター ドライバーがインストールされている。  
  
##### <a name="resolution"></a>解決策  
 マイクロソフト サポート技術情報の資料 326155 の解決方法」の手順に従って"Internet Explorer で Web サイトにアクセスしようとすると、エラー メッセージ:「ページを表示できません」"でご利用いただけます[ http://support.microsoft.com/kb/326155](http://support.microsoft.com/kb/326155)します。  
  
#### <a name="401---access-denied-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>IIS サーバー上の Web ページへのアクセス時に "401 - アクセスが拒否されました" エラーが発生する  
  
##### <a name="problem"></a>問題  
 IIS サーバー上の Web ページにアクセスしようとすると、次のようなエラーが表示されます。  
  
 “401 - アクセスが拒否されました”  
  
##### <a name="cause"></a>原因  
 IIS では、エラーの原因をより具体的に示すいくつかの 401 エラーを定義しています。 これらの限定的なエラー コードは、ブラウザーに表示されます。  
  
- “401.1 - 資格情報が無効のため、アクセスが拒否されました。”  
  
- “401.2 – サーバーの構成によりアクセスが拒否されました。”  
  
- “401.3 – 要求したリソースに設定された ACL によりアクセスが拒否されました。”  
  
- “401.4 – Web サーバーにインストールされたフィルターによって、認証が失敗しました。”  
  
- “401.5 – ISAPI または CGI アプリケーションによって、認証が失敗しました。”  
  
- “401.7 – Web サーバーの URL 承認ポリシーにより、アクセスが拒否されました。” これは、IIS 6.0 固有のエラー コードです。  
  
  IIS 7.0 の状態コードの一覧は、マイクロソフト サポート技術情報の資料 943891「、「IIS 7.0 の HTTP 状態コード」を参照してください。 いただけます[ http://support.microsoft.com/kb/943891](http://support.microsoft.com/kb/943891)します。  
  
##### <a name="resolution"></a>解決策  
 次の手順では、 [IIS アクセス許可の問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)IIS のアクセス許可の問題を解決します。  
  
#### <a name="500---internal-server-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>IIS サーバー上の Web ページにアクセスすると "500 - 内部サーバー エラー" が発生する  
  
##### <a name="problem"></a>問題  
 IIS サーバー上の Web ページにアクセスしようとすると、次のようなエラーが表示されます。  
  
 “500 - 内部サーバー エラー”  
  
##### <a name="cause"></a>原因  
 このエラー メッセージは、サーバー側のさまざまな問題が原因で発生する可能性があります。  
  
##### <a name="resolution"></a>解決策  
 この問題を解決するには、以下の手順を実行します。  
  
- IIS サーバーのアプリケーション ログで、このエラーが発生する理由に関する情報がないか調べます。  
  
- IIS ログ ファイルまたは HTTPERR ログ ファイルで、エラー原因の特定に役立つ可能性のある情報を確認します。 既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] オペレーティング システムが稼働しているコンピューターの IIS ログ ファイルは、次のディレクトリにあります。  
  
   <em>%Windir%\\</em>system32\LogFiles\W3SVC1\  
  
  > [!NOTE]
  >  *%Windir%* IIS サーバー上の Windows ディレクトリの場所のプレース ホルダーです。  
  
   既定では、Windows Server 2008 コンピューターまたは Windows Vista コンピューターの IIS ログ ファイルは、次のディレクトリにあります。  
  
   C:\inetpub\logs\LogFiles\W3SVC1\  
  
   既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] の HTTPERR ログ ファイルは、次のディレクトリにあります。  
  
   <em>%Windir%</em>system32LogFilesHTTPERR  
  
  > [!NOTE]
  >  HTTPERR ログ ファイルを使用できるのは、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] または Windows Vista のコンピューターだけです。  
  
#### <a name="service-unavailable-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>IIS サーバー上の Web ページにアクセスすると "サービスは利用できません" エラーが発生する  
  
##### <a name="problem"></a>問題  
 IIS サーバー上の Web ページにアクセスしようとすると、次のようなエラーが表示されます。  
  
 “サービスは利用できません”  
  
##### <a name="cause"></a>原因  
 このエラーの最も一般的な原因は、Web ページのアプリケーション プール (IIS 6.0 および IIS 7.0) が停止していることです。 一般には、アプリケーション プールまたは COM+ アプリケーションを構成している ID に無効なユーザー名またはパスワードが指定されている場合にこのエラーが発生します。  
  
##### <a name="resolution"></a>解決策  
 トピックの「IIS アプリケーション ホスト プロセス Id の設定」セクションの手順に従って[IIS アクセス許可問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)適切なホスト プロセス id を設定します。  
  
## <a name="see-also"></a>参照  
 [IIS のアクセス許可の問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)