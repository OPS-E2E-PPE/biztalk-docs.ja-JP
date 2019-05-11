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
# <a name="troubleshooting-internet-information-services"></a>インターネット インフォメーション サービスのトラブルシューティング
Microsoft インターネット インフォメーション サービス (IIS) は Microsoft によって広く使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HTTP、SOAP、および Windows SharePoint Services アダプターのなどさまざまな機能です。 このトピックでは、IIS とこれらの問題の解決方法で発生する既知の問題について説明します。  
  
## <a name="known-issues"></a>既知の問題  
 HTTP エラー メッセージの簡易表示を無効にする Internet Explorer を構成しない限り、このトピックに記載されているエラーは表示されません。  
  
#### <a name="to-configure-internet-explorer-to-disable-friendly-http-error-messages"></a>HTTP エラー メッセージの簡易表示を無効にする Internet Explorer を構成するには  
  
1.  **ツール** メニューのをクリックして**インターネット オプション**します。  
  
2.  **詳細設定**  タブで、**ブラウズ** セクションで、クリア、**フレンドリ HTTP エラー メッセージを表示する**チェック ボックスをオンにし**ok**。  
  
3.  Internet Explorer を閉じます。  
  
#### <a name="http-404---file-not-found-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>"HTTP 404 - ファイルが見つかりませんでした"エラーは、IIS サーバー上の Web ページにアクセスするときに発生します。  
  
##### <a name="problem"></a>問題  
 IIS サーバー上の Web ページにアクセスしようとしたときに、次のようなエラーが表示されます。  
  
 ページが見つかりません  
  
 \- - または -  
  
 HTTP 404 - ファイルが見つかりません。  
  
##### <a name="cause"></a>原因  
 このエラーは、次の理由で発生する可能性があります。  
  
-   要求されたファイルの名前が変更されています。  
  
-   要求されたファイルが別の場所に移動または削除されています。  
  
-   要求されたファイルは、メンテナンス、アップグレード、またはその他の不明なエラーの原因のため一時的にご利用いただけません。  
  
-   要求されたファイルが存在しません。  
  
-   IIS 6.0:適切な Web サービス拡張機能または MIME の種類が無効です。  
  
-   仮想ディレクトリは、別のサーバー上のドライブのルートにマップされます。  
  
##### <a name="resolution"></a>解決策  
 マイクロソフト サポート技術情報資料 248033、"一般的な理由の IIS サーバーには、「HTTP 404 - ファイルが見つかりません」エラーが返されます。"解決方法」の手順で使用可能な[ http://support.microsoft.com/kb/248033](http://support.microsoft.com/kb/248033)します。  
  
#### <a name="cannot-find-server-or-dns-error-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>IIS サーバー上の Web ページにアクセスするときに発生する"cannot find server or DNS エラー"  
  
##### <a name="problem"></a>問題  
 IIS サーバー上の Web ページにアクセスしようとしたときに、次のようなエラーが表示されます。  
  
 ページを表示することはできません。  
  
 \- - または -  
  
 サーバーまたは DNS エラーを見つけることができません。  
  
##### <a name="cause"></a>原因  
 このエラーは、次の理由で発生する可能性があります。  
  
-   Internet Explorer の接続設定が正しくありません。  
  
-   正しく構成されている、機能していないまたは互換性のないファイアウォールまたはプロキシ ソフトウェアがインストールされていません。  
  
-   ホスト ファイルに正しくないエントリがあります。  
  
-   ネットワーク アダプターが正しく機能していないまたは互換性のないネットワーク アダプター ドライバーがインストールされています。  
  
##### <a name="resolution"></a>解決策  
 マイクロソフト サポート技術情報の資料 326155 の解決方法」の手順に従って"Internet Explorer で Web サイトにアクセスしようとすると、エラー メッセージ。「ページを表示できません」"でご利用いただけます[ http://support.microsoft.com/kb/326155](http://support.microsoft.com/kb/326155)します。  
  
#### <a name="401---access-denied-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>「401-アクセスが拒否されました」エラーは、IIS サーバー上の Web ページにアクセスするときに発生します。  
  
##### <a name="problem"></a>問題  
 IIS サーバー上の Web ページにアクセスしようとしたときに、次のようなエラーが表示されます。  
  
 401-アクセスが拒否されました  
  
##### <a name="cause"></a>原因  
 IIS では、エラーの原因をより具体的に示すいくつかのさまざまな 401 エラーを定義します。 これらの特定のエラー コードは、ブラウザーで表示されます。  
  
- 401.1 - ログオンに失敗しました。  
  
- 401.2 - サーバーの構成により、ログオンに失敗しました。  
  
- 401.3 - ACL をリソースにします。  
  
- 401.4 - 承認フィルターによって失敗しました。  
  
- 401.5 - 承認 ISAPI または CGI アプリケーションが失敗しました。  
  
- 401.7 – Web サーバーの URL 承認ポリシーによって拒否されたアクセス。 このエラー コードは、IIS 6.0 に固有です。  
  
  IIS 7.0 の状態コードの一覧は、マイクロソフト サポート技術情報の資料 943891「、「IIS 7.0 の HTTP 状態コード」を参照してください。 いただけます[ http://support.microsoft.com/kb/943891](http://support.microsoft.com/kb/943891)します。  
  
##### <a name="resolution"></a>解決策  
 次の手順では、 [IIS アクセス許可の問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)IIS のアクセス許可の問題を解決します。  
  
#### <a name="500---internal-server-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>「500-内部サーバー エラー」は、IIS サーバー上の Web ページにアクセスするときに発生します。  
  
##### <a name="problem"></a>問題  
 IIS サーバー上の Web ページにアクセスしようとしたときに、次のようなエラーが表示されます。  
  
 500-内部サーバー エラー  
  
##### <a name="cause"></a>原因  
 このエラー メッセージは、さまざまなサーバー側の問題によることができます。  
  
##### <a name="resolution"></a>解決策  
 問題を解決するには、次の操作を行います。  
  
- このエラーが発生した理由については、IIS サーバーのアプリケーション ログを確認します。  
  
- IIS ログ ファイルまたは HTTPERR ログ ファイルでエラーの原因を特定するのに役立つ可能性がある情報を確認します。 既定では、IIS が実行しているコンピューター上のファイルをログ[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]オペレーティング システムは、次のディレクトリに配置されます。  
  
   <em>%WinDir%\\</em>system32\LogFiles\W3SVC1\  
  
  > [!NOTE]
  >  *%Windir%* IIS サーバー上の Windows ディレクトリの場所のプレース ホルダーです。  
  
   既定では、IIS は、Windows Server 2008 または Windows Vista を実行するコンピューターでログ ファイルは、次のディレクトリに配置されます。  
  
   C:\inetpub\logs\LogFiles\W3SVC1\  
  
   既定では、HTTPERR ログ ファイル[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]次のディレクトリにあります。  
  
   <em>%WinDir%</em>system32LogFilesHTTPERR  
  
  > [!NOTE]
  >  HTTPERR ログ ファイルで使用できるのみ、 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、または Windows Vista のコンピューター。  
  
#### <a name="service-unavailable-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>「サービスは利用できません」エラーは、IIS サーバー上の Web ページにアクセスするときに発生します。  
  
##### <a name="problem"></a>問題  
 IIS サーバー上の Web ページにアクセスしようとしたときに、次のようなエラーが表示されます。  
  
 サービス利用不可  
  
##### <a name="cause"></a>原因  
 このエラーの最も一般的な原因は、Web ページのアプリケーション プール (IIS 6.0 および IIS 7.0) が停止していることです。 これは、問題は発生アプリケーション プールまたは COM + アプリケーションが構成されている場合、Id を指定されたユーザー名またはパスワードが無効です。  
  
##### <a name="resolution"></a>解決策  
 トピックの「IIS アプリケーション ホスト プロセス Id の設定」セクションの手順に従って[IIS アクセス許可問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)適切なホスト プロセス id を設定します。  
  
## <a name="see-also"></a>参照  
 [IIS のアクセス許可の問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)