---
title: BizTalk RosettaNet アクセラレータ (BTARN) での既知の問題は、BizTalk Server にインストールのトラブルシューティングと |Microsoft Docs"
description: BizTalk Server で BTARN のインストールで SQL では、ホスト インスタンス、および既知のエラーのサービス アカウントをインストールするための推奨事項
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 493a46d63fa85f181b2e019c307b7b5be66c9d72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280442"
---
# <a name="troubleshoot-the-installation-and-see-the-known-install-issues"></a>インストールのトラブルシューティングし、インストールの既知の問題を参照してください。


## <a name="do-not-install-sql-server-on-the-domain-controller-computer"></a>ドメイン コント ローラー コンピューター上の SQL サーバーをインストールしません。  
 ドメイン コント ローラー コンピューターと同じコンピューターに SQL Server をインストールする場合は、SQL 送信ポートを作成する際、次のエラー メッセージを返します。  

```
Error: Failed updating binding information.  
BindingException: Could not validate TransportTypeData or Address properties for Primary Transport of Send Port 'SendPort1'. Exception from HRESULT: 0x80131500.  
Error: Failed updating binding information.  
BindingException: Could not validate TransportTypeData or Address properties for Primary Transport of Send Port 'SendPort1'. Exception from HRESULT: 0x80131500  
```

> [!IMPORTANT]
>  ドメイン コント ローラーのコンピューターで SQL Server をインストールできません。  

## <a name="service-account-for-the-application-pools-must-be-the-same-as-the-service-account-for-the-isolated-host-and-host-instances"></a>アプリケーション プールのサービス アカウントには、分離ホストとホスト インスタンスのサービス アカウントと同じである必要があります。  
 設定の BTARN アプリケーション プール サービス アカウントが別の分離ホスト アカウントの場合は、BTARN は受信メッセージが正しく処理されません。 受信 .aspx ページが、パイプラインを呼び出すと、パイプラインには適切な証明書へのアクセスはありません。 そのため、受信メッセージの暗号化を解除したりしない署名を検証します。 また、メッセージ ボックス データベースにアクセスすることができません。  


## <a name="known-install-issues"></a>インストールの既知の問題


### <a name="btarn-http-front-end-feature-configuration-fails"></a>BTARN HTTP フロント エンド機能の構成が失敗します。  
 **問題**  

 BTARN HTTP フロント エンド機能のみをインストールするカスタム インストールを実行する場合、次のエラーでセットアップが完了した後に、BTARN の構成が失敗します。 

`Failed to create object for feature: WebApp`  

 **解決方法**  

手動でファイルをコピーして再構成します。 

1. BizTalk Server コンピューターから BTARN HTTP フロント エンド機能がインストールされているコンピューターに次の 2 つのファイルをコピーします。

   - Microsoft.VC80.ATL.manifest  

   - atl80.dll  

     2 つのファイルのソース フォルダーは、Visual Studio は、BizTalk Server と同じコンピューターにインストールされて場合、<*ドライブ*>: \Program Files\Microsoft Visual Studio < バージョン\>\VC\redist\x86\Microsoft.VC100.ATL.  

     同じ BizTalk Server コンピューターに Visual Studio がインストールされていない場合、2 つのファイルのソース フォルダーは <*ドライブ*>: \WINDOWS\WinSxS します。  

2. BTARN HTTP フロント エンド機能がインストールされているコンピューターにコピーしたファイルを追加します。 既定では、ファイルのコピー <*ドライブ*>: \Program Files\Microsoft BizTalk Accelerator for RosettaNet。  

3. HTTP フロント エンド コンピューターにファイルをコピーした後、実行**Configuration.exe**もう一度です。  

### <a name="some-btarn-assemblies-stay-in-gac-after-uninstalling"></a>一部の BTARN アセンブリが GAC にアンインストールした後に維持します。  
 **問題**  

 BTARN をアンインストールすると、一部のアセンブリはグローバル アセンブリ キャッシュ (GAC) に残ります。  

 **解決方法**  

 BTARN を再インストールする前に、GAC からアセンブリを削除します。  

 使用して、 **BtarnClean**ユーティリティ、SDK アセンブリを削除するからです。 ユーティリティは、次の操作を実行します。  

- 停止し、すべての BTARN オーケストレーションの参加を解除します。  

- 停止し、関連するすべてのポートを削除します。  

- すべての Microsoft.Solutions.BTARN.* アセンブリの展開を解除します。  

  ユーティリティを実行した後、GAC にアセンブリが残ってがある場合は、Windows エクスプ ローラーを開き、"C:\Windows\Assembly"フォルダーに移動および Microsoft.Solutions.BTARN で始まるすべてのアセンブリを手動で削除します。  

### <a name="service-unavailable-error-on-64-bit-os"></a>64 ビット OS 上のサービス利用不可エラー
 **問題**  

 取得することがあります、 `Service Unavailable` BTARN HTTP にアクセスしようとするときにエラーが 64 ビット Windows オペレーティング システム上の場所を受信します。  

 **原因**  

 この問題は"RPCProxy.dll"ISAPI によって発生することができますフィルター。  

 **解決方法**  

RPC プロキシ ISAPI フィルターへの参照を削除し、IIS を再起動します。

1.  インターネット インフォメーション サービス (IIS) マネージャーで、右クリックして**Websites**、順にクリックします**プロパティ**します。  

2.  **Web サイトのプロパティ**ダイアログ ボックスで、 をクリックして、 **ISAPI フィルター**  タブで、削除**RPC プロキシ**フィルター処理、およびクリックして**ok**します。  

3.  IIS を再起動します。  

4.  IIS を再起動した後にアクセスすることをお試しください http://localhost します。 インターネット ブラウザーから 400 メッセージが返されます。  

### <a name="sql-server-mixed-mode-not-supported"></a>SQL Server 混在モードはサポートされていません  
BTARN は、混在モードで SQL Server をサポートしていません。  

### <a name="run-setupx64bat-to-set-up-the-double-action-pipautomation-orchestration-sample"></a>ダブル アクション PIPAutomation オーケストレーション サンプルを設定する setupx64.bat を実行します。 

\Program Files\Microsoft BizTalk Accelerator for rosettanet \sdk\pipautomation\doubleaction フォルダー Double Action PIPAutomation Orchestration サンプルを設定するには、setupx64.bat を実行します。

### <a name="download-the-btarn-setup-file-from-the-web-to-a-temp-folder"></a>BTARN セットアップ ファイルを Web から一時フォルダーにダウンロードします。  
 **問題**  

 BTARN の自己解凍形式実行可能ファイル、Web からダウンロードして実行可能ファイルの BizTalk 実行しようとしたときに、BizTalk Server のルート フォルダーに保存すると**セットアップ ウィザード**BTARN セットアップ ウィザードではなく、実行します。  

 **解決方法**  

 BTARN の自己解凍形式の実行可能ファイルをダウンロードし、一時フォルダーにファイルを保存します。
