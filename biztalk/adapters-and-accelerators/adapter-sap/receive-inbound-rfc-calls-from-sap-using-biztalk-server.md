---
title: "RFC 呼び出しの受信を BizTalk Server を使用して SAP から受信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: RFC calls, receiving using BizTalk Server
ms.assetid: 822fd9fb-772f-4910-a11e-25c1d5dca6e1
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b949ae0d6d5938493c78ed542a67d3c8bd09b48
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="receive-inbound-rfc-calls-from-sap-using-biztalk-server"></a>BizTalk Server を使用して SAP から受信 RFC 呼び出しの受信します。
RFC サーバーのシナリオでは、3 つのエンティティがあります。  
  
-   SAP RFC を呼び出すために、要求を送信する SAP クライアント。 SAP GUI を使用して、または、RFC クライアントを通じて呼び出しをすることでこの呼び出すが、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
-   SAP クライアントが呼び出す RFC 関数定義を含む SAP システムです。 要求で、SAP システムでは、RFC サーバー (アダプター) を渡します。 これは、操作は、SAP サーバーは、アダプターに、RFC 呼び出しのメタデータを取得するアダプターによって使用されます。  
  
-   [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]は RFC サーバーとして機能し、実際の RFC をホストします。  
  
 最初のエンティティでは、SAP クライアントは、このトピックでは説明しません。 RFC を呼び出すため、SAP GUI を使用している場合は、SAP のマニュアルを参照してください。 使用している場合、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] RFC を呼び出すを参照してください。[呼び出しを使用して BizTalk Server での SAP Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)です。  
  
 このセクションでは、RFC が SAP クライアントによって呼び出されると、RFC サーバー呼び出しを受信するアダプターを使用する方法の指示を提供します。 アダプターが受信側の RFC をサポートする方法の詳細についてサーバーの呼び出しを使用して、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP Rfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)です。  
  
## <a name="how-to-receive-an-inbound-rfc-call-from-the-sap-system"></a>SAP システムから受信 RFC 呼び出しを受信する方法は?  
 SAP システムを使用して、操作を実行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [SAP アプリケーションを作成するビルド ブロック](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)です。 これらのタスクは、SAP システムから、RFC 呼び出しを受信するには。  
  
1.  RFC をここでは、外部アプリケーションに送信する SAP システムを構成、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
2.  BizTalk プロジェクトを作成し、RFC のスキーマを生成する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムから受信します。  
  
3.  SAP システムからメッセージを受信して応答を送信する BizTalk プロジェクトでメッセージを作成します。  
  
4.  SAP システムから RFC を受信、処理、および SAP システムへの応答を送信するためのオーケストレーションを作成します。  
  
5.  構築し、BizTalk プロジェクトを展開します。  
  
6.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
7.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="activities-on-the-sap-system"></a>SAP システムでのアクティビティ  
 使用する前に、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムから受信 RFC 呼び出しを受信するには、SAP システムで、次のタスクを完了するを確認してください。  
  
-   SAP アダプターの RFC 変換先が存在する必要があります。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムで定義されている、RFC 変換先を使用して SAP システムからの Rfc を受信します。 RFC 転送先には、SAP ゲートウェイ ホスト、SAP ゲートウェイ サービスと、SAP プログラム ID をコードで接続 URI で指定する必要がありますが含まれています。 SAP に、RFC 変換先をセットアップする方法については、次を参照してください。 [Create RFC、RFC 変換先、および送信の SAP システムから RFC](creating-an-rfc-in-an-sap-system.md)です。  
  
-   SAP システムで、RFC を定義する関数モジュールを作成する必要があります。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムで、RFC 定義を使用して、RFC (デザイン時および実行時に両方) に関するメタデータを取得します。 詳細については、次を参照してください。 [SAP システムで RFC を作成する](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md)です。  
  
     RFC を 2 つの整数を追加し、その結果を返しますの SAP システム上のソース コードの例を次に示します。 コードでは、指定した宛先を介して、RFC だけ呼び出します。 関数の実装は、SAP アダプターのクライアント コードで行われます。  
  
    ```  
    FUNCTION Z_RFC_ADD.  
    *"------------------------------------------------------------------  
    *"  
    *"Local interface:  
    *"  IMPORTING  
    *"     VALUE(X) TYPE  INT4  
    *"     VALUE(Y) TYPE  INT4  
    *"     VALUE(DEST) TYPE  CHAR20 DEFAULT 'SAPADAPTER'  
    *"  EXPORTING  
    *"     VALUE(RESULT) TYPE  INT4  
    *"------------------------------------------------------------------  
    CALL FUNCTION 'Z_RFC_ADD' DESTINATION DEST  
      EXPORTING X = X  
                Y = Y  
      IMPORTING RESULT = RESULT.  
  
    ENDFUNCTION.  
    ```  
  
## <a name="sample-based-on-this-topic"></a>このトピックの内容に基づくサンプル  
 サンプルは、RFCServer、このトピックの内容に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。 [SAP アダプターのサンプル](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)です。  
  
## <a name="generating-the-schema"></a>スキーマを生成します。  
 このトピックでは、SAP システムから受信 RFC 呼び出しを受信する方法を示すおスキーマを生成*Z_RFC_ADD* RFC です。 前の手順では、この RFC を作成します。 この RFC では、入力パラメーターとして 2 つの整数値を受け取ります。  
  
 参照してください[参照、検索、および get メタデータの SAP RFC 操作](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)手順については、特定の RFC のスキーマを生成する方法です。  
  
> [!IMPORTANT]
>  受信 RFC 呼び出しのスキーマを生成するために選択を確認してください**サービス (入力方向の操作)**から、**選択コントラクト型**ドロップダウン リストで、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]です。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションの種類からのメッセージに最初の手順で生成したスキーマをリンクする必要があります。  
  
 このトピックでは、2 つのメッセージを作成する必要があります: SAP システムとは、SAP システムへの応答を送信するメッセージを受信する 1 つです。  
  
 メッセージを作成し、スキーマにそれらをリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  新しいオーケストレーションを BizTalk プロジェクトに追加します。  
  
2.  オーケストレーションの種類、BizTalk プロジェクトを開くまだ開いていない場合。 をクリックして**ビュー**、 をポイント**その他のウィンドウ**、 をクリック**オーケストレーション**です。  
  
3.  **オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。  
  
4.  右クリックし、新規メッセージを作成および選択**プロパティ ウィンドウ**します。  
  
5.  **プロパティ**のウィンドウ**Message_1**次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**要求**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*RFCServer.SAPBindingSchema.Z_RFC_ADD*ここで、 *RFCServer* BizTalk プロジェクトの名前を指定します。 *SAPBindingSchema* RFC に対して生成されたスキーマは、 *Z_RFC_ADD*です。|  
  
6.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**新しいメッセージ用のウィンドウは、以下を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**応答**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*RFCServer.SAPBindingSchema.Z_RFC_ADDResponse*です。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SAP システムから RFC サーバー呼び出しを受信するためです。 この例では、RFC クライアントが 2 つの整数を追加する SAP システムに要求を送信するシナリオを検討してください。 SAP システムが、入力パラメーターを使用して、要求を受け取り、によってホストされている外部の RFC サーバーに渡します、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]プロセス 2 つの整数を追加する要求を SAP システムから要求を受信し、応答を生成します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 、順番に渡される RFC クライアント SAP システムへの応答を渡します。  
  
 これを実現するオーケストレーションの一部として、オーケストレーションを含める必要があります。  
  
-   双方向の受信ポートを SAP システムから、RFC サーバーによって要求を受信し、応答を送信します。  
  
-   送信図形と受信図形。  
  
-   メッセージの構築図形、RFC サーバー要求を処理する、メッセージの割り当て図形が SAP システムから送信されるとします。  
  
 RFC サーバー呼び出しのサンプルのオーケストレーションには、次のようになります。  
  
 ![RFC サーバー呼び出しを行うオーケストレーション](../../adapters-and-accelerators/adapter-sap/media/f5da2947-56d6-41f0-b411-c8e6eacf68cd.gif "f5da2947-56d6-41f0-b411-c8e6eacf68cd")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。 示されている名前、*図形*列が上記のオーケストレーションで表示される、メッセージの構築図形の名前を示します。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ListenToSAP|Receive|-設定**名前**に*ListenToSAP*<br />-設定**アクティブ**に*は True。*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
### <a name="adding-construct-message-shape"></a>メッセージの構築図形を追加します。  
 2 つの整数値を追加する受信の RFC 呼び出しを処理するには、メッセージの構築図形を追加する必要があり、そのを 2 つの間、オーケストレーションにメッセージの割り当て図形が図形を送信します。 この例では、2 つの整数を追加するメッセージの割り当て図形を呼び出します。 メッセージの割り当て図形では、SAP システムに送信される応答のアクションも設定します。  
  
 メッセージの構築図形、設定、**メッセージ構築**プロパティを**応答**です。  
  
 RFC の要求を処理するコードは、BizTalk プロジェクトと同じ Visual Studio ソリューションの一部になります。 2 つの整数を追加するためのサンプル コードは、次のように検索します。  
  
```  
namespace RFCServerResponseCreator  
{  
    public class RFCServerResponseCreator  
    {  
        private static XmlDocument messageIn;  
        private static XmlDocument messageOut;  
        public static XmlDocument CreateRequest(int a, int b, string destination)  
        {  
            messageIn = new XmlDocument();  
            messageIn.LoadXml(  "<Z_RFC_ADD xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\">" +  
                                "<DEST>" + destination + "</DEST>" +  
                                "<X>" + a + "</X>" +  
                                "<Y>" + b + "</Y>" +   
                                "</Z_RFC_ADD>"  
                             );  
            return messageIn;  
        }  
        public static XmlDocument CreateResponse(int a, int b)  
        {  
            int c = a + b;  
            messageOut = new XmlDocument();  
            messageOut.LoadXml( "<Z_RFC_ADDResponse xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\">" +  
                                "<RESULT>" + c + "</RESULT>" +   
                                "</Z_RFC_ADDResponse>"  
                              );  
            return messageOut;  
        }  
    }  
}  
```  
  
> [!NOTE]
>  プロジェクトをビルドした後、RFCServerResponseCreator.dll はプロジェクト ディレクトリに作成されます。 グローバル アセンブリ キャッシュ (GAC) には、この DLL を追加する必要があります。  
  
 メッセージの割り当て図形から次のコードを呼び出すと、SAP システムに送信される応答のアクションを設定する次の式を追加します。 式を追加するには、式エディターを開く、メッセージの割り当て図形をダブルクリックします。  
  
```  
Response = RFCServerResponseCreator.RFCServerResponseCreator.CreateResponse(Request.X, Request.Y);  
Response(WCF.Action) = "http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADD/response";  
```  
  
> [!IMPORTANT]
>  応答メッセージのアクションを明示的に設定する必要があります。 アクションを設定しないと、Wcf-custom アダプターは要求された操作を"Response"を追加することによって、アクション メッセージでに到着します。 そのため、応答メッセージのアクションを`http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADDResponse`です。 ただし、sapBinding が必要ですが、応答アクションを追加して"/応答"例については、要求された操作に`http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADD/response`です。  
  
### <a name="adding-ports"></a>ポートの追加  
 次のプロパティ、論理ポートを指定することを確認してください。 表示される名前、*ポート*列は、ポートの名前、オーケストレーションで表示されます。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|RFCServerPort|-設定**識別子**に*RFCServerPort*<br />-設定**型**に*RFCServerPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*受信送信*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表は、プロパティと、メッセージのアクション図形およびポートにリンクすることを指定するために設定するには、その値を指定します。 示されている名前、*図形*列が上記のオーケストレーションで表示される、メッセージの構築図形の名前を示します。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ListenToSAP|-設定**メッセージ**に*要求*<br />-設定**操作**に*RFCServerPort.Add.Request*|  
|SendResponse|-設定**メッセージ**に*FuncResponse*<br />-設定**操作**に*RFCServerPort.Add.Response*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 これで、BizTalk ソリューションをビルドしして、BizTalk Server に展開する必要があります。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 アプリケーションの構成の詳細については、次を参照してください。[アプリケーションを構成する方法](../../core/how-to-configure-an-application.md)です。
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   WCF カスタム定義または WCF SAP 受信ポートにします。 このポートは、SAP システムから受信 RFC 呼び出しを受信および SAP システムへの応答を送信します。 ポートを作成する方法については、次を参照してください。 [SAP アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)です。  
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または受信ポート (着信)、BizTalk 管理コンソールからこのバインド ファイルをインポートすることができます。 詳細については、次を参照してください。 [sap ポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)です。
  
 RFCServerResponseCreator プロジェクトのアセンブリを BizTalk アプリケーションに追加することも必要があります。 SAP システムから受信した RFC 呼び出しを処理するには、このプロジェクトを作成したとします。 そのためには次を行います。  
  
1.  右クリックし、バインドをインポートする BizTalk アプリケーションの下で、BizTalk Server 管理コンソールの左側にあるコンソール ツリーで**リソース**、 をポイント**追加**をクリックし、**BizTalk アセンブリ**です。  
  
2.  **リソースの追加**] ダイアログ ボックス、[**追加**、し RFCServerResponseCreator.dll を含むフォルダーに移動します。 ファイルを選択し、をクリックして**開く**です。  
  
3.  **リソースの追加**ダイアログ ボックスで、をクリックして**OK**です。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 SAP システムから受信 RFC 呼び出しを受信するための BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)、および[アプリケーションを起動する方法](../../core/how-to-start-and-stop-a-biztalk-application.md)です。
  
 この段階で確認します。  
  
-   Wcf-custom または WCF SAP RFC 呼び出しを受信するポートが表示される SAP システムを実行しています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後は、するには、RFC を送信する必要があります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 SAP システムでトランザクション SE37 を実行することによって行うことができます。 RFC 呼び出しの入力パラメーターも指定する必要があります。 アダプターは、パラメータと共に呼び出しを受信、処理、および SAP システムへの応答を送信します。 RFC を送信してから、同じトランザクションの応答を表示することができます。  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 例外については、BizTalk Server を使用して SAP システムから RFC サーバー呼び出しを受信中に発生する可能性が、次を参照してください。[例外とエラー処理、SAP アダプター](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)です。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。[を再利用の SAP アダプターのバインド](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)です。
  
## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)