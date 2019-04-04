---
title: BizTalk Server を使用してトランザクション コンテキストでの SAP の Idoc を受信する |Microsoft Docs
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
ms.openlocfilehash: c58bccbb48603af8bf5a5cc0d12b4c2200e78704
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013365"
---
# <a name="receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server"></a>BizTalk Server を使用してトランザクション コンテキストでの SAP の Idoc を受信します。
トランザクションのコンテキストで IDOC を受信は、トランザクションのコンテキストで Trfc の受信に似ています。 このような場合は、SAP システムから受信した IDOC がの一部として、TID を含む、 *\<TransactionalRfcOperationIdentifier\>* 要素。 この TID は、アダプターによって、SQL database に保存されます。 IDOC を送信する SAP システムで、ABAP コードに"COMMIT WORK"ステートメントがある場合は、SAP システムへの応答が送信された後に、TID が SQL データベースから削除されます。  
  
 IDOC を受信するために必要なオーケストレーションは、IDOC はトランザクションのコンテキストで受信したかどうかに関係なくと似ています。 参照してください[Idoc を SAP から BizTalk Server を使用して受信](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)します。 ただし、特定、Idoc がトランザクションのコンテキストで受信したかどうかを確認する追加のタスクを実行する必要があります。  
  
1. デザイン時に、IDOC を受信するため、スキーマを生成します。  
  
2. 実行時に、バインド プロパティの設定を確認します**TidDatabaseConnectionString**します。 このプロパティは、TID を格納する SQL database に接続する接続文字列を取得します。 接続文字列の例は、ようになります。  
  
   ```  
   Data Source=<myServerAddress>;Initial Catalog=<myDataBase>;User Id=<myUsername>;Password=<myPassword>;  
   ```  
  
    バインディングのプロパティとその設定方法の詳細については、[mySAP Business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)を参照してください。  
  
   > [!IMPORTANT]
   >  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]しばらくお待ちくださいこの処理には、数分かかることがあります SQL スクリプト、SapAdapter-DbScript-Install.sql、SQL server データベースおよびデータベース オブジェクトを作成する SQL Server の管理者によって実行する必要があります。 スクリプトは通常にインストールされて*\<インストール ドライブ\>*: Program FilesMicrosoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。  
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
  
## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)