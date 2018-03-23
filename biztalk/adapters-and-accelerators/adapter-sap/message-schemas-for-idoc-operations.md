---
title: IDOC 操作のメッセージ スキーマの BizTalk では、my SAP アダプター |Microsoft ドキュメント
description: メッセージ操作、構造、および mySAP アダプターの BizTalk アダプター パック (BAP) を使用して Idoc を送受信するアクション
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 601aa9f9-e42f-47aa-b020-7a1eed4f0780
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53da14ff55d427e3507273af4c991072cff26bec
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="message-schemas-for-idoc-operations"></a>IDOC 操作のメッセージ スキーマ
中間ドキュメント (IDOC) は、SAP および SAP 以外のシステムの両方で非同期的に通信するため、SAP でサポートされている標準の EDI のようなドキュメントです。 IDOC は、取引先の SAP システムまたは外部プログラムの間の販売注文のようなビジネス ドキュメントの送受信に使用されます。  
  
 SAP システムが送受信するように (たとえば、file ポートまたは CPIC ポート) の IDOC のポートの種類の数をサポートしていますが、 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] tRFC ポートを使用して、IDOC の送受信をサポートしています。  
  
-   発信 IDOC での[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]tRFC クライアントとして機能し、SAP に IDOC を送信するには RFC を呼び出します。  
  
-   受信 IDOC での[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]tRFC サーバーとして機能し、IDOC を受信する SAP から tRFC クライアント呼び出しを受け入れます。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムでの IDOC の送受信に使用できる IDOC ノードの下の 4 つの操作を表示します。  
  
-   **SendIdoc**です。 文字列データとしてアダプターに IDOC を送信します。 この操作は、IDOC のルート ノードの直下に確認できます。 同じ操作は、すべての Idoc に使用されます。  
  
-   **送信**です。 厳密に型指定されたデータとしてアダプターに IDOC を送信します。 この操作は、IDOC ごとに特定のノードの下で確認できます。  
  
-   **ReceiveIdoc**です。 文字列データとして、アダプターからの IDOC を受信します。 この操作は、IDOC のルート ノードの直下に確認できます。 同じ操作は、すべての Idoc に使用されます。  
  
-   **受信**です。 厳密に型指定されたデータとして、アダプターからの IDOC を受信します。 この操作は、IDOC ごとに特定のノードの下で確認できます。  
  
> [!NOTE]
>  これら 4 つの操作は、プログラムの間での Idoc を交換するためのさまざまな方法を提供し、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 アダプター常に使用、RFC (ように、次のセクションで説明) を送信するか、SAP システムでの Idoc を受信します。  
  
 4 つの IDOC 操作の 1 つを使用して、だけでなくも送信または受信する IDOC によって内部的に使用される、Rfc のいずれかを使用して、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Idoc を SAP システムと交換します。 方法の概要については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サポート Idoc を参照してください[sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)です。  
  
 このトピックには、メッセージ スキーマおよび IDOC 操作に使用されるメッセージのアクションに関する情報が含まれています。  
  
## <a name="rfcs-used-by-the-sap-adapter-to-send-and-receive-idocs"></a>送信および受信 Idoc を SAP アダプターで使用される Rfc  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] IDOC を SAP システムと交換する次のリモート関数呼び出し (Rfc) を内部的に使用します。 送信側 (SAP システムへのアダプター) で、アダプターは、RFC を呼び出す tRFC クライアントとして機能します。 (SAP アダプターから) 受信側では、SAP は tRFC サーバーとして機能すると、アダプターの RFC を呼び出します。  
  
|RFC|Description|  
|---------|-----------------|  
|IDOC_INBOUND_ASYNCHRONOUS|この関数モジュールを使用するには 4.0 以降のリリースを使用します。 4.x リリースで有効なレコードの種類の IDOC を処理します。 これにより、長い IDOC セグメントの名前がサポートされていること。<br /><br /> この RFC パラメーターは次のとおりです。<br /><br /> -idoc_control_rec_40 (SAP の構造は EDI_DC40)<br /><br /> -idoc_data_rec_40 (SAP の構造は EDI_DD40)<br /><br /> IDOC 制御レコードは、次のフィールドで構成されます。<br /><br /> - **Mestyp**です。 論理のメッセージの型。 ビジネス上のメッセージの意味が示されます。 これは、必須フィールドです。<br /><br /> - **Idoctyp**です。 IDOC の基本的な構造体。 このフィールドは、このメッセージを使用するレイアウト セットを識別します。 これは、必須フィールドです。<br /><br /> -                      **Cimtyp**です。 顧客の拡張機能の構造体。 SAP の基本的な構造を拡張すると、お客様は、拡張機能の構造に名前を付けます必要があります。 これは、顧客が; 拡張機能を行った場合の必須フィールドそれ以外の場合の初期。<br /><br /> - **フィールドをパートナー**です。 これらは送信側であり、パートナーの種類、パートナーの番号、パートナー関数などの側パートナー パラメーターを受け取る。<br /><br /> IDOC データ レコードは、次のフィールドで構成されます。<br /><br /> - **ヘッダー フィールド**です。 テーブル名、セグメントの数、セグメントの種類などのヘッダー フィールドを分割します。 これらは、必須フィールドです。<br /><br /> -                      **Sdata**です。 IDOC によって使用されるデータ用のフィールドを 1000 バイト文字。これは、必須フィールドです。|  
|INBOUND_IDOC_PROCESS|この関数モジュールについては、4.0 までのリリースで使用されます。 3.x リリースで有効なレコードの種類の IDOC を処理します。 4.x でこの関数モジュールを使用することもできます。<br /><br /> この RFC パラメーターは次のとおりです。<br /><br /> -idoc_control (SAP の構造は EDI_DC)<br /><br /> -idoc_data (SAP の構造は EDI_DD)|  
  
## <a name="operations-to-send-idocs"></a>Idoc を送信する操作  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Idoc を SAP システムに送信するクライアントの送信と SendIdoc 操作を公開します。 送信操作が IDOC は厳密に型指定されたデータとして表されます。SendIdoc 操作は、IDOC は文字列データとして表されます。 これらの操作では、アダプターと、アプリケーションの間の IDOC データの表現方法を決定します。 アダプターは常に、IDOC_INBOUND_ASYNCHRONOUS または IDOC_INBOUND_PROCESS (t) の RFC を使用して、sap Idoc を送信します。 IDOC を SAP システムを送信するには、送信または SendIdoc 操作を使用できます。 または、適切な RFC を直接呼び出すことができます。  
  
### <a name="message-structures-for-idoc-client-operations"></a>IDOC のクライアント操作のメッセージの構造体  
 次の表は、送信と SendIdoc 操作のメッセージ構造を示します。  
  
|操作|XML データ構造|Description|  
|---------------|-------------------|-----------------|  
|Send|`<Send xmlns="[MSG_VERSION]/Idoc/[VERSION]/[IDOCTYP]/                    [CIMTYP]/[RELNO]/Send">   <idocData>     <[EDI_DC40/EDI_DC] xmlns="/Types/Idoc/      [VERSION]/[IDOCTYP]/[CIMTYP]/[RELNO]">       <EDIDC_FIELD1>value1</ EDIDC_FIELD1>       <EDIDC_FIELD2>value2</ EDIDC_FIELD2>       …     </EDI_DC40>     <[SEGMENT_DEFN]_1>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_1>     <[SEGMENT_DEFN]_2>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_2>     …     </[EDI_DC40/EDI_DC]>   </idocData>   <guid>guid</guid> </Send>`|厳密に型指定された IDOC を SAP に送信します。<br /><br /> の IDOC スキーマは、厳密に型指定されたです。<br /><br /> -公開は、レコードのフィールドを制御します。<br /><br /> -セグメント ヘッダー セグメント フィールドなどのデータ レコードのフィールドを公開します。<br /><br /> [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP トランザクション ID (TID) IDOC を送信に使用される GUID を関連付けます。 要求メッセージ内の GUID を指定するかどうかを選択できます。 要求メッセージの GUID が含まれていない場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]いずれかが生成されます。 GUID は、応答メッセージで返されます。|  
|応答を送信します。|`<SendResponse xmlns="[MSG_VERSION]/Idoc/[VERSION]/         [IDOCTYP]/[CIMTYP]/[RELNO]/Send">   <guid>guid</guid> </SendResponse>`|IDOC が SAP システムに送信されたことを示します。<br /><br /> 場合、 **AutoConfirmSentIdocs**プロパティのバインドは**true**、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムでトランザクションを自動的に確認し、応答で返される GUID を無視することができます。 場合、 **AutoConfirmSentIdocs**プロパティのバインドは**false**、呼び出す必要があります、 **RfcConfirmTransID** GUID を持つ操作がによって返される、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]にSAP システムでトランザクションを完了します。<br /><br /> 呼び出すことができます、 **SapAdapterUtilities.ConvertGuidToTid**作業 (LUW) の論理ユニットに関連付けられている TID を取得します。|  
|SendIdoc|`<SendIdoc xmlns="[MSG_VERSION]/Idoc">   <idocData>docDataString</idocData>   <guid>guid</guid> </SendIdoc>`|弱い型指定の IDOC を SAP に送信します。<br /><br /> の IDOC スキーマは、弱い型指定します。<br /><br /> -制御レコードとのデータ レコードで構成される 1 つの文字列フィールドとして、IDOC を公開します。<br /><br /> [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] IDOC を送信に使用される SAP TID は GUID を関連付けます。 要求メッセージ内の GUID を指定するかどうかを選択できます。 要求メッセージの GUID が含まれていない場合、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 1 つ生成されます。 応答メッセージの GUID が返されます|  
|SendIdoc 応答|`<SendIdocResponse xmlns="[MSG_VERSION]/Idoc">   <guid>guid</guid> </SendIdocResponse>`|IDOC が SAP システムに送信されたことを示します。<br /><br /> 場合、 **AutoConfirmSentIdocs**プロパティのバインドは**true**、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムでトランザクションを自動的に確認し、応答で返される GUID を無視することができます。 場合、 **AutoConfirmSentIdocs**プロパティのバインドは**false**、呼び出す必要があります、 **RfcConfirmTransID** GUID を持つ操作がによって返される、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]にSAP システムでトランザクションを完了します。<br /><br /> 呼び出すことができます、 **SapAdapterUtilities.ConvertGuidToTid** LUW に関連付けられている TID を取得します。|  
  
 [MSG_VERSION] = メッセージ バージョンの文字列です。たとえば、http://Microsoft.LobServices.Sap/2007/03です。  
  
 [バージョン] (2 または 3) の IDOC のリリース バージョンを = です。  
  
 [IDOCTYP] = IDOC の種類です。たとえば、ORDERS05 です。  
  
 [CIMTYP]、カスタマイズされた IDOC の Cimtype を = です。  
  
 [RELNO] = リリース番号です。たとえば、620 です。  
  
 [EDI_DC40/EDI_DC] = リリース用に EDI_DC40 の Idoc のバージョン 3 およびの EDI_DC version2 Idoc をリリースします。  
  
 [EDIDC_FIELD] EDI_DC40/EDI_DC 制御レコードの構造を構成するフィールドを = です。  
  
 [SEGMENT_DEFN] = セグメントの定義名 (セグメントの型名ではなく) です。たとえば、E2EDK01005 です。 セグメントの定義のノードでした セグメント グループ ノードでも表示されるメモは、IDOC の構造に基づいています。  
  
 [DATAHEADERCOLUMN_(SEGHDR_FLD)] = 各セグメントには、セグメント データのヘッダー フィールドの標準的なセットで構成されるセグメント ヘッダー。 セグメントのデータは、すべてのセグメント フィールドとデータで構成されます。 このノードが表すセグメントのヘッダー フィールドです。たとえば、DATAHEADERCOLUMN_SEGNAM です。  
  
 [SEG_FIELD] 特定のセグメントの定義 [SEGMENT_DEFN] を構成するセグメント フィールド名を = です。  
  
 [guid] GUID パラメーターを = です。  
  
### <a name="message-actions-for-idoc-client-operations"></a>IDOC のクライアント操作のメッセージの動作  
 次の表は、送信と SendIdoc の操作のメッセージ アクションを示します。  
  
|操作|操作|例|  
|---------------|------------|-------------|  
|Send|[MESSAGE_VERSION]/Idoc/[バージョン]/[IDOCTYP]/[CIMTYP]/[RELNO]/[送信]|http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Send|  
|応答を送信します。|[MESSAGE_VERSION]/Idoc/[VERSION] /[IDOCTYP]/[CIMTYP]/[RELNO]/Send/response|http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Send/response|  
|SendIdoc|[MESSAGE_VERSION]/Idoc/SendIdoc|http://Microsoft.LobServices.Sap/2007/03/Idoc/SendIdoc|  
|SendIdoc 応答|[MESSAGE_VERSION]/Idoc/SendIdoc/応答|http://Microsoft.LobServices.Sap/2007/03/Idoc/SendIdoc/response|  
  
 [MESSAGE_VERSION] = メッセージ バージョンの文字列です。たとえば、http://Microsoft.LobServices.Sap/2007/03です。  
  
 [バージョン] (2 または 3) の IDOC のリリース バージョンを = です。  
  
 [IDOCTYP] = IDOC の種類です。たとえば、ORDERS05 です。  
  
 [CIMTYP]、カスタマイズされた IDOC の Cimtype を = です。  
  
 [RELNO] = リリース番号です。たとえば、620 です。  
  
## <a name="operations-to-receive-idocs"></a>Idoc を受信する操作  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムから Idoc を受信するアプリケーションの受信と ReceiveIdoc 操作を公開します。 受信操作が IDOC は厳密に型指定されたデータとして表されます。ReceiveIdoc 操作は、IDOC は文字列データとして表されます。  
  
 これらの操作では、アダプターによって、アプリケーションに IDOC データを生成する方法を決定します。 アダプターは常に、IDOC_INBOUND_ASYNCHRONOUS または IDOC_INBOUND_PROCESS tRFC として、SAP システムから Idoc を受け取ります。 受信パイプラインまたは ReceiveIdoc の操作を使用できます。 または RFC 形式で IDOC データを受信することができます。 設定する、 **ReceiveIdocFormat**アダプターが、アプリケーションに IDOC データを出力する式を指定するプロパティをバインドします。 詳細については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインドのプロパティを参照してください[mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
### <a name="message-structures-for-idoc-receive-operations"></a>受信操作での IDOC メッセージの構造体  
 次の表は、受信パイプラインおよび ReceiveIdoc 操作のメッセージ構造を示します。  
  
|操作|XML データ構造|Description|  
|---------------|-------------------|-----------------|  
|Receive|`<Receive xmlns="[MSG_VERSION]/Idoc/[VERSION]/[IDOCTYP]/                 [CIMTYP]/[RELNO]/Receive">   <idocData>     <[EDI_DC40/EDI_DC] xmlns="/Types/Idoc/      [VERSION]/[IDOCTYP]/[CIMTYP]/[RELNO]">       <EDIDC_FIELD1>value1</ EDIDC_FIELD1>       <EDIDC_FIELD2>value2</ EDIDC_FIELD2>       …     </EDI_DC40>     <[SEGMENT_DEFN]_1>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_1>     <[SEGMENT_DEFN]_2>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_2>     …     </[EDI_DC40/EDI_DC]>   </idocData> </Receive>`|厳密に型指定された IDOC が SAP から受信します。<br /><br /> の IDOC スキーマは、厳密に型指定されたです。<br /><br /> -公開は、レコードのフィールドを制御します。<br /><br /> -セグメント ヘッダー セグメント フィールドなどのデータ レコードのフィールドを公開します。|  
|応答を受信します。|`<ReceiveResponse xmlns="[MSG_VERSION]/Idoc/[VERSION]/[IDOCTYP]/         [CIMTYP]/[RELNO]/Receive"> </ReceiveResponse>`|IDOC が SAP システムから受信されたことを示します。|  
|ReceiveIdoc|`<ReceiveIdoc xmlns="[MSG_VERSION]/Idoc">   <idocData>docDataString</idocData> </ReceiveIdoc>`|SAP からの弱い型指定の IDOC を受信します。<br /><br /> の IDOC スキーマは、弱い型指定します。<br /><br /> -制御レコードとのデータ レコードで構成される 1 つの文字列フィールドとして、IDOC を公開します。|  
|ReceiveIdoc 応答|`<ReceiveIdocResponse xmlns="[MSG_VERSION]/Idoc"> </ReceiveIdocResponse>`|IDOC が SAP システムから受信されたことを示します。|  
  
 [MSG_VERSION] = メッセージ バージョンの文字列です。たとえば、http://Microsoft.LobServices.Sap/2007/03です。  
  
 [バージョン] (2 または 3) の IDOC のリリース バージョンを = です。  
  
 [IDOCTYP] = IDOC の種類です。たとえば、ORDERS05 です。  
  
 [CIMTYP]、カスタマイズされた IDOC の Cimtype を = です。  
  
 [RELNO] = リリース番号です。たとえば、620 です。  
  
 [EDI_DC40/EDI_DC] = リリース用に EDI_DC40 Idoc のバージョン 3 の EDI_DC のリリースの Idoc のバージョン 2 です。  
  
 [EDIDC_FIELD] EDI_DC40/EDI_DC 制御レコードの構造を構成するフィールドを = です。  
  
 [SEGMENT_DEFN] = セグメントの定義名 (セグメントの型名ではなく) です。たとえば、E2EDK01005 です。 セグメントの定義ノードは、IDOC の構造に基づくセグメント グループ ノードでも表示できます。  
  
 [DATAHEADERCOLUMN_(SEGHDR_FLD)] = 各セグメントには、セグメント データのヘッダー フィールドの標準的なセットで構成されるセグメント ヘッダー。 セグメントのデータは、すべてのセグメント フィールドとデータで構成されます。 このノードが表すセグメントのヘッダー フィールドです。たとえば、DATAHEADERCOLUMN_SEGNAM です。  
  
 [SEG_FIELD] 特定のセグメントの定義 [SEGMENT_DEFN] を構成するセグメント フィールド名を = です。  
  
#### <a name="receiving-an-idoc-in-rfc-format"></a>RFC 形式での IDOC の受信  
 RFC 形式でも Idoc を受信できます。 SAP からの Idoc を受信するために使用する Rfc は次のとおりです。  
  
-   Idoc のバージョン 3 の IDOC_INBOUND_ASYNCHRONOUS します。  
  
-   Idoc のバージョン 2 の INBOUND_IDOC_PROCESS します。  
  
 次のコードは、IDOC_INBOUND_ASYNCHRONOUS 操作として受信した IDOC の構造を示しています。  
  
```  
<IDOC_INBOUND_ASYNCHRONOUS xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <IDOC_CONTROL_REC_40>  
    <EDI_DC40 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <EDIDC_FIELD1>field1</EDIDC_FIELD1>  
      <EDIDC_FIELD2>field2</EDIDC_FIELD2>  
      …  
    </EDI_DC40>  
  <IDOC_DATA_REC_40>  
    <EDI_DD40 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <[SEG_HEADER_FIELD1]>value1</[SEG_HEADER_FIELD1]>  
      <[SEG_HEADER_FIELD2]>value2</[SEG_HEADER_FIELD2]>  
      …  
      <SDATA>segment value</SDATA>  
    </EDI_DD40>  
    …  
  </IDOC_DATA_REC_40>  
</IDOC_INBOUND_ASYNCHRONOUS>  
```  
  
 [EDIDC_FIELD] EDI_DC40/EDI_DC 制御レコードの構造を構成するフィールドを =  
  
 [SEG_HEADER_FIELD] = 各セグメントには、セグメント データのヘッダー フィールドの標準的なセットで構成されるセグメント ヘッダー。 セグメントのデータは、すべてのセグメント フィールドとデータで構成されます。 このノードが表すセグメントのヘッダー フィールドです。たとえば、SEGNAM、MANDT、および DOCNUM にします。  
  
 TRFC 操作の書式設定に関する詳細については、次を参照してください。 [tRFC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)です。  
  
### <a name="message-actions-for-idoc-receive-operations"></a>受信操作での IDOC メッセージ アクション  
 次の表は、受信パイプラインおよび ReceiveIdoc 操作のメッセージ アクションを示します。  
  
|操作|操作|例|  
|---------------|------------|-------------|  
|Receive|[MESSAGE_VERSION]/Idoc/[VERSION] /[IDOCTYP]/[CIMTYP]/[RELNO]/Receive|http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Receive|  
|応答を受信します。|[MESSAGE_VERSION]/Idoc/[VERSION] /[IDOCTYP]/[CIMTYP]/[RELNO]/Receive/response|http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Receive/response|  
|ReceiveIdoc|[MESSAGE_VERSION]/Idoc/ReceiveIdoc|http://Microsoft.LobServices.Sap/2007/03/Idoc/ReceiveIdoc|  
|ReceiveIdoc 応答|[MESSAGE_VERSION]/Idoc/ReceiveIdoc/応答|http://Microsoft.LobServices.Sap/2007/03/Idoc/ReceiveIdoc/response|  
  
