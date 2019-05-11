---
title: ReceiveLocationTransportType (ReceiveLocation ノード) |Microsoft Docs
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
ms.openlocfilehash: aba0abcf71824d1109bb7a47104ab928df247fd0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398136"
---
# <a name="receivelocationtransporttype-receivelocation-node"></a>ReceiveLocationTransportType (ReceiveLocation ノード)
バインド ファイルの ReceiveLocation ノードの ReceiveLocationTransportType ノードには、バインド ファイルと共にエクスポートされるトランスポートに関連付けられたアダプターに関する特定の情報が含まれています。  
  
## <a name="nodes-in-the-receivelocationtransporttype-node"></a>ReceiveLocationTransportType ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|トランスポートに関連付けられているアダプターの名前を指定します。|任意|既定値: 空|  
|Capabilities|属性|xs:int|トランスポートに関連付けられているアダプターの機能を指定します。|必須|既定値: なし<br /><br /> 設定可能な値には、 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 列挙体に使用できる値が含まれます。|  
|ConfigurationClsid|属性|xs:string|トランスポートに関連付けられているアダプターの構成 GUID を指定します。|任意|既定値: 空|