---
title: BizTalk Server を使用して SQL から FOR XML 句で SELECT ステートメントを使用してポーリング メッセージを受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65c629c1-9ef7-4aa1-8ec1-f94a3cb41cb0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf980dc092f1142001f0df232595c54a997f4734
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368539"
---
# <a name="receive-polling-messages-using-select-statements-with-for-xml-clause-from-sql-using-biztalk-server"></a>BizTalk Server を使用して SQL から FOR XML 句で SELECT ステートメントを使用してポーリング メッセージを受信します。
構成することができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SELECT ステートメントまたは FOR XML 句を含むストアド プロシージャを使用して SQL Server テーブルまたはビューの定期的なデータ変更メッセージを受信します。 これらのステートメントは、データベースをポーリングするアダプターを実行するポーリング ステートメントとして指定できます。 ポーリング ステートメントには、SELECT ステートメントまたはストアド プロシージャを返す結果セットを使用できます。  
  
 アダプターがポーリングをサポートする方法の詳細については、次を参照してください。[のポーリング サポート](https://msdn.microsoft.com/library/dd788416.aspx)します。 ポーリング操作用の SOAP メッセージの構造については、次を参照してください。 [Polling 操作と TypedPolling 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)します。 SQL [FOR XML 句](https://docs.microsoft.com/sql/relational-databases/xml/for-xml-sql-server)について詳しく説明します。
  
> [!NOTE]
>  このトピックでは、使用する方法を示します、 **XmlPolling**ポーリング メッセージを受信する操作を受信します。 **XmlPolling**操作は、SELECT ステートメントまたは FOR XML 句を含むストアド プロシージャを使用して SQL Server データベースをポーリングするために使用します。 メッセージ、 **XmlPolling**操作には、SQL Server Management Studio で、SELECT ステートメントまたはストアド プロシージャを実行して受信した xml メッセージが含まれています。  
> 
>  さまざまな種類のポーリング メッセージを受信するのにアダプターを使用することもできます。  
> 
> - 厳密に型指定されたポーリング メッセージを取得するには、ポーリング操作を使用する必要があります。 詳細については、次を参照してください。[を使用して BizTalk Server によって SQL Server からのデータ変更メッセージの受信のポーリングに基づいた](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)します。  
>   -   使用する必要がありますを厳密に型指定されたポーリング メッセージを取得する場合、 **TypedPolling**操作。 使用することも必要があります、 **TypedPolling**工程に 1 つの BizTalk アプリケーションで複数の操作をポーリングします。 手順を実行する方法について**TypedPolling**操作を参照してください[BizTalk Server を使用して SQL Server からデータ変更のポーリングに基づいたメッセージを受信厳密に型指定された](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md)します。  
> 
> [!IMPORTANT]
>  1 つの BizTalk アプリケーションでは、複数のポーリング操作を必要するかどうか、指定する必要あります、 **InboundID**接続して一意の URI の一部として接続プロパティです。 一意接続 URI を複数作成できます、同じデータベースまたはデータベースでも同じテーブルをポーリングするポートを受信します。 詳細については、次を参照してください。[受信ポーリング メッセージ間で複数受信ポートから BizTalk Server を使用して SQL](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)します。  
  
## <a name="how-this-topic-demonstrates-polling"></a>このトピックでポーリングしていますか  
 示すために、このトピックでどのように[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]メッセージの変更データの受信をサポート、SQL Server データベースをポーリングする FOR XML 句と SELECT ステートメントを使用します。 SQL Server Management Studio で、このようなステートメントを呼び出すと、出力は xml メッセージの形式です。 このようなステートメントを使用してを SQL Server データベースをポーリングするには、応答の xml メッセージのスキーマがあります。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] FOR XML 句を伴う SELECT ステートメントを実行した後でポーリング メッセージを受信するには、このスキーマが必要です。 そのため、FOR XML 句と SELECT ステートメントを使用して、SQL Server データベースをポーリングする、次の一連のタスクを実行する必要があります。  
  
1.  FOR XML 句を含む SELECT ステートメントの XML 応答メッセージのスキーマを生成します。  
  
2.  BizTalk プロジェクトを作成し、生成されたスキーマをプロジェクトに追加します。  
  
3.  SQL Server データベースから XML 応答メッセージを受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
4.  SQL Server データベースからメッセージを受信して、フォルダーに保存するオーケストレーションを作成します。  
  
5.  ビルドし、BizTalk プロジェクトを配置します。  
  
6.  BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
    > [!IMPORTANT]
    >  受信のポーリングのシナリオは、Wcf-custom の一方向常に構成する必要があります。 または WCF SQL 受信ポート。 Wcf-custom または WCF-SQL の双方向受信ポートの受信操作はサポートされていません。  
  
7.  BizTalk アプリケーションを起動します。  
  
##  <a name="BKMK_RespSchema"></a> SELECT ステートメントの応答メッセージのスキーマを生成します。  
 SELECT ステートメントの応答メッセージのスキーマを生成するには含めることによって、`xmlschema`句、`for xml`句。 このトピックでは、指定された従業員 ID の従業員の詳細を取得するのに SELECT ステートメントを使用します スキーマを取得するには、SELECT ステートメントを実行することによって、次のように、SELECT ステートメントを記述する必要があります。  
  
```  
SELECT Employee_ID ,Name ,Designation FROM Employee for xml auto, xmlschema  
```  
  
 応答メッセージのスキーマを取得する次の SELECT ステートメントを実行します。 スキーマを保存します。 BizTalk プロジェクトを作成する必要が今すぐ[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]し、このスキーマをプロジェクトに追加します。 このスキーマを名前をこの例では、 **PollingResponse.xsd**します。  
  
> [!IMPORTANT]
>  削除するかどうかを確認、`xmlschema`スキーマを生成する SELECT ステートメントを実行した後の句。 XmlPolling 操作の一環として BizTalk からの SELECT ステートメントを最後に実行するときにこれを行うに失敗した場合は、応答メッセージのスキーマを再生成されます。 削除する必要があります xml として応答メッセージを取得するため、`xmlschema`句。  
  
#### <a name="to-add-the-schema-to-a-biztalk-project"></a>スキーマを BizTalk プロジェクトに追加するには  
  
1. BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。  
  
2. BizTalk プロジェクトにストアド プロシージャ用に生成した応答スキーマを追加します。 ソリューション エクスプ ローラーで BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**既存項目の**します。 既存項目の追加 ダイアログ ボックスで、スキーマとクリックを保存した場所に移動します。**追加**します。  
  
3. スキーマを開き[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]次の変更を行います。  
  
   1.  スキーマにノードを追加し、新しく追加されたこのノードの下の既存のルート ノードを移動します。 ルート ノードに名前を付けます。 このトピックでは、名前を変更するルート ノード**ルート**します。  
  
   2.  SELECT ステートメントの生成、応答スキーマを sqltypes.xsd を参照します。 Sqltypes.xsd スキーマから取得できます[ http://go.microsoft.com/fwlink/p/?LinkId=131087](http://go.microsoft.com/fwlink/p/?LinkId=131087)します。 Sqltypes.xsd スキーマを BizTalk プロジェクトに追加します。  
  
   3.  SELECT ステートメントの生成、スキーマ内の値を変更`import schemaLocation`以下。  
  
       ```  
       import schemaLocation=”sqltypes.xsd”  
       ```  
  
        Sqltypes.xsd スキーマは、BizTalk プロジェクトに既に追加されたために実行します。  
  
   4.  スキーマのターゲットの名前空間を提供します。 をクリックして、 **\<スキーマ\>** ノード プロパティ ウィンドウで名前空間を指定し、 **Target Namespace**プロパティ。 このトピックでは、名前空間を与える`http://ForXmlPolling/namespace`します。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 スキーマが生成されるは、BizTalk プロジェクトのオーケストレーションからメッセージをリンクする必要があります。  
  
 このトピックでは、SQL Server データベースからメッセージを受信する 1 つのメッセージを作成する必要があります。  
  
 メッセージを作成し、スキーマにリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。  
  
2.  開いていない場合は、BizTalk プロジェクトのオーケストレーション ビュー ウィンドウを開きます。 をクリックして**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
3.  **オーケストレーション**、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。  
  
4.  新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  
  
5.  **プロパティ**ウィンドウ **[message_1]** 次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**PollingMessage**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選択と*ForXMLPolling.PollingResponse*ここで、 *ForXMLPolling* BizTalk プロジェクトの名前を指定します。 *PollingResponse* 」の説明に従って SELECT ステートメントの実行によって生成される応答スキーマの名前を指定[と FOR XML 句 BizTalk Server を使用した SQL から SELECT ステートメントを使用してポーリング メッセージを受信](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md)します。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SQL Server データベースからのポーリング ベースのデータ変更メッセージを受信します。 このオーケストレーションでの指定した select ステートメントの応答を受信、 **PollingStatement**プロパティをバインドします。 SELECT ステートメントの応答は、ファイルの場所に保存されます。 SQL Server データベースをポーリングするための一般的なオーケストレーションが含まれます。  
  
- 受信図形と送信図形を SQL Server からメッセージを受信し、それぞれ、ファイルのポートに送信します。  
  
- 一方向の受信ポートを SQL Server からメッセージを受信します。  
  
  > [!IMPORTANT]
  >  常に設定する必要があります、ポーリングの受信シナリオの一方向の受信ポート。 双方向受信ポートは受信操作のサポートされていません。  
  
- SQL Server データベースからフォルダーにポーリング応答を送信する一方向の送信ポート。  
  
  サンプル オーケストレーションでは、次の項目に似ています。  
  
  ![SQL Server データベースをポーリングするためのオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/5cf65d53-d70d-444d-82f7-2561efcd9ee4.gif "5cf65d53-d70d-444d-82f7-2561efcd9ee4")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 図形の列に示した名前は、単に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-設定**名前**に*ReceiveMessage*<br /><br /> -設定**アクティブ**に*は True。*|  
|SaveMessage|Send|-設定**名前**に*SaveMessage*|  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認します。 ポート列に示した名前は、オーケストレーションで表示されているポートの名前です。  
  
|Port|[プロパティ]|  
|----------|----------------|  
|SQLReceivePort|-設定**識別子**に*SQLReceivePort*<br /><br /> -設定**型**に*SQLReceivePortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*受信*|  
|SaveMessagePort|-設定**識別子**に*SaveMessagePort*<br /><br /> -設定**型**に*SaveMessagePortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*送信*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表では、プロパティとアクション図形のメッセージを指定して、メッセージ ポートにリンクを設定する必要があります、値を指定します。 図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*受信*<br /><br /> -設定**操作**に*SQLReceivePort.XmlPolling.Request*|  
|SaveMessage|-設定**メッセージ**に*受信*<br /><br /> -設定**操作**に*SaveMessagePort.XmlPolling.Request*|  
  
 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、次を参照してください。[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)します。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールにアプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル。基本的な BizTalk アプリケーション展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)します。
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーション、SQL Server データベースからメッセージをドロップできる場所での場所を定義します。 これらのメッセージは、受信ポートの指定したポーリング ステートメントへの応答になります。  
  
  - WCF-SQL の一方向受信ポートまたは物理 Wcf-custom を定義します。 このポートは、ポートを指定するポーリング ステートメントを使用して SQL Server データベースをポーリングします。 ポートを作成する方法については、次を参照してください。 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)します。 受信ポートのバインドのプロパティを指定することを確認します。  
  
    > [!IMPORTANT]
    >  デザイン時のバインドのプロパティが指定されている場合は、この手順を実行する必要はありません。 このような場合は、WCF カスタムを作成または WCF-SQL によって作成されたバインド ファイルをインポートすることによって、必要なバインドのプロパティを設定すると、ポートを受信する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)します。  
  
    |プロパティのバインド|値|  
    |----------------------|-----------|  
    |**InboundOperationType**|これを設定することを確認**XmlPolling**します。|  
    |**PolledDataAvailableStatement**|SQL ステートメントを指定することを確認します。 このトピックでは、次のように指定します。<br /><br /> `SELECT COUNT(*) FROM Employee`|  
    |**PollingStatement**|なし、同じステートメントを入力してください、 `xmlschema` 」の説明に従って、スキーマの生成中に指定されている句、[と FOR XML 句 BizTalk Serverを使用したSQLからSELECTステートメントを使用してポーリングメッセージを受信](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md).<br /><br /> `SELECT Employee_ID ,Name ,Designation FROM Employee for xml auto`<br /><br /> **注:** SELECT ステートメントは含まれていない、`xmlschema`句。|  
    |**XmlStoredProcedureRootNodeName**|トピックに示すように、SELECT ステートメント用に生成した応答スキーマに追加したルート ノードの名前を指定[SELECT ステートメントの応答メッセージのスキーマを生成する](#BKMK_RespSchema)します。 このトピックに設定**ルート**します。|  
    |**XmlStoredProcedureRootNodeNamespace**|トピックに示すように、SELECT ステートメント用に生成した応答スキーマのターゲット名前空間を指定[SELECT ステートメントの応答メッセージのスキーマを生成する](#BKMK_RespSchema)します。 このトピックに設定`http://ForXmlPolling/namespace`します。|  
  
     異なるバインディング プロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。  
  
    > [!NOTE]
    >  使用して受信操作の実行中に、トランザクション分離レベルとトランザクションのタイムアウトを構成することをお勧めします。、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 ように、サービスを追加することで、Wcf-custom または WCF SQL を構成するときに動作の受信ポートを行うことができます。 サービスの動作を追加する方法については、次を参照してください。[トランザクション分離レベルの構成と SQL を使用したトランザクション タイムアウト](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)します。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 SQL Server データベースからメッセージを受信する BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを開始する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)します。
  
 この段階で、ことを確認します。  
  
-   Wcf-custom または WCF SQL 一方向受信ポートで、指定されたステートメントを使用して SQL Server データベースをポーリングします**PollingStatement**プロパティ、バインドが実行されています。  
  
-   SQL Server からメッセージを受信する、ファイル送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後、次の一連のアクションに、同じシーケンスを実行します。  
  
-   アダプターの実行、 **PolledDataAvailableStatement**従業員テーブルし、テーブルがポーリングのレコードを決定します。  
  
-   アダプターは、ポーリング ステートメントを実行し、SQL Server データベースからポーリング メッセージを受信します。 ポーリング ステートメントが FOR XML 句を使用した SELECT ステートメントで構成されているために、ポーリング メッセージをアダプターによって受信は、次のようになります。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Root xmlns="http://ForXmlPolling/namespace">  
      <Employee Employee_ID="10765" Name="John" Designation="Tester" xmlns="" />   
      <Employee Employee_ID="10766" Name="Sam" Designation="Manager" xmlns="" />   
      .....  
      .....  
    </Root>  
    ```  
  
     含む SELECT ステートメントを実行することによって生成されると、同じスキーマでポーリング メッセージを受信することに注意してください、 **xmlschema**句。 なお、ルート ノードと名前空間は、値として指定したものと同じである**XmlStoredProcedureRootNodeName**と**XmlStoredProcedureRootNodeNamespace**それぞれバインドのプロパティ。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ポーリングからの受信ポートを明示的に無効にするまでは引き続き、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定、ファイルからインポートできます。 バインド ファイルの詳細については、次を参照してください。[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)します。
  
## <a name="see-also"></a>参照  
 [BizTalk Server を SQL アダプターを使用して SQL Server をポーリング](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)