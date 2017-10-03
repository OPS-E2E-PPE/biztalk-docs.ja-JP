---
title: "Oracle データベースの重要な機能によって BizTalk Adapter |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- features, operations-related
- adapters, new and deprecated features
- features, technology-related
- features, new and deprecated
- features, performance-related
- features, metadata-related
ms.assetid: 7e79714c-1472-4721-a693-5be2a9a0cd1f
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4277c5d0691d44bdae26b6b395a91d2ecb8f093
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="key-features-in-biztalk-adapter-for-oracle-database"></a>BizTalk Adapter 用 Oracle Database の主要な機能
このセクションに一覧表示、非推奨の新機能と[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]です。  

  
## <a name="technology-related-features"></a>テクノロジに関連する機能  
  
|機能|解説|  
|-------------|-------------|  
|Oracle データベースへの接続のための新しい方法|(以前のバージョンのアダプター) のように tnsnames.ora ファイルで net サービス名を使用して Oracle データベース アダプターに接続するとは別のクライアント接続できるようも Oracle データベースに直接パラメーターを指定して、接続、およびこのインターフェイスnet サービス名または tnsnames.ora ファイルを使用する必要があります。 Oracle データベースへの接続に tnsnames.ora ファイルを必要としない済むため手間接続パラメーター (net サービス名) を手動で更新をすべてのクライアント コンピューターで tnsnames.ora ファイルで追加またはで Oracle サーバーを更新するとき、環境。 詳細については、次を参照してください。 [Oracle データベースへの接続を作成する](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)です。|  
|Windows 認証のサポート|アダプターのクライアントは、Oracle データベースへの接続に Windows 認証を使用できます。 Windows 認証では、Windows のログオン資格情報に基づくユーザーの id を確認することができますあり、したがって、Windows 環境の組み込みのセキュリティを活用することができます。 Windows 認証の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベースを使用して Windows 認証への接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)です。|  
  
## <a name="operations-related-features"></a>操作に関連する機能 
  
|機能|解説|  
|-------------|-------------|  
|挿入操作のインラインの値を指定するためのサポート|使用することができます、 **InlineValue** Oracle データベースのテーブルまたはビューに計算値を挿入する Insert 操作での属性です。 これは省略可能な属性は、複数のレコード挿入操作ですべての単純なデータ レコードの使用可能です。 この属性の値を指定する場合は、指定されたレコードの値が上書きされます。 InlineValue 属性の詳細については、次を参照してください。 [Insert、Update、Delete、および Oracle のテーブルおよびビューに対する選択操作](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-and-select-operations-on-oracle-tables-and-views.md)です。|  
|強化されたポーリング|[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]では、Oracle データベースを定期的にポーリングするストアド プロシージャ、関数、またはパッケージ化されたプロシージャまたは関数を使用して、「ポーリング ベース」のデータ変更メッセージを受信します。 だけでなく、SELECT ステートメントでは、今すぐストアド プロシージャ、関数、またはパッケージ化されたプロシージャを指定したり、アダプターが Oracle データベースをポーリングする定期的に実行されるポーリング ステートメントとして機能できます。 ポーリングの詳細については、次を参照してください。[データ変更のポーリングの受信に基づいたメッセージのサポート](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md)です。|  
|Oracle ユーザー定義型 (Udt) のサポート|[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle Udt を含む Oracle データベースでの成果物に対する操作の実行をサポートします。 UDT のサポートについては、次を参照してください。 [Oracle User-Defined 型 Oracle データベースでのサポート](../../adapters-and-accelerators/adapter-oracle-database/support-for-oracle-user-defined-types-in-oracle-database.md)です。|  
|複合操作のサポート|[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアントが Oracle データベースでの複合操作を実行できるようにします。 複合操作は、次の操作、および任意の順序で任意の数を含めることができます。<br /><br /> -テーブルおよびビューの操作です。<br />-プロシージャ、関数、およびプロシージャまたは表示されたパッケージ内で関数をアダプターでの操作として格納されます。<br /><br /> 複合操作の詳細については、次を参照してください。[複合操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)です。|  
|ユーザーによって所有されていないスキーマでストアド プロシージャを実行するためのサポート|[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle では、スキーマ上のアクセス許可がユーザーに提供される、現在のユーザーは、スキーマの所有者ではない場合でも、スキーマでストアド プロシージャを実行することができます。 ただし、ストアド プロシージャは、レコードの種類を使用している場合は、ストアド プロシージャと同じスキーマで、定義する必要があります。 使用してストアド プロシージャを実行する方法について、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[関数およびストアド プロシージャで操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-stored-procedures1.md)です。|  
|データベースの変更通知のサポート|アダプターのクライアントは、トリガーを起動する SELECT ステートメントに基づいて、Oracle データベースからデータベースの変更通知を受信できます。 としてアダプター クライアントと、結果セットの SELECT ステートメントの変更時に、Oracle データベースで通知が送信されます。 データベースの変更通知の詳細については、次を参照してください。[データベースの変更通知の受信に関する考慮事項](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)です。|  
|シノニムのサポート|アダプターのクライアントは、テーブル、ビュー、ストアド プロシージャ、関数、およびパッケージ用に作成されたシノニムに対する操作を実行できます。 シノニム、および使用する方法については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]にシノニムに対して操作を実行するには、次を参照してください。 [Oracle データベースでシノニムに対する操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-synonyms-in-oracle-database.md)です。|  
|ブール型のパラメーターと PL/SQL テーブル型のサポート|アダプターのクライアントは、ストアド プロシージャとブール型のパラメーターと PL/SQL テーブル型を含む関数で操作を実行できます。|  
  
### <a name="other-features"></a>その他の機能  
  
|機能|解説|  
|-------------|-------------|  
|BizTalk Server でアダプターを使用する新しい方法|[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で BizTalk WCF カスタム ポートまたは Wcf-oracledb ポートとして使用できます。 使用する場合、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF カスタム ポートを経由は、WCF カスタム ポートが既定では、BizTalk Server 管理コンソールに追加されるため、WCF カスタム ポートを BizTalk Server 管理コンソールに追加する必要はありません。 ただし、使用する場合、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Wcf-oracledb ポートを経由する必要があります最初、Wcf-oracledb アダプターを追加する BizTalk Server 管理コンソールです。 詳細については、次を参照してください。 [BizTalk Server 管理コンソールへの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)です。|  
  
## <a name="deprecated-features-in-the-oracle-adapter"></a>Oracle アダプターの非推奨機能  
 次の表に、現在のバージョンで廃止された機能、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
|機能|解説|  
|-------------|-------------|  
|バインドのプロパティ|**PollingRetryCount**、 **TransactionIsolationLevel**、および**LongDataTypeColumnSize**バインドのプロパティは推奨されなくなりました。 <br/><br/>**注**受信操作のトランザクション分離レベルを設定するには、受信ポートを構成するときに、サービスの動作を追加することで適切な値を設定します。 トランザクション分離レベルを設定する方法の手順については、次を参照してください。[トランザクション分離レベルの構成とトランザクションのタイムアウト](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)です。|  
  
## <a name="changes-to-note"></a>変更点

### <a name="general"></a>全般  
* REF CURSOR を IN 型のパラメーター

    -   ストアド プロシージャ内で REF カーソル値に対する変更がない場合、出力の値は入力の REF CURSOR の値と同じです。  
  
    -   REF CURSOR の入力と出力のデータでは、同じ型です。  
  
-   "Nil"属性の不適切な動作: すべての単純なデータ型の場合は"true"に nil 属性の値を設定して、フィールドまたはパラメーターの値が存在し、Oracle データベース アダプター不適切に渡したこと NULL の代わりに、指定された値。 この問題を回避するに、フィールドやパラメーターに NULL 値を渡す場合、必ずフィールドまたはパラメーターの値が指定されていないこと。 たとえば、フィールドの NULL 値を渡すに"name"という名前。  
  
    ```  
    <name xsi:nil="true"/>  
    ```  
-   Real、Float、および Long データ型、および選択操作の結果セット内の値の末尾に追加のゼロ (0) は切り捨てられません。 さらに、常に、Select 操作の結果セットは、実際の 8 有効桁数、Float、長いデータ型と値を返します。  
  
-   レコードの種類のデータの処理: の値に依存するこれらのノードについて、値が渡された、 **SkipNilNodes**プロパティをバインドします。 このバインドのプロパティの詳細については、次を参照してください。 [Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。 
  
-   送信操作: 入力 XML ファイルで指定された値がないパラメーターの値は送信されません。 Oracle データベースにストアド プロシージャで既定値を指定すると、アダプターによって値が渡されないためその値を使用します。 ユーザーが"true"の"nil"属性の値を設定して、入力 XML ファイル内の NULL ノードを指定する必要がある場合は、NULL 値は、送信する必要があります、  
  
-   コマンドのタイムアウトはサポートされています。  
  
-   UpdateLOB 操作は、トランザクションの一部として実行する必要があります。 これは、値を確認する、 **UseAmbientTransaction** binding プロパティを設定する必要があります**True**です。  
  
### <a name="biztalk-scenario"></a>BizTalk のシナリオ  
  
-   送信操作: 場合、 **UseAmbientTransaction**プロパティのバインドは、"True は、"Oracle データベースでの操作と BizTalk メッセージ ボックス データベースは、同じ分散トランザクション内で実行されます。 内のトランザクションの詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターでのトランザクションの処理](../../adapters-and-accelerators/adapter-oracle-database/handle-transactions-with-the-oracle-database-adapter.md)です。  
  
-   受信操作: 要求-応答を使用することはできません受信ポートの[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を使用して受信操作のため、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 のみ一方向受信ポートを使用できます。  
  
### <a name="other-scenarios"></a>その他のシナリオ  
  
-   送信操作: アダプターがトランザクションを開始していません。 ユーザーでは、複数の行を同じトランザクション内で挿入する必要がある場合は、System.Transactions トランザクション スコープ内で操作を実行するユーザーの責任です。 ユーザーもの値を設定する必要があります、 **UseAmbientTransaction**プロパティを**True**です。 内のトランザクションの詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターでのトランザクションの処理](../../adapters-and-accelerators/adapter-oracle-database/handle-transactions-with-the-oracle-database-adapter.md)です。  
  
-   送信操作: Oracle データベースに同じ物理的な接続で同じ IRequestChannel/プロキシ オブジェクトに対して実行される Sll 操作を実行することができません。  
  
-   WCF チャネル モデル: [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF チャネル モデルを使用しているときに IReplyChannel をサポートしていません。 ただし、IInputChannel を使用して、受信操作を実行することができます。 さらに、トランザクションに関して、アダプターがポーリング ステートメントを実行して、Oracle データベースに対してポーリング ステートメントの後、WCF ディスパッチャーが開始したトランザクションに依存しています。 ServiceBehavior で適切な値を設定して、トランザクション分離レベルと、WCF ディスパッチャーが開始したトランザクションのタイムアウトを制御できます。  
  
## <a name="see-also"></a>参照  
 [Oracle データベースの Biztalk アダプターを理解します。](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)