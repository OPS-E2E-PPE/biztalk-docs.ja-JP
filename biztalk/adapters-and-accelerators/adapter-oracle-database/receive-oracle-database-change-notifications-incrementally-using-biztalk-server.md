---
title: "BizTalk Server を使用して増分値 Oracle データベースの変更通知を受け取る |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 17cef39f-a1aa-4f46-993f-620008f3890d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b700382d96b24b24470617749e810c7cce2d2f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="receive-oracle-database-change-notifications-incrementally-using-biztalk-server"></a>BizTalk Server を使用して増分値 Oracle データベースの変更通知を受信します。
> [!IMPORTANT]
>  ここでは簡略化のため、このトピックには、通知を受信する差分方法のみについて説明します。 ビジネス シナリオで、オーケストレーションは理想的には受信した通知メッセージの種類を抽出し、後続の操作を実行するためのロジックを含める必要があります。 つまり、上で説明されているオーケストレーションにこのトピックで説明されているオーケストレーションを構築する必要が[BizTalk Sever を使用して Oracle データベースで特定のタスクを完了する通知メッセージを処理](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md)です。  
  
 このトピックの内容を構成する方法を示しています、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle から増分クエリ通知メッセージを受信します。 インクリメンタル通知を示すためには、ACCOUNTACTIVITY、列を持つテーブルを「処理」を検討します。 このテーブルに新しいレコードが挿入されると、「処理」列の値 éý 'è' n ' です。 通知を受信する差分、次の手順を実行して、アダプターを構成することができます。  
  
-   として「処理済み」の列が含まれるすべてのレコードを取得する SELECT ステートメントを使用して通知の登録 'n' です。 これを行うの SELECT ステートメントを指定することによって、 **NotificationStatement**プロパティをバインドします。  
  
-   通知されている行のためには、'y'「処理」列を更新します。  
  
 このトピックでは、BizTalk オーケストレーションを作成してこれを実現する BizTalk アプリケーションを構成する方法を示します。  
  
## <a name="configuring-notifications-with-the-oracle-database-adapter-binding-properties"></a>Oracle データベース アダプターのプロパティをバインドに通知を構成します。  
 次の表、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドのプロパティ、Oracle データベースから通知の受信を構成するために使用します。 受信ポートを構成するときにこれらのバインディング プロパティを指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
> [!NOTE]
>  スキーマを生成するときに、これらのバインディング プロパティを指定することもできます、**通知**操作、必須ではない場合でもです。 これを行うと、ポートのバインド ファイル、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成され、メタデータの生成の一部では、バインドのプロパティを指定する値も含まれます。 このバインド ファイルを後でインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロパティは既に設定されています。 バインドで wcf-custom または Wcf-oracledb を作成する管理コンソールの受信ポート。 バインド ファイルを使用して受信ポートの作成の詳細については、次を参照してください。 [Oracle データベースへのポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)です。  
  
|プロパティのバインド|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|受信操作を実行することを指定します。 通知メッセージを受信するには、これを設定**通知**です。|  
|**NotificationPort**|ODP.NET が Oracle データベースからデータベースの変更通知をリッスンするように開く必要があるポート番号を指定します。|  
|**NotificationStatement**|クエリ通知の登録に使用する SELECT ステートメントを指定します。 アダプターは、指定した SELECT ステートメントの変更の結果セットの場合にのみ、通知メッセージを取得します。|  
|**NotifyOnListenerStart**|リスナーが開始されたときに、アダプターがアダプターのクライアントに通知を送信するかどうかを指定します。|  
  
 これらのプロパティの詳細については、次を参照してください。 [BizTalk Adapter 用 Oracle Database バインド プロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)です。 使用する方法の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]さらに通知を受信する Oracle データベースから、読み取る。  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a>どのように、このトピックでは通知メッセージの受信を示しています  
 このトピックの内容を示すためにどのように[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ACCOUNTACTIVTY テーブルへの変更の通知を受信するアダプターを構成して、Oracle データベースからのデータベースの増分変更の通知メッセージの受信をサポートするには、おです。 お知らせ ACCOUNTACTIVITY テーブルの列"TID"、「アカウント」および「処理」であると仮定します。 新しいレコードを追加するたびに、「処理済み」の列の設定は 'n' です。 そのため、インクリメンタル通知を取得する必要を BizTalk オーケストレーションの一部として、次のタスクを行うには。  
  
-   ここで、「処理」はすべてのレコードの通知を受け取る 'n' です。 通知のステートメントと SELECT ステートメントを指定することによって、これを行うことができます。  
  
-   特定のレコードに対して、通知を受け取った後に、'y'「処理」を設定します。 PROCESS_RECORDS で、「処理」列を更新し、ストアド プロシージャを実行することによって、これを行うことができます。  
  
 インクリメンタル通知の受信を示すためは、次を操作します。  
  
-   スキーマを生成、**通知**(受信操作)、および**PROCESS_RECORDS** (送信操作) ACCOUNTACTIVITY テーブルにします。  
  
-   次のあるオーケストレーションを作成します。  
  
    -   通知メッセージを受信する受信場所。 通知として SELECT ステートメントを指定することによって構成できます。  
  
        ```  
        SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’  
        ```  
  
        > [!NOTE]
        >  スキーマ名と共に、テーブル名を指定する必要があります。 たとえば、 `SCOTT.ACCOUNTACTIVITY`のようにします。  
  
    -   通知が既に送信されている行を更新する送信ポートです。 PROCESS_RECORDS ストアド プロシージャは、通知を受信したレコードの 'y'「処理」列の値を設定するには、このポートで実行されます。  
  
         この操作は、処理された行が更新されるようにメッセージ通知の受信後に実行する必要がありますに注意してください。 通知応答を取得するまで待機し、PROCESS_RECORDS プロシージャを実行する要求メッセージを手動で削除のオーバーヘッドが除去には、オーケストレーション自体内 PROCESS_RECORDS プロシージャの要求メッセージを生成するされます。 これを行うを使用して、**メッセージの構築**図形をオーケストレーション内です。  
  
## <a name="how-to-receive-notification-messages-from-the-oracle-database"></a>Oracle データベースから通知メッセージを受信する方法  
 Oracle データベースを使用して、操作を実行[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明する手順のタスクでは、[の Oracle データベースと BizTalk アプリケーションを開発する基盤](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)です。 これらのタスクは通知メッセージを受信アダプターを構成するのには。  
  
1.  BizTalk プロジェクトを作成しのスキーマを生成、**通知**(受信操作) と**PROCESS_RECORDS** ACCOUNTACTIVITY テーブルで、手順 (送信操作)。 必要に応じての値を指定することができます、 **InboundOperationType**、 **NotificationPort**、および**NotificationStatement**プロパティをバインドします。  
  
2.  Oracle データベースから通知を受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  PROCESS_RECORDS ストアド プロシージャを実行して、応答メッセージの送受信用の BizTalk プロジェクトでメッセージを作成します。  
  
4.  次のオーケストレーションを作成します。  
  
    -   Oracle データベースから通知メッセージを受信します。  
  
    -   PROCESS_RECORDS プロシージャを実行するメッセージを作成します。  
  
    -   Oracle データベースを選択して、レコードを更新し、応答を受信するには、このメッセージを送信します。  
  
5.  構築し、BizTalk プロジェクトを展開します。  
  
6.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
    > [!NOTE]
    >  通知メッセージを受信するように、受信操作の一方向の WCF カスタムのみを構成する必要があります。 または Wcf-oracledb 受信ポート。 双方向受信ポートが受信操作のサポートされていません。  
  
7.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 スキーマを生成する必要があります、**通知**操作と**PROCESS_RECORDS**プロシージャです。 参照してください[Visual Studio での Oracle 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)スキーマを生成する方法についての詳細。 スキーマを生成するときに、次のタスクを実行します。 デザイン時のバインドのプロパティを指定しない場合は、最初の手順をスキップします。  
  
1.  値を指定**InboundOperationType**、 **NotificationPort**、および**NotificationStatement**スキーマの生成中にプロパティをバインドします。 このバインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter 用 Oracle Database バインド プロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)です。 バインドのプロパティを指定する方法については、次を参照してください。[バインドのプロパティを指定する](https://msdn.microsoft.com/library/dd788420.aspx)です。  
  
2.  コントラクトの種類を選択して**サービス (入力方向の操作)**です。  
  
3.  スキーマを生成、**通知**操作します。  
  
4.  コントラクトの種類を選択して**クライアント (送信操作)**です。  
  
5.  スキーマを生成、 **PROCESS_RECORDS**プロシージャです。 この手順で使用可能な**ACCOUNT_PKG**パッケージです。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 スキーマが生成されるは、BizTalk プロジェクトのオーケストレーションの種類からのメッセージをリンクする必要があります。  
  
 このトピックでは、3 つのメッセージを作成する必要があります: PROCESS_RECORDS プロシージャを実行して、プロシージャの応答を受信する Oracle データベースから通知を受け取るいずれか。  
  
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
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択し、 *OracleNotifyIncremental.OracleDBBinding.Notification*ここで、 *OracleNotifyIncremental*の名前を指定します。BizTalk プロジェクトです。 *OracleDBBinding*に対して生成されたスキーマは、**通知**操作します。|  
  
6.  手順 3 を繰り返して 2 つの新しいメッセージを作成します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |識別子に設定します。|メッセージの種類を設定|  
    |-----------------------|-------------------------|  
    |手順|*OracleNotifyIncremental.OracleDBBinding1.PROCESS_RECORDS*ここで、 *OracleDBBinding1*に対して生成されたスキーマは、 **PROCESS_RECORDS**プロシージャです。|  
    |ProcedureResponse|*OracleNotifyIncremental.OracleDBBinding1.PROCESS_RECORDSResponse*|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の Oracle データベースから通知メッセージを受信し、通知を受信した行を更新します。 このオーケストレーションでの指定した SELECT ステートメントに基づく通知メッセージを受信、 **NotificationStatement**プロパティをバインドします。 通知メッセージは、ファイルの場所で受信されます。 応答が受信されると、オーケストレーションは、通知を受信した行を更新する、PROCESS_RECORDS プロシージャを呼び出すためのメッセージを構築します。 このメッセージの応答を同じファイルの場所にも受信します。  
  
 そのため、オーケストレーションは、次が必要があります。  
  
-   一方向の WCF カスタムまたは Wcf-oracledb 通知メッセージを受信するポートを受信します。  
  
-   双方向の WCF カスタムまたは Wcf-oracledb PROCESS_RECORDS プロシージャを実行するメッセージを送信するポートを送信します。  
  
-   A**メッセージの構築**図形をオーケストレーション内での PROCESS_RECORDS プロシージャを実行する、メッセージを構築します。  
  
-   ファイルは、通知メッセージと PROCESS_RECORDS プロシージャへの応答を保存するポートを送信します。  
  
-   受信図形と送信図形。  
  
 サンプル オーケストレーションには、次のようになります。  
  
 ![Oracle から通知を受信するオーケストレーション](../../adapters-and-accelerators/adapter-oracle-database/media/cef49414-490a-4bd5-a32d-b3f4cde5950a.gif "cef49414-490a-4bd5-a32d-b3f4cde5950a")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。 図形 列に表示名は、単に記載されているオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveNotification|Receive|-設定**名前**に*ReceiveNotification*<br /><br /> -設定**アクティブ**に*は True。*|  
|SaveNotification|Send|-設定**名前**に*SaveNotification*|  
|SendProcMessage|Send|-設定**名前**に*SendProcMessage*|  
|ReceiveProcResponse|Receive|-設定**名前**に*ReceiveProcResponse*|  
|SaveProcResponse|Send|-設定**名前**に*SaveProcResponse*|  
  
### <a name="adding-construct-message-shape"></a>メッセージの構築図形を追加します。  
 使用することができます、**メッセージの構築**図形 PROCESS_RECORDS プロシージャを実行するオーケストレーション内で要求メッセージを生成します。 これを行うには、追加する必要があります、**メッセージの構築**図形という、**メッセージの割り当て**図形をオーケストレーションにします。 この例で、**メッセージの割り当て**図形は、プロシージャを実行する Oracle データベースに送信されるメッセージを生成するコードを呼び出します。 **メッセージの割り当て**図形も、Oracle データベースに送信されるメッセージのアクションを設定します。  
  
 メッセージの構築図形、設定、**メッセージ構築**プロパティを**プロシージャ**です。  
  
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
            XmlFileLocation = "C:\\TestLocation\\MessageIn";  
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
  
 要求メッセージを生成できるように上記のコード例でする必要があります (PROCESS_RECORDS プロシージャ) の場合、XML 要求メッセージの指定した場所に、`XmlFileLocation`変数。  
  
> [!NOTE]
>  プロジェクトをビルドした後、MessageCreator.dll はプロジェクト ディレクトリに作成されます。 グローバル アセンブリ キャッシュ (GAC) には、この DLL を追加する必要があります。 また、BizTalk プロジェクトに参照として、MessageCreator.dll を追加する必要があります。  
  
 次のコードを呼び出すには、次の式を追加、**メッセージの割り当て**図形とメッセージのアクションを設定します。 式を追加するにはダブルクリック、**メッセージの割り当て**図形式エディターを開きます。  
  
```  
Procedure = SampleMessageCreator.SampleMessageCreator.XMLMessageCreator();  
Procedure(WCF.Action) = "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/PROCESS_RECORDS";  
```  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認してください。 ポート列に表示される名前は、オーケストレーションで表示されているポートの名前です。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|OracleNotifyPort|-設定**識別子**に*OracleNotifyPort*<br /><br /> -設定**型**に*OracleNotifyPortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*受信*|  
|SaveMessagePort|-設定**識別子**に*SaveMessagePort*<br /><br /> -設定**型**に*SaveMessagePortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*送信*<br /><br /> 操作を作成する*通知*です。 この操作は、通知メッセージに使用されます。<br /><br /> 操作を作成する*プロシージャ*です。 この操作は、応答メッセージを使用します。|  
|OracleOutboundPort|-設定**識別子**に*OracleOutboundPort*<br /><br /> -設定**型**に*OracleOutboundPortType*<br /><br /> -設定**通信パターン**に*要求-応答*<br /><br /> -設定**通信方向**に*送受信*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表は、プロパティとアクション図形のメッセージを指定して、メッセージ、ポートにリンクを設定する必要があります、値を指定します。 図形 列に表示名は、既に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveNotification|-設定**メッセージ**に*NotifyReceive*<br /><br /> -設定**操作**に*OracleNotifyPort.Notify.Request*|  
|SaveNotification|-設定**メッセージ**に*NotifyReceive*<br /><br /> -設定**操作**に*SaveMessagePort.Notify.Request*|  
|SendProcMessage|-設定**メッセージ**に*プロシージャ*<br /><br /> -設定**操作**に*OracleOutboundPort.Procedure.Request*|  
|ReceiveProcResponse|-設定**メッセージ**に*ProcedureResponse*<br /><br /> -設定**操作**に*OracleOutboundPort.Procedure.Response*|  
|SaveProcResponse|-設定**メッセージ**に*ProedureResponse*<br /><br /> -設定**操作**に*SaveMessagePort.Procedure.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**ペインで、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール アプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   物理 Wcf-custom を定義するか、Wcf-oracledb 一方向の受信ポートです。 このポートは、Oracle データベースからの通知をリッスンします。 受信ポートを作成する方法についてを参照してください[Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)です。 受信ポートのバインドのプロパティを指定することを確認してください。  
  
        > [!IMPORTANT]
        >  デザイン時のバインドのプロパティを指定した場合、この手順を実行する必要はありません。 このような場合は、することができます、受信ポートを作成、必要なバインド プロパティを設定、によって作成されたバインド ファイルをインポートすることによって、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 詳細については、次を参照してください。 [Oracle データベースへのポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)です。  
  
        |プロパティのバインド|値|  
        |----------------------|-----------|  
        |**InboundOperationType**|これを設定して**通知**です。|  
        |**NotificationPort**|ODP.NET が Oracle データベースからデータベースの変更通知をリッスンするように開く必要があるポート番号を指定します。 これは、Windows ファイアウォールの例外一覧に追加する必要があります同じポート番号を設定します。 Windows ファイアウォールの例外リストにポートを追加する方法については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)です。<br /><br /> **重要:**これを既定値は-1 を設定する場合は、通知メッセージを受け取るための Windows ファイアウォールを完全に無効にする必要があります。|  
        |**NotificationStatement**|これを設定します。<br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’`<br /><br /> **注:**スキーマ名とテーブル名を指定する必要があります。 たとえば、 `SCOTT.ACCOUNTACTIVITY`のようにします。|  
        |**NotifyOnListenerStart**|これを設定して**True**です。|  
  
         異なるバインディングのプロパティの詳細については、次を参照してください。 [BizTalk Adapter 用 Oracle Database バインド プロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)です。  
  
        > [!NOTE]
        >  使用して受信操作の実行中に、トランザクション分離レベルとトランザクションのタイムアウトを構成することをお勧め、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 サービスを追加することで、Wcf-custom または Wcf-oracledb を構成するときに動作の受信ポートを行うことができます。 サービスの動作を追加する方法については、次を参照してください。[トランザクション分離レベルの構成とトランザクションのタイムアウト](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)です。  
  
    -   PROCESS_REOCRDS プロシージャを実行する Oracle データベースにメッセージを送信する物理 Wcf-custom または Wcf-oracledb 送信ポートを定義します。 送信ポートでアクションを指定することもあります。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが Oracle データベースからメッセージをドロップ場所に場所を定義します。 これらは、Oracle データベースから受信した通知メッセージと WCF カスタムを通じて実行 PROCESS_RECORDS プロシージャのメッセージか Wcf-oracledb 送信ポート。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 Oracle データベースから通知メッセージを受信して、PROCESS_RECORDS 手順を実行するために、BizTalk アプリケーションを開始する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。  
  
 この段階で確認します。  
  
-   Wcf-custom または Wcf-oracledb 一方向の受信ポートで、データベースが実行されている Oracle から通知メッセージを受信します。  
  
-   PROCESS_RECORDS プロシージャを実行する Wcf-custom または Wcf-oracledb 送信ポートが実行されています。  
  
-   Oracle データベースからメッセージを受信する FILE 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 ACCOUNTACTIVITY テーブルが既にレコードの一部であると仮定します。 また、C:\TestLocation\MessageIn で使用される PROCESS_RECORDS プロシージャを実行する XML メッセージを確認します。 XML ファイルは、次のようになります。  
  
```  
<PROCESS_RECORDS xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG"/>  
```  
  
 BizTalk オーケストレーションが開始されると、次の一連のアクションが実行、同じ順序で。  
  
-   アダプターは、次のような通知メッセージを受信します。  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Info>ListenerStarted</Info>   
      <Source>OracleDBBinding</Source>   
      <Type>Startup</Type>   
    </Notification>  
    ```  
  
     このメッセージは、通知メッセージを受信する受信ポートが開始されたことを通知します。 なおの値、`<Info>`要素は、"ListnerStarted"です。  
  
-   アダプターでは、PROCESS_RECORDS プロシージャを実行します。 Oracle データベースから次の応答では、プロシージャのです。  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <PROCESS_RECORDSResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
      <TABLE_DATA>  
        \<xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          \<xs:element msdata:IsDataSet="true" name="NewDataSet">  
            \<xs:complexType>  
              \<xs:sequence>  
                \<xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  \<xs:complexType>  
                    \<xs:sequence>  
                      \<xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                      \<xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                      \<xs:element minOccurs="0" name="PROCESSED" type="xs:string" />   
                    \</xs:sequence>  
                  \</xs:complexType>  
                \</xs:element>  
              \</xs:sequence>  
            \</xs:complexType>  
          \</xs:element>  
        \</xs:schema>  
        \<diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
        <NewDataSet xmlns="">  
          <NewTable>  
            <TID>1</TID>   
            <ACCOUNT>100001</ACCOUNT>   
            <PROCESSED>n</PROCESSED>   
          </NewTable>  
          <NewTable>  
            ......  
            ......  
          </NewTable>  
          ......  
          ......  
        </NewDataSet>  
        \</diffgr:diffgram>  
      </TABLE_DATA>  
    </PROCESS_RECORDSResponse>  
    ```  
  
     これは、PROCESS_RECORDS 手順の一部として、SELECT ステートメントの実行の応答です。  
  
-   PROCESS_RECORDS プロシージャでは、'y' に処理を設定する行も更新します。 そのため、アダプターは、更新操作に別の通知を受け取ります。  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>  
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Details>  
        <NotificationDetails>  
          <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
          <Info>32</Info>   
          <QueryId>0</QueryId>   
        </NotificationDetails>  
      </Details>  
      <Info>Update</Info>   
      <ResourceNames>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
      </ResourceNames>  
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     なお、`Info`要素には、「Update」が含まれています。  
  
-   2 番目の通知後、アダプターは再度 PROCESS_RECORDS プロシージャを実行します。 ただし、今すぐに処理された列が設定されているレコードがないため ' n '、プロシージャは、次のような空の応答を返します。  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <PROCESS_RECORDSResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
      <TABLE_DATA>  
        \<xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          \<xs:element msdata:IsDataSet="true" name="NewDataSet">  
            \<xs:complexType>  
              \<xs:sequence>  
                \<xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  \<xs:complexType>  
                    \<xs:sequence>  
                      \<xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                      \<xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                      \<xs:element minOccurs="0" name="PROCESSED" type="xs:string" />   
                    \</xs:sequence>  
                  \</xs:complexType>  
                \</xs:element>  
              \</xs:sequence>  
            \</xs:complexType>  
          \</xs:element>  
        \</xs:schema>  
        \<diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
          <NewDataSet xmlns="" />   
        \</diffgr:diffgram>  
      </TABLE_DATA>  
    </PROCESS_RECORDSResponse>  
    ```  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。 [Oracle データベース アダプターの再利用バインド](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して Oracle データベースの変更通知を受け取る](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)