---
title: ReceiveHandler (ReceiveLocation ノード) |Microsoft ドキュメント
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
ms.openlocfilehash: e865886624731414f979c77f3f2e898e417c8b11
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268538"
---
# <a name="receivehandler-receivelocation-node"></a>ReceiveHandler (ReceiveLocation ノード)
バインド ファイルの ReceiveLocation ノードの ReceiveHandler ノードには、バインド ファイルと共にエクスポートされるトランスポートに関連付けられた受信ハンドラーに関する特定の情報が含まれます。  
  
## <a name="nodes-in-the-receivehandler-node"></a>ReceiveHandler ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|トランスポートに関連付けられている受信ハンドラーの名前を指定します。|任意|既定値: 空|  
|HostTrusted|属性|xs:boolean|受信ハンドラーに関連付けられているホストが信頼されているかどうかを指定します。|必須|既定値: なし<br /><br /> 設定**true**ホストが信頼されている場合、それ以外の場合 'éý' **false**です。|  
|[TransportType (ReceiveHandler ノード)](../core/transporttype-receivehandler-node.md)|レコード|ProtocolType (ComplexType)|トランスポートの種類を指定します。これはこの受信ハンドラーと共に使用されるアダプターの名前でもあります。|必須|既定値: なし|