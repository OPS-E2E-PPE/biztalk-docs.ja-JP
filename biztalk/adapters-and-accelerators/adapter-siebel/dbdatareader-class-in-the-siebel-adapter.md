---
title: "Siebel アダプターの DbDataReader クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, DbDataReader
- DbDataReader
ms.assetid: 7673cd10-ec1e-4cb0-93c2-f11928d00ca2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00fc3329cbe4dc75a4eccd5b71ded45ad6ebfe63
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="dbdatareader-class-in-the-siebel-adapter"></a>Siebel アダプターの DbDataReader クラス
[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]提供、 `DbDataReader` XML データ リーダーを活用することです。 これは、Siebel データ ソースのコンシューマーの行の順方向専用ストリームを読み取る機能を提供します。  
  
## <a name="supported-properties"></a>サポートされているプロパティ  
 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]次のサポート`DbDataReader`プロパティです。  
  
|名前|取得/設定|Description|  
|----------|--------------|-----------------|  
|**HasRows**|取得|このプロパティはサポートされていません、アクセスする場合、例外がスローされます。|  
|**IsClosed**|取得|示す値を取得するかどうか、`DbDataReader`が閉じられます。|  
|**RecordsAffected**|取得|示す値を取得するかどうか、 `DbDataReader` 1 つまたは複数の行が含まれています。|  
|**Item(Int32)**|取得|オブジェクトのインスタンスとして指定された列の値を取得します。 このインデクサーを呼び出すときに、必要な列の序数を使用します。|  
|**Item(String)**|取得|オブジェクトのインスタンスとして指定された列の値を取得します。 このインデクサーを呼び出すときに、必要な列の名前を使用します。|  
  
## <a name="supported-methods"></a>サポートされているメソッド  
 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]次のサポート`DbDataReader`メソッドです。  
  
|名前|Description|  
|----------|-----------------|  
|**GetSchemaTable**|`DbDataReader` の列メタデータを表す `DataTable` を返します。 サポートされているスキーマの列属性、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]は。<br /><br /> -ColumnName<br />-ColumnOrdinal<br />.NET データ型<br />長<br />単精度 (使用可能な場合)<br />-小数点以下桁数 (使用可能な場合)<br />-AllowDBNull<br />-LocalName<br />-拡張 LocalName<br />-Namespace|  
|**GetString**|指定した列の値を `String` のインスタンスとして取得します。|  
|**GetValue**|指定した列の値を `String` のインスタンスとして取得します。|  
|**データ型**|列に存在しないか、不足している値が含まれるかどうかを示す値を取得します。|  
|**NextResult**|Siebel データ プロバイダーは、常に、1 つの結果セットを返しますこの呼び出しが完全に現在の結果を返す前にセットを過ぎるため**false**です。|  
|**読み取り**|リーダーを結果セットの次のレコードに進めます。  返します**true**成功した場合と**false**場合は、リーダーは、レコードを左にします。|  
|**[閉じる]**|閉じる、`DbDataReader`オブジェクト。 **注意:**したらを使用して、`DbDataReader`オブジェクト、Siebel COM ライブラリ オブジェクトを解放するために、それを閉じる必要があります。 それ以外の場合、クライアント アプリケーションのメモリとハンドルの使用率が上がるです。|  
  
## <a name="see-also"></a>参照  
 [Siebel アダプターと ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)