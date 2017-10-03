---
title: "SAP アダプターで SAPDataReader クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SAPDataReader, supported methods and classes
ms.assetid: bd0e55ea-7413-498f-851f-ed97bd8bacab
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70fe658058b6d00b4a22b333ef5683a285b9cab3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sapdatareader-class-in-the-sap-adapter"></a>SAP アダプターで SAPDataReader クラス
次のセクションではメソッドとプロパティの一覧表示、 **SAPDataReader**クラスです。 これは、派生元**System.Data.Common.DbDataReader**です。  
  
## <a name="supported-properties"></a>サポートされているプロパティ  
  
|名前|取得/設定|Description|  
|----------|--------------|-----------------|  
|**[奥行]**|取得|サポートされていません。 0 を返します。|  
|**FieldCount**|取得|現在のレコード セット内のフィールドの数|  
|**IsClosed**|取得|データ リーダーの状態を返します|  
|**RecordsAffected**|取得|サポートされていません。 -1 を返します|  
  
## <a name="supported-methods"></a>サポートされているメソッド  
  
|名前|Description|  
|----------|-----------------|  
|**Close()**|DataReader を終了します。|  
|**Get [メソッド]**<sup>*</sup><br /><br /> ここで [メソッド] は、予想されるデータ型です。 例: GetInt32(int)|予期されるデータ型に基づいて列の値を取得します。|  
|**IsDBNull(int)**|サポートされていません。 False を返します。|  
  
## <a name="see-also"></a>参照  
 [SAP アダプターと ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)