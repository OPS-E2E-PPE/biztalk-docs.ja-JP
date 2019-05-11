---
title: SendHandler (PrimaryTransport ノード) |Microsoft Docs
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
ms.openlocfilehash: 6128a66f766bad0275957f343fd536f01140e80d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254447"
---
# <a name="sendhandler-primarytransport-node"></a>SendHandler (PrimaryTransport ノード)
バインド ファイルの PrimaryTransport ノードの SendHandler ノードには、バインド ファイルと共にエクスポートされるトランスポートに関連付けられている送信ハンドラーに関する特定の情報が含まれています。  
  
## <a name="nodes-in-the-sendhandler-node"></a>SendHandler ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|トランスポートに関連付けられている送信ハンドラーの名前を指定します。|任意|既定値: 空|  
|HostTrusted|属性|xs:boolean|送信ハンドラーに関連付けられているホストが信頼されているかどうかを指定します。|必須|既定値: なし<br /><br /> 設定**true**ホストが信頼されている場合がそれ以外の場合に設定**false**します。|  
|[TransportType](../core/transporttype.md)|レコード|ProtocolType (ComplexType)|これは、この送信ハンドラーで使用するアダプターの名前でもトランスポートの種類を指定します。|必須|既定値: なし|