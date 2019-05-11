---
title: SQL アダプターを使用して大規模なデータ型を持つテーブルとビューで操作を実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cec15b01-7a57-4917-8c21-44a1cfaadc59
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7115d902616856c3b256dcbd22a52611d772143
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368099"
---
# <a name="run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter"></a>SQL アダプターを使用して大規模なデータ型を持つテーブルとビューで操作を実行します。
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントの読み取りし、は、大規模なデータ型の列のデータを更新する、varchar (max)、nvarchar (max)、または varbinary (max) を有効にします。 このような列からデータを読み取る、アダプターのクライアントは、選択操作を使用できます。 を挿入またはこのような列にデータを更新するには、は、アダプターは、< column_name > がの型 varchar (max)、nvarchar (max)、または varbinary (max) 列の名前を、< column_name > の設定操作を公開します。  
  
 さらに、SQL Server 2008 でテキスト ドキュメントやイメージなどの非構造化データを格納する varbinay(max) 列があることができます。 このような非構造化データには、FILESTREAM データが呼び出されます。 FILESTREAM データは、ファイル システム上のファイルとして格納することができます。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]により、クライアントは、varbinary (max) 型の列に FILESTREAM データを入力できます。 FILESTREAM ストレージの詳細については、次を参照してください。 [FILESTREAM の概要](https://msdn.microsoft.com/library/bb933993(SQL.100).aspx)します。  
  
 このトピックでは実行する必要があります、特定のタスクについては、コンピューター上には、SQL Server および挿入または FILESTREAM データを更新できるアダプター クライアントを実行しているコンピューターを実行しています。 このトピックでは、FILESTREAM データを挿入するセット < column_name > の操作を実行する方法の手順も示します。  
  
> [!NOTE]
>  ユーザー定義型の列を含むテーブルに対して操作を実行している場合ことを確認するを参照してください[テーブルと、SQL アダプターを使用してユーザー定義型を持つビューで操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)アプリケーションの開発を開始する前にします。  
  
## <a name="prerequisites"></a>前提条件  
 SQL Server を実行しているコンピューターと、アダプターのクライアントを実行しているコンピューターでは、次のタスクを実行する必要があります。  

  
- **SQL Server を実行するコンピューター**  
  
  -   SQL Server インスタンスで FILESTREAM を有効にする必要があります。 詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=122486](http://go.microsoft.com/fwlink/?LinkId=122486)します。  
  
  -   FILESTREAM が有効なデータベースを作成する必要があります。 詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=122487](http://go.microsoft.com/fwlink/?LinkId=122487)します。  
  
  -   FILESTREAM データを格納するためのテーブルが必要です。 詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=122488](http://go.microsoft.com/fwlink/?LinkId=122488)します。  
  
  -   SQL Server データベースをホストするコンピューターでは、MSDTC を構成する必要があります。 MSDTC を構成する方法については、次を参照してください。 [SQL サーバーとアダプターのクライアントで MSDTC を構成する](../../adapters-and-accelerators/adapter-sql/configure-msdtc-on-sql-server-and-adapter-client.md)します。  
  
- **アダプターのクライアントを実行するコンピューター**  
  
  -   インストールされている SQL Client Connectivity SDK が必要です。 SQL クライアント接続 SDK をインストールするには、SQL Server 2008 セットアップを実行し、選択**SQL Client Connectivity SDK**で、**機能の選択**ウィザードのページ。 アダプターは、FILESTREAM 操作を実行するのに SQL クライアント接続 sdk では、インストールされている、sqlncli10.dll を使用します。  
  
  -   アダプターのクライアントを実行しているコンピューターでは、MSDTC を構成する必要があります。 MSDTC を構成する方法については、次を参照してください。 [SQL サーバーとアダプターのクライアントで MSDTC を構成する](../../adapters-and-accelerators/adapter-sql/configure-msdtc-on-sql-server-and-adapter-client.md)します。  
  
  これらのタスクを完了すると、設定は完了を挿入または SQL Server 2008 データベース テーブル内の FILESTREAM データを更新します。  
  
## <a name="how-this-topic-demonstrates-operations-on-large-data-types"></a>ここで大量のデータ型に対する演算をについて説明する方法  
 大規模なデータ型を持つテーブルに対するセット < column_name > の操作を実行する方法を示すためには、テーブルをレコード Id とドキュメントの列を持つを実行します。 Id 列は型の一意識別子は GUID を受け取ります。 ドキュメントの列は、varbinary (max) 型のです。 Id 列は既に、GUID を前提としています。 '`438B7B4C-5491-409F-BCC1-78817C399EC3`'。 ドキュメントの列を更新するには、アダプターは、SetDocument 操作を公開します。  
  
> [!NOTE]
>  SQL Server 2008 では、FILESTREAM 操作を示すためには、ドキュメントの列が FILESTREAM データを格納できます想定しています。  
  
## <a name="how-to-perform-operations-on-a-sql-server-database"></a>SQL Server データベースで操作を実行する方法  
 使用して SQL Server データベースでの操作を実行する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)します。 大規模なデータ型を持つテーブルに対する操作を実行するには、これらのタスクは。  
  
1. BizTalk プロジェクトを作成し、< column_name > の設定操作のスキーマを生成します。 このトピックでは、スキーマを生成、 **SetDocument**の操作、**レコード**テーブル。  
  
2. SQL Server データベースからメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
3. レコードのテーブルで SetDocument 操作を呼び出すオーケストレーションを作成します。  
  
4. ビルドし、BizTalk プロジェクトを配置します。  
  
5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
6. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックに基づくサンプル  
 サンプル FILESTREAMOperation、このトピックの「に基づいてが付属、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、次を参照してください。 [SQL アダプタのサンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 大規模なデータ型の列の値を更新する方法を示すためには、レコードのテーブルの SetDocument 操作用のスキーマを生成します。 BizTalk プロジェクトを作成して使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。 参照してください[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)スキーマを生成する方法の詳細について。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 先に生成したスキーマは、オーケストレーションのメッセージに求められる "型" を記述します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 オーケストレーションのメッセージを作成し、前の手順で生成したスキーマにリンクする必要がありますようになりました。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。  
  
2.  開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
3.  オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  
  
4.  新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  
  
5.  **プロパティ**のウィンドウ、 **Message_1**次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Request`」と入力します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *SetOperation.TableOperation_dbo_Records.SetDocument*SetOperation は、BizTalk プロジェクトの名前です。 TableOperation_dbo_Records は、レコードのテーブルで SetDocument 操作に対して生成されるスキーマです。|  
  
6.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Response`」と入力します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *SetOperation.TableOperation_dbo_Records.SetDocumentResponse*します。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の SQL Server で操作を実行します。 このオーケストレーションでの要求メッセージを削除する、定義されている受信場所。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]がこのメッセージを使用して、SQL Server に渡します。 SQL Server からの応答は、別の場所に保存されます。 送信を含めるし、受信図形とそれぞれに、応答を受信する SQL Server にメッセージを送信する必要があります。 SetDocument 操作サンプルのオーケストレーションには、次のようになります。  
  
 ![FILESTREAM 操作を実行するオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/b8c1c04c-142f-44a0-a545-8ec0cfdd9a5b.gif "b8c1c04c-142f-44a0-a545-8ec0cfdd9a5b")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 図形の列に示した名前は、単に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-設定**名前**に*ReceiveMessage*<br />-設定**アクティブ**に*は True。*|  
|SendMessage|Send|-設定**名前**に*SendMessage*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認します。 ポート列に示した名前は、オーケストレーションで表示されているポートの名前です。  
  
|Port|[プロパティ]|  
|----------|----------------|  
|MessageIn|-設定**識別子**に*MessageIn*<br />-設定**型**に*MessageInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|ResponseOut|-設定**識別子**に*ResponseOut*<br />-設定**型**に*ResponseOutType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>アクション図形は、メッセージを指定し、ポートに接続  
 次の表では、プロパティとアクション図形のメッセージを指定して、メッセージ ポートにリンクを設定する必要があります、値を指定します。 図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*MessageIn.FileStream.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.FileStream.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.FileStream.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*ResponseOut.FileStream.Request*|  
  
 これらのプロパティを指定したら、メッセージの構築図形とポートを接続すると、し、オーケストレーションが完了します。  
  
 BizTalk ソリューションをビルドし、BizTalk Server に展開する必要がありますようになりました。 詳細については、次を参照してください。[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)します。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 [オーケストレーション] ペインで先ほど作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールにアプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル。基本的な BizTalk アプリケーション展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)します。
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- 物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 このオーケストレーションの次の操作を行う必要があります。  
  
  - ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用し、SQL Server データベースに送信します。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションが、SQL Server データベースからの応答を含む応答メッセージをドロップする場所の場所を定義します。  
  
  - SQL Server データベースにメッセージを送信する物理 Wcf-custom または WCF-SQL 送信ポートを定義します。 送信ポートでアクションを指定することも必要があります。 ポートを作成する方法については、次を参照してください。 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)します。
  
    > [!IMPORTANT]
    >  トランザクション内では、FILESTREAM データを入力する操作を実行する必要があります。 そのため、必ず、 **UseAmbientTransaction**に設定されているプロパティのバインド**True** Wcf-custom または WCF-SQL 送信ポート。 バインディング プロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。  
    > 
    > [!IMPORTANT]
    >  操作を実行するためには、FILESTREAM データを挿入する必要があります常に Windows 認証を使用して WCF カスタム上の SQL Server に接続または WCF-SQL 送信ポート。 そのためで、**資格情報** タブで、ポートのプロパティ ダイアログ ボックスで、**シングル サインオンを使用しないでください**オプション、およびユーザー名とパスワードを空白のままにします。  
    > 
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール (発信) の送信ポートを作成したり (着信) 用のポートを受信します。 詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)します。
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 実行するための BizTalk アプリケーションを起動する必要があります、 **SetDocument**操作、**レコード**テーブル。 BizTalk アプリケーションを開始する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)します。
  
 この段階で、ことを確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   SQL Server データベースにメッセージを送信する Wcf-custom または WCF-SQL 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 ファイルに要求メッセージを削除する必要があります、アプリケーションを実行した後の受信場所。 要求メッセージのスキーマは、先に生成した SetDocument 操作のスキーマに準拠する必要があります。 たとえば、ドキュメントの列を更新する要求メッセージには。  
  
```  
<SetDocument xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Records">  
  <Filter>WHERE Id='438B7B4C-5491-409F-BCC1-78817C399EC3'</Filter>  
  <Data>UwBlAHQAdgBfAHYAYQByAGIAaQBuAGEAcgB5AE0AQQBYAA==</Data>  
</SetDocument>  
```  
  
> [!IMPORTANT]
>  `Filter`要素は、WHERE 句の条件を含める必要があります、アダプターが、レコードを更新します。 `Data`要素は、ドキュメントの列に挿入する base64 でエンコードされた値を含める必要があります。  
  
 この要求メッセージは、指定の値を持つドキュメントの列を更新します。 オーケストレーションはメッセージを使用し、SQL Server データベースに送信します。 SQL Server データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、前の要求メッセージの SQL Server データベースからの応答には。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<SetDocumentResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Records" />  
```  
  
 空の応答送信、 **< column_name > が設定**操作。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定、ファイルからインポートできます。 バインド ファイルの詳細については、次を参照してください。[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)します。
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用して BizTalk アプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)