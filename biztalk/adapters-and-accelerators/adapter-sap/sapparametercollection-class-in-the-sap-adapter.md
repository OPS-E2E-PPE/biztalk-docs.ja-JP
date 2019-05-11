---
title: SAP アダプターの SAPParameterCollection クラス |Microsoft Docs
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
ms.openlocfilehash: c94dc7e8219a2439d58fbfea78fc7fe9c42b64bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372918"
---
# <a name="sapparametercollection-class-in-the-sap-adapter"></a>SAP アダプターの SAPParameterCollection クラス
メソッドおよびプロパティを次のセクションの一覧、 **SAPParameterCollection**クラス。 これは、派生元**System.Data.Common.DbParameterCollection**します。  
  
## <a name="supported-properties"></a>サポートされているプロパティ  
  
|名前|Get/Set|説明|  
|----------|--------------|-----------------|  
|**Count**|取得|コレクション内のパラメーターの数。|  
|**IsFixedSize**|取得|サポートされていません。 False を返します。|  
|**IsReadOnly**|取得|サポートされていません。 False を返します。|  
|**IsSynchronized**|取得|サポートされていません。 False を返します。|  
|**SyncRoot**|取得|ロック オブジェクトを返します。|  
  
## <a name="supported-methods"></a>サポートされているメソッド  
  
|名前|説明|  
|----------|-----------------|  
|**Add(SAPParameter)**|パラメーターは、1 つ以上の ParameterCollection に属することはできません。|  
|**Add(object)**|オブジェクトは、SAPParameter 型である必要があります。|  
|**AddRange(System.Array)**|SAPParameter インスタンスの配列を追加します。|  
|**Clear()**|コレクション内のパラメーターを消去します。|  
|**Contains(object)**|パラメーターのインスタンスを確認します。|  
|**Contains(string)**|パラメーター名に基づいたチェックします。|  
|**CopyTo (SAPParameter, int)**|SAPParameter 型の配列にパラメーター リストをコピーします。|  
|**CopyTo(System.Array, int)**|配列にパラメーター リストをコピーします。|  
|**GetEnumerator()**|パラメーターのコレクションの列挙子を取得します。|  
|**IndexOf(object)**|SAPParameter インスタンスに基づいて、パラメーターのインデックス。|  
|**IndexOf(string)**|SAPParameter 名に基づいて、パラメーターのインデックス。|  
|**Insert(int, object)**|コレクション内に、SAPParameter を挿入します。|  
|**Remove(object)**|インスタンスに基づくコレクションに、SAPParameter を削除します。|  
|**RemoveAt(int)**|コレクション内の指定したインデックスに、SAPParameter を削除します。|  
|**RemoveAt(string)**|名前に基づくコレクションに、SAPParameter を削除します。|  
  
## <a name="see-also"></a>参照  
 [SAP アダプターを使用した ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)