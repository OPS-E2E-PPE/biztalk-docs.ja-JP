---
title: "BizTalk ESB Toolkit のトラブルシューティング |Microsoft ドキュメント"
description: "インストールの問題、および BizTalk Server で ESB Toolkit に関する一般的なエラーをトラブルシューティングします。"
caps.latest.revision: "2"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1ea2d56-2ace-40f2-80df-8a7489bbfc2e
ms.author: mandia
ms.openlocfilehash: 8fc1305e481de2444a54ea994f8a53da83b2eaed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-the-biztalk-esb-toolkit"></a>BizTalk ESB Toolkit をトラブルシューティングします。

  
## <a name="installation"></a>インストール  
  
|問題点|解決策|  
|-----------|----------------|  
|インストール中に「アクセス許可の割り当てエラー」例外が表示されます。|[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用して、インストール プロセスまたはインストール中に存在する必要があります標準 BizTalk アカウント グループは失敗します。 さらに、ツールキットには、コンピューターがワークグループのメンバーをスタンドアロン インストールか、コンピューターがドメインのメンバーをエンタープライズ インストールが想定しています。|  
|アプリケーションのインポートは、信頼レベルの不一致の警告がエラー メッセージで失敗します。|Microsoft.BizTalk.ESB バインド ファイルは、BizTalkServerApplication と BizTalkServerIsolatedHost、信頼されていないモードで実行するように構成がさらに、既定値を使用する構成されます。 信頼モードで実行するホストを変更した場合、バインド ファイルはインポートされません。 これを修正するには、信頼されていないを信頼レベルを変更するか、BizTalk Toolkit \Bindings ディレクトリに環境に合わせて、バインド ファイルを編集する必要があります。|  
|Kerberos 認証には、インターネット インフォメーション サービス (IIS) が構成されていません。|IIS での Kerberos 認証を有効にするには、Microsoft サポート技術情報の次の記事を参照してください。<br /><br /> -   [ネットワークの認証に Kerberos プロトコルと NTLM プロトコルの両方をサポートするために IIS を構成する方法](http://go.microsoft.com/fwlink/?LinkId=188566)<br />-   [ドメイン コント ローラーではないコンピューターで Kerberos 認証を使用するように IIS を有効にする方法](http://go.microsoft.com/fwlink/?LinkId=188567)<br />-   [ことはできませんプロトコルの構成、ネゴシエート] または [NTLM Windows 統合認証を IIS マネージャーでのインターネット インフォメーション サービス (IIS) 7.0](http://go.microsoft.com/fwlink/?LinkId=188568)|  
  
## <a name="general-issues"></a>一般的な問題  
  
|問題点|解決策|  
|-----------|----------------|  
|汎用の ESB 行程ランプで Web サービスにメッセージを送信するときに、「内部 SOAP 処理」例外が表示されます。|BizTalk Server 管理コンソールを使用して、Microsoft.Practices.ESB アプリケーションが実行されていることを確認するには実行されていない場合は、それを開始します。|  
|ESB 管理ポータル サイトには、例外メッセージは表示されません。|BizTalk 管理者グループの概要 ページと、Windows アプリケーション イベント ログ メッセージを送信するエラーを示すエントリを確認します。 環境に合わせて例外 Send Adapter (Microsoft.Practices.ESB アプリケーションの一部) を再構成する必要があります。 さらに、BizTalk 失敗のメッセージのルーティング機能と、BizTalk ESB Toolkit 例外管理フレームワークの両方が例外メッセージを生成することに注意してください。 そのため、有効にすることを確認してください、**できませんでしたメッセージ上のルート**オプションを送信および受信ポート。|  
|静的な競合回避モジュールで WCF サービスを使用するときに、無効な SOAP アクションの例外が表示されます。|WCF サービスの SOAP アクションにターゲットの名前空間が含まれていない場合は、設定の競合回避モジュールで次の形式で SOAP アクションの値を設定します。 ターゲットの名前空間がない、ESB Toolkit コア エンジンによって実行時に連結するを指定するには、{アクション}。|