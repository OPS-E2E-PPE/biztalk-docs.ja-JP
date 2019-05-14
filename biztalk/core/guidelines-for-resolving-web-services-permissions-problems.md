---
title: Web サービスのアクセス許可の問題を解決するためのガイドライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e29543e9-9b87-437b-ac91-8f1cce01fab4
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c56d784362861ad90788e8a3e8dde666dd863efb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344806"
---
# <a name="guidelines-for-resolving-web-services-permissions-problems"></a>Web サービスの権限の問題を解決するためのガイドライン
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には Web サービスが広く採用され、SOAP アダプターで使用したり、オーケストレーションを Web サービスとして公開したりできるようになっています。 このトピックでは、Web サービスのアクセス許可の問題を最小限に抑えるための一般的なガイドラインを提供し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に影響を与える Web サービスのアクセス許可の問題をトラブルシューティングするための手順について説明します。  
  
## <a name="general-guidelines"></a>一般的なガイドライン  
  
- **ユーザー アカウントの設定**:仮想ディレクトリに関連付けられた IIS アプリケーション ホスト プロセス id をホストする Web サービスが特定のユーザー アカウントに設定を使用することを確認し、このユーザー アカウントが次のグループに追加されるように。  
  
  - BizTalk 分離ホスト ユーザー (ドメインまたはローカル グループ)  
  
  - IIS_WPG (ローカル グループ)  
  
    BizTalk Web サービス公開ウィザードで作成された Web サービスに、BizTalk メッセージ ボックス データベースに SOAP 要求メッセージを公開する (これにより、サブスクライブを行うオーケストレーションをアクティブ化する) ための適切な権限を与えるには、これら 2 つのグループのメンバーシップが必要です。 決定または IIS アプリケーション ホスト プロセス id の設定の詳細については、次を参照してください、 **IIS アプリケーション ホスト プロセス Id の設定**の[にIISのアクセス許可問題を解決するためのガイドライン。](../core/guidelines-for-resolving-iis-permissions-problems.md).  
  
- **TEMP 環境変数によって指定されたフォルダーのアクセス許可設定**:Web サービスをホストする仮想ディレクトリの IIS アプリケーション ホスト プロセス id の読み取りがあることを確認し、TEMP 環境変数によって指定されたフォルダーに対する書き込みアクセス許可。 TEMP 環境変数によって指定されているフォルダーを確認するには、BizTalk Server でコマンド プロンプトを開き、次のコマンドを入力して、Enter キーを押します。  
  
  ```  
  echo %TEMP%  
  ```  
  
   TEMP 環境変数によって指定されたフォルダーは、Web サービスがダイナミック リンク ライブラリ (dll) ファイル形式に Just In Time (JIT) コンパイルされる場所であるため、このユーザー アカウントが読み取り/書き込みアクセス許可を使用してアクセスできる必要があります。  
  
- **SOAP メソッドの呼び出しで資格情報を送信する**:Web サービス クライアントが SOAP メソッドの呼び出しで資格情報を送信していることを確認します。 既定では、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] の IIS 7.0 では Windows 認証が必要です。 Internet Explorer を使用して Web サービスをテストするときは、現在ログオンしているユーザーの資格情報が自動的に送信されます。このため、Web サービスは、Internet Explorer からは機能していても、別のクライアントからは機能していない可能性があります。 Web サービス クライアントが SOAP メソッドの呼び出しに資格情報を追加しない場合、認証の失敗によって SOAP 例外が発生します。 SOAP メソッドの資格情報の送信の詳細については、呼び出しで使用可能なサンプル コードを参照してください。[新しい System.Net クラスを使用して HTTP クライアントを作成する方法](http://support.microsoft.com/kb/303436)します。  
  
- **Web サービスの呼び出しエラーのトラブルシューティング**:Web サービスを呼び出すときにエラーが発生した場合、アプリケーション ログを確認するかメッセージを BizTalk Server 管理イベントとサービス インスタンスの追跡**グループ ハブ**ページ。 エラーの考えられる原因の詳細については、次を参照してください。 [BizTalk Server の監視](../core/monitoring-biztalk-server.md)と[グループ ハブ ページを使用して](../core/using-the-group-hub-page.md)します。  
  
- **デバッグ情報の収集**:詳細なデバッグ情報を取得するトピックに記載されている手順に従います[公開 Web サービスのデバッグ](../core/debugging-published-web-services.md)上記の手順に従っても問題が解決しない場合。  
  
## <a name="known-issues"></a>既知の問題  
 に関する既知の問題に関する追加情報について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web サービスのアクセス許可に関連してを参照してください「BizTalk Server を実行しているサーバー上の Web サービスとして公開されているオーケストレーションを呼び出すことはできません」 [ http://go.microsoft.com/fwlink/?LinkId=196379 ](http://go.microsoft.com/fwlink/?LinkId=196379).  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のアクセス許可のトラブルシューティング](../core/troubleshooting-biztalk-server-permissions.md)   
 [IIS のアクセス許可の問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)