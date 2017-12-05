---
title: "BizTalk Server を使用して SAP で tRFCs を呼び出す |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tRFCs, invoking using BizTalk Server
ms.assetid: 9489adca-cf2c-4e15-8573-445acd7ebf73
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4eeaa8b0d67e4592ef6622f747a1ddaea875084d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-trfcs-in-sap-using-biztalk-server"></a>BizTalk Server を使用して SAP で tRFCs を呼び出す
トランザクション リモート関数呼び出し (tRFCs) は、SAP システムの RFC の 1 つだけのランタイム実行を保証します。 いずれかの側に表示される、Rfc を呼び出すことができます、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] tRFC として。 RFC の呼び出しと似ています、tRFC の呼び出し (を参照してください[呼び出しを使用して BizTalk Server での SAP Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md))、次の点が異なります。  
  
-   [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェスの別のノードの下にある tRFCs (**TRFC**) の Rfc より (**RFC**)。  
  
-   tRFC 操作に含めるによって tRFC の SAP トランザクション ID にマップされている GUID パラメーター、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
-   TRFC の呼び出し後に呼び出す RfcConfirmTransID 操作 (コミット)、SAP システムで tRFC を確認する必要があります。 この操作はの直下に表示される、 **TRFC**内のノード[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
 方法の詳細については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、tRFC の呼び出しをサポートするを参照してください[SAP で tRFCs に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)です。 SOAP の構造の詳細については、tRFC の呼び出しのメッセージを参照してください[tRFC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)です。  
  
## <a name="how-to-invoke-a-trfc-in-an-sap-system-using-biztalk-server"></a>SAP システムを使用して BizTalk Server で tRFC を呼び出す方法ですか。  
 SAP システムを使用して、操作を実行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [SAP アプリケーションを作成するビルド ブロック](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)です。 SAP システムで、tRFC を呼び出し、これらのタスクです。  
  
1.  BizTalk プロジェクトを作成し、SAP システムで、呼び出し先 tRFC のスキーマを生成します。 スキーマを生成することも必要があります、 **RfcConfirmTransID** TID を SAP システムにコミットする操作。  
  
2.  SAP システムからメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  SAP システムで、tRFC を呼び出すし、によって tRFC の呼び出しに対する応答での SAP システムで作成される TID をコミットするオーケストレーションを作成、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックの内容に基づくサンプル  
 サンプルは、tRFCClient、このトピックの内容に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。 [SAP アダプターのサンプルを](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)です。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 TRFC を使用して、起動する方法を示すために、このトピックで、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]のスキーマを生成します。  
  
-   *BAPI_SALESORDER_CREATEFROMDAT2* tRFC です。  
  
-   RfcConfirmTransID 操作です。 この操作を使用すると、SAP システムで作成される TID をコミットするのに必要があります。 SAP システムがこの呼び出しを受け取った後、TID をシステムから削除します。  
  
 参照してください[参照、検索、および tRFC SAP の操作のメタデータを取得](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-trfc-operations-in-sap.md)スキーマを生成する方法についての詳細。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションの種類からのメッセージを生成したスキーマをリンクする必要があります。  
  
 このトピックでは、4 つのメッセージを作成する必要があります: RfcConfirmTransID 操作を呼び出すため、要求-応答メッセージを呼び出し、tRFC および別の要求-応答メッセージに設定を設定します。  
  
 メッセージを作成し、スキーマにそれらをリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションの種類、BizTalk プロジェクトを開くまだ開いていない場合。 をクリックして**ビュー**、 をポイント**その他のウィンドウ**、 をクリック**オーケストレーション**です。  
  
2.  **オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。  
  
3.  右クリックし、新規メッセージを作成および選択**プロパティ ウィンドウ**します。  
  
4.  **プロパティ**のウィンドウ**Message_1**次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**要求**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**メッセージの種類を選択します。 たとえば、選択*tRFC_Client.SAPBindingSchema1.BAPI_SALESORDER_CREATEFROMDAT2*ここで、 *tRFC_Client* BizTalk プロジェクトの名前を指定します。 *SAPBindingSchema1*に対して生成されたスキーマは、 *BAPI_SALESORDER_CREATEFROMDAT2*です。|  
  
5.  次の 3 つ以上のメッセージを作成する前の手順を繰り返します。 **プロパティ**、新しいメッセージ ウィンドウ、次の操作です。  
  
    |識別子に設定します。|メッセージの種類を設定|  
    |-----------------------|-------------------------|  
    |応答|*tRFC_Client.SAPBindingSchema1.BAPI_SALESORDER_CREATEFROMDAT2Response*|  
    |TIDRequest|*tRFC_Client.SAPBindingSchema3.RfcConfirmTransID*|  
    |TIDResponse|*tRFC_Client.SAPBindingSchema3.RfcConfirmTransIDResponse*|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]tRFCs を SAP システムで起動するためです。 このオーケストレーションで削除する要求メッセージに、定義されている受信場所。 オーケストレーションは、このメッセージを消費し、SAP システムに渡します。 応答は、SAP から受信したされ、別の場所に保存されます。 応答メッセージには、GUID が含まれています。 オーケストレーションが含まれています、**メッセージの構築**を応答から GUID を抽出しのスキーマに準拠したメッセージの構築図形、 **RfcConfirmTransID**操作します。 呼び出すメッセージ、 **RfcConfirmTransID**操作は、SAP としてシステムに送信の GUID を持つパラメーター _ 続けて、SAP システムで tRFCs を呼び出すための一般的なオーケストレーション、 **RfcConfirmTransID**操作が含まれます。  
  
-   SAP システムにメッセージを送信し、応答を受信する図形を送受信します。  
  
-   メッセージの構築図形内のメッセージを構築する図形のメッセージの割り当てと、 **RfcConfirmTransID**操作します。  
  
-   一方向の受信ポートを tRFC の呼び出しに SAP システムに送信する要求メッセージを受信します。  
  
-   双方向の送信ポートを tRFC を起動し、応答を受信するメッセージを送信します。  
  
-   双方向の送信ポートを呼び出すメッセージを送信する、 **RfcConfirmTransID**操作応答を受信します。  
  
-   2 つの一方向の送信フォルダーを SAP システムからの応答を送信するポート。  
  
 サンプル オーケストレーションには、次のようになります。  
  
 ![TRFC クライアント呼び出しを行うオーケストレーション](../../adapters-and-accelerators/adapter-sap/media/369d62dd-9ae4-4673-b346-03d2acfb453a.gif "369d62dd-9ae4-4673-b346-03d2acfb453a")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 各メッセージの構築図形の次のプロパティを指定します。 示されている名前、*図形*列が上記のオーケストレーションで表示される、メッセージの構築図形の名前を示します。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveXml|Receive|-設定**名前**に*ReceiveXml*<br />-設定**アクティブ**に*は True。*|  
|SendToLOB|Send|-設定**名前**に*SendToLOB*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
|SendTIDMsg|Send|-設定**名前**に*SendTIDMsg*|  
|ReceiveTIDRsp|Receive|-設定**名前**に*ReceiveTIDRsp*<br />-設定**アクティブ**に*False*|  
|SendTIDRsp|Send|-設定**名前**に*SendTIDRsp*|  
  
### <a name="adding-the-construct-message-shape"></a>メッセージの構築図形を追加します。  
 TRFC の呼び出しの SAP システムからの応答には、GUID が含まれています。 TRFC の呼び出しをコミットするには、RfcConfirmTransID 操作には、同じ GUID を渡す必要があります。 メッセージの構築図形を含める必要があり、そのメッセージの割り当て図形をオーケストレーションでします。 ここでは、メッセージの構築図形の目的は次のとおりです。  
  
-   TRFC の呼び出しの SAP システムから受信した応答から GUID を抽出します。  
  
-   RfcConfirmTransID 操作のメッセージ スキーマに準拠したメッセージを作成します。  
  
 設定する必要があります、メッセージの構築図形、**メッセージ構築**プロパティを**TIDRequest**です。  
  
 メッセージの割り当て図形には、次のコードの抜粋を追加する必要があります。  
  
```  
XmlDoc = new System.Xml.XmlDocument();  
XmlDoc.LoadXml("<RfcConfirmTransID xmlns='http://Microsoft.LobServices.Sap/2007/03/RfcApi/'><TransactionalRfcOperationIdentifier /></RfcConfirmTransID>");  
TIDRequest = XmlDoc;  
TIDRequest.TransactionalRfcOperationIdentifier = xpath(Response,"string(/*[local-name()='BAPI_SALESORDER_CREATEFROMDAT2Response']/*[local-name()='TransactionalRfcOperationIdentifier']/text())");  
```  
  
 上記のコード例を使用するのには、次が必要です。  
  
-   変数を作成した**XmlDoc**BizTalk プロジェクト、およびその型を System.Xml.XmlDocument に設定します。 変数の作成の詳細については、次を参照してください。[オーケストレーションで変数を使用して](../../core/using-variables-in-orchestrations.md)です。
  
-   昇格、 **TransactionalRfcOperationIdentifier** RfcConfirmTransID 操作のスキーマ内のプロパティです。 プロパティを昇格させる方法の詳細については、次を参照してください。[プロパティの昇格](../../core/promoting-properties.md)です。
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認してください。 示されている名前、*ポート*オーケストレーションで表示される、列が、ポートの名前を示します。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|FileIn|-設定**識別子**に*FileIn*<br />-設定**型**に*FileInPortType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|tRFC_Port|-設定**識別子**に*tRFC_Port*<br />-設定**型**に*tRFC_PortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|SavetRFCResponse|-設定**識別子**に*SavetRFCResponse*<br />-設定**型**に*SavetRFCResponsePortType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
|TID_Port|-設定**識別子**に*TID_Port*<br />-設定**型**に*TIDPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|SaveTIDResponse|-設定**識別子**に*SaveTIDResponse*<br />-設定**型**に*SaveTIDResponsePortType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表は、プロパティと、メッセージのアクション図形およびポートにリンクすることを指定するために設定するには、その値を指定します。 示されている名前、*図形*列が以前のオーケストレーションで表示される、メッセージの構築図形の名前を示します。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveXml|-設定**メッセージ**に*要求*<br />-設定**操作**に*FileIn.tRFC.Request*|  
|SendToLOB|-設定**メッセージ**に*要求*<br />-設定**操作**に*tRFC_Port.tRFC.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*tRFC_Port.tRFC.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*SavetRFCResponse.tRFC.Request*|  
|SendTIDMsg|-設定**メッセージ**に*TIDRequest*<br />-設定**操作**に*TID_Port.TID.Request*|  
|ReceiveTIDRsp|-設定**メッセージ**に*TIDResponse*<br />-設定**操作**に*TID_Port.TID.Response*|  
|SendTIDRsp|-設定**メッセージ**に*TIDResponse*<br />-設定**操作**に*SaveTIDResponse.TID.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 これで、BizTalk ソリューションをビルドしして、BizTalk Server に展開する必要があります。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 アプリケーションの構成の詳細については、次を参照してください。[アプリケーションを構成する方法](../../core/how-to-configure-an-application.md)です。
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。 BizTalk オーケストレーションは、SAP システムに送信する要求メッセージを消費します。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが SAP システムからの応答を含む応答メッセージをドロップする場所に場所を定義します。  
  
    -   WCF SAP が SAP システムにメッセージを送信ポート (1 つずつ tRFC 要求メッセージと RfcConfirmTransID メッセージ) を送信または物理 Wcf-custom を定義します。 送信ポートでアクションを指定することもあります。 ポートを作成する方法については、次を参照してください。 [SAP アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)です。
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または受信ポート (着信)、BizTalk Server 管理コンソールから、このバインド ファイルをインポートすることができます。 詳細については、次を参照してください。 [sap ポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)です。
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 SAP システムで tRFCs を呼び出すための BizTalk アプリケーションを開始する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)、または[アプリケーションを起動する方法](../../core/how-to-start-and-stop-a-biztalk-application.md)です。  
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   SAP システムにメッセージを送信する Wcf-custom または SAP WCF 送信ポートを実行しています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後は、オーケストレーションの要求メッセージを削除する必要があります。 参照してください[tRFC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)SAP システムで、tRFC の呼び出しの要求メッセージのスキーマについて知ることです。 たとえばを呼び出す、tRFC として BAPI_SALEASORDER_CREATEFROMDAT2 要求メッセージには。  
  
```  
<BAPI_SALESORDER_CREATEFROMDAT2 xmlns="http://Microsoft.LobServices.Sap/2007/03/Trfc/">  
  <ORDER_HEADER_IN>  
    <DOC_TYPE xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">TA</DOC_TYPE>  
    <SALES_ORG xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">1000</SALES_ORG>  
    <DISTR_CHAN xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">10</DISTR_CHAN>  
    <DIVISION xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">00</DIVISION>  
    <SALES_OFF xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">1000</SALES_OFF>  
    <REQ_DATE_H xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">2006-09-01T23:50:00</REQ_DATE_H>  
    <PURCH_DATE xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">2006-08-25T23:50:00</PURCH_DATE>  
    <PURCH_NO_C xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">Cust PO</PURCH_NO_C>  
    <CURRENCY xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">EUR</CURRENCY>  
  </ORDER_HEADER_IN>  
  <ORDER_ITEMS_IN>  
    <BAPISDITM xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <MATERIAL>P-109</MATERIAL>  
      <PLANT>1000</PLANT>  
      <TARGET_QU>ST</TARGET_QU>  
    </BAPISDITM>  
  </ORDER_ITEMS_IN>  
  <ORDER_PARTNERS>  
    <BAPIPARNR xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <PARTN_ROLE>AG</PARTN_ROLE>  
      <PARTN_NUMB>0000001390</PARTN_NUMB>  
    </BAPIPARNR>  
  </ORDER_PARTNERS>  
  <RETURN/>  
  <TransactionalRfcOperationIdentifier>def689b1-b514-4627-a861-d6d7f51c84e3</TransactionalRfcOperationIdentifier>  
</BAPI_SALESORDER_CREATEFROMDAT2>  
```  
  
 オーケストレーションは、メッセージを使用して、SAP システムに渡します、SAP システムから応答を受信します。 応答メッセージは、オーケストレーションの一部として指定されたその他のファイルの場所に保存されます。 SAP システムからの応答には、GUID が含まれています。 オーケストレーションはし、応答から別の要求メッセージを生成し、RfcConfirmTransID を実行する SAP システムに渡されます。 RfcConfirmTransID 操作の SAP システムからの応答を受信すると後、は、ファイルの場所にコピーされます。 要約すると、操作が正常に実行された後に。  
  
-   呼び出すには tRFC SAP からの応答メッセージは、ファイルの場所にコピーされます。 これには、SAP システムに送信された同じ GUID が含まれています。 TRFC、現状有姿 BAPI_SALESORDER_CREATEFROMDAT2 を呼び出して応答メッセージ:  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <BAPI_SALESORDER_CREATEFROMDAT2Response xmlns="http://Microsoft.LobServices.Sap/2007/03/Trfc/">  
      <TransactionalRfcOperationIdentifier>def689b1-b514-4627-a861-d6d7f51c84e3</TransactionalRfcOperationIdentifier>  
    </BAPI_SALESORDER_CREATEFROMDAT2Response>  
    ```  
  
-   RfcConfirmTransID の応答メッセージは、同じ場所にコピーされます。 これは、空の応答です。 RfcConfirmTransID の応答メッセージは次のとおりです。  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <RfcConfirmTransIDResponse xmlns="http://Microsoft.LobServices.Sap/2007/03/RfcApi/"></RfcConfirmTransIDResponse>  
    ```  
  
> [!NOTE]
>  使用することができます、 **ConvertGuidToTid()** GUID にマップされている SAP システムで TID を取得する SAP アダプターのアセンブリによって公開されているパブリック メソッド。 詳細については、次を参照してください。[特別な操作](../../adapters-and-accelerators/adapter-sap/special-operations.md)です。  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 例外については、BizTalk Server を使用して SAP システムで、tRFC の呼び出し中に発生する可能性が、次を参照してください。[例外とエラー処理、SAP アダプター](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)です。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。[を再利用の SAP アダプターのバインド](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)です。
  
## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)