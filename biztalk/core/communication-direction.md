---
title: 通信方向 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- port types, communication direction
- communication direction [port types]
ms.assetid: b278325e-a1da-49a6-8332-80a5f640cc22
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 307c8bae32aa7be0fee74f2f25c1bf4a2252ed0b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357096"
---
# <a name="communication-direction"></a><span data-ttu-id="4f2a5-102">通信方向</span><span class="sxs-lookup"><span data-stu-id="4f2a5-102">Communication Direction</span></span>
<span data-ttu-id="4f2a5-103">各*ポート*が独自の通信方向。</span><span class="sxs-lookup"><span data-stu-id="4f2a5-103">Each *port* has its own communication direction.</span></span> <span data-ttu-id="4f2a5-104">通信方向は、ポートの使用方法の定義を完了するに、ポートの種類の通信方式と組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="4f2a5-104">The communication direction is used in combination with the communication pattern of the port's type to complete the definition of how a port can be used.</span></span> <span data-ttu-id="4f2a5-105">通信方向、つまり極性によって、そのポート経由で、メッセージを送信する方向を決定します。</span><span class="sxs-lookup"><span data-stu-id="4f2a5-105">The communication direction, or polarity, determines in which direction messages will be transmitted over that port.</span></span>  
  
 <span data-ttu-id="4f2a5-106">ポートの種類の一方向通信パターンの場合、通信方向は送信または受信のいずれかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4f2a5-106">If the port's type has a one-way communication pattern, its communication direction can be either Send or Receive.</span></span> <span data-ttu-id="4f2a5-107">ポートの種類の双方向 (要求-応答) の通信パターンの場合、通信方向は送信と受信要求を送信し、応答を受信すると、または受信、送信、要求を受信し、応答の送信を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4f2a5-107">If the port's type has a two-way (request-response) communication pattern, its communication direction can be Send-Receive, in which a request is sent and a response is received, or Receive-Send, in which a request is received and a response is sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f2a5-108">参照</span><span class="sxs-lookup"><span data-stu-id="4f2a5-108">See Also</span></span>  
 [<span data-ttu-id="4f2a5-109">通信方式</span><span class="sxs-lookup"><span data-stu-id="4f2a5-109">Communication Pattern</span></span>](../core/communication-pattern.md)  
 <span data-ttu-id="4f2a5-110">[ポート構成ウィザードを実行する方法](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="4f2a5-110">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="4f2a5-111">オーケストレーションでのポートの使用</span><span class="sxs-lookup"><span data-stu-id="4f2a5-111">Using Ports in Orchestrations</span></span>](../core/using-ports-in-orchestrations.md)