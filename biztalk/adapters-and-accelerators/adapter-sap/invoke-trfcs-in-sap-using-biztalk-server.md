---
title: BizTalk Server を使用して SAP の Trfc を呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tRFCs, invoking using BizTalk Server
ms.assetid: 9489adca-cf2c-4e15-8573-445acd7ebf73
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baebf2a3f1723265612974f4728797bca7a070a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989755"
---
# <a name="invoke-trfcs-in-sap-using-biztalk-server"></a>BizTalk Server を使用して SAP の Trfc を呼び出す
トランザクション リモート関数呼び出し (Trfc) は、SAP システムの RFC の 1 つだけの時間実行を保証します。 いずれかの側に表示される、Rfc を呼び出すことができます、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] tRFC として。 RFC の呼び出しに似ていますが、tRFC を呼び出す (を参照してください[を使用して BizTalk Server での SAP の Rfc を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md))、次の点が異なります。  
  
- [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェスのさまざまなノードの下の Trfc (**TRFC**) の Rfc より (**RFC**)。  
  
- tRFC 操作によって tRFC の SAP トランザクション ID にマップされている GUID パラメーターを含める、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
- TRFC を呼び出すには、(コミット)、SAP システムの tRFC を確認する RfcConfirmTransID 操作を呼び出す必要があります。 この操作はのすぐ下に表示される、 **TRFC**内のノード[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。  
  
  方法の詳細については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]の tRFC を呼び出すサポートを参照してください[SAP の Trfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)します。 SOAP の構造の詳細については、tRFC を呼び出すためメッセージを参照してください[tRFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)します。  
  
## <a name="how-to-invoke-a-trfc-in-an-sap-system-using-biztalk-server"></a>SAP システムを使用して BizTalk Server での tRFC を呼び出す方法は?  
 使用して SAP システムでの操作を実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[SAP アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)します。 これらのタスクは SAP システムで、tRFC を呼び出すには。  
  
1. BizTalk プロジェクトを作成し、SAP システムで、呼び出し先 tRFC のスキーマを生成します。 スキーマを生成することも必要があります、 **RfcConfirmTransID** TID を SAP システムにコミットする操作。  
  
2. SAP システムからメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
3. SAP システムで、tRFC を呼び出すし、tRFC の呼び出しに対する応答で SAP システムで作成される TID をコミットするオーケストレーションを作成、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
4. ビルドし、BizTalk プロジェクトを配置します。  
  
5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
6. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックに基づくサンプル  
 サンプル tRFCClient、このトピックの「に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、[SAP アダプターのサンプルを](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)を参照してください。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 使用して、tRFC を呼び出す方法を示すために、このトピックで、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]のスキーマを生成します。  
  
- *BAPI_SALESORDER_CREATEFROMDAT2* tRFC します。  
  
- RfcConfirmTransID 操作です。 この操作を使用して、SAP システムで作成される TID をコミットする必要があります。 SAP システムがこの呼び出しを受け取ると、システムから TID を削除します。  
  
  参照してください[参照、検索、および tRFC sap 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-trfc-operations-in-sap.md)スキーマを生成する方法の詳細について。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションからメッセージを生成したスキーマをリンクする必要があります。  
  
 このトピックでは、4 つのメッセージを作成する必要があります: RfcConfirmTransID 操作を呼び出す、tRFC を呼び出す別の要求-応答メッセージに設定要求-応答メッセージを設定します。  
  
 メッセージを作成し、スキーマにリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションの種類を BizTalk プロジェクトを開くまだ開いていない場合。 をクリックして**ビュー**、 をポイント**その他の Windows**、 をクリック**オーケストレーション**します。  
  
2.  **オーケストレーション**、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。  
  
3.  右クリックし、新規メッセージを作成および選択**プロパティ ウィンドウ**します。  
  
4.  **プロパティ**ウィンドウ **[message_1]** 次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**要求**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**メッセージの種類を選択します。 たとえば、 *tRFC_Client.SAPBindingSchema1.BAPI_SALESORDER_CREATEFROMDAT2*ここで、 *tRFC_Client* BizTalk プロジェクトの名前を指定します。 *SAPBindingSchema1*に対して生成されたスキーマは、 *BAPI_SALESORDER_CREATEFROMDAT2*します。|  
  
5.  次の 3 つ以上のメッセージを作成する前の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  
  
    |識別子を設定するには|メッセージの種類を設定|  
    |-----------------------|-------------------------|  
    |応答|*tRFC_Client.SAPBindingSchema1.BAPI_SALESORDER_CREATEFROMDAT2Response*|  
    |TIDRequest|*tRFC_Client.SAPBindingSchema3.RfcConfirmTransID*|  
    |TIDResponse|*tRFC_Client.SAPBindingSchema3.RfcConfirmTransIDResponse*|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SAP システムで Trfc を呼び出すためです。 要求メッセージをこのオーケストレーションで削除する、定義されている受信場所。 オーケストレーションでは、このメッセージを使用し、SAP システムに渡します。 応答は、SAP から受信したが、別の場所に保存されます。 応答メッセージには、GUID が含まれています。 オーケストレーションが含まれています、**メッセージの構築**を応答から GUID を抽出しのスキーマに準拠したメッセージの構築図形、 **RfcConfirmTransID**操作。 呼び出すメッセージ、 **RfcConfirmTransID**操作が送信される SAP システムの GUID を持つパラメーター _ として後に、SAP システムで Trfc を呼び出すための一般的なオーケストレーション、 **RfcConfirmTransID**操作が含まれます。  
  
- SAP システムにメッセージを送信し、応答を受信する図形を送受信します。  
  
- メッセージの構築図形内でメッセージの割り当て図形のメッセージを構築して、 **RfcConfirmTransID**操作。  
  
- 一方向の受信ポートを tRFC を呼び出すために、SAP システムに送信する要求メッセージを受信します。  
  
- 双方向の送信ポート、tRFC を呼び出すし、応答の受信にメッセージを送信します。  
  
- 双方向の送信ポートを呼び出すメッセージを送信する、 **RfcConfirmTransID**操作応答を受信します。  
  
- 2 つの一方向の送信、フォルダーを SAP システムからの応答を送信するポート。  
  
  サンプル オーケストレーションには、次のようになります。  
  
  ![TRFC クライアント呼び出しを行うためのオーケストレーション](../../adapters-and-accelerators/adapter-sap/media/369d62dd-9ae4-4673-b346-03d2acfb453a.gif "369d62dd-9ae4-4673-b346-03d2acfb453a")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 各メッセージの構築図形の次のプロパティを指定します。 表示される名前、*図形*前のオーケストレーションに表示される、列は、メッセージの構築図形の名前。  
  
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
 TRFC の呼び出しの SAP システムからの応答には、GUID が含まれています。 TRFC の呼び出しをコミットするには、RfcConfirmTransID 操作に同じ GUID を渡す必要があります。 これを行うには、メッセージの構築図形を含める必要があり、メッセージの割り当てが図形内で、オーケストレーションします。 ここでは、メッセージの構築図形の目的は次のとおりです。  
  
- TRFC の呼び出しの SAP システムから受信した応答から GUID を抽出します。  
  
- RfcConfirmTransID 操作のメッセージ スキーマに準拠したメッセージを構築します。  
  
  設定する必要があります、メッセージの構築図形、**メッセージ構築**プロパティを**TIDRequest**します。  
  
  次のコードの抜粋は、メッセージの割り当て図形を追加する必要があります。  
  
```  
XmlDoc = new System.Xml.XmlDocument();  
XmlDoc.LoadXml("<RfcConfirmTransID xmlns='http://Microsoft.LobServices.Sap/2007/03/RfcApi/'><TransactionalRfcOperationIdentifier /></RfcConfirmTransID>");  
TIDRequest = XmlDoc;  
TIDRequest.TransactionalRfcOperationIdentifier = xpath(Response,"string(/*[local-name()='BAPI_SALESORDER_CREATEFROMDAT2Response']/*[local-name()='TransactionalRfcOperationIdentifier']/text())");  
```  
  
 上記のコード例を使用するには、が必要です。  
  
-   変数を作成した**XmlDoc**プロジェクトで、BizTalk、および、その型を System.Xml.XmlDocument に設定します。 変数の作成方法の詳細については、[オーケストレーションで変数を使用して](../../core/using-variables-in-orchestrations.md)を参照してください。
  
-   昇格、 **TransactionalRfcOperationIdentifier** RfcConfirmTransID 操作のスキーマ内のプロパティ。 プロパティを昇格させる方法についての詳細については、[プロパティの昇格](../../core/promoting-properties.md)を参照してください。
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認します。 表示される名前、*ポート*列は、ポートの名前、オーケストレーションに表示されます。  
  
|Port|[プロパティ]|  
|----------|----------------|  
|FileIn|-設定**識別子**に*FileIn*<br />-設定**型**に*FileInPortType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|tRFC_Port|-設定**識別子**に*tRFC_Port*<br />-設定**型**に*tRFC_PortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|SavetRFCResponse|-設定**識別子**に*SavetRFCResponse*<br />-設定**型**に*SavetRFCResponsePortType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
|TID_Port|-設定**識別子**に*TID_Port*<br />-設定**型**に*TIDPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|SaveTIDResponse|-設定**識別子**に*SaveTIDResponse*<br />-設定**型**に*SaveTIDResponsePortType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表には、プロパティとメッセージのアクション図形とポートにリンクすることを指定するために設定するには、その値を指定します。 表示される名前、*図形*前のオーケストレーションに表示される、列は、メッセージの構築図形の名前。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveXml|-設定**メッセージ**に*要求*<br />-設定**操作**に*FileIn.tRFC.Request*|  
|SendToLOB|-設定**メッセージ**に*要求*<br />-設定**操作**に*tRFC_Port.tRFC.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*tRFC_Port.tRFC.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*SavetRFCResponse.tRFC.Request*|  
|SendTIDMsg|-設定**メッセージ**に*TIDRequest*<br />-設定**操作**に*TID_Port.TID.Request*|  
|ReceiveTIDRsp|-設定**メッセージ**に*TIDResponse*<br />-設定**操作**に*TID_Port.TID.Response*|  
|SendTIDRsp|-設定**メッセージ**に*TIDResponse*<br />-設定**操作**に*SaveTIDResponse.TID.Request*|  
  
 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 BizTalk ソリューションを構築するようになりましたし、BizTalk Server にデプロイする必要があります。 詳細については、[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)を参照してください。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 アプリケーションを構成する方法の詳細については、[アプリケーションを構成する方法](../../core/how-to-configure-an-application.md)を参照してください。
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
  - ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションでは、SAP システムに送信する要求メッセージを使用します。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションでの SAP システムからの応答を含む応答メッセージをドロップする場所の場所を定義します。  
  
  - 物理 WCF カスタム定義または WCF SAP が SAP システムにメッセージを送信ポート (1 つずつ、tRFC の要求メッセージと RfcConfirmTransID メッセージ) を送信します。 送信ポートでアクションを指定することも必要があります。 ポートを作成する方法については、[SAP アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)を参照してください。
  
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または (着信) 用のポートを受信する BizTalk Server 管理コンソールから、このバインド ファイルをインポートできます。 詳細については、[sap ポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)を参照してください。
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 SAP システムで Trfc を呼び出すための BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを開始する手順については、[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)、または[アプリケーションを起動する方法](../../core/how-to-start-and-stop-a-biztalk-application.md)を参照してください。  
  
 この段階で、ことを確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   SAP システムにメッセージを送信する Wcf-custom または WCF-SAP 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後、オーケストレーションの要求メッセージを削除する必要があります。 参照してください[tRFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)SAP システムで、tRFC を呼び出すための要求メッセージのスキーマについて理解します。 たとえば、BAPI_SALEASORDER_CREATEFROMDAT2 として、tRFC を呼び出す要求メッセージには。  
  
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
  
 オーケストレーション、メッセージを使用するには、SAP システムに渡しますおよび SAP システムから応答を受信します。 応答メッセージは、オーケストレーションの一部として指定されたその他のファイルの場所に保存されます。 SAP システムからの応答には、GUID が含まれています。 オーケストレーションは、応答から別の要求メッセージが生成され、RfcConfirmTransID を実行する SAP システムに渡します。 RfcConfirmTransID 操作の SAP システムからの応答を受け取った後は、ファイルの場所にコピーされます。 まとめると、操作が正常に実行された後。  
  
-   SAP から、tRFC を呼び出すための応答メッセージは、ファイルの場所にコピーされます。 これには、SAP システムに送信されたのと同じ GUID が含まれています。 BAPI_SALESORDER_CREATEFROMDAT2 を呼び出し、tRFC は応答メッセージ:  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <BAPI_SALESORDER_CREATEFROMDAT2Response xmlns="http://Microsoft.LobServices.Sap/2007/03/Trfc/">  
      <TransactionalRfcOperationIdentifier>def689b1-b514-4627-a861-d6d7f51c84e3</TransactionalRfcOperationIdentifier>  
    </BAPI_SALESORDER_CREATEFROMDAT2Response>  
    ```  
  
-   RfcConfirmTransID の応答メッセージは、同じ場所にコピーされます。 これは、空の応答です。 RfcConfirmTransID の応答メッセージです。  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <RfcConfirmTransIDResponse xmlns="http://Microsoft.LobServices.Sap/2007/03/RfcApi/"></RfcConfirmTransIDResponse>  
    ```  
  
> [!NOTE]
>  使用することができます、 **ConvertGuidToTid()** GUID にマップされている SAP システムで TID を取得する SAP アダプターのアセンブリによって公開されるパブリック メソッド。 詳細については、[特別な操作](../../adapters-and-accelerators/adapter-sap/special-operations.md)を参照してください。  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 BizTalk Server を使用して SAP システムで、tRFC の呼び出し中に発生する可能性が、例外については、[例外とエラーは、SAP アダプターを使用した処理](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)を参照してください。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した後は、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありませんように、ファイルから構成設定をインポートできます。 バインド ファイルの詳細については、[再利用の SAP アダプター バインド](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)を参照してください。
  
## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)