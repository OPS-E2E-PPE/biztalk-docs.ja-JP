---
title: "受信元インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7ab77d4-705a-4b39-8c33-a7532ae6484c
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77b42530d721a6dcee52e082fe46deae9ae06405
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="receiver-interfaces"></a>受信元インターフェイス
実装するアダプターの必要性が表示される、標準的なアダプター インターフェイスに加えて、 **IBTTransportConfig**です。 これは、BizTalk Server メッセージング エンジンが、受信場所の構成をアダプターに送信するインターフェイスです。  
  
## <a name="request-response-adapters"></a>要求-応答アダプター  
 受信アダプターでは、送信メッセージの処理が必要となる場合もあります。 一般に、これを実行するアダプターは、双方向アダプター、つまり要求 - 応答アダプターと呼ばれます。 メッセージを送信できるようにするには、受信アダプターを実装する必要がある**IBTTransmitter**です。  
  
 次の図は、受信アダプターによって実装されるインターフェイスを示します。  
  
> [!NOTE]
>  **IBTBatchTransmitter**要求-応答アダプターのインターフェイスがサポートされていません。  
  
 ![](../core/media/requestresponseadapters.gif "RequestResponseAdapters")