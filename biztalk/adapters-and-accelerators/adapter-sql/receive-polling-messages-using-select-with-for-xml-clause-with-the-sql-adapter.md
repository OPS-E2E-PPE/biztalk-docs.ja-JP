---
title: "BizTalk Server を使用して SQL から FOR XML 句で SELECT ステートメントを使用してポーリング メッセージを受信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65c629c1-9ef7-4aa1-8ec1-f94a3cb41cb0
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77ac34fb06497f72b778592b3ce4c927b0ca3a07
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="receive-polling-messages-using-select-statements-with-for-xml-clause-from-sql-using-biztalk-server"></a>BizTalk Server を使用して SQL から FOR XML 句で SELECT ステートメントを使用してポーリング メッセージを受信します。
構成することができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SELECT ステートメントまたは FOR XML 句を含むストアド プロシージャを使用して SQL Server のテーブルまたはビューのデータの定期的な変更メッセージを受信します。 これらのステートメントは、データベースをポーリングするアダプターを実行するポーリング ステートメントとして指定できます。 ポーリング ステートメントには、SELECT ステートメントまたは結果セットを返すストアド プロシージャを使用できます。  
  
 アダプターがポーリングをサポートする方法の詳細については、次を参照してください。[ポーリングのサポート](https://msdn.microsoft.com/library/dd788416.aspx)です。 ポーリング操作用の SOAP メッセージの構造については、次を参照してください。[ポーリングと TypedPolling 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)です。 SQL [FOR XML 句](https://docs.microsoft.com/sql/relational-databases/xml/for-xml-sql-server)詳細を示します。
  
> [!NOTE]
>  このトピックを使用する方法を示します、 **XmlPolling**ポーリング メッセージを受信する操作を受信します。 **XmlPolling** SELECT ステートメントまたは FOR XML 句を含むストアド プロシージャを使用して SQL Server データベースをポーリングする操作を使用します。 メッセージを**XmlPolling**操作には、SQL Server Management Studio で、SELECT ステートメントまたはストアド プロシージャを実行することで受信した xml メッセージが含まれています。  
>   
>  また、各種のポーリング メッセージを受信するのにアダプターを使用することができます。  
>   
>  -   ポーリングの弱い型指定メッセージを取得する場合は、ポーリング操作を使用する必要があります。 詳細については、次を参照してください。[ポーリング受信ベースのデータ変更のメッセージを使用して BizTalk Server で、SQL Server から](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)です。  
> -   使用する必要がありますを厳密に型指定されたポーリング メッセージを取得する場合、 **TypedPolling**操作します。 使用することも必要があります、 **TypedPolling**工程に 1 つの BizTalk アプリケーションで複数の操作をポーリングします。 実行する方法の詳細について**TypedPolling**操作を参照してください[BizTalk Server を使用して SQL Server からデータ変更のポーリングに基づいたメッセージを受信厳密に型指定された](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md)です。  
  
> [!IMPORTANT]
>  かどうかは 1 つの BizTalk アプリケーションに複数のポーリング操作を必要がありますを指定する、 **InboundID**接続一意にする URI の一部として接続プロパティです。 一意の接続 URI の場合を複数作成できます、同じデータベースまたはデータベースでも同じテーブルをポーリングするポートを受信します。 詳細については、次を参照してください。[受信ポーリング メッセージ間で複数の受信ポートから BizTalk Server を使用して SQL](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)です。  
  
## <a name="how-this-topic-demonstrates-polling"></a>このトピックの内容がポーリングを示しています  
 このトピックの内容を示すために方法、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サポート データを受信するメッセージの変更、FOR XML 句を使用して、SELECT ステートメントを使用して SQL Server データベースをポーリングするおです。 SQL Server Management Studio で、このようなステートメントを呼び出す場合、出力は、xml メッセージの形式です。 このようなステートメントを使用して、SQL Server データベースをポーリングする、するには、xml の応答メッセージのスキーマが必要です。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] FOR XML 句を伴う SELECT ステートメントを実行した後、ポーリング メッセージを受信するには、このスキーマが必要です。 そのため、SQL Server データベースをポーリングする FOR XML 句で SELECT ステートメントを使用するに次の一連のタスクを実行する必要があります。  
  
1.  FOR XML 句を伴う SELECT ステートメントの XML 応答メッセージのスキーマを生成します。  
  
2.  BizTalk プロジェクトを作成し、生成されたスキーマをプロジェクトに追加します。  
  
3.  SQL Server データベースから XML 応答メッセージを受信するための BizTalk プロジェクトでメッセージを作成します。  
  
4.  SQL Server データベースからメッセージを受信して、フォルダーに保存するオーケストレーションを作成します。  
  
5.  構築し、BizTalk プロジェクトを展開します。  
  
6.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
    > [!IMPORTANT]
    >  受信ポーリングのシナリオは、一方向の WCF カスタム常に構成する必要があります。 または WCF SQL 受信ポート。 双方向の WCF カスタムまたは WCF SQL 受信ポートの受信操作はサポートされていません。  
  
7.  BizTalk アプリケーションを起動します。  
  
##  <a name="BKMK_RespSchema"></a>SELECT ステートメントの応答メッセージのスキーマを生成します。  
 含めることによって、SELECT ステートメントの応答メッセージのスキーマを生成することができます、`xmlschema`句、`for xml`句。 このトピックで指定された従業員 ID の従業員の個人情報を取得するのに SELECT ステートメントを使用しました 、SELECT ステートメントを実行することによって、スキーマを取得するには、次のように、SELECT ステートメントを記述する必要があります。  
  
```  
SELECT Employee_ID ,Name ,Designation FROM Employee for xml auto, xmlschema  
```  
  
 応答メッセージのスキーマを取得する次の SELECT ステートメントを実行します。 スキーマを保存します。 BizTalk プロジェクトを作成する必要が今すぐ[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]し、このスキーマをプロジェクトに追加します。 この例では、名前を指定できますと、このスキーマ**PollingResponse.xsd**です。  
  
> [!IMPORTANT]
>  削除するかどうかを確認、`xmlschema`句のスキーマを生成する SELECT ステートメントを実行した後です。 失敗した場合に、最後に XmlPolling 操作の一環として BizTalk を通じて、SELECT ステートメントを実行するときに、応答メッセージのスキーマを再生成されます。 削除する必要があります xml として応答メッセージを取得する、`xmlschema`句。  
  
#### <a name="to-add-the-schema-to-a-biztalk-project"></a>BizTalk プロジェクトにスキーマを追加するには  
  
1.  BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。  
  
2.  BizTalk プロジェクトにストアド プロシージャの生成、応答スキーマを追加します。 ソリューション エクスプ ローラーで BizTalk プロジェクトを右クリックし、**追加**、クリックして**既存項目の**します。 [既存項目の追加] ダイアログ ボックスをクリックして、スキーマを保存した場所に移動**追加**です。  
  
3.  内のスキーマを開く[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]次の変更を加えます。  
  
    1.  スキーマにノードを追加し、新しく追加されたこのノードの下の既存のルート ノードを移動します。 ルート ノードに名前を指定します。 このトピックの名前を変更するルート ノード**ルート**です。  
  
    2.  SELECT ステートメントの生成、応答スキーマは、sqltypes.xsd を参照します。 Sqltypes.xsd スキーマから取得できます[http://go.microsoft.com/fwlink/p/?LinkId=131087](http://go.microsoft.com/fwlink/p/?LinkId=131087)です。 Sqltypes.xsd スキーマを BizTalk プロジェクトに追加します。  
  
    3.  SELECT ステートメントの生成、スキーマ内の値を変更`import schemaLocation`以下にします。  
  
        ```  
        import schemaLocation=”sqltypes.xsd”  
        ```  
  
         これを行う sqltypes.xsd スキーマは、BizTalk プロジェクトに既に追加されたためです。  
  
    4.  スキーマのターゲット名前空間を指定します。 クリックして、 **\<スキーマ >**ノード、プロパティ ウィンドウで、名前空間を指定し、 **Target Namespace**プロパティ。 このトピックの付与と名前空間`http://ForXmlPolling/namespace`です。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 スキーマが生成されるは、BizTalk プロジェクトのオーケストレーションの種類からのメッセージをリンクする必要があります。  
  
 このトピックのメッセージを受信する SQL Server データベースから 1 つのメッセージを作成する必要があります。  
  
 メッセージを作成し、それらのスキーマにリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**です。  
  
2.  まだ開いていない場合は、BizTalk プロジェクトのオーケストレーション ビュー ウィンドウを開きます。 をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。  
  
3.  **オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。  
  
4.  新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。  
  
5.  **プロパティ**ウィンドウ**Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**PollingMessage**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*ForXMLPolling.PollingResponse*ここで、 *ForXMLPolling* BizTalk プロジェクトの名前を指定します。 *PollingResponse*下にある説明に従って、SELECT ステートメントを実行することによって生成される応答スキーマの名前を指定[BizTalk Server を使用して SQL から FOR XML 句で SELECT ステートメントを使用してポーリング メッセージを受信](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md)です。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SQL Server データベースからデータの変更のポーリングに基づいたメッセージを受信します。 このオーケストレーションでアダプターが指定された select ステートメントの応答を受信、 **PollingStatement**プロパティをバインドします。 SELECT ステートメントの応答には、ファイルの場所に保存されます。 SQL Server データベースをポーリングするための一般的なオーケストレーションにが含まれます。  
  
-   受信図形と送信図形を SQL Server からメッセージを受信し、それぞれ、FILE ポートに送信します。  
  
-   一方向の受信ポートを SQL Server からメッセージを受信します。  
  
    > [!IMPORTANT]
    >  受信のポーリングのシナリオが常に設定する必要がありますの一方向の受信ポート。 双方向受信ポートが受信操作のサポートされていません。  
  
-   SQL Server データベースからフォルダーにポーリング応答を送信する一方向の送信ポートです。  
  
 サンプル オーケストレーションには、次のようになります。  
  
 ![SQL Server データベースをポーリングするためのオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/5cf65d53-d70d-444d-82f7-2561efcd9ee4.gif "5cf65d53-d70d-444d-82f7-2561efcd9ee4")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。 図形 列に表示名は、単に記載されているオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-設定**名前**に*ReceiveMessage*<br /><br /> -設定**アクティブ**に*は True。*|  
|SaveMessage|Send|-設定**名前**に*SaveMessage*|  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認してください。 ポート列に表示される名前は、オーケストレーションで表示されているポートの名前です。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|SQLReceivePort|-設定**識別子**に*SQLReceivePort*<br /><br /> -設定**型**に*SQLReceivePortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*受信*|  
|SaveMessagePort|-設定**識別子**に*SaveMessagePort*<br /><br /> -設定**型**に*SaveMessagePortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*送信*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表は、プロパティとアクション図形のメッセージを指定して、メッセージ、ポートにリンクを設定する必要があります、値を指定します。 図形 列に表示名は、既に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*受信*<br /><br /> -設定**操作**に*SQLReceivePort.XmlPolling.Request*|  
|SaveMessage|-設定**メッセージ**に*受信*<br /><br /> -設定**操作**に*SaveMessagePort.XmlPolling.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール アプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが、SQL Server データベースからメッセージをドロップ場所に場所を定義します。 これらのメッセージは、受信ポートの指定したポーリング ステートメントへの応答になります。  
  
    -   物理 Wcf-custom を定義するか、WCF SQL 一方向の受信ポートです。 このポートは、ポートを指定するポーリング ステートメントを使用して SQL Server データベースをポーリングします。 ポートを作成する方法については、次を参照してください。 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)です。 受信ポートのバインドのプロパティを指定することを確認してください。  
  
        > [!IMPORTANT]
        >  デザイン時のバインドのプロパティを指定した場合、この手順を実行する必要はありません。 このような場合は、WCF カスタムを作成または WCF SQL 受信ポート、必要なバインド プロパティを設定、によって作成されたバインド ファイルをインポートすることによって、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)です。  
  
        |プロパティのバインド|値|  
        |----------------------|-----------|  
        |**InboundOperationType**|これを設定するかどうかを確認**XmlPolling**です。|  
        |**PolledDataAvailableStatement**|SQL ステートメントを指定することを確認してください。 このトピックの次のように指定します。<br /><br /> `SELECT COUNT(*) FROM Employee`|  
        |**PollingStatement**|せず、同じステートメントを入力してください、 `xmlschema` 」の説明に従って、スキーマの生成中に指定した句[のBizTalkServerを使用してSQLからFORXML句でSELECTステートメントを使用してポーリングメッセージを受信](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md).<br /><br /> `SELECT Employee_ID ,Name ,Designation FROM Employee for xml auto`<br /><br /> **注:** 、SELECT ステートメントを含まないなお、`xmlschema`句。|  
        |**XmlStoredProcedureRootNodeName**|下の説明に従って、SELECT ステートメントの生成、応答スキーマに追加したルート ノードの名前を指定[SELECT ステートメントの応答メッセージのスキーマを生成する](#BKMK_RespSchema)です。 このトピックのこれを設定**ルート**です。|  
        |**XmlStoredProcedureRootNodeNamespace**|下の説明に従って、SELECT ステートメントの生成、応答スキーマのターゲット名前空間を指定[SELECT ステートメントの応答メッセージのスキーマを生成する](#BKMK_RespSchema)です。 このトピックのこれを設定`http://ForXmlPolling/namespace`です。|  
  
         異なるバインディングのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
        > [!NOTE]
        >  使用して受信操作の実行中に、トランザクション分離レベルとトランザクションのタイムアウトを構成することをお勧め、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 サービスを追加することで、Wcf-custom または WCF SQL の構成中に動作の受信ポートを行うことができます。 サービスの動作を追加する方法については、次を参照してください。[トランザクション分離レベルの構成と SQL を使用したトランザクションのタイムアウト](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)です。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 SQL Server データベースからメッセージを受信する BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。
  
 この段階で確認します。  
  
-   Wcf-custom または WCF SQL 一方向受信ポートを指定されたステートメントを使用して SQL Server データベースをポーリングする、 **PollingStatement**バインディング プロパティが実行されています。  
  
-   SQL Server からメッセージを受信する FILE 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後、次の一連のアクションが実行と同じ順序で。  
  
-   アダプターの実行、 **PolledDataAvailableStatement**従業員のテーブルが表示され、テーブルにポーリングのレコードがあることを決定します。  
  
-   アダプターは、ポーリング ステートメントを実行し、SQL Server データベースからポーリング メッセージを受信します。 ポーリング ステートメントは、FOR XML 句を伴う SELECT ステートメントから構成されているために、アダプターによって受信されたポーリング メッセージは、次のようになります。  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <Root xmlns="http://ForXmlPolling/namespace">  
      <Employee Employee_ID="10765" Name="John" Designation="Tester" xmlns="" />   
      <Employee Employee_ID="10766" Name="Sam" Designation="Manager" xmlns="" />   
      .....  
      .....  
    </Root>  
    ```  
  
     含む SELECT ステートメントを実行することによって生成されると、同じスキーマでポーリング メッセージを受信することに注意してください、 **xmlschema**句。 ルート ノードと名前空間は、の値として指定したものと同じであるにも注意してください**XmlStoredProcedureRootNodeName**と**XmlStoredProcedureRootNodeNamespace**それぞれのプロパティをバインドします。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]はポーリングから受信ポートを明示的に無効にするまで引き続き、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)です。
  
## <a name="see-also"></a>参照  
 [BizTalk Server と SQL アダプタを使用して SQL サーバーにポーリング](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)