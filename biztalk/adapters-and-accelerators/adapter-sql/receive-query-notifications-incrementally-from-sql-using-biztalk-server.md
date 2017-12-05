---
title: "BizTalk Server を使用して SQL からの受信通知の差分クエリ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6972e01-80be-47be-986a-c2e4e0fb0cd1
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fc9eda3ba1bee61b4737428f41870fc31504e3a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="receive-query-notifications-incrementally-from-sql-using-biztalk-server"></a>BizTalk Server を使用して SQL からの受信通知の差分クエリ
> [!IMPORTANT]
>  ここでは簡略化のため、このトピックには、通知を受信する差分方法のみについて説明します。 ビジネス シナリオで、オーケストレーションは理想的には受信した通知メッセージの種類を抽出し、後続の操作を実行するためのロジックを含める必要があります。 つまり、上で説明されているオーケストレーションにこのトピックで説明されているオーケストレーションを構築する必要が[を BizTalk Server を使用して SQL の特定のタスクの完了の通知メッセージを処理](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)です。  
  
 このトピックの内容を構成する方法を示しています、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server データベースから増分クエリ通知メッセージを受信します。 インクリメンタル通知を示すためには、テーブル、従業員、"Status"列を含むを検討してください。 このテーブルに新しいレコードが挿入されると、[状態] 列の値は 0 に設定します。 通知を受信する差分、次の手順を実行して、アダプターを構成することができます。  
  
-   [状態] 列が 0 であるすべてのレコードを取得する SQL ステートメントを使用して通知を登録します。 これを行うための SQL ステートメントを指定することによって、 **NotificationStatement**プロパティをバインドします。  
  
-   通知のメッセージが受信された行のためには、1 にステータス列を更新します。  
  
 このトピックでは、BizTalk オーケストレーションを作成してこれを実現する BizTalk アプリケーションを構成する方法を示します。  
  
## <a name="configuring-notifications-with-the-sql-adapter-binding-properties"></a>SQL アダプターのプロパティのバインドと通知の構成  
 次の表、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドのプロパティ構成の SQL Server から通知を受信するために使用します。 受信ポートを構成するときにこれらのバインディング プロパティを指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
> [!NOTE]
>  スキーマを生成するときに、これらのバインディング プロパティを指定することもできます、**通知**操作、必須ではない場合でもです。 これを行うと、ポートのバインド ファイル、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成され、メタデータの生成の一部では、バインドのプロパティを指定する値も含まれます。 このバインド ファイルを後でインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロパティは既に設定されています。 バインドで wcf-custom または WCF SQL を作成する管理コンソールの受信ポート。 詳細については、バインド ファイルを使用するポートを作成する、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)です。  
  
|プロパティのバインド|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|受信操作を実行することを指定します。 通知メッセージを受信するには、これを設定**通知**です。|  
|**NotificationStatement**|SQL ステートメントを指定します (選択または EXEC\<ストアド プロシージャ\>) のクエリ通知を登録するために使用します。 アダプターは、指定された SQL ステートメントの変更の結果セットの場合にのみ、SQL Server から通知メッセージを取得します。|  
|**NotifyOnListenerStart**|リスナーが開始されたときに、アダプターがアダプターのクライアントに通知を送信するかどうかを指定します。|  
  
 これらのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。 使用する方法の詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]さらに通知を受信する SQL Server から、読み取る。  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a>どのように、このトピックでは通知メッセージの受信を示しています  
 示すためにどのように[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]SQL Server からの通知メッセージの受信をサポートするには、このトピックは Employee テーブルへの変更の通知を受信するアダプターを構成する方法をデモンストレーションします。 Employee テーブルの列 Employee_ID、名、および状態であると仮定します。 新しい従業員が追加されるたびに、[状態] 列の値は 0 に設定します。  
  
 通知の受信を示すためには、次の操作を行います。  
  
-   スキーマを生成、**通知**(受信操作)、および**選択**(送信操作) Employee テーブルにします。  
  
-   次のあるオーケストレーションを作成します。  
  
    -   通知メッセージを受信する受信場所。 通知として SELECT ステートメントを指定することによって構成できます。  
  
        ```  
        SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0  
        ```  
  
        > [!NOTE]
        >  具体的には、これで示すように、ステートメント内の列名の SELECT ステートメントを指定する必要があります。 また、スキーマ名と共に、テーブル名を必ず指定する必要があります。 たとえば、 `dbo.Employee`のようにします。  
  
    -   通知が既に送信されている行を更新する送信ポートです。 1 に [状態] 列の値を設定します。 選択操作の一部としてこのは、アダプターに、次のメッセージを送信することによって行うことができます。  
  
        ```  
        <Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
          <Columns>Employee_ID,Name,Status</Columns>  
          <Query>where Status=0;UPDATE Employee SET Status=1 WHERE Status=0</Query>  
        </Select>  
        ```  
  
         一部としてこのメッセージに、 `<Query>` [状態] 列を更新する UPDATE ステートメントを指定する要素。 この操作は、処理された行が更新されるようにメッセージ通知の受信後に実行する必要がありますに注意してください。 通知応答を取得するまで待機し、行を更新する要求メッセージを手動で削除のオーバーヘッドが除去には、オーケストレーション自体内の行を更新するため、要求メッセージを生成するされます。 これを行うを使用して、**メッセージの構築**図形をオーケストレーション内です。  
  
## <a name="how-to-receive-notification-messages-from-the-sql-server-database"></a>SQL Server データベースから通知メッセージを受信する方法  
 SQL Server データベースを使用して、操作を実行[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明する手順のタスクでは、 [SQL アダプターと BizTalk アプリケーションを開発する基盤](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)です。 これらのタスクは通知メッセージを受信アダプターを構成するのには。  
  
1.  BizTalk プロジェクトを作成しのスキーマを生成、**通知**(受信操作) と**選択**(送信操作) Employee テーブルにします。 必要に応じての値を指定することができます、 **InboundOperationType**と**NotificationStatement**プロパティをバインドします。  
  
2.  SQL Server データベースから通知を受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  SQL Server データベース上の情報を選択を実行して、応答メッセージの受信用の BizTalk プロジェクトでメッセージを作成します。  
  
4.  次のオーケストレーションを作成します。  
  
    -   SQL Server から通知メッセージを受信します。  
  
    -   選択し、通知を受信した行を更新するメッセージを作成します。  
  
    -   行を更新する SQL Server にこのメッセージを送信し、応答を受信します。  
  
5.  構築し、BizTalk プロジェクトを展開します。  
  
6.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
    > [!NOTE]
    >  通知メッセージを受信するように、受信操作の一方向の WCF カスタムのみを構成する必要があります。 または WCF SQL 受信ポート。 双方向の WCF カスタムまたは WCF SQL 受信ポートの受信操作はサポートされていません。  
  
7.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックの内容に基づくサンプル  
 サンプルは、IncrementalNotification、このトピックの内容に基づいてが付属して、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。 [SQL アダプタ サンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)です。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 スキーマを生成する必要があります、**通知**操作と**選択**Employee テーブルに対して操作します。 参照してください[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)スキーマを生成する方法についての詳細。 スキーマを生成するときに、次のタスクを実行します。 デザイン時のバインドのプロパティを指定しない場合は、最初の手順をスキップします。  
  
1.  値を指定**InboundOperationType**と**NotificationStatement**スキーマの生成中にプロパティをバインドします。 このバインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。 バインドのプロパティを指定する方法については、次を参照してください。 [SQL アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)です。  
  
2.  コントラクトの種類を選択して**サービス (入力方向の操作)**です。  
  
3.  スキーマを生成、**通知**操作します。  
  
4.  コントラクトの種類を選択して**クライアント (送信操作)**です。  
  
5.  スキーマを生成、**選択**操作**従業員**テーブル。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 スキーマが生成されるは、BizTalk プロジェクトのオーケストレーションの種類からのメッセージをリンクする必要があります。  
  
 このトピックでは、3 つのメッセージを作成する必要があります-通知を受信する SQL Server データベース、Select 操作を実行する 1 つの Select 操作の応答を受信する 1 つからいずれか。  
  
 メッセージを作成し、それらのスキーマにリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**です。  
  
2.  まだ開いていない場合は、BizTalk プロジェクトのオーケストレーション ビュー ウィンドウを開きます。 をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。  
  
3.  **オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。  
  
4.  新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。  
  
5.  **プロパティ**ウィンドウ**Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`NotifyReceive`.|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*SQLNotify.Notification*ここで、 *SQLNotify* BizTalk プロジェクトの名前を指定します。 *通知*に対して生成されたスキーマは、**通知**操作します。|  
  
6.  手順 3 を繰り返して 2 つの新しいメッセージを作成します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |識別子に設定します。|メッセージの種類を設定|  
    |-----------------------|-------------------------|  
    |Select|*SQLNotify.TableOperation_dbo_Employee.Select*ここで、 *TableOperation_dbo_Employee*に対して生成されたスキーマは、**選択**操作|  
    |SelectResponse|*SQLNotify.TableOperation_dbo_Employee.SelectResponse*|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の SQL Server データベースから通知メッセージを受信し、通知を受信した行を更新します。 このオーケストレーションでの指定した SELECT ステートメントに基づく通知メッセージを受信、 **NotificationStatement**プロパティをバインドします。 通知メッセージは、ファイルの場所で受信されます。 応答が受信されると、オーケストレーションは、通知を受信した行の更新に使用されるメッセージを構築します。 このメッセージの応答を同じファイルの場所にも受信します。  
  
 そのため、オーケストレーションは、次が必要があります。  
  
-   一方向の受信ポートを通知メッセージを受信します。  
  
-   双方向の送信ポートの行を更新し、同じの応答を受信するメッセージを送信します。  
  
-   A**メッセージの構築**図形をオーケストレーション内で、更新操作を実行する、メッセージを構築します。  
  
-   ファイルは、更新操作の応答を保存するポートを送信します。  
  
-   受信図形と送信図形。  
  
 サンプル オーケストレーションには、次のようになります。  
  
 ![SQL Server の通知を受信するオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/f13ad3b8-8161-42e5-a521-424bbf549ad5.gif "f13ad3b8-8161-42e5-a521-424bbf549ad5")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。 図形 列に表示名は、単に記載されているオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveNotification|Receive|-設定**名前**に*ReceiveNotification*<br /><br /> -設定**アクティブ**に*は True。*|  
|SaveNotification|Send|-設定**名前**に*SaveNotification*|  
|SendSelectMessage|Send|-設定**名前**に*SendSelectMessage*|  
|ReceiveSelectResponse|Receive|-設定**名前**に*ReceiveSelectResponse*|  
|SaveSelectResponse|Send|-設定**名前**に*SaveSelectResponse*|  
  
### <a name="adding-construct-message-shape"></a>メッセージの構築図形を追加します。  
 使用することができます、**メッセージの構築**図形を選択操作を実行する操作内で要求メッセージを生成します。 これを行うには、追加する必要があります、**メッセージの構築**図形という、**メッセージの割り当て**図形をオーケストレーションにします。 この例で、**メッセージの割り当て**図形が選択操作を実行する SQL Server に送信されるメッセージを生成するコードを呼び出します。 **メッセージの割り当て**図形も、SQL Server に送信するメッセージに対するアクションを設定します。  
  
 メッセージの構築図形、設定、**メッセージ構築**プロパティを**選択**です。  
  
 応答を生成するコードは、BizTalk プロジェクトと同じ Visual Studio ソリューションの一部になります。 応答メッセージを生成するためのサンプル コードは、次のように検索します。  
  
```  
namespace SampleMessageCreator  
{  
    public class SampleMessageCreator  
    {  
        private static XmlDocument Message;  
        private static string XmlFileLocation;  
        private static string ResponseDoc;  
        public static XmlDocument XMLMessageCreator()  
        {  
            XmlFileLocation = "C:\\TestLocation\\CreateMessage";  
            try  
            {  
                ResponseDoc = (Directory.GetFiles(XmlFileLocation, "*.xml", SearchOption.TopDirectoryOnly))[0];  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Trying to get XML from: " + XmlFileLocation);  
                Console.WriteLine("EXCEPTION: " + ex.ToString());  
                throw ex;  
            }  
            //Create Message From XML  
            Message = new XmlDocument();  
            Message.PreserveWhitespace = true;  
            Message.Load(ResponseDoc);  
            return Message;  
        }   
    }  
}  
```  
  
 要求メッセージを生成できる上記のコードの抜粋をする必要があります (従業員テーブルに対する Select 操作) の XML 要求メッセージの指定した場所に、`XmlFileLocation`変数。  
  
> [!NOTE]
>  プロジェクトをビルドした後、SampleMessageCreator.dll はプロジェクト ディレクトリに作成されます。 グローバル アセンブリ キャッシュ (GAC) には、この DLL を追加する必要があります。 また、BizTalk プロジェクトに参照として、SampleMessageCreator.dll を追加する必要があります。  
  
 次のコードを呼び出すには、次の式を追加、**メッセージの割り当て**図形とメッセージのアクションを設定します。 式を追加するにはダブルクリック、**メッセージの割り当て**図形式エディターを開きます。  
  
```  
Select = SampleMessageCreator.SampleMessageCreator.XMLMessageCreator();  
Select(WCF.Action) = "TableOp/Select/dbo/Employee";  
```  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認してください。 ポート列に表示される名前は、オーケストレーションで表示されているポートの名前です。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|SQLNotifyPort|-設定**識別子**に*SQLNotifyPort*<br /><br /> -設定**型**に*SQLNotifyPortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*受信*|  
|SaveMessagePort|-設定**識別子**に*SaveMessagePort*<br /><br /> -設定**型**に*SaveMessagePortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*送信*<br /><br /> 操作を作成する*通知*です。 この操作は、通知メッセージに使用されます。<br /><br /> 操作を作成する*選択*です。 この操作は、応答メッセージを使用します。|  
|SQLOutboundPort|-設定**識別子**に*SQLOutboundPort*<br /><br /> -設定**型**に*SQLOutboundPortType*<br /><br /> -設定**通信パターン**に*要求-応答*<br /><br /> -設定**通信方向**に*送受信*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表は、プロパティとアクション図形のメッセージを指定して、メッセージ、ポートにリンクを設定する必要があります、値を指定します。 図形 列に表示名は、既に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveNotification|-設定**メッセージ**に*NotifyReceive*<br /><br /> -設定**操作**に*SQLNotifyPort.Notify.Request*|  
|SaveNotification|-設定**メッセージ**に*NotifyReceive*<br /><br /> -設定**操作**に*SaveMessagePort.Notify.Request*|  
|SendSelectMessage|-設定**メッセージ**に*選択*<br /><br /> -設定**操作**に*SQLOutboundPort.Select.Request*|  
|ReceiveSelectResponse|-設定**メッセージ**に*SelectResponse*<br /><br /> -設定**操作**に*SQLOutboundPort.Select.Response*|  
|SaveSelectResponse|-設定**メッセージ**に*SelectResponse*<br /><br /> -設定**操作**に*SaveMessagePort.Select.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   物理 Wcf-custom を定義するか、WCF SQL 一方向の受信ポートです。 このポートは、SQL Server データベースからの通知をリッスンします。 ポートを作成する方法については、次を参照してください。 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)です。 受信ポートのバインドのプロパティを指定することを確認してください。  
  
        > [!IMPORTANT]
        >  デザイン時のバインドのプロパティを指定した場合、この手順を実行する必要はありません。 このような場合は、WCF カスタムを作成または WCF SQL 受信ポート、必要なバインド プロパティを設定、によって作成されたバインド ファイルをインポートすることによって、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)です。  
  
        |プロパティのバインド|値|  
        |----------------------|-----------|  
        |**InboundOperationType**|これを設定して**通知**です。|  
        |**NotificationStatement**|これを設定します。<br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> **注:**する必要があります具体的には、列名を指定、ステートメントで次の SELECT ステートメントで示すようにします。 また、スキーマ名と共に、テーブル名を必ず指定する必要があります。 たとえば、 `dbo.Employee`のようにします。|  
        |**NotifyOnListenerStart**|これを設定して**True**です。|  
  
         異なるバインディングのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
        > [!NOTE]
        >  使用して受信操作の実行中に、トランザクション分離レベルとトランザクションのタイムアウトを構成することをお勧め、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 サービスを追加することで、Wcf-custom または WCF SQL の構成中に動作の受信ポートを行うことができます。 サービスの動作を追加する方法については、次を参照してください。[トランザクション分離レベルの構成と SQL を使用したトランザクションのタイムアウト](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)です。  
  
    -   SQL Server データベースにメッセージを送信する物理 Wcf-custom または WCF-SQL 送信ポートを定義します。 送信ポートでアクションを指定することもあります。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが、SQL Server データベースからメッセージをドロップ場所に場所を定義します。 これらは、SQL Server から受信した通知メッセージと、選択のメッセージと更新操作、Wcf-custom または WCF SQL を使用して実行する送信ポート。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 SQL Server データベースから通知メッセージを受信して、Select および Update の後続の操作を実行するために、BizTalk アプリケーションを開始する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。
  
 この段階で確認します。  
  
-   Wcf-custom または WCF SQL 一方向の受信ポートで、データベースが実行されている SQL Server から通知メッセージを受信します。  
  
-   実行する Wcf-custom または WCF-SQL 送信ポートを選択し、Employee テーブルでの Update 操作が実行されています。  
  
-   SQL Server からメッセージを受信する FILE 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 この操作を実行するには、Employee テーブルにレコードを挿入する必要があります。 次の内容でレコードを挿入すると仮定お知らせします。  
  
```  
Name = John Smith  
Designation = Manager  
Salary = 100000  
```  
  
 またを実行する、XML メッセージを選択し、更新操作は C:\TestLocation\MessageIn で利用できることを確認してください。 XML ファイルは、次のようになります。  
  
```  
<Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
  <Columns>Employee_ID,Name,Status</Columns>  
  <Query>where Status=0;UPDATE Employee SET Status=1 WHERE Status=0</Query>  
</Select>  
```  
  
 レコードが挿入されると、次の一連のアクションが実行、同じ順序で。  
  
-   アダプターは、次のような通知メッセージを受信します。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     このメッセージは、Employee テーブルのレコードが挿入されたことを通知します。 なおの値、`<Info>`要素は、"Insert"です。  
  
-   アダプターは、Select 操作を実行します。 XML の選択操作には、Update ステートメントも含まれているため、Update ステートメントも実行します。 SQL Server から次の応答では、Select ステートメントです。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <SelectResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <SelectResult>  
        <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
          <Employee_ID>10006</Employee_ID>   
          <Name>John</Name>   
          <Status>0</Status>  
        </Employee>  
      </SelectResult>  
    </SelectResponse>  
    ```  
  
     この応答は、Employee テーブルにレコードが挿入された、そのレコードの状態は 0 を示します。  
  
-   Select ステートメントの一部として、Update ステートメントの実行もと、新しいレコードの状態 列が 1 に変更されました。 SQL Server から別の通知をもう一度トリガーこれと、次のような対応する通知メッセージを受信します。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Update</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     このメッセージは、Employee テーブルのレコードが更新されたことを通知します。 なおの値、`<Info>`要素は、「更新」です。  
  
-   2 番目の通知後は、アダプターは、Select ステートメントを実行します。 ただし、0 と状態があるので、レコードがありません、ため、アダプターは、次のような空の応答を取得します。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <SelectResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <SelectResult />   
    </SelectResponse>  
    ```  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。[アダプターのバインドが SQL の再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)です。
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して SQL クエリ通知を受信します。](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)