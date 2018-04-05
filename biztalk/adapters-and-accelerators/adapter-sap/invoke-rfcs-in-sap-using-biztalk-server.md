---
title: BizTalk Server を使用して SAP Rfc を呼び出す |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RFCs, invoking using BizTalk Server
ms.assetid: cc859ca2-aa9a-48fd-a941-ae28bee96f06
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3db5180d8b4183a2a48c726fd5e73b3347f82dc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-rfcs-in-sap-using-biztalk-server"></a>BizTalk Server を使用して SAP Rfc を呼び出す
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアントから呼び出すことができる操作として、SAP システムによって公開されている Rfc を表示します。 このセクションの内容を使用して SAP システムでの RFC を呼び出すための手順を説明する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 方法の詳細については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]SAP システムで RFC を呼び出すサポートを参照してください[SAP Rfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)です。 RFC を呼び出すための SOAP メッセージの構造に関する詳細については、次を参照してください。 [RFC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)です。  
  
## <a name="how-to-invoke-an-rfc-in-an-sap-system"></a>SAP システムで RFC を呼び出す方法ですか。  
 SAP システムを使用して、操作を実行、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [SAP アプリケーションを作成するビルド ブロック](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)です。 SAP システムでは、RFC を呼び出し、これらのタスクです。  
  
1.  BizTalk プロジェクトを作成し、SAP システムで、呼び出し先の RFC のスキーマを生成します。  
  
2.  SAP システムからメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  SAP システムで RFC を呼び出すオーケストレーションを作成します。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックでは、SAP システムで RFC を起動する方法を示すおスキーマを生成*RFC_CUSTOMER_GET*です。 参照してください[参照、検索、および SAP RFC 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)スキーマを生成する方法についての詳細。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションの種類からのメッセージを生成したスキーマをリンクする必要があります。  
  
 このトピックでは、2 つのメッセージを作成する必要があります: SAP システムと他の応答を受信する要求を送信する 1 つです。  
  
 メッセージを作成し、スキーマにそれらをリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションの種類、BizTalk プロジェクトを開くまだ開いていない場合。 をクリックして**ビュー**、 をポイント**その他のウィンドウ**、 をクリック**オーケストレーション**です。  
  
2.  **オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。  
  
3.  右クリックし、新規メッセージを作成および選択**プロパティ ウィンドウ**します。  
  
4.  **プロパティ**のウィンドウ**Message_1**次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**要求**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GET*ここで、 *InvokeRFC* BizTalk プロジェクトの名前を指定します。  *SAPBindingSchema*に対して生成されたスキーマは、 *RFC_CUSTOMER_GET*です。|  
  
5.  新しいメッセージを作成する前の手順を繰り返します。 **プロパティ**新しいメッセージ用のウィンドウは、以下を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**応答**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GETResponse*です。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SAP システムでの Rfc を呼び出すためです。 このオーケストレーションでの要求メッセージを削除する受信場所が、定義されています。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]メッセージを使用して、SAP システムに渡します。 SAP システムからの応答は、別の場所に保存されます。 SAP システムでの呼び出し元の Rfc の一般的なオーケストレーションにが含まれます。  
  
-   SAP システムにメッセージを送信し、応答を受信する図形を送受信します。  
  
-   一方向の受信ポートを SAP システムに送信する要求メッセージを受信します。  
  
-   双方向の送信ポートを SAP システムに要求メッセージを送信し、応答を受信します。  
  
-   SAP システムからフォルダーに、応答を送信する一方向の送信ポートです。  
  
 サンプル オーケストレーションには、次のようになります。  
  
 ![接続されているポートとオーケストレーション](../../adapters-and-accelerators/adapter-sap/media/c228e79f-02e8-4de3-b447-8703caa28d3b.gif "c228e79f-02e8-4de3-b447-8703caa28d3b")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。 示されている名前、*図形*列が上記のオーケストレーションで表示される、メッセージの構築図形の名前を示します。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|Receive_Request|Receive|-設定**名前**に*Receive_Request*<br />-設定**アクティブ**に*は True。*|  
|Send_LOB|Send|-設定**名前**に*Send_LOB*|  
|Receive_LOB|Receive|-設定**名前**に*Receive_LOB*<br />-設定**アクティブ**に*False*|  
|Send_Response|Send|-設定**名前**に*Send_Response*|  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとには、次のプロパティを指定します。 示されている名前、*ポート*オーケストレーションで表示される、列が、ポートの名前を示します。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|ReceiveMsgPort|-設定**識別子**に*ReceiveMsgPort*<br />-設定**型**に*ReceiveMsgPortType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|SendToLOBPort|-設定**識別子**に*SendToLOBPort*<br />-設定**型**に*SendToLOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|SendMsgPort|-設定**識別子**に*SendMsgPort*<br />-設定**型**に*SendMsgPortType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表は、プロパティと、メッセージのアクション図形およびポートにリンクすることを指定するために設定するには、その値を指定します。 示されている名前、*図形*列が上記のオーケストレーションで表示される、メッセージの構築図形の名前を示します。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|Receive_Request|-設定**メッセージ**に*要求*<br />-設定**操作**に*ReceiveMsgPort.Operation_1.Request*|  
|Send_LOB|-設定**メッセージ**に*要求*<br />-設定**操作**に*SendToLOBPort.Operation_1.Request*|  
|Receive_LOB|-設定**メッセージ**に*応答*<br />-設定**操作**に*SendToLOBPort.Operation_1.Response*|  
|Send_Response|-設定**メッセージ**に*応答*<br />-設定**操作**に*SendMsgPort.Operation_1.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 アプリケーションの構成の詳細については、次を参照してください。[アプリケーションを構成する方法](../../core/how-to-configure-an-application.md)です。
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。 BizTalk オーケストレーションは、要求メッセージを消費し、SAP システムに送信します。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが SAP システムからの応答を含む応答メッセージをドロップする場所に場所を定義します。  
  
    -   SAP システムにメッセージを送信する物理 Wcf-custom または WCF SAP 送信ポートを定義します。 送信ポートでアクションを指定することもあります。 ポートを作成する方法については、次を参照してください。 [SAP アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)です。
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または受信ポート (着信)、BizTalk Server 管理コンソールから、このバインド ファイルをインポートすることができます。 詳細については、次を参照してください。 [sap ポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)です。
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 呼び出す RFC に SAP システムで BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)または[アプリケーションを起動する方法](../../core/how-to-start-and-stop-a-biztalk-application.md)です。
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   SAP システムにメッセージを送信する Wcf-custom または SAP WCF 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後に、定義済みの場所で、オーケストレーションの要求メッセージを削除する必要があります。 参照してください[RFC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)を呼び出す RFC に SAP システムで要求メッセージのスキーマについて知ることです。 たとえば、RFC_CUSTOMER_GET を起動する要求メッセージには。  
  
```  
<RFC_CUSTOMER_GET xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <KUNNR>0000001390</KUNNR>  
  <NAME1>*</NAME1>  
  <CUSTOMER_T/>  
</RFC_CUSTOMER_GET>  
```  
  
 オーケストレーションはメッセージを処理して、SAP システムに送信します。 SAP システムからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、上記の要求メッセージを SAP システムからの応答には。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<RFC_CUSTOMER_GETResponse xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <CUSTOMER_T>  
    <RFCCUST xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <KUNNR>0000001390</KUNNR>   
      <ANRED>Firma</ANRED>   
      <NAME1>Contoso, Ltd.</NAME1>   
      <PFACH />   
      <STRAS>4567 Main Street</STRAS>   
      <PSTLZ>98052</PSTLZ>   
      <ORT01>USA</ORT01>   
      <TELF1>555-0101</TELF1>   
      <TELFX>555-0102</TELFX>   
    </RFCCUST>  
  </CUSTOMER_T>  
</RFC_CUSTOMER_GETResponse>  
```  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 例外については、BizTalk Server を使用して SAP システムでの RFC の呼び出し中に発生する可能性が、次を参照してください。[例外とエラー処理、SAP アダプター](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)です。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。[を再利用の SAP アダプターのバインド](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)です。  
  
## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)