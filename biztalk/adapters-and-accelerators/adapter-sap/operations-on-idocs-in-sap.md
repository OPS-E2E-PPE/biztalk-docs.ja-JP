---
title: "SAP での Idoc に対する操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDOC, operations to receive an
- IDOCs
- IDOCs, operations on
- tRFC server
- IDOC, operations to send an
- RFC server
ms.assetid: 6abcc646-c7a3-48cf-a09e-01f516dcef97
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6a70e6bc4062a6c2865c9adb8f76d68a078e965
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-idocs-in-sap"></a>SAP での Idoc に対する操作
Idoc は、SAP が非同期的に SAP および SAP 以外のシステムと通信するためにサポートする標準の EDI のようなドキュメントです。 Idoc は、取引先の SAP システムまたは外部プログラムの間の販売注文、たとえばなどの「ビジネス」ドキュメントの送受信に使用されます。  
  
 SAP システムが Idoc を送受信するポートの種類の数をサポートしています (file ポートなど CPIC ポート) では、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] tRFC ポート経由での Idoc の送受信をサポートしています。  
  
## <a name="operations-to-send-an-idoc"></a>IDOC を送信する操作  
 TRFC の呼び出しと、SAP IDOC 呼び出しはすべては内部的に扱われ、アダプターが tRFC クライアントとして機能し、SAP IDOC を送信するの RFC を呼び出します。 その他の tRFC クライアント呼び出しと同じようにアダプター クライアントは、アダプターは、さらに、トランザクション ID (TID)、SAP システムでの呼び出しに使用する関連付けに必要に応じてデータの GUID を渡します。 (アダプターのクライアントに GUID が渡されない場合、アダプターが生成する、独自の GUID です。)GUID には、アダプターでクライアントに応答メッセージが返されます。 アダプターのクライアントでは、この GUID を使用して、SAP システムで TID を確認します。 TRFC の呼び出しは、SAP バインドの特別な静的メソッドを呼び出すことによって取得できるは、アダプターで使用される実際の SAP TID **ConvertGuidToTid**です。 実際の TID を持つには、SAP システムの問題のトラブルシューティングに役立つ可能性があります。  
  
 IDOC の完了を送信する呼び出しの後に、SAP システムで TID を確認してください。 これにより、そのデータベースから TID を削除する SAP システムです。 アダプターのクライアントは、SAP システムで TID を確認できます。  
  
-   呼び出すことによって、明示的に、 **RfcConfirmTransID**アダプターで操作します。 この操作は、(上記の応答メッセージで返される) の GUID を取得し、アダプターは、SAP システムに関連付けられている TID を確認します。  
  
-   設定して暗黙的には、 **AutoConfirmSentIdocs**プロパティをバインドします。 このバインドのプロパティが true の場合、アダプターにより自動的にコミット TID IDOC を SAP システムに送信した後です。 参照してください[mySAP Business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)詳細についてはします。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]の次の Rfc を使用して、IDOC を送信します。  
  
-   INBOUND_IDOC_PROCESS です。 この関数モジュールが使用される 4.0 より前に、の SAP リリースします。  
  
-   IDOC_INBOUND_ASYNCHRONOUS です。 この関数モジュールは、使用される SAP リリース 4.0 以降がします。  
  
### <a name="sending-idocs-with-segment-data-across-multiple-lines"></a>複数の行の Idoc のセグメントのデータを送信します。  
 Idoc はセグメントの角形で構成します。 IDOC フラット ファイル内の各セグメント エントリには、(DOCNUM フィールドを含む)、セグメント ヘッダー情報と、セグメント データが含まれています。 一部の Idoc の複数の行、セグメント データを分割できます。 例:  
  
```  
Segment header (DOCNUM is one of the fields here)  |  Segment data  
Segment header (DOCNUM is one of the fields here)  |  Segment data  
Segment data wrapped from the previous line  
Segment header (DOCNUM is one of the fields here)  |  Segment data  
```  
  
 WCF ベース[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]SAP システムにこのような Idoc の送信をサポートします。 このような Idoc の送信をサポートするために、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]かどうか、1 つ前の継続は、各セグメントのデータまたはセグメントの新しいデータであるかどうかを判断します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]セグメントの各ヘッダーを解析および DOCNUM フィールドを探してによってこれを決定します。 2 番目の行が、セグメント ヘッダーを持たない場合は、セグメント データは 2 つの直線に分割、およびその結果、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] DOCNUM フィールドを見つけられません。 したがって、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]前のセグメント データの継続タスクであることを確認できます。  
  
 たとえば、上に示した IDOC の表記で、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]の任意の DOCNUM フィールドが見つからない"`Segment data wrapped from the previous line`"し、回線が前のセグメント データの継続タスクを決定することがします。 IDOC のサイズを考えると、処理時間が長くの各セグメントのデータに対してそのようなチェックを実行して、実稼働環境でのフラット ファイルがあります。  
  
> [!NOTE]
>  アダプターは、IDOC データから識別および各セグメント レコードを抽出、復帰改行 (CRLF) ではなく DOCNUM フィールドを使用します。 無効または部分的に空白、DOCNUM レコードのフィールド コントロールとデータがある場合、アダプタは IDOC を解析に失敗します。 そのため、IDOC が SAP システムへは送信されません。  
  
### <a name="operations-to-send-an-idoc"></a>IDOC を送信する操作  
 次の操作は、Idoc を SAP システムに送信するためにサポートされます。  
  
-   **送信**です。 厳密に型指定されたスキーマを使用して SAP システムに IDOC を送信するのにには、この操作を使用します。 この操作のスキーマは、制御レコードのフィールドとセグメントのヘッダー セグメント フィールドなど、データ レコードのフィールドを公開します。 送信操作が IDocType + CimType + ReleaseNumber + バージョンに固有の組み合わせ。  
  
     この操作は各 IDOC の確認の特定の IDOC ノードで使用可能な[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
    > [!NOTE]
    >  正常に実行できる、**送信**操作、SAP システムに関連する承認が必要です。 詳しくは、  
  
-   **SendIdoc**です。 弱い型指定のスキーマを使用して、SAP システムに IDOC を送信するのにには、この操作を使用します。 この操作のスキーマは、制御レコードとのデータ レコードで構成される 1 つの文字列フィールドとして Idoc を公開します。 SendIdoc 操作は、IDOC 文字列および GUID をパラメーターとして受け取ります。  
  
     これは、SAP システムによって公開されているすべての Idoc に表示される 1 つの操作は、ルートで使用可能な**IDOC**内のノード、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
 詳細については。  
  
-   BizTalk Server を使用して SAP システムに IDOC を送信するを参照してください[を使用して BizTalk Server での SAP への Idoc の送信](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-biztalk-server.md)です。  
  
-   IDOC を送信する WCF サービスのモデルを使用して SAP システムを参照してください[WCF サービス モデルを使用して sap Idoc の送信](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-the-wcf-service-model.md)です。  
  
-   メッセージの構造と、IDOC を送信するための SOAP アクションを参照してください[IDOC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)です。  
  
## <a name="operations-to-receive-an-idoc"></a>IDOC を受信する操作  
 IDOC を受信する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] tRFC サーバーまたは RFC サーバーとして動作できます。  
  
-   TRFC サーバー バインド プロパティとして動作するようにアダプター **TidDatabaseConnectionString** TID 上のデータベース コンピューターの接続文字列に設定する必要があります。 TRFC サーバーのシナリオは、アダプターは、SAP システムから IDOC を受信する tRFC クライアント呼び出しを受け入れます。  
  
-   アダプターが RFC サーバーとして動作するため、 **TidDatabaseConnectionString** null にする必要があります (既定値)。 RFC サーバー シナリオでは、アダプターは、IDOC を受信する SAP システムからの RFC クライアント呼び出しを受け入れます。  
  
 次の Rfc が Idoc; の送受信に使用されます。Idoc を送信するときに、アダプターは、SAP システムがそれらを使用して IDOC を受信するときに対し、これらの Rfc を使用します。  
  
-   INBOUND_IDOC_PROCESS です。 この関数モジュールが使用される 4.0 より前に、の SAP リリースします。  
  
-   IDOC_INBOUND_ASYNCHRONOUS です。 この関数モジュールは、使用される SAP リリース 4.0 以降がします。  
  
 次の操作は、SAP システムから Idoc を受信するためにサポートされます。  
  
-   **受信**です。 この操作は、厳密に型指定されたスキーマを使用して SAP システムから IDOC を受信する場合に使用します。 この操作のスキーマは、制御レコードのフィールドとセグメントのヘッダー セグメント フィールドなどのデータ レコードのフィールドを公開します。  
  
     この操作は各 IDOC の確認の特定の IDOC ノードで使用可能な[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
    > [!NOTE]
    >  正常に実行できる、**受信**操作、SAP システムに関連する承認が必要です。 詳しくは、  
  
    > [!NOTE]
    >  使用して、**受信**操作、複数の Idoc を受信することもできます。  
  
-   **ReceiveIdoc**です。 この操作は、弱い型指定のスキーマを使用して SAP システムから IDOC を受信する場合に使用します。 この操作のスキーマは、制御レコードとのデータ レコードから成る 1 つの文字列フィールドとして Idoc を公開します。 この操作は、下にある XML メッセージの文字列として Idoc を受信、 \<idocData > タグです。  
  
     これは、SAP システムによって公開されているすべての Idoc に表示される 1 つの操作は、ルートで使用可能な**IDOC**内のノード、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
 Idoc を受信するときに、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインディング プロパティの値として指定できる、さまざまなメッセージ形式をサポートしている**ReceiveIDocFormat**によって公開されている、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
-   かどうか「型指定された」に設定すると、XML スキーマは厳密に型指定 IDOC の受信中にします。 (このメッセージのスキーマは受信操作から確認できます。 注スキーマが Idoc の別の異なるもの)。 これには、XML IDOC が生成されます。  
  
-   かどうかは"String"に設定して、IDOC の受信データが返されます、文字列値として。 (このメッセージのスキーマは ReceiveIdoc 操作から確認できます。) これは、結果の XML メッセージ、 \<idocData > タグです。  
  
-   場合は、メッセージ スキーマである"Rfc"に設定では、操作のため、RFC IDOC_INBOUND_ASYNCHRONOUS または INBOUND_IDOC_PROCESS、受信した IDOC のバージョンに応じて、RFC (または tRFC) スキーマと一致します。 このバインディングのプロパティを指定する場合は、IDOC を受信する IDOC_INBOUND_ASYNCHRONOUS または INBOUND_IDOC_PROCESS RFC を使用する必要があります。 最初の 2 つのオプションでは、アダプターは、この RFC を内部的に使用します。 このオプションでは、IDOC を受信するのに明示的にこの RFC を使用するだけです。  
  
 操作 IDOC を受信するために使用は、アダプターによって生成される IDOC データの形式に一致する必要があります。 次の表は、SAP から IDOC を受信できるさまざまな組み合わせの概要を提供します。  
  
|使用して、IDOC を受信するには|ReceiveIDOCFormat binding プロパティを設定するには|  
|------------------------------|---------------------------------------------------|  
|**受信**操作|型指定あり|  
|**ReciveIdoc**操作|文字列|  
|IDOC_INBOUND_ASYNCHRONOUS RFC|Rfc|  
|INBOUND_IDOC_PROCESS RFC|Rfc|  
  
 別のバインド プロパティ**PadReceivedIdocsWithSpaces**省略可能なときに、フィールドを受信した IDOC を空白で埋める受信予期される形式は"String"です。 これにより、アダプターの以前のバージョンを使用して受信した IDOC データ形式との互換性。  
  
 バインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
 詳細については。  
  
-   BizTalk Server を使用して SAP システムから IDOC の受信を参照してください[を使用して BizTalk Server での SAP からの Idoc の受信](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)です。  
  
-   BizTalk Server を使用して、トランザクションのコンテキスト内の SAP システムから IDOC を受信を参照してください[を使用して BizTalk Server でのトランザクション コンテキストでの SAP からの Idoc の受信](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server.md)です。  
  
-   メッセージの構造と、IDOC を受信するための SOAP アクションを参照してください[IDOC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)です。  
  
##  <a name="BKMK_Authorize"></a>SAP の送信を使用するための承認または受信操作  
 使用すると、**送信**または**受信**送信または厳密に型指定のスキーマを使用して Idoc を受信する操作、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]内部的に、IDOCTYPE_READ_COMPLETE RFC のメタデータを取得するを呼び出しますIDOC です。 この RFC を呼び出すには、SAP では、次の承認が必要です。  
  
```  
Authorisation object S_IDOCDEFT, Fields:  
EDI_TCD, value 'WE30'  
ACTVT, value - 03 (display)  
EDI_DOC, value  *  
EDI_CIM, value *  
```  
  
 SAP の SU01 トランザクションを使用すると、認証オブジェクトを追加します。 トランザクションに関する詳細については、SAP 管理者に問い合わせるか、SAP のマニュアルを参照してください。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)