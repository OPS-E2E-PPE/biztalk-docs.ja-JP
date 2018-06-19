---
title: BizTalk Server を使用して sap Idoc を送信 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDOCs, sample for sending
- IDOCs, sending to SAP using BizTalk Server
- IDOCs, business scenarios for sending
ms.assetid: 92042623-ffbf-472f-9515-e9a77eb320fb
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b2e493f5b99c9b100a9683ffb90584a9cfd92b3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967584"
---
# <a name="send-idocs-to-sap-using-biztalk-server"></a>BizTalk Server を使用して sap Idoc を送信します。
SAP へのすべての IDOC 呼び出しは、tRFC の呼び出し、アダプターは tRFC クライアントとして機能して、IDOC を送信する SAP の RFC を呼び出してとして内部的に扱われます。 このセクションの内容についての情報を使用して sap Idoc を送信する、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Idoc を送信する 2 つの異なる操作を表示します。  
  
-   **送信**操作を厳密に型指定されたスキーマが Idoc を送信するアダプターのクライアントを有効にします。  
  
-   **SendIdoc**操作により、弱い型指定のスキーマが Idoc を送信するクライアントはアダプターです。 これを使用して、アダプターのクライアントは、SAP システムにフラット ファイル Idoc を送信できます。 全体のフラット ファイル IDOC を SendIdoc XML メッセージ内のノードの値となります。  
  
 方法の詳細については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]SAP システムへの Idoc の送信をサポートを参照してください[sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)です。 SOAP の構造の詳細については、IDOC を送信するメッセージを参照してください[IDOC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)です。  
  
## <a name="biztalk-scenarios-for-sending-idocs-with-the-sap-adapter"></a>SAP アダプターでの Idoc を送信するための BizTalk シナリオ  
 次の表は、Idoc を SAP システムに送信するため、BizTalk、主要なシナリオを示します。  
  
|BizTalk への入力|BizTalk 処理|出力アダプターを|  
|----------------------|------------------------|-----------------------|  
|フラット ファイル IDOC|**メタデータ デザイン時**<br /><br /> 1.GenerateFlatFileCompatibleIdocSchema binding プロパティを設定する**True**です。<br />2.スキーマを生成、**送信**特定 IDOC を使用して、操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。<br /><br /> **オーケストレーションのデザイン時**<br /><br /> 1.フラット ファイル IDOC を受信します。<br />2.フラット ファイル逆アセンブラーを使用して、今生成されたスキーマを使用して XML IDOC フラット ファイル IDOC に変換します。<br />3.アクション**送信**操作します。|メッセージを送信します。|  
|フラット ファイル IDOC|**メタデータ デザイン時**<br /><br /> 1.GenerateFlatFileCompatibleIdocSchema binding プロパティを設定する**True**です。<br />2.スキーマを生成、 **SendIdoc** 、IDOC を使用してノードから操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。<br /><br /> **オーケストレーションのデザイン時**<br /><br /> 1.フラット ファイル IDOC を受信します。<br />2.フラット ファイル逆アセンブラーを使用して、フラット ファイル IDOC を XML に変換する (この場合、XML メッセージに含まれる、 \<idocData\>フラット ファイル Idoc メッセージ全体を含むノードです) 今生成されたスキーマを使用します。<br />3.アクション**SendIdoc**操作します。|SendIdoc メッセージ|  
|XML の IDOC|**メタデータ デザイン時**<br /><br /> スキーマを生成、**送信**特定 IDOC を使用して、操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。<br /><br /> **オーケストレーションのデザイン時**<br /><br /> 1.XML の IDOC を受信します。<br />2.アクション**送信**操作します。|メッセージを送信します。|  
|XML メッセージのフラット ファイル IDOC|**メタデータ デザイン時**<br /><br /> スキーマを生成、 **SendIdoc** 、IDOC を使用してノードから操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。<br /><br /> **オーケストレーションのデザイン時**<br /><br /> 1.XML メッセージを受信します。<br />2.アクション**SendIdoc**操作します。|SendIdoc メッセージ|  
  
## <a name="how-to-send-an-idoc-to-an-sap-system"></a>IDOC を SAP システムに送信する方法  
 SAP システムを使用して、操作を実行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [SAP アプリケーションを作成するビルド ブロック](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)です。 IDOC を SAP システムに送信するには、これらのタスクです。  
  
1.  BizTalk プロジェクトを作成し、IDOC が SAP システムで、呼び出し先のスキーマを生成します。 スキーマの生成中を確認してください、必要なバインドのプロパティを設定する前の表に一覧表示します。 バインドのプロパティを設定する方法の手順については、次を参照してください。 [SAP アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)です。  
  
2.  SAP システムからメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  IDOC を SAP システムに送信するためのオーケストレーションを作成します。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックの内容に基づくサンプル  
 サンプルは、IDOCSend、このトピックの内容に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。 [SAP アダプターのサンプル](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)です。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックは、SAP システムへのスキーマを生成することによって、IDOC を送信する方法を示します、*送信*\IDOC\ORDERS\ORDERS05\ORDERS05 の下で操作します。V3(620) IDOC です。 参照してください[SAP IDOC 操作のメタデータを参照、検索、および get](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-idoc-operations-in-sap.md)特定 IDOC のスキーマを生成する方法についての詳細。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションの種類からのメッセージに最初の手順で生成したスキーマをリンクする必要があります。  
  
 このトピックでは、2 つのメッセージを作成する必要があります: SAP システムと他の応答を受信する IDOC を送信する 1 つです。  
  
 メッセージを作成し、スキーマにそれらをリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションの種類、BizTalk プロジェクトを開くまだ開いていない場合。 をクリックして**ビュー**、 をポイント**その他のウィンドウ**、 をクリック**オーケストレーション**です。  
  
2.  **オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。  
  
3.  右クリックし、新規メッセージを作成および選択**プロパティ ウィンドウ**します。  
  
4.  **プロパティ**ウィンドウ**Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**IDOCSend**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*IDOCSend.SAPBindingSchema3*ここで、 *IDOCSend* BizTalk プロジェクトの名前を指定します。 *SAPBindingSchema3*送信操作に対して生成されるスキーマです。|  
  
5.  新しいメッセージを作成する前の手順を繰り返します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**IDOCResponse**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*IDOCSend.SAPBindingSchema4*です。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Idoc を SAP システムに送信するためです。 このオーケストレーションで削除するフラット ファイルで定義されている IDOC の受信場所。 このファイルは、フラット ファイル逆アセンブラーを使用して XML 要求メッセージに変換されます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]このメッセージを消費し、SAP システムに渡します。 GUID を持つ応答は、SAP から受信したされ、別の場所に保存されます。 送信を含めるし、受信図形の Idoc を SAP システムに送信し、応答を受信する必要があります。 フラット ファイル逆アセンブラー、フラット ファイルを XML ファイルに変換を含める必要もあります。 送信する一般的なオーケストレーションおよび IDOC を SAP システムが含まれます。  
  
-   SAP システムにメッセージを送信し、応答を受信する図形を送受信します。  
  
-   一方向の受信ポートを SAP システムに送信するフラット ファイル Idoc を受信します。  
  
-   フラット ファイル逆アセンブラー、フラット ファイル IDOC を XML ファイルに変換します。  
  
-   双方向の送信、IDOC を SAP システムに送信し、応答を受信するポート。  
  
-   SAP システムからフォルダーに、応答を送信する一方向の送信ポートです。  
  
 サンプル オーケストレーションは、次のようになります。  
  
 ![Idoc を SAP に送信するオーケストレーション](../../adapters-and-accelerators/adapter-sap/media/db1490c8-da52-4af3-8a4f-d93bd815025d.gif "db1490c8-da52-4af3-8a4f-d93bd815025d")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。 示されている名前、*図形*列が上記のオーケストレーションで表示される、メッセージの構築図形の名前を示します。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveFile|Receive|-設定**名前**に*ReceiveFile*<br />-設定**アクティブ**に*は True。*|  
|SendToLOB|Send|-設定**名前**に*SendToLOB*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認してください。 示されている名前、*ポート*オーケストレーションで表示される、列が、ポートの名前を示します。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|FileIn|-設定**識別子**に*FileIn*<br />-設定**型**に*FileInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|SaveResponse|-設定**識別子**に*SaveResponse*<br />-設定**型**に*SaveResponseType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
### <a name="adding-a-flat-file-disassembler"></a>フラット ファイル逆アセンブラーを追加します。  
 フラット ファイル IDOC を XML 形式に変換するオーケストレーションには、フラット ファイル逆アセンブラーを追加する必要があります。  
  
##### <a name="to-add-a-flat-file-disassembler"></a>フラット ファイル逆アセンブラーを追加するには  
  
1.  BizTalk プロジェクトを右クリックし、**追加**を選択して**新しい項目の**します。  
  
2.  ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |カテゴリ|パイプライン ファイル|  
    |Visual Studio にインストールされたテンプレート|[受信パイプライン]|  
    |名前|IDOCReceive|  
  
3.  パイプライン デザイナーが開きます。 **BizTalk パイプライン コンポーネント**ツールボックス、ドラッグ、**フラット ファイル逆アセンブラー**にパイプライン コンポーネント、**逆アセンブル**受信パイプラインのステージ。  
  
4.  **パイプライン コンポーネントのプロパティ**ビューで、値を指定、**ドキュメント スキーマ**プロパティです。 ドロップダウン リストから IDOC の送信操作に対応するスキーマを選択していることを確認します。  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表は、プロパティと、メッセージのアクション図形およびポートにリンクすることを指定するために設定するには、その値を指定します。 示されている名前、*図形*列が上記のオーケストレーションで表示される、メッセージの構築図形の名前を示します。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveFile|-設定**メッセージ**に*IDOCSend*<br />-設定**操作**に*FileIn.SendIDOC.Request*|  
|SendToLob|-設定**メッセージ**に*IDOCSend*<br />-設定**操作**に*LOBPort.SendIDOC.Request*|  
|ReceiveResponse|-設定**メッセージ**に*IDOCResponse*<br />-設定**操作**に*LOBPort.SendIDOC.Response*|  
|SendResponse|-設定**メッセージ**に*IDOCResponse*<br />-設定**操作**に*SaveResponse.SendIDOC.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 アプリケーションの構成の詳細については、次を参照してください。[アプリケーションを構成する方法](../../core/how-to-configure-an-application.md)です。
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。 BizTalk オーケストレーションは、要求メッセージを消費し、SAP システムに送信します。  
  
        > [!IMPORTANT]
        >  このポートの XMLReceive パイプラインの選択を確認します***IDOCReceive***です。 BizTalk プロジェクトの一部としてこのパイプラインを作成したとします。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが SAP システムからの応答を含む応答メッセージをドロップする場所に場所を定義します。  
  
    -   SAP システムにメッセージを送信する物理 Wcf-custom または WCF SAP 送信ポートを定義します。 送信ポートでアクションを指定することもあります。 ポートを作成する方法については、次を参照してください。 [SAP アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)です。
  
        > [!NOTE]
        >  設定することも、 *AutoConfirmSentIdocs* Idoc が SAP システムに自動的にコミットするプロパティをバインドします。 これを行う場合は、Idoc をコミットする RfcConfirmTransID 操作を明示的に呼び出す必要はありません。 バインディング プロパティの詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。 RfcConfirmTransID 操作に関する詳細については、次を参照してください。 [SAP で tRFCs に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)です。  
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または受信ポート (着信)、BizTalk 管理コンソールからこのバインド ファイルをインポートすることができます。 詳細については、次を参照してください。 [sap ポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)です。
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 IDOC を SAP システムに送信するための BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)、または[アプリケーションを起動する方法](../../core/how-to-start-and-stop-a-biztalk-application.md)です。
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   SAP システムにメッセージを送信する Wcf-custom または SAP WCF 送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後は、オーケストレーションの要求メッセージを削除する必要があります。 この例ではドロップ フラット ファイル IDOC で定義されたファイルの受信場所。 要求メッセージを削除した後、次の操作が実行されます。  
  
-   オーケストレーションは、このフラット ファイル IDOC を取得し、以前に生成したスキーマに準拠している対象のスキーマの XML 要求メッセージに変換します。  
  
-   指定した要求メッセージに GUID が含まれている場合、アダプターはトランザクション ID (TID) を生成し、SAP システムに送信します。  
  
-   指定した要求メッセージに GUID が含まれていない場合、アダプターは GUID を生成し、その GUID を使用して、TID を生成します。 TID は SAP システムに送信されます。  
  
 いずれの場合は、SAP システムからの応答メッセージには、GUID が含まれています。 たとえば、ORDERS05 IDOC に対する送信操作の応答メッセージには。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<SendResponse xmlns="http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Send">  
  <guid>a5afe162-d5cc-47b0-bf6f-3b0bfe06a97e</guid>  
</SendResponse>  
```  
  
 呼び出す必要があります、GUID が表示されたら、 **RfConfirmTransID** TID をコミットする操作。 詳細については、 **RfcConfirmTransID**操作を参照してください[SAP で tRFCs に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)です。 作成することも、新しいオーケストレーションをこの操作を呼び出すか、既存のオーケストレーションを変更します。 新しいオーケストレーションを作成する場合は、SAP システムで他の任意のオーケストレーションに似ていますがあります。 既存のオーケストレーションを更新する場合は、「[で BizTalk Server を使用して SAP tRFCs を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)です。 オーケストレーション、トピックの説明に従って、tRFC の呼び出しを呼び出す方法を示します、 **RfcConfirmTransID**同じオーケストレーションから操作します。  
  
> [!NOTE]
>  設定した場合に、RfcConfirmTransID 操作を呼び出す必要がありますいない、 *AutoConfirmSentIdocs*にプロパティのバインド**True**です。  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 例外については、BizTalk Server を使用して SAP システムへの IDOC の送信中に発生する可能性が、次を参照してください。[例外とエラー処理、SAP アダプター](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)です。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。[を再利用の SAP アダプターのバインド](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)です。
  
## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)