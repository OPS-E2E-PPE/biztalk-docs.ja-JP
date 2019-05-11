---
title: ModuleRef (ModuleRefCollection ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ModuleRef node [binding file]
ms.assetid: 61787779-33bd-499a-a5c1-c1e0bd306b48
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 604efe0b0d5d93c6d545b7725d2a0f85609fc32a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394416"
---
# <a name="moduleref-modulerefcollection-node"></a>ModuleRef (ModuleRefCollection ノード)
バインド ファイルの ModuleRef ノードには、バインド ファイルと共にエクスポートされた .NET アセンブリに関する特定の情報が含まれています。 ModuleRef ノードでは、含めることができますが、カスタム コード、スキーマ、およびオーケストレーションを含んでいるアセンブリの説明に制限はありません。  
  
## <a name="nodes-in-the-moduleref-node"></a>ModuleRef ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[Services](../core/services-moduleref-node.md)|レコード|ArrayOfServiceRef (ComplexType)|この .NET アセンブリに関連付けられたサービスのコンテナー ノードです。|任意|既定値: なし|  
|[TrackedSchemas (ModuleRef ノード)](../core/trackedschemas-moduleref-node.md)|レコード|ArrayOfSchema (ComplexType)|この .NET アセンブリに関連付けられたスキーマのコンテナー ノード|任意|既定値: なし|