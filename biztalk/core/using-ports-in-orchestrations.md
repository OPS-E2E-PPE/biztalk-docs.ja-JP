---
title: "オーケストレーションでポートを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7f48c1c070e3a3a3e7ebe7e86618a4fd9ebc90d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-ports-in-orchestrations"></a><span data-ttu-id="662c2-102">オーケストレーションでのポートの使用</span><span class="sxs-lookup"><span data-stu-id="662c2-102">Using Ports in Orchestrations</span></span>
<span data-ttu-id="662c2-103">ポートを使用して、オーケストレーションでの、他のビジネス プロセスを対象としたメッセージの送受信方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="662c2-103">Ports specify how your orchestration will send messages to and receive messages from other business processes.</span></span> <span data-ttu-id="662c2-104">各ポートは、種類、方向、バインドを保持しています。これらの組み合わせによって、通信方向、通信方式、メッセージの送信先場所と送信元場所、および通信の実行方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="662c2-104">Each port has a type, a direction, and a binding, which together determine the direction of communication, the pattern of communication, the location to or from which the message is sent or received, and how the communication takes place.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="662c2-105">ポートとポートの種類は異なります。</span><span class="sxs-lookup"><span data-stu-id="662c2-105">There is a distinction between a port and a port type.</span></span> <span data-ttu-id="662c2-106">ポートは、ポートの種類のインスタンスです。このため、複数の異なるポートが同じポートの種類を保持する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="662c2-106">A port is an instance of a port type; several different ports may have the same port type.</span></span>  
  
 <span data-ttu-id="662c2-107">これらの要素に応じて、ポートは、URI (物理的な場所)、トランスポート (FILE、HTTP、SOAP、SMTP、または BizTalk メッセージ キュー)、送信用のメッセージを準備する (たとえば、他の操作のアセンブル、暗号化、圧縮、または実行を行う) 送信パイプライン、および処理用の受信メッセージを準備する (たとえば、メッセージの逆アセンブル、復号化、または圧縮解除を行う) 受信パイプラインと関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="662c2-107">Depending on these factors, a port may have associated with it a URI (a physical location), a transport (either FILE, HTTP, SOAP, SMTP or BizTalk Message Queuing), a send pipeline to prepare a message for sending (for example, by assembling, encrypting, compressing, or performing some other action on it), and a receive pipeline to prepare a received message for processing (for example, by disassembling, decrypting, or decompressing it).</span></span>  
  
 <span data-ttu-id="662c2-108">コントロールを Web フォームまたは Windows フォームに追加する場合と同じ方法で、ポートをオーケストレーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="662c2-108">You add ports to an orchestration in much the same way that you add controls to a Web Form or Windows Form.</span></span> <span data-ttu-id="662c2-109">[オーケストレーションの種類] ウィンドウで、ポートを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="662c2-109">You can also add ports by using the Orchestration View window.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="662c2-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="662c2-110">In This Section</span></span>  
  
-   [<span data-ttu-id="662c2-111">通信方式</span><span class="sxs-lookup"><span data-stu-id="662c2-111">Communication Pattern</span></span>](../core/communication-pattern.md)  
  
-   [<span data-ttu-id="662c2-112">通信方向</span><span class="sxs-lookup"><span data-stu-id="662c2-112">Communication Direction</span></span>](../core/communication-direction.md)  
  
-   [<span data-ttu-id="662c2-113">ポートのバインド</span><span class="sxs-lookup"><span data-stu-id="662c2-113">Port Bindings</span></span>](../core/port-bindings.md)  
  
-   [<span data-ttu-id="662c2-114">オーケストレーションでポートを使用する方法</span><span class="sxs-lookup"><span data-stu-id="662c2-114">How to Use Ports in Orchestrations</span></span>](../core/how-to-use-ports-in-orchestrations.md)  
  
-   [<span data-ttu-id="662c2-115">ポートの種類を操作する方法</span><span class="sxs-lookup"><span data-stu-id="662c2-115">How to Work with Port Types</span></span>](../core/how-to-work-with-port-types.md)  
  
-   [<span data-ttu-id="662c2-116">ポート構成ウィザードを実行する方法</span><span class="sxs-lookup"><span data-stu-id="662c2-116">How to Run the Port Configuration Wizard</span></span>](../core/how-to-run-the-port-configuration-wizard.md)  
  
-   [<span data-ttu-id="662c2-117">オーケストレーションでの直接バインド ポートの操作</span><span class="sxs-lookup"><span data-stu-id="662c2-117">Working with Direct Bound Ports in Orchestrations</span></span>](../core/working-with-direct-bound-ports-in-orchestrations.md)  
  
## <a name="see-also"></a><span data-ttu-id="662c2-118">参照</span><span class="sxs-lookup"><span data-stu-id="662c2-118">See Also</span></span>  
 <span data-ttu-id="662c2-119">[ポート構成ウィザードを実行する方法](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="662c2-119">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="662c2-120">オーケストレーションでロール リンクの使用</span><span class="sxs-lookup"><span data-stu-id="662c2-120">Using Role Links in Orchestrations</span></span>](../core/using-role-links-in-orchestrations.md)