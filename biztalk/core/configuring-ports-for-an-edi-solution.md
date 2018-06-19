---
title: EDI ソリューションのポートの構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 779965c05a5875295fd28e74df6ceacd5037cd2d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233138"
---
# <a name="configuring-ports-for-an-edi-solution"></a><span data-ttu-id="5889d-102">EDI ソリューションのポートの構成</span><span class="sxs-lookup"><span data-stu-id="5889d-102">Configuring Ports for an EDI Solution</span></span>
<span data-ttu-id="5889d-103">EDI メッセージと確認を送受信するには、次の受信ポートと送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="5889d-103">To receive and send EDI messages and acknowledgments, create the following receive and send ports:</span></span>  
  
-   <span data-ttu-id="5889d-104">EDI インターチェンジと確認を受信する一方向の静的 FILE 受信ポート、または EDI インターチェンジを受信して、確認を送信する双方向の要求 - 応答 FILE 受信ポート。</span><span class="sxs-lookup"><span data-stu-id="5889d-104">A one-way static FILE receive port that receives EDI interchanges and acknowledgments or a two-way request-response FILE receive port that receives EDI interchanges and sends acknowledgments.</span></span>  
  
-   <span data-ttu-id="5889d-105">EDI インターチェンジまたは確認を送信する一方向の FILE 送信ポート。</span><span class="sxs-lookup"><span data-stu-id="5889d-105">A one-way FILE send port that sends EDI interchanges or acknowledgments.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5889d-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5889d-106">In This Section</span></span>  
  
-   [<span data-ttu-id="5889d-107">EDI メッセージおよび受信確認を受信するためのポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="5889d-107">Configuring a Port to Receive EDI Messages and Acknowledgments</span></span>](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)  
  
-   [<span data-ttu-id="5889d-108">EDI インターチェンジと確認を送信する静的な送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="5889d-108">Configuring a Static Send Port to Send EDI Interchanges and Acknowledgments</span></span>](../core/configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments.md)  
  
-   [<span data-ttu-id="5889d-109">EDI インターチェンジと確認を送信する動的送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="5889d-109">Configuring a Dynamic Send Port to Send EDI Interchanges and Acknowledgments</span></span>](../core/configuring-a-dynamic-send-port-to-send-edi-interchanges-and-acknowledgments.md)  
  
-   [<span data-ttu-id="5889d-110">1 つのメッセージ内の複数のインターチェンジの受信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5889d-110">Enabling the Receiving of Multiple Interchanges in a Single Message</span></span>](../core/enabling-the-receiving-of-multiple-interchanges-in-a-single-message.md)  
  
## <a name="see-also"></a><span data-ttu-id="5889d-111">参照</span><span class="sxs-lookup"><span data-stu-id="5889d-111">See Also</span></span>  
 [<span data-ttu-id="5889d-112">開発および BizTalk Server EDI ソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="5889d-112">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)