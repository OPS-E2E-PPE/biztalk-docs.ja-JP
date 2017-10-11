---
title: "BizTalk Adapter Pack での mySAP アダプターのメタデータのノード Id |Microsoft ドキュメント"
description: "メタデータ、検索、取得ノードの種類および mySAP アダプター - BizTalk アダプター パック (BAP) で公開されている SAP コンポーネントで使用される Id"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 46385060-f56a-4e06-9122-b75808776716
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 138e46b198df48348dcef35662589f6a3c2e317a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="node-types-and-ids-for-the-sap-adapter"></a>ノードの種類と SAP アダプターの Id

## <a name="metadata-node-types-and-ids"></a>メタデータのノード型および Id
次の表は、SAP アイテムのノードの ID とノード型を[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]サーフェスします。 ノード ID で使用されているノードの絶対パスである、 **IMetadataRetrievalContractBrowse**、**検索**、および**GetMetadata**メソッドです。  
  
|成果物の表示名|ノードの種類|ノード ID|  
|---------------------------|---------------|-------------|  
|RFC|カテゴリ|[バージョン]/RFCSECTION|  
|[RFC_APPL_GROUP_NAME]|カテゴリ|[バージョン]/RFCGROUP/[RFC_APPL_GROUP_ID]|  
|[RFC_NAME]|OPERATION|[バージョン]/Rfc/[RFC_NAME]|  
|RfcGetAttributes|OPERATION|[バージョン]/RfcApi RfcGetAttributes|  
|TRFC|カテゴリ|[バージョン]/TRFCSECTION|  
|[TRFC_APPL_GROUP_NAME]|カテゴリ|[バージョン]/TRFCGROUP/[TRFC_APPL_GROUP_ID]|  
|[TRFC_NAME]|OPERATION|[バージョン]/TRfc/[TRFC_NAME]|  
|RfcConfirmTransID|OPERATION|[バージョン]/RfcApi RfcConfirmTransID|  
|BAPI|カテゴリ|[バージョン] BAPISECTION/000001|  
|[BAPI_APPL_GROUP_NAME]|カテゴリ|[バージョン]/BAPISECTION/[BAPI_APPL_GROUP_NODE_ID]|  
|[BUSINESS_OBJECT_NAME]|カテゴリ|[バージョン]/BAPIOBJ/[BUSOBJ_TYPE]|  
|[BUSINESS_OBJECT_METHOD]|OPERATION|[バージョン]/BAPIOBJ/[BUSOBJ_TYPE]/[BUSOBJ_METHOD]/[FUNCTION_MODULE]|  
|IDOC|カテゴリ|[バージョン]/IDOCSECTION|  
|[IDOC_MSG_TYPE_NAME]|カテゴリ|[バージョン]/IDOCMESTYP/[IDOC_MSG_TYPE_NAME]|  
|([IDOC_TYPE_NAME])([IDOC_CIMTYPE])|カテゴリ|[バージョン]/IDOCCIMTYP/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[FIRST_IDOC_REL_NO]|  
|([IDOC_TYPE_NAME] です。V[IDOC_VERSION]) ([IDOC_CIMTYPE]) ([IDOC_REL_NO])|カテゴリ|[バージョン]/IDOCCIMVER/[IDOC_VERSION]/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[IDOC_REL_NO]|  
|Send|OPERATION|[バージョン]/Idoc/[IDOC_VERSION]/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[IDOC_REL_NO]/[送信]|  
|SendIdoc|OPERATION|[バージョン]/Idoc SendIdoc|  
|Receive|OPERATION|[バージョン]/Idoc/[IDOC_VERSION]/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[IDOC_REL_NO]/受信|  
|ReceiveIdoc|OPERATION|[バージョン]/Idoc ReceiveIdoc|  
  
 [バージョン] = バージョン文字列です。たとえば、http://Microsoft.LobServices.Sap/2007/03 です。  
  
 [RFC_APPL_GROUP_NAME]、アプリケーション グループの名前を =たとえば、Sales です。  
  
 [RFC_APPL_GROUP_ ID] SAP; のアプリケーション グループに関連付けられている ID を =たとえば、V (売上) です。  
  
 [RFC_NAME] RFC; の名前を =たとえば、RFC_GET_SYSTEM_INFO です。  
  
 [TRFC_APPL_GROUP_NAME]、アプリケーション グループの名前を =たとえば、Sales です。 これは、Rfc のアプリケーション グループと同じです。  
  
 [TRFC_APPL_GROUP_ ID] SAP; のアプリケーション グループに関連付けられている ID を =たとえば、V (売上) です。 これは、Rfc の ID と同じです。  
  
 [TRFC_NAME]、tRFC; の名前を =たとえば、RFC_GET_SYSTEM_INFO です。 これは、RFC 名と同じです。  
  
 [BAPI_APPL_GROUP_NAME] SAP の BAPI エクスプ ローラーと同様に、BAPI グループの名前を = です。 たとえば、販売および配布します。  
  
 [BAPI_APPL_GROUP_NODE_ID] SAP; での BAPI のエクスプ ローラー ツリーで、対応するノードに関連付けられている ID を =たとえば、販売および配布 3253 です。 指定された BAPI グループ ノードの下に複数のグループ ノードが存在することに注意してください。 販売および配布など、ノードが別のグループ ノード下にある Sales (ノード ID 3375) と呼ばれることです。  
  
 [BUSINESS_OBJECT_NAME]; ビジネス オブジェクトの名前を =たとえば、Sales Order です。  
  
 [BUSOBJ_TYPE] SAP; でビジネス オブジェクトの種類を =たとえば、販売注文のビジネス オブジェクトの BUS2032 します。  
  
 [BUSINESS_OBJECT_METHOD]、ビジネス オブジェクトのメソッドの名前を =たとえば、販売注文のビジネス オブジェクトの GETLIST します。  
  
 [関数モジュール]、ビジネス オブジェクトのメソッドの SAP 関数モジュールを =たとえば、BAPI_SALESORDER_GETLIST GETLIST メソッドの販売注文のビジネス オブジェクトの。  
  
 [IDOC_MSG_TYPE_NAME] の IDOC メッセージの種類の名前を =たとえば、注文します。  
  
 [IDOC_TYPE_NAME] IDOC の種類の名前を =たとえば、ORDERS05 です。  
  
 [IDOC_CIMTYPE] = IDOC CIM 型 (拡張子) です。たとえば、Z1ORDERS です。  
  
 [FIRST_IDOC_REL_NO]、特定の IDOC 型の最小の IDOC リリース番号を =たとえば、特定の SAP システム内の ORDERS05 46A です。  
  
 [IDOC_VERSION] = IDOC のリリース バージョン番号です。2 をリリースの IDOC の 2 および 3 をリリースの IDOC の 3.  
  
 [IDOC_REL_NO] = IDOC のリリース番号です。たとえば 46A、46B、または 620 にします。  
  
## <a name="metadata-search-node-ids"></a>ノード Id でメタデータの検索  
 メタデータの検索では、高度な機能、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]サーフェスの一部としてその**IMetadataRetrievalContract**インターフェイスです。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次の SAP アイテムの検索をサポートするためにこの機能を使用します。  
  
|成果物の表示名|ノード ID|Description|  
|---------------------------|-------------|-----------------|  
|/RFC|[バージョン]/RFCSECTION|検索式に一致するすべての RFC 操作を返します。|  
|/RFC/[RFC_APPL_GROUP_NAME]|[バージョン]/RFCGROUP/[RFC_APPL_GROUP_NAME]|検索式に一致するアプリケーション グループの RFC 操作を返します。|  
|/TRFC|[バージョン]/TRFCSECTION|検索式に一致するすべての RFC 操作を返します。|  
|/TRFC/[TRFC_APPL_GROUP_NAME]|[バージョン]/TRFCGROUP/[TRFC_APPL_GROUP_NAME]|検索式に一致するアプリケーション グループの RFC 操作を返します。|  
|/BAPI|[バージョン]/BAPISECTION|検索式に一致するすべての Bapi を返します。|  
|/IDOC|[バージョン]/IDOCSECTION|検索式に一致するすべての Idoc を返します。|  
  
 次の表のワイルドカード文字を[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]検索式でサポートしています。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|プラス (+)|1 文字と一致します。<br /><br /> たとえば、A + 一致 AB、AC、AD などです。|  
|アスタリスク (*)|0 個以上の文字と一致します。たとえば、「A *」と一致"A"、"AB"、"ABC"、およびなどです。|  
  
## <a name="metadata-retrieval-node-ids"></a>メタデータの取得のノード Id  
 次の表に、によって返されるメタデータ特性[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
|成果物|メタデータの特性|  
|--------------|------------------------------|  
|RFC|RFC の名前です。<br />RFC のインポート、エクスポート、変更、およびテーブルのパラメーターです。<br />RFC パラメーターのデータ型。<br />ファセットの maxlength プロパティにマップされている RFC パラメーター フィールド長<br />ファセットの minOccurs にマップされている RFC 必須パラメーター 1 を =<br />-ファセットの minOccurs にマップされている RFC 省略可能なパラメーター 0 を =<br />RFC パラメーター ファセット isNillable にマップされている NULL 制約 = true です。 これは、アダプターが SAP システムへでこのパラメーターを渡す必要がありますいないことを意味します。<br />-RFC 自体は、操作です。|  
|TRFC|除く RFC と同じ<br /><br /> RFC インポートのパラメーターは表示されません。 TRFC は非同期なので、出力パラメーターは発生しません。|  
|BAPI|ビジネス オブジェクトの名前<br />ビジネス オブジェクト メソッドの名前<br />-RFC 特性と同じ|  
|IDOC|IDOC の種類<br /><br /> CIMType<br /><br /> IDOC のリリース番号<br /><br /> IDOC のバージョン<br /><br /> IDOC EDI_DC 複合型にマップされている制御レコードのフィールド<br /><br /> IDOC データ レコードのセグメントと EDI_DD 複合型にマップされているセグメント フィールド<br /><br /> セグメントの親子関係<br /><br /> IDOC セグメントの必須パラメーターが minOccurs にマップされている 1 を =<br /><br /> IDOC セグメントの minOccurs にマップされている省略可能なパラメーター 0 を =<br /><br /> IDOC セグメントのヘッダー フィールドの名前<br /><br /> IDOC セグメント ヘッダー フィールドのデータ型<br /><br /> IDOC セグメント フィールド名<br /><br /> IDOC セグメント フィールドのデータ型<br /><br /> IDOC セグメント フィールド値の列挙<br /><br /> IDOC セグメント フィールドの最小、最大値 (範囲)**注:**ときの IDOC セグメント フィールドには最小値の一覧が含まれています、列挙体として提示されます。 IDOC セグメント フィールドには、min と max の値の両方が含まれている場合に、列挙型または範囲の構造なしの文字列として確認できます。|  
  
 詳細については、形式のメタデータを[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]特定のアイテムおよび操作で、SAP システムに公開を参照してください[メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)です。  
  
