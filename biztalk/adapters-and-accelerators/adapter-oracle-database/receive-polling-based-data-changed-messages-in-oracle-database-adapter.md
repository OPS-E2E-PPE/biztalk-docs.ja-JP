---
title: Oracle データベース アダプターのデータ変更のポーリングに基づいたメッセージを受信 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- polling-base notification, support for
ms.assetid: 043afb88-701c-41d8-8b8e-84702bd0d984
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f234e57353d22c785dc57271add297e7a6d2c9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="receive-polling-based-data-changed-messages-in-oracle-database-adapter"></a>Oracle データベース アダプターのデータ変更のポーリングに基づいたメッセージを受信します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle データベースをポーリングすることによってデータ変更のポーリングに基づいたメッセージの受信をサポートします。 アダプターは、によって、アプリケーションにメッセージを提供します。  
  
-   データのポーリングに使用できるかどうかが判定を SQL SELECT クエリを実行しています。 継続的に、定期的にまたは、SQL SELECT クエリを実行するアダプターを構成することができます。  
  
-   Oracle のテーブルまたはビューに対して SQL SELECT クエリを実行するかを実行するストアド プロシージャ、関数、またはパッケージ化されたプロシージャと関数。  
  
-   Oracle データベースで、省略可能な後ポーリング PL/SQL コード ブロックを実行しています。 ターゲットの照会されたレコードにフィールドを更新するか、照会されたレコードを別のテーブルまたはビューに移動する、次のコード ブロックがよく使用されます。  
  
-   結果のクエリの結果を返す POLLINGSTMT 操作またはストアド プロシージャ、関数、またはパッケージ化されたプロシージャおよびポーリング操作として公開されている関数を呼び出すことによって設定します。  
  
 アダプターは、すべての Oracle トランザクション内でこれらの操作を実行します。  
  
 アダプターでは公開することで、同じアプリケーションで複数の Oracle 成果物のためのデータ変更メッセージを受信することもできます、`PollingId`接続 URI 内のパラメーターです。 このパラメーターは、POLLINGSTMT 操作のターゲットの名前空間を変更します。  
  
## <a name="change-the-target-namespace-of-pollingstmt"></a>POLLINGSTMT のターゲットの名前空間を変更します。  
 POLLINGSTMT 操作のターゲットの名前空間を変更するには、設定、`PollingId`接続 URI の文字列パラメーターをクエリします。 場合、`PollingId`接続 URI で指定されて、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で指定する文字列を追加、 `PollingId` POLLINGSTMT 操作の既定のターゲット名前空間は、パラメーター:`http://microsoft.lobservices.oracledb/2007/03/POLLINGSTMT`です。 POLLINGSTMT 操作のメッセージのアクションは変更されません。  
  
 たとえば、次の接続 URI が指定されている場合: `OracleDb://User=SCOTT;Password=TIGER@Adapter?PollingId=AcctActivity`、ターゲットの名前空間になります`http:/microsoft.lobservices.oracledb/2007/03/POLLINGSTMTAcctActivity`です。  
  
 POLLINGSTMT 操作ごとに一意の名前空間を提供する、アプリケーションで複数の Oracle テーブルとビューのデータ変更のメッセージを受け取ることができます。  
  
 詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接続 URI を参照してください[Oracle Database 接続 URI を作成する](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。  
  
## <a name="receive-data-changed-messages-using-binding-properties"></a>バインドのプロパティを使用してデータの変更メッセージを受信します。
 構成する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メッセージを受信するデータ変更を次のバインドのプロパティの一部またはすべてを設定します。  
  
|プロパティのバインド|値|既定値|必須/省略可|  
|----------------------|-----------|-------------|------------------------|  
|**InboundOperationType**|値が 設定されていることを確認してください**ポーリング**です。|ポーリング|必須。 以外の場合に明示的に設定、既定値に適用されます。|  
|**PolledDataAvailableStatement**|すべてのデータが特定のテーブルのポーリングに使用できるかどうかを判断するために実行する SELECT ステートメントを指定します。 指定されたステートメントは、結果の行と列で構成されるセットを返す必要があります。 結果セットの最初のセルの値では、アダプターが指定された値を実行するかどうかを示します、 **PollingStatement**プロパティをバインドします。 結果の最初のセルには正の値が含まれている場合、アダプターは、ポーリング ステートメントを実行します。 たとえば、このバインディングのプロパティの有効なステートメントになります。<br /><br /> `Select * from <table_name>`<br /><br /> **注:**のストアド プロシージャをこのバインドのプロパティを指定する必要があります。 また、このステートメントは、基になる Oracle データベースで変更しないでください。|デュアルから 1 を選択します|必須。 表示ない場合は、明示的に設定、既定値に適用されます、アダプターがポーリングされてテーブルにデータがかどうかどうかに関係なく、ポーリングを続行する必要がありますが含まれています。|  
|**PollingAction**|ポーリング操作のアクションを指定します。 使用して、操作を生成するメタデータから特定の操作についてのポーリング動作を指定できます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。|null|テーブルとビューの SELECT ステートメントを使用してポーリング操作の省略可能です。|  
|**PollingInterval**|アダプターは、Oracle データベースのクエリを実行する秒単位で間隔を設定します。 このプロパティは、ポーリング間隔とポーリング トランザクションのタイムアウトを指定します。値は、ポーリング後ステートメント (いずれかを指定)、Oracle データベースの場合、クエリの実行に要する時間にクライアントがクエリ データを処理し、ポーリング応答メッセージを返すにかかる時間の時間を加えたより大きくする必要があります。|500|必須。 以外の場合に明示的に設定、既定値に適用されます。|  
|**PollingStatement**|次のいずれかを指定します。<br /><br /> Oracle データベースに対して実行される SQL SELECT ステートメント。 このステートメントは、FOR UPDATE 句を含める必要があります。 FOR UPDATE 句の詳細については、次を参照してください。[ポーリング ステートメントでの UPDATE 句を指定する](#ForUpdate)このトピックで後述します。<br /><br /> ストアド プロシージャ、関数、またはプロシージャまたは関数にポーリングするパッケージ内のメッセージを要求します。|null|必須。 設定**PollingStatement** null 以外の値にポーリングを有効にします。|  
|**PollWhileDataFound**|指定するかどうか、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ポーリング間隔を無視し、継続的にデータがポーリングするテーブルで使用できる場合は、Oracle データベースをポーリングします。 指定されたポーリング間隔で SQL ステートメントを実行する、テーブルで使用できるデータがない場合は、アダプターを元に戻します|False|必須。 以外の場合に明示的に設定、既定値に適用されます。|  
|**PostPollStatement**|クエリが実行されるが、クエリの前に、データがクライアントに返される後に、アダプターによって実行される省略可能な PL/SQL コード ブロックに設定されます。|null|省略可。 値が指定されていない場合、ポーリング後ステートメントは実行されません。|  
  
> [!NOTE]
>  WCF サービス モデルまたは WCF チャネル モデルを使用している場合、必要がありますも設定する、 **AcceptCredentialsInUri**プロパティをバインドします。  
  
##  <a name="ForUpdate"></a>ポーリング ステートメントでの更新プログラムを入力してください。  
 ポーリング ステートメントと SELECT ステートメントで指定された行に影響するポーリング後ステートメントを実行すると、SELECT ステートメントを使用している場合は、ポーリング ステートメントで FOR UPDATE 句を使用する必要があります。 ポーリング ステートメントによって選択したレコードが、トランザクション中にロックされていることと、ポーリング後ステートメントがそれらに必要な更新を実行できることにより、FOR UPDATE 句を指定します。  
  
> [!CAUTION]
>  内のどこにポーリングし、ポーリング後ステートメントの間の時間枠のシナリオを持つことができますより多くのレコードは、ポーリング後ステートメントの条件を満たすテーブルに追加されます。 このような状況では、条件を満たすすべてのレコードと、ポーリング ステートメントの一部として選択されているレコードだけでなく、ポーリング後ステートメントを更新します。  
  
 ポーリング後ステートメントが指定されている、ポーリング ステートメントに FOR UPDATE 句が含まれていない場合は、次の 2 つの条件のいずれかが発生します。  
  
-   場合**TransactionIsolationLevel**に設定されている**ReadCommitted**、後のポーリング クエリでは、選択した行は更新されません。  
  
-   場合**TransactionIsolationLevel**に設定されている**Serializable**、次のシステム例外の対象 (**Microsoft.ServiceModel.Channels.Common.TargetSystemException**)、ポーリング後ステートメントが実行されたときに発生します。"ora-08177 シリアル化できませんこのトランザクションへのアクセス"です。 このような場合は、設定する必要があります、 **PollingRetryCount**数を定義するプロパティのバインド アダプターは、同じトランザクションを再試行する回数。  
  
 トランザクション分離レベルを設定する方法の手順については、次を参照してください。[の Oracle データベースとトランザクション分離レベルとトランザクションのタイムアウトを構成](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)です。  
  
 トランザクションとの値を使用するアダプターのクライアントが構成されている場合、ポーリング ステートメントとポーリング後ステートメントがトランザクションで実行される、 **UseAmbientTransaction**に設定されているプロパティのバインド**True**アダプターでします。  
  
 FOR UPDATE オプションを使用して、ポーリング クエリの例を示します。  
  
```  
SELECT * from EMP WHERE FLAG = 'Y' FOR UPDATE  
```  
  
### <a name="enter-a-nowait-clause-in-the-polling-statement"></a>ポーリング ステートメントでは、NOWAIT 句を入力します。  
 同時実行スレッドがポーリングされて、テーブルにアクセスするシナリオがありますが多すぎます競合テーブル内に先行します。 テーブルの行のロックを取得するブロックされるまでに、ポーリング クエリがあります。 ポーリング ステートメントと SELECT ステートメントを使用する場合は、SELECT ステートメントで FOR UPDATE キーワードと共に NOWAIT キーワードを指定します。 これにより、アダプターを選択しようとして、ポーリング クエリの行にロックがあるかどうかにすぐに返す内でのポーリング クエリの実行。 例外は通常このような条件下で Oracle によってスローされます。 アダプターのクライアントを再び使用することがあります、 **PollingInterval**データをポーリングする時間間隔後アダプター クライアントが再試行する必要がありますを指定するプロパティをバインドします。  
  
 NOWAIT オプションを使用して、ポーリング クエリの例を示します。  
  
```  
SELECT * from EMP WHERE FLAG = 'Y' FOR UPDATE NOWAIT  
```  
  
### <a name="enter-a-skip-locked-clause-in-the-polling-statement"></a>ポーリング ステートメントで、ロックされたスキップ句を入力してください。  
 ここで同時実行スレッドをポーリングするテーブルにアクセスするため、ポーリング クエリで指定した WHERE 句の結果セット内のいくつかの行がロックされているシナリオがあります。 たとえば、ポーリング クエリがテーブルから 6 つの行を返します他のトランザクションのため、これら 6 つの行外の 4 はロックアウトされています。 この場合、WHERE 句で指定された行をロックして、既にロックされていることが判明しているすべての行をスキップするを試行するように指示される FOR UPDATE キーワードと共に SKIP がロックされているキーワードを指定することができます。 トランザクション中に、WHERE 句でロックされていない行がロックされている、ポーリング後ステートメントは、これらの行が再度ポーリングされませんようにの必要な更新を実行できます。 これにより、メッセージを受信する、ポーリングの WHERE 句によってロックされていないすべての行を指定するまで待機する必要はありません。  
  
 ロックされたスキップ キーワードは、データベース内の同じテーブルをポーリングしている複数のコンピューターでアダプターのクライアントが存在するシナリオに便利です。 WHERE 句で指定された時間、その時点でのロック解除されている行のデータの変更のポーリングに基づくメッセージが表示されるように、ポーリング操作を構成することによってアダプターのクライアント間での負荷し、ことを確認する行を更新できます。クライアントがアダプターによってポーリング ベースのデータ変更メッセージを受信する場合、その他のクライアントは発生しません、同じメッセージ。  
  
 ロックされたスキップ オプションを使用して、ポーリング クエリの例を示します。  
  
```  
SELECT * from EMP WHERE FLAG = 'Y' FOR UPDATE SKIP LOCKED  
```  
  
## <a name="support-for-ordered-delivery-fifo"></a>順次配送 (FIFO) のサポート  
 運用環境では、Oracle データベースでデータ変更を監視するポーリングを使用できます。 これらのデータ変更のメッセージがアダプターを使用してクライアントによって受信されて、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 ビジネス シナリオに基づいて、だということ、正しい順序でアダプターのクライアントでデータ変更のメッセージが受信したことが重要です。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]配信または最初先出しの順序をサポートしている Oracle データベースからメッセージが受信される順序を維持するために (FIFO) です。 ここでは、受信シナリオにおける FIFO のサポートに関連するいくつかの考慮事項、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
-   メッセージがオーケストレーションによって処理される場合、オーケストレーションがあります設定から送られたメッセージの順次配送、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ポートを受信します。  
  
-   送信ポートで、コンテンツ ベースのルーティング) シナリオによってメッセージが処理される場合、送信ポートが設定から送られたメッセージの配信を順序付けする必要があります、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ポートを受信します。  
  
 Wcf-custom または Wcf-oracledb アダプター プロパティが含まれる**エラー発生時に要求メッセージを保留**受信処理に失敗した要求メッセージを中断するかどうかを指定します。 このプロパティを設定することができます、**メッセージ**下にあるポートを受信する Wcf-custom または Wcf-oracledb タブ、**エラー処理**セクションです。 次の表は、このプロパティを設定するかどうかと、メッセージのサブスクライバー (オーケストレーションまたはポート) の状態に基づいて、受信メッセージの処理方法を説明するシナリオを一覧表示します。  
  
|Port プロパティ|参加解除状態でサブスクライバー|停止状態が参加済みでサブスクライバー|  
|-------------------|------------------------------------|----------------------------------------------|  
|**エラー発生時に要求メッセージを中断**プロパティ|の中断 (再開不可メッセージ) としてルーティング エラー報告が生成されます。<br /><br /> 実際のメッセージが中断されていません。<br /><br /> -Post のトランザクションが中止を取得すると、ポーリング クエリは実行されません。 そのためにポーリングが繰り返され、もう一度、行がフェッチされます。<br /><br /> -エラー ログの作業内容が発生したイベントを報告します。|-できません「エラー」と見なされます。 イベント ログにエラー メッセージはありません。<br /><br /> 実際のメッセージは、中断 (再開可能) キューに配置されます。<br /><br /> -起動時、サブスクライブしているポートまたはオーケストレーション、メッセージが自動的に再開されます。 順次配送がサブスクライバーに設定されている場合は、それが受け入れられます。<br /><br /> -メッセージを手動で再開も可能性があります。|  
|**エラー発生時に要求メッセージを中断**プロパティの設定|の中断 (再開不可メッセージ) としてルーティング エラー報告が生成されます。<br /><br /> 実際のメッセージが中断されても<br /><br /> -Post のトランザクションが中止を取得すると、ポーリング クエリは実行されません。 そのためにポーリングが繰り返され、もう一度、行がフェッチされます。<br /><br /> -エラー ログの作業内容が発生したイベントを報告します。|-できません「エラー」と見なされます。 イベント ログにエラー メッセージはありません。<br /><br /> 実際のメッセージは、中断 (再開可能) キューに配置されます。<br /><br /> -起動時、サブスクライブしているポートまたはオーケストレーション、メッセージが自動的に再開されます。 順次配送がサブスクライバーに設定されている場合は、それが受け入れられます。<br /><br /> -メッセージを手動で再開も可能性があります。|  
  
## <a name="see-also"></a>参照  
[Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)  
 [BizTalk Server を使用して Oracle データベースをポーリング](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-database-using-biztalk-server.md)   
 [WCF サービス モデルを使用して Oracle データベースでデータ変更のポーリングに基づいたメッセージを受信します。](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-service.md)   
 [WCF チャネル モデルを使用して Oracle データベースでデータ変更のポーリングに基づいたメッセージを受信します。](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-channel.md)