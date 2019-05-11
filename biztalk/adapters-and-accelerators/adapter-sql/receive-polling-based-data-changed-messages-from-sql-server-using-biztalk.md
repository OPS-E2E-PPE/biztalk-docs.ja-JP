---
title: BizTalk Server を使用して SQL Server からのポーリングに基づいたデータ変更メッセージの受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ecaf6f7-974b-4487-8c65-d1ab628cbfeb
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe32e1d20925818b813a0b9ad40183068a27f61a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368624"
---
# <a name="receive-polling-based-data-changed-messages-from-sql-server-using-biztalk-server"></a>BizTalk Server を使用して SQL Server からのポーリングに基づいたデータ変更メッセージを受信します。
構成することができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server テーブルまたはビューの定期的なデータ変更メッセージを受信します。 データベースをポーリングするアダプターを実行するポーリング ステートメントを指定することができます。 ポーリング ステートメントには、SELECT ステートメントまたはストアド プロシージャを返す結果セットを使用できます。  

  
 アダプターがポーリングをサポートする方法の詳細については、次を参照してください。[のポーリング サポート](https://msdn.microsoft.com/library/dd788416.aspx)します。 ポーリング操作用の SOAP メッセージの構造については、次を参照してください。 [Polling 操作と TypedPolling 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)します。  
  
> [!NOTE]
>  このトピックでは、使用する方法を示します、**ポーリング**ポーリング メッセージを使用する操作を受信します。 ポーリング操作のメッセージは厳密に型指定ではありませんし、実行時に、メッセージと共にポーリングされているオブジェクトのスキーマを取得します。 使用する必要がありますを厳密に型指定されたポーリング メッセージを取得する場合、 **TypedPolling**操作。 使用することも必要があります、 **TypedPolling**工程に 1 つの BizTalk アプリケーションで複数の操作をポーリングします。 手順を実行する方法について**TypedPolling**操作を参照してください[SQL Server を使用して BizTalk Server からデータ変更のポーリングに基づいたメッセージを受信厳密に型指定された](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md)します。  
  
> [!IMPORTANT]
>  1 つの BizTalk アプリケーションでは、複数のポーリング操作を必要するかどうか、指定する必要あります、 **InboundID**接続して一意の URI の一部として接続プロパティです。 一意接続 URI を複数作成できます、同じデータベースまたはデータベースでも同じテーブルをポーリングするポートを受信します。 詳細については、次を参照してください。[受信ポーリング メッセージ間で複数受信ポートから BizTalk Server を使用して SQL](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)します。  
  
## <a name="how-this-topic-demonstrates-polling"></a>このトピックでポーリングしていますか  
 示すために、このトピックでどのように[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]データの受信をサポートは、メッセージの変更、BizTalk プロジェクトを作成し、スキーマを生成、**ポーリング**操作。 ポーリングを指定する場合は、関連するデザイン時にプロパティをバインドする、指定、 **PolledDataAvailableStatement**として。  
  
```  
SELECT COUNT(*) FROM Employee  
```  
  
 **PolledDataAvailableStatement**正の値を格納している最初のセルを含む結果セットを返す必要があります。 最初のセルに正の値が含まれていない場合でも、アダプターでは、ポーリング ステートメントは実行されません。  
  
 ポーリング ステートメントの一部として、次の操作を実行します。  
  
- Employee テーブルからすべての行を選択します。  
  
- ストアド プロシージャ、EmployeeHistory テーブルに、Employee テーブルからすべてのレコードを移動するには、(MOVE_EMP_DATA) を実行します。  
  
- Employee テーブルに新しいレコードを追加するには、(ADD_EMP_DETAILS) ストアド プロシージャを実行します。 この手順は、従業員の名前、表記、および給与をパラメーターとして受け取ります。  
  
  これらの操作を実行するは、次を指定する必要があります、 **PollingStatement**プロパティをバインドします。  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 ポーリング ステートメントが実行された後に Employee テーブルからすべてのレコードが選択されているし、SQL Server からのメッセージが受信場所を削除します。 アダプターによって MOVE_EMP_DATA ストアド プロシージャを実行すると、すべてのレコードが EmployeeHistory テーブルに移動されます。 次に、Employee テーブルに新しいレコードを追加する ADD_EMP_DETAILS ストアド プロシージャが実行されます。 次のポーリングの実行は、1 つのレコードのみ戻ります。 このサイクルは、受信を無効にするまで SQL Server をポーリングするポート。  
  
## <a name="configuring-a-polling-query-with-the-sql-adapter-binding-properties"></a>SQL アダプターのプロパティのバインドと、ポーリング クエリの構成  
 次の表にまとめたものです、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドのプロパティのデータ変更メッセージを受信するアダプターを構成するために使用します。 受信ポートを構成するときにこれらのバインドのプロパティを指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
> [!NOTE]
>  スキーマを生成するときに、これらのバインドのプロパティを指定することができます、**ポーリング**は必須でない場合でも、操作します。 ポートのバインド ファイルをこのようにする場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部にもバインドのプロパティで指定する値が含まれているが生成されます。 後でこのバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロパティは既に設定されています。 バインドで wcf-custom または WCF SQL を作成する管理コンソールの受信ポート。 バインド ファイルを使用してポートを作成する方法の詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)します。  
  
|         プロパティのバインド         |                                                                                                                                                                                                                                         説明                                                                                                                                                                                                                                          |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                             実行するかどうかを指定します**ポーリング**、 **TypedPolling**、または**通知**操作を受信します。 既定値は**ポーリング**します。                                                                                                                                                                              |
| **PolledDataAvailableStatement** |                                                                                       すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。 SQL ステートメントには、結果の行と列で構成されるセットを返す必要があります。 SQL ステートメントが指定した行を使用できる場合のみ、 **PollingStatement**プロパティのバインドが実行されます。                                                                                       |
|   **PollingIntervalInSeconds**   |                         秒単位で間隔を指定、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]に指定されたステートメントが実行される、 **PolledDataAvailableStatement**プロパティをバインドします。 既定値は 30 秒です。 ポーリング間隔は、連続するポーリングの間隔を決定します。 ステートメントは、指定した期間内で実行される、アダプターは、残りの時間間隔での待機します。                          |
|       **PollingStatement**       | SQL Server データベースのテーブルをポーリングする SQL ステートメントを指定します。 単純な SELECT ステートメントまたはストアド プロシージャのポーリング ステートメントを指定することができます。 既定値は null です。 値を指定する必要があります**PollingStatement**ポーリングを有効にします。 ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。 セミコロンで区切られた SQL ステートメントの任意の数を指定できます。 |
|      **PollWhileDataFound**      |                            指定するかどうか、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ポーリング間隔を無視し、継続的に指定された SQL ステートメントを実行、 **PolledDataAvailableStatement**データがポーリングされるテーブルで使用できる場合は、プロパティをバインドします。 テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔で SQL ステートメントを実行する元に戻します。 既定値は**false**します。                             |
  
 これらのプロパティの詳細については、次を参照してください。 [for SQL Server アダプターのバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。 使用する方法の詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を SQL Server をポーリングするには、さらに読み進める。  
  
## <a name="how-to-receive-data-change-messages-from-the-sql-server-database"></a>SQL Server データベースからデータ変更メッセージを受信する方法  
 SQL Server データベースを使用して、操作を実行[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)します。 これらのタスクはデータ変更メッセージを受信するアダプターを構成するには。  
  
1. BizTalk プロジェクトを作成しのスキーマを生成し、**ポーリング**操作。 値を指定する、必要に応じて、 **PolledDataAvailableStatement**と**PollingStatement**プロパティをバインドします。  
  
2. SQL Server データベースからメッセージを受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
3. SQL Server データベースからメッセージを受信して、フォルダーに保存するオーケストレーションを作成します。  
  
4. ビルドし、BizTalk プロジェクトを配置します。  
  
5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
   > [!IMPORTANT]
   >  受信のポーリングのシナリオは、Wcf-custom の一方向常に構成する必要があります。 または WCF SQL 受信ポート。 Wcf-custom または WCF-SQL の双方向受信ポートの受信操作はサポートされていません。  
  
6. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 スキーマを生成する必要があります、**ポーリング**操作。 参照してください[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)スキーマを生成する方法の詳細について。 スキーマを生成するときに、次のタスクを実行します。 デザイン時のバインドのプロパティを指定しない場合は、最初の手順をスキップします。  
  
1.  値を指定**PolledDataAvailableStatement**と**PollingStatement**スキーマの生成中にプロパティをバインドします。 このバインドのプロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。  
  
     バインドのプロパティを指定する方法については、次を参照してください。 [SQL アダプタのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)します。  
  
2.  コントラクトの種類を選択します。**サービス (受信操作)** します。  
  
3.  スキーマの生成、**ポーリング**操作。  
  
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
    |[Identifier]|型**受信**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選択と*PollingQuery.Polling*ここで、 *PollingQuery* BizTalk プロジェクトの名前を指定します。 *ポーリング*に対して生成されたスキーマには、**ポーリング**操作。|  
  
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
|ReceiveMessage|-設定**メッセージ**に*受信*<br /><br /> -設定**操作**に*SQLReceivePort.Polling.Request*|  
|SaveMessage|-設定**メッセージ**に*受信*<br /><br /> -設定**操作**に*SaveMessagePort.Polling.Request*|  
  
 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、次を参照してください。[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)します。 
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 チュートリアルについては、次を参照してください。[チュートリアル。基本的な BizTalk アプリケーション展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)します。  
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーション、SQL Server データベースからメッセージをドロップできる場所での場所を定義します。 これらのメッセージは、受信ポートの指定したポーリング ステートメントへの応答になります。  
  
  - WCF-SQL の一方向受信ポートまたは物理 Wcf-custom を定義します。 このポートは、ポートを指定するポーリング ステートメントを使用して SQL Server データベースをポーリングします。 ポートを作成する方法については、次を参照してください。 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)します。 受信ポートのバインドのプロパティを指定することを確認します。  
  
    > [!IMPORTANT]
    >  デザイン時のバインドのプロパティが指定されている場合は、この手順を実行する必要はありません。 このような場合は、WCF カスタムを作成または WCF-SQL によって作成されたバインド ファイルをインポートすることによって、必要なバインドのプロパティを設定すると、ポートを受信する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)します。  
  
    |プロパティのバインド|値|  
    |----------------------|-----------|  
    |**InboundOperationType**|これを設定することを確認**ポーリング**します。|  
    |**PolledDataAvailableStatement**|SQL ステートメントを指定することを確認します。 このトピックでは、次のように指定します。<br /><br /> `SELECT COUNT(*) FROM Employee`|  
    |**PollingStatement**|ポーリング ステートメントを指定することを確認します。 このトピックでは、次のように指定します。<br /><br /> `SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000`|  
  
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
  
- アダプターの実行、 **PolledDataAvailableStatement**従業員テーブルし、テーブルがポーリングのレコードを決定します。  
  
- アダプターは、ポーリング ステートメントを実行します。 ポーリング ステートメントと SELECT ステートメントおよびストアド プロシージャは、アダプターは、その他の後に 1 つのすべてのステートメントを実行します。  
  
  - アダプターは、まず、従業員テーブル内のすべてのレコードを返す SELECT ステートメントを実行します。  
  
  - アダプターは、EmployeeHistory テーブルに、Employee テーブルからすべてのデータを移動する MOVE_EMP_DATA ストアド プロシージャを実行します。 このストアド プロシージャでは、任意の値は返されません。  
  
  - アダプターは、Employee テーブルに 1 つのレコードを追加する ADD_EMP_DETAILS ストアド プロシージャを実行します。 このストアド プロシージャは、挿入されたレコードの従業員 ID を返します。  
  
    そのため、SQL Server から受信したメッセージは (SELECT ステートメントのおよび ADD_EMP_DETAILS ストアド プロシージャの) 複数の結果セットが格納され、次のようになります。  
  
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
  
   前の応答には、2 つのデータ セットが含まれています。 最初のデータ セットには、SELECT ステートメントの応答が含まれています。 SELECT ステートメントでは、Employee テーブルのすべてのレコードを選択します。 2 番目のデータ セットは、ADD_EMP_DETAILS ストアド プロシージャのです。 このストアド プロシージャでは、Employee テーブルにレコードを追加し、新しいレコードの従業員 ID を返します。  
  
  > [!NOTE]
  >  MOVE_EMP_DATA ストアド プロシージャでは、結果セットは返されません。 そのため、セットがない対応するデータ、応答メッセージにします。  
  
- アダプターが実行される場合、 **PollDataAvailableStatement** ADD_EMP_DETAILS で挿入されたレコードを 1 つのストアド プロシージャをもう一度検索します。 アダプターが指定されているすべての 3 つのステートメントを実行し、 **PollingStatement**プロパティをバインドします。 このとき、SQL Server からの応答には、SELECT ステートメントの 1 つのレコードが含まれていて、ストアド プロシージャの 1 つのレコード、ADD_EMP_DETAILS。 すべての後続のポーリングには、同様の応答が返されます。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ポーリングからの受信ポートを明示的に無効にするまでは引き続き、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定、ファイルからインポートできます。 バインド ファイルの詳細については、次を参照してください。[アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)します。
  
## <a name="see-also"></a>参照  
 [BizTalk Server と SQL アダプタを使用して SQL Server をポーリング](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)