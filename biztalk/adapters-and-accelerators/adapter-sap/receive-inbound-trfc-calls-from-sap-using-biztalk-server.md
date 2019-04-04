---
title: BizTalk Server を使用して SAP から受信 tRFC 呼び出しを受信する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tRFC calls, receiving using BizTalk Server
- tRFCs, sample
ms.assetid: 500eedea-3d27-478c-a64c-903a1fa2b02f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49d83d8710b36d0900c2d7b3a6b02c7d0a389ba4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978619"
---
# <a name="receive-inbound-trfc-calls-from-sap-using-biztalk-server"></a>BizTalk Server を使用して SAP から受信 tRFC 呼び出しを受信します。
TRFC サーバーの呼び出しは、トランザクションの RFC サーバー呼び出しです。 トランザクションのコンテキストでの RFC の受信に必要なオーケストレーションは、SAP システムから送信されたすべての他の受信 RFC を受信するオーケストレーションに似ています。 ただし、Rfc がトランザクションのコンテキストで受信したかどうかを確認する特定の追加タスクを実行する必要があります。 受信 RFC を使用して SAP システムから受信の詳細については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[BizTalk Server を使用して SAP からの受信 RFC 呼び出しの受信](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)します。 方法の詳細については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、SAP システムからの受信 tRFC 呼び出しの受信をサポートを参照してください[SAP の Trfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)します。  
  
 SAP システムから送信される、受信 tRFC の受信は、受信 RFC、相違点を次の受信と同様です。  
  
1. スキーマの生成中に、デザイン時の下にある tRFC を選択するを確認、 **TRFC**ノード。  
  
2. 実行時に、バインド プロパティの設定を確認します**TidDatabaseConnectionString**します。 このプロパティは、TID を格納する SQL database に接続する接続文字列を取得します。 接続文字列の例は、ようになります。  
  
   ```  
   Data Source=<myServerAddress>;Initial Catalog=<myDataBase>;User Id=<myUsername>;Password=<myPassword>;  
   ```  
  
    バインディングのプロパティとその設定方法の詳細については、[mySAP Business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)を参照してください。  
  
   > [!IMPORTANT]
   >  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]しばらくお待ちくださいこの処理には、数分かかることがあります SQL スクリプト、SapAdapter-DbScript-Install.sql、SQL server データベースおよびデータベース オブジェクトを作成する SQL Server の管理者によって実行する必要があります。 スクリプトは通常にインストールされて*\<インストール ドライブ\>: Program FilesMicrosoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]* します。  
   > 
   >  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Tid を永続化するこれらのオブジェクトを使用します。 そのため、SQL Server 管理者ようにするユーザー名と接続文字列の一部があるストアド プロシージャを実行するための十分な特権を提供します。 Windows ユーザーがデータベースにストアド プロシージャを実行するための十分なアクセス許可を持っていれば、Windows 認証のこともできます。  
  
3. アダプターがインストールされているコンピューターで MSDTC を有効にすることを確認します。 MSDTC を有効にするのには、次の手順を実行します。  
  
   1.  コンポーネント サービス MMC スナップインを起動します。  
  
   2.  コンポーネント サービス MMC スナップインで、左側のウィンドウから展開**コンポーネント サービス**、展開**コンピューター**、右クリックして**マイ コンピューター**、 をクリック**プロパティ**します。  
  
   3.  **マイ コンピューター プロパティ**ダイアログ ボックスで、をクリックして、 **MSDTC**タブ。  
  
   4.  **トランザクション構成**セクションで、、**セキュリティ構成**ボタンをクリックします。  
  
   5.  **セキュリティ構成**ダイアログ ボックスで、**ネットワーク DTC アクセス**チェック ボックスをオンし、次のように選択します。、**リモート クライアントを許可する**チェック ボックスをオンします。  
  
   6.  **トランザクション マネージャー通信**セクションで、**受信を許可する**と**送信を許可する**チェック ボックス。  
  
   7.  **セキュリティの構成**ダイアログ ボックスで、をクリックして**OK**。  
  
   8.  をクリックして**はい** ダイアログ ボックス通知、MSDTC サービスが再開されることにします。 MSDTC サービスが再起動されると、クリックして**OK**  ダイアログ ボックス。  
  
   9. **マイ コンピューター プロパティ**ダイアログ ボックスで、をクリックして**OK**。  
  
4. 既に追加されていない場合、MSDTC を Windows ファイアウォール例外一覧に追加します。 次のコマンドを実行します。  
  
   ```  
   netsh firewall set allowedprogram %windir%\system32\msdtc.exe MSDTC enable  
   ```  
  
> [!IMPORTANT]
>  受信 tRFC 呼び出しは、「トランザクション」のコンテキストでの SAP システムから Idoc を受信中に使用されます。  
  
## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)