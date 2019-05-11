---
title: BizTalk Server を使用して SQL Server での FOR XML 句を含むストアド プロシージャの実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d8fe927-90bf-48fc-a418-63b920b409ed
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d68473929852b8a57acb25317656fd52a38880b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369643"
---
# <a name="execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk-server"></a>BizTalk Server を使用して SQL Server での FOR XML 句を含むストアド プロシージャを実行します。
SQL SELECT ステートメントには、FOR XML 句を XML として行セットではなく、クエリの結果を返すことができます。 ストアド プロシージャは FOR XML 句を使用した SELECT ステートメントをすることもできます。 [FOR XML (SQL Server)](https://msdn.microsoft.com/library/ms178107.aspx)の詳細。
  
 WCF ベースを使用する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ストアド プロシージャなどを実行します。  
  
> [!IMPORTANT]
>  「ネイティブ」の SQL アダプターで使用可能な[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]に SELECT ステートメントの一部として、FOR XML 句を指定のストアド プロシージャが必要です。 このようなストアド プロシージャを使用するには、WCF ベースで[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ストアド プロシージャの定義に変更を加えずにします。  
> 
>  以前のバージョンの指定された 'native' の SQL アダプターを使用して生成されたスキーマを使用することが常に[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、次を参照してください。 [WCF-SQL アダプターを使用して FOR XML クエリ](http://go.microsoft.com/fwlink/?LinkId=223428)(<http://go.microsoft.com/fwlink/?LinkId=223428>)。  
  
## <a name="how-to-invoke-stored-procedures-with-for-xml-clause"></a>FOR XML 句を使用したストアド プロシージャを呼び出す方法  
 SQL Server Management Studio または SQL アダプターで使用可能なを使用して FOR XML 句を使用してストアド プロシージャを呼び出すと[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]出力は、xml メッセージの形式。 WCF ベースでこれらの手順を使用する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、出力メッセージのスキーマがあります。 WCF ベース[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]FOR XML 句を使用してストアド プロシージャを実行した後、SQL Server から応答メッセージを受信中にこのスキーマが必要です。 このストアド プロシージャを呼び出す要求メッセージがアダプター自体によって生成されることに注意してください。  
  
 応答メッセージのスキーマとは別で、WCF ベースを使用して FOR XML 句でストアド プロシージャを呼び出す特定のタスクを実行する必要がありますも[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
1. FOR XML 句を使用してストアド プロシージャの応答メッセージのスキーマを生成します。 使用可能な「ネイティブ」の SQL アダプターによって生成される応答のスキーマがあれば[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、この手順をスキップすることができます。  
  
2. BizTalk プロジェクトを作成し、生成されたスキーマをプロジェクトに追加します。  
  
3. WCF ベースを使用して FOR XML 句を使用して、ストアド プロシージャのスキーマを生成[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 これは、アダプター ストアド プロシージャを呼び出すには、SQL Server に送信する要求メッセージのスキーマを提供します。  
  
4. SQL Server からメッセージを送受信する BizTalk プロジェクトでは、メッセージを作成します。 要求メッセージは、アダプターによって生成された要求メッセージのスキーマに準拠している必要があります。 応答メッセージは、または SQL Server Management Studio での FOR XML 句を使用してストアド プロシージャを実行することによって、「ネイティブ」の SQL アダプターを使用して取得した応答メッセージのスキーマに準拠する必要があります。  
  
5. SQL Server データベースでストアド プロシージャを呼び出すオーケストレーションを作成します。  
  
6. ビルドし、BizTalk プロジェクトを配置します。  
  
7. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
8. BizTalk アプリケーションを起動します。  
  
##  <a name="BKMK_RespSchema"></a> ストアド プロシージャの応答メッセージのスキーマを生成します。  
  
> [!NOTE]
>  使用可能な SQL アダプターによって生成される応答のスキーマがある場合は、この手順を実行する必要はありません[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  
  
 ストアド プロシージャで応答メッセージのスキーマを生成するには、ストアド プロシージャの SELECT ステートメントがある提供される、`xmlschema`句、`for xml`句。 このトピックで指定された従業員 ID の従業員の詳細情報を取得する GET_EMP_DETAILS_FOR_XML ストアド プロシージャを使用します ストアド プロシージャを実行することによって、スキーマを取得するには、は、SELECT ステートメントは、次のようになります。  
  
```  
SELECT [Employee_ID] ,[Name] ,[DOJ] ,[Designation] ,[Job_Description] ,[Photo] ,cast([Rating] as varchar(100)) as Rating ,[Salary] ,[Last_Modified] ,[Status] ,[Address]   
FROM [Adapt_Doc].[dbo].[Employee] for xml auto, xmlschema  
```  
  
 応答メッセージのスキーマを取得するこのストアド プロシージャを実行します。 ストアド プロシージャからの応答には、ストアド プロシージャの実行からのデータだけでなく、スキーマが含まれているに注意してください。 応答からスキーマをコピーし、テキストのパッドに保存する必要があります。 このスキーマを名前をこの例では、 **ResponseSchema.xsd**します。 BizTalk プロジェクトを作成する必要が今すぐ[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]し、このスキーマをプロジェクトに追加します。  
  
> [!IMPORTANT]
>  削除するかどうかを確認、`xmlschema`スキーマを生成するストアド プロシージャを実行した後の句。 最後に、BizTalk からストアド プロシージャを実行するときにこれを行うに失敗した場合は、応答メッセージのスキーマを再度生成されます。 削除する必要があります xml として応答メッセージを取得するため、`xmlschema`句。  
  
#### <a name="to-add-the-schema-to-a-biztalk-project"></a>スキーマを BizTalk プロジェクトに追加するには  
  
1. BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。  
  
2. BizTalk プロジェクトにストアド プロシージャ用に生成した応答スキーマを追加します。 ソリューション エクスプ ローラーで BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**既存項目の**します。 既存項目の追加 ダイアログ ボックスで、スキーマとクリックを保存した場所に移動します。**追加**します。  
  
3. スキーマを開き[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]次の変更を行います。  
  
   1.  スキーマにノードを追加し、新しく追加されたこのノードの下の既存のルート ノードを移動します。 ルート ノードに名前を付けます。 このトピックでは、名前を変更するルート ノード**ルート**します。  
  
   2.  ストアド プロシージャの生成、応答スキーマを sqltypes.xsd を参照します。 Sqltypes.xsd スキーマから取得できます[ http://go.microsoft.com/fwlink/?LinkId=131087](http://go.microsoft.com/fwlink/?LinkId=131087)します。 Sqltypes.xsd スキーマを BizTalk プロジェクトに追加します。  
  
   3.  ストアド プロシージャの生成、スキーマ内の値を変更`import schemaLocation`以下。  
  
       ```  
       import schemaLocation=”sqltypes.xsd”  
       ```  
  
        Sqltypes.xsd スキーマは、BizTalk プロジェクトに既に追加されたために実行します。  
  
   4.  スキーマのターゲットの名前空間を提供します。 をクリックして、 **\<スキーマ\>** ノード プロパティ ウィンドウで名前空間を指定し、 **Target Namespace**プロパティ。 このトピックでは、名前空間を与える`http://ForXmlStoredProcs/namespace`します。  
  
## <a name="generating-schema-for-the-request-message-to-invoke-the-stored-procedure"></a>ストアド プロシージャを呼び出す要求メッセージのスキーマを生成します。  
 使用することが要求メッセージのスキーマを生成する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]で BizTalk プロジェクトから[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。 このトピックでは、GET_EMP_DETAILS_FOR_XML ストアド プロシージャのスキーマを生成します。 使用してスキーマを生成する方法の詳細についての[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を参照してください[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)します。  
  
> [!IMPORTANT]
>  プロシージャからのみを選択して、スキーマを生成する必要があります、**プロシージャ**ノード[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 先に生成したスキーマは、オーケストレーションのメッセージに求められる "型" を記述します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 オーケストレーションでは、メッセージを作成し、前の手順で生成したスキーマにリンクする必要がありますようになりました。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。  
  
2.  開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
3.  オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  
  
4.  新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  
  
5.  **プロパティ**のウィンドウ、 **Message_1**次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Request`」と入力します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *ForXMLProcedure.Procedure_dbo します。GET_EMP_DETAILS_FOR_XML*ForXMLProcedure は、BizTalk プロジェクトの名前です。 Procedure_dbo は GET_EMP_DETAILS_FOR_XML プロシージャを呼び出すために生成されたスキーマを示します。|  
  
6.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Response`」と入力します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *ForXMLProcedure.ResponseSchema*ResponseSchema としてストアド プロシージャの実行によって生成される応答スキーマの名前です「[ストアド プロシージャの応答メッセージ スキーマを生成する](#BKMK_RespSchema)します。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の SQL Server ストアド プロシージャを実行します。 このオーケストレーションでの要求メッセージを削除する、定義されている受信場所。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]がこのメッセージを使用して、SQL Server に渡します。 SQL Server からの応答は、別の場所に保存されます。 送信を含めるし、受信図形を SQL Server にメッセージを送信し、それぞれ、応答を受信する必要があります。 プロシージャを呼び出すためのサンプル オーケストレーションには、次のようになります。  
  
 ![ストアド プロシージャを呼び出すオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/eac6e8b6-f0f4-44af-8218-03ca3864b267.gif "eac6e8b6-f0f4-44af-8218-03ca3864b267")  
  
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
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*MessageIn.FOR_XML します。要求*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.FOR_XML します。要求*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.FOR_XML します。応答*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*ResponseOut.FOR_XML します。要求*|  
  
 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、次を参照してください。[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)します。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 [オーケストレーション] ペインで先ほど作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールにアプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル。基本的な BizTalk アプリケーション展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)します。
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- 物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 このオーケストレーションの次の操作を行う必要があります。  
  
  - ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用し、SQL Server データベースに送信します。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションが SQL Server データベースからの応答を含む応答メッセージをドロップする場所の場所を定義します。  
  
  - SQL Server データベースにメッセージを送信する物理 Wcf-custom または WCF-SQL 送信ポートを定義します。 送信ポートを作成する方法については、次を参照してください。 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)します。
  
     送信ポートでアクションを指定することも必要があります。 FOR XML 句を含む手順については、次の形式でアクションを設定する必要があります。  
  
    ```  
    XmlProcedure/<schema_name>/<procedure_name>  
    ```  
  
     そのため、このトピックでは GET_EMP_DETAILS_FOR_XML プロシージャを実行しましたが、アクションになります。  
  
    ```  
    XmlProcedure/dbo/GET_EMP_DETAILS_FOR_XML  
    ```  
  
     設定アクションの詳細については、次を参照してください。 [SQL アダプタの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)します。
  
     FOR XML 句を使用してストアド プロシージャを実行するときに、次のバインドのプロパティを設定することも必要があります。  
  
    |バインドのプロパティ名|これを設定します。|  
    |---------------------------|-----------------|  
    |XmlStoredProcedureRootNodeName|トピックに示すように、ストアド プロシージャ用に生成した応答スキーマに追加したルート ノードの名前を指定[ストアド プロシージャの応答メッセージのスキーマを生成する](#BKMK_RespSchema)します。 このトピックに設定**ルート**します。|  
    |XmlStoredProcedureRootNodeNamespace|トピックに示すように、ストアド プロシージャ用に生成した応答スキーマのターゲット名前空間を指定[ストアド プロシージャの応答メッセージのスキーマを生成する](#BKMK_RespSchema)します。 このトピックに設定`http://ForXmlStoredProcs/namespace`します。|  
  
     バインドのプロパティの値を指定する方法については、次を参照してください。 [SQL アダプタのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)します。  
  
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール (発信) の送信ポートを作成したり (着信) 用のポートを受信します。 詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)します。
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 SQL Server データベースでは、プロシージャを呼び出す BizTalk アプリケーションを開始する必要があります。 BizTalk アプリケーションを開始する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)します。
  
 この段階で、ことを確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   SQL Server データベースにメッセージを送信する Wcf-custom または WCF-SQL 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 ファイルに要求メッセージを削除する必要があります、アプリケーションを実行した後の受信場所。 要求メッセージのスキーマを使用して生成する手順については、要求スキーマに準拠している必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 たとえば、GET_EMP_DETAILS_FOR XML を起動する要求メッセージには。  
  
```  
<GET_EMP_DETAILS_FOR_XML xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo">  
  <emp_id>10765</emp_id>  
</GET_EMP_DETAILS_FOR_XML>  
```  
  
 参照してください[プロシージャと関数のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)を使用して、データベースの SQL Server でプロシージャを呼び出すための要求メッセージ スキーマの詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
 オーケストレーションはメッセージを使用し、SQL Server データベースに送信します。 SQL Server データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、前の要求メッセージ用の SQL Server データベースからの応答には。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Root xmlns="http://ForXmlStoredProcs/namespace">  
  <Adapt_Doc.dbo.Employee Employee_ID="10765" Name="John" Designation="asdfaf" Salary="3434.00" Last_Modified="AAAAAAAANso=" Status="0" xmlns="" />  
</Root>  
```  
  
 ストアド プロシージャの実行によって生成される、同じスキーマで応答を受信することに注意してください。 なお、ルート ノードと名前空間は、値として指定したものと同じである**XmlStoredProcedureRootNodeName**と**XmlStoredProcedureRootNodeNamespace**それぞれバインドのプロパティ。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定、ファイルからインポートできます。 バインド ファイルの詳細については、次を参照してください。[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)します。  
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用して BizTalk アプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)