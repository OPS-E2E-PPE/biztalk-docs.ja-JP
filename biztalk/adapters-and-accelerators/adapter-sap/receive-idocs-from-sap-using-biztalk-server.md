---
title: BizTalk Server を使用して SAP からの Idoc を受信 |Microsoft ドキュメント
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
ms.openlocfilehash: cb03368a9d046eacf31f8b7bbed5c0a7f090c3d3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968064"
---
# <a name="receive-idocs-from-sap-using-biztalk-server"></a>BizTalk Server を使用して SAP からの Idoc を受信します。
IDOC の受信では、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP からの特別な RFC 呼び出しを受信する RFC サーバーとして機能します。 SAP アダプターは、RFC サーバーまたは tRFC サーバーとして機能する Idoc を受信できます。 TRFC サーバーとして動作して、アダプターによる IDOC の受信の詳細については、次を参照してください。[を使用して BizTalk Server でのトランザクション コンテキストでの SAP からの Idoc の受信](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server.md)です。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Idoc を受信する 2 つの異なる操作を表示します。  
  
-   **受信**操作を厳密に型指定されたスキーマが Idoc を受信するアダプターを有効にします。  
  
-   **ReceiveIdoc**操作を厳密に型指定されたスキーマが Idoc を受信するアダプターを有効にします。 この操作は、下にある XML メッセージの文字列として Idoc を受信、 \<idocData\>タグ。  
  
 アダプター側での値を指定することができます、 **ReceiveIDocFormat**アダプターは受信 IDOC の形式を指定するプロパティをバインドします。  
  
-   **型指定された**アダプターは厳密に型指定されたスキーマでの Idoc の受信を指定します。 これには、XML IDOC が生成されます。  
  
-   **文字列**弱い型指定のスキーマを持つアダプターが Idoc を受信するかを指定します。 これは、結果の XML メッセージ、 \<idocData\>タグ。  
  
-   **Rfc**アダプターは任意の形式での Idoc の受信を指定します。  
  
 Idoc を受信するため、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]も、オーケストレーションでアダプターのクライアントが使用できるメッセージ コンテキスト プロパティのセットをサポートします。 プロパティの一覧で、次を参照してください。[の Idoc の受信のメッセージ コンテキスト プロパティ](../../adapters-and-accelerators/adapter-sap/message-context-properties-for-receiving-idocs.md)です。  
  
 方法の詳細については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、SAP システムからの Idoc の受信をサポートを参照してください[sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)です。 SOAP の構造の詳細については、IDOC を受信するメッセージを参照してください[IDOC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)です。  
  
## <a name="biztalk-scenarios-for-receiving-idocs-from-an-sap-system"></a>SAP システムから Idoc を受信するための BizTalk シナリオ  
 次の表は、SAP システムから Idoc を受信するため、BizTalk、主要なシナリオを示します。  
  
|SAP からアダプターへの入力|BizTalk 処理|出力|  
|-------------------------------|------------------------|------------|  
|(TRFC インターフェイス) を使用して IDOC|**メタデータ デザイン時**<br /><br /> 1.GenerateFlatFileCompatibleIdocSchema binding プロパティを設定する**True**です。<br />2.スキーマを生成、**受信**特定 IDOC を使用して、操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。<br />3.ReceiveIdocFormat binding プロパティを設定する**型指定された**です。<br /><br /> **オーケストレーションのデザイン時**<br /><br /> 1.XML の IDOC を受信します。<br />2.フラット ファイル アセンブラーを使用して、フラット ファイルを XML IDOC に変換します。|フラット ファイル IDOC|  
|(TRFC インターフェイス) を使用して IDOC|**メタデータ デザイン時**<br /><br /> 1.GenerateFlatFileCompatibleIdocSchema binding プロパティを設定する**True**です。<br />2.スキーマを生成、**受信**特定 IDOC を使用して、操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。<br />3.ReceiveIdocFormat binding プロパティを設定する**型指定された**です。<br /><br /> **オーケストレーションのデザイン時**<br /><br /> -XML IDOC を受信します。|XML の IDOC|  
|(TRFC インターフェイス) を使用して IDOC|**メタデータ デザイン時**<br /><br /> 1.GenerateFlatFileCompatibleIdocSchema binding プロパティを設定する**True**です。<br />2.スキーマを生成、**受信**特定 IDOC を使用して、操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。<br />3.ReceiveIdocFormat binding プロパティを設定する**文字列**です。<br /><br /> **オーケストレーションのデザイン時**<br /><br /> 1.フラット ファイル IDOC でのメッセージが XML \<idocData\>タグ。<br />2.受信ポートの構成で、WCF アダプターの XPath のサポートを使用して、XML メッセージからフラット ファイル IDoc を抽出します。 例:<br />     `/*[local-name()='ReceiveIdoc']/*[local-name()='idocData']`<br />3.フラット ファイル逆アセンブラーを使用して、フラット ファイル IDOC を XML IDOC に変換します。<br /><br /> **重要な**、new を使用して Idoc を受信するこの方法を使用できる WCF ベース[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]し、直接、既存の BizTalk SAP アダプターからの Idoc を受信するために記述された既存の BizTalk プロジェクトに適用します。 これもリリース番号 (SYSREL) よりも小さいバージョン番号で Idoc を受信する方法をお勧めします。|XML の IDOC|  
|(TRFC インターフェイス) を使用して IDOC|**メタデータ デザイン時**<br /><br /> 1.スキーマを生成、 **ReceiveIdoc** 、IDOC を使用してノードから操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。<br />2.ReceiveIdocFormat binding プロパティを設定する**文字列**です。<br /><br /> **オーケストレーションのデザイン時**<br /><br /> 受信 XML メッセージの文字列として表される IDOC と、 \<idocData\>タグ。|XML メッセージのフラット ファイル IDOC|  
  
## <a name="how-to-receive-an-idoc-from-an-sap-system"></a>SAP システムから IDOC を受信する方法は?  
 SAP システムを使用して、操作を実行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [SAP アプリケーションを作成するビルド ブロック](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)です。 これらのタスクは、SAP システムから IDOC を受信するには。  
  
1.  BizTalk プロジェクトを作成し、IDOC が SAP システムで、呼び出し先のスキーマを生成します。 スキーマの生成中を確認してください、必要なバインドのプロパティを設定する前の表に一覧表示します。 バインドのプロパティを設定する方法の手順については、次を参照してください。 [SAP アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)です。  
  
2.  SAP システムからメッセージを送受信するための BizTalk プロジェクトでメッセージを作成します。  
  
3.  SAP システムから IDOC を受信するオーケストレーションを作成します。  
  
4.  構築し、BizTalk プロジェクトを展開します。  
  
5.  BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
6.  BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="samples-based-on-this-topic"></a>このトピックの内容に基づくサンプル  
 サンプル、ReceiveIDOC および ReceiveIDOC_SYSREL、このトピックの内容に基づくも付属しています、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。 [SAP アダプターのサンプル](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)です。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 スキーマを生成する必要があります、*受信*の操作、 *ORDERS03 です。V3.620* IDOC、 */IDOC/ORDERS/ORDERS03*ノード。 参照してください[参照、検索と get メタデータの SAP IDOC 操作](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-idoc-operations-in-sap.md)手順については、特定の IDOC のスキーマを生成する方法です。 スキーマを生成するときにも、次のプロパティを設定する可能性があります。  
  
-   *GenerateFlatFileCompatibleIDoc* – 生成\<appinfo\>タグで、BizTalk フラット ファイル パーサーは、フラット ファイル Idoc をサポートするために BizTalk のシナリオで使用できるようにします。  
  
-   *FlatFileSegmentIndicator* – を示す場合、IDOC スキーマ\<appinfo\>タグは、セグメントの定義名またはセグメントの型名を含める必要があります。 これは、ときに/SAP からのフラット ファイル IDOC の送信/受信するのに使用されると適用されます。 場合、 *GenerateFlatFileCompatibleIDoc*が false に設定し、 *FlatFileSegmentIndicator*バインディング プロパティは無視されます。  
  
> [!IMPORTANT]
>  着信 IDOC のスキーマを生成するためには、選択を確認してください**サービス (入力方向の操作)** から、**選択コントラクト型**ドロップダウン リストで、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]です。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションの種類からのメッセージに最初の手順で生成したスキーマをリンクする必要があります。  
  
 このトピックでは、2 つのメッセージを作成する必要があります: SAP システムとは、応答を送信する IDOC を受信します。  
  
 メッセージを作成し、スキーマにそれらをリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  新しいオーケストレーションを BizTalk プロジェクトに追加します。  
  
2.  オーケストレーションの種類、BizTalk プロジェクトを開くまだ開いていない場合。 をクリックして**ビュー**、 をポイント**その他のウィンドウ**、 をクリック**オーケストレーション**です。  
  
3.  **オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。  
  
4.  右クリックし、新規メッセージを作成および選択**プロパティ ウィンドウ**します。  
  
5.  **プロパティ**ウィンドウ**Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**要求**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*ReceiveIDOC.SAPBindingSchema2*ここで、 *ReceiveIDOC* BizTalk プロジェクトの名前を指定します。 *SAPBindingSchema2*受信操作に対して生成されるスキーマです。|  
  
6.  新しいメッセージを作成する 2 の手順を繰り返します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**応答**です。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**を選択して*ReceiveIDOC.SAPBindingSchema3*です。|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SAP システムから Idoc を受信するためです。 一般的なシナリオで、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムから IDOC 呼び出しを受信が要求を処理し、SAP システムへの応答を渡します。 これを実現するオーケストレーションの一部として、オーケストレーションを含める必要があります。  
  
-   双方向の受信ポートを SAP システムから Idoc を受信し、応答を送信します。  
  
-   送信図形と受信図形。  
  
-   メッセージの構築図形、およびそのメッセージの割り当て図形、SAP システムに送信される応答を生成します。  
  
    > [!NOTE]
    >  オーケストレーションが含まれている場合は、双方向受信ポート (要求-応答)、SAP システムから Idoc を受信するため、オーケストレーションは、SAP システムへの応答を送信する必要があります。 それ以外の場合は、SAP システムは、[次へ] の IDOC を送信しません。 ただし場合は、一方向の受信ポート、オーケストレーションが SAP システムへの応答を送信する必要はありません。  
  
-   フォルダーに SAP システムから受信した Idoc を送信する一方向の送信ポート。  
  
 SAP システムから IDOC を受信するためのサンプル オーケストレーションは、ようになります。  
  
 ![Idoc を受信するオーケストレーション](../../adapters-and-accelerators/adapter-sap/media/20d4f251-2474-4fd5-becd-2915f9efa81b.gif "20d4f251-2474-4fd5-becd-2915f9efa81b")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。 示されている名前、*図形*列が上記のオーケストレーションで表示される、メッセージの構築図形の名前を示します。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ListenToSAP|Receive|-設定**名前**に*ListenToSAP*<br /><br /> -設定**アクティブ**に*は True。*|  
|SaveIDOC|Send|-設定**名前**に*SaveIDOC*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
### <a name="adding-construct-message-shape"></a>メッセージの構築図形を追加します。  
 そのオーケストレーション内では、応答を生成して SAP システムに送信します。 これを行うには、メッセージの構築図形を追加する必要があり、そのメッセージの割り当ての図形をオーケストレーションにします。 メッセージの割り当て図形では、SAP システムに送信される応答メッセージを生成するコードを呼び出します。 メッセージの割り当て図形では、SAP システムに送信される応答のアクションも設定します。  
  
> [!IMPORTANT]
>  オーケストレーションが含まれている場合は、双方向受信ポート (要求-応答)、SAP システムから Idoc を受信するため、オーケストレーションは、SAP システムへの応答を送信する必要があります。 それ以外の場合は、SAP システムは、[次へ] の IDOC を送信しません。 ただし場合は、一方向の受信ポート、オーケストレーションが SAP システムへの応答を送信する必要はありません。  
  
 メッセージの構築図形、設定、**メッセージ構築**プロパティを**応答**です。  
  
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
>  プロジェクトをビルドした後、IdocReceiveResponseMessageCreator.dll はプロジェクト ディレクトリに作成されます。 グローバル アセンブリ キャッシュ (GAC) には、この DLL を追加する必要があります。  
  
 メッセージの割り当て図形から次のコードを呼び出すと、SAP システムに送信される応答のアクションを設定する次の式を追加します。 式を追加するには、式エディターを開く、メッセージの割り当て図形をダブルクリックします。  
  
```  
Response = IdocReceiveResponseMessageCreator.IdocReceiveResponseMessageCreator.XMLMessageCreator();  
Response(WCF.Action)= "http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS03//620/Receive/response";  
```  
  
> [!IMPORTANT]
>  応答メッセージのアクションを明示的に設定する必要があります。 アクションを設定しないと、Wcf-custom アダプターは要求された操作を"Response"を追加することによって、アクション メッセージでに到着します。 そのため、応答メッセージのアクションを`http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS03//620/ReceiveResponse`です。 ただし、sapBinding が必要ですが、応答アクションを追加して"/応答"例については、要求された操作に`http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS03//620/Receive/response`です。  
  
### <a name="adding-ports"></a>ポートの追加  
 次のプロパティ、論理ポートを指定することを確認してください。 表示される名前、*ポート*列は、ポートの名前、オーケストレーションで表示されます。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|ReceiveIDOCPort|-設定**識別子**に*ReceiveIDOCPort*<br /><br /> -設定**型**に*ReceiveIDOCPortType*<br /><br /> -設定**通信パターン**に*要求-応答*<br /><br /> -設定**通信方向**に*受信送信*|  
|GetIDOCPort|-設定**識別子**に*GetIDOCPort*<br /><br /> -設定**型**に*GetIDOCPortType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*送信*|  
  
> [!IMPORTANT]
>  オーケストレーションが含まれている場合は、双方向受信ポート (要求-応答)、SAP システムから Idoc を受信するため、オーケストレーションは、SAP システムへの応答を送信する必要があります。 それ以外の場合は、SAP システムは、[次へ] の IDOC を送信しません。  
  
### <a name="adding-a-flat-file-assembler"></a>フラット ファイル アセンブラーを追加します。  
 IDOC の受信メッセージをフラット ファイルに変換するアセンブラーを追加する必要があります。  
  
##### <a name="to-add-a-flat-file-assembler"></a>フラット ファイル アセンブラーを追加するには  
  
1.  BizTalk プロジェクトを右クリックし、**追加**を選択して**新しい項目の**します。  
  
2.  ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |カテゴリ|パイプライン ファイル|  
    |Visual Studio にインストールされたテンプレート|送信パイプライン|  
    |名前|SendIDOC|  
  
3.  パイプライン デザイナーが開きます。 **BizTalk パイプライン コンポーネント**ツールボックス、ドラッグ、**フラット ファイル アセンブラー**にパイプライン コンポーネント、**アセンブル**送信パイプラインのステージ。  
  
4.  **パイプライン コンポーネントのプロパティ**ビューで、値を指定、**ドキュメント スキーマ**プロパティです。 ドロップダウン リストから、スキーマを選択することを確認してください、IDOC に対応する受信操作します。  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表は、プロパティと、メッセージのアクション図形およびポートにリンクすることを指定するために設定するには、その値を指定します。 示されている名前、*図形*列が上記のオーケストレーションで表示される、メッセージの構築図形の名前を示します。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ListenToSAP|-設定**メッセージ**に*要求*<br /><br /> -設定**操作**に*ReceiveIDOCPort.ReceiveIDOC.Request*|  
|SaveIDOC|-設定**メッセージ**に*要求*<br /><br /> -設定**操作**に*GetIDOCPort.ReceiveIDOC.Request*|  
|SendResponse|-設定**メッセージ**に*応答*<br /><br /> -設定**操作**に*ReceiveIDOCPort.ReceiveIDOC.Response*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください[のビルドおよび実行するオーケストレーション。](../../core/building-and-running-orchestrations.md)
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 アプリケーションの構成の詳細については、次を参照してください。[アプリケーションを構成する方法](../../core/how-to-configure-an-application.md)です。
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   送信場所と物理送信ポートを定義します。 この場所は、SAP システムから Idoc が含まれます。  
  
        > [!IMPORTANT]
        >  XMLTransmit パイプラインの選択を確認します***SendIDOC***です。 BizTalk プロジェクトの一部としてこのパイプラインを作成したとします。  
  
    -   WCF カスタム定義または WCF SAP 受信ポートにします。 このポートは SAP システムから受信 IDOC を受信し、オーケストレーションを渡します。 このポートは、SAP システムへの応答も送信します。 ポートを作成する方法については、次を参照してください。 [SAP アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)です。
  
        > [!IMPORTANT]
        >  バインディング プロパティを確認してください**ReceiveIDocFormat**に設定されている**型指定された**です。  
  
        > [!IMPORTANT]
        >  場合はバインディング プロパティ**EnableBizTalkCompatibilityMode** BizTalk プロパティ スキーマ DLL を追加するかどうかを確認を真に設定されているため、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] BizTalk アプリケーションでは、アプリケーションのリソースとして、プロジェクトを配置します。 リソースを追加する手順についてを参照してください。 [SAP アダプターでの運用上の問題のトラブルシューティングを行う](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md)です。  
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または受信ポート (着信)、BizTalk 管理コンソールからこのバインド ファイルをインポートすることができます。 詳細については、次を参照してください。 [sap ポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)です。
  
 IdocReceiveResponseMessageCreator プロジェクトのアセンブリを BizTalk アプリケーションに追加することも必要があります。 SAP システムに送信される応答を生成するには、このプロジェクトを作成したとします。 そのためには次を行います。  
  
1.  右クリックし、バインドをインポートする BizTalk アプリケーションの下で、BizTalk Server 管理コンソールの左側にあるコンソール ツリーで**リソース**、 をポイント**追加** をクリックし、**BizTalk アセンブリ**です。  
  
2.  **リソースの追加**] ダイアログ ボックス、[**追加**IdocReceiveResponseMessageCreator.dll を含むフォルダーに移動します。 ファイルを選択し、をクリックして**開く**です。  
  
3.  **リソースの追加**ダイアログ ボックスで、をクリックして**OK**です。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 SAP システムから IDOC を受信するための BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)、または[アプリケーションを起動する方法](../../core/how-to-start-and-stop-a-biztalk-application.md)です。
  
 この段階で確認します。  
  
-   ファイルの場所に受信した IDOC を保存する FILE 送信ポートが実行されています。  
  
-   受信 Idoc を受信するポートの Wcf-custom または WCF SAP SAP からシステムが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行すると、したら、SAP システムを移動して、アダプターに IDOC を送信する必要があります。 アダプターは、IDOC を受信し、オーケストレーションの一部として指定されたファイルの場所に保存します。  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 例外については、BizTalk Server を使用して SAP システムから IDOC を受信中に発生する可能性が、次を参照してください。[例外とエラー処理、SAP アダプター](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)です。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。[を再利用の SAP アダプターのバインド](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)です。
  
## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)