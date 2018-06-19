---
title: TrackedSchemas (ModuleRef ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TrackedSchemas node [binding file]
ms.assetid: a2b99fbf-df6b-4a94-97b8-ac5eb819604f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 303aeb1ed17b001583a596d5b550faf63ea1200b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278914"
---
# <a name="trackedschemas-moduleref-node"></a>TrackedSchemas (ModuleRef ノード)
バインド ファイルの TrackedSchemas ノードは、バインド ファイルと共にエクスポートされるサービスにバインドされたスキーマを記述するすべての Schema ノードの親ノードです。  
  
## <a name="nodes-in-the-trackedschemas-node"></a>TrackedSchemas ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[スキーマ](../core/schema-trackedschemas-node.md)|レコード|ArrayOfSchema (ComplexType)|バインド ファイルと共にエクスポートされるサービスにバインドされたスキーマのコンテナー ノードです。|任意|既定値: なし|