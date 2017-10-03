---
title: "SAP アダプターで SAPParameter クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SAPParameter, supported methods, classes, and constructors
ms.assetid: 60053393-ad22-4c99-abae-e538d43c8e18
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ff43c344cc14adb3deef226c270adc3ca94f2a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sapparameter-class-in-the-sap-adapter"></a>SAP アダプターで SAPParameter クラス
次のセクションではメソッドとプロパティの一覧表示、 **SAPParameter**クラスです。 これは、派生元**System.Data.Common.DbParameter**です。  
  
## <a name="supported-properties"></a>サポートされているプロパティ  
  
|名前|取得/設定|Description|  
|----------|--------------|-----------------|  
|**DbType**|取得|DbType 場合は、パラメーターが返されます。 設定することはできません。|  
|**方向**|Get および Set|ParameterDirection.ReturnValue がサポートされていません。|  
|**IsNullable**|-|サポートされていません。|  
|**パラメーター名**|Get および Set|パラメーターの名前です。|  
|**サイズ**|-|サポートされていません。|  
|**SourceColumn**|-|サポートされていません。|  
|**SourceColumnNullMapping**|-|サポートされていません。|  
|**SourceVersion**|-|サポートされていません。|  
|**値**|Get および Set|パラメーターの値|  
  
## <a name="supported-methods"></a>サポートされているメソッド  
  
|名前|Description|  
|----------|-----------------|  
|**ResetDbType()**|サポートされていません。|  
  
## <a name="supported-constructors"></a>サポートされているコンス トラクター  
  
|名前|Description|  
|----------|-----------------|  
|**SAPParameter()**|SAP パラメーターのインスタンス。|  
|**SAPParameter(string)**|SAP パラメーターの名前を持つ SAP パラメーター。|  
|**SAPParameter (string, DbType)**|SAP パラメーター名と DbType SAP パラメーター。|  
|**SAPParameter (文字列、オブジェクト)**|SAP パラメーター名と値を持つ SAP パラメーター。 複合型では、データ テーブルの型の値と XML 文字列があります。|  
|**SAPParameter (string, ParameterDirection)**|SAP パラメーターの名前とパラメーターの方向と SAP のパラメーターです。|  
  
## <a name="see-also"></a>参照  
 [SAP アダプターと ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)