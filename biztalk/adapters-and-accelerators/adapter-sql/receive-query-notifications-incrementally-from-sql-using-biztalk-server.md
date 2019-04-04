---
title: BizTalk Server を使用して SQL から段階的クエリ通知の受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a6972e01-80be-47be-986a-c2e4e0fb0cd1
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e278b4e25db6c62127d2aac4ee8d29c3c422e463
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007763"
---
# <a name="receive-query-notifications-incrementally-from-sql-using-biztalk-server"></a>BizTalk Server を使用して SQL から段階的クエリ通知を受け取る
> [!IMPORTANT]
>  説明を簡潔にするため、このトピックには、段階的に通知を受信する方法のみについて説明します。 ビジネスのシナリオで、オーケストレーションは理想的には受信した通知メッセージの種類を抽出し、後続の操作を実行するためのロジックを含める必要があります。 つまり、このトピックで説明されているオーケストレーションで説明されているオーケストレーションの上に構築する必要があります[BizTalk Server を使用して SQL の特定のタスクを実行する通知メッセージを処理](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)します。  
  
 このトピックでは、構成する方法を示します、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server データベースからの増分クエリ通知メッセージを受信します。 インクリメンタル通知を示すために、従業員、列を持つテーブルを"Status"を検討してください。 このテーブルに新しいレコードが挿入されると、[状態] 列の値は 0 に設定します。 次の手順に従ってインクリメンタル通知を受信するアダプターを構成できます。  
  
- 0 の状態 列であるすべてのレコードを取得する SQL ステートメントを使用して通知を登録します。 SQL ステートメントを指定することによって行うことができます、 **NotificationStatement**プロパティをバインドします。  
  
- 行の通知のメッセージが受信された場合に、1 に、状態列を更新します。  
  
  このトピックでは、BizTalk オーケストレーションを作成してこれを実現する BizTalk アプリケーションを構成する方法を示します。  
  
## <a name="configuring-notifications-with-the-sql-adapter-binding-properties"></a>SQL アダプター バインドのプロパティを使用した通知の構成  
 次の表にまとめたものです、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドのプロパティ構成の SQL Server から通知を受信するために使用します。 受信ポートを構成するときにこれらのバインドのプロパティを指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
> [!NOTE]
>  スキーマを生成するときに、これらのバインドのプロパティを指定することができます、**通知**は必須でない場合でも、操作します。 ポートのバインド ファイルをこのようにする場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部にもバインドのプロパティで指定する値が含まれているが生成されます。 後でこのバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロパティは既に設定されています。 バインドで wcf-custom または WCF SQL を作成する管理コンソールの受信ポート。 バインド ファイルを使用してポートを作成する方法の詳細については、[SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)を参照してください。  
  
|プロパティのバインド|説明|  
|----------------------|-----------------|  
|**InboundOperationType**|実行する受信操作を指定します。 通知メッセージを受信するこれを設定**通知**します。|  
|**NotificationStatement**|SQL ステートメントを指定します (SELECT または EXEC\<ストアド プロシージャ\>) のクエリ通知を登録するために使用します。 アダプターは、指定された SQL ステートメントの変更の結果セットの場合にのみ、SQL Server から通知メッセージを取得します。|  
|**NotifyOnListenerStart**|リスナーが開始されると、アダプターがアダプター クライアントに通知を送信するかどうかを指定します。|  
  
 これらのプロパティの詳細については、[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)を参照してください。 使用する方法の詳細については、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server からの通知を受信するさらに読み進める。  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a>このトピックで通知メッセージの受信について説明する方法  
 示すためにどのように[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]SQL Server からの通知メッセージの受信をサポートするには、このトピックでは、Employee テーブルへの変更の通知を受信するアダプターを構成する方法を示しますが。 Employee テーブルの列 Employee_ID、名、および状態であると仮定します。 新しい従業員が追加されたときに、[状態] 列の値が 0 に設定されます。  
  
 通知の受信を示すためには、次の操作を行います。  
  
-   スキーマを生成、**通知**(入力方向の操作)、および**選択**(送信操作) Employee テーブルにします。  
  
-   次を含むオーケストレーションを作成します。  
  
    -   通知メッセージを受信する受信場所。 として、SELECT ステートメントを指定することで、通知を構成できます。  
  
        ```  
        SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0  
        ```  
  
        > [!NOTE]
        >  具体的には、これで示すように、ステートメント内の列名の SELECT ステートメントを指定する必要があります。 また、スキーマ名とテーブル名を必ず指定する必要があります。 たとえば、 `dbo.Employee`のようにします。  
  
    -   通知が送信されて既に行を更新する送信ポートです。 これを 1 に、[状態] 列の値を設定して行います。 アダプターに次のメッセージを送信することによって、選択操作の一部として、これを行うことができます。  
  
        ```  
        <Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
          <Columns>Employee_ID,Name,Status</Columns>  
          <Query>where Status=0;UPDATE Employee SET Status=1 WHERE Status=0</Query>  
        </Select>  
        ```  
  
         一部としてこのメッセージで、`<Query>`要素では、[状態] 列を更新する UPDATE ステートメントを指定します。 この操作は、処理された行が更新されるようにメッセージ通知の受信後に実行する必要がありますに注意してください。 通知応答を待機していると、行を更新する要求メッセージを手動で削除のオーバーヘッドがすぐには、オーケストレーション自体内の行を更新するための要求メッセージが生成されます。 使用して行うことができます、**メッセージの構築**図形をオーケストレーション内。  
  
## <a name="how-to-receive-notification-messages-from-the-sql-server-database"></a>SQL Server データベースから通知メッセージを受信する方法  
 SQL Server データベースを使用して、操作を実行[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)します。 これらのタスクは通知メッセージを受信するアダプターを構成するには。  
  
1. BizTalk プロジェクトを作成しのスキーマを生成し、**通知**(入力方向の操作) と**選択**(送信操作) Employee テーブルにします。 値を指定する、必要に応じて、 **InboundOperationType**と**NotificationStatement**プロパティをバインドします。  
  
2. SQL Server データベースから通知を受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
3. SQL Server データベースの選択についてを実行して、応答メッセージの受信用の BizTalk プロジェクトでは、メッセージを作成します。  
  
4. 次のオーケストレーションを作成します。  
  
   -   SQL Server から通知メッセージを受信します。  
  
   -   選択し、通知を受信した行を更新するメッセージを作成します。  
  
   -   行を更新する SQL Server にこのメッセージを送信し、応答を受信します。  
  
5. ビルドし、BizTalk プロジェクトを配置します。  
  
6. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
   > [!NOTE]
   >  受信操作の場合、通知メッセージを受信するように Wcf-custom の一方向のみを構成する必要があります。 または WCF SQL 受信ポート。 Wcf-custom または WCF-SQL の双方向受信ポートの受信操作はサポートされていません。  
  
7. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックに基づくサンプル  
 サンプル IncrementalNotification、このトピックの「に基づいてが付属、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、[SQL アダプタのサンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)を参照してください。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 スキーマを生成する必要があります、**通知**操作と**選択**従業員テーブルに対する操作。 参照してください[SQL アダプタを使用して Visual Studio で SQL Server 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)スキーマを生成する方法の詳細について。 スキーマを生成するときに、次のタスクを実行します。 デザイン時のバインドのプロパティを指定しない場合は、最初の手順をスキップします。  
  
1.  値を指定**InboundOperationType**と**NotificationStatement**スキーマの生成中にプロパティをバインドします。 このバインドのプロパティの詳細については、[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)を参照してください。 バインドのプロパティを指定する方法については、[SQL アダプタのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)を参照してください。  
  
2.  コントラクトの種類を選択します。**サービス (受信操作)** します。  
  
3.  スキーマの生成、**通知**操作。  
  
4.  コントラクトの種類を選択します。**クライアント (送信操作)** します。  
  
5.  スキーマの生成、**選択**操作**従業員**テーブル。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 スキーマが生成されるは、BizTalk プロジェクトのオーケストレーションからメッセージをリンクする必要があります。  
  
 このトピックでは、3 つのメッセージを作成する必要があります: SQL Server データベースや選択の操作を実行する 1 つの Select 操作の応答を受信する 1 つから通知を受信する 1 つ。  
  
 メッセージを作成し、スキーマにリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。  
  
2.  開いていない場合は、BizTalk プロジェクトのオーケストレーション ビュー ウィンドウを開きます。 をクリックして**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
3.  **オーケストレーション**、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。  
  
4.  新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  
  
5.  **プロパティ**ウィンドウ **[message_1]** 次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`NotifyReceive`.|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選択と*SQLNotify.Notification*ここで、 *SQLNotify* BizTalk プロジェクトの名前を指定します。 *通知*に対して生成されたスキーマには、**通知**操作。|  
  
6.  手順 3 を 2 つの新しいメッセージを作成する. **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  
  
    |識別子を設定するには|メッセージの種類を設定|  
    |-----------------------|-------------------------|  
    |Select|*SQLNotify.TableOperation_dbo_Employee.Select*ここで、 *TableOperation_dbo_Employee*に対して生成されたスキーマには、**選択**操作|  
    |SelectResponse|*SQLNotify.TableOperation_dbo_Employee.SelectResponse*|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の SQL Server データベースから通知メッセージを受信し、通知を受信した行を更新します。 このオーケストレーションでの指定した SELECT ステートメントに基づいて、通知メッセージを受信、 **NotificationStatement**プロパティをバインドします。 通知メッセージは、ファイルの場所で受信されます。 応答が受信されると、オーケストレーションは、通知を受信した行を更新するために使用するメッセージを構築します。 このメッセージの応答を同じファイルの場所で受信もします。  
  
 そのため、オーケストレーションは、次に含める必要があります。  
  
- 一方向の受信の通知メッセージを受信するポート。  
  
- 双方向の送信ポートの行を更新し、同じ応答を受信するメッセージを送信します。  
  
- A**メッセージの構築**図形をオーケストレーション内で、更新操作を実行する、メッセージを構築します。  
  
- ファイルは、更新操作の応答を保存するポートを送信します。  
  
- 受信図形と送信図形。  
  
  サンプル オーケストレーションでは、次の項目に似ています。  
  
  ![SQL Server 通知を受信するオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/f13ad3b8-8161-42e5-a521-424bbf549ad5.gif "f13ad3b8-8161-42e5-a521-424bbf549ad5")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 図形の列に示した名前は、単に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveNotification|Receive|-設定**名前**に*ReceiveNotification*<br /><br /> -設定**アクティブ**に*は True。*|  
|SaveNotification|Send|-設定**名前**に*SaveNotification*|  
|SendSelectMessage|Send|-設定**名前**に*SendSelectMessage*|  
|ReceiveSelectResponse|Receive|-設定**名前**に*ReceiveSelectResponse*|  
|SaveSelectResponse|Send|-設定**名前**に*SaveSelectResponse*|  
  
### <a name="adding-construct-message-shape"></a>メッセージの構築図形を追加します。  
 使用することができます、**メッセージの構築**図形を選択操作を実行する操作に含まれる要求メッセージを生成します。 これを行うには、追加する必要があります、**メッセージの構築**図形し、その中を**メッセージの割り当て**図形をオーケストレーションにします。 この例で、**メッセージの割り当て**図形が選択操作を実行する SQL Server に送信されるメッセージを生成するコードを呼び出します。 **メッセージの割り当て**図形も、SQL Server に送信するメッセージに対するアクションを設定します。  
  
 メッセージの構築図形で、設定、**メッセージ構築**プロパティを**選択**します。  
  
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
  
 要求メッセージを生成できるように上記のコードの抜粋、する必要があります (Employee テーブルの選択の操作) の XML 要求メッセージに指定された場所で、`XmlFileLocation`変数。  
  
> [!NOTE]
>  プロジェクトをビルドした後に SampleMessageCreator.dll がプロジェクト ディレクトリに作成されます。 この DLL は、グローバル アセンブリ キャッシュ (GAC) に追加する必要があります。 また、BizTalk プロジェクトに参照として、SampleMessageCreator.dll を追加する必要があります。  
  
 次のコードを呼び出すには、次の式を追加、**メッセージの割り当て**図形とメッセージのアクションを設定します。 式を追加するには、ダブルクリック、**メッセージの割り当て**図形式エディターを開きます。  
  
```  
Select = SampleMessageCreator.SampleMessageCreator.XMLMessageCreator();  
Select(WCF.Action) = "TableOp/Select/dbo/Employee";  
```  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認します。 ポート列に示した名前は、オーケストレーションで表示されているポートの名前です。  
  
|Port|[プロパティ]|  
|----------|----------------|  
|SQLNotifyPort|-設定**識別子**に*SQLNotifyPort*<br /><br /> -設定**型**に*SQLNotifyPortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*受信*|  
|SaveMessagePort|-設定**識別子**に*SaveMessagePort*<br /><br /> -設定**型**に*SaveMessagePortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*送信*<br /><br /> -作成操作*通知*します。 この操作は、通知メッセージに使用されます。<br /><br /> -作成操作*選択*します。 この操作は、応答メッセージに使用されます。|  
|SQLOutboundPort|-設定**識別子**に*SQLOutboundPort*<br /><br /> -設定**型**に*SQLOutboundPortType*<br /><br /> -設定**通信パターン**に*要求-応答*<br /><br /> -設定**通信方向**に*送受信*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表では、プロパティとアクション図形のメッセージを指定して、メッセージ ポートにリンクを設定する必要があります、値を指定します。 図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveNotification|-設定**メッセージ**に*NotifyReceive*<br /><br /> -設定**操作**に*SQLNotifyPort.Notify.Request*|  
|SaveNotification|-設定**メッセージ**に*NotifyReceive*<br /><br /> -設定**操作**に*SaveMessagePort.Notify.Request*|  
|SendSelectMessage|-設定**メッセージ**に*を選択します*<br /><br /> -設定**操作**に*SQLOutboundPort.Select.Request*|  
|ReceiveSelectResponse|-設定**メッセージ**に*SelectResponse*<br /><br /> -設定**操作**に*SQLOutboundPort.Select.Response*|  
|SaveSelectResponse|-設定**メッセージ**に*SelectResponse*<br /><br /> -設定**操作**に*SaveMessagePort.Select.Request*|  
  
 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)を参照してください。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 チュートリアルについては、[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)を参照してください。
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
  - WCF-SQL の一方向受信ポートまたは物理 Wcf-custom を定義します。 このポートは、SQL Server データベースから通知をリッスンします。 ポートを作成する方法については、[SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)を参照してください。 受信ポートのバインドのプロパティを指定することを確認します。  
  
    > [!IMPORTANT]
    >  デザイン時のバインドのプロパティを指定した場合、この手順を実行する必要はありません。 このような場合は、WCF カスタムを作成または WCF-SQL によって作成されたバインド ファイルをインポートすることによって、必要なバインドのプロパティを設定すると、ポートを受信する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 詳細については、[SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)を参照してください。  
  
    |プロパティのバインド|値|  
    |----------------------|-----------|  
    |**InboundOperationType**|これを設定**通知**します。|  
    |**NotificationStatement**|これを設定します。<br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> **注:** この SELECT ステートメントで示すように、ステートメントで列名に指定すること具体的にする必要があります。 また、スキーマ名とテーブル名を必ず指定する必要があります。 たとえば、 `dbo.Employee`のようにします。|  
    |**NotifyOnListenerStart**|これを設定**True**します。|  
  
     異なるバインディング プロパティの詳細については、[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)を参照してください。  
  
    > [!NOTE]
    >  使用して受信操作の実行中に、トランザクション分離レベルとトランザクションのタイムアウトを構成することをお勧めします。、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 ように、サービスを追加することで、Wcf-custom または WCF SQL を構成するときに動作の受信ポートを行うことができます。 サービスの動作を追加する方法については、[トランザクション分離レベルの構成と SQL を使用したトランザクション タイムアウト](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)を参照してください。  
  
  - SQL Server データベースにメッセージを送信する物理 Wcf-custom または WCF-SQL 送信ポートを定義します。 送信ポートでアクションを指定することも必要があります。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーション、SQL Server データベースからメッセージをドロップできる場所での場所を定義します。 これらは、SQL Server から受信した通知メッセージとメッセージを選択し、Wcf-custom または WCF SQL を使用して実行する更新操作がポートを送信します。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 SQL Server データベースから通知メッセージを受信するため、後続の Select および Update 操作を実行するために、BizTalk アプリケーションを開始する必要があります。 BizTalk アプリケーションを開始する手順については、[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)を参照してください。
  
 この段階で、ことを確認します。  
  
-   Wcf-custom または WCF SQL 一方向の受信ポートで、データベースが実行されている SQL Server から通知メッセージを受信します。  
  
-   実行する Wcf-custom または WCF-SQL 送信ポートを選択し、Employee テーブルの更新操作が実行されています。  
  
-   SQL Server からメッセージを受信する、ファイル送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 この操作を実行するには、Employee テーブルにレコードを挿入する必要があります。 お知らせ、次の詳細情報を持つレコードを挿入するとします。  
  
```  
Name = John Smith  
Designation = Manager  
Salary = 100000  
```  
  
 また、実行する XML メッセージを選択し、更新操作は C:\TestLocation\MessageIn を確認します。 XML ファイルは、次のようになります。  
  
```  
<Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
  <Columns>Employee_ID,Name,Status</Columns>  
  <Query>where Status=0;UPDATE Employee SET Status=1 WHERE Status=0</Query>  
</Select>  
```  
  
 レコードが挿入されると、次の一連のアクションが、同じシーケンス内の場所。  
  
-   アダプターは、次のような通知メッセージを受け取ります。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     このメッセージは、Employee テーブルにレコードが挿入されたことを通知します。 注意の値、`<Info>`要素は、"Insert"。  
  
-   アダプターは、選択操作を実行します。 選択操作で XML には、Update ステートメントも含まれているため、Update ステートメントも実行されます。 SQL Server から次の応答は、Select ステートメントです。  
  
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
  
-   Select ステートメントの一部として、Update ステートメントが実行されることも、新しいレコードの状態 列が 1 に変更されました。 SQL Server から別の通知をもう一度トリガーこれと対応する、次のような通知メッセージを受信します。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Update</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     このメッセージは、Employee テーブルにレコードが更新されたことを通知します。 注意の値、`<Info>`要素は、「更新」します。  
  
-   2 番目の通知後は、アダプターは、Select ステートメントを実行します。 ただし、0 としてステータスがあるので、レコードがありません、ため、アダプターは、次のような空の応答を取得します。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <SelectResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <SelectResult />   
    </SelectResponse>  
    ```  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定、ファイルからインポートできます。 バインド ファイルの詳細については、[再利用の SQL アダプター バインド](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)を参照してください。
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して SQL クエリ通知を受け取る](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)