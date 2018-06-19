---
title: Oracle E-business Suite からデータ変更のポーリングに基づいたメッセージを受信 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cbcb23d0-508d-4601-91b4-c674d76cd063
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3aed2e9b42be9aaa44f1f79bf11da03d737dac4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218618"
---
# <a name="receive-polling-based-data-changed-messages-from-oracle-e-business-suite"></a>Oracle E-business Suite からデータ変更のポーリングに基づいたメッセージを受信します。
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]インターフェイス テーブル、インターフェイス ビュー、テーブル、およびビューをポーリングすることによってデータ変更のポーリングに基づいたメッセージの受信をサポートします。 アダプターは、によって、アプリケーションにメッセージを提供します。  
  
-   データのポーリングに使用できるかどうかが判定を SQL SELECT クエリを実行しています。 継続的に、定期的にまたは、SQL SELECT クエリを実行するアダプターを構成することができます。  
  
-   Oracle のテーブルまたはビューに対して SQL SELECT クエリを実行するかを実行するストアド プロシージャ、関数、またはパッケージ化されたプロシージャと関数。  
  
-   Oracle E-business Suite で省略可能な後ポーリング PL/SQL コード ブロックを実行します。 ターゲットの照会されたレコードにフィールドを更新するか、照会されたレコードを別のテーブルまたはビューに移動する、次のコード ブロックがよく使用されます。  
  
-   結果のクエリの結果を返す、ポーリング操作またはストアド プロシージャ、関数、またはパッケージ化されたプロシージャおよびポーリング操作として公開されている関数を呼び出すことによって設定します。  
  
 アダプターは、すべての Oracle トランザクション内のこれらの操作を実行します。  
  
## <a name="how-do-i-configure-the-oracle-e-business-adapter-for-receiving-data-changed-messages-using-binding-properties"></a>バインドのプロパティを使用してデータの変更メッセージを受信するための Oracle E-business アダプターの構成方法  
 構成する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]メッセージを受信するデータ変更を次のバインドのプロパティの一部またはすべてを設定します。  
  
|プロパティのバインド|値|既定値|必須/省略可|  
|----------------------|-----------|-------------|------------------------|  
|**InboundOperationType**|値が 設定されていることを確認してください**ポーリング**です。|ポーリング|必須。 以外の場合に明示的に設定、既定値に適用されます。|  
|**PolledDataAvailableStatement**|すべてのデータが特定のテーブルのポーリングに使用できるかどうかを判断するために実行する SELECT ステートメントを指定します。 指定されたステートメントは、結果の行と列で構成されるセットを返す必要があります。 結果セットの最初のセルの値では、アダプターが指定された値を実行するかどうかを示します、 **PollingInput**プロパティをバインドします。 結果の最初のセルには正の値が含まれている場合、アダプターは、ポーリング ステートメントを実行します。 たとえば、このバインディングのプロパティの有効なステートメントになります。<br /><br /> `Select * from <table_name>`<br /><br /> **注:** のストアド プロシージャをこのバインドのプロパティを指定する必要があります。 また、このステートメントでは、Oracle E-business Suite または基になる Oracle データベースのデータは変更する必要があります。|null|必須。|  
|**PollingAction**|ポーリング操作のアクションを指定します。 使用して、操作を生成するメタデータから特定の操作についてのポーリング動作を指定できます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。|null|テーブルとビューの SELECT ステートメントを使用してポーリング操作の省略可能です。|  
|**PollingInput**|次のいずれかを指定します。<br /><br /> Oracle E-business Suite に対して実行される SQL SELECT ステートメント。 このステートメントは、FOR UPDATE 句を含める必要があります。 FOR UPDATE 句の詳細については、次を参照してください。[ポーリング ステートメントでの UPDATE 句を指定する](#ForUpdate)このトピックで後述します。<br /><br /> ストアド プロシージャ、関数、またはプロシージャまたは関数にポーリングするパッケージ内のメッセージを要求します。|null|必須。 設定**PollingInput** null 以外の値にポーリングを有効にします。|  
|**PollingInterval**|Oracle E-business Suite のクエリにアダプターを使用する秒単位で、間隔に設定されます。 このプロパティは、ポーリング間隔とポーリング トランザクションのタイムアウトを指定します。値は、クライアントがクエリ データを処理し、ポーリング応答メッセージを返すにかかる時間の時間が加え (が指定されている) Oracle E-business Suite の場合、ポーリング後ステートメントは、クエリの実行に要する時間より大きくなければなりません。|30|必須。 以外の場合に明示的に設定、既定値に適用されます。|  
|**PollWhileDataFound**|指定するかどうか、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ポーリング間隔を無視し、データがポーリングするテーブルで使用できる場合、Oracle E-business Suite を継続的にポーリングします。 指定されたポーリング間隔で SQL ステートメントを実行する、テーブルで使用できるデータがない場合は、アダプターを元に戻します|False|必須。 以外の場合に明示的に設定、既定値に適用されます。|  
|**PostPollStatement**|クエリが実行されるが、クエリの前に、データがクライアントに返される後に、アダプターによって実行される省略可能な PL/SQL コード ブロックに設定されます。|null|省略可。 値が指定されていない場合、ポーリング後ステートメントは実行されません。|  
  
> [!NOTE]
>  WCF サービス モデルまたは WCF チャネル モデルを使用している場合、必要がありますも設定する、 **AcceptCredentialsInUri**プロパティをバインドします。  
  
##  <a name="ForUpdate"></a>ポーリング ステートメントの句を更新 FOR を指定します。  
 ポーリング ステートメントと SELECT ステートメントで指定された行に影響するポーリング後ステートメントを実行すると、SELECT ステートメントを使用している場合は、ポーリング ステートメントで FOR UPDATE 句を使用する必要があります。 ポーリング ステートメントによって選択したレコードが、トランザクション中にロックされていることと、ポーリング後ステートメントがそれらに必要な更新を実行できることにより、FOR UPDATE 句を指定します。  
  
> [!CAUTION]
>  内のどこにポーリングし、ポーリング後ステートメントの間の時間枠のシナリオを持つことができますより多くのレコードは、ポーリング後ステートメントの条件を満たすテーブルに追加されます。 このような状況では、条件を満たすすべてのレコードと、ポーリング ステートメントの一部として選択されているレコードだけでなく、ポーリング後ステートメントを更新します。  
  
 ポーリング後ステートメントが指定されている、ポーリング ステートメントに FOR UPDATE 句が含まれていない場合は、次の 2 つの条件のいずれかが発生します。  
  
-   場合**TransactionIsolationLevel**に設定されている**ReadCommitted**、後のポーリング クエリでは、選択した行は更新されません。  
  
-   場合**TransactionIsolationLevel**に設定されている**Serializable**、次のシステム例外の対象 (**Microsoft.ServiceModel.Channels.Common.TargetSystemException**)、ポーリング後ステートメントが実行されたときに発生します。"ora-08177 シリアル化できませんこのトランザクションへのアクセス"です。 このような場合は、設定する必要があります、 **PollingRetryCount**数を定義するプロパティのバインド アダプターは、同じトランザクションを再試行する回数。  
  
 トランザクション分離レベルを設定する方法の手順については、次を参照してください。 [Oracle E-business Suite でのトランザクション分離レベルとトランザクションのタイムアウトを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)です。  
  
 トランザクションとの値を使用するアダプターのクライアントが構成されている場合、ポーリング ステートメントとポーリング後ステートメントがトランザクションで実行される、 **UseAmbientTransaction**に設定されているプロパティのバインド**True**アダプターでします。  
  
 FOR UPDATE オプションを使用して、ポーリング クエリの例を示します。  
  
```  
SELECT * from EMP WHERE FLAG = 'Y' FOR UPDATE  
```  
  
### <a name="specifying-a-nowait-clause-in-the-polling-statement"></a>ポーリング ステートメントで NOWAIT 句を指定します。  
 同時実行スレッドがポーリングされて、テーブルにアクセスするシナリオがありますが多すぎます競合テーブル内に先行します。 テーブルの行のロックを取得するブロックされるまでに、ポーリング クエリがあります。 ポーリング ステートメントと SELECT ステートメントを使用する場合は、SELECT ステートメントで FOR UPDATE キーワードと共に NOWAIT キーワードを指定します。 これにより、アダプターを選択しようとして、ポーリング クエリの行にロックがあるかどうかにすぐに返す内でのポーリング クエリの実行。 例外は通常このような条件下で Oracle によってスローされます。 アダプターのクライアントを再び使用することがあります、 **PollingInterval**データをポーリングする時間間隔後アダプター クライアントが再試行する必要がありますを指定するプロパティをバインドします。  
  
 NOWAIT オプションを使用して、ポーリング クエリの例を示します。  
  
```  
SELECT * from EMP WHERE FLAG = 'Y' FOR UPDATE NOWAIT  
```  
  
### <a name="specifying-a-skip-locked-clause-in-the-polling-statement"></a>ポーリング ステートメントで SKIP ロック句を指定します。  
 ここで同時実行スレッドをポーリングするテーブルにアクセスするため、ポーリング クエリで指定した WHERE 句の結果セット内のいくつかの行がロックされているシナリオがあります。 たとえば、ポーリング クエリがテーブルから 6 つの行を返します他のトランザクションのため、これら 6 つの行外の 4 はロックアウトされています。 この場合、WHERE 句で指定された行をロックして、既にロックされていることが判明しているすべての行をスキップするを試行するように指示される FOR UPDATE キーワードと共に SKIP がロックされているキーワードを指定することができます。 トランザクション中に、WHERE 句でロックされていない行がロックされている、ポーリング後ステートメントは、これらの行が再度ポーリングされませんようにの必要な更新を実行できます。 これにより、メッセージを受信する、ポーリングの WHERE 句によってロックされていないすべての行を指定するまで待機する必要はありません。  
  
 ロックされたスキップ キーワードは、データベース内の同じテーブルをポーリングしている複数のコンピューターでアダプターのクライアントが存在するシナリオに便利です。 WHERE 句で指定された時間、その時点でのロック解除されている行のデータの変更のポーリングに基づくメッセージが表示されるように、ポーリング操作を構成することによってアダプターのクライアント間での負荷し、ことを確認する行を更新できます。クライアントがアダプターによってポーリング ベースのデータ変更メッセージを受信する場合、その他のクライアントは発生しません、同じメッセージ。  
  
 ロックされたスキップ オプションを使用して、ポーリング クエリの例を示します。  
  
```  
SELECT * from EMP WHERE FLAG = 'Y' FOR UPDATE SKIP LOCKED  
```  
  
## <a name="support-for-ordered-delivery-fifo"></a>順次配送 (FIFO) のサポート  
 運用環境では、Oracle E-business Suite でデータ変更を監視するポーリングを使用できます。 これらのデータ変更のメッセージがアダプターを使用してクライアントによって受信されて、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 ビジネス シナリオに基づいて、だということ、正しい順序でアダプターのクライアントでデータ変更のメッセージが受信したことが重要です。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]配信または最初先出しの順序をサポートしている Oracle E-business Suite からメッセージが受信される順序を維持するために (FIFO) です。 ここでは、受信シナリオにおける FIFO のサポートに関連するいくつかの考慮事項、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。  
  
-   メッセージがオーケストレーションによって処理される場合、オーケストレーションがあります設定から送られたメッセージの順次配送、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ポートを受信します。  
  
-   送信ポートで、コンテンツ ベースのルーティング) シナリオによってメッセージが処理される場合、送信ポートが設定から送られたメッセージの配信を順序付けする必要があります、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ポートを受信します。  
  
 Wcf-custom または Wcf-oracleebs アダプター プロパティが含まれる**エラー発生時に要求メッセージを保留**受信処理に失敗した要求メッセージを中断するかどうかを指定します。 このプロパティを設定することができます、**メッセージ**下にあるポートを受信する Wcf-custom または Wcf-oracleebs タブ、**エラー処理**セクションです。 次の表は、このプロパティを設定するかどうかと、メッセージのサブスクライバー (オーケストレーションまたはポート) の状態に基づいて、受信メッセージの処理方法を説明するシナリオを一覧表示します。  
  
|WCF カスタム ポートのプロパティ|参加解除状態でサブスクライバー|停止状態が参加済みでサブスクライバー|  
|-------------------------------|------------------------------------|----------------------------------------------|  
|**エラー発生時に要求メッセージを中断**プロパティ|の中断 (再開不可メッセージ) としてルーティング エラー報告が生成されます。<br /><br /> 実際のメッセージが中断されていません。<br /><br /> -Post のトランザクションが中止を取得すると、ポーリング クエリは実行されません。 そのためにポーリングが繰り返され、もう一度、行がフェッチされます。<br /><br /> -エラー ログの作業内容が発生したイベントを報告します。|-できません「エラー」と見なされます。 イベント ログにエラー メッセージはありません。<br /><br /> 実際のメッセージは、中断 (再開可能) キューに配置されます。<br /><br /> -起動時、サブスクライブしているポートまたはオーケストレーション、メッセージが自動的に再開されます。 順次配送がサブスクライバーに設定されている場合は、それが受け入れられます。<br /><br /> -メッセージを手動で再開も可能性があります。|  
|**エラー発生時に要求メッセージを中断**プロパティの設定|の中断 (再開不可メッセージ) としてルーティング エラー報告が生成されます。<br /><br /> 実際のメッセージが中断されても<br /><br /> -Post のトランザクションが中止を取得すると、ポーリング クエリは実行されません。 そのためにポーリングが繰り返され、もう一度、行がフェッチされます。<br /><br /> -エラー ログの作業内容が発生したイベントを報告します。|-できません「エラー」と見なされます。 イベント ログにエラー メッセージはありません。<br /><br /> 実際のメッセージは、中断 (再開可能) キューに配置されます。<br /><br /> -起動時、サブスクライブしているポートまたはオーケストレーション、メッセージが自動的に再開されます。 順次配送がサブスクライバーに設定されている場合は、それが受け入れられます。<br /><br /> -メッセージを手動で再開も可能性があります。|  
  
## <a name="see-also"></a>参照  
 [開発アクティビティ](../../esb-toolkit/development-activities.md)   
 [BizTalk Server を使用してポーリング Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md)