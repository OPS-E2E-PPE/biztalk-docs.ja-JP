---
title: "BizTalk Server を使用して SQL Server からデータ変更のポーリングに基づいたメッセージを受信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9ecaf6f7-974b-4487-8c65-d1ab628cbfeb
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2251ec6f5019fab4eecff36ac35314183f9a7d61
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="receive-polling-based-data-changed-messages-from-sql-server-using-biztalk-server"></a>BizTalk Server を使用して SQL Server からのデータ変更のポーリングに基づいたメッセージを受信します。
構成することができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server のテーブルまたはビューのデータの定期的な変更メッセージを受信します。 データベースをポーリングするアダプターを実行するポーリング ステートメントを指定することができます。 ポーリング ステートメントには、SELECT ステートメントまたは結果セットを返すストアド プロシージャを使用できます。  

  
 アダプターがポーリングをサポートする方法の詳細については、次を参照してください。[ポーリングのサポート](https://msdn.microsoft.com/library/dd788416.aspx)です。 ポーリング操作用の SOAP メッセージの構造については、次を参照してください。[ポーリングと TypedPolling 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)です。  
  
> [!NOTE]
>  このトピックを使用する方法を示します、**ポーリング**ポーリング メッセージを使用する操作を受信します。 ポーリング操作のメッセージは厳密に型指定がないと、実行時に、メッセージと共にポーリングされているオブジェクトのスキーマを取得します。 使用する必要がありますを厳密に型指定されたポーリング メッセージを取得する場合、 **TypedPolling**操作します。 使用することも必要があります、 **TypedPolling**工程に 1 つの BizTalk アプリケーションで複数の操作をポーリングします。 実行する方法の詳細について**TypedPolling**操作を参照してください[SQL Server を使用して BizTalk Server からデータ変更のポーリングに基づいたメッセージを受信厳密に型指定された](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md)です。  
  
> [!IMPORTANT]
>  かどうかは 1 つの BizTalk アプリケーションに複数のポーリング操作を必要がありますを指定する、 **InboundID**接続一意にする URI の一部として接続プロパティです。 一意の接続 URI の場合を複数作成できます、同じデータベースまたはデータベースでも同じテーブルをポーリングするポートを受信します。 詳細については、次を参照してください。[受信ポーリング メッセージ間で複数の受信ポートから BizTalk Server を使用して SQL](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)です。  
  
## <a name="how-this-topic-demonstrates-polling"></a>このトピックの内容がポーリングを示しています  
 このトピックの内容を示すため方法、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]メッセージの変更、BizTalk プロジェクトを作成およびのスキーマを生成するデータの受信をサポート、**ポーリング**操作します。 ポーリングを指定する場合は、デザイン時にプロパティをバインドするには、関連を指定、 **PolledDataAvailableStatement**として。  
  
```  
SELECT COUNT(*) FROM Employee  
```  
  
 **PolledDataAvailableStatement**正の値を含む最初のセルを含む結果セットを返す必要があります。 最初のセルには正の値が含まれていない場合でも、アダプターでは、ポーリング ステートメントは実行されません。  
  
 ポーリング ステートメントの一部として、次の操作を実行します。  
  
-   Employee テーブルからすべての行を選択します。  
  
-   ストアド プロシージャ、EmployeeHistory テーブルには Employee テーブルからすべてのレコードを移動するには、(MOVE_EMP_DATA) を実行します。  
  
-   Employee テーブルに新しいレコードを追加するには、(ADD_EMP_DETAILS) ストアド プロシージャを実行します。 この手順は、従業員名、指定、および給与をパラメーターとして受け取ります。  
  
 これらの操作を実行するは、次を指定する必要があります、 **PollingStatement**プロパティをバインドします。  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 ポーリング ステートメントが実行された後に Employee テーブルからのすべてのレコードが選択され、SQL Server からのメッセージが受信場所にドロップしました。 アダプターによって MOVE_EMP_DATA ストアド プロシージャを実行すると、すべてのレコードが EmployeeHistory テーブルに移動されます。 次に、Employee テーブルに新しいレコードを追加する ADD_EMP_DETAILS ストアド プロシージャが実行されます。 次のポーリングの実行には、1 つのレコードだけを返します。 このサイクルは、受信を無効にするまで SQL サーバーをポーリングするポート。  
  
## <a name="configuring-a-polling-query-with-the-sql-adapter-binding-properties"></a>SQL アダプターのプロパティのバインドと、ポーリング クエリの構成  
 次の表、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドのプロパティ データの変更メッセージを受信するアダプターを構成するために使用します。 受信ポートを構成するときにこれらのバインディング プロパティを指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
> [!NOTE]
>  スキーマを生成するときに、これらのバインディング プロパティを指定することもできます、**ポーリング**操作、必須ではない場合でもです。 これを行うと、ポートのバインド ファイル、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成され、メタデータの生成の一部では、バインドのプロパティを指定する値も含まれます。 このバインド ファイルを後でインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロパティは既に設定されています。 バインドで wcf-custom または WCF SQL を作成する管理コンソールの受信ポート。 詳細については、バインド ファイルを使用するポートを作成する、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)です。  
  
|プロパティのバインド|Description|  
|---|---|  
|**InboundOperationType**|実行するかどうかを指定します**ポーリング**、 **TypedPolling**、または**通知**操作を受信します。 既定値は**ポーリング**です。|  
|**PolledDataAvailableStatement**|すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。 SQL ステートメントには、結果の行と列で構成されるセットを返す必要があります。 SQL ステートメントが指定した行がある場合のみ、 **PollingStatement**プロパティのバインドが実行されます。|  
|**PollingIntervalInSeconds**|秒単位で間隔を指定、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]の指定されたステートメントの実行、 **PolledDataAvailableStatement**プロパティをバインドします。 既定値は 30 秒です。 ポーリング間隔では、連続するポーリングの間隔を決定します。 ステートメントは、指定した期間内で実行される、アダプターは、間隔の残り時間を待機します。|  
|**PollingStatement**|SQL Server データベース テーブルをポーリングする SQL ステートメントを指定します。 単純な SELECT ステートメントまたはストアド プロシージャのポーリング ステートメントを指定できます。 既定値は null です。 値を指定する必要があります**PollingStatement**ポーリングを有効にします。 ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。 セミコロンで区切られた SQL ステートメントの任意の数を指定できます。|  
|**PollWhileDataFound**|指定するかどうか、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ポーリング間隔を無視し、継続的に指定された SQL ステートメントを実行、 **PolledDataAvailableStatement**をポーリングするテーブルにデータがある場合、プロパティをバインドします。 テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔で SQL ステートメントを実行する元に戻します。 既定値は**false**です。|  
  
 これらのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for SQL Server アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。 使用する方法の詳細については、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL サーバーのポーリングを読みます。  
  
## <a name="how-to-receive-data-change-messages-from-the-sql-server-database"></a>SQL Server データベースからのデータ変更メッセージを受信する方法  
 SQL Server データベースを使用して、操作を実行[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明する手順のタスクでは、 [SQL アダプターと BizTalk アプリケーションを開発する基盤](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)です。 これらのタスクはデータ変更メッセージを受信するアダプターを構成するのには。  
  
1.  BizTalk プロジェクトを作成しのスキーマを生成、**ポーリング**操作します。 必要に応じての値を指定することができます、 **PolledDataAvailableStatement**と**PollingStatement**プロパティをバインドします。  
  
2.  SQL Server データベースからメッセージを受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  SQL Server データベースからメッセージを受信して、フォルダーに保存するオーケストレーションを作成します。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
    > [!IMPORTANT]
    >  受信ポーリングのシナリオは、一方向の WCF カスタム常に構成する必要があります。 または WCF SQL 受信ポート。 双方向の WCF カスタムまたは WCF SQL 受信ポートの受信操作はサポートされていません。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 スキーマを生成する必要があります、**ポーリング**操作します。 参照してください[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)スキーマを生成する方法についての詳細。 スキーマを生成するときに、次のタスクを実行します。 デザイン時のバインドのプロパティを指定しない場合は、最初の手順をスキップします。  
  
1.  値を指定**PolledDataAvailableStatement**と**PollingStatement**スキーマの生成中にプロパティをバインドします。 このバインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
     バインドのプロパティを指定する方法については、次を参照してください。 [SQL アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)です。  
  
2.  コントラクトの種類を選択して**サービス (入力方向の操作)**です。  
  
3.  スキーマを生成、**ポーリング**操作します。  
  
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
    |[Identifier]|型**受信**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*PollingQuery.Polling*ここで、 *PollingQuery* BizTalk プロジェクトの名前を指定します。 *ポーリング*に対して生成されたスキーマは、**ポーリング**操作します。|  
  
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
|ReceiveMessage|-設定**メッセージ**に*受信*<br /><br /> -設定**操作**に*SQLReceivePort.Polling.Request*|  
|SaveMessage|-設定**メッセージ**に*受信*<br /><br /> -設定**操作**に*SaveMessagePort.Polling.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。 
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。  
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが、SQL Server データベースからメッセージをドロップ場所に場所を定義します。 これらのメッセージは、受信ポートの指定したポーリング ステートメントへの応答になります。  
  
    -   物理 Wcf-custom を定義するか、WCF SQL 一方向の受信ポートです。 このポートは、ポートを指定するポーリング ステートメントを使用して SQL Server データベースをポーリングします。 ポートを作成する方法については、次を参照してください。 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)です。 受信ポートのバインドのプロパティを指定することを確認してください。  
  
        > [!IMPORTANT]
        >  デザイン時のバインドのプロパティを指定した場合、この手順を実行する必要はありません。 このような場合は、WCF カスタムを作成または WCF SQL 受信ポート、必要なバインド プロパティを設定、によって作成されたバインド ファイルをインポートすることによって、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)です。  
  
        |プロパティのバインド|値|  
        |----------------------|-----------|  
        |**InboundOperationType**|これを設定するかどうかを確認**ポーリング**です。|  
        |**PolledDataAvailableStatement**|SQL ステートメントを指定することを確認してください。 このトピックの次のように指定します。<br /><br /> `SELECT COUNT(*) FROM Employee`|  
        |**PollingStatement**|ポーリング ステートメントを指定することを確認してください。 このトピックの次のように指定します。<br /><br /> `SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000`|  
  
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
  
-   アダプターでは、ポーリング ステートメントを実行します。 ポーリング ステートメントと SELECT ステートメントおよびストアド プロシージャは、アダプターは、他の後に 1 つのすべてのステートメントを実行します。  
  
    -   アダプターは、最初は Employee テーブルのすべてのレコードを返す SELECT ステートメントを実行します。  
  
    -   アダプターは、EmployeeHistory テーブルには Employee テーブルからすべてのデータを移動する MOVE_EMP_DATA ストアド プロシージャを実行します。 このストアド プロシージャは、任意の値を返しません。  
  
    -   アダプターは、Employee テーブルに 1 つのレコードを追加する ADD_EMP_DETAILS ストアド プロシージャを実行します。 このストアド プロシージャでは、挿入したレコードの従業員 ID を返します。  
  
     そのため、SQL Server から受信したメッセージでは、(SELECT ステートメントおよび ADD_EMP_DETAILS ストアド プロシージャ)、複数の結果セットが含まれ、次のようになります。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Polling xmlns="http://schemas.microsoft.com/Sql/2008/05/Polling/">  
      <PolledData>  
        <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">  
          <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
            <xs:element msdata:IsDataSet="true" name="NewDataSet">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                    <xs:complexType>  
                      <xs:sequence>  
                        <xs:element minOccurs="0" name="Employee_ID" type="xs:int" />   
                        <xs:element minOccurs="0" name="Name" type="xs:string" />   
                        <xs:element minOccurs="0" name="DOJ" type="xs:dateTime" />   
                        <xs:element minOccurs="0" name="Designation" type="xs:string" />   
                        <xs:element minOccurs="0" name="Job_Description" type="xs:string" />   
                        <xs:element minOccurs="0" name="Photo" type="xs:base64Binary" />   
                        <xs:element minOccurs="0" name="Rating" type="xs:string" />   
                        <xs:element minOccurs="0" name="Salary" type="xs:decimal" />   
                        <xs:element minOccurs="0" name="Last_Modified" type="xs:base64Binary" />   
                      </xs:sequence>  
                    </xs:complexType>  
                  </xs:element>  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
          </xs:schema>  
          <diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
            <NewDataSet xmlns="">  
              <NewTable>  
                <Employee_ID>10001</Employee_ID>   
                <Name>John</Name>   
                <Designation>Tester</Designation>   
                <Salary>100000.00</Salary>   
                <Last_Modified>AAAAAAAAF34=</Last_Modified>   
              </NewTable>  
              ........  
              ........  
              <NewTable>  
                <Employee_ID>10005</Employee_ID>   
                <Name>Wilson</Name>   
                <Designation>Tester3</Designation>   
                <Salary>100000.00</Salary>   
                <Last_Modified>AAAAAAAAF4E=</Last_Modified>   
              </NewTable>  
            </NewDataSet>  
          </diffgr:diffgram>  
        </DataSet>  
        <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">  
          <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
            <xs:element msdata:IsDataSet="true" name="NewDataSet">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                    <xs:complexType>  
                      <xs:sequence>  
                        <xs:element minOccurs="0" name="Employee_ID" type="xs:int" />   
                      </xs:sequence>  
                    </xs:complexType>  
                  </xs:element>  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
          </xs:schema>  
          <diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
            <NewDataSet xmlns="">  
              <NewTable>  
                <Employee_ID>10006</Employee_ID>  
              </NewTable>  
            </NewDataSet>  
          </diffgr:diffgram>  
        </DataSet>  
      </PolledData>  
    </Polling>  
    ```  
  
     前の応答には、2 つのデータセットが含まれています。 最初のデータ セットには、SELECT ステートメントの応答が含まれています。 SELECT ステートメントでは、Employee テーブルのすべてのレコードを選択します。 2 番目のデータ セットは、ADD_EMP_DETAILS ストアド プロシージャのです。 このストアド プロシージャは、Employee テーブルにレコードを追加し、新しいレコードの従業員 ID を返します。  
  
    > [!NOTE]
    >  MOVE_EMP_DATA ストアド プロシージャは、結果セットを返しません。 そのためはありませんに対応するデータ セットで応答メッセージです。  
  
-   アダプターが実行される場合、 **PollDataAvailableStatement** ADD_EMP_DETAILS によって挿入されたレコードを 1 つのストアド プロシージャ、もう一度検索します。 アダプターが指定されているすべての 3 つのステートメントを実行し、 **PollingStatement**プロパティをバインドします。 このとき、SQL Server からの応答には、SELECT ステートメントの 1 つのレコードが含まれています。 し、ストアド プロシージャを ADD_EMP_DETAILS の 1 つのレコードです。 すべての後続のポーリングには、同様の応答が返されます。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]はポーリングから受信ポートを明示的に無効にするまで引き続き、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)です。
  
## <a name="see-also"></a>参照  
 [BizTalk Server と SQL アダプタを使用して SQL サーバーにポーリング](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)