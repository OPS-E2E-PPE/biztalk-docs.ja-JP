---
title: BizTalk Server を使用して SAP の Idoc を受信する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDOCs, sample (receiving)
- IDOCs, business scenarios for receiving
- IDOCs, receiving from SAP using BizTalk Server
ms.assetid: b904bf07-1108-4ed3-8564-d83eaafff247
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6673d6a35853ab240218c29afba50579c614135e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373086"
---
# <a name="receive-idocs-from-sap-using-biztalk-server"></a>BizTalk Server を使用して SAP の Idoc を受信します。
IDOC の受信では、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP からの特別な RFC 呼び出しを受信する RFC サーバーとして機能します。 SAP アダプターは、RFC サーバーまたは tRFC サーバーとして機能する Idoc を受信できます。 TRFC サーバーとして動作してアダプターを使用した IDOC の受信についての詳細については、次を参照してください。[を使用して BizTalk Server でのトランザクション コンテキストでの SAP からの Idoc の受信](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server.md)します。  

 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェスの Idoc を受信する 2 つの異なる操作。  

- **受信**操作により厳密に型指定されたスキーマが Idoc を受信するアダプター。  

- **ReceiveIdoc**操作により厳密に型指定のスキーマが Idoc を受信するアダプター。 この操作での XML メッセージの文字列としての Idoc の受信、 \<idocData\>タグ。  

  アダプター側での値を指定することができます、 **ReceiveIDocFormat**アダプターの受信が IDOC の形式を指定するプロパティをバインドします。  

- **型指定された**厳密に型指定されたスキーマで Idoc を受信するが、アダプターを指定します。 これには、XML IDOC が生成されます。  

- **文字列**厳密に型指定のスキーマで Idoc を受信するが、アダプターを指定します。 XML メッセージが生成されます、 \<idocData\>タグ。  

- **Rfc**任意の形式で Idoc を受信するが、アダプターを指定します。  

  Idoc を受信するため、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]も、オーケストレーションでアダプターのクライアントが使用できるメッセージ コンテキスト プロパティのセットをサポートしています。 プロパティの一覧で、次を参照してください。[メッセージ コンテキスト プロパティの Idoc の受信を](../../adapters-and-accelerators/adapter-sap/message-context-properties-for-receiving-idocs.md)します。  

  方法の詳細については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、SAP システムから Idoc を受信するサポートを参照してください[sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)します。 SOAP の構造の詳細については、IDOC を受信するメッセージを参照してください。 [IDOC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)します。  

## <a name="biztalk-scenarios-for-receiving-idocs-from-an-sap-system"></a>SAP システムから Idoc を受信するための BizTalk シナリオ  
 次の表は、SAP システムから Idoc を受信するため、BizTalk の主なシナリオを示します。  


| SAP からアダプターへの入力 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        BizTalk 処理                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |            [出力]             |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| (TRFC インターフェイス) を使用して IDOC |                                                                                                                                                                                                                                                                                                                                           **メタデータ デザイン時**<br /><br /> 1.GenerateFlatFileCompatibleIdocSchema バインディング プロパティを設定する**True**します。<br />2.スキーマを生成、**受信**操作を使用して特定 IDOC の[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。<br />3.ReceiveIdocFormat バインディング プロパティを設定する**型指定された**します。<br /><br /> **オーケストレーションのデザイン時**<br /><br /> 1.XML の IDOC を受信します。<br />2.フラット ファイル IDOC を XML に変換するのにには、フラット ファイル アセンブラーを使用します。                                                                                                                                                                                                                                                                                                                                           |        フラット ファイル IDOC         |
| (TRFC インターフェイス) を使用して IDOC |                                                                                                                                                                                                                                                                                                                                                                             **メタデータ デザイン時**<br /><br /> 1.GenerateFlatFileCompatibleIdocSchema バインディング プロパティを設定する**True**します。<br />2.スキーマを生成、**受信**操作を使用して特定 IDOC の[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。<br />3.ReceiveIdocFormat バインディング プロパティを設定する**型指定された**します。<br /><br /> **オーケストレーションのデザイン時**<br /><br /> -XML の IDOC を受信します。                                                                                                                                                                                                                                                                                                                                                                              |           XML の IDOC            |
| (TRFC インターフェイス) を使用して IDOC | **メタデータ デザイン時**<br /><br /> 1.GenerateFlatFileCompatibleIdocSchema バインディング プロパティを設定する**True**します。<br />2.スキーマを生成、**受信**操作を使用して特定 IDOC の[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。<br />3.ReceiveIdocFormat バインディング プロパティを設定する**文字列**します。<br /><br /> **オーケストレーションのデザイン時**<br /><br /> 1.受信 XML メッセージをフラット ファイル IDOC で\<idocData\>タグ。<br />2.受信ポートの構成で、WCF アダプターの XPath のサポートを使用して、XML メッセージからフラット ファイル IDoc を抽出します。 以下に例を示します。<br />     `/*[local-name()='ReceiveIdoc']/*[local-name()='idocData']`<br />3.XML の IDOC フラット ファイル IDOC に変換するのにには、フラット ファイル逆アセンブラーを使用します。<br /><br /> **重要な**、new を使用して Idoc を受信するのにはこの方法を使用できる WCF ベース[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]し、既存の BizTalk SAP アダプターからの Idoc の受信に書き込まれた既存の BizTalk プロジェクトに直接適用します。 これは、また、バージョン番号未満のリリース番号 (SYSREL) Idoc を受信するための推奨アプローチです。 |           XML の IDOC            |
| (TRFC インターフェイス) を使用して IDOC |                                                                                                                                                                                                                                                                                                                                                                                     **メタデータ デザイン時**<br /><br /> 1.スキーマを生成、 **ReceiveIdoc**操作を使用して IDOC ノード[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。<br />2.ReceiveIdocFormat バインディング プロパティを設定する**文字列**します。<br /><br /> **オーケストレーションのデザイン時**<br /><br /> -文字列として表される IDOC と XML メッセージが表示される、 \<idocData\>タグ。                                                                                                                                                                                                                                                                                                                                                                                     | XML メッセージのフラット ファイル IDOC |

## <a name="how-to-receive-an-idoc-from-an-sap-system"></a>SAP システムから IDOC を受信する方法は?  
 使用して SAP システムでの操作を実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[SAP アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)します。 これらのタスクは、SAP システムから IDOC を受信するには。  

1. BizTalk プロジェクトを作成し、SAP システムを起動する IDOC のスキーマを生成します。 スキーマの生成中にことを必要なバインドのプロパティを設定することを確認して、前の表に記載されています。 バインドのプロパティを設定する方法については、次を参照してください。 [SAP アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)します。  

2. SAP システムからメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。  

3. SAP システムから IDOC を受信するオーケストレーションを作成します。  

4. ビルドし、BizTalk プロジェクトを配置します。  

5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  

6. BizTalk アプリケーションを起動します。  

   このトピックでは、これらのタスクを実行する手順を説明します。  

## <a name="samples-based-on-this-topic"></a>このトピックに基づくサンプル  
 サンプル、ReceiveIDOC、このトピックに基づく ReceiveIDOC_SYSREL も付属している、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、次を参照してください。 [SAP アダプターのサンプル](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)します。  

## <a name="generating-schema"></a>スキーマを生成します。  
 スキーマを生成する必要があります、*受信*の操作、 *ORDERS03 します。V3.620* IDOC、 */IDOC/ORDERS/ORDERS03*ノード。 参照してください[参照、検索と SAP の IDOC 操作のメタデータを get](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-idoc-operations-in-sap.md)特定 IDOC のスキーマを生成する方法の詳細について。 スキーマを生成するときにも、次のプロパティを設定する可能性があります。  

-   *GenerateFlatFileCompatibleIDoc* – 生成\<appinfo\>タグを BizTalk フラット ファイル パーサーは、フラット ファイル Idoc をサポートするために BizTalk のシナリオで使用できるようにします。  

-   *FlatFileSegmentIndicator* – 場合を示します、IDOC スキーマ\<appinfo\>タグは、セグメントの定義名またはセグメントの型名を含める必要があります。 これは、SAP とは、フラット ファイル IDOC の送信/受信、使用を希望の場合に適用されます。 場合、 *GenerateFlatFileCompatibleIDoc*を false に設定し、 *FlatFileSegmentIndicator*プロパティのバインドは無視されます。  

> [!IMPORTANT]
>  着信 IDOC のスキーマを生成するため、選択して確認**サービス (受信操作)** から、**コントラクト型を選択します**ドロップダウン リストで、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]します。  

## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションからメッセージを最初の手順で生成したスキーマをリンクする必要があります。  

 このトピックでは、2 つのメッセージを作成する必要があります: 応答を送信する他の SAP システムから IDOC を受信する 1 つ。  

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
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選択と*ReceiveIDOC.SAPBindingSchema2*ここで、 *ReceiveIDOC* BizTalk プロジェクトの名前を指定します。 *SAPBindingSchema2*は受信操作に対して生成されるスキーマです。|  

6.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**応答**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選択および*ReceiveIDOC.SAPBindingSchema3*します。|  

## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SAP システムから Idoc を受信するためです。 一般的なシナリオで、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムから IDOC の呼び出しを受け取り、要求を処理し、SAP システムへの応答を渡します。 オーケストレーションの一部として、これを実現するには、オーケストレーションを含める必要があります。  

- 双方向の受信ポート、SAP システムから Idoc を受信し、応答を送信します。  

- 送信し、受信図形。  

- メッセージの図形を作成し、その中の SAP システムに送信される応答を生成する、メッセージの割り当て図形。  

  > [!NOTE]
  >  オーケストレーションが含まれている場合は、双方向受信ポート (要求-応答) に SAP システムから Idoc を受信する、オーケストレーションは、SAP システムへの応答を送信する必要があります。 それ以外の場合は、SAP システムは、[次へ] の IDOC を送信しません。 ただし場合は、一方向の受信ポート、オーケストレーションが SAP システムへの応答を送信する必要はありません。  

- フォルダーに、SAP システムから受信した Idoc を送信する一方向の送信ポート。  

  SAP システムから IDOC を受信するためのサンプルのオーケストレーションは、ようになります。  

  ![Idoc を受信するオーケストレーション](../../adapters-and-accelerators/adapter-sap/media/20d4f251-2474-4fd5-becd-2915f9efa81b.gif "20d4f251-2474-4fd5-becd-2915f9efa81b")  

### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 表示される名前、*図形*列は、メッセージの構築図形の名前、オーケストレーションの上に表示されます。  

|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ListenToSAP|Receive|-設定**名前**に*ListenToSAP*<br /><br /> -設定**アクティブ**に*は True。*|  
|SaveIDOC|Send|-設定**名前**に*SaveIDOC*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  

### <a name="adding-construct-message-shape"></a>メッセージの構築図形を追加します。  
 オーケストレーション内では、応答を生成し、SAP システムに送信する必要があります。 これを行うには、メッセージの構築図形を追加する必要があり、内でメッセージの割り当ての図形をオーケストレーションにします。 メッセージの割り当て図形では、SAP システムに送信される応答メッセージを生成するコードを呼び出します。 メッセージの割り当て図形では、SAP システムに送信される応答のアクションも設定します。  

> [!IMPORTANT]
>  オーケストレーションが含まれている場合は、双方向受信ポート (要求-応答) に SAP システムから Idoc を受信する、オーケストレーションは、SAP システムへの応答を送信する必要があります。 それ以外の場合は、SAP システムは、[次へ] の IDOC を送信しません。 ただし場合は、一方向の受信ポート、オーケストレーションが SAP システムへの応答を送信する必要はありません。  

 メッセージの構築図形で、設定、**メッセージ構築**プロパティを**応答**します。  

 応答を生成するコードは、BizTalk プロジェクトと同じ Visual Studio ソリューションの一部になります。 応答メッセージを生成するためのサンプル コードは、次のように検索します。  

```  
namespace IdocReceiveResponseMessageCreator  
{  
    public class IdocReceiveResponseMessageCreator  
    {  
        private static XmlDocument Message;  
        private static string XmlFileLocation;  
        private static string ResponseDoc;  

        public static XmlDocument XMLMessageCreator()  
        {  
            XmlFileLocation = "C:\\test\\in";  
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

> [!NOTE]
>  プロジェクトをビルドした後に IdocReceiveResponseMessageCreator.dll がプロジェクト ディレクトリに作成されます。 この DLL は、グローバル アセンブリ キャッシュ (GAC) に追加する必要があります。  

 メッセージの割り当て図形から次のコードを呼び出すと、SAP システムに送信する応答のアクションを設定するのには、次の式を追加します。 式を追加するには、式エディターを開きますメッセージの割り当て図形をダブルクリックします。  

```  
Response = IdocReceiveResponseMessageCreator.IdocReceiveResponseMessageCreator.XMLMessageCreator();  
Response(WCF.Action)= "http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS03//620/Receive/response";  
```  

> [!IMPORTANT]
>  応答メッセージのアクションを明示的に設定する必要があります。 アクションを設定しないと、WCF カスタム アダプターが"Response"要求された操作を追加することでのアクションのメッセージが到着します。 そのため、応答メッセージのアクションを`http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS03//620/ReceiveResponse`します。 ただし、sapBinding が必要ですが、応答アクションを追加して"/応答"例については、要求アクションに`http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS03//620/Receive/response`します。  

### <a name="adding-ports"></a>ポートの追加  
 論理ポートの次のプロパティを指定することを確認します。 名前、*ポート*列が、ポートの名前、オーケストレーションに表示されます。  

|Port|[プロパティ]|  
|----------|----------------|  
|ReceiveIDOCPort|-設定**識別子**に*ReceiveIDOCPort*<br /><br /> -設定**型**に*ReceiveIDOCPortType*<br /><br /> -設定**通信パターン**に*要求-応答*<br /><br /> -設定**通信方向**に*受信送信*|  
|GetIDOCPort|-設定**識別子**に*GetIDOCPort*<br /><br /> -設定**型**に*GetIDOCPortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*送信*|  

> [!IMPORTANT]
>  オーケストレーションが含まれている場合は、双方向受信ポート (要求-応答) に SAP システムから Idoc を受信する、オーケストレーションは、SAP システムへの応答を送信する必要があります。 それ以外の場合は、SAP システムは、[次へ] の IDOC を送信しません。  

### <a name="adding-a-flat-file-assembler"></a>フラット ファイル アセンブラーを追加します。  
 フラット ファイル IDOC の受信メッセージに変換するアセンブラーを追加する必要があります。  

##### <a name="to-add-a-flat-file-assembler"></a>フラット ファイル アセンブラーを追加するには  

1.  BizTalk プロジェクトを右クリックし、**追加**、選択および**新しい項目の**します。  

2.  ダイアログ ボックスで、次の操作を行います。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |カテゴリ|パイプライン ファイル|  
    |Visual Studio にインストールされたテンプレート|送信パイプライン|  
    |名前|SendIDOC|  

3.  パイプライン デザイナーが開きます。 **BizTalk パイプライン コンポーネント**ツールボックス、ドラッグ、**フラット ファイル アセンブラー**パイプライン コンポーネントを**アセンブル**送信パイプラインのステージ。  

4.  **パイプライン コンポーネントのプロパティ**ビューの値を指定、**ドキュメント スキーマ**プロパティ。 ドロップダウン リストから作成スキーマを選択することを確認して、IDOC に対応する受信操作。  

## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表には、プロパティとメッセージのアクション図形とポートにリンクすることを指定するために設定するには、その値を指定します。 表示される名前、*図形*列は、メッセージの構築図形の名前、オーケストレーションの上に表示されます。  

|図形|[プロパティ]|  
|-----------|----------------|  
|ListenToSAP|-設定**メッセージ**に*要求*<br /><br /> -設定**操作**に*ReceiveIDOCPort.ReceiveIDOC.Request*|  
|SaveIDOC|-設定**メッセージ**に*要求*<br /><br /> -設定**操作**に*GetIDOCPort.ReceiveIDOC.Request*|  
|SendResponse|-設定**メッセージ**に*応答*<br /><br /> -設定**操作**に*ReceiveIDOCPort.ReceiveIDOC.Response*|  

 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  

 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、次を参照してください[のビルドとオーケストレーションの実行。](../../core/building-and-running-orchestrations.md)

## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 アプリケーションを構成する方法の詳細については、次を参照してください。[アプリケーションを構成する方法](../../core/how-to-configure-an-application.md)します。

 アプリケーションを構成する必要があります。  

- アプリケーションのホストを選択します。  

- BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  

  - 送信場所と物理送信ポートを定義します。 この場所は、SAP システムから Idoc が格納されます。  

    > [!IMPORTANT]
    >  XMLTransmit パイプラインのことを選択することを確認して***SendIDOC***します。 BizTalk プロジェクトの一部としてこのパイプラインを作成したとします。  

  - WCF カスタム定義または WCF SAP 受信ポート。 このポートは、SAP システムから受信 IDOC を受信し、オーケストレーションに渡します。 このポートには、SAP システムへの応答も送信します。 ポートを作成する方法については、次を参照してください。 [SAP アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)します。

    > [!IMPORTANT]
    >  バインディングのプロパティを必ず**ReceiveIDocFormat**に設定されている**型指定された**します。  
    > 
    > [!IMPORTANT]
    >  場合バインディング プロパティ**EnableBizTalkCompatibilityMode** BizTalk プロパティ スキーマ DLL を追加するかどうかを確認してください、true に設定されているため、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] BizTalk アプリケーションでは、アプリケーションのリソースとして、プロジェクトがデプロイされます。 リソースを追加する手順についてを参照してください。 [SAP アダプターを使用した運用上の問題のトラブルシューティングを行う](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md)します。  
    > 
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または (着信) 用のポートを受信する BizTalk 管理コンソールから、このバインド ファイルをインポートできます。 詳細については、次を参照してください。 [sap ポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)します。

  BizTalk アプリケーションに IdocReceiveResponseMessageCreator プロジェクトのアセンブリを追加することも必要があります。 SAP システムに送信される応答を生成するには、このプロジェクトを作成したとします。 そのためには次を行います。  

1.  右クリックし、バインドをインポートする BizTalk アプリケーションの下で、BizTalk Server 管理コンソールの左側にあるコンソール ツリーで**リソース**、 をポイント**追加**順にクリックします**BizTalk アセンブリ**します。  

2.  **リソースの追加** ダイアログ ボックスをクリックします**追加**IdocReceiveResponseMessageCreator.dll を含むフォルダーに移動します。 ファイルを選択し、をクリックし、**オープン**します。  

3.  **リソースの追加**ダイアログ ボックスで、をクリックして**OK**。  

## <a name="starting-the-application"></a>アプリケーションの起動  
 SAP システムから IDOC を受信するための BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを開始する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)、または[アプリケーションを起動する方法](../../core/how-to-start-and-stop-a-biztalk-application.md)します。

 この段階で、ことを確認します。  

-   ファイルの場所を受信した IDOC を保存する FILE 送信ポートが実行されています。  

-   受信 Idoc を受信するポートの Wcf-custom または WCF SAP SAP からシステムが実行されています。  

-   操作の BizTalk オーケストレーションが実行されています。  

## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後は、SAP システムを移動し、アダプターに IDOC を送信する必要があります。 アダプターは、IDOC を受信し、オーケストレーションの一部として指定されたファイルの場所に保存します。  

## <a name="possible-exceptions"></a>可能性のある例外  
 BizTalk Server を使用して SAP システムから IDOC を受信中に発生する可能性が、例外については、次を参照してください。[例外とエラーは、SAP アダプターを使用した処理](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)します。  

## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した後は、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありませんように、ファイルから構成設定をインポートできます。 バインド ファイルの詳細については、次を参照してください。[再利用の SAP アダプター バインド](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)します。

## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)