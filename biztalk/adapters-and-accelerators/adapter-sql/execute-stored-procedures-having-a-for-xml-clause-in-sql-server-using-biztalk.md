---
title: "BizTalk Server を使用して SQL Server での FOR XML 句を持つストアド プロシージャを実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d8fe927-90bf-48fc-a418-63b920b409ed
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c1b69c522f01f2561ea8145c11dec3e36b5cd4e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk-server"></a>BizTalk Server を使用して SQL Server での FOR XML 句を持つストアド プロシージャを実行します。
SQL SELECT ステートメントでは、行セットではなく XML としてクエリ結果を返す FOR XML 句を持つことができます。 また、ストアド プロシージャを FOR XML 句を伴う SELECT ステートメントを持つことができます。 [FOR XML (SQL Server)](https://msdn.microsoft.com/library/ms178107.aspx)の詳細についてはします。
  
 WCF ベースを使用することができます[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]などを実行するストアド プロシージャです。  
  
> [!IMPORTANT]
>  「ネイティブ」の SQL アダプターで使用可能な[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]FOR XML 句を SELECT ステートメントの一部として保持するストアド プロシージャが必要です。 このようなストアド プロシージャを使用するには、WCF ベースで[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ストアド プロシージャの定義に変更を加えずにします。  
>   
>  以前のバージョンに用意されている 'native' の SQL アダプターを使用して生成されたスキーマを常に使用することができます[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。 [WCF-SQL アダプターを使用して FOR XML クエリ](http://go.microsoft.com/fwlink/?LinkId=223428)(http://go.microsoft.com/fwlink/?LinkId=223428)。  
  
## <a name="how-to-invoke-stored-procedures-with-for-xml-clause"></a>FOR XML 句を使用してストアド プロシージャを呼び出す方法  
 SQL Server Management Studio または SQL アダプターで使用可能なを使用して FOR XML 句を使用してストアド プロシージャを呼び出した場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]出力は次の xml メッセージの形式でします。 WCF ベースでこれらの手順を使用する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、出力メッセージのスキーマをする必要があります。 WCF ベース[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]FOR XML 句を使用してストアド プロシージャを実行した後、SQL Server からの応答メッセージを受信中にこのスキーマが必要です。 このストアド プロシージャを呼び出す要求メッセージがアダプター自体によって生成されることに注意してください。  
  
 応答メッセージのスキーマとは別で、WCF ベースを使用して FOR XML 句を使用してストアド プロシージャを呼び出すための特定のタスクを実行する必要がありますも[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
1.  FOR XML 句を使用してストアド プロシージャの応答メッセージのスキーマを生成します。 使用可能な「ネイティブ」の SQL アダプターによって生成される応答のスキーマがあれば[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、この手順をスキップすることができます。  
  
2.  BizTalk プロジェクトを作成し、生成されたスキーマをプロジェクトに追加します。  
  
3.  WCF ベースを使用して FOR XML 句を使用して、ストアド プロシージャのスキーマを生成[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 これは、ストアド プロシージャを呼び出す SQL Server にアダプターを送信する要求メッセージのスキーマを提供します。  
  
4.  SQL Server からメッセージを送受信する BizTalk プロジェクトでメッセージを作成します。 要求メッセージは、アダプターによって生成された要求メッセージのスキーマに準拠している必要があります。 応答メッセージは、または SQL Server Management Studio での FOR XML 句を使用してストアド プロシージャを実行することによって、「ネイティブ」の SQL アダプターを使用するか取得した応答メッセージのスキーマに準拠する必要があります。  
  
5.  SQL Server データベースにストアド プロシージャを呼び出すオーケストレーションを作成します。  
  
6.  構築し、BizTalk プロジェクトを展開します。  
  
7.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
8.  BizTalk アプリケーションを起動します。  
  
##  <a name="BKMK_RespSchema"></a>ストアド プロシージャの応答メッセージのスキーマを生成します。  
  
> [!NOTE]
>  使用可能な SQL アダプターによって生成される応答のスキーマがある場合は、この手順を実行する必要はありません[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
 ストアド プロシージャで応答メッセージのスキーマを生成するには、ストアド プロシージャで SELECT ステートメントがある提供される、`xmlschema`句、`for xml`句。 このトピックでは指定された従業員 ID の従業員の詳細情報を取得する GET_EMP_DETAILS_FOR_XML が格納されている手順に従いますお ストアド プロシージャを実行することによって、スキーマを取得するには、SELECT ステートメントは、次のようになります。  
  
```  
SELECT [Employee_ID] ,[Name] ,[DOJ] ,[Designation] ,[Job_Description] ,[Photo] ,cast([Rating] as varchar(100)) as Rating ,[Salary] ,[Last_Modified] ,[Status] ,[Address]   
FROM [Adapt_Doc].[dbo].[Employee] for xml auto, xmlschema  
```  
  
 応答メッセージのスキーマを取得するこのストアド プロシージャを実行します。 ストアド プロシージャからの応答には、ストアド プロシージャの実行からのデータと同様に、スキーマが含まれていることを注意してください。 応答からスキーマをコピーし、テキスト パッドに保存する必要があります。 この例では、名前を指定できますと、このスキーマ**ResponseSchema.xsd**です。 BizTalk プロジェクトを作成する必要が今すぐ[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]し、このスキーマをプロジェクトに追加します。  
  
> [!IMPORTANT]
>  削除するかどうかを確認、`xmlschema`句のスキーマを生成するストアド プロシージャを実行した後です。 失敗した場合に、最後に、BizTalk によってストアド プロシージャを実行するときに、応答メッセージのスキーマを再生成されます。 削除する必要があります xml として応答メッセージを取得する、`xmlschema`句。  
  
#### <a name="to-add-the-schema-to-a-biztalk-project"></a>BizTalk プロジェクトにスキーマを追加するには  
  
1.  BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。  
  
2.  BizTalk プロジェクトにストアド プロシージャの生成、応答スキーマを追加します。 ソリューション エクスプ ローラーで BizTalk プロジェクトを右クリックし、**追加**、クリックして**既存項目の**します。 [既存項目の追加] ダイアログ ボックスをクリックして、スキーマを保存した場所に移動**追加**です。  
  
3.  内のスキーマを開く[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]次の変更を加えます。  
  
    1.  スキーマにノードを追加し、新しく追加されたこのノードの下の既存のルート ノードを移動します。 ルート ノードに名前を指定します。 このトピックの名前を変更するルート ノード**ルート**です。  
  
    2.  ストアド プロシージャの生成、応答スキーマは、sqltypes.xsd を参照します。 Sqltypes.xsd スキーマから取得できます[http://go.microsoft.com/fwlink/?LinkId=131087](http://go.microsoft.com/fwlink/?LinkId=131087)です。 Sqltypes.xsd スキーマを BizTalk プロジェクトに追加します。  
  
    3.  ストアド プロシージャの生成、スキーマ内の値を変更する`import schemaLocation`以下にします。  
  
        ```  
        import schemaLocation=”sqltypes.xsd”  
        ```  
  
         これを行う sqltypes.xsd スキーマは、BizTalk プロジェクトに既に追加されたためです。  
  
    4.  スキーマのターゲット名前空間を指定します。 クリックして、 **\<スキーマ\>**ノード、プロパティ ウィンドウで、名前空間を指定し、 **Target Namespace**プロパティ。 このトピックの付与と名前空間`http://ForXmlStoredProcs/namespace`です。  
  
## <a name="generating-schema-for-the-request-message-to-invoke-the-stored-procedure"></a>ストアド プロシージャを呼び出す要求メッセージのスキーマを生成します。  
 使用することが要求メッセージのスキーマを生成する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]で BizTalk プロジェクトから[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 このトピックでは、GET_EMP_DETAILS_FOR_XML ストアド プロシージャのスキーマを生成します。 使用してスキーマを生成する方法の詳細についての[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を参照してください[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)です。  
  
> [!IMPORTANT]
>  プロシージャからのみを選択して、スキーマを生成する必要があります、**プロシージャ**内のノード[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 先に生成したスキーマは、オーケストレーションのメッセージに求められる "型" を記述します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 今すぐ、オーケストレーションのメッセージを作成して、前の手順で生成したスキーマにリンクします。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**です。  
  
2.  まだ開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。  
  
3.  オーケストレーション ビューで右クリック**メッセージ**、クリックして**新しいメッセージ**です。  
  
4.  新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。  
  
5.  **プロパティ**のウィンドウ、 **Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Request`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *ForXMLProcedure.Procedure_dbo です。GET_EMP_DETAILS_FOR_XML*ForXMLProcedure は、BizTalk プロジェクトの名前。 Procedure_dbo は GET_EMP_DETAILS_FOR_XML プロシージャを呼び出すことの生成スキーマです。|  
  
6.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Response`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *ForXMLProcedure.ResponseSchema*ResponseSchema としてストアド プロシージャを実行することによって生成される応答スキーマの名前下に説明[ストアド プロシージャ用の応答メッセージのスキーマを生成する](#BKMK_RespSchema)です。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の SQL Server のストアド プロシージャを実行します。 このオーケストレーションでの要求メッセージを削除する受信場所が、定義されています。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]このメッセージを消費し、SQL Server に渡します。 SQL Server からの応答は、別の場所に保存されます。 送信を含めるし、受信図形を SQL Server にメッセージを送信し、それぞれ、応答を受信する必要があります。 プロシージャを呼び出すためのサンプル オーケストレーションには、次のようになります。  
  
 ![ストアド プロシージャを呼び出すオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/eac6e8b6-f0f4-44af-8218-03ca3864b267.gif "eac6e8b6-f0f4-44af-8218-03ca3864b267")  
  
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
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*MessageIn.FOR_XML です。要求*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.FOR_XML です。要求*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.FOR_XML です。応答*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*ResponseOut.FOR_XML です。要求*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 [オーケストレーション] ペインで以前に作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール アプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。 BizTalk オーケストレーションは、要求メッセージを消費し、SQL Server データベースに送信します。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが SQL Server データベースからの応答を含む応答メッセージをドロップする場所に場所を定義します。  
  
    -   SQL Server データベースにメッセージを送信する物理 Wcf-custom または WCF-SQL 送信ポートを定義します。 送信ポートを作成する方法については、次を参照してください。 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)です。
  
         送信ポートでアクションを指定することもあります。 FOR XML 句を含む手順では、次の形式でアクションを設定する必要があります。  
  
        ```  
        XmlProcedure/<schema_name>/<procedure_name>  
        ```  
  
         そのため、GET_EMP_DETAILS_FOR_XML プロシージャを実行して、このトピックのアクションになります。  
  
        ```  
        XmlProcedure/dbo/GET_EMP_DETAILS_FOR_XML  
        ```  
  
         設定アクションの詳細については、次を参照してください。 [SQL アダプタの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)です。
  
         FOR XML 句を使用してストアド プロシージャを実行するときに、次のバインド プロパティを設定することもあります。  
  
        |バインディングのプロパティ名|これを設定します。|  
        |---------------------------|-----------------|  
        |XmlStoredProcedureRootNodeName|下の説明に従って、ストアド プロシージャの生成、応答スキーマに追加したルート ノードの名前を指定[ストアド プロシージャ用の応答メッセージのスキーマを生成する](#BKMK_RespSchema)です。 このトピックのこれを設定**ルート**です。|  
        |XmlStoredProcedureRootNodeNamespace|下の説明に従って、ストアド プロシージャの生成、応答スキーマのターゲット名前空間を指定[ストアド プロシージャ用の応答メッセージのスキーマを生成する](#BKMK_RespSchema)です。 このトピックのこれを設定`http://ForXmlStoredProcs/namespace`です。|  
  
         バインドのプロパティの値を指定する方法の詳細については、次を参照してください。 [SQL アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)です。  
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] (着信) の受信ポートを (発信) の送信ポートを作成または管理コンソールです。 詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)です。
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 SQL Server データベースでプロシージャを呼び出す BizTalk アプリケーションを開始する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   SQL Server データベースにメッセージを送信する Wcf-custom または WCF-SQL 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後、ファイルに要求メッセージをドロップする必要がありますの受信場所。 要求メッセージのスキーマを使用して生成する手順については、要求スキーマに従う必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 たとえばを呼び出す GET_EMP_DETAILS_FOR XML 要求メッセージには。  
  
```  
<GET_EMP_DETAILS_FOR_XML xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo">  
  <emp_id>10765</emp_id>  
</GET_EMP_DETAILS_FOR_XML>  
```  
  
 参照してください[プロシージャと関数のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)を使用して、データベースの SQL Server でプロシージャを呼び出すための要求メッセージ スキーマの詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
 オーケストレーションはメッセージを使用して、SQL Server データベースに送信します。 SQL Server データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、上記の要求メッセージ用の SQL Server データベースからの応答には。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Root xmlns="http://ForXmlStoredProcs/namespace">  
  <Adapt_Doc.dbo.Employee Employee_ID="10765" Name="John" Designation="asdfaf" Salary="3434.00" Last_Modified="AAAAAAAANso=" Status="0" xmlns="" />  
</Root>  
```  
  
 ストアド プロシージャを実行することによって生成されたものと、同じスキーマで、応答を受信したことに注意してください。 ルート ノードと名前空間は、の値として指定したものと同じであるにも注意してください**XmlStoredProcedureRootNodeName**と**XmlStoredProcedureRootNodeNamespace**それぞれのプロパティをバインドします。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)です。  
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用して BizTalk アプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)