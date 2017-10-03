---
title: "SELECT ステートメントを使用してポーリング Oracle データベース |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- polling-based notifications, receiving from Oracle
- polling query, configuring a
ms.assetid: d2689eb9-6f17-498f-8a32-07f43a368833
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26e840148b4a5cfb8b390d5e89ee0e8edc677aad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="poll-oracle-database-using-the-select-statement"></a>SELECT ステートメントを使用してポーリング Oracle データベース
構成することができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]テーブルおよび Oracle は Oracle データベースでビューを継続的にポーリングする SELECT ステートメントを使用して、定期的なデータの変更メッセージを受信します。 Oracle データベースをポーリングするアダプターが定期的に実行されるポーリング ステートメントと SELECT ステートメントを指定できます。 必要に応じて、データの変更がある場合に、アダプターが実行される後ポーリング PL/SQL コード ブロックも指定することができます。 多くの場合、このブロックを使用するは、ターゲット内のクエリ対象のレコードにフィールドを更新する照会されたレコードを別のテーブルまたはビューに移動したりできます。  
  
 これが有効にする必要がありますを指定する特定のバインディング プロパティで、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 設定して、POLLINGSTMT 操作のターゲット名前空間を変更することも、 **PollingId**接続 URI のプロパティです。 詳細については、次を参照してください。[ポーリング受信ベースのデータ変更メッセージで Oracle データベースでサポート](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md)と[Oracle データベース アダプターのデータ変更のポーリングに基づいたメッセージを受信](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)です。 ポーリング操作用の SOAP メッセージの構造については、次を参照してください。[ポーリング Operations2 のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md)です。  
  
## <a name="configuring-a-polling-operation-with-oracle-database-adapter-binding-properties"></a>Oracle データベース アダプターのバインドのプロパティとポーリング操作を構成します。  
 次の表、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]データを受信するアダプターの構成に使用するバインドのプロパティがメッセージを変更します。 受信ポートを構成するときにこれらのバインディング プロパティを指定する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
|プロパティのバインド|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|ポーリングを実行するかどうかを指定または通知の受信操作します。 既定値は**ポーリング**です。|  
|**PolledDataAvailableStatement**|すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。 レコードがある場合にのみ、SELECT ステートメントを指定するため、 **PollingStatement**プロパティのバインドが実行されます。 既定値は`SELECT 1 FROM DUAL`、か、アダプターにかどうかをポーリングするテーブルにデータに関係なく、ポーリングを続ける必要がありますが含まれています。|  
|**PollingInterval**|秒単位で間隔を指定、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]の指定されたステートメントの実行、 **PolledDataAvailableStatement**プロパティをバインドします。 既定値は、500 秒です。 ポーリング間隔では、連続するポーリングの間隔を決定します。 ステートメントは、指定した期間内で実行される、アダプター休止状態に入ります残り時間の間隔。|  
|**PollingStatement**|ポーリング ステートメントを指定します。 SELECT ステートメントを使用してポーリングを行うには、このバインディングのプロパティの SELECT ステートメントを指定する必要があります。 既定値は null です。<br /><br /> 値を指定する必要があります**PollingStatement**ポーリングを有効にするプロパティをバインドします。 ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。|  
|**PollingAction**|ポーリング操作のアクションを指定します。 使用して、操作を生成するメタデータから特定の操作についてのポーリング動作を指定できます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。|  
|**PostPollStatement**|指定されたステートメントの後に実行されるステートメント ブロックを指定します、 **PollingStatement**プロパティのバインドを実行します。|  
|**PollWhileDataFound**|指定するかどうか、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ポーリング間隔を無視し、継続的にデータで使用できる場合、テーブルをポーリングするポーリング ステートメントを実行します。 テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔でポーリング ステートメントを実行する元に戻します。 既定値は false です。|  
  
 これらのプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。 使用する方法の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]さらに、Oracle データベースをポーリングするには、読み取る。  
  
## <a name="how-this-topic-demonstrates-polling"></a>このトピックの内容がポーリングを示しています  
 このトピックの内容を示すために方法、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] SELECT ステートメントを使用してメッセージを変更する、BizTalk プロジェクトを作成およびのスキーマを生成するデータの受信をサポート、 **POLLINGSTMT**操作を設定して、 **PollingStatement**バインディングには、次のプロパティ。  
  
```  
SELECT * FROM ACCOUNTACTIVITY FOR UPDATE  
```  
  
 データベースでこれらのオブジェクトを作成するサンプルに用意されている SQL スクリプトを実行すると、ACCOUNTACTIVITY テーブルが作成されます。  
  
> [!NOTE]
>  では、オーケストレーションにこのトピックのポーリング、ACCOUNTACTIVITY の表に、ベース データベース テーブルは、サンプルを提供されるスクリプトを実行してこれを作成します。 他のテーブルをポーリングするには、このトピックの説明に従ってと同様の手順を実行する必要があります。  
  
 ポーリング操作を示すためは、次を操作します。  
  
-   SELECT ステートメントを指定、 **PolledDataAvailableStatement**データがある場所のテーブルでポーリング (ACCOUNTACTIVITY) を決定するプロパティをバインドします。 この例では、このバインディングのプロパティとしてを設定できます。  
  
    ```  
    SELECT COUNT (*) FROM ACCOUNTACTIVITY  
    ```  
  
     これにより、ACCOUNTACTIVITY テーブルにレコードの一部がある場合にのみ、アダプターが、ポーリング ステートメントを実行します。  
  
-   前に述べたように、SELECT ステートメントを指定、 **PollingStatement**プロパティをバインドします。 このステートメントは、ACCOUNTACTIVITY テーブル内のすべての行を取得します。  
  
-   一部としての PL/SQL ブロックの実行、 **PostPollStatement**プロパティをバインドします。 このステートメントは、データベース内の別のテーブルに ACCOUNTACTIVITY テーブルからすべてのデータが移動されます。 指定されたステートメントが次回こうなる**PollingStatement**は実行すると、それはフェッチできませんすべてのデータ。  
  
-   多くのデータは、ACCOUNTACTIVITY テーブルに追加される、まで、ポーリングのすべてのメッセージは取得しません。 そのため、新しいレコードを含む ACCOUNTACTIVITY テーブルを再作成する必要があります。 サンプルに用意されている more_activity_data.sql スクリプトを実行して、これを行うことができます。 このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。  
  
## <a name="how-to-receive-data-change-messages-from-oracle"></a>Oracle からのデータ変更メッセージを受信する方法  
 使用して Oracle データベースでの操作を実行する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている次の手順のタスクでは、[の Oracle データベースと BizTalk アプリケーションを開発する基盤](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)です。 これらのタスクは、SELECT ステートメントを使用して Oracle データベースをポーリングするアダプターを構成するのには。  
  
1.  BizTalk プロジェクトを作成しのスキーマを生成、 **POLLINGSTMT**をポーリングするテーブルを操作します。  
  
2.  Oracle データベースからメッセージを受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  Oracle からメッセージを受信し、フォルダーに保存するためのオーケストレーションを作成します。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
    > [!IMPORTANT]
    >  受信のポーリングのシナリオが常に設定する必要がありますの一方向の受信ポート。 双方向受信ポートが受信操作のサポートされていません。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 スキーマを生成する必要があります、 **POLLINGSTMT**操作します。 使用して、スキーマの生成中に、次のタスクを実行、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
-   値を指定**PollingStatement**スキーマの生成中にプロパティをバインドします。 このバインドのプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。 たとえば、ポーリング ステートメントとして、次を指定します。  
  
    ```  
    SELECT * FROM ACCOUNTACTIVITY FOR UPDATE  
    ```  
  
-   コントラクトの種類を選択して**サービス (入力方向の操作)**です。  
  
-   スキーマを生成、 **POLLINGSTMT**操作します。  
  
 スキーマを生成する方法の詳細については、次を参照してください。[参照、検索、および get 操作のメタデータの Oracle データベース](../../adapters-and-accelerators/adapter-oracle-database/browse-search-and-get-metadata-for-oracle-database-operations.md)です。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 スキーマが生成されるは、BizTalk プロジェクトのオーケストレーションの種類からのメッセージをリンクする必要があります。  
  
 このトピックでは、Oracle からメッセージを受信する 1 つのメッセージを作成する必要があります。  
  
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
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*TablePolling.OracleDBBinding*ここで、 *TablePolling* BizTalk プロジェクトの名前を指定します。 *OracleDBBindingSchema* 、応答スキーマに対して生成されるは、 **POLLINGSTMT** ACCOUNTACTIVITY テーブルで操作します。<br /><br /> **重要な**ポーリングは、一方向の操作、アダプターによって生成されたスキーマにノードがありません、応答、およびスキーマには 1 つだけのルート ノードがない、ためためです。 メッセージ型のようなスキーマを使用する場合は、生成されたスキーマのファイル名でスキーマを識別する必要があります。<br /><br /> たとえば、双方向の操作のスキーマを作成する場合、スキーマ内のノード ファイルの名前を持つ`OracleDBBindingSchema`「要求」および"Response"のようになります。 確認して、リスト内のスキーマを識別するには、要求スキーマにマップされるオーケストレーションでメッセージを作成する場合は、`OracleDBBindingSchema.Request`です。 ただし、ポーリング操作の場合、唯一のノードが"POLLINGSTMT"であるため簡単ではありません 1 つのノードでスキーマに設定されていないためにマップするスキーマを識別する\<schemafilename >.\<rootnodename >。 代わりに、このようなスキーマ ファイル名のみが表示されます。 このような場合は、スキーマ ファイル名、たとえば、OracleDBBindingSchema では、スキーマを識別するしかありません。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle からのデータの変更のポーリングに基づくメッセージを受信するためです。 このオーケストレーションでアダプターがの指定した SELECT ステートメントを実行することによって、応答を受信、 **PollingStatement**プロパティをバインドします。 SELECT ステートメントの応答メッセージは、ファイルの場所に保存されます。 Oracle データベースをポーリングするための一般的なオーケストレーションにが含まれます。  
  
-   受信図形と送信図形を Oracle からメッセージを受信し、それぞれ、FILE ポートに送信します。  
  
-   一方向の受信ポートを Oracle データベースからメッセージを受信します。  
  
    > [!IMPORTANT]
    >  受信のポーリングのシナリオが常に設定する必要がありますの一方向の受信ポート。 双方向受信ポートが受信操作のサポートされていません。  
  
-   Oracle データベースからポーリング応答を送信する一方向の送信ポートです。  
  
 サンプル オーケストレーションには、次のようになります。  
  
 ![Oracle のポーリング クエリのオーケストレーション](../../adapters-and-accelerators/adapter-oracle-database/media/6eddfe32-bfd0-4bd9-9e2a-fb4a7d0b53e3.gif "6eddfe32-bfd0-4bd9-9e2a-fb4a7d0b53e3")  
  
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
|OracleReceivePort|-設定**識別子**に*OracleReceivePort*<br /><br /> -設定**型**に*OracleReceivePortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*受信*|  
|SaveMessagePort|-設定**識別子**に*SaveMessagePort*<br /><br /> -設定**型**に*SaveMessagePortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*送信*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表は、プロパティとアクション図形のメッセージを指定して、メッセージ、ポートにリンクを設定する必要があります、値を指定します。 図形 列に表示名は、既に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*受信*<br /><br /> -設定**操作**に*OracleReceivePort.Polling.Request*|  
|SaveMessage|-設定**メッセージ**に*受信*<br /><br /> -設定**操作**に*SaveMessagePort.Polling.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、対応する FILE ポートを BizTalk オーケストレーション Oracle からのメッセージをドロップできる場所に場所を定義します。 これらのメッセージは、受信ポートの指定したポーリング ステートメントへの応答になります。  
  
    -   物理 Wcf-custom を定義するか、Wcf-oracledb 一方向の受信ポートです。 このポートは、Oracle データベースをポーリングします。 受信ポートを作成する方法についてを参照してください[Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)です。 受信ポートのバインドのプロパティを指定することを確認してください。  
  
        |プロパティのバインド|値|  
        |----------------------|-----------|  
        |**InboundOperationType**|これを設定して**ポーリング**です。|  
        |**PolledDataAvailableStatement**|この例このバインドのプロパティを設定します。<br /><br /> `SELECT COUNT (*) FROM ACCOUNTACTIVITY`<br /><br /> これにより、ACCOUNTACTIVITY テーブルにレコードの一部がある場合にのみ、アダプターが、ポーリング ステートメントを実行します。|  
        |**PollingStatement**|このバインド プロパティの ACCOUNTACTIVITY テーブルからすべてのレコードを取得する SELECT ステートメントを指定します。 この例このバインドのプロパティを設定します。<br /><br /> `SELECT * FROM ACCOUNTACTIVITY FOR UPDATE`|  
        |**PostPollStatement**|ACCOUNTACTIVITY テーブルから別のテーブルにすべてのデータを移動する、ポーリング後ステートメントを指定します。 この例このバインドのプロパティを設定します。<br /><br /> `BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;`|  
  
         異なるバインディングのプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。  
  
        > [!NOTE]
        >  使用して受信操作の実行中に、トランザクション分離レベルとトランザクションのタイムアウトを構成することをお勧め、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 受信ポートを構成するときに、サービスの動作を追加することによって行うことができます。 サービスの動作を追加する方法については、次を参照してください。[トランザクション分離レベルとトランザクションのタイムアウト構成](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)です。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 Oracle データベースをポーリングするための BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。  
  
 この段階で確認します。  
  
-   Wcf-custom または Wcf-oracledb 一方向の受信ポートの指定した SELECT ステートメントを使用して oracle データベースをポーリングする、 **PollingStatement**バインディング プロパティが実行されています。  
  
-   Oracle データベースからメッセージを受信する FILE 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後、次の一連のアクションが実行と同じ順序で。  
  
-   アダプターが実行、 **PolledDataAvailableStatement**アダプターに指定されたステートメントを実行することを示す正の値が返されます**PollingStatement**プロパティをバインドします。  
  
-   アダプターの SELECT ステートメントの実行、 **PollingStatement** ACCOUNTACTIVITY テーブルのバインディング プロパティ、およびすべての行を返します。 Oracle データベースからの応答には、次のようになります。  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <POLLINGSTMT xmlns="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT">  
      <POLLINGSTMTRECORD>  
        <POLLINGSTMTRECORD>  
          <TID>1</TID>   
          <ACCOUNT>100001</ACCOUNT>   
          <AMOUNT>500</AMOUNT>   
          <DESCRIPTION />   
          <TRANSDATE>2008-08-03T20:10:28</TRANSDATE>   
          <PROCESSED>n</PROCESSED>   
        <POLLINGSTMTRECORD>  
      <POLLINGSTMTRECORD>  
          ......  
          ......  
      </POLLINGSTMTRECORD>  
        ......  
        ......  
      </POLLINGSTMTRECORD>  
    </POLLINGSTMT>  
    ```  
  
-   アダプターでは、別のテーブルに ACCOUNTACTIVITY テーブルからすべてのデータが移動後ポーリング ステートメントを実行します。  
  
-   ポーリング間隔後に、アダプターがもう一度実行される**PolledDataAvailableStatement**です。 ACCOUNTACTIVITY テーブルにはレコードがあるないようになりました、ため**PolledDataAvailableStatement**は正の値を返さないため、アダプターに指定されたステートメントを実行できませんし、 **PollingStatement**プロパティをバインドします。 その結果、アダプターのクライアントは、ポーリング メッセージを取得できません。  
  
-   レコードの一部は明示的に ACCOUNTACTIVITY テーブルに挿入されるまで、アダプターのクライアントは、これ以上ポーリング メッセージを取得できません。 複数のレコードを挿入するには、サンプルに用意されている more_activity_data.sql スクリプトを実行できます。 次に、このスクリプトを実行した後**PolledDataAvailableStatement**が実行すると、正の値を返します。 結果として、アダプターがポーリング ステートメントを実行し、アダプターのクライアントが再度ポーリング メッセージを受信します。  
  
> [!NOTE]
>  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]はポーリングから受信ポートを明示的に無効にするまで引き続き、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 使用して、データベースの例外については、Oracle のポーリング クエリの実行中に発生する可能性が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[例外と、Oracle データベース アダプターによるエラー処理](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)です。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。 [Oracle データベース アダプターの再利用バインド](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して Oracle データベースをポーリング](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-database-using-biztalk-server.md)