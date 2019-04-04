---
title: 段階的に BizTalk Server を使用して Oracle E-business Suite の変更通知の受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63dbeacc-ecde-497d-b12d-d5f9944a33f0
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37c596a5a383f55f38f90a367caae45a4ce3ec0e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004852"
---
# <a name="receive-oracle-e-business-suite-change-notifications-incrementally-using-biztalk-server"></a>段階的に BizTalk Server を使用して Oracle E-business Suite の変更通知を受け取る
> [!IMPORTANT]
>  説明を簡潔にするため、このトピックには、段階的に通知を受信する方法のみについて説明します。 ビジネスのシナリオで、オーケストレーションは理想的には受信した通知メッセージの種類を抽出し、後続の操作を実行するためのロジックを含める必要があります。 つまり、このトピックで説明されているオーケストレーションで説明されているオーケストレーションの上に構築する必要があります[Oracle E-business Suite で特定のタスクを実行するプロセスの通知メッセージ](../../adapters-and-accelerators/adapter-oracle-ebs/process-notification-messages-to-complete-specific-tasks-in-oracle-ebs.md)します。  
  
 このトピックでは、構成する方法を示します、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle から差分クエリ通知メッセージを受信します。 インクリメンタル通知を示すには、テーブル、ACCOUNTACTIVITY、「処理済み」列を含むについて考えます。 「処理済み」列の値設定してこのテーブルに新しいレコードが挿入されると、' n ' です。 次の手順に従ってインクリメンタル通知を受信するアダプターを構成できます。  
  
- として「処理済み」列が含まれるすべてのレコードを取得する SELECT ステートメントを使用して通知を登録 'n' です。 SELECT ステートメントを指定することによって行うことができます、 **NotificationStatement**プロパティをバインドします。  
  
- 行のために通知して、"y"を「処理済み」列を更新します。  
  
  このトピックでは、BizTalk オーケストレーションを作成してこれを実現する BizTalk アプリケーションを構成する方法を示します。  
  
## <a name="configuring-notifications-with-the-oracle-e-business-adapter-binding-properties"></a>Oracle E-business アダプターのバインドのプロパティと通知の構成  
 次の表にまとめたものです、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite から通知を受け取る構成に使用するプロパティをバインドします。 受信ポートを構成するときにこれらのバインドのプロパティを指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
> [!NOTE]
>  スキーマを生成するときに、これらのバインドのプロパティを指定することができます、**通知**は必須でない場合でも、操作します。 ポートのバインド ファイルをこのようにする場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部にもバインドのプロパティで指定する値が含まれているが生成されます。 後でこのバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロパティは既に設定されています。 バインドで wcf-custom または Wcf-oracleebs を作成する管理コンソールの受信ポート。 バインド ファイルを使用して受信ポートを作成する方法の詳細については、[Oracle E-business Suite へのポート バインド ファイルを、物理ポートを使用してバインディングを構成](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)を参照してください。  
  
|プロパティのバインド|説明|  
|----------------------|-----------------|  
|**InboundOperationType**|実行する受信操作を指定します。 通知メッセージを受信するこれを設定**通知**します。|  
|**NotificationPort**|Oracle データベースからのデータベース変更通知をリッスンする ODP.NET を開く必要があるポート番号を指定します。|  
|**NotificationStatement**|クエリ通知に登録するために使用する SELECT ステートメントを指定します。 アダプターは、指定した SELECT ステートメントの変更の結果セットの場合にのみ、通知メッセージを取得します。|  
|**NotifyOnListenerStart**|リスナーが開始されると、アダプターがアダプター クライアントに通知を送信するかどうかを指定します。|  
  
 これらのプロパティの詳細については、[for Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)を参照してください。 使用する方法の詳細については、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite から通知を受信するさらに読み進める。  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a>このトピックで通知メッセージの受信について説明する方法  
 示すために、このトピックでどのように[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]Oracle E-business Suite からのデータベースの増分変更の通知メッセージの受信をサポートするには、ACCOUNTACTIVTY テーブルへの変更の通知を受信するアダプターを構成しますが。 お知らせ ACCOUNTACTIVITY テーブルは、"TID"、「アカウント」および「処理済み」の列であると仮定します。 「処理済み」列の値を設定するたびに新しいレコードを追加すると、' n ' です。 そのため、インクリメンタル通知を取得するは、BizTalk オーケストレーションの一環として、次のタスクを実行する必要があります。  
  
- 「処理済み」であるすべてのレコードに関する通知を受け取ります 'n' です。 通知のステートメントと SELECT ステートメントを指定することで、これを行うことができます。  
  
- 特定のレコードの通知を受け取った後は、「処理」を 'y' に設定します。 「処理済み」列を更新する、PROCESS_RECORDS、ストアド プロシージャを実行して、これを行うことができます。  
  
  インクリメンタル通知の受信を示すために、次の項目行います。  
  
- スキーマを生成、**通知**(入力方向の操作)、および**PROCESS_RECORDS** (送信操作) ACCOUNTACTIVITY テーブルにします。  
  
- 次を含むオーケストレーションを作成します。  
  
  -   通知メッセージを受信する受信場所。 として、SELECT ステートメントを指定することで、通知を構成できます。  
  
      ```  
      SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’  
      ```  
  
      > [!NOTE]
      >  スキーマ名とテーブル名を指定する必要があります。 たとえば、 `SCOTT.ACCOUNTACTIVITY`のようにします。  
  
  -   通知が送信されて既に行を更新する送信ポートです。 通知を受信したレコードの 'y' の「処理済み」列の値を設定するには、このポートに PROCESS_RECORDS ストアド プロシージャが実行されます。  
  
       この操作は、処理された行が更新されるようにメッセージ通知の受信後に実行する必要がありますに注意してください。 通知応答を待機していると、PROCESS_RECORDS プロシージャを実行する要求メッセージを手動で削除のオーバーヘッドがすぐには、オーケストレーション自体内 PROCESS_RECORDS プロシージャの要求メッセージが生成されます。 使用して行うことができます、**メッセージの構築**図形をオーケストレーション内。  
  
## <a name="how-to-receive-notification-messages-from-oracle-e-business-suite"></a>Oracle E-business Suite から通知メッセージを受信する方法  
 Oracle E-business Suite を使用して、操作を実行する[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[Oracle E-business Suite のアプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)します。 これらのタスクは通知メッセージを受信するアダプターを構成するには。  
  
1. BizTalk プロジェクトを作成しのスキーマを生成し、**通知**(入力方向の操作) と**PROCESS_RECORDS** ACCOUNTACTIVITY テーブルでは、手順 (送信操作)。 値を指定する、必要に応じて、 **InboundOperationType**、 **NotificationPort**、および**NotificationStatement**プロパティをバインドします。  
  
2. Oracle E-business Suite から通知を受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
3. PROCESS_RECORDS ストアド プロシージャを実行して、応答メッセージを受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
4. 次のオーケストレーションを作成します。  
  
   -   Oracle E-business Suite から通知メッセージを受信します。  
  
   -   PROCESS_RECORDS プロシージャを実行するメッセージを作成します。  
  
   -   このメッセージを選択し、レコードの更新し、応答を受信する Oracle E-business Suite に送信します。  
  
5. ビルドし、BizTalk プロジェクトを配置します。  
  
6. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
   > [!NOTE]
   >  受信操作の場合、通知メッセージを受信するように Wcf-custom の一方向のみを構成する必要があります。 または Wcf-oracleebs 受信ポート。 双方向受信ポートは受信操作のサポートされていません。  
  
7. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 スキーマを生成する必要があります、**通知**操作と**PROCESS_RECORDS**プロシージャ。 参照してください[Visual Studio での Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)スキーマを生成する方法の詳細について。 スキーマを生成するときに、次のタスクを実行します。 デザイン時のバインドのプロパティを指定しない場合は、最初の手順をスキップします。  
  
1.  値を指定**InboundOperationType**、 **NotificationPort**、および**NotificationStatement**スキーマの生成中にプロパティをバインドします。 このバインドのプロパティの詳細については、[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)を参照してください。 バインドのプロパティを指定する方法については、[for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)を参照してください。  
  
2.  コントラクトの種類を選択します。**サービス (受信操作)** します。  
  
3.  スキーマの生成、**通知**操作。  
  
4.  コントラクトの種類を選択します。**クライアント (送信操作)** します。  
  
5.  スキーマの生成、 **PROCESS_RECORDS**プロシージャ。 この手順で使用可能な**ACCOUNT_PKG**パッケージ。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 スキーマが生成されるは、BizTalk プロジェクトのオーケストレーションからメッセージをリンクする必要があります。  
  
 このトピックでは、3 つのメッセージを作成する必要があります: 1、Oracle E-business Suite から通知を受け取る、PROCESS_RECORDS プロシージャを実行する 1 つおよびプロシージャの応答を受信する 1 つ。  
  
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
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選択と*OracleNotifyIncremental.OracleEBSBinding.Notification*ここで、 *OracleNotifyIncremental*の名前を指定します。BizTalk プロジェクト。 *OracleEBSBinding*に対して生成されたスキーマには、**通知**操作。|  
  
6.  手順 3 を 2 つの新しいメッセージを作成する. **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  
  
    |識別子を設定するには|メッセージの種類を設定|  
    |-----------------------|-------------------------|  
    |手順|*OracleNotifyIncremental.OracleEBSBinding1.PROCESS_RECORDS*ここで、 *OracleEBSBinding1*に対して生成されたスキーマには、 **PROCESS_RECORDS**プロシージャ。|  
    |ProcedureResponse|*OracleNotifyIncremental.OracleEBSBinding1.PROCESS_RECORDSResponse*|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]for Oracle E-business Suite から通知メッセージを受信し、通知を受信した行を更新します。 このオーケストレーションでの指定した SELECT ステートメントに基づいて、通知メッセージを受信、 **NotificationStatement**プロパティをバインドします。 通知メッセージは、ファイルの場所で受信されます。 応答が受信されると、オーケストレーションは通知を受信した行を更新する PROCESS_RECORDS プロシージャを呼び出すメッセージを構築します。 このメッセージの応答を同じファイルの場所で受信もします。  
  
 そのため、オーケストレーションは、次に含める必要があります。  
  
- 一方向の WCF カスタムまたは Wcf-oracleebs 通知メッセージを受信するポートを受信します。  
  
- 双方向の WCF カスタムまたは Wcf-oracleebs PROCESS_RECORDS プロシージャを実行するメッセージを送信するポートを送信します。  
  
- A**メッセージの構築**図形をオーケストレーション内での PROCESS_RECORDS プロシージャを実行する、メッセージを構築します。  
  
- ファイルは、通知メッセージと応答 PROCESS_RECORDS プロシージャを保存するポートを送信します。  
  
- 受信図形と送信図形。  
  
  サンプル オーケストレーションでは、次の項目に似ています。  
  
  ![Oracle から通知を受信するオーケストレーション](../../adapters-and-accelerators/adapter-oracle-database/media/cef49414-490a-4bd5-a32d-b3f4cde5950a.gif "cef49414-490a-4bd5-a32d-b3f4cde5950a")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 図形の列に示した名前は、単に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveNotification|Receive|-設定**名前**に*ReceiveNotification*<br /><br /> -設定**アクティブ**に*は True。*|  
|SaveNotification|Send|-設定**名前**に*SaveNotification*|  
|SendProcMessage|Send|-設定**名前**に*SendProcMessage*|  
|ReceiveProcResponse|Receive|-設定**名前**に*ReceiveProcResponse*|  
|SaveProcResponse|Send|-設定**名前**に*SaveProcResponse*|  
  
### <a name="adding-construct-message-shape"></a>メッセージの構築図形を追加します。  
 使用することができます、**メッセージの構築**図形をオーケストレーション内で PROCESS_RECORDS プロシージャを実行する要求メッセージを生成します。 これを行うには、追加する必要があります、**メッセージの構築**図形し、その中を**メッセージの割り当て**図形をオーケストレーションにします。 この例で、**メッセージの割り当て**図形は、プロシージャを実行する Oracle E-business Suite に送信されるメッセージを生成するコードを呼び出します。 **メッセージの割り当て**図形も、Oracle E-business Suite に送信するメッセージに対するアクションを設定します。  
  
 メッセージの構築図形で、設定、**メッセージ構築**プロパティを**プロシージャ**します。  
  
 応答を生成するコードは、BizTalk プロジェクトと同じ Visual Studio ソリューションの一部になります。 応答メッセージを生成するためのサンプル コードは、次のように検索します。  
  
```  
namespace MessageCreator  
{  
    public class MessageCreator  
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
  
 要求メッセージを生成できるように上記のコードの抜粋をする必要があります (PROCESS_RECORDS 手順) については、XML 要求メッセージに指定された場所で、`XmlFileLocation`変数。  
  
> [!NOTE]
>  プロジェクトをビルドした後に MessageCreator.dll がプロジェクト ディレクトリに作成されます。 この DLL は、グローバル アセンブリ キャッシュ (GAC) に追加する必要があります。 また、BizTalk プロジェクトに参照として、MessageCreator.dll を追加する必要があります。  
  
 次のコードを呼び出すには、次の式を追加、**メッセージの割り当て**図形とメッセージのアクションを設定します。 式を追加するには、ダブルクリック、**メッセージの割り当て**図形式エディターを開きます。  
  
```  
Procedure = MessageCreator.MessageCreator.XMLMessageCreator();  
Procedure(WCF.Action) = "PackageApis/SCOTT/ACCOUNT_PKG/PROCESS_RECORDS";  
```  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認します。 ポート列に示した名前は、オーケストレーションで表示されているポートの名前です。  
  
|Port|[プロパティ]|  
|----------|----------------|  
|OracleNotifyPort|-設定**識別子**に*OracleNotifyPort*<br /><br /> -設定**型**に*OracleNotifyPortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*受信*|  
|SaveMessagePort|-設定**識別子**に*SaveMessagePort*<br /><br /> -設定**型**に*SaveMessagePortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*送信*<br /><br /> -作成操作*通知*します。 この操作は、通知メッセージに使用されます。<br /><br /> -作成操作*プロシージャ*します。 この操作は、応答メッセージに使用されます。|  
|OracleOutboundPort|-設定**識別子**に*OracleOutboundPort*<br /><br /> -設定**型**に*OracleOutboundPortType*<br /><br /> -設定**通信パターン**に*要求-応答*<br /><br /> -設定**通信方向**に*送受信*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表では、プロパティとアクション図形のメッセージを指定して、メッセージ ポートにリンクを設定する必要があります、値を指定します。 図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveNotification|-設定**メッセージ**に*NotifyReceive*<br /><br /> -設定**操作**に*OracleNotifyPort.Notify.Request*|  
|SaveNotification|-設定**メッセージ**に*NotifyReceive*<br /><br /> -設定**操作**に*SaveMessagePort.Notify.Request*|  
|SendProcMessage|-設定**メッセージ**に*プロシージャ*<br /><br /> -設定**操作**に*OracleOutboundPort.Procedure.Request*|  
|ReceiveProcResponse|-設定**メッセージ**に*ProcedureResponse*<br /><br /> -設定**操作**に*OracleOutboundPort.Procedure.Response*|  
|SaveProcResponse|-設定**メッセージ**に*ProedureResponse*<br /><br /> -設定**操作**に*SaveMessagePort.Procedure.Request*|  
  
 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細についてを参照してください「オーケストレーションを構築および実行されている」 [ http://go.microsoft.com/fwlink/?LinkId=102359](http://go.microsoft.com/fwlink/?LinkId=102359)します。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**ペインで、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールにアプリケーションを構成します。 アプリケーションを構成する方法の詳細についてを参照してください「する方法をアプリケーションの構成」 [ http://go.microsoft.com/fwlink/?LinkID=196961](http://go.microsoft.com/fwlink/?LinkID=196961)します。  
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- 物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 このオーケストレーションの次の操作を行う必要があります。  
  
  - Wcf-oracleebs 一方向受信ポートまたは物理 Wcf-custom を定義します。 このポートは、Oracle E-business Suite から送る通知をリッスンします。 受信ポートを作成する方法についてを参照してください[、Oracle E-business アダプターを物理ポート バインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)します。 受信ポートのバインドのプロパティを指定することを確認します。  
  
    > [!IMPORTANT]
    >  デザイン時のバインドのプロパティが指定されている場合は、この手順を実行する必要はありません。 このような場合は、作成、受信ポートで、必要なバインドのプロパティを設定によって作成されたバインド ファイルをインポートすることによって、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 詳細については、[Oracle E-business Suite へのポートのバインド ファイルを物理ポートのバインドを使用して、を構成](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)を参照してください。  
  
    |プロパティのバインド|値|  
    |----------------------|-----------|  
    |**InboundOperationType**|これを設定**通知**します。|  
    |**NotificationPort**|Oracle データベースからのデータベース変更通知をリッスンする ODP.NET を開く必要があるポート番号を指定します。 これは、Windows ファイアウォールの例外リストに追加する必要があります、同じポート番号に設定します。 Windows ファイアウォールの例外リストにポートを追加する方法については、[ http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)を参照してください。<br /><br /> **重要:** これを既定値は-1 に設定すると、通知メッセージを受信する Windows ファイアウォールを完全に無効にする必要があります。|  
    |**NotificationStatement**|これを設定します。<br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’`<br /><br /> **注:** スキーマ名とテーブル名を指定する必要があります。 たとえば、 `SCOTT.ACCOUNTACTIVITY`のようにします。|  
    |**NotifyOnListenerStart**|これを設定**True**します。|  
  
     異なるバインディング プロパティの詳細については、[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)を参照してください。  
  
    > [!IMPORTANT]
    >  インターフェイス テーブルの通知を構成する場合は、必要なバインドのプロパティを指定することによってアプリケーション コンテキストを設定する必要があります。 アプリケーション コンテキストの設定の詳細については、[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)を参照してください。  
    > 
    > [!NOTE]
    >  使用して受信操作の実行中に、トランザクション分離レベルとトランザクションのタイムアウトを構成することをお勧めします。、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 WCF カスタムを構成するときに、サービスの動作を追加することで行うことができますか、Wcf-oracleebs 受信ポート。 サービスの動作を追加する方法については、[トランザクション分離レベルの構成と Oracle E-business Suite でのトランザクション タイムアウト](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)を参照してください。  
  
  - PROCESS_REOCRDS プロシージャを実行する Oracle E-business Suite にメッセージを送信する物理 Wcf-custom または Wcf-oracleebs 送信ポートを定義します。 送信ポートでアクションを指定することも必要があります。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションから Oracle E-business Suite、メッセージをドロップできる場所での場所を定義します。 Wcf-custom または Wcf-oracleebs を通じて実行する PROCESS_RECORDS プロシージャのメッセージの送信ポートと、これらは、Oracle E-business Suite から受信した通知メッセージとなります。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 Oracle E-business Suite から通知メッセージを受信するため、PROCESS_RECORDS プロシージャを実行するために、BizTalk アプリケーションを開始する必要があります。 BizTalk アプリケーションを開始する手順についてで「する方法をオーケストレーションの開始」を参照してください[ http://go.microsoft.com/fwlink/?LinkId=102387](http://go.microsoft.com/fwlink/?LinkId=102387)します。  
  
 この段階で、ことを確認します。  
  
-   Wcf-custom または Wcf-oracleebs 一方向受信ポートが実行されている Oracle E-business Suite から通知メッセージを受信します。  
  
-   PROCESS_RECORDS プロシージャを実行するには、Wcf-custom または Wcf-oracleebs 送信ポートが実行されています。  
  
-   Oracle E-business Suite からメッセージを受信する、ファイル送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 ACCOUNTACTIVITY テーブルが既にレコードの一部であると仮定します。 また、C:\TestLocation\MessageIn で使用される PROCESS_RECORDS プロシージャを実行する XML メッセージを確認します。 XML ファイルは、次のようになります。  
  
```  
<PROCESS_RECORDS xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/SCOTT/ACCOUNT_PKG" />  
```  
  
 BizTalk オーケストレーションを開始すると、次の一連のアクションが、同じシーケンス内の場所。  
  
-   アダプターは、次のような通知メッセージを受け取ります。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
      <Info>ListenerStarted</Info>   
      <Source>OracleEBSBinding</Source>   
      <Type>Startup</Type>   
    </Notification>  
    ```  
  
     このメッセージは、通知メッセージを受信する受信ポートが開始されたことを通知します。 注意の値、`<Info>`要素は、"ListnerStarted"。  
  
-   アダプターは、PROCESS_RECORDS プロシージャを実行します。 Oracle E-business Suite から [次へ] の応答は、手順についてはします。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <PROCESS_RECORDSResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/SCOTT/ACCOUNT_PKG">  
      <TABLE_DATA>  
        <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          <xs:element msdata:IsDataSet="true" name="NewDataSet">  
            <xs:complexType>  
              <xs:sequence>  
                <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  <xs:complexType>  
                    <xs:sequence>  
                      <xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="PROCESSED" type="xs:string" />   
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
        </diffgr:diffgram>  
      </TABLE_DATA>  
    </PROCESS_RECORDSResponse>  
    ```  
  
     これは、PROCESS_RECORDS プロシージャの一部として、SELECT ステートメントを実行するための応答です。  
  
-   PROCESS_RECORDS プロシージャでは、処理を 'y' に設定する行も更新されます。 そのため、アダプターは、更新操作に別の通知を受け取ります。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
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
  
     なお、`Info`要素には、"Update"が含まれています。  
  
-   2 つ目の通知後に、アダプターでは、PROCESS_RECORDS プロシージャがもう一度実行します。 ただし、今すぐに処理された列が設定されているレコードがないため、' n '、プロシージャは、次のような空の応答を返します。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <PROCESS_RECORDSResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/SCOTT/ACCOUNT_PKG">  
      <TABLE_DATA>  
        <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          <xs:element msdata:IsDataSet="true" name="NewDataSet">  
            <xs:complexType>  
              <xs:sequence>  
                <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  <xs:complexType>  
                    <xs:sequence>  
                      <xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="PROCESSED" type="xs:string" />   
                    </xs:sequence>  
                  </xs:complexType>  
                </xs:element>  
              </xs:sequence>  
            </xs:complexType>  
          </xs:element>  
        </xs:schema>  
        <diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
          <NewDataSet xmlns="" />   
        </diffgr:diffgram>  
      </TABLE_DATA>  
    </PROCESS_RECORDSResponse>  
    ```  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定、ファイルからインポートできます。 バインド ファイルの詳細については、[Oracle E-business suite アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [Oracle E-business Suite データベース変更通知 BizTalk Server を使用しての受信します。](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-biztalk-server.md)