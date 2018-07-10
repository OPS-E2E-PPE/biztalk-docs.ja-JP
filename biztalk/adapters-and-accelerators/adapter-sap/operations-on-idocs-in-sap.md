---
title: Sap Idoc に対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDOC, operations to receive an
- IDOCs
- IDOCs, operations on
- tRFC server
- IDOC, operations to send an
- RFC server
ms.assetid: 6abcc646-c7a3-48cf-a09e-01f516dcef97
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9c3bbf45074024b8745b845b3f9ca85f5ff814e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972227"
---
# <a name="operations-on-idocs-in-sap"></a>Sap Idoc に対する操作
Idoc は、SAP と SAP 以外のシステムと非同期的に通信するために SAP がサポートしている標準の EDI のようなドキュメントです。 Idoc は、取引先の SAP システムまたは外部プログラムの間の販売の注文などの"business"ドキュメントの送受信に使用されます。  
  
 SAP システム数を送信し、Idoc を受信するポートの種類をサポートしています (file ポートなど CPIC ポート)、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] tRFC ポート経由で Idoc の送受信をサポートしています。  
  
## <a name="operations-to-send-an-idoc"></a>IDOC を送信する操作  
 TRFC の呼び出し、すべての SAP IDOC 呼び出しは内部的に扱われます、アダプターは、tRFC クライアントとして機能し、IDOC を送信する SAP の RFC を呼び出します。 その他の tRFC クライアント呼び出しと同じようアダプター クライアントは必要に応じて、アダプターでは、さらにトランザクション ID (TID) での SAP システムの呼び出しに使用した関連付けますに GUID を渡します。 (アダプター クライアントが GUID を渡さない場合、アダプターが生成する、独自の GUID です。)アダプターでクライアントに応答メッセージは、GUID が返されます。 アダプター クライアントでは、この GUID を使用して、SAP システムで TID を確認します。 TRFC の呼び出しは、SAP バインドで特殊な静的メソッドを呼び出すことによって取得できますに、アダプターによって使用される実際の SAP TID **ConvertGuidToTid**します。 実際の TID を持つには、SAP システムの問題のトラブルシューティングに役立つ可能性があります。  
  
 IDOC の完了を送信する呼び出しの後に、SAP システムで TID を確認する必要があります。 これにより、そのデータベースから TID を削除する SAP システムができます。 アダプターのクライアントは、SAP システムで TID を確認できます。  
  
- 明示的に呼び出して、 **RfcConfirmTransID**アダプターの操作。 この操作は、(上記の応答メッセージで返される) の GUID を受け取り、アダプターは、SAP システムに関連付けられている TID を確認します。  
  
- 設定して、暗黙的、 **AutoConfirmSentIdocs**プロパティをバインドします。 このバインドのプロパティが true の場合 IDOC を SAP システムに送信した後、アダプターがその TID を自動的にコミットします。 参照してください[mySAP Business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)詳細についてはします。  
  
  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次の Rfc を使用して、IDOC を送信します。  
  
- INBOUND_IDOC_PROCESS します。 この関数のモジュールが使用される SAP が 4.0 より前にリリースします。  
  
- IDOC_INBOUND_ASYNCHRONOUS します。 この関数のモジュールに使用される SAP リリース 4.0 以降です。  
  
### <a name="sending-idocs-with-segment-data-across-multiple-lines"></a>複数の行のデータ セグメントで Idoc を送信します。  
 セグメントの Idoc を使用したされます。 IDOC フラット ファイル内の各セグメント エントリには、(DOCNUM フィールドを含む) セグメントのヘッダー情報と、セグメント データが含まれています。 いくつかの Idoc の複数の行、セグメント データを分割できます。 以下に例を示します。  
  
```  
Segment header (DOCNUM is one of the fields here)  |  Segment data  
Segment header (DOCNUM is one of the fields here)  |  Segment data  
Segment data wrapped from the previous line  
Segment header (DOCNUM is one of the fields here)  |  Segment data  
```  
  
 WCF ベース[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]SAP システムにこのような Idoc の送信をサポートします。 、このような Idoc の送信をサポートするために、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]かどうかは、前の続きは、各セグメントのデータまたはある新しいセグメント データであるかを判断します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]各セグメント ヘッダーを解析して DOCNUM フィールドを探してこれを決定します。 2 行目がセグメント ヘッダーを持たない場合、セグメント データは、2 つの行に分かれては、その結果、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] DOCNUM フィールドが見つからない。 そのため、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]前のセグメント データの継続があると判断できます。  
  
 など前に、示した IDOC の表記で、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] DOCNUM のフィールドが見つからない"`Segment data wrapped from the previous line`"行に、前のセグメント データの継続があると判断することができます。 IDOC のサイズを考えると、処理時間が長く、各セグメントのデータをそのようなチェックを実行する運用環境でのフラット ファイルがあります。  
  
> [!NOTE]
>  アダプターは、IDOC データから識別および各セグメント レコードを抽出、復帰改行 (CRLF) ではなく DOCNUM フィールドを使用します。 コントロールとデータのレコードの DOCNUM フィールドは、無効または部分的に空白には、アダプターは、IDOC の解析に失敗します。 そのため、IDOC が SAP システムには送信されません。  
  
### <a name="operations-to-send-an-idoc"></a>IDOC を送信する操作  
 Idoc を SAP システムに送信するため、次の操作がサポートされます。  
  
- **送信**します。 厳密に型指定されたスキーマを使用して、SAP システムに IDOC を送信するのにには、この操作を使用します。 この操作のスキーマは、制御レコードのフィールドとセグメントのヘッダー セグメント フィールドなど、データ レコードのフィールドを公開します。 送信操作は、IDocType + CimType + ReleaseNumber + バージョンに固有の組み合わせ。  
  
   この操作は、idoc ごとに表示されの特定の IDOC ノード下にある、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。  
  
  > [!NOTE]
  >  IDOC_INBOUND_ASYNCHRONOUS RFC 詳しくは、  
  
- **Rfc INBOUND_IDOC_PROCESS RFC 別のバインド プロパティPadReceivedIdocsWithSpaces受信した IDOC を空白で埋めるときに省略可能なフィールドの受信に必要な形式は"String"です。 これにより、アダプターの以前のバージョンを使用して受信した IDOC データ形式との互換性ができます。  
  
   バインド プロパティの詳細については、次を参照してください。 **mySAP Business Suite バインド プロパティの BizTalk アダプターについて**します。  
  
  BizTalk Server を使用して SAP システムから IDOC の受信を参照してくださいを使用して BizTalk Server での SAP からの Idoc の受信します。  
  
- BizTalk Server を使用してトランザクション コンテキストでの SAP システムから IDOC を受信するを参照してください[を使用して BizTalk Server でのトランザクション コンテキストでの SAP からの Idoc の受信](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-biztalk-server.md)します。  
  
- メッセージの構造と IDOC を受信するための SOAP アクションを参照してください[IDOC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-the-wcf-service-model.md)します。  
  
- SAP の送信を使用するための承認または受信操作  
  
## <a name="operations-to-receive-an-idoc"></a>使用すると、送信または受信送信または厳密に型指定されたスキーマを使用して Idoc を受信する操作、内部的にメタデータを取得する IDOCTYPE_READ_COMPLETE RFC を呼び出すIDOC します。  
 この RFC を呼び出すには、SAP で次の承認が必要です。  
  
- SAP で SU01 トランザクションを使用すると、承認オブジェクトを追加します。 トランザクションに関する詳細については、SAP 管理者に問い合わせるか、SAP のマニュアルを参照してください。  
  
- どのような操作は、アダプターを使用して実行しますか? RFC サーバー シナリオでは、アダプターは、SAP システムから IDOC を受信するため RFC クライアント呼び出しを受け入れます。  
  
  次の Rfc は Idoc; を送受信するために使用します。Idoc を送信するときに、アダプターは、SAP システムがそれらを使用して IDOC を受信するときに、これらの Rfc を使用します。  
  
- INBOUND_IDOC_PROCESS します。 この関数のモジュールが使用される SAP が 4.0 より前にリリースします。  
  
- IDOC_INBOUND_ASYNCHRONOUS します。 この関数のモジュールに使用される SAP リリース 4.0 以降です。  
  
  SAP システムから Idoc を受信するため、次の操作がサポートされます。  
  
- **受信**します。 厳密に型指定されたスキーマを使用して、SAP システムから IDOC を受信するのにには、この操作を使用します。 この操作のスキーマは、制御レコードのフィールドとセグメントのヘッダーとセグメント フィールドを含むデータ レコードのフィールドを公開します。  
  
   この操作は、idoc ごとに表示されの特定の IDOC ノード下にある、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。  
  
  > [!NOTE]
  >  正常に実行できる、**受信**操作、SAP システムに関連する承認が必要です。 詳しくは、  
  
  > [!NOTE]
  >  使用して、**受信**操作、複数の Idoc を受信することもできます。  
  
- **ReceiveIdoc**します。 厳密に型指定のスキーマを使用して、SAP システムから IDOC を受信するのにには、この操作を使用します。 この操作のスキーマでは、制御レコードとレコードのデータで構成される 1 つの文字列フィールドとして Idoc を公開します。 この操作での XML メッセージの文字列としての Idoc の受信、 \<idocData\>タグ。  
  
   バインド プロパティの詳細については、次を参照してください。 **mySAP Business Suite バインド プロパティの BizTalk アダプターについて**します。  
  
  Idoc を受信するときに、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインディング プロパティの値として指定できる、さまざまなメッセージ形式をサポートしている**ReceiveIDocFormat**によって公開されている、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
- かどうか「型指定された」に設定すると、XML スキーマは厳密に型指定 IDOC 受信されています。 (このメッセージのスキーマは受信操作から確認できます。 2004 スキーマが Idoc の別の異なる)。 これには、XML IDOC が生成されます。  
  
- かどうか"String"に設定して、IDOC の受信データが返されますの文字列値として。 (このメッセージのスキーマは ReceiveIdoc 操作から確認できます。) XML メッセージが生成されます、 \<idocData\>タグ。  
  
- 場合は、メッセージ スキーマである"Rfc"に設定では、受信した IDOC のバージョンに応じて RFC 操作 IDOC_INBOUND_ASYNCHRONOUS または INBOUND_IDOC_PROCESS、RFC (または tRFC) スキーマと一致します。 このバインドのプロパティを指定する場合は、IDOC を受信する IDOC_INBOUND_ASYNCHRONOUS または INBOUND_IDOC_PROCESS RFC を使用する必要があります。 最初の 2 つのオプションで、アダプターは、この RFC を内部的に使用します。 このオプションで明示的に IDOC を受信するのにこの RFC を使用します。  
  
  IDOC を受信するために使用する操作は、アダプターによって出力される IDOC データの形式に一致する必要があります。 次の表では、IDOC を SAP から受信できるさまざまな組み合わせの概要を示します。  
  
|使用して、IDOC を受信するには|ReceiveIDOCFormat バインディング プロパティを設定するには|  
|------------------------------|---------------------------------------------------|  
|**受信**操作|型指定あり|  
|**ReciveIdoc**操作|String|  
|IDOC_INBOUND_ASYNCHRONOUS RFC|Rfc|  
|INBOUND_IDOC_PROCESS RFC|Rfc|  
  
 別のバインド プロパティ**PadReceivedIdocsWithSpaces**受信した IDOC を空白で埋めるときに省略可能なフィールドの受信に必要な形式は"String"です。 これにより、アダプターの以前のバージョンを使用して受信した IDOC データ形式との互換性ができます。  
  
 バインド プロパティの詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。  
  
 BizTalk Server を使用して SAP システムから IDOC の受信を参照してくださいを使用して BizTalk Server での SAP からの Idoc の受信します。  
  
-   BizTalk Server を使用して SAP システムから IDOC の受信を参照してください[を使用して BizTalk Server での SAP からの Idoc の受信](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)します。  
  
-   BizTalk Server を使用してトランザクション コンテキストでの SAP システムから IDOC を受信するを参照してください[を使用して BizTalk Server でのトランザクション コンテキストでの SAP からの Idoc の受信](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server.md)します。  
  
-   メッセージの構造と IDOC を受信するための SOAP アクションを参照してください[IDOC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)します。  
  
##  <a name="BKMK_Authorize"></a> SAP の送信を使用するための承認または受信操作  
 使用すると、**送信**または**受信**送信または厳密に型指定されたスキーマを使用して Idoc を受信する操作、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]内部的にメタデータを取得する IDOCTYPE_READ_COMPLETE RFC を呼び出すIDOC します。 この RFC を呼び出すには、SAP で次の承認が必要です。  
  
```  
Authorisation object S_IDOCDEFT, Fields:  
EDI_TCD, value 'WE30'  
ACTVT, value - 03 (display)  
EDI_DOC, value  *  
EDI_CIM, value *  
```  
  
 SAP で SU01 トランザクションを使用すると、承認オブジェクトを追加します。 トランザクションに関する詳細については、SAP 管理者に問い合わせるか、SAP のマニュアルを参照してください。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)