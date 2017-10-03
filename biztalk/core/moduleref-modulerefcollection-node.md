---
title: "ModuleRef (ModuleRefCollection ノード) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ModuleRef node [binding file]
ms.assetid: 61787779-33bd-499a-a5c1-c1e0bd306b48
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ed580b022e9896ade824c8cf8eccc2458c7ddce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="moduleref-modulerefcollection-node"></a>ModuleRef (ModuleRefCollection ノード)
バインド ファイルの ModuleRef ノードには、バインド ファイルと共にエクスポートされた .NET アセンブリに関する特定の情報が含まれます。 ModuleRef ノードには、カスタム コード、スキーマ、およびオーケストレーションを含むアセンブリの説明などを含めることができます。  
  
## <a name="nodes-in-the-moduleref-node"></a>ModuleRef ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[サービス](../core/services-moduleref-node.md)|レコード|ArrayOfServiceRef (ComplexType)|この .NET アセンブリに関連付けられているサービスのコンテナー ノードです。|任意|既定値: なし|  
|[TrackedSchemas (ModuleRef ノード)](../core/trackedschemas-moduleref-node.md)|レコード|ArrayOfSchema (ComplexType)|この .NET アセンブリに関連付けられているスキーマのコンテナー ノードです。|任意|既定値: なし|