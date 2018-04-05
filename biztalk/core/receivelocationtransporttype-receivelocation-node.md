---
title: ReceiveLocationTransportType (ReceiveLocation ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ReceiveLocationTransportType node [binding file]
ms.assetid: 375076c3-d5e6-4c25-b054-b452e29717e0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0eae3e2c4fd9f5f668cb12ffd630640b1b63c74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="receivelocationtransporttype-receivelocation-node"></a>ReceiveLocationTransportType (ReceiveLocation ノード)
バインド ファイルの ReceiveLocation ノードの ReceiveLocationTransportType ノードには、そのバインド ファイルと共にエクスポートされるトランスポートに関連付けられているアダプターに関する情報が含まれます。  
  
## <a name="nodes-in-the-receivelocationtransporttype-node"></a>ReceiveLocationTransportType ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|トランスポートに関連付けられているアダプターの名前を指定します。|任意|既定値: 空|  
|Capabilities|属性|xs:int|トランスポートに関連付けられているアダプターの機能を指定します。|Required|既定値: なし<br /><br /> 設定可能な値には、 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 列挙体に使用できる値が含まれます。|  
|ConfigurationClsid|属性|xs:string|トランスポートに関連付けられているアダプターの構成 GUID を指定します。|任意|既定値: 空|