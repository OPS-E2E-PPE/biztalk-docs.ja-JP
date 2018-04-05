---
title: TransportType |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TransportType node [binding file]
ms.assetid: 64eb00be-47c9-473f-aec6-03cb7f948e3b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8d9636e7aa6dd8b09bb73678072242ed8b8725a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="transporttype"></a>TransportType
バインド ファイルの SendHandler ノードの TransportType ノードには、バインド ファイルと共にエクスポートされる送信ハンドラーに関連付けられたアダプターに関する特定の情報が含まれます。  
  
## <a name="nodes-in-the-transporttype-node"></a>TransportType ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|送信ハンドラーに関連付けられているアダプターの名前を指定します。|任意|既定値: 空|  
|Capabilities|属性|xs:int|送信ハンドラーに関連付けられているアダプターの機能を指定します。|Required|既定値: なし<br /><br /> 設定可能な値には、 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 列挙体に使用できる値が含まれます。|  
|ConfigurationClsid|属性|xs:string|送信ハンドラーに関連付けられているアダプターの構成 GUID を指定します。|任意|既定値: 空|