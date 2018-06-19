---
title: SendHandler (PrimaryTransport ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendHandler node [binding file]
ms.assetid: c0b200ee-ecbc-4708-a2c8-c37cd6cd0060
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 029285e9b56aeb91bbca7a7c9eacf6abedc7ebbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270530"
---
# <a name="sendhandler-primarytransport-node"></a>SendHandler (PrimaryTransport ノード)
バインド ファイルの PrimaryTransport ノードの SendHandler ノードには、バインド ファイルと共にエクスポートされるトランスポートに関連付けられた送信ハンドラーに関する特定の情報が含まれます。  
  
## <a name="nodes-in-the-sendhandler-node"></a>SendHandler ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|トランスポートに関連付けられている送信ハンドラーの名前を指定します。|任意|既定値: 空|  
|HostTrusted|属性|xs:boolean|送信ハンドラーに関連付けられているホストが信頼されているかどうかを指定します。|必須|既定値: なし<br /><br /> 設定**true**ホストが信頼されている場合、それ以外の場合 'éý' **false**です。|  
|[TransportType](../core/transporttype.md)|レコード|ProtocolType (ComplexType)|トランスポートの種類を指定します。これはこの送信ハンドラーと共に使用されるアダプターの名前でもあります。|必須|既定値: なし|