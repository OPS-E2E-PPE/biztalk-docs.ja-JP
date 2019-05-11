---
title: IDOC 操作のメッセージ スキーマの BizTalk で、SAP アダプター |Microsoft Docs
description: メッセージ処理、構造、および mySAP アダプターの BizTalk アダプター パック (BAP) を使用して Idoc を送受信するアクション
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 601aa9f9-e42f-47aa-b020-7a1eed4f0780
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ff2135fe19c5dc9ac96be694220ac3c1762bf73
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373237"
---
# <a name="message-schemas-for-idoc-operations"></a>IDOC 操作のメッセージ スキーマ
中間ドキュメント (IDOC) は、SAP と SAP 以外のシステムと非同期的に通信するために、SAP でサポートされる標準の EDI のようなドキュメントです。 IDOC は、取引先の SAP システムまたは外部プログラムの間の販売注文のようなビジネス ドキュメントの送受信に使用されます。  

 SAP システム数を送信し、(file ポートまたは CPIC ポート) IDOC を受信するポートの種類をサポートしていますが、 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] tRFC ポートを使用して IDOC の送受信をサポートしています。  

- 発信 IDOC での[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]tRFC クライアントとして機能し、SAP に IDOC を送信するには RFC を呼び出します。  

- 受信 IDOC での[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]tRFC サーバーとして機能し、IDOC を受信する SAP の tRFC クライアント呼び出しを受け入れます。  

  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムでの IDOC の送受信に使用できる IDOC ノードの下の 4 つの操作を表示します。  

- **SendIdoc**します。 文字列データとしてアダプターに IDOC を送信します。 この操作は、IDOC のルート ノードのすぐ下に表示されます。 同じ操作は、すべての Idoc のために使用されます。  

- **送信**します。 厳密に型指定されたデータとしてアダプターに IDOC を送信します。 この操作は、IDOC ごとに特定のノードの下に表示されます。  

- **ReceiveIdoc**します。 文字列データとして、アダプターからの IDOC を受信します。 この操作は、IDOC のルート ノードのすぐ下に表示されます。 同じ操作は、すべての Idoc のために使用されます。  

- **受信**します。 厳密に型指定されたデータとして、アダプターからの IDOC を受信します。 この操作は、IDOC ごとに特定のノードの下に表示されます。  

> [!NOTE]
>  これら 4 つの操作は、プログラム間で Idoc を交換するためのさまざまな方法を提供し、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 アダプター常には使用、RFC (次のセクションで説明) を送信または SAP システムで Idoc を受信します。  

 4 つの IDOC 操作のいずれかを使用する以外も送信またはによって内部的に使用される、Rfc のいずれかで IDOC を受信することができます、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Idoc を SAP システムを交換します。 方法の概要については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サポート Idoc を参照してください[sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)します。  

 このトピックには、メッセージのスキーマおよび IDOC 操作のために使用するメッセージの動作に関する情報が含まれています。  

## <a name="rfcs-used-by-the-sap-adapter-to-send-and-receive-idocs"></a>Rfc は、送信への SAP アダプターによって使用され、Idoc を受信します。  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] IDOC を SAP システムを交換する次のリモート関数呼び出し (Rfc) を内部的に使用します。 送信側 (SAP システムへのアダプター) では、アダプターは、RFC を呼び出す tRFC クライアントとして機能します。 受信側 (SAP アダプター) では、SAP は、RFC、tRFC サーバーとして機能すると、アダプターでを呼び出します。  

|RFC|説明|  
|---------|-----------------|  
|IDOC_INBOUND_ASYNCHRONOUS|この関数のモジュールは、4.0 およびそれ以降のリリースから使用されます。 4.x のリリースで有効なレコードの種類の IDOC を処理します。 これにより、長い IDOC セグメントの名前がサポートされていること。<br /><br /> この RFC パラメーターは次のとおりです。<br /><br /> -idoc_control_rec_40 (SAP の構造は EDI_DC40)<br /><br /> -idoc_data_rec_40 (SAP の構造は EDI_DD40)<br /><br /> IDOC の制御レコードは、次のフィールドで構成されます。<br /><br /> - **Mestyp**します。 論理のメッセージの種類。 メッセージのビジネスの意味を伝達します。 これは必須フィールドです。<br /><br /> - **Idoctyp**します。 IDOC の基本的な構造体。 このフィールドは、このメッセージを使用するレイアウトのセットを識別します。 これは必須フィールドです。<br /><br /> -                      **Cimtyp**します。 顧客の拡張機能の構造体。 SAP の基本的な構造を拡張すると、お客様は、拡張機能の構造に名前を 必要があります。 これは、顧客が; 拡張機能を行った場合の必須フィールド初期それ以外の場合。<br /><br /> - **フィールドをパートナー**します。 これらは送信側であり、受信側パートナーの種類、パートナーの数、パートナー関数などのパートナー パラメーター。<br /><br /> IDOC データ レコードは、次のフィールドで構成されます。<br /><br /> - **ヘッダー フィールド**します。 テーブル名、セグメントの数、セグメントの種類のヘッダー フィールドを分割します。 これらは、必須フィールドです。<br /><br /> -                      **Sdata**します。 IDOC で使用されるデータ用のフィールドを 1000 バイト文字。これは必須フィールドです。|  
|INBOUND_IDOC_PROCESS|この関数のモジュールは、4.0 までのリリースで使用されます。 3.x リリースに対して有効なレコードの種類の IDOC を処理します。 4.x でこの関数モジュールを使用することもできます。<br /><br /> この RFC パラメーターは次のとおりです。<br /><br /> -idoc_control (SAP の構造は EDI_DC)<br /><br /> -idoc_data (SAP の構造は EDI_DD)|  

## <a name="operations-to-send-idocs"></a>Idoc を送信する操作  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Idoc を SAP システムに送信するクライアントの送信および SendIdoc の操作を公開します。 送信操作では、IDOC は厳密に型指定されたデータとして表されます。SendIdoc 操作の場合は、IDOC は文字列データとして表されます。 これらの操作では、アダプターとアプリケーション間の IDOC のデータの表示方法を指定します。 アダプターは常に、IDOC_INBOUND_ASYNCHRONOUS または IDOC_INBOUND_PROCESS (t) の RFC を使用して、sap の Idoc を送信します。 IDOC を SAP システムに送信するには、送信または SendIdoc 操作を使用することができますか、または適切な RFC を直接呼び出すことができます。  

### <a name="message-structures-for-idoc-client-operations"></a>IDOC のクライアント操作のメッセージの構造体  
 次の表では、送信と SendIdoc 操作のメッセージの構造を示します。  


|     演算     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   XML の構造体                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                                                                                   説明                                                                                                                                                                                                                                                                                                                                                                   |
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       Send        | `<Send xmlns="[MSG_VERSION]/Idoc/[VERSION]/[IDOCTYP]/                    [CIMTYP]/[RELNO]/Send">   <idocData>     <[EDI_DC40/EDI_DC] xmlns="/Types/Idoc/      [VERSION]/[IDOCTYP]/[CIMTYP]/[RELNO]">       <EDIDC_FIELD1>value1</ EDIDC_FIELD1>       <EDIDC_FIELD2>value2</ EDIDC_FIELD2>       …     </EDI_DC40>     <[SEGMENT_DEFN]_1>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_1>     <[SEGMENT_DEFN]_2>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_2>     …     </[EDI_DC40/EDI_DC]>   </idocData>   <guid>guid</guid> </Send>` |                                               厳密に型指定された IDOC を SAP に送信します。<br /><br /> の IDOC スキーマは、厳密に型指定します。<br /><br /> -公開では、レコードのフィールドを制御します。<br /><br /> -セグメント ヘッダーとセグメント フィールドを含むデータ レコードのフィールドを公開します。<br /><br /> [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP トランザクション ID (TID) IDOC を送信するために使用する GUID を関連付けます。 要求メッセージ内での GUID を指定するかどうかを選択できます。 GUID は、要求メッセージに含まれていない場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]いずれかが生成されます。 GUID は、応答メッセージで返されます。                                                |
|   応答を送信します。   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         `<SendResponse xmlns="[MSG_VERSION]/Idoc/[VERSION]/         [IDOCTYP]/[CIMTYP]/[RELNO]/Send">   <guid>guid</guid> </SendResponse>`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | IDOC が SAP システムに送信されたことを示します。<br /><br /> 場合、 **AutoConfirmSentIdocs**プロパティのバインドは**true**、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムでトランザクションを自動的に確認し、応答で返される GUID を無視できます。 場合、 **AutoConfirmSentIdocs**プロパティのバインドは**false**、呼び出す必要があります、 **RfcConfirmTransID**によって返される GUID を持つ操作、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]にSAP システムでトランザクションを完了します。<br /><br /> 呼び出すことができます、 **SapAdapterUtilities.ConvertGuidToTid**作業 (LUW) の論理ユニットに関連付けられている TID を取得します。 |
|     SendIdoc      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    `<SendIdoc xmlns="[MSG_VERSION]/Idoc">   <idocData>docDataString</idocData>   <guid>guid</guid> </SendIdoc>`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                                                                   厳密に型指定の IDOC を SAP に送信します。<br /><br /> の IDOC スキーマは、厳密に型指定します。<br /><br /> -制御レコードとレコードのデータで構成される 1 つの文字列フィールドとして、IDOC を公開します。<br /><br /> [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] IDOC を送信するために使用する SAP TID は GUID に関連付けます。 要求メッセージ内での GUID を指定するかどうかを選択できます。 GUID は、要求メッセージに含まれていない場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]いずれかが生成されます。 応答メッセージの GUID が返されます                                                                    |
| SendIdoc 応答 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              `<SendIdocResponse xmlns="[MSG_VERSION]/Idoc">   <guid>guid</guid> </SendIdocResponse>`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |             IDOC が SAP システムに送信されたことを示します。<br /><br /> 場合、 **AutoConfirmSentIdocs**プロパティのバインドは**true**、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムでトランザクションを自動的に確認し、応答で返される GUID を無視できます。 場合、 **AutoConfirmSentIdocs**プロパティのバインドは**false**、呼び出す必要があります、 **RfcConfirmTransID**によって返される GUID を持つ操作、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]にSAP システムでトランザクションを完了します。<br /><br /> 呼び出すことができます、 **SapAdapterUtilities.ConvertGuidToTid** LUW に関連付けられている TID を取得します。             |

 [MSG_VERSION] = メッセージ バージョン文字列。たとえば、 http://Microsoft.LobServices.Sap/2007/03 します。  

 [バージョン] = IDOC のリリース バージョン (2 または 3)。  

 [IDOCTYP] = IDOC の種類。たとえば、ORDERS05 です。  

 [CIMTYP]、カスタマイズされた IDOC の Cimtype を = です。  

 [RELNO]; のリリース番号を =たとえば、620 です。  

 [EDI_DC40/EDI_DC] = リリース用に EDI_DC40 の Idoc のバージョン 3 およびの EDI_DC version2 Idoc をリリースします。  

 [EDIDC_FIELD] EDI_DC40/EDI_DC 制御レコードの構造を構成するフィールドを = です。  

 [SEGMENT_DEFN] = セグメントの定義名 (セグメントの種類名ではなく)。たとえば、E2EDK01005 です。 セグメントの定義のノードでした セグメント グループ ノードでは、表示されることも、IDOC の構造に基づいています。  

 [DATAHEADERCOLUMN_(SEGHDR_FLD)] = 各セグメントには、標準的な一連のヘッダー フィールドによって、セグメント データで構成されるセグメント ヘッダーを取得します。 セグメントのデータは、すべてのセグメント フィールドとデータで構成されます。 このノードが表すセグメント ヘッダー フィールド。たとえば、DATAHEADERCOLUMN_SEGNAM です。  

 [SEG_FIELD] 特定のセグメントの定義 [SEGMENT_DEFN] を構成するセグメント フィールド名を = です。  

 [guid] = GUID パラメーター。  

### <a name="message-actions-for-idoc-client-operations"></a>IDOC のクライアント操作のメッセージのアクション  
 次の表では、送信と SendIdoc の操作のためのメッセージのアクションを示します。  


|     演算     |                                   操作                                   |                                   例                                   |
|-------------------|----------------------------------------------------------------------------|-----------------------------------------------------------------------------|
|       Send        |     [MESSAGE_VERSION]/Idoc/[バージョン]/[IDOCTYP]/[CIMTYP]/[RELNO]/[送信]      |     http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Send      |
|   応答を送信します。   | [MESSAGE_VERSION]/Idoc/[バージョン]/[IDOCTYP]/[CIMTYP]/[RELNO]/送信/応答 | http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Send/response |
|     SendIdoc      |                      [MESSAGE_VERSION]/Idoc SendIdoc                       |           http://Microsoft.LobServices.Sap/2007/03/Idoc/SendIdoc            |
| SendIdoc 応答 |                  [MESSAGE_VERSION]/Idoc/SendIdoc/応答                  |       http://Microsoft.LobServices.Sap/2007/03/Idoc/SendIdoc/response       |

 [MESSAGE_VERSION] = メッセージ バージョン文字列。たとえば、 http://Microsoft.LobServices.Sap/2007/03します。  

 [バージョン] = IDOC のリリース バージョン (2 または 3)。  

 [IDOCTYP] = IDOC の種類。たとえば、ORDERS05 です。  

 [CIMTYP]、カスタマイズされた IDOC の Cimtype を = です。  

 [RELNO]; のリリース番号を =たとえば、620 です。  

## <a name="operations-to-receive-idocs"></a>Idoc を受信する操作  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムから Idoc を受信するアプリケーションの受信および ReceiveIdoc の操作を公開します。 受信操作では、IDOC は厳密に型指定されたデータとして表されます。ReceiveIdoc 操作の場合は、IDOC は文字列データとして表されます。  

 これらの操作では、アダプターによって、アプリケーションに IDOC データを生成する方法を決定します。 アダプターは常に、IDOC_INBOUND_ASYNCHRONOUS または IDOC_INBOUND_PROCESS tRFC として、SAP システムから Idoc を受け取ります。 受信パイプラインまたは ReceiveIdoc の操作を使用するかまたは RFC 形式で IDOC データを受信することができます。 設定する、 **ReceiveIdocFormat**は、アダプターは、アプリケーションに IDOC データ出力形式を指定するプロパティをバインドします。 詳細については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインドのプロパティを参照してください[mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。  

### <a name="message-structures-for-idoc-receive-operations"></a>メッセージの構造体の IDOC の受信操作  
 次の表は、受信および ReceiveIdoc 操作のメッセージの構造を示します。  

|演算|XML の構造体|説明|  
|---------------|-------------------|-----------------|  
|Receive|`<Receive xmlns="[MSG_VERSION]/Idoc/[VERSION]/[IDOCTYP]/                 [CIMTYP]/[RELNO]/Receive">   <idocData>     <[EDI_DC40/EDI_DC] xmlns="/Types/Idoc/      [VERSION]/[IDOCTYP]/[CIMTYP]/[RELNO]">       <EDIDC_FIELD1>value1</ EDIDC_FIELD1>       <EDIDC_FIELD2>value2</ EDIDC_FIELD2>       …     </EDI_DC40>     <[SEGMENT_DEFN]_1>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_1>     <[SEGMENT_DEFN]_2>       <[DATAHEADERCOLUMN_[SEGHDR_FLD1]>         header_value_1       </[DATAHEADERCOLUMN_[SEGHDR_FLD1]>       <[DATAHEADERCOLUMN_[SEGHDR_FLD2]>         header_value_2       </[DATAHEADERCOLUMN_[SEGHDR_FLD2]>       …       <SEG_FIELD1>value1</SEG_FIELD1>       <SEG_FIELD2>value2</SEG_FIELD2>       …     </[SEGMENT_DEFN]_2>     …     </[EDI_DC40/EDI_DC]>   </idocData> </Receive>`|厳密に型指定された IDOC を SAP から受信します。<br /><br /> の IDOC スキーマは、厳密に型指定します。<br /><br /> -公開では、レコードのフィールドを制御します。<br /><br /> -セグメント ヘッダーとセグメント フィールドを含むデータ レコードのフィールドを公開します。|  
|応答を受信します。|`<ReceiveResponse xmlns="[MSG_VERSION]/Idoc/[VERSION]/[IDOCTYP]/         [CIMTYP]/[RELNO]/Receive"> </ReceiveResponse>`|IDOC が SAP システムから受信されたことを示します。|  
|ReceiveIdoc|`<ReceiveIdoc xmlns="[MSG_VERSION]/Idoc">   <idocData>docDataString</idocData> </ReceiveIdoc>`|厳密に型指定の IDOC を SAP から受信します。<br /><br /> の IDOC スキーマは、厳密に型指定します。<br /><br /> -制御レコードとレコードのデータで構成される 1 つの文字列フィールドとして、IDOC を公開します。|  
|ReceiveIdoc 応答|`<ReceiveIdocResponse xmlns="[MSG_VERSION]/Idoc"> </ReceiveIdocResponse>`|IDOC が SAP システムから受信されたことを示します。|  

 [MSG_VERSION] = メッセージ バージョン文字列。たとえば、 http://Microsoft.LobServices.Sap/2007/03 します。  

 [バージョン] = IDOC のリリース バージョン (2 または 3)。  

 [IDOCTYP] = IDOC の種類。たとえば、ORDERS05 です。  

 [CIMTYP]、カスタマイズされた IDOC の Cimtype を = です。  

 [RELNO]; のリリース番号を =たとえば、620 です。  

 [EDI_DC40/EDI_DC] = リリース用に EDI_DC40 の Idoc のバージョン 3 および EDI_DC の Idoc のバージョン 2 をリリースします。  

 [EDIDC_FIELD] EDI_DC40/EDI_DC 制御レコードの構造を構成するフィールドを = です。  

 [SEGMENT_DEFN] = セグメントの定義名 (セグメントの種類名ではなく)。たとえば、E2EDK01005 です。 セグメントの定義のノードは、IDOC の構造に基づいて、セグメント グループ ノードも表示できます。  

 [DATAHEADERCOLUMN_(SEGHDR_FLD)] = 各セグメントには、標準的な一連のヘッダー フィールドによって、セグメント データで構成されるセグメント ヘッダーを取得します。 セグメントのデータは、すべてのセグメント フィールドとデータで構成されます。 このノードが表すセグメント ヘッダー フィールド。たとえば、DATAHEADERCOLUMN_SEGNAM です。  

 [SEG_FIELD] 特定のセグメントの定義 [SEGMENT_DEFN] を構成するセグメント フィールド名を = です。  

#### <a name="receiving-an-idoc-in-rfc-format"></a>RFC 形式で IDOC を受信  
 RFC 形式で Idoc を受信できます。 Idoc を SAP から受信するために使用する Rfc は次のとおりです。  

- Idoc のバージョン 3 の IDOC_INBOUND_ASYNCHRONOUS します。  

- Idoc のバージョン 2 の INBOUND_IDOC_PROCESS します。  

  次のコードでは、IDOC_INBOUND_ASYNCHRONOUS 操作として受信した IDOC の構造を示します。  

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

 [SEG_HEADER_FIELD] = 各セグメントには、標準的な一連のヘッダー フィールドによって、セグメント データで構成されるセグメント ヘッダーを取得します。 セグメントのデータは、すべてのセグメント フィールドとデータで構成されます。 このノードが表すセグメント ヘッダー フィールド。たとえば、SEGNAM、MANDT、および DOCNUM にします。  

 TRFC 操作の詳細形式の詳細については、次を参照してください。 [tRFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)します。  

### <a name="message-actions-for-idoc-receive-operations"></a>メッセージのアクションの IDOC の受信操作  
 次の表では、受信と ReceiveIdoc の操作のためのメッセージのアクションを示します。  


|      演算       |                                    操作                                     |                                    例                                     |
|----------------------|-------------------------------------------------------------------------------|--------------------------------------------------------------------------------|
|       Receive        |     [MESSAGE_VERSION]/Idoc/[バージョン]/[IDOCTYP]/[CIMTYP]/[RELNO]/受信      |     http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Receive      |
|   応答を受信します。   | [MESSAGE_VERSION]/Idoc/[バージョン]/[IDOCTYP]/[CIMTYP]/[RELNO]/受信/応答 | http://Microsoft.LobServices.Sap/2007/03/Idoc/3/ORDERS05//620/Receive/response |
|     ReceiveIdoc      |                      [MESSAGE_VERSION]/Idoc ReceiveIdoc                       |           http://Microsoft.LobServices.Sap/2007/03/Idoc/ReceiveIdoc            |
| ReceiveIdoc 応答 |                  [MESSAGE_VERSION]/Idoc/ReceiveIdoc/応答                  |       http://Microsoft.LobServices.Sap/2007/03/Idoc/ReceiveIdoc/response       |

