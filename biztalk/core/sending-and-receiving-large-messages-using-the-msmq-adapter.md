---
title: MSMQ アダプターを使用してサイズの大きいメッセージを送受信する |Microsoft ドキュメント
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
ms.openlocfilehash: 8a23265be84f2767849e4d61c2e9a95bfc9ed4ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269530"
---
# <a name="sending-and-receiving-large-messages-using-the-msmq-adapter"></a><span data-ttu-id="419d3-102">MSMQ アダプタを使用したサイズの大きいメッセージの送受信</span><span class="sxs-lookup"><span data-stu-id="419d3-102">Sending and Receiving Large Messages Using the MSMQ Adapter</span></span>
<span data-ttu-id="419d3-103">MSMQ アダプタの既定のメッセージ処理には、メッセージのサイズに依存する部分があります。</span><span class="sxs-lookup"><span data-stu-id="419d3-103">The MSMQ adapter default message handling depends, in part, on the size of the message.</span></span> <span data-ttu-id="419d3-104">メッセージのサイズが 4 MB 未満の場合、MSMQ アダプタで .NET Framework クラス ライブラリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="419d3-104">When a message is less than four megabytes (4 MB), the MSMQ adapter uses the .NET Framework Class Library.</span></span> <span data-ttu-id="419d3-105">4 MB 以上の場合は、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の、サイズの大きいメッセージ用拡張機能が使用されます。</span><span class="sxs-lookup"><span data-stu-id="419d3-105">Otherwise, it uses the large message extensions in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="419d3-106">アプリケーションで、常にサイズの大きいメッセージの送受信を行う場合、アダプタで使用するメモリ量の制御が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="419d3-106">If your application consistently receives or sends large messages, you may have to control the amount of memory that the adapter uses.</span></span> <span data-ttu-id="419d3-107">メモリの節約の詳細については、次を参照してください。 [MSMQ アダプターのパフォーマンスの最適化](../core/optimizing-performance-of-the-msmq-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="419d3-107">For more information about conserving memory, see [Optimizing Performance of the MSMQ Adapter](../core/optimizing-performance-of-the-msmq-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="419d3-108">参照</span><span class="sxs-lookup"><span data-stu-id="419d3-108">See Also</span></span>  
 <span data-ttu-id="419d3-109">[MSMQ アダプターのパフォーマンスを最適化します。](../core/optimizing-performance-of-the-msmq-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="419d3-109">[Optimizing Performance of the MSMQ Adapter](../core/optimizing-performance-of-the-msmq-adapter.md) </span></span>  
 [<span data-ttu-id="419d3-110">MSMQ アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="419d3-110">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)