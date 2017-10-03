---
title: "SQL アダプターを使用して大規模なデータ型を持つテーブルとビューの操作を実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cec15b01-7a57-4917-8c21-44a1cfaadc59
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85403ed8ed76246b93bd30c5246fb7a799284ec1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter"></a>SQL アダプターを使用して大規模なデータ型を持つテーブルとビューの操作を実行します。
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントの読み取りし、は、大規模なデータ型の列のデータを更新する、varchar (max)、nvarchar (max)、または varbinary (max) を有効にします。 このような列からデータを読み取る、アダプターのクライアントは、Select 操作を使用できます。 挿入またはこのような列にデータを更新は、アダプターは、ここでの型 varchar (max)、nvarchar (max)、または varbinary (max) 列の名前は < column_name > 設定 < column_name > 操作を公開します。  
  
 さらに、SQL Server 2008 でテキスト ドキュメントやイメージなどの非構造化データを格納 varbinay(max) 列を持つことができます。 このような非構造化データには、FILESTREAM データは呼び出されます。 FILESTREAM データは、ファイル システム上のファイルとして格納することができます。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] Varbinary (max) 型の列に FILESTREAM データを入力するクライアントを有効にします。 FILESTREAM ストレージの詳細については、次を参照してください。 [FILESTREAM の概要](https://msdn.microsoft.com/library/bb933993(SQL.100).aspx)です。  
  
 このトピックの内容が行う必要があります、特定のタスクに関する情報を提供、コンピューター上には、SQL Server とを挿入または FILESTREAM データを更新できるアダプターのクライアントを実行しているコンピューターを実行しています。 このトピックでは、FILESTREAM データを挿入するセット < column_name > の操作を実行する手順についても示します。  
  
> [!NOTE]
>  ユーザー定義型の列を含むテーブルでの操作を実行する場合、必ずするを参照してください[テーブルと、SQL アダプターを使用してユーザー定義型を持つビューに対して操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)アプリケーションの開発を開始する前にします。  
  
## <a name="prerequisites"></a>前提条件  
 SQL Server を実行しているコンピューターと、アダプターのクライアントを実行しているコンピューターで、次のタスクを行う必要があります。  

  
-   **SQL Server を実行するコンピューター**  
  
    -   SQL Server インスタンスで FILESTREAM を有効にする必要があります。 詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=122486](http://go.microsoft.com/fwlink/?LinkId=122486)です。  
  
    -   FILESTREAM が有効なデータベースを作成する必要があります。 詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=122487](http://go.microsoft.com/fwlink/?LinkId=122487)です。  
  
    -   FILESTREAM データを格納するテーブルが必要です。 詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=122488](http://go.microsoft.com/fwlink/?LinkId=122488)です。  
  
    -   SQL Server データベースをホストするコンピューターで MSDTC を構成する必要があります。 MSDTC を構成する方法については、次を参照してください。 [SQL サーバーとアダプターのクライアントで MSDTC を構成する](../../adapters-and-accelerators/adapter-sql/configure-msdtc-on-sql-server-and-adapter-client.md)です。  
  
-   **アダプターのクライアントを実行するコンピューター**  
  
    -   SQL クライアント接続 SDK がインストールされている可能性があります。 SQL Server 2008 セットアップを実行しを選択すると、SQL クライアント接続 SDK をインストールすることができます**SQL クライアント接続 SDK**で、**機能の選択**ウィザードのページです。 アダプターは、FILESTREAM 操作を実行するのに、SQL クライアント接続 SDK と共にインストールされる、sqlncli10.dll を使用します。  
  
    -   アダプターのクライアントを実行しているコンピューターで MSDTC を構成する必要があります。 MSDTC を構成する方法については、次を参照してください。 [SQL サーバーとアダプターのクライアントで MSDTC を構成する](../../adapters-and-accelerators/adapter-sql/configure-msdtc-on-sql-server-and-adapter-client.md)です。  
  
 これらのタスクを完了するがすべて設定するを挿入または SQL Server 2008 データベースのテーブルに FILESTREAM データを更新します。  
  
## <a name="how-this-topic-demonstrates-operations-on-large-data-types"></a>このトピックの内容が大量のデータ型に対する操作を示しています  
 大規模なデータ型を持つテーブルでセット < column_name > 操作を実行する方法を示すためには、列 Id とドキュメントを持つレコード、テーブルを取得します。 Id 列では、型は uniqueidentifier はあり、GUID ではします。 [ドキュメント] 列は型 varbinary (max) です。 Id 列が既に GUID であると仮定 '`438B7B4C-5491-409F-BCC1-78817C399EC3`' です。 [ドキュメント] 列を更新するには、アダプターは、SetDocument 操作を公開します。  
  
> [!NOTE]
>  SQL Server 2008 では、FILESTREAM 操作を示すためには、想定してドキュメントの列が FILESTREAM データを格納できます。  
  
## <a name="how-to-perform-operations-on-a-sql-server-database"></a>SQL Server データベースで操作を実行する方法  
 使用して、SQL Server データベースでの操作を実行[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [SQL アダプターと BizTalk アプリケーションを開発する基盤](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)です。 大規模なデータ型を持つテーブルでの操作を実行するには、これらのタスクです。  
  
1.  BizTalk プロジェクトを作成し、< column_name > の設定操作のスキーマを生成します。 このトピックのスキーマを生成する、 **SetDocument**の操作、**レコード**テーブル。  
  
2.  SQL Server データベースからメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  レコードの表に、SetDocument 操作を呼び出すオーケストレーションを作成します。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックの内容に基づくサンプル  
 サンプルは、FILESTREAMOperation、このトピックの内容に基づいてが付属して、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。 [SQL アダプタ サンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)です。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 大規模なデータ型の列の値を更新する方法を示すためには、レコードの表の SetDocument 操作用のスキーマを生成します。 BizTalk プロジェクトを作成して使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。 参照してください[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)スキーマを生成する方法についての詳細。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 先に生成したスキーマは、オーケストレーションのメッセージに求められる "型" を記述します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 オーケストレーションのメッセージを作成し、それらを前の手順で生成されたスキーマにリンクする必要がありますようになりました。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**です。  
  
2.  まだ開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。  
  
3.  オーケストレーション ビューで右クリック**メッセージ**、クリックして**新しいメッセージ**です。  
  
4.  新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。  
  
5.  **プロパティ**のウィンドウ、 **Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Request`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *SetOperation.TableOperation_dbo_Records.SetDocument*SetOperation は、BizTalk プロジェクトの名前。 TableOperation_dbo_Records は、レコードのテーブルで SetDocument 操作に対して生成されるスキーマです。|  
  
6.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Response`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *SetOperation.TableOperation_dbo_Records.SetDocumentResponse*です。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SQL Server で操作を実行するためです。 このオーケストレーションでの要求メッセージを削除する受信場所が、定義されています。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]このメッセージを消費し、SQL Server に渡します。 SQL Server からの応答は、別の場所に保存されます。 送信を含めるし、受信図形の SQL Server にメッセージを送信し、それぞれ、応答を受信する必要があります。 SetDocument 操作のサンプルのオーケストレーションには、次のようになります。  
  
 ![FILESTREAM 操作を実行するオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/b8c1c04c-142f-44a0-a545-8ec0cfdd9a5b.gif "b8c1c04c-142f-44a0-a545-8ec0cfdd9a5b")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。 図形 列に表示名は、単に記載されているオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-設定**名前**に*ReceiveMessage*<br />-設定**アクティブ**に*は True。*|  
|SendMessage|Send|-設定**名前**に*SendMessage*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認してください。 ポート列に表示される名前は、オーケストレーションで表示されているポートの名前です。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|MessageIn|-設定**識別子**に*MessageIn*<br />-設定**型**に*MessageInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|ResponseOut|-設定**識別子**に*ResponseOut*<br />-設定**型**に*ResponseOutType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>アクション図形のメッセージを指定して、ポートへの接続  
 次の表は、プロパティとアクション図形のメッセージを指定して、メッセージ、ポートにリンクを設定する必要があります、値を指定します。 図形 列に表示名は、既に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*MessageIn.FileStream.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.FileStream.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.FileStream.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*ResponseOut.FileStream.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートを接続しているし、オーケストレーションが完了します。  
  
 BizTalk ソリューションをビルドし、BizTalk Server に展開する必要がありますようになりました。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 [オーケストレーション] ペインで以前に作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール アプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。 BizTalk オーケストレーションは、要求メッセージを消費し、SQL Server データベースに送信します。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが、SQL Server データベースからの応答を含む応答メッセージをドロップする場所に場所を定義します。  
  
    -   SQL Server データベースにメッセージを送信する物理 Wcf-custom または WCF-SQL 送信ポートを定義します。 送信ポートでアクションを指定することもあります。 ポートを作成する方法については、次を参照してください。 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)です。
  
        > [!IMPORTANT]
        >  トランザクション内では、FILESTREAM データを入力する操作を実行する必要があります。 そのため、確認、 **UseAmbientTransaction**に設定されているプロパティのバインド**True** Wcf-custom または WCF-SQL 送信ポート。 バインディング プロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
        > [!IMPORTANT]
        >  操作を実行するためには、FILESTREAM データを挿入する必要があります常に Windows 認証を使用して Wcf-custom 上の SQL Server に接続または WCF-SQL 送信ポート。 で、**資格情報** タブで、ポートのプロパティ ダイアログ ボックスで、**シングル サインオンを使用しないでください**オプション、およびユーザー名とパスワードを空白のままにします。  
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] (着信) の受信ポートを (発信) の送信ポートを作成または管理コンソールです。 詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)です。
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 実行するための BizTalk アプリケーションを開始する必要があります、 **SetDocument**での操作、**レコード**テーブル。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   SQL Server データベースにメッセージを送信する Wcf-custom または WCF-SQL 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後、ファイルに要求メッセージをドロップする必要がありますの受信場所。 要求メッセージのスキーマは、以前に生成した SetDocument 操作用のスキーマに準拠している必要があります。 たとえば、ドキュメントの列を更新する要求メッセージには。  
  
```  
<SetDocument xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Records">  
  <Filter>WHERE Id='438B7B4C-5491-409F-BCC1-78817C399EC3'</Filter>  
  <Data>UwBlAHQAdgBfAHYAYQByAGIAaQBuAGEAcgB5AE0AQQBYAA==</Data>  
</SetDocument>  
```  
  
> [!IMPORTANT]
>  `Filter`要素は、WHERE 句の条件を含める必要がありますが、アダプターがレコードを更新します。 `Data`要素はドキュメントの列に挿入する base64 でエンコードされた値を含める必要があります。  
  
 この要求メッセージは、指定の値を持つドキュメントの列を更新します。 オーケストレーションはメッセージを処理して、SQL Server データベースに送信します。 SQL Server データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、上記の要求メッセージ用の SQL Server データベースからの応答には。  
  
```  
\<?xml version="1.0" encoding="utf-8" ?>   
<SetDocumentResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Records" />  
```  
  
 アダプターの空の応答を送信する、**設定 < column_name >**操作します。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)です。
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)