---
title: オーケストレーションでポートを使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, receiving
- ports, configuring manually
- send ports, messages
- ports, creating
- ports, messages
- creating, ports
- send ports, sending
- ports, operations
- configuring, ports
- ports, deleting
- deleting, ports
- orchestrations, ports
- Port Configuration Wizard [Orchestration Designer]
- ports
- ports, about ports
- ports, configuring
ms.assetid: 968b2d1b-e233-4eb0-8254-9ec6b7642cdf
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2204e5bb00cd6614c66f9325f043db131b402fbd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396576"
---
# <a name="using-ports-in-orchestrations"></a><span data-ttu-id="0449d-102">オーケストレーションでポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="0449d-102">Using Ports in Orchestrations</span></span>
<span data-ttu-id="0449d-103">ポートは、オーケストレーションはメッセージを送信し、他のビジネス プロセスからメッセージを受信する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="0449d-103">Ports specify how your orchestration will send messages to and receive messages from other business processes.</span></span> <span data-ttu-id="0449d-104">各ポートは、種類、方向、バインドを保持しています。これらの組み合わせによって、通信方向、通信方式、メッセージの送信先場所と送信元場所、および通信の実行方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="0449d-104">Each port has a type, a direction, and a binding, which together determine the direction of communication, the pattern of communication, the location to or from which the message is sent or received, and how the communication takes place.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0449d-105">ポートとポートの種類の間の違いがあります。</span><span class="sxs-lookup"><span data-stu-id="0449d-105">There is a distinction between a port and a port type.</span></span> <span data-ttu-id="0449d-106">ポート、ポートの種類のインスタンスとは複数のポートと同じポートの種類があります。</span><span class="sxs-lookup"><span data-stu-id="0449d-106">A port is an instance of a port type; several different ports may have the same port type.</span></span>  
  
 <span data-ttu-id="0449d-107">これらの要因に応じて、ポートが関連付けられていると (たとえば、アセンブル、暗号化、圧縮を送信するため、メッセージを準備するには、URI (物理的な場所)、トランスポート (FILE、HTTP、SOAP、SMTP または BizTalk メッセージ キュー)、送信パイプラインまたは他の何らかのアクションを実行することで)、および受信パイプライン処理 (たとえば、逆アセンブル、復号化、または、展開で) 受信したメッセージを準備します。</span><span class="sxs-lookup"><span data-stu-id="0449d-107">Depending on these factors, a port may have associated with it a URI (a physical location), a transport (either FILE, HTTP, SOAP, SMTP or BizTalk Message Queuing), a send pipeline to prepare a message for sending (for example, by assembling, encrypting, compressing, or performing some other action on it), and a receive pipeline to prepare a received message for processing (for example, by disassembling, decrypting, or decompressing it).</span></span>  
  
 <span data-ttu-id="0449d-108">ポートを追加でオーケストレーションを Web フォームまたは Windows フォーム コントロールを追加することと同じ方法。</span><span class="sxs-lookup"><span data-stu-id="0449d-108">You add ports to an orchestration in much the same way that you add controls to a Web Form or Windows Form.</span></span> <span data-ttu-id="0449d-109">オーケストレーションの種類 ウィンドウを使用してポートを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="0449d-109">You can also add ports by using the Orchestration View window.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0449d-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0449d-110">In This Section</span></span>  
  
-   [<span data-ttu-id="0449d-111">通信方式</span><span class="sxs-lookup"><span data-stu-id="0449d-111">Communication Pattern</span></span>](../core/communication-pattern.md)  
  
-   [<span data-ttu-id="0449d-112">通信方向</span><span class="sxs-lookup"><span data-stu-id="0449d-112">Communication Direction</span></span>](../core/communication-direction.md)  
  
-   [<span data-ttu-id="0449d-113">ポートのバインド</span><span class="sxs-lookup"><span data-stu-id="0449d-113">Port Bindings</span></span>](../core/port-bindings.md)  
  
-   [<span data-ttu-id="0449d-114">オーケストレーションでポートを使用する方法</span><span class="sxs-lookup"><span data-stu-id="0449d-114">How to Use Ports in Orchestrations</span></span>](../core/how-to-use-ports-in-orchestrations.md)  
  
-   [<span data-ttu-id="0449d-115">ポートの種類を操作する方法</span><span class="sxs-lookup"><span data-stu-id="0449d-115">How to Work with Port Types</span></span>](../core/how-to-work-with-port-types.md)  
  
-   [<span data-ttu-id="0449d-116">ポート構成ウィザードを実行する方法</span><span class="sxs-lookup"><span data-stu-id="0449d-116">How to Run the Port Configuration Wizard</span></span>](../core/how-to-run-the-port-configuration-wizard.md)  
  
-   [<span data-ttu-id="0449d-117">オーケストレーションでの直接バインド ポートの操作</span><span class="sxs-lookup"><span data-stu-id="0449d-117">Working with Direct Bound Ports in Orchestrations</span></span>](../core/working-with-direct-bound-ports-in-orchestrations.md)  
  
## <a name="see-also"></a><span data-ttu-id="0449d-118">参照</span><span class="sxs-lookup"><span data-stu-id="0449d-118">See Also</span></span>  
 <span data-ttu-id="0449d-119">[ポート構成ウィザードを実行する方法](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="0449d-119">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="0449d-120">オーケストレーションでのロール リンクの使用</span><span class="sxs-lookup"><span data-stu-id="0449d-120">Using Role Links in Orchestrations</span></span>](../core/using-role-links-in-orchestrations.md)