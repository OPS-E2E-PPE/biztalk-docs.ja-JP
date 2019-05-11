---
title: 受信元インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7ab77d4-705a-4b39-8c33-a7532ae6484c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 540da1fac24c69bd352a5fd0db9f2831f62f920f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398078"
---
# <a name="receiver-interfaces"></a>受信元インターフェイス
標準的なアダプター インターフェイスに加えて受信アダプターが実装しなければ**IBTTransportConfig**します。 これは、BizTalk メッセージング エンジンは受信場所の構成をアダプターにするインターフェイスです。  
  
## <a name="request-response-adapters"></a>要求-応答アダプター  
 受信アダプターは、場合によっては、送信メッセージを処理する必要もあります。 このアダプターは通常、双方向に呼ばれますまたは要求-応答アダプター。 受信アダプターはメッセージを送信できるようにするには、実装する必要がある**IBTTransmitter**します。  
  
 次の図は、受信アダプターによって実装されるインターフェイスを示します。  
  
> [!NOTE]
>  **IBTBatchTransmitter**要求-応答アダプターのインターフェイスがサポートされていません。  
  
 ![](../core/media/requestresponseadapters.gif "RequestResponseAdapters")