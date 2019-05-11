---
title: EDI ソリューションのポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 94445da5-9ee0-4006-a8c2-3919f128a575
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f3e06271a00d836d999f603f0160dc8966fc60e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355274"
---
# <a name="configuring-ports-for-an-edi-solution"></a><span data-ttu-id="e0587-102">EDI ソリューションのポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="e0587-102">Configuring Ports for an EDI Solution</span></span>
<span data-ttu-id="e0587-103">EDI メッセージと確認を送受信するには、次の受信ポートと送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0587-103">To receive and send EDI messages and acknowledgments, create the following receive and send ports:</span></span>  
  
-   <span data-ttu-id="e0587-104">EDI インターチェンジと確認を受信する一方向の静的 FILE 受信ポート、または EDI インターチェンジを受信して、確認を送信する双方向の要求 - 応答 FILE 受信ポート。</span><span class="sxs-lookup"><span data-stu-id="e0587-104">A one-way static FILE receive port that receives EDI interchanges and acknowledgments or a two-way request-response FILE receive port that receives EDI interchanges and sends acknowledgments.</span></span>  
  
-   <span data-ttu-id="e0587-105">EDI インターチェンジまたは確認を送信する一方向の FILE 送信ポート。</span><span class="sxs-lookup"><span data-stu-id="e0587-105">A one-way FILE send port that sends EDI interchanges or acknowledgments.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e0587-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e0587-106">In This Section</span></span>  
  
-   [<span data-ttu-id="e0587-107">EDI メッセージおよび受信確認を受信するポートの構成</span><span class="sxs-lookup"><span data-stu-id="e0587-107">Configuring a Port to Receive EDI Messages and Acknowledgments</span></span>](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)  
  
-   [<span data-ttu-id="e0587-108">EDI インターチェンジと受信確認を送信するための静的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="e0587-108">Configuring a Static Send Port to Send EDI Interchanges and Acknowledgments</span></span>](../core/configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments.md)  
  
-   [<span data-ttu-id="e0587-109">EDI インターチェンジと確認を送信するための動的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="e0587-109">Configuring a Dynamic Send Port to Send EDI Interchanges and Acknowledgments</span></span>](../core/configuring-a-dynamic-send-port-to-send-edi-interchanges-and-acknowledgments.md)  
  
-   [<span data-ttu-id="e0587-110">単一メッセージ内の複数インターチェンジの受信を可能にする</span><span class="sxs-lookup"><span data-stu-id="e0587-110">Enabling the Receiving of Multiple Interchanges in a Single Message</span></span>](../core/enabling-the-receiving-of-multiple-interchanges-in-a-single-message.md)  
  
## <a name="see-also"></a><span data-ttu-id="e0587-111">参照</span><span class="sxs-lookup"><span data-stu-id="e0587-111">See Also</span></span>  
 [<span data-ttu-id="e0587-112">BizTalk Server EDI ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="e0587-112">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)