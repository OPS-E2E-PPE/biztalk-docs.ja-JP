---
title: ReceiveHandler (ReceiveLocation ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ReceiveHandler node [binding file]
ms.assetid: dd105052-ec71-4762-aa74-e8cdb806a6bf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e04d45b94641703b045a3d3d8d571d7586424c57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398169"
---
# <a name="receivehandler-receivelocation-node"></a>ReceiveHandler (ReceiveLocation ノード)
バインド ファイルの ReceiveLocation ノードの ReceiveHandler ノードには、バインド ファイルと共にエクスポートされるトランスポートに関連付けられている受信ハンドラーに関する特定の情報が含まれています。  
  
## <a name="nodes-in-the-receivehandler-node"></a>ReceiveHandler ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|トランスポートに関連付けられている受信ハンドラーの名前を指定します。|任意|既定値: 空|  
|HostTrusted|属性|xs:boolean|受信ハンドラーに関連付けられているホストが信頼されているかどうかを指定します。|必須|既定値: なし<br /><br /> 設定**true**ホストが信頼されている場合がそれ以外の場合に設定**false**します。|  
|[TransportType (ReceiveHandler ノード)](../core/transporttype-receivehandler-node.md)|レコード|ProtocolType (ComplexType)|これで使用するアダプターの名前でもあるトランスポートの種類を指定します。 受信ハンドラー。|必須|既定値: なし|