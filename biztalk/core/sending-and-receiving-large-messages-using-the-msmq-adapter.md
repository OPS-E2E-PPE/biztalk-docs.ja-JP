---
title: MSMQ アダプターを使用してサイズの大きいメッセージの送受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, large messages
- configuring [MSMQ adapters], large messages
- MSMQ adapters, large messages
ms.assetid: 208efbed-7b58-4da5-ba27-65a315c2713b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b5a1267aa0ee1ffc2d44326ad8922d6fac16a1c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399028"
---
# <a name="sending-and-receiving-large-messages-using-the-msmq-adapter"></a><span data-ttu-id="212a8-102">MSMQ アダプターを使用してサイズの大きいメッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="212a8-102">Sending and Receiving Large Messages Using the MSMQ Adapter</span></span>
<span data-ttu-id="212a8-103">MSMQ アダプターの既定のメッセージ処理、部分的に異なります、メッセージのサイズ。</span><span class="sxs-lookup"><span data-stu-id="212a8-103">The MSMQ adapter default message handling depends, in part, on the size of the message.</span></span> <span data-ttu-id="212a8-104">メッセージが 4 メガバイト (4 MB) の場合は、MSMQ アダプターは、.NET Framework クラス ライブラリを使用します。</span><span class="sxs-lookup"><span data-stu-id="212a8-104">When a message is less than four megabytes (4 MB), the MSMQ adapter uses the .NET Framework Class Library.</span></span> <span data-ttu-id="212a8-105">Microsoft では、サイズの大きいメッセージの拡張機能を使用して、それ以外の場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="212a8-105">Otherwise, it uses the large message extensions in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="212a8-106">アプリケーションは一貫して受信またはサイズの大きいメッセージを送信、アダプターが使用するメモリの量を制御する必要があります。</span><span class="sxs-lookup"><span data-stu-id="212a8-106">If your application consistently receives or sends large messages, you may have to control the amount of memory that the adapter uses.</span></span> <span data-ttu-id="212a8-107">メモリの節約の詳細については、次を参照してください。 [MSMQ アダプターのパフォーマンスの最適化](../core/optimizing-performance-of-the-msmq-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="212a8-107">For more information about conserving memory, see [Optimizing Performance of the MSMQ Adapter](../core/optimizing-performance-of-the-msmq-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="212a8-108">参照</span><span class="sxs-lookup"><span data-stu-id="212a8-108">See Also</span></span>  
 <span data-ttu-id="212a8-109">[MSMQ アダプターのパフォーマンスを最適化します。](../core/optimizing-performance-of-the-msmq-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="212a8-109">[Optimizing Performance of the MSMQ Adapter](../core/optimizing-performance-of-the-msmq-adapter.md) </span></span>  
 [<span data-ttu-id="212a8-110">MSMQ アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="212a8-110">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)