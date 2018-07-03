---
title: Oracle データベースの BizTalk アダプターの機能をキー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- features, operations-related
- adapters, new and deprecated features
- features, technology-related
- features, new and deprecated
- features, performance-related
- features, metadata-related
ms.assetid: 7e79714c-1472-4721-a693-5be2a9a0cd1f
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e63212e0f0c77e020ea4ad1a43639dff09cd7654
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995691"
---
# <a name="key-features-in-biztalk-adapter-for-oracle-database"></a>BizTalk Adapter for Oracle Database の主要な機能
このセクションでは、新しいと非推奨の機能を示します[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]します。  

  
## <a name="technology-related-features"></a>テクノロジ関連の機能  
  
|                   機能                    |                                                                                                                                                                                                                                                                                                                                                                                                     解説                                                                                                                                                                                                                                                                                                                                                                                                     |
|----------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Oracle データベースに接続する新しい方法 | (以前のバージョンのアダプター) のように tnsnames.ora ファイルで、net サービス名を使用して Oracle データベース アダプターに接続するとは別のクライアントもに接続できます、Oracle データベース、接続パラメーターを指定することで直接ためnet サービス名または tnsnames.ora ファイルを使用する必要はありません。 Oracle データベースへの接続に tnsnames.ora ファイルを必要としないを保存する接続パラメーター (net サービス名) を手動で更新する負担からすべてのクライアント コンピューターで tnsnames.ora ファイルで追加またはで Oracle サーバーを更新するときに、環境。 詳細については、次を参照してください。 [Oracle データベースへの接続を作成する](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)します。 |
|      Windows 認証のサポート      |                                                                                                アダプターのクライアントは、Oracle データベースへの接続に Windows 認証を使用できます。 Windows 認証では、Windows のログオン資格情報に基づいて、ユーザーの id を確認することができ、Windows 環境の組み込みのセキュリティを活用できます。 Windows 認証の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[、Oracle データベースを使用して Windows 認証への接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)します。                                                                                                |
  
## <a name="operations-related-features"></a>操作に関連の機能 
  
|                                   機能                                    |                                                                                                                                                                                                                                                                                                                                                              解説                                                                                                                                                                                                                                                                                                                                                              |
|------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         挿入操作のインラインの値を指定するためのサポート         |                                                    使用することができます、 **InlineValue** Oracle データベースのテーブルまたはビューに計算値を挿入する挿入操作の属性。 省略可能な属性は、これは、複数のレコードの挿入操作ですべての単純なデータ レコードの使用。 この属性の値を指定する場合は、レコードの指定した値が上書きされます。 InlineValue 属性の詳細については、次を参照してください。 [Insert、Update、Delete、および Oracle のテーブルとビューの操作の選択](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-and-select-operations-on-oracle-tables-and-views.md)します。                                                    |
|                               強化されたポーリング                               | [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースを定期的にポーリングするストアド プロシージャ、関数、またはパッケージ化されたプロシージャまたは関数を使用して、「ポーリング ベース」のデータ変更メッセージを受信するようになりました。 SELECT ステートメントだけでなくようになりましたストアド プロシージャ、関数、またはパッケージ化されたプロシージャを指定したり、Oracle データベースをポーリングするアダプターを定期的に実行するポーリング ステートメントとして機能できます。 ポーリングの詳細については、次を参照してください。[ポーリングの受信に基づいたデータ変更メッセージのサポート](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md)します。 |
|                 Oracle ユーザー定義型 (Udt) のサポート                 |                                                                                                                                                                [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle Udt が含まれている Oracle データベースでの成果物に対する操作の実行をサポートします。 UDT のサポートについては、次を参照してください。 [Oracle User-Defined 型 Oracle データベースでのサポート](../../adapters-and-accelerators/adapter-oracle-database/support-for-oracle-user-defined-types-in-oracle-database.md)します。                                                                                                                                                                 |
|                       複合操作のサポート                       |                                         [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアントが Oracle データベースでの複合操作を実行できるようにします。 複合操作では、および任意の順序で、次の操作の任意の数を含めることができます。<br /><br /> -テーブルおよびビューに対する操作。<br />-アダプターでの操作として、プロシージャ、関数、およびプロシージャまたは表示されるパッケージ内の関数を格納します。<br /><br /> 複合操作の詳細については、次を参照してください。[複合操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)します。                                         |
| ユーザーが所有していないスキーマでストアド プロシージャを実行するためのサポート |                           [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ユーザーは、Oracle では、スキーマに対する権限を持って提供される、現在のユーザーは、スキーマの所有者ではない場合でも、スキーマでストアド プロシージャを実行することができます。 ただし、ストアド プロシージャは、レコードの種類を使用している場合は、ストアド プロシージャと同じスキーマで、定義する必要があります。 使用してストアド プロシージャを実行する方法について、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[関数およびストアド プロシージャに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-stored-procedures1.md)します。                            |
|                  データベース変更通知のサポート                   |                                                                                                    アダプター クライアントは、トリガーを起動する SELECT ステートメントに基づいて、Oracle データベースからデータベース変更通知を受信できます。 としてアダプター クライアントを使用して、結果セットの SELECT ステートメントの変更の Oracle データベースで、通知が送信されます。 データベース変更通知の詳細については、次を参照してください。[データベース変更通知の受信に関する考慮事項](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)します。                                                                                                    |
|                             シノニムのサポート                             |                                                                                                                                       アダプターのクライアントは、テーブル、ビュー、ストアド プロシージャ、関数、およびパッケージ用に作成されたシノニムに対する操作を実行できます。 シノニム、および使用する方法については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]シノニムに対する操作を実行するには、次を参照してください。 [Oracle データベースでシノニムに対する操作](../../adapters-and-accelerators/adapter-oracle-database/operations-on-synonyms-in-oracle-database.md)します。                                                                                                                                        |
|            ブール型パラメーターと PL/SQL テーブル型のサポート             |                                                                                                                                                                                                                                                                                                 アダプター クライアントは、ストアド プロシージャとブール型パラメーターと PL/SQL テーブル型が含まれている関数で操作を実行できます。                                                                                                                                                                                                                                                                                                  |
  
### <a name="other-features"></a>その他の機能  
  
|                    機能                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                           解説                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BizTalk Server でアダプターを使用する新しい方法 | [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Biztalk WCF カスタム ポートまたは Wcf-oracledb ポートとして使用できます。 使用する場合、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF カスタム ポートには、WCF カスタム ポートが既定では、BizTalk Server 管理コンソールに追加されるため、WCF カスタム ポートを BizTalk Server 管理コンソールに追加する必要はありません。 ただし、使用する場合、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Wcf-oracledb ポートを経由する必要があります最初に追加する Wcf-oracledb アダプターの BizTalk Server 管理コンソール。 詳細については、次を参照してください。[を BizTalk Server 管理コンソールの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)します。 |
  
## <a name="deprecated-features-in-the-oracle-adapter"></a>Oracle アダプターの非推奨の機能  
 次の表に、現在のバージョンのでは非推奨の機能、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
|機能|解説|  
|-------------|-------------|  
|バインドのプロパティ|**PollingRetryCount**、 **TransactionIsolationLevel**、および**LongDataTypeColumnSize**バインドのプロパティが非推奨とされます。 <br/><br/>**注**受信操作のトランザクション分離レベルを設定するには、受信ポートを構成するときに、サービスの動作を追加することで適切な値を設定する必要があります。 トランザクション分離レベルを設定する方法の詳細については、次を参照してください。[トランザクション分離レベルの構成とトランザクション タイムアウト](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)します。|  
  
## <a name="changes-to-note"></a>変更に注意してください。

### <a name="general"></a>全般  
* REF CURSOR を IN 型のパラメーター

    -   ストアド プロシージャ内で REF カーソル値に変更されなかった場合、出力の値は、入力の REF CURSOR の値として同じになります。  
  
    -   REF CURSOR の入力と出力データは、同じ型のです。  
  
* "Nil"属性の不適切な動作: すべての単純なデータ型を"true"に nil 属性の値を設定して、フィールドまたはパラメーターの値が存在する場合、Oracle データベース アダプター不適切に渡したこと NULL の代わりに、指定した値。 この問題を回避するには、フィールドまたはパラメーターに NULL 値を渡す場合、必ずフィールドまたはパラメーターの値が指定されていないこと。 たとえば、フィールドの NULL 値を渡す"name"呼び出されます。  
  
  ```  
  <name xsi:nil="true"/>  
  ```  
* 実際、Float、および時間の長いデータ型、および選択操作の結果セット内の値の末尾に追加のゼロ (0) は切り捨てられません。 さらに、常に選択操作の結果セットは、実際の 8 の有効桁数、Float、Long データ型と値を返します。  
  
* レコードの種類のデータの処理: の値に依存するこれらのノードの値が渡される、 **SkipNilNodes**プロパティをバインドします。 このバインドのプロパティの詳細については、次を参照してください。 [for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)します。 
  
* 送信操作: 入力 XML ファイルで指定された値がないパラメーターの値は送信されません。 Oracle データベースにストアド プロシージャで既定値を指定すると、値が、アダプターによって送信されなかったため、その値を使用します。 ユーザーが入力 XML ファイルを"true"にします"nil"属性の値を設定して NULL のノードを指定する必要がありますを NULL 値が送信する必要がある場合  
  
* コマンドのタイムアウトがサポートされています。  
  
* UpdateLOB 操作は、トランザクションの一部として実行する必要があります。 これの値を確認する、 **UseAmbientTransaction**に設定するプロパティをバインドする必要があります**True**します。  
  
### <a name="biztalk-scenario"></a>BizTalk のシナリオ  
  
- 送信操作: 場合、 **UseAmbientTransaction**プロパティのバインドは、"True,"Oracle データベースの操作と、BizTalk メッセージ ボックス データベースは、同じ分散トランザクション内で実行されます。 内のトランザクションの詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターでトランザクションを処理](../../adapters-and-accelerators/adapter-oracle-database/handle-transactions-with-the-oracle-database-adapter.md)します。  
  
- 受信操作: 要求-応答を使用することはできません受信ポートの[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の受信の操作を使用して、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 のみ一方向受信ポートを使用できます。  
  
### <a name="other-scenarios"></a>その他のシナリオ  
  
- 送信操作。 アダプターはトランザクションを開始できません。 ユーザーでは、複数の行を同じトランザクション内で挿入する必要がある場合は、System.Transactions トランザクションのスコープ内で操作を実行するユーザーの責任です。 ユーザーもの値を設定する必要があります、 **UseAmbientTransaction**プロパティを**True**します。 内のトランザクションの詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターでトランザクションを処理](../../adapters-and-accelerators/adapter-oracle-database/handle-transactions-with-the-oracle-database-adapter.md)します。  
  
- 送信操作: Oracle データベースへの同じ物理接続で同じ IRequestChannel/プロキシ オブジェクトに対して実行される Sll 操作を実行することができません。  
  
- WCF チャネル モデル: [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF チャネル モデルを使用しているときに IReplyChannel をサポートしていません。 ただし、受信操作を実行するため、IInputChannel を使用することができます。 さらに、トランザクションに関して、アダプターがポーリング ステートメントを実行して、Oracle データベースに対してポーリング ステートメントを公開し、WCF ディスパッチャーが開始されたトランザクションに依存しています。 トランザクション分離レベルと、WCF ディスパッチャーが開始されたトランザクションのタイムアウトは、ServiceBehavior で適切な値を設定して制御できます。  
  
## <a name="see-also"></a>参照  
 [Oracle データベースの Biztalk アダプターを理解します。](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)