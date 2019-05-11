---
title: Ports (Service ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Ports node [binding file]
ms.assetid: 498d4310-4e9e-4e74-bc3d-5cbf1319c4ff
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8c7c160529b23a66d2c7cb444908adbaff13184
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394818"
---
# <a name="ports-service-node"></a>Ports (Service ノード)
バインド ファイルの Ports ノードは、すべてのポート ノードは、バインド ファイルと共にエクスポートされるサービスにバインドされるポートに関する特定の情報を含む親ノードです。  
  
## <a name="node-in-the-ports-node"></a>[ポート] ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[[ポート]](../core/port-ports-node.md)|レコード|ServicePortRef (ComplexType)|バインド ファイルと共にエクスポートされるサービスにバインドされたポートに関する情報を指定します。|任意|既定値: なし|