---
title: BizTalk Server を使用して sap の Idoc の送信 |Microsoft Docs
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
ms.openlocfilehash: 1ca8464af7002fe7863246dc440a4da27ee23e1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970323"
---
# <a name="send-idocs-to-sap-using-biztalk-server"></a>BizTalk Server を使用して sap の Idoc を送信します。
Sap IDOC のすべての呼び出しは、内部的に tRFC の呼び出し、アダプターが tRFC クライアントとして機能し、IDOC を送信する SAP の RFC を呼び出すとして扱われます。 このセクションを使用して SAP の Idoc を送信することで情報を提供する、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェスの Idoc を送信する 2 つの異なる操作。  

- **送信**操作には、厳密に型指定されたスキーマが Idoc を送信するアダプターのクライアントが使用できます。  

- **SendIdoc**操作には、厳密に型指定のスキーマが Idoc を送信するアダプターのクライアントが使用できます。 これを使用して、アダプターのクライアントは、SAP システムをフラット ファイル Idoc を送信できます。 全体のフラット ファイル IDOC を SendIdoc XML メッセージ内のノードの値となります。  

  方法の詳細については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]Idoc を SAP システムに送信をサポートを参照してください[sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)します。 IDOC を送信するためのメッセージの詳細については、SOAP の構造を参照してください。 [IDOC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)します。  

## <a name="biztalk-scenarios-for-sending-idocs-with-the-sap-adapter"></a>SAP アダプターを使用した Idoc を送信するための BizTalk シナリオ  
 次の表は、Idoc を SAP システムに送信するため、BizTalk の主なシナリオを示します。  


|       BizTalk への入力        |                                                                                                                                                                                                                                                                                                                 BizTalk 処理                                                                                                                                                                                                                                                                                                                  | アダプターへの出力 |
|-------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|
|        フラット ファイル IDOC         |                                                         **メタデータ デザイン時**<br /><br /> 1.GenerateFlatFileCompatibleIdocSchema バインディング プロパティを設定する**True**します。<br />2.スキーマを生成、**送信**操作を使用して特定 IDOC の[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。<br /><br /> **オーケストレーションのデザイン時**<br /><br /> 1.フラット ファイル IDOC を受信します。<br />2.フラット ファイル IDOC を生成したスキーマを使用して XML IDOC に変換するのにには、フラット ファイル逆アセンブラーを使用します。<br />3.アクションに設定**送信**操作。                                                         |   メッセージを送信します。    |
|        フラット ファイル IDOC         | **メタデータ デザイン時**<br /><br /> 1.GenerateFlatFileCompatibleIdocSchema バインディング プロパティを設定する**True**します。<br />2.スキーマを生成、 **SendIdoc**操作を使用して IDOC ノード[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。<br /><br /> **オーケストレーションのデザイン時**<br /><br /> 1.フラット ファイル IDOC を受信します。<br />2.フラット ファイル逆アセンブラーを使用して、フラット ファイル IDOC を XML に変換する (この場合は、XML メッセージに含まれる、 \<idocData\>フラット ファイル Idoc メッセージ全体を含むノード) 生成したスキーマを使用して。<br />3.アクションに設定**SendIdoc**操作。 | SendIdoc メッセージ  |
|           XML の IDOC            |                                                                                                                                                           **メタデータ デザイン時**<br /><br /> スキーマを生成、**送信**操作を使用して特定 IDOC の[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。<br /><br /> **オーケストレーションのデザイン時**<br /><br /> 1.XML の IDOC を受信します。<br />2.アクションに設定**送信**操作。                                                                                                                                                           |   メッセージを送信します。    |
| XML メッセージのフラット ファイル IDOC |                                                                                                                                                      **メタデータ デザイン時**<br /><br /> スキーマを生成、 **SendIdoc**操作を使用して IDOC ノード[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。<br /><br /> **オーケストレーションのデザイン時**<br /><br /> 1.XML メッセージが表示されます。<br />2.アクションに設定**SendIdoc**操作。                                                                                                                                                      | SendIdoc メッセージ  |

## <a name="how-to-send-an-idoc-to-an-sap-system"></a>IDOC を SAP システムに送信する方法  
 使用して SAP システムでの操作を実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[SAP アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)します。 IDOC を SAP システムに送信するには、これらのタスクは。  

1. BizTalk プロジェクトを作成し、SAP システムを起動する IDOC のスキーマを生成します。 スキーマの生成中にことを必要なバインドのプロパティを設定することを確認して、前の表に記載されています。 バインドのプロパティを設定する方法については、次を参照してください。 [SAP アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)します。  

2. SAP システムからメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。  

3. IDOC を SAP システムに送信するオーケストレーションを作成します。  

4. ビルドし、BizTalk プロジェクトを配置します。  

5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  

6. BizTalk アプリケーションを起動します。  

   このトピックでは、これらのタスクを実行する手順を説明します。  

## <a name="sample-based-on-this-topic"></a>このトピックに基づくサンプル  
 サンプル IDOCSend、このトピックの「に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、次を参照してください。 [SAP アダプターのサンプル](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)します。  

## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックでは、SAP システムへのスキーマを生成することで IDOC を送信する方法を示します、*送信*\IDOC\ORDERS\ORDERS05\ORDERS05 で操作します。V3(620) IDOC します。 参照してください[sap IDOC 操作のメタデータを参照、検索、および get](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-idoc-operations-in-sap.md)特定 IDOC のスキーマを生成する方法の詳細について。  

## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションからメッセージを最初の手順で生成したスキーマをリンクする必要があります。  

 このトピックでは、2 つのメッセージを作成する必要があります: 1 つの SAP システムとその応答を受信する他に IDOC を送信します。  

 メッセージを作成し、スキーマにリンクするには、次の手順に従います。  

#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  

1.  オーケストレーションの種類を BizTalk プロジェクトを開くまだ開いていない場合。 をクリックして**ビュー**、 をポイント**その他の Windows**、 をクリック**オーケストレーション**します。  

2.  **オーケストレーション**、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。  

3.  右クリックし、新規メッセージを作成および選択**プロパティ ウィンドウ**します。  

4.  **プロパティ**ウィンドウ **[message_1]** 次の操作を行います。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**IDOCSend**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選択と*IDOCSend.SAPBindingSchema3*ここで、 *IDOCSend* BizTalk プロジェクトの名前を指定します。 *SAPBindingSchema3*送信操作の生成されたスキーマです。|  

5.  新しいメッセージを作成する前の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**IDOCResponse**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選択および*IDOCSend.SAPBindingSchema4*します。|  

## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Idoc を SAP システムに送信するためです。 フラット ファイルをこのオーケストレーションで削除する、定義されているで IDOC の受信場所。 このファイルは、フラット ファイル逆アセンブラーを使用して XML 要求メッセージに変換されます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]がこのメッセージを使用して、SAP システムに渡します。 GUID を持つ応答は、SAP から受信され、別の場所に保存されます。 送信が含まれます、受信図形に Idoc を SAP システムに送信し、応答を受信する必要があります。 フラット ファイルを XML ファイルに変換するフラット ファイル逆アセンブラーを追加することもあります。 送信する一般的なオーケストレーションと IDOC を SAP システムが含まれます。  

- SAP システムにメッセージを送信し、応答を受信する図形を送受信します。  

- SAP システムに送信するフラット ファイル Idoc を受信するポートは一方向の受信します。  

- フラット ファイル逆アセンブラー、フラット ファイル IDOC を XML ファイルに変換します。  

- SAP システムに IDOC を送信し、応答を受信するポートを双方向に送信します。  

- SAP システムからフォルダーに、応答を送信する一方向の送信ポート。  

  サンプル オーケストレーションは、次のようになります。  

  ![Idoc を SAP に送信するオーケストレーション](../../adapters-and-accelerators/adapter-sap/media/db1490c8-da52-4af3-8a4f-d93bd815025d.gif "db1490c8-da52-4af3-8a4f-d93bd815025d")  

### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 表示される名前、*図形*列は、メッセージの構築図形の名前、オーケストレーションの上に表示されます。  

|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveFile|Receive|-設定**名前**に*ReceiveFile*<br />-設定**アクティブ**に*は True。*|  
|SendToLOB|Send|-設定**名前**に*SendToLOB*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  

### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認します。 表示される名前、*ポート*列は、ポートの名前、オーケストレーションに表示されます。  

|Port|[プロパティ]|  
|----------|----------------|  
|FileIn|-設定**識別子**に*FileIn*<br />-設定**型**に*FileInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|SaveResponse|-設定**識別子**に*SaveResponse*<br />-設定**型**に*SaveResponseType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  

### <a name="adding-a-flat-file-disassembler"></a>フラット ファイル逆アセンブラーを追加します。  
 フラット ファイル逆アセンブラーをフラット ファイル IDOC を XML 形式に変換するオーケストレーションに追加する必要があります。  

##### <a name="to-add-a-flat-file-disassembler"></a>フラット ファイル逆アセンブラーを追加するには  

1.  BizTalk プロジェクトを右クリックし、**追加**、選択および**新しい項目の**します。  

2.  ダイアログ ボックスで、次の操作を行います。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |カテゴリ|パイプライン ファイル|  
    |Visual Studio にインストールされたテンプレート|[受信パイプライン]|  
    |名前|IDOCReceive|  

3.  パイプライン デザイナーが開きます。 **BizTalk パイプライン コンポーネント**ツールボックス、ドラッグ、**フラット ファイル逆アセンブラー**パイプライン コンポーネントを**逆アセンブル**受信パイプラインのステージ。  

4.  **パイプライン コンポーネントのプロパティ**ビューの値を指定、**ドキュメント スキーマ**プロパティ。 ドロップダウン リストから、IDOC の送信操作に対応するスキーマを選択していることを確認します。  

## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表には、プロパティとメッセージのアクション図形とポートにリンクすることを指定するために設定するには、その値を指定します。 表示される名前、*図形*列は、メッセージの構築図形の名前、オーケストレーションの上に表示されます。  

|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveFile|-設定**メッセージ**に*IDOCSend*<br />-設定**操作**に*FileIn.SendIDOC.Request*|  
|SendToLob|-設定**メッセージ**に*IDOCSend*<br />-設定**操作**に*LOBPort.SendIDOC.Request*|  
|ReceiveResponse|-設定**メッセージ**に*IDOCResponse*<br />-設定**操作**に*LOBPort.SendIDOC.Response*|  
|SendResponse|-設定**メッセージ**に*IDOCResponse*<br />-設定**操作**に*SaveResponse.SendIDOC.Request*|  

 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  

 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、次を参照してください。[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)します。

## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 アプリケーションを構成する方法の詳細については、次を参照してください。[アプリケーションを構成する方法](../../core/how-to-configure-an-application.md)します。

 アプリケーションを構成する必要があります。  

- アプリケーションのホストを選択します。  

- BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  

  - ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用し、SAP システムに送信します。  

    > [!IMPORTANT]
    >  このポートの XMLReceive パイプラインのことを選択することを確認して***IDOCReceive***します。 BizTalk プロジェクトの一部としてこのパイプラインを作成したとします。  

  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションでの SAP システムからの応答を含む応答メッセージをドロップする場所の場所を定義します。  

  - SAP システムにメッセージを送信する物理 Wcf-custom または WCF-SAP 送信ポートを定義します。 送信ポートでアクションを指定することも必要があります。 ポートを作成する方法については、次を参照してください。 [SAP アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)します。

    > [!NOTE]
    >  設定することも、 *AutoConfirmSentIdocs* Idoc を SAP システムに自動的にコミットするプロパティをバインドします。 これを行う場合は、Idoc をコミットする RfcConfirmTransID 操作を明示的に呼び出す必要はありません。 バインディング プロパティの詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。 RfcConfirmTransID 操作に関する詳細については、次を参照してください。 [SAP の Trfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)します。  
    > 
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または (着信) 用のポートを受信する BizTalk 管理コンソールから、このバインド ファイルをインポートできます。 詳細については、次を参照してください。 [sap ポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)します。

## <a name="starting-the-application"></a>アプリケーションの起動  
 IDOC を SAP システムに送信するための BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを開始する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)、または[アプリケーションを起動する方法](../../core/how-to-start-and-stop-a-biztalk-application.md)します。

 この段階で、ことを確認します。  

-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  

-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  

-   SAP システムにメッセージを送信する Wcf-custom または WCF SAP の送信ポートが実行されています。  

-   操作の BizTalk オーケストレーションが実行されています。  

## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後、オーケストレーションの要求メッセージを削除する必要があります。 この例で、定義済みのフラット ファイル IDOC を削除しましたがファイルの受信場所。 要求メッセージを削除した後、次の操作が行われます。  

- オーケストレーションでは、このフラット ファイル IDOC を取得し、以前に生成したスキーマに準拠している対象のスキーマ、XML 要求メッセージに変換します。  

- 指定した要求メッセージに GUID が含まれている場合、アダプターはトランザクション ID (TID) を生成し、SAP システムに送信します。  

- 指定した要求メッセージに GUID が含まれていない場合、アダプターは GUID を生成し、その GUID を使用して、TID を生成します。 TID は SAP システムに送信されます。  

  いずれの場合は、SAP システムからの応答メッセージには、GUID が含まれています。 たとえば、既に ORDERS05 IDOC に対する送信操作の応答メッセージには。  

```  
<?xml version="1.0" encoding="utf-8"?>  
<SendResponse xmlns="http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Send">  
  <guid>a5afe162-d5cc-47b0-bf6f-3b0bfe06a97e</guid>  
</SendResponse>  
```  

 呼び出す必要があります、GUID が表示されたら、 **RfConfirmTransID** TID をコミットする操作。 詳細については、 **RfcConfirmTransID**操作を参照してください[SAP の Trfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)します。 この操作を呼び出すか、既存のオーケストレーションに新しいオーケストレーションを作成することができますか。 新しいオーケストレーションを作成する場合は、SAP システムの他の任意のオーケストレーションようになります。 既存のオーケストレーションを更新する場合を参照してください。 [BizTalk Server を使用して SAP の Trfc を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)します。 トピックの説明に従っての tRFC を呼び出すためのオーケストレーションを呼び出す方法を示します、 **RfcConfirmTransID**同じオーケストレーションから操作します。  

> [!NOTE]
>  設定した場合に RfcConfirmTransID 操作を呼び出す必要がありますいない、 *AutoConfirmSentIdocs*プロパティをバインド**True**します。  

## <a name="possible-exceptions"></a>可能性のある例外  
 BizTalk Server を使用して、SAP システムに IDOC を送信中に発生する可能性が、例外については、次を参照してください。[例外とエラーは、SAP アダプターを使用した処理](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)します。  

## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した後は、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありませんように、ファイルから構成設定をインポートできます。 バインド ファイルの詳細については、次を参照してください。[再利用の SAP アダプター バインド](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)します。

## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)