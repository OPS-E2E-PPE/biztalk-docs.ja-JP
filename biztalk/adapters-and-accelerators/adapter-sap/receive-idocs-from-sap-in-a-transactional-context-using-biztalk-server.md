---
title: BizTalk Server を使用して、トランザクションのコンテキストでの SAP からの Idoc を受信 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transactional context
- IDOCs, receiving in a transactional context using BizTalk Server
ms.assetid: 6a01bb82-7292-4b70-8ad7-996d389a9365
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8903b6010555b3c7c6aba9a07e12c9204bcf19c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962744"
---
# <a name="receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server"></a>BizTalk Server を使用して、トランザクションのコンテキストでの SAP からの Idoc を受信します。
IDOC を受信して、トランザクションのコンテキストでは、トランザクションのコンテキストで tRFCs の受信に似ています。 このような場合は、SAP システムから受信した IDOC が含まれています、TID には一部として、  *\<TransactionalRfcOperationIdentifier\>* 要素。 この TID はアダプターによって、SQL データベースに永続化されます。 IDOC を送信する SAP システム内の ABAP コードに"COMMIT WORK"ステートメントがある場合、TID は、SAP システムへの応答が送信された後、SQL データベースから削除されます。  
  
 IDOC を受信するために必要なオーケストレーションは、IDOC をトランザクションのコンテキストで受信したかいないかどうかに関係なくと似ています。 参照してください[Idoc を SAP から BizTalk Server を使用して、受信](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)です。 ただし、トランザクションのコンテキストで、Idoc を受け取るかどうかを確認する特定のタスクを実行する必要があります。  
  
1.  デザイン時に、IDOC を受信するため、スキーマを生成します。  
  
2.  実行時に、必ずバインディング プロパティを設定してください**TidDatabaseConnectionString**です。 このプロパティは、TID を格納する SQL データベースに接続する接続文字列を取得します。 サンプルの接続文字列は、ようになります。  
  
    ```  
    Data Source=<myServerAddress>;Initial Catalog=<myDataBase>;User Id=<myUsername>;Password=<myPassword>;  
    ```  
  
     バインディング プロパティとその設定方法の詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
    > [!IMPORTANT]
    >  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ ウィザードをインストールする SQL スクリプト、SapAdapter-DbScript-Install.sql、SQL Server でデータベースおよびデータベース オブジェクトを作成する SQL Server の管理者によって実行する必要があります。 インストールされている通常の*\<インストール ドライブ\>*: プログラム FilesMicrosoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。  
    >   
    >  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Tid を永続化するこれらのオブジェクトを使用します。 そのため、SQL Server の管理者ことを確認、ユーザー名、接続文字列の一部がストアド プロシージャを実行するための十分な特権を持つように指定します。 Windows ユーザーがデータベースにストアド プロシージャを実行するための十分なアクセス許可を持っていれば、Windows 認証のこともできます。  
  
3.  アダプターがインストールされているコンピューターで MSDTC を有効にすることを確認します。 MSDTC を有効にするのには、次の手順を実行します。  
  
    1.  コンポーネント サービス MMC スナップインを起動します。  
  
    2.  コンポーネント サービス MMC スナップインで、左側のウィンドウから、展開**コンポーネント サービス**、展開**コンピューター**を右クリックして**マイ コンピューター**、 をクリック**プロパティ**です。  
  
    3.  **マイ コンピューター プロパティ**ダイアログ ボックスで、をクリックして、 **MSDTC**タブです。  
  
    4.  **トランザクション構成**セクションで、をクリックして、**セキュリティ構成**ボタンをクリックします。  
  
    5.  **セキュリティ構成**ダイアログ ボックスで、**ネットワーク DTC アクセス**チェック ボックスをオンし、をクリックして、**リモート クライアントを許可する**チェック ボックスをオンします。  
  
    6.  **トランザクション マネージャー通信** セクションで、select、**受信を許可する**と**送信を許可する**チェック ボックスです。  
  
    7.  **セキュリティの構成**ダイアログ ボックスで、をクリックして**OK**です。  
  
    8.  をクリックして**はい**ダイアログ ボックスに通知、MSDTC サービスが再開されることにします。 MSDTC サービスを再起動すると、をクリックして**OK**  ダイアログ ボックス。  
  
    9. **マイ コンピューター プロパティ**ダイアログ ボックスで、をクリックして**OK**です。  
  
4.  既に追加されていない場合、Windows ファイアウォールの例外一覧に MSDTC を追加します。 次のコマンドを実行します。  
  
    ```  
    netsh firewall set allowedprogram %windir%\system32\msdtc.exe MSDTC enable  
    ```  
  
## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)