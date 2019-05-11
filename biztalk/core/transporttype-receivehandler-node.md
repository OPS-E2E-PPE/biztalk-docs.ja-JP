---
title: TransportType (ReceiveHandler ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TransportType node [binding file]
ms.assetid: d893b3ac-8e2c-41fb-926c-cea23f6f93b3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f1acfd92363a8378d46caaeaf907efd969c0337
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243241"
---
# <a name="transporttype-receivehandler-node"></a>TransportType (ReceiveHandler ノード)
バインド ファイルの ReceiveHandler ノードの TransportType ノードには、バインド ファイルと共にエクスポートされる受信ハンドラーに関連付けられたアダプターに関する特定の情報が含まれます。  
  
## <a name="nodes-in-the-transporttype-node"></a>TransportType ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|受信ハンドラーに関連付けられているアダプターの名前を指定します。|任意|既定値: 空|  
|Capabilities|属性|xs:int|受信ハンドラーに関連付けられているアダプターの機能を指定します。|Required|既定値: なし<br /><br /> 設定可能な値には、 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 列挙体に使用できる値が含まれます。|  
|ConfigurationClsid|属性|xs:string|受信ハンドラーに関連付けられているアダプターの構成 GUID を指定します。|任意|既定値: 空|