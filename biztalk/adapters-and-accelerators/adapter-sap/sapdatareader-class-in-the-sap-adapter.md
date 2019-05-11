---
title: SAP アダプターの SAPDataReader クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPDataReader, supported methods and classes
ms.assetid: bd0e55ea-7413-498f-851f-ed97bd8bacab
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f05550dea2c42d8227e0c135759eea24238c0e4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372956"
---
# <a name="sapdatareader-class-in-the-sap-adapter"></a>SAP アダプターの SAPDataReader クラス
メソッドおよびプロパティを次のセクションの一覧、 **SAPDataReader**クラス。 これは、派生元**System.Data.Common.DbDataReader**します。  
  
## <a name="supported-properties"></a>サポートされているプロパティ  
  
|名前|Get/Set|説明|  
|----------|--------------|-----------------|  
|**[奥行]**|取得|サポートされていません。 0 を返します。|  
|**FieldCount**|取得|現在のレコード セット内のフィールドの数|  
|**IsClosed**|取得|データ リーダーの状態を返します|  
|**RecordsAffected**|取得|サポートされていません。 -1 を返します。|  
  
## <a name="supported-methods"></a>サポートされているメソッド  
  
|名前|説明|  
|----------|-----------------|  
|**Close()**|DataReader を閉じる|  
|**Get [メソッド]** <sup>*</sup><br /><br /> 場所 [メソッド] は、必要なデータ型です。 例: GetInt32(int)|必要なデータ型に基づいて列の値を取得します。|  
|**IsDBNull(int)**|サポートされていません。 False を返します。|  
  
## <a name="see-also"></a>参照  
 [SAP アダプターを使用した ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)