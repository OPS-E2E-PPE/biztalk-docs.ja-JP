---
title: BizTalk Server を使用して SAP から受信 RFC 呼び出しを受信する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RFC calls, receiving using BizTalk Server
ms.assetid: 822fd9fb-772f-4910-a11e-25c1d5dca6e1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e70e2b81fd71a01ef6eae9e77ae3efea8cbf494
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986987"
---
# <a name="receive-inbound-rfc-calls-from-sap-using-biztalk-server"></a>BizTalk Server を使用して SAP から受信 RFC 呼び出しを受信します。
RFC サーバーのシナリオでは、3 つのエンティティがあります。  
  
- SAP RFC を呼び出すために、要求を送信する SAP クライアント。 これは、呼び出すことができる、SAP GUI を使用して、または、RFC クライアントを介して呼び出しを行うことで、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
- SAP クライアントが呼び出す RFC 関数の定義を含む SAP システム。 要求での SAP システムでは、RFC サーバー (アダプター) に渡します。 これは、SAP サーバーがアダプターには、RFC 呼び出しのメタデータを取得するアダプターによって使用されます。  
  
- [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]は RFC サーバーとして機能し、実際の RFC をホストします。  
  
  最初のエンティティでは、SAP のクライアントは、このトピックでは説明しません。 RFC を呼び出すために、SAP GUI を使用する場合は、SAP のマニュアルを参照してください。 使用する場合、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] RFC を呼び出すを参照してください。[を使用して BizTalk Server での SAP の Rfc を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)します。  
  
  このセクションでは、アダプターを使用して、RFC が SAP クライアントによって呼び出されると、RFC サーバー呼び出しを受信する方法を説明します。 サーバーを使用してを呼び出す、アダプターが受信側の RFC をサポートする方法の詳細については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP で Rfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)します。  
  
## <a name="how-to-receive-an-inbound-rfc-call-from-the-sap-system"></a>SAP システムから受信 RFC 呼び出しを受信する方法でしょうか。  
 使用して SAP システムでの操作を実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[SAP アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)します。 これらのタスクは、SAP システムから RFC 呼び出しを受信するには。  
  
1. この場合、外部のアプリケーションに RFC を送信する SAP システムを構成、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
2. BizTalk プロジェクトを作成し、RFC のスキーマを生成する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムから受信します。  
  
3. SAP システムからメッセージを受信して応答を送信する BizTalk プロジェクトでは、メッセージを作成します。  
  
4. SAP システムからの RFC の受信、処理、および SAP システムへの応答を送信するためのオーケストレーションを作成します。  
  
5. ビルドし、BizTalk プロジェクトを配置します。  
  
6. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
7. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="activities-on-the-sap-system"></a>SAP システムでのアクティビティ  
 使用する前に、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムから受信 RFC 呼び出しを受信する SAP システムでは、次のタスクの完了を確認します。  
  
- SAP アダプターの RFC 転送先が存在する必要があります。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Rfc を SAP システムで定義された RFC 転送先を使用して SAP システムから受信します。 RFC 転送先には、SAP ゲートウェイ ホスト、SAP ゲートウェイ サービス、および SAP プログラム ID をコードで接続 URI で指定する必要がありますが含まれています。 SAP で RFC 転送先をセットアップする方法については、[RFC を作成する、RFC 変換先、および RFC を送信する SAP システムから](creating-an-rfc-in-an-sap-system.md)を参照してください。  
  
- SAP システムに対する RFC を定義する関数モジュールを作成する必要があります。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] (デザイン時および実行時の両方)、RFC に関するメタデータを取得する SAP システムの RFC 定義を使用します。 詳細については、[SAP システムでの RFC を作成する](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md)を参照してください。  
  
   次は、RFC を 2 つの整数を追加し、その結果を返しますの SAP システムのソース コードの例です。 コードは、指定した変換先をだけで、RFC を呼び出します。 関数の実装は、SAP アダプター クライアントのコードによって実行されます。  
  
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
  
## <a name="sample-based-on-this-topic"></a>このトピックに基づくサンプル  
 サンプル RFCServer、このトピックの「に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、[SAP アダプターのサンプル](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)を参照してください。  
  
## <a name="generating-the-schema"></a>スキーマを生成します。  
 このトピックで、SAP システムから受信 RFC 呼び出しを受信する方法を示すためにスキーマを生成*Z_RFC_ADD* RFC します。 この RFC は、前の手順で作成されます。 この RFC では、入力パラメーターとして 2 つの整数値を受け取ります。  
  
 参照してください[参照、検索、および SAP の RFC 操作のメタデータを get](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md) RFC を特定のスキーマを生成する方法の詳細について。  
  
> [!IMPORTANT]
>  受信 RFC 呼び出しのスキーマを生成するため、選択して確認**サービス (受信操作)** から、**コントラクト型を選択します**ドロップダウン リストで、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]します。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションからメッセージを最初の手順で生成したスキーマをリンクする必要があります。  
  
 このトピックでは、2 つのメッセージを作成する必要があります: 1 つから、SAP システムと他の SAP システムへの応答を送信するメッセージを受信します。  
  
 メッセージを作成し、スキーマにリンクするには、次の手順に従います。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  新しいオーケストレーションを BizTalk プロジェクトに追加します。  
  
2.  オーケストレーションの種類を BizTalk プロジェクトを開くまだ開いていない場合。 をクリックして**ビュー**、 をポイント**その他の Windows**、 をクリック**オーケストレーション**します。  
  
3.  **オーケストレーション**、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。  
  
4.  右クリックし、新規メッセージを作成および選択**プロパティ ウィンドウ**します。  
  
5.  **プロパティ**ウィンドウ **[message_1]** 次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**要求**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選択と*RFCServer.SAPBindingSchema.Z_RFC_ADD*ここで、 *RFCServer* BizTalk プロジェクトの名前を指定します。 *SAPBindingSchema*は、RFC の生成スキーマ*Z_RFC_ADD*します。|  
  
6.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**応答**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選択および*RFCServer.SAPBindingSchema.Z_RFC_ADDResponse*します。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SAP システムから RFC サーバー呼び出しを受信します。 この例では、RFC クライアントが 2 つの整数を追加する SAP システムに要求を送信するシナリオを検討してください。 SAP システムが、入力パラメーターを使用して、要求を受け取り、外部でホストされている RFC サーバーに渡します、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]プロセス 2 つの整数を追加する要求である SAP システムから要求を受け取り、応答が生成されます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] RFC クライアントにさらに、渡される SAP システムへの応答を渡します。  
  
 オーケストレーションの一部として、これを実現するには、オーケストレーションを含める必要があります。  
  
- 双方向の受信ポートを SAP システムから RFC サーバー要求を受信し、応答を送信します。  
  
- 送信し、受信図形。  
  
- メッセージの構築図形、内では、SAP システムから送信されるメッセージの割り当て図形、RFC サーバー要求を処理するとします。  
  
  RFC サーバー呼び出しのサンプル オーケストレーションでは、次の項目に似ています。  
  
  ![RFC サーバー呼び出しを行うためのオーケストレーション](../../adapters-and-accelerators/adapter-sap/media/f5da2947-56d6-41f0-b411-c8e6eacf68cd.gif "f5da2947-56d6-41f0-b411-c8e6eacf68cd")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 表示される名前、*図形*前のオーケストレーションに表示される、列は、メッセージの構築図形の名前。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ListenToSAP|Receive|-設定**名前**に*ListenToSAP*<br />-設定**アクティブ**に*は True。*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
### <a name="adding-construct-message-shape"></a>メッセージの構築図形を追加します。  
 2 つの整数値を追加する受信 RFC 呼び出しを処理するには、メッセージの構築図形を追加する必要があり、2 つの間、オーケストレーションにメッセージの割り当て図形の送信図形内でします。 この例では、2 つの整数を追加するメッセージの割り当て図形を呼び出します。 メッセージの割り当て図形では、SAP システムに送信される応答のアクションも設定します。  
  
 メッセージの構築図形で、設定、**メッセージ構築**プロパティを**応答**します。  
  
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
>  プロジェクトをビルドした後に RFCServerResponseCreator.dll がプロジェクト ディレクトリに作成されます。 この DLL は、グローバル アセンブリ キャッシュ (GAC) に追加する必要があります。  
  
 メッセージの割り当て図形から次のコードを呼び出すと、SAP システムに送信する応答のアクションを設定するのには、次の式を追加します。 式を追加するには、式エディターを開きますメッセージの割り当て図形をダブルクリックします。  
  
```  
Response = RFCServerResponseCreator.RFCServerResponseCreator.CreateResponse(Request.X, Request.Y);  
Response(WCF.Action) = "http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADD/response";  
```  
  
> [!IMPORTANT]
>  応答メッセージのアクションを明示的に設定する必要があります。 アクションを設定しないと、WCF カスタム アダプターが"Response"要求された操作を追加することでのアクションのメッセージが到着します。 そのため、応答メッセージのアクションを`http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADDResponse`します。 ただし、sapBinding が必要ですが、応答アクションを追加して"/応答"例については、要求アクションに`http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADD/response`します。  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートの次のプロパティを指定することを確認します。 名前、*ポート*列が、ポートの名前、オーケストレーションに表示されます。  
  
|Port|[プロパティ]|  
|----------|----------------|  
|RFCServerPort|-設定**識別子**に*RFCServerPort*<br />-設定**型**に*RFCServerPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*受信送信*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表には、プロパティとメッセージのアクション図形とポートにリンクすることを指定するために設定するには、その値を指定します。 表示される名前、*図形*前のオーケストレーションに表示される、列は、メッセージの構築図形の名前。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ListenToSAP|-設定**メッセージ**に*要求*<br />-設定**操作**に*RFCServerPort.Add.Request*|  
|SendResponse|-設定**メッセージ**に*FuncResponse*<br />-設定**操作**に*RFCServerPort.Add.Response*|  
  
 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 BizTalk ソリューションを構築するようになりましたし、BizTalk Server にデプロイする必要があります。 詳細については、[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)を参照してください。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 アプリケーションを構成する方法の詳細については、[アプリケーションを構成する方法](../../core/how-to-configure-an-application.md)を参照してください。
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
  - WCF カスタム定義または WCF SAP 受信ポート。 このポートでは、SAP システムから受信 RFC 呼び出しを受け取るし、SAP システムへの応答に送信されます。 ポートを作成する方法については、[SAP アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)を参照してください。  
  
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または (着信) 用のポートを受信する BizTalk 管理コンソールから、このバインド ファイルをインポートできます。 詳細については、[sap ポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)を参照してください。
  
  BizTalk アプリケーションに RFCServerResponseCreator プロジェクトのアセンブリを追加することも必要があります。 SAP システムから受信 RFC 呼び出しを処理するには、このプロジェクトを作成したとします。 そのためには次を行います。  
  
1.  右クリックし、バインドをインポートする BizTalk アプリケーションの下で、BizTalk Server 管理コンソールの左側にあるコンソール ツリーで**リソース**、 をポイント**追加**、順にクリックします**BizTalk アセンブリ**します。  
  
2.  **リソースの追加** ダイアログ ボックスをクリックします**追加**RFCServerResponseCreator.dll を含むフォルダーに移動します。 ファイルを選択し、をクリックし、**オープン**します。  
  
3.  **リソースの追加**ダイアログ ボックスで、をクリックして**OK**。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 SAP システムから受信 RFC 呼び出しを受信するための BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを開始する手順については、[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)、および[アプリケーションを起動する方法](../../core/how-to-start-and-stop-a-biztalk-application.md)を参照してください。
  
 この段階で、ことを確認します。  
  
-   受信 RFC 呼び出しを受信するポートの Wcf-custom または WCF SAP SAP からシステムが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後に RFC を送信する必要があります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 SAP システムでトランザクション SE37 を実行することによって行うことができます。 RFC 呼び出しの入力パラメーターを指定することも必要があります。 アダプターは、パラメーターと呼び出しを受信、処理、および SAP システムへの応答を送信します。 RFC を送信してから、同じトランザクションで、応答が表示できるようにします。  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 BizTalk Server を使用して SAP システムから RFC サーバー呼び出しを受信中に発生する可能性が、例外については、[例外とエラーは、SAP アダプターを使用した処理](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)を参照してください。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した後は、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありませんように、ファイルから構成設定をインポートできます。 バインド ファイルの詳細については、[再利用の SAP アダプター バインド](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)を参照してください。
  
## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)