---
title: TrackedSchemas (ModuleRef ノード) |Microsoft Docs
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
ms.openlocfilehash: 0aa14543e64685e6f12a268c4e825c01d277fda9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313979"
---
# <a name="trackedschemas-moduleref-node"></a>TrackedSchemas (ModuleRef ノード)
バインド ファイルの TrackedSchemas ノードは、すべてのバインド ファイルと共にエクスポートされるサービスにバインドされているスキーマを記述するスキーマ ノードの親ノードです。  
  
## <a name="nodes-in-the-trackedschemas-node"></a>TrackedSchemas ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[[スキーマ]](../core/schema-trackedschemas-node.md)|レコード|ArrayOfSchema (ComplexType)|バインド ファイルと共にエクスポートされるサービスにバインドされているスキーマのコンテナー ノードです。|任意|既定値: なし|