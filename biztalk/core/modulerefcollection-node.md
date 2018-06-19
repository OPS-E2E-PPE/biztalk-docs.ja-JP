---
title: ModuleRefCollection ノード |Microsoft ドキュメント
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
ms.openlocfilehash: 039cabd380195f840e9ffb99de5071026b3810c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262682"
---
# <a name="modulerefcollection-node"></a>ModuleRefCollection ノード
バインド ファイルの ModuleRefCollection セクションは、バインド ファイルと共にエクスポートされる .NET アセンブリに関する特定の情報を含むすべての ModuleRef ノードの親ノードです。  
  
## <a name="entries-in-the-modulerefcollection-section"></a>ModuleRefCollection セクションのエントリ  
 次の表に、バインド ファイルのこのセクション内のノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[ModuleRef](../core/moduleref-modulerefcollection-node.md)|レコード|ModuleRef (ComplexType)|バインド ファイルと共にエクスポートされる .NET アセンブリ モジュールのコンテナー ノードです。|任意|既定値: なし|