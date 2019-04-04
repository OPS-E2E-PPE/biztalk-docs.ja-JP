---
title: SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて確認 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2019
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4606f583-da74-4a26-95cb-88915ecafe37
caps.latest.revision: 43
author: MandiOhlinger
ms.author: niklase,mandia
manager: anneta
ms.openlocfilehash: e9851d5c77a3470d784defd1d544d42014251dd7
ms.sourcegitcommit: 22b43db719de5a916b44331e79e88e68f0648b37
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58794583"
---
# <a name="read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties"></a>SQL Server のアダプターのバインド プロパティの BizTalk アダプターについてください。
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]いくつかのバインド プロパティを表示します。 これらのプロパティを設定するには、アダプターの動作の一部を制御できます。 このセクションで公開されているバインド プロパティを説明します、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 アクセスする方法に .NET プログラミングを使用して、またはプロパティを設定しても表示されます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]物理ポートのバインド。  

## <a name="the-adapter-binding-properties"></a>アダプターのバインドのプロパティ  
 次の表は[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]カテゴリ別にグループ化プロパティをバインドします。 カテゴリは、各バインド プロパティがアダプター (またはバインド) を構成するさまざまなアプリケーションで表示されるダイアログ ボックスで表示されるノードを参照します。  

#### <a name="xmlstoredprocedurerootnodename"></a>XmlStoredProcedureRootNodeName
**カテゴリ**:FOR XML  
**説明**:SELECT ステートメントで FOR XML 句を含むストアド プロシージャの応答スキーマのルート ノードの名前を指定します。 このルート ノードには、このようなストアド プロシージャの実行後に SQL Server から受信する XML 応答がカプセル化します。 トピックの説明に従って、応答スキーマにこのルート ノードを追加する必要があります[Execute ストアド プロシージャが BizTalk Server を使用して SQL Server で、FOR XML 句を持つ](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk.md)します。

> [!IMPORTANT]
> FOR XML 句を使用したストアド プロシージャの実行中には、このバインドのプロパティを設定する必要があります。

**.NET 型**: 文字列

#### <a name="xmlstoredprocedurerootnodenamespace"></a>XmlStoredProcedureRootNodeNamespace
**カテゴリ**:FOR XML  
**説明**:SELECT ステートメントで FOR XML 句を含むストアド プロシージャの応答スキーマのルート ノードのターゲットの名前空間を指定します。  
**.NET 型**: 文字列

#### <a name="closetimeout"></a>CloseTimeout
**カテゴリ**:全般  
**説明**:[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]接続タイムアウトを閉じます。 既定では 1 分です。  
**.NET 型**:System.TimeSpan

#### <a name="name"></a>名前
**カテゴリ**:全般  
**説明**:によって生成されたファイルの名前を取得する読み取り専用値、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]保持するために、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアント クラス。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]フォームの値にファイル名の「クライアント」を追加して、**名前**プロパティ。 このプロパティの既定値は"SqlAdapterBinding";この値は、生成されたファイルはという名前を付ける"SqlAdapterBindingClient"。  
**.NET 型**: 文字列

#### <a name="opentimeout"></a>OpenTimeout
**カテゴリ**:全般  
**説明**:指定します、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]接続オープン タイムアウトします。 既定では 1 分です。

> [!IMPORTANT]
> [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]は常に使用**OpenTimeout** SQL Server への接続を開くときに、接続のオープン タイムアウトを設定します。 アダプターが何らかのタイムアウトを無視します (**System.TimeSpan**) 通信オブジェクトを開くと、パラメーターが渡されます。 たとえば、アダプターでは、チャネルを開くときに渡されるタイムアウト パラメーターは無視されます。

**.NET 型**:System.TimeSpan

#### <a name="receivetimeout"></a>ReceiveTimeout
**カテゴリ**:全般  
**説明**:指定します、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メッセージ受信のタイムアウト。 基本的には、これは、アダプタが受信メッセージの待機時間の最大量を意味します。 既定値は、10 分です。

> [!IMPORTANT]
> ポーリングなどの受信操作は、24.20:31:23.6470000 (24 日) は、最大の可能な値にタイムアウトの設定をお勧めします。 アダプターを使用する場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、タイムアウトを大きな値に設定した場合、アダプターの機能は影響しません。

**.NET 型**:System.TimeSpan

#### <a name="sendtimeout"></a>SendTimeout
**カテゴリ**:全般  
**説明**:指定します、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メッセージ送信のタイムアウト。 既定では 1 分です。  
**.NET 型**:System.TimeSpan

#### <a name="enablebiztalkcompatibilitymode"></a>EnableBizTalkCompatibilityMode
**カテゴリ**:BizTalk  
**説明**:と共に、アダプターを使用するかどうかを示す[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]または .NET アプリケーション。

- アダプターを使用するときに BizTalk Server (または BizTalk プロジェクトでアダプターを使用して SQL Server での操作のメタデータを生成する) 必要があります常に、プロパティに設定する**True**します。 これにより、System.Data.DataSet に対して生成されたスキーマが BizTalk Server と互換性のある形式であります。 それ以外の場合、BizTalk プロジェクトはコンパイルに失敗します。
- アダプターを使用するときに[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、.NET アプリケーション プロパティを設定する必要があります**False**をデータセットとして、応答を使用する場合。 これにより、System.Data.DataSet に対して生成されたスキーマが WCF DataContractSerializer と互換性のある形式であります。

**.NET 型**: bool (System.Boolean)

#### <a name="batchsize"></a>BatchSize
**カテゴリ**:Buffering  
**説明**:SQL Server データベース テーブルまたはビューの複数レコードの挿入、更新、および削除操作のバッチ サイズを指定します。 既定値は 20 です。 値の**BatchSize** 、1 より大きい、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バッチの 1 つの呼び出しに指定されたレコード数。 値が高いパフォーマンスを向上させることがありますが、メモリ消費量に影響を与えます。  
**.NET 型**: int 型 (System.Int32)

#### <a name="chunksize"></a>ChunkSize
**カテゴリ**:Buffering  
**説明**:< Column_name > セット操作に使用されるバッファーのサイズを指定します。 既定値は 4194304 バイトです。 値が高いパフォーマンスを向上させることがありますが、メモリ消費量に影響を与えます。

> [!NOTE]
> < Column_name > の設定操作の詳細については、[テーブルとビューを含めることが大きなデータ型を SQL アダプターを使用してで操作](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)を参照してください。

**.NET 型**: int 型 (System.Int32)

#### <a name="encrypt"></a>Encrypt
**カテゴリ**:接続  
**説明**:SQL Server とクライアント間のすべてのデータ転送 (インストールされている有効な証明書) を含む SQL Server が SSL 暗号化を使用するかどうかを指定します。 既定値は**false**します。  
**.NET 型**: bool (System.Boolean)

#### <a name="maxconnectionpoolsize"></a>MaxConnectionPoolSize
**カテゴリ**:接続**説明**:接続プール内の特定の接続文字列の許可される接続の最大数を指定します。 既定値は、100 です。 このプロパティは、パフォーマンスのチューニングに使用されます。

> [!IMPORTANT]
> 設定する必要があります**MaxConnectionPoolSize**慎重にします。 この値が大きすぎる場合は、使用可能な接続の数を使い果たしてに考えられるです。

**.NET 型**: int 型 (System.Int32)

#### <a name="workstationid"></a>WorkstationId
**カテゴリ**:接続  
**説明**:使用して、SQL Server データベースに接続するワークステーション (クライアント コンピューター) の一意の ID を指定します、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 このバインド プロパティの値は、指定されている場合の使用は、**ワークステーション ID** SqlConnection.ConnectionString プロパティのキーワード。 詳細については、[SqlConnection.ConnectionString プロパティ](https://docs.microsoft.com/dotnet/api/system.data.sqlclient.sqlconnection.connectionstring?redirectedfrom=MSDN&view=netframework-4.7.2#System_Data_SqlClient_SqlConnection_ConnectionString)を参照してください。  
**.NET 型**: 文字列

#### <a name="enableperformancecounters"></a>EnablePerformanceCounters
**カテゴリ**:診断  
**説明**:有効にするかどうかを指定します、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]パフォーマンス カウンターと[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]LOB 待機時間のパフォーマンス カウンター。 既定値は**False**; パフォーマンス カウンターが無効になっています。 LOB の待機時間のパフォーマンス カウンターで費やされた時間の合計の測定、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で SQL Server データベースへの呼び出しを行います。<br /><br /> パフォーマンス カウンターの詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL アダプターを使用したパフォーマンス カウンターを使用して](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md)します。  
**.NET 型**: int 型 (System.Int32)

#### <a name="inboundoperationtype"></a>InboundOperationType
**カテゴリ**:受信  
**説明**:実行するかどうかを指定します**ポーリング**、 **TypedPolling**、 **XmlPolling**、または**通知**操作を受信します。 既定値は**ポーリング**します。<br /><br /> 詳細については**ポーリング**、 **TypedPolling**、および**XmlPolling**を参照してください[のポーリング サポート](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md)します。 詳細については**通知**を参照してください[に関する考慮事項を受け取るクエリ通知を使用して、SQL アダプター](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)します。  
**.NET 型**: 列挙型

#### <a name="usedatabasenameinxsdnamespace"></a>UseDatabaseNameInXsdNamespace
**カテゴリ**:メタデータ  
**説明**:特定の成果物の生成される XSD がデータベース名を含めるかどうかを指定します。 これを設定**True**データベース名を指定します。 それ以外の場合、これを設定**False**します。 既定値は**False**します。

これは、異なるデータベースでさまざまなメタデータと同じ名前を持つ成果物の操作を実行する 1 つのアプリケーションが必要があるシナリオで役立ちます。 名前空間内にデータベース名がない場合、生成されたメタデータが競合します。 このバインドのプロパティを設定してできます、データベース名を名前空間に追加するしているため、一意。 名前空間の変更を強調表示する例を次に示します。

**UseDatabaseNameInXsdNamespace = False**  
`http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee`

**UseDatabaseNameInXsdNamespace = True**  
`http://schemas.microsoft.com/Sql/2008/05/TableOp/MyDatabase/dbo/Employee`

バインド プロパティ設定されている場合、名前空間で、データベース名が含まれることに注意してください。 **True**します。

**.NET 型**: 列挙型

#### <a name="allowidentityinsert"></a>AllowIdentityInsert
**カテゴリ**:その他  
**説明**:アダプターが Insert および Update 操作中に id 列の値を挿入できるかどうかを指定します。 このプロパティを設定**True**を挿入または id 列の値を更新します。 それ以外の場合に設定**False** (既定値)。

> [!NOTE]
> このプロパティを設定**True**アダプターを使用して、変換されます`SET IDENTITY_INSERT <table_name> ON`します。 詳細については、[SET IDENTITY_INSERT (TRANSACT-SQL)](https://docs.microsoft.com/sql/t-sql/statements/set-identity-insert-transact-sql?view=sql-server-2017)を参照してください。 

このバインドのプロパティを使用しているときに、次の点を考慮する必要があります。

- アダプターでは、id 列のメソッドに渡す値は検証されません。 たとえば、テーブルを 100 に設定する「Identity シード」を持つ id 列がある「Identity インクリメント」が 1 に設定し、アダプターのクライアントが値を渡す、たとえば 95、アダプターの id 列に渡すだけこの値を SQL Server。
- 設定した場合でも**AllowIdentityInsert**に**True**、要求メッセージ内で id 列の値を指定するアダプター クライアントの必須ではありません。 Id 列の値があるアダプターにより SQL Server に渡します。 値が存在しない場合、SQL Server は id 列の仕様に基づいて値を挿入します。  

**.NET 型**: bool (System.Boolean)

#### <a name="notificationstatement"></a>NotificationStatement
**カテゴリ**:通知 (受信)  
**説明**:SQL ステートメントを指定します (SELECT または EXEC\<ストアド プロシージャ\>) の SQL Server の通知を登録するために使用します。 具体的には、次の SELECT ステートメントで示すように、列名をステートメントに入力する必要があります。

`SELECT Employee_ID,Designation FROM dbo.Employee WHERE Status=0`

> [!NOTE]
> スキーマ名とデータベース オブジェクトの名前を指定する必要があります。 たとえば、`dbo.Employee` のようにします。

アダプターは、指定された SQL ステートメントの変更の結果セットの場合にのみ、SQL Server から通知メッセージを取得します。

**.NET 型**: 文字列

#### <a name="notifyonlistenerstart"></a>NotifyOnListenerStart
**カテゴリ**:通知 (受信)  
**説明**:アダプターが受信場所が実行されていること、リスナーの開始時にことを知らせる、アダプターのクライアントに通知メッセージを送信するかどうかを指定します。 既定値は**True**します。

通知メッセージを受信するは、次のようになります。

```xml
<?xml version="1.0" encoding="utf-8" ?>
 <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">
   <Info>ListenerStarted</Info>
    <Source>SqlBinding</Source>
    <Type>Startup</Type>
  </Notification>
```

**.NET 型**: bool (System.Boolean)

#### <a name="polleddataavailablestatement"></a>PolledDataAvailableStatement
**カテゴリ**:ポーリング (受信)  
**説明**:すべてのデータが SQL Server データベースの特定のテーブルのポーリングに使用できるかどうかを判断するために実行する SQL ステートメントを指定します。 指定したステートメントには、結果の行と列で構成されるセットを返す必要があります。 結果セットの最初のセルの値は、アダプターが指定された SQL ステートメントを実行するかどうかを示す、 **PollingStatement**プロパティをバインドします。 結果の最初のセルに正の値が含まれている場合、アダプターはポーリング ステートメントを実行します。 

このバインドのプロパティに指定できる有効なステートメントをいくつかの例を次に示します。

- SELECT ステートメントを指定する: 場合

  `SELECT COUNT(*) from <table_name>`

- ストアド プロシージャを指定する場合として、ストアド プロシージャを定義する場合があります。

  ```sql
  CREATE PROCEDURE <procedure_name>
  AS BEGIN
  SELECT COUNT(*) FROM <table_name>
  END
  GO
  ```

  または

  ```sql
  CREATE PROCEDURE <procedure_name>
  AS BEGIN
  DECLARE @count int
  SELECT @count = SELECT(*) FROM <table_name>
  SELECT @count
  END
  GO
  ```

指定したかどうかは、ストアド プロシージャを使っている場合、 **PolledDataAvailableStatement**として`EXEC <procedure_name>`します。

> [!IMPORTANT]
> 内にこのバインドのプロパティが実行されないために指定したステートメント*開始アダプター*トランザクション、および (ステートメントを実行する場合でも、実際のポーリング ステートメントが実行される前に複数回を呼び出すことがあります指定されたポーリングの使用可能な行があること)。

**.NET 型**: 文字列

#### <a name="pollingintervalinseconds"></a>PollingIntervalInSeconds
**カテゴリ**:ポーリング (受信)  
**説明**:秒単位で間隔を指定、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]に指定されたステートメントが実行される、 **PolledDataAvailableStatement**プロパティをバインドします。 既定値は 30 秒です。 ポーリング間隔は、連続するポーリングの間隔を決定します。 指定時間内でステートメントを実行する場合、アダプターが非アクティブの残りの時間間隔でします。  
**.NET 型**: int 型 (System.Int32)

#### <a name="pollingstatement"></a>PollingStatement
**カテゴリ**:ポーリング (受信)  
**説明**:SQL Server データベースのテーブルをポーリングする SQL ステートメントを指定します。 単純な SELECT ステートメントまたはストアド プロシージャ、ポーリング ステートメントを指定できます。 既定値は **null**です。 値を指定する必要があります**PollingStatement**ポーリングを有効にします。 ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。

セミコロンで区切られた SQL ステートメントの任意の数を指定できます。 ポーリング ステートメントを使用して、読み取りまたは SQL Server データベース テーブル内のデータを更新することができます。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 1 つのトランザクション内でポーリング ステートメントを実行します。 アダプターを使用するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、同じトランザクションは、BizTalk メッセージ ボックスに SQL Server からメッセージを送信するために使用します。

**.NET 型**: 文字列

#### <a name="pollwhiledatafound"></a>PollWhileDataFound
**カテゴリ**:ポーリング (受信)  
**説明**:指定するかどうか、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ポーリング間隔を無視し、継続的に指定された SQL ステートメントを実行、 **PolledDataAvailableStatement**データがポーリングされるテーブルで使用できる場合は、プロパティをバインドします。 テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔で SQL ステートメントを実行する元に戻します。 既定値は**false**します。

ポーリング間隔は 60 秒に設定し、ステートメントが指定されたシナリオを検討してください。 **PolledDataAvailableStatement**ポーリングに使用できるデータが返されます。 アダプターの指定されたステートメントを実行し、 **PollingStatement**プロパティをバインドします。 アダプターは、ポーリング ステートメントの実行に 10 秒だけを受け取り、仮定を実行する前に 50 秒間待機する必要はようになりましたが、 **PolledDataAvailableStatement**もう一度、し、その後、ポーリング ステートメントを実行. 代わりに、設定できるパフォーマンスを最適化するために、 **PollWhileDataFound**プロパティをバインド**true**アダプターが次のポーリング サイクルで前回のポーリング サイクルとすぐに実行を開始できるように終了します。  

**.NET 型**: bool (System.Boolean)

#### <a name="useambienttransaction"></a>UseAmbientTransaction
**カテゴリ**:トランザクション  
**説明**:指定するかどうか、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]呼び出し元によって提供されるトランザクションのコンテキストを使用して、操作を実行します。 既定値は**true**アダプターは、トランザクションのコンテキストでの操作を常に実行することを意味します。 場合は、トランザクションに参加しているその他のリソースがあり、SQL Server トランザクションに参加することも、トランザクションは MSDTC トランザクションに昇格を取得します。

ただし、トランザクションのコンテキストで操作を実行するアダプターを避けたい場合があります。 例 :

- SQL Server での単純な選択操作の実行中にデータベースします。
- Select 操作を実行し、Delete ステートメントまたはストアド プロシージャを呼び出すことによって、テーブルへの変更を伴わないポーリング ステートメントを指定するときにします。

これらの操作では、データベース テーブルには、すべての更新は行いません、そのため、パフォーマンスのオーバーヘッドをする、MSDTC トランザクションを使用してこれらの操作を昇格させることができます。 このようなシナリオをバインディング プロパティを設定できます**false**ように、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]トランザクション コンテキストでは、処理を実行しません。

> [!NOTE]
> - ときに**UseAmbientTransaction**を False に設定されている、 **PolledDataAvailableStatement**というはありません。 アダプターを直接呼び出す代わりに、 **PollingStatement**します。 
> - 操作を実行していないトランザクションのコンテキストでは、データベースに変更を加えないでください操作に対してのみお勧めします。 データベース内のデータを更新する操作、ことをお勧めバインド プロパティを設定する**true**します。 それ以外の場合、受信または送信の操作を実行するかどうかに応じて、メッセージの損失または重複、メッセージが発生する可能性があります。  

**.NET 型**: bool (System.Boolean)

## <a name="how-do-i-set-sql-server-binding-properties"></a>SQL Server のバインドのプロパティを設定する方法はありますか  
 SQL Server への接続を指定する場合は、SQL Server のバインドのプロパティを設定できます。 バインドのプロパティを設定する方法についてはときにします。  

- 使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]を参照してください[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。  

  > [!IMPORTANT]
  >  使用しているときに、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]文字列型のバインド プロパティの値を指定しないし、そのバインドのプロパティは、バインド ファイル (XML ファイル) または app.config ファイルでは使用できませんが既定値が null の場合は、それぞれします。 必要があります手動で追加するバインドのプロパティとその値にバインド ファイルまたは app.config ファイルを必要な場合。  

- 送信ポートを構成または BizTalk Server ソリューションでの受信ポート (場所) を参照してください[SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)します。

- プログラミング ソリューションで WCF チャネル モデルを使用して、参照してください[SQL アダプターを使用してチャネルを作成](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md)です。  

- プログラミング ソリューションで WCF サービス モデルを使用して、参照してください[クライアント バインディングを構成、SQL アダプターの](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)します。  

## <a name="see-also"></a>参照  
[SQL アプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)
