---
title: BizTalk Server を使用して SAP で Rfc を呼び出す |Microsoft Docs
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
ms.openlocfilehash: 381cbebae5e87e459b8283c90b4bbc0de9afb1cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988787"
---
# <a name="invoke-rfcs-in-sap-using-biztalk-server"></a>BizTalk Server を使用して SAP で Rfc を呼び出す
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアントによって呼び出すことができる操作として、SAP システムによって公開されている Rfc 明らかになります。 このセクションを使用して SAP システムでの RFC を呼び出すための説明、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 方法の詳細については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]RFC を呼び出すことは、SAP システムにサポートを参照してください[SAP で Rfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)します。 RFC を呼び出すための SOAP メッセージの構造の詳細については、[RFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)を参照してください。  
  
## <a name="how-to-invoke-an-rfc-in-an-sap-system"></a>SAP システムでの RFC を呼び出す方法でしょうか。  
 使用して SAP システムに対する演算を実行、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[SAP アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)します。 これらのタスクは、SAP システムの RFC を呼び出すには。  
  
1. BizTalk プロジェクトを作成し、SAP システムが呼び出す RFC のスキーマを生成します。  
  
2. SAP システムからメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
3. SAP システムでの RFC を呼び出すオーケストレーションを作成します。  
  
4. ビルドし、BizTalk プロジェクトを配置します。  
  
5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
6. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックでは、SAP システムでの RFC を呼び出す方法を示すためにスキーマを生成*RFC_CUSTOMER_GET*します。 参照してください[参照、検索、および SAP の RFC 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)スキーマを生成する方法の詳細について。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションからメッセージを生成したスキーマをリンクする必要があります。  
  
 このトピックでは、2 つのメッセージを作成する必要があります: 1 つに、SAP システムと他の応答を受信する要求を送信します。  
  
 メッセージを作成し、スキーマにリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションの種類を BizTalk プロジェクトを開くまだ開いていない場合。 をクリックして**ビュー**、 をポイント**その他の Windows**、 をクリック**オーケストレーション**します。  
  
2.  **オーケストレーション**、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。  
  
3.  右クリックし、新規メッセージを作成および選択**プロパティ ウィンドウ**します。  
  
4.  **プロパティ**ウィンドウ **[message_1]** 次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**要求**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選択と*InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GET*ここで、 *InvokeRFC* BizTalk プロジェクトの名前を指定します。  *SAPBindingSchema*に対して生成されたスキーマは、 *RFC_CUSTOMER_GET*します。|  
  
5.  新しいメッセージを作成する前の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**応答**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選択および*InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GETResponse*します。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SAP システムでの Rfc を呼び出すためです。 このオーケストレーションでの要求メッセージを削除する、定義されている受信場所。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]メッセージを使用して、SAP システムに渡します。 SAP システムからの応答は、別の場所に保存されます。 SAP システムでの呼び出し元の Rfc の一般的なオーケストレーションが含まれます。  
  
- SAP システムにメッセージを送信し、応答を受信する図形を送受信します。  
  
- SAP システムに送信する要求メッセージを受信するポートは一方向の受信します。  
  
- SAP システムに要求メッセージを送信し、応答を受信するポートを双方向に送信します。  
  
- SAP システムからフォルダーに、応答を送信する一方向の送信ポート。  
  
  サンプル オーケストレーションには、次のようになります。  
  
  ![オーケストレーション ポートが接続された](../../adapters-and-accelerators/adapter-sap/media/c228e79f-02e8-4de3-b447-8703caa28d3b.gif "c228e79f-02e8-4de3-b447-8703caa28d3b")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 表示される名前、*図形*前のオーケストレーションに表示される、列は、メッセージの構築図形の名前。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|Receive_Request|Receive|-設定**名前**に*Receive_Request*<br />-設定**アクティブ**に*は True。*|  
|Send_LOB|Send|-設定**名前**に*Send_LOB*|  
|Receive_LOB|Receive|-設定**名前**に*Receive_LOB*<br />-設定**アクティブ**に*False*|  
|Send_Response|Send|-設定**名前**に*Send_Response*|  
  
### <a name="adding-ports"></a>ポートの追加  
 ごとの論理ポートには、次のプロパティを指定します。 表示される名前、*ポート*列は、ポートの名前、オーケストレーションに表示されます。  
  
|Port|[プロパティ]|  
|----------|----------------|  
|ReceiveMsgPort|-設定**識別子**に*ReceiveMsgPort*<br />-設定**型**に*ReceiveMsgPortType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|SendToLOBPort|-設定**識別子**に*SendToLOBPort*<br />-設定**型**に*SendToLOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|SendMsgPort|-設定**識別子**に*SendMsgPort*<br />-設定**型**に*SendMsgPortType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表には、プロパティとメッセージのアクション図形とポートにリンクすることを指定するために設定するには、その値を指定します。 表示される名前、*図形*前のオーケストレーションに表示される、列は、メッセージの構築図形の名前。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|Receive_Request|-設定**メッセージ**に*要求*<br />-設定**操作**に*ReceiveMsgPort.Operation_1.Request*|  
|Send_LOB|-設定**メッセージ**に*要求*<br />-設定**操作**に*SendToLOBPort.Operation_1.Request*|  
|Receive_LOB|-設定**メッセージ**に*応答*<br />-設定**操作**に*SendToLOBPort.Operation_1.Response*|  
|Send_Response|-設定**メッセージ**に*応答*<br />-設定**操作**に*SendMsgPort.Operation_1.Request*|  
  
 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)を参照してください。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 アプリケーションを構成する方法の詳細については、[アプリケーションを構成する方法](../../core/how-to-configure-an-application.md)を参照してください。
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
  - ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用し、SAP システムに送信します。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションでの SAP システムからの応答を含む応答メッセージをドロップする場所の場所を定義します。  
  
  - SAP システムにメッセージを送信する物理 Wcf-custom または WCF-SAP 送信ポートを定義します。 送信ポートでアクションを指定することも必要があります。 ポートを作成する方法については、[SAP アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)を参照してください。
  
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または (着信) 用のポートを受信する BizTalk Server 管理コンソールから、このバインド ファイルをインポートできます。 詳細については、[sap ポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)を参照してください。
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 SAP システムでの RFC を呼び出すための BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを開始する手順については、[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)または[アプリケーションを起動する方法](../../core/how-to-start-and-stop-a-biztalk-application.md)を参照してください。
  
 この段階で、ことを確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   SAP システムにメッセージを送信する Wcf-custom または WCF SAP の送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後に、定義済みの場所で要求メッセージをオーケストレーションを削除する必要があります。 参照してください[RFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)SAP システムでの RFC を呼び出すための要求メッセージのスキーマについて理解します。 たとえば、RFC_CUSTOMER_GET を起動する要求メッセージには。  
  
```  
<RFC_CUSTOMER_GET xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <KUNNR>0000001390</KUNNR>  
  <NAME1>*</NAME1>  
  <CUSTOMER_T/>  
</RFC_CUSTOMER_GET>  
```  
  
 オーケストレーションはメッセージを使用し、SAP システムに送信します。 SAP システムからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、上記の要求メッセージの SAP システムからの応答には。  
  
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
 BizTalk Server を使用して SAP システムでの RFC の呼び出し中に発生する可能性が、例外については、[例外とエラーは、SAP アダプターを使用した処理](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)を参照してください。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した後は、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありませんように、ファイルから構成設定をインポートできます。 バインド ファイルの詳細については、[再利用の SAP アダプター バインド](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)を参照してください。  
  
## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)