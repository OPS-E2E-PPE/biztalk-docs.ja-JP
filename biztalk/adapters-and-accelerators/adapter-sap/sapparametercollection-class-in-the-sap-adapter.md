---
title: SAP アダプターで SAPParameterCollection クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPParameterCollection, supported methods and classes
ms.assetid: fd09355b-95f4-4d49-a643-b13058e63d74
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 924cb884c64f337cec0e628c804b5c5a8c6cf37b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sapparametercollection-class-in-the-sap-adapter"></a>SAP アダプターで SAPParameterCollection クラス
次のセクションではメソッドとプロパティの一覧表示、 **SAPParameterCollection**クラスです。 これは、派生元**System.Data.Common.DbParameterCollection**です。  
  
## <a name="supported-properties"></a>サポートされているプロパティ  
  
|名前|取得/設定|Description|  
|----------|--------------|-----------------|  
|**Count**|取得|コレクション内のパラメーターの数。|  
|**IsFixedSize**|取得|サポートされていません。 False を返します。|  
|**IsReadOnly**|取得|サポートされていません。 False を返します。|  
|**IsSynchronized**|取得|サポートされていません。 False を返します。|  
|**SyncRoot**|取得|ロック オブジェクトを返します。|  
  
## <a name="supported-methods"></a>サポートされているメソッド  
  
|名前|Description|  
|----------|-----------------|  
|**Add(SAPParameter)**|パラメーターは、1 つ以上の ParameterCollection に属することはできません。|  
|**してください。**|オブジェクトは、SAPParameter 型でなければなりません。|  
|**AddRange(System.Array)**|SAPParameter インスタンスの配列を追加します。|  
|**Clear()**|コレクション内のパラメーターを消去します。|  
|**Contains(object)**|パラメーターのインスタンスに基づいてチェックします。|  
|**Contains(string)**|パラメーター名に基づいたチェックします。|  
|**CopyTo (SAPParameter, int)**|SAPParameter 型の配列にパラメーター リストをコピーします。|  
|**CopyTo (System.Array、int)**|配列にパラメーター リストをコピーします。|  
|**GetEnumerator()**|パラメーターのコレクションの列挙子を取得します。|  
|**IndexOf(object)**|SAPParameter インスタンスに基づいて、パラメーターのインデックス。|  
|**IndexOf(string)**|SAPParameter 名に基づくパラメーターのインデックス。|  
|**挿入 (int, object)**|コレクションに、SAPParameter を挿入します。|  
|**Remove(object)**|インスタンスに基づくコレクションに、SAPParameter を削除します。|  
|**RemoveAt(int)**|コレクション内の指定したインデックス位置に、SAPParameter を削除します。|  
|**RemoveAt(string)**|名前に基づくコレクションに、SAPParameter を削除します。|  
  
## <a name="see-also"></a>参照  
 [SAP アダプターと ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)