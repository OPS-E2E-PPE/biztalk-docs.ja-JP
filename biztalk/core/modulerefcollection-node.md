---
title: ModuleRefCollection ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ModuleRefCollection node [binding file]
ms.assetid: fa8593bf-6548-4615-9f98-1e0eadde9aa4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a8f756d15e7b4dd88029ad169d5aac66e894aff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324502"
---
# <a name="modulerefcollection-node"></a>ModuleRefCollection ノード
バインド ファイルの ModuleRefCollection セクションは、すべてのバインド ファイルと共にエクスポートされる .NET アセンブリに関する特定の情報を含む ModuleRef ノードの親ノードです。  
  
## <a name="entries-in-the-modulerefcollection-section"></a>ModuleRefCollection セクションのエントリ  
 次の表では、バインド ファイルのこのセクションで、ノードに対して設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[ModuleRef](../core/moduleref-modulerefcollection-node.md)|レコード|ModuleRef (ComplexType)|バインド ファイルと共にエクスポートされた .NET アセンブリのモジュールのコンテナー ノードです。|任意|既定値:なし|