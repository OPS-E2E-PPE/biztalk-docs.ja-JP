---
title: SAP アダプターの SAPParameter クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPParameter, supported methods, classes, and constructors
ms.assetid: 60053393-ad22-4c99-abae-e538d43c8e18
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67f87932d7add9723d67e0af822a8d6f389b59fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372942"
---
# <a name="sapparameter-class-in-the-sap-adapter"></a>SAP アダプターの SAPParameter クラス
メソッドおよびプロパティを次のセクションの一覧、 **SAPParameter**クラス。 これは、派生元**System.Data.Common.DbParameter**します。  
  
## <a name="supported-properties"></a>サポートされているプロパティ  
  
|名前|Get/Set|説明|  
|----------|--------------|-----------------|  
|**DbType**|取得|DbType 場合は、パラメーターが返されます。 設定することはできません。|  
|**[方向]**|Get と Set|ParameterDirection.ReturnValue がサポートされていません。|  
|**IsNullable**|-|サポートされていません。|  
|**ParameterName**|Get と Set|パラメーターの名前。|  
|**Size**|-|サポートされていません。|  
|**SourceColumn**|-|サポートされていません。|  
|**SourceColumnNullMapping**|-|サポートされていません。|  
|**SourceVersion**|-|サポートされていません。|  
|**[値]**|Get と Set|パラメーターの値|  
  
## <a name="supported-methods"></a>サポートされているメソッド  
  
|名前|説明|  
|----------|-----------------|  
|**ResetDbType()**|サポートされていません。|  
  
## <a name="supported-constructors"></a>サポートされているコンス トラクター  
  
|名前|説明|  
|----------|-----------------|  
|**SAPParameter()**|SAP パラメーターのインスタンス。|  
|**SAPParameter(string)**|SAP SAP パラメーターの名前のパラメーター。|  
|**SAPParameter(string, DbType)**|SAP パラメーター名と DbType SAP パラメーター。|  
|**SAPParameter (文字列、オブジェクト)**|SAP パラメーター名および値を持つ SAP パラメーター。 複合型は、DataTable の型の値と XML 文字列があります。|  
|**SAPParameter(string, ParameterDirection)**|SAP パラメーターの名前とパラメーターの方向を持つ SAP パラメーター。|  
  
## <a name="see-also"></a>参照  
 [SAP アダプターを使用した ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)