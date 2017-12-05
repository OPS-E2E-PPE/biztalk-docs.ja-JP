---
title: "Transactional Adapter (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31a13377-cc89-4763-ad1b-508a16fc9708
caps.latest.revision: "36"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f934857103952a035159cc08678c8ce8c8e51a56
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="transactional-adapter-biztalk-server-sample"></a>Transactional Adapter (BizTalk Server サンプル)
Transactional Adapter サンプルは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージの処理中にデータベースに対して明示的な Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクションを作成および使用する方法を示すものです。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルには、MSDTC トランザクションを使用して SQL Server データベースからデータを取得するために、ユーザーが指定した間隔で SQL ステートメントを実行する受信アダプターが含まれています。 データは同じトランザクションのコンテキストでメッセージ形式で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージ ボックス データベースに送信されます。  
  
 対応する送信アダプターは、トランザクションのコンテキストで BizTalk メッセージからの入力を使用してユーザー指定の SQL ストアド プロシージャを実行します。 そのメッセージからの特定のデータを使用して、同じトランザクションでメッセージ ボックス データベースから対応するメッセージを削除します。  
  
## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 このサンプルのソリューションには 2 つのプロジェクトが含まれています。 1 つ目のプロジェクトは、ユーザーがこのアダプターを使用する受信場所と送信ポートを構成できるようにランタイムの前に使用される管理プロジェクト (Admin) です。 2 つ目のプロジェクトは、送信アダプターと受信アダプターの実行中に実行されるランタイム プロジェクト (Runtime) です。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、SDK がある次の場所にあります。  
  
 \<*パスのサンプル*\>\Samples\AdaptersDevelopment\TransactionalAdapter。 管理構成プロジェクトは \Admin フォルダーにあり、ランタイム プロジェクトは \Runtime フォルダーにあります。  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|管理プロジェクトのファイル名|管理プロジェクト ファイルの説明|  
|----------------------------|------------------------------------|  
|TransactionalAdmin.csproj|ランタイム前の構成に使用されるアダプター管理プロジェクト ファイル|  
|TransactionalReceiveHandler.xsd|受信ハンドラー プロパティの XSD|  
|TransactionalReceiveLocation.xsd|受信場所プロパティの XSD|  
|TransactionalTransmitLocation.xsd|送信場所プロパティの XSD|  
|TransactionalTransmitHandler.xsd|送信ハンドラー プロパティの XSD|  
|TransactionalAdapterManagement.cs|アダプター構成管理。 サポートされていると考えられる構成の種類 (4 種類) のそれぞれに XSD 構成スキーマを返すために、BizTalk アダプター フレームワークによって呼び出される GetConfigSchema を含んでいます。|  
  
|ランタイム プロジェクトのファイル名|ランタイム プロジェクト ファイルの説明|  
|------------------------------|--------------------------------------|  
|Transactional.csproj|アダプター ランタイム プロジェクト ファイル|  
|TransactionalAsyncBatch.cs|アダプターの送信部分の非同期的な実装|  
|TransactionalDeleteBatch.cs|メッセージ バッチを削除し、トランザクションをコミットまたは中断するように指定します|  
|TransactionalProperties.cs|構成プロパティを抽出および設定します|  
|TransactionalReceiver.cs|受信エンドポイントを作成および管理します|  
|TransactionalReceiverEndpoint.cs|受信場所ごとの実際の受信待機またはポーリング|  
|TransactionalTransmitter.cs|メッセージ エンジンから送信されるメッセージ バッチを受け取ります|  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 このサンプルは、明示的なトランザクションを使用してカスタムの送信アダプターと受信アダプターを作成するときに使用するフレームワークです。  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
  
> [!IMPORTANT]
>  BizTalk 環境が 64 ビットである、またはインストール場所が変更されている場合は、それに合わせて OutboundAssemblyPath、InboundAssemblyPath、および AdapterMgmtAssemblyPath を変更する必要があります。  
  
#### <a name="create-a-strong-name-key-for-the-transactional-adapter-sample"></a>Transactional Adapter サンプルの厳密な名前キーの作成します。  
  
1.  開始**Visual Studio コマンド プロンプト**です。  
  
2.  コマンド プロンプトで次のコマンドを入力し、Enter キーを押します。  
  
    ```  
    cd \Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersDevelopment\TransactionalAdapter\Runtime  
    ```  
  
3.  コマンド プロンプトで次のコマンドを入力し、Enter キーを押します。  
  
    ```  
    sn –k TransactionalAdapter.snk  
    ```  
  
4.  コマンド プロンプトで次のように入力します。**終了**、し、enter キーを押し、コマンド プロンプト ウィンドウを閉じます。  
  
#### <a name="build-the-transactional-adapter-solution"></a>トランザクション アダプター ソリューションをビルドします。  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**アクセサリ**、順にクリック**Windows エクスプ ローラー**です。  
  
2.  参照[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AdaptersDevelopment\TransactionalAdapter、 をダブルクリック**TransactionalAdapter.sln**を開くにはこのソリューションで[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。  
  
3.  ソリューション エクスプ ローラーで Transactional Adapter プロジェクト (Admin および Runtime) の両方を構築を右クリックして**Solution transactionaladapter**、順にクリック**リビルド**です。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="register-the-transactional-adapter"></a>トランザクション アダプターを登録します。  
  
1.  Windows エクスプローラーで、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AdaptersDevelopment\TransactionalAdapter\Admin に移動します。  
  
2.  トランザクション アダプター データをレジストリに追加するにはダブルクリック**TransactionalAdmin.reg**です。  
  
    > [!NOTE]
    >  **TransactionalAdmin.reg** C:\Program files \microsoft BizTalk Server へのハードコードされたパスが含まれています\\です。 既定の場所に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールしなかった場合や、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストールを以前のバージョンからアップグレードした場合は、TransactionalAdmin.reg ファイルを変更して適切なパスを指定する必要があります。 "InboundAssemblyPath"、"OutboundAssemblyPath"、および "AdapterMgmtAssemblyPath" の値に関連付けられたパスを、指定されたファイルの正しい場所を指すように更新します。  
  
    > [!IMPORTANT]
    >  BizTalk を 64 ビット コンピューターにインストールする場合は、hkey_classes_root \clsid\ レジストリ エントリのすべてのインスタンスを hkey_classes_root \wow6432node\clsid\ に変更、 **TransactionalAdmin.reg**レジストリ ファイル。  
  
3.  **レジストリ エディター**ダイアログ ボックスで、をクリックして**はい**サンプル アダプターをレジストリに追加し、をクリックする**[ok]**です。  
  
4.  クリックして、Windows エクスプ ローラーを閉じます**ファイル**、クリックして**閉じる**です。  
  
#### <a name="add-the-transactional-adapter-to-biztalk-server"></a>BizTalk Server へのトランザクション アダプターの追加  
  
1.  クリックして、**開始**メニューの **すべてのプログラム**を選択[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、し、 **BizTalk Server 管理コンソール**です。  
  
2.  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開、 **BizTalk Server 管理コンソール**ツリーで、展開、 **BizTalk グループ**ツリーを展開し、展開、**プラットフォームの設定**ツリー。  
  
3.  右クリック**アダプター**をクリックして**新規**、順にクリック**アダプター**です。  
  
4.  **アダプター プロパティ** ダイアログ ボックスで、次の操作です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |名前|型**TransactionalAdapter**です。|  
    |[アダプター]|選択**Txn**ドロップダウン リストからです。 実行結果としてこのエントリが表示されます、 **TransactionalAdmin.reg**ファイルの以前です。|  
    |Description|型**Transactional Adapter サンプル**です。|  
  
5.  クリックして **OK.** これで、BizTalk 管理コンソールの右ウィンドウにあるアダプターの一覧にアダプターが表示されます。  
  
#### <a name="create-a-receive-port-and-location-that-uses-the-adapter"></a>アダプターを使用する受信ポートと受信場所の作成  
  
1.  展開、 **BizTalk グループ [サーバー名]**内のノード[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**アプリケーション** ノードを展開**BizTalk アプリケーション 1**ノード。  
  
2.  右クリック**受信ポート**、順にクリック**新規****一方向の受信ポート。**  
  
3.  **名**、入力**TxnReceivePort1**、クリックして**[ok]**です。  
  
4.  右クリックし、**受信場所**ノード、をクリックして**新規**、し、**一方向の受信場所**です。  
  
5.  **受信ポートの選択**ダイアログ ボックスで、 **TxnReceivePort1**、順にクリック**OK**です。  
  
6.  **受信場所のプロパティ**ダイアログ ボックスで、**全般** タブで、入力**TxnReceiveLocation1**の**名前**です。 確認してください、**受信ポート**表示にラベルを付ける**TxnReceivePort1**です。  
  
7.  **型**で、ボックスの一覧、**トランスポート**フレームで、 **TransactionalAdapter です。**  
  
8.  **受信 * * * パイプライン**ボックスで、確認**PassThruReceive**が選択されています。 残りのプロパティは既定の設定のままにします。  
  
9. クリックして、**構成**横に、**型**ボックスの一覧です。 これにより、このアダプターに固有のダイアログが表示されます。 次のように、必要に応じて指定順にクリックして**[ok]**です。  
  
    |プロパティ|設定|  
    |--------------|-------------|  
    |接続文字列|Northwind データベースとの接続と認証に使用される SQL データベース接続文字列。 後でこのデータベースを使用する SQL スクリプトを実行します。|  
    |コマンド テキスト|Northwind データベースのデータを取得して BizTalk メッセージに格納するために、Northwind データベースに対して実行される SQL ステートメント。|  
    |Cookie|URI の一部を構成します。受信場所の名前 (TxnReceiveLocation1 など) のような一意の名前を入力してください。|  
    |[ポーリング間隔の単位]|データのポーリング時間の測定単位。 "秒" に設定します。|  
    |ポーリング間隔|データのポーリング時間を示す数値。 15 秒に設定します。|  
  
10. をクリックして**[ok]**を構成 ダイアログ ボックスを閉じ**OK**を閉じます、**受信場所のプロパティ** ダイアログ ボックスに戻るには、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]です。  
  
#### <a name="create-a-send-port-and-send-handler-that-use-the-adapter"></a>アダプターを使用する送信ポートと送信ハンドラーの作成  
  
1.  **BizTalk アプリケーション 1**ノードが展開を右クリックして**送信ポート**、クリックして**新規**を選択し、**静的の一方向送信ポート**.  
  
2.  **名前**フィールドに「 **TxnSendPort1**です。  
  
3.  **トランスポート**フレームの**型**ドロップダウン リストで、**TransactionalAdapter**`.`  
  
4.  **送信パイプライン**ボックスで、確認**PassThruTransmit**が選択されています。  
  
5.  クリックして、**構成**横に、**トランスポート**ドロップダウン リスト。表示されるダイアログ ボックスで、適切なように、次を指定し、をクリックして**OK**です。  
  
    |プロパティ|設定|  
    |--------------|-------------|  
    |Cookie|一部を構成 - URI の値を入力して、一意ここで、受信場所の名前などのインスタンス: **TxnSendPort1**です。|  
    |接続文字列|Northwind データベースとの接続と認証に使用される SQL データベース接続文字列。 最も高くなります、構成に使用されるものと同じ、 **TxnReceiveLocation1**受信場所。|  
    |ストアド プロシージャ|ストアド プロシージャの名前のデータベースをポーリングするために実行を取得する**sp_txnProc**です。 という名前の文字列パラメーターとしてストアド プロシージャを BizTalk にメッセージを指定の本文@Dataです。 たとえば、ユーザーはここでは後で構成ストアド プロシージャ、名前を持つ**sp_txnProc**です。 アダプターのランタイムはデータベースに対しこの呼び出しと同等のものを実行します。<br /><br /> exec sp_txnProc @Data 「BizTalk メッセージの内容」を =|  
  
6.  左側のナビゲーション ウィンドウで **フィルター**です。  
  
7.  フィルター式エディターで、次の式を入力してこの送信ポートのサブスクリプションを設定し、TxnReceivePort1 受信ポートから受信されるすべてのメッセージを受信します。  
  
     これらの値を入力してください:**BTS です。ReceivePortName TxnReceivePort1 を = =**  
  
    1.  `(property)`  **BTS です。ReceivePortName**  
  
    2.  `(operator)`  **==**  
  
    3.  `(value)`  **TxnReceivePort1**  
  
8.  アダプターのプロパティの残りの既定値を使用して選択**OK**です。  
  
## <a name="run-the-sample"></a>サンプルの実行  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2** **SQL Server Management Studio**。  
  
2.  **サーバーへの接続** ダイアログ ボックスで確認**サーバーの種類**に設定されている**データベース エンジン**、データベース サーバーに認証する資格情報を入力し、の選択**接続**です。  
  
3.  選択、**新しいクエリ**ツールバーのボタンと貼り付け、次の点をテスト テーブル、テスト データ、およびテストを挿入する新しいクエリ ウィンドウをストアド プロシージャを Northwind データベースにします。 選択、 **Execute**ツールバー ボタンをクリックします。  
  
    ```  
    use [Northwind]  
    GO  
    if exists (select * from dbo.sysobjects where id = object_id(N'[dbo].[scratch]') and OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    drop table [dbo].[scratch]  
    GO  
    CREATE TABLE [dbo].[scratch] (  
         [id] [int] IDENTITY (1, 1) NOT NULL ,  
         [msg] [nvarchar] (4000) NOT NULL   
    ) ON [PRIMARY]  
    GO  
    GRANT SELECT , UPDATE , INSERT ON [dbo].[scratch] TO [public]  
    GO  
    if exists (select * from dbo.sysobjects where id = object_id(N'[dbo].[sp_txnProc]') and OBJECTPROPERTY(id, N'IsProcedure') = 1)  
    drop procedure [dbo].[sp_txnProc]  
    GO  
    CREATE PROCEDURE [dbo].[sp_txnProc] @Data nvarchar (4000)  
    AS   
    INSERT scratch ( msg ) values ( @Data )  
    GO  
    GRANT EXECUTE ON [dbo].[sp_txnProc] TO [public]  
    GO  
    ```  
  
4.  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開、**送信ポート**ノードで、選択、 **TxnSendPort1**送信ポート、および選択**開始**です。  
  
5.  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開、 **ReceiveLocations**ノードで、選択、 **TxnRecieveLocation1**受信場所をクリックし **を有効にする**です。  
  
6.  受信場所を有効にすると、指定された間隔で自動的にデータベースがポーリングされ、データが変更されているかどうかが判断されます。  
  
## <a name="classes-or-methods-used-in-the-sample"></a>クラスまたはメソッドが、サンプルで使用します。  
* IBTTransmitterBatch インターフェイス (COM)
  
* IBTTransportProxy インターフェイス (COM)

これらの方法が説明されている[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。 
  
## <a name="see-also"></a>参照  
 [アダプタ サンプル - 開発](../core/adapter-samples-development.md)   
 [アダプターの登録](../core/registering-an-adapter.md)