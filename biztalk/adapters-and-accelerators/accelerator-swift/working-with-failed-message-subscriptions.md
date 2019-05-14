---
title: メッセージのサブスクリプションの失敗の操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- failed messages, subscriptions
- failed messages, developing
- developing, failed message subscriptions
ms.assetid: 8dee0aa8-53bf-40be-866b-f1b83960dc99
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0244ea33744d592377261c8e532d981cc5d828aa
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529670"
---
# <a name="working-with-failed-message-subscriptions"></a><span data-ttu-id="09f3e-102">失敗したメッセージのサブスクリプションの使用</span><span class="sxs-lookup"><span data-stu-id="09f3e-102">Working with Failed Message Subscriptions</span></span>
<span data-ttu-id="09f3e-103">ときに、Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]逆アセンブラーのプロセス (解析および検証します)、メッセージをそのメッセージのプロパティを昇格します。</span><span class="sxs-lookup"><span data-stu-id="09f3e-103">When the Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] disassembler processes (parses and validates) a message, it promotes properties for that message.</span></span> <span data-ttu-id="09f3e-104">これらの昇格させたプロパティは、A4SWIFT 受信バッチの一環として、メッセージを受信した場合、バッチに関連する情報だけでなく、正確性と、メッセージの有効性についての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="09f3e-104">These promoted properties provide information about the correctness and validity of the message, as well as batch-related information if A4SWIFT received the message as part of an inbound batch.</span></span> <span data-ttu-id="09f3e-105">これらのプロパティの完全な一覧を参照してください。 [a4swift _ \* 昇格プロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="09f3e-105">For a complete list of these properties, see [A4SWIFT_\* Promoted Properties](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).</span></span>  
  
 <span data-ttu-id="09f3e-106">ネイティブの BizTalk 逆アセンブラーとは異なり、A4SWIFT 逆アセンブラーはメッセージを保留しない生成エラーや障害を処理するときにします。</span><span class="sxs-lookup"><span data-stu-id="09f3e-106">Unlike native BizTalk Disassemblers, the A4SWIFT disassembler does not suspend a message when processing produces errors or failures.</span></span> <span data-ttu-id="09f3e-107">代わりに、そのメッセージを発行、失敗したメッセージ ボックス データベースに有効なメッセージと同様です。</span><span class="sxs-lookup"><span data-stu-id="09f3e-107">Instead, it publishes the failed message to the MessageBox database just as it would a valid message.</span></span> <span data-ttu-id="09f3e-108">その結果、失敗したメッセージはメッセージ ボックス データベースにエラーの詳細を実行できます。</span><span class="sxs-lookup"><span data-stu-id="09f3e-108">As a result, failed messages can carry error details into the MessageBox database.</span></span> <span data-ttu-id="09f3e-109">メッセージ ボックス データベースからメッセージを取得、処理し、メッセージを修復しても、メッセージ ボックス データベースにメッセージを再送信できます。</span><span class="sxs-lookup"><span data-stu-id="09f3e-109">You can retrieve the message from the MessageBox database, handle and repair the message, and even resubmit the message back into the MessageBox database.</span></span> <span data-ttu-id="09f3e-110">メッセージが実際にあった場合、これらのタスクのほとんどを実行することはできません*中断*します。</span><span class="sxs-lookup"><span data-stu-id="09f3e-110">You would not be able to perform most of these tasks if the message was actually *suspended*.</span></span>  
  
 <span data-ttu-id="09f3e-111">A4SWIFT が昇格させたプロパティによってエラーがあるかどうかと、メッセージ ボックス データベースに公開するメッセージを識別できます。</span><span class="sxs-lookup"><span data-stu-id="09f3e-111">You can identify a message that A4SWIFT has published to the MessageBox database as failed or erroneous by its promoted properties.</span></span> <span data-ttu-id="09f3e-112">SWIFT 逆アセンブラーが設定し、昇格失敗したメッセージを処理する際、 **A4SWIFT_Failed**プロパティ、および 1 つ以上のメッセージをメッセージ ボックス データベースに公開する前に、他の次プロパティ。</span><span class="sxs-lookup"><span data-stu-id="09f3e-112">When processing a failed message, the SWIFT disassembler populates and promotes the **A4SWIFT_Failed** property, and one or more of the other following properties, before publishing the message to the MessageBox database:</span></span>  
  
- <span data-ttu-id="09f3e-113">**A4SWIFT_ParseErrors**解析処理中に発生 (形式が正しくないデータ) などのエラーの数を示します。</span><span class="sxs-lookup"><span data-stu-id="09f3e-113">**A4SWIFT_ParseErrors** indicates the number of parsing errors (such as malformed data) encountered during processing.</span></span>  
  
- <span data-ttu-id="09f3e-114">**A4SWIFT_XmlValidationErrors**処理中に発生した (無効なデータやスキーマに関して型が正しくない) XML 検証のエラーの数を示します。</span><span class="sxs-lookup"><span data-stu-id="09f3e-114">**A4SWIFT_XmlValidationErrors** indicates the number of XML validation errors (such as invalid data or incorrect type with respect to the schema) encountered during processing.</span></span>  
  
- <span data-ttu-id="09f3e-115">**A4SWIFT_BreValidationErrors**処理中に発生した (SWIFT ネットワーク規則に違反するデータ) などのビジネス ルール エンジン (BRE) の検証エラーの数を示します。</span><span class="sxs-lookup"><span data-stu-id="09f3e-115">**A4SWIFT_BreValidationErrors** indicates the number of Business Rule Engine (BRE) validation errors (such as data that breaks a SWIFT network rule) encountered during processing.</span></span>  
  
- <span data-ttu-id="09f3e-116">**A4SWIFT_Failed**は**true**任意の数、上記のプロパティが 0 より大きい場合、または**false**カウントが 0 に等しい場合。</span><span class="sxs-lookup"><span data-stu-id="09f3e-116">**A4SWIFT_Failed** is **true** when the count of any the above properties is greater than zero, or **false** when the count is equal to zero.</span></span>  
  
  <span data-ttu-id="09f3e-117">これらのプロパティは、Microsoft のすべての一部です。Solutions.A4SWIFT.Property 名前空間。</span><span class="sxs-lookup"><span data-stu-id="09f3e-117">These properties are all part of the Microsoft .Solutions.A4SWIFT.Property namespace.</span></span> <span data-ttu-id="09f3e-118">これらおよびその他の昇格させたプロパティの詳細については、次を参照してください。 [a4swift _ \* 昇格プロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="09f3e-118">For more information about these and other promoted properties, see [A4SWIFT_\* Promoted Properties](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).</span></span>  
  
  <span data-ttu-id="09f3e-119">Catch または失敗したメッセージを取得、送信ポートのフィルター式 (サブスクリプション) を作成する必要があるまたはオーケストレーションの受信図形を含む、上記のプロパティの一部として**AND**式の句。</span><span class="sxs-lookup"><span data-stu-id="09f3e-119">To catch or retrieve failed messages, you need to create filter expressions (subscriptions) for send ports or orchestration receive shapes that include some of the properties listed above, as **AND** clauses of the expression.</span></span>  
  
  <span data-ttu-id="09f3e-120">次の句を追加するすべての失敗したメッセージをサブスクライブするなど、(として、 **AND**句の他の句がある場合)。</span><span class="sxs-lookup"><span data-stu-id="09f3e-120">For example, to subscribe to all failed messages, you add the following clause (as an **AND** clause if there are other clauses):</span></span>  
  
  <span data-ttu-id="09f3e-121">Microsoft .Solutions.A4SWIFT.Property.A4SWIFT_Failed == **true**</span><span class="sxs-lookup"><span data-stu-id="09f3e-121">Microsoft .Solutions.A4SWIFT.Property.A4SWIFT_Failed == **true**</span></span>  
  
  <span data-ttu-id="09f3e-122">解析エラーのみを持つメッセージをサブスクライブするには、加算、次の句。</span><span class="sxs-lookup"><span data-stu-id="09f3e-122">To subscribe to messages with only parse failures, you add the following clauses together:</span></span>  
  
  <span data-ttu-id="09f3e-123">**AND** Microsoft。Solutions.A4SWIFT.Property.A4SWIFT_Failed = = **true**、**AND**Microsoft。Solutions.A4SWIFT.Property.A4SWIFT_XmlValidationErrors 0、= =**AND**Microsoft。Solutions.A4SWIFT.Property.A4SWIFT_BreValidationErrors; 0 = =</span><span class="sxs-lookup"><span data-stu-id="09f3e-123">**AND** Microsoft .Solutions.A4SWIFT.Property.A4SWIFT_Failed == **true**,**AND**Microsoft .Solutions.A4SWIFT.Property.A4SWIFT_XmlValidationErrors == 0,**AND**Microsoft .Solutions.A4SWIFT.Property.A4SWIFT_BreValidationErrors == 0;</span></span>  
  
  <span data-ttu-id="09f3e-124">逆に、送信ポートまたはオーケストレーションの有効なメッセージのみを処理するように設計の場合は、"**AND**Microsoft。Solutions.A4SWIFT.Property.A4SWIFT_Failed = = **false**"として、フィルター式の句。</span><span class="sxs-lookup"><span data-stu-id="09f3e-124">Conversely, for send ports or orchestrations designed to handle only valid messages, include "**AND**Microsoft .Solutions.A4SWIFT.Property.A4SWIFT_Failed == **false**" as a clause in their filter expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09f3e-125">サブスクリプションが重なっている場合、A4SWIFT はすべてのサブスクリプションを満たします。</span><span class="sxs-lookup"><span data-stu-id="09f3e-125">If subscriptions overlap, A4SWIFT will fulfill all subscriptions.</span></span> <span data-ttu-id="09f3e-126">つまり、(送信ポートまたはオーケストレーション) は、複数のサービスには、特定のメッセージによって実行されるフィルター式にある場合、このようなすべてのサービスは、同じメッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="09f3e-126">That is, if more than one service (send port or orchestration) has filter expressions fulfilled by a particular message, all such services will receive the same message.</span></span> <span data-ttu-id="09f3e-127">たとえば、送信ポートがすべて失敗したメッセージをサブスクライブすると、オーケストレーションは、解析エラー メッセージのみをサブスクライブ、両方のサブスクリプションが満たされる A4SWIFT でメッセージを処理するときに解析エラーが発生したときにします。</span><span class="sxs-lookup"><span data-stu-id="09f3e-127">For example, if a send port subscribes to all failed messages and an orchestration subscribes to only messages with parse failures, both subscriptions will be satisfied when A4SWIFT encounters parse errors when processing a message.</span></span> <span data-ttu-id="09f3e-128">サービス間でのサブスクリプションで不要な重複を排除してください。</span><span class="sxs-lookup"><span data-stu-id="09f3e-128">Be sure to eliminate unwanted overlaps in subscriptions across services.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="09f3e-129">A4SWIFT 受信メッセージを処理し、MessageBox データベースにそのメッセージを発行するメッセージがすべてのサブスクリプションを満たさない場合は、A4SWIFT はメッセージを中断、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]サブスクライバーがないことを示すエラー。</span><span class="sxs-lookup"><span data-stu-id="09f3e-129">If A4SWIFT receives and processes a message, and publishes that message to the MessageBox database, but the message does not satisfy any subscription, A4SWIFT will suspend the message with a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] error indicating a lack of subscribers.</span></span> <span data-ttu-id="09f3e-130">例では、すべてのメッセージをサブスクライブするサービスがある場合の"A4SWIFT_Failed false = ="、サービスがメッセージをサブスクライブしないが、場所"A4SWIFT_Failed true = ="、サブスクライバーがないのために解析に失敗したメッセージまたは検証を中断するが実際にします。</span><span class="sxs-lookup"><span data-stu-id="09f3e-130">For example, if you have a service subscribing to all messages "A4SWIFT_Failed == false", but no services subscribe to messages where "A4SWIFT_Failed == true", then messages that fail parsing or validation will indeed be suspended due to a lack of subscribers.</span></span> <span data-ttu-id="09f3e-131">実際にこのシナリオでは失敗したメッセージの従来の中断を模倣することができます。</span><span class="sxs-lookup"><span data-stu-id="09f3e-131">This scenario actually enables you to mimic traditional suspension of failed messages.</span></span> <span data-ttu-id="09f3e-132">中断したくないすべてのメッセージをサブスクライブすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="09f3e-132">Be sure to subscribe to all messages that you do not want to have suspended.</span></span> <span data-ttu-id="09f3e-133">BizTalk Server のヘルプを参照して、メッセージ ボックス データベースのサブスクリプションの詳細については、送信ポート、オーケストレーション、およびフィルター式。</span><span class="sxs-lookup"><span data-stu-id="09f3e-133">See BizTalk Server Help for additional details about MessageBox database subscriptions, send ports, orchestrations, and filter expressions.</span></span>  
  
 <span data-ttu-id="09f3e-134">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="09f3e-134">This section contains:</span></span>  
  
-   [<span data-ttu-id="09f3e-135">失敗したメッセージと ErrorCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="09f3e-135">Failed Messages and ErrorCollection Objects</span></span>](../../adapters-and-accelerators/accelerator-swift/failed-messages-and-errorcollection-objects.md)