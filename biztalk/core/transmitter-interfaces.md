---
title: 送信元インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ffa6db3b-739e-438c-b410-8823a20eed82
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e0bab66be2867d8f0117d951b706953f2b541a2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243097"
---
# <a name="transmitter-interfaces"></a><span data-ttu-id="8fc4a-102">送信元インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8fc4a-102">Transmitter Interfaces</span></span>
<span data-ttu-id="8fc4a-103">(送信) アダプターの送信の必須のアダプター インターフェイスに加えて、どちらかを実装する必要があります**IBTTransmitter**非バッチ処理している場合または**IBTBatchTransmitter**バッチ化されている場合。</span><span class="sxs-lookup"><span data-stu-id="8fc4a-103">In addition to the mandatory adapter interfaces, transmit (send) adapters, need to implement either **IBTTransmitter** if they are non-batched or **IBTBatchTransmitter** if they are batched.</span></span>  
  
 <span data-ttu-id="8fc4a-104">次の図は、バッチと非バッチ送信アダプターが実装する必要があるインターフェイスを示しています。</span><span class="sxs-lookup"><span data-stu-id="8fc4a-104">The following figure shows the interfaces that batched and non-batched send adapters need to implement.</span></span>  
  
 <span data-ttu-id="8fc4a-105">![](../core/media/transmitterinterfaces.gif "TransmitterInterfaces")</span><span class="sxs-lookup"><span data-stu-id="8fc4a-105">![](../core/media/transmitterinterfaces.gif "TransmitterInterfaces")</span></span>