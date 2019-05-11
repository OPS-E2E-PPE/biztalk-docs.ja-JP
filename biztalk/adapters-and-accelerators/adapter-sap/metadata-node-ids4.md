---
title: BizTalk Adapter Pack での mySAP アダプター メタデータのノード Id |Microsoft Docs
description: メタデータ、検索、取得のタイプのノードと mySAP アダプターの BizTalk アダプター パック (BAP) で公開されている SAP コンポーネントで使用される Id
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46385060-f56a-4e06-9122-b75808776716
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9efcb2a3fd48f1a92d27314c73dfe684e87b37aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373198"
---
# <a name="node-types-and-ids-for-the-sap-adapter"></a>ノードの種類と SAP アダプターの Id

## <a name="metadata-node-types-and-ids"></a>メタデータのノードの種類と Id
次の表は、ノードの種類と SAP アイテム用のノード ID を[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]サーフェス。 ノード ID で使用されているノードの絶対パス、 **IMetadataRetrievalContractBrowse**、**検索**、および**GetMetadata**メソッド。  
  
|成果物の表示名|ノードの種類|ノード ID|  
|---------------------------|---------------|-------------|  
|RFC|カテゴリ|[バージョン]/RFCSECTION|  
|[RFC_APPL_GROUP_NAME]|カテゴリ|[VERSION]/RFCGROUP/[RFC_APPL_GROUP_ID]|  
|[RFC_NAME]|操作|[VERSION]/Rfc/[RFC_NAME]|  
|RfcGetAttributes|操作|[バージョン]/RfcApi RfcGetAttributes|  
|TRFC|カテゴリ|[バージョン]/TRFCSECTION|  
|[TRFC_APPL_GROUP_NAME]|カテゴリ|[VERSION]/TRFCGROUP/[TRFC_APPL_GROUP_ID]|  
|[TRFC_NAME]|操作|[VERSION]/TRfc/[TRFC_NAME]|  
|RfcConfirmTransID|操作|[バージョン]/RfcApi RfcConfirmTransID|  
|BAPI|カテゴリ|[バージョン] BAPISECTION/000001|  
|[BAPI_APPL_GROUP_NAME]|カテゴリ|[バージョン]/BAPISECTION/[BAPI_APPL_GROUP_NODE_ID]|  
|[BUSINESS_OBJECT_NAME]|カテゴリ|[バージョン]/BAPIOBJ/[BUSOBJ_TYPE]|  
|[BUSINESS_OBJECT_METHOD]|操作|[バージョン]/BAPIOBJ/[BUSOBJ_TYPE]/[BUSOBJ_METHOD]/[FUNCTION_MODULE]|  
|IDOC|カテゴリ|[バージョン]/IDOCSECTION|  
|[IDOC_MSG_TYPE_NAME]|カテゴリ|[VERSION]/IDOCMESTYP/[IDOC_MSG_TYPE_NAME]|  
|([IDOC_TYPE_NAME]) ([IDOC_CIMTYPE])|カテゴリ|[バージョン]/IDOCCIMTYP/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[FIRST_IDOC_REL_NO]|  
|([IDOC_TYPE_NAME].V[IDOC_VERSION]) ([IDOC_CIMTYPE]) ([IDOC_REL_NO])|カテゴリ|[バージョン]/IDOCCIMVER/[IDOC_VERSION]/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[IDOC_REL_NO]|  
|Send|操作|[バージョン]/Idoc/[IDOC_VERSION]/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[IDOC_REL_NO]/[送信]|  
|SendIdoc|操作|[VERSION]/Idoc/SendIdoc|  
|Receive|操作|[バージョン]/Idoc/[IDOC_VERSION]/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[IDOC_REL_NO]/受信|  
|ReceiveIdoc|操作|[VERSION]/Idoc/ReceiveIdoc|  
  
 [バージョン] = バージョン文字列です。たとえば、 http://Microsoft.LobServices.Sap/2007/03 です。  
  
 [RFC_APPL_GROUP_NAME]; アプリケーション グループの名前を =たとえば、Sales です。  
  
 [RFC_APPL_GROUP_ ID] SAP; でアプリケーション グループに関連付けられている ID を =たとえば、V (Sales) です。  
  
 [RFC_NAME] RFC; の名前を =たとえば、RFC_GET_SYSTEM_INFO です。  
  
 [TRFC_APPL_GROUP_NAME]; アプリケーション グループの名前を =たとえば、Sales です。 これは、Rfc にアプリケーション グループの同じです。  
  
 [TRFC_APPL_GROUP_ ID] SAP; でアプリケーション グループに関連付けられている ID を =たとえば、V (Sales) です。 これは、Rfc の ID と同じです。  
  
 [TRFC_NAME]、tRFC; の名前を =たとえば、RFC_GET_SYSTEM_INFO です。 これは、RFC 名と同じです。  
  
 [BAPI_APPL_GROUP_NAME] = SAP の BAPI エクスプ ローラーのように、BAPI グループの名前。 たとえば、販売および配布できます。  
  
 [BAPI_APPL_GROUP_NODE_ID]; SAP の BAPI のエクスプ ローラー ツリーで、対応するノードに関連付けられている ID を =たとえば、Sales and Distribution の 3253 です。 指定された BAPI グループ ノードの下に複数のグループ ノードが存在する可能性がありますに注意してください。 たとえば、Sales and Distribution ノードが Sales (ノード ID 3375) と呼ばれるその下にある別のグループ ノード。  
  
 [BUSINESS_OBJECT_NAME]; ビジネス オブジェクトの名前を =たとえば、Sales Order です。  
  
 [BUSOBJ_TYPE]; sap ビジネス オブジェクトの種類を =たとえば、販売注文のビジネス オブジェクトの BUS2032 します。  
  
 [BUSINESS_OBJECT_METHOD] ビジネス オブジェクト メソッドの名前を =たとえば、販売注文のビジネス オブジェクトの GETLIST します。  
  
 [関数モジュール]、ビジネス オブジェクトのメソッドの SAP 関数モジュールを =たとえば、BAPI_SALESORDER_GETLIST の販売注文のビジネス オブジェクトの GETLIST メソッド。  
  
 [IDOC_MSG_TYPE_NAME]、IDOC メッセージの種類の名前を =たとえば、注文します。  
  
 [IDOC_TYPE_NAME] IDOC の種類の名前を =たとえば、ORDERS05 です。  
  
 [IDOC_CIMTYPE] = IDOC CIM 型 (拡張子) です。たとえば、Z1ORDERS です。  
  
 [FIRST_IDOC_REL_NO]; 特定の IDOC タイプの最小の IDOC リリース数を =たとえば、特定の SAP システム内の ORDERS05 46 a です。  
  
 [IDOC_VERSION] = IDOC のリリース バージョン番号です。2 をリリースの IDOC の 2 および 3 をリリースの IDOC の 3.  
  
 [IDOC_REL_NO] = IDOC のリリース番号です。たとえば 46A、46B、または 620 にします。  
  
## <a name="metadata-search-node-ids"></a>メタデータの検索のノード Id  
 メタデータの検索は、強力な機能、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]サーフェスの一部としてその**IMetadataRetrievalContract**インターフェイス。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次の SAP アイテムの検索をサポートするこの機能を使用します。  
  
|成果物の表示名|ノード ID|説明|  
|---------------------------|-------------|-----------------|  
|/RFC|[バージョン]/RFCSECTION|検索式に一致するすべての RFC 操作を返します。|  
|/RFC/[RFC_APPL_GROUP_NAME]|[VERSION]/RFCGROUP/[RFC_APPL_GROUP_NAME]|検索式に一致するアプリケーション グループでは、RFC 操作を返します。|  
|/TRFC|[バージョン]/TRFCSECTION|検索式に一致するすべての RFC 操作を返します。|  
|/TRFC/[TRFC_APPL_GROUP_NAME]|[VERSION]/TRFCGROUP/[TRFC_APPL_GROUP_NAME]|検索式に一致するアプリケーション グループでは、RFC 操作を返します。|  
|/BAPI|[バージョン]/BAPISECTION|検索式に一致するすべての Bapi を返します。|  
|/IDOC|[バージョン]/IDOCSECTION|検索式に一致するすべての Idoc を返します。|  
  
 次の表のワイルドカード文字を[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]検索式をサポートしています。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|プラス (+)|1 つだけの文字と一致します。<br /><br /> たとえば、A + と一致する AB、AC、AD、これにします。|  
|アスタリスク (*)|0 個以上の文字と一致たとえば、「A *」と一致する"A"、"AB"、"ABC"、およびなど。|  
  
## <a name="metadata-retrieval-node-ids"></a>メタデータの取得のノード Id  
 次の表は、によって返されるメタデータの特性をまとめたものです。[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
|成果物|メタデータの特性|  
|--------------|------------------------------|  
|RFC|RFC の名前。<br />RFC のインポート、エクスポート、変更、およびテーブル パラメーターです。<br />RFC パラメーターのデータ型。<br />RFC パラメーター フィールドの長さが maxLength のファセットにマップされています。<br />ファセットの minOccurs にマップされている RFC 必須パラメーター 1 を =<br />-ファセットの minOccurs にマップされている RFC 省略可能なパラメーター 0 を =<br />RFC パラメーター ファセット isNillable にマップされている NULL 制約 = true。 これは、アダプターがの SAP システムでこのパラメーターを渡す必要がありますいないことを意味します。<br />-RFC 自体は、操作です。|  
|TRFC|RFC を除くと同じ<br /><br /> RFC インポート パラメーターは表示されません。 TRFC は非同期であるために、出力パラメーターは発生しません。|  
|BAPI|-ビジネス オブジェクトの名前<br />-ビジネス オブジェクト メソッドの名前<br />-RFC 特性と同じ|  
|IDOC|IDOC の種類<br /><br /> CIMType<br /><br /> IDOC のリリース番号<br /><br /> IDOC のバージョン<br /><br /> IDOC EDI_DC の複合型にマップされている制御レコードのフィールド<br /><br /> IDOC データ レコードがセグメントとセグメント フィールド EDI_DD の複合型にマップされます。<br /><br /> セグメントの親子関係<br /><br /> IDOC セグメントの必須パラメーターが minOccurs にマップされている 1 を =<br /><br /> IDOC セグメントの minOccurs にマップされている省略可能なパラメーター 0 を =<br /><br /> IDOC セグメント ヘッダー フィールドの名前<br /><br /> IDOC セグメント ヘッダー フィールドのデータ型<br /><br /> IDOC セグメント フィールド名<br /><br /> IDOC セグメント フィールドのデータ型<br /><br /> IDOC セグメント フィールドの値の列挙<br /><br /> IDOC セグメント フィールドの最小、最大値 (範囲)**に注意してください。** IDOC のセグメント フィールドに最小値の一覧が含まれている場合は、列挙体として表示されます。 IDOC セグメントのフィールドに最小値と最大値の両方が含まれる場合は、列挙または範囲構造なしの文字列として表示されます。|  
  
 メタデータの形式に関する詳細情報を[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]特定の成果物と、SAP システムに対する操作の公開を参照してください[メッセージと BizTalk adapter for mySAP Business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)します。  
  
