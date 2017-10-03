---
title: "通信方向 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- port types, communication direction
- communication direction [port types]
ms.assetid: b278325e-a1da-49a6-8332-80a5f640cc22
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d6c664643629971366805d08600677d22d7c419
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="communication-direction"></a><span data-ttu-id="7ff26-102">[通信方向]</span><span class="sxs-lookup"><span data-stu-id="7ff26-102">Communication Direction</span></span>
<span data-ttu-id="7ff26-103">各*ポート*独自通信の方向がします。</span><span class="sxs-lookup"><span data-stu-id="7ff26-103">Each *port* has its own communication direction.</span></span> <span data-ttu-id="7ff26-104">通信方向は、ポートの種類の通信方式と組み合わせて、ポートの使用方法の定義に使用されます。</span><span class="sxs-lookup"><span data-stu-id="7ff26-104">The communication direction is used in combination with the communication pattern of the port's type to complete the definition of how a port can be used.</span></span> <span data-ttu-id="7ff26-105">通信方向、つまり極性によって、そのポートでメッセージが送信される方向が決定します。</span><span class="sxs-lookup"><span data-stu-id="7ff26-105">The communication direction, or polarity, determines in which direction messages will be transmitted over that port.</span></span>  
  
 <span data-ttu-id="7ff26-106">ポートの種類で一方向の通信方式が使用できる場合、通信方向は送信または受信のどちらかにできます。</span><span class="sxs-lookup"><span data-stu-id="7ff26-106">If the port's type has a one-way communication pattern, its communication direction can be either Send or Receive.</span></span> <span data-ttu-id="7ff26-107">ポートの種類で双方向 (要求 - 応答) の通信方式が使用できる場合、通信方向は、要求を送信して応答を受信する "送信と受信"、または要求を受信して応答を送信する "受信と送信" のどちらかにできます。</span><span class="sxs-lookup"><span data-stu-id="7ff26-107">If the port's type has a two-way (request-response) communication pattern, its communication direction can be Send-Receive, in which a request is sent and a response is received, or Receive-Send, in which a request is received and a response is sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ff26-108">参照</span><span class="sxs-lookup"><span data-stu-id="7ff26-108">See Also</span></span>  
 [<span data-ttu-id="7ff26-109">通信方式</span><span class="sxs-lookup"><span data-stu-id="7ff26-109">Communication Pattern</span></span>](../core/communication-pattern.md)  
 <span data-ttu-id="7ff26-110">[ポート構成ウィザードを実行する方法](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="7ff26-110">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="7ff26-111">オーケストレーションでポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="7ff26-111">Using Ports in Orchestrations</span></span>](../core/using-ports-in-orchestrations.md)