---
title: Ports (Service ノード) |Microsoft ドキュメント
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
ms.openlocfilehash: 31e09470b9f3287cce5ce15c2941d2165157ec48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="ports-service-node"></a>Ports (Service ノード)
バインド ファイルの Ports ノードは、バインド ファイルと共にエクスポートされるサービスにバインドされるポートに関する特定の情報を含むすべての Port ノードの親ノードです。  
  
## <a name="node-in-the-ports-node"></a>Ports ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[[ポート]](../core/port-ports-node.md)|レコード|ServicePortRef (ComplexType)|バインド ファイルと共にエクスポートされるサービスにバインドされたポートに関する情報を指定します。|任意|既定値: なし|