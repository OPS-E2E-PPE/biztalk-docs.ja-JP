---
title: メッセージ キューのキュー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [MSMQ adapters], queue paths
- naming conventions, MSMQ adapters
- configuring [MSMQ adapters], naming conventions
- messages, queuing
- MSMQ adapters, troubleshooting
- MSMQ adapters, message queues
- configuring [MSMQ adapters], troubleshooting
- troubleshooting, queue paths [MSMQ adapters]
- naming conventions, queue paths [MSMQ adapters]
- configuring [MSMQ adapters], message queues
ms.assetid: b802348e-8543-4b06-a6e4-149b86139fb1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2f5c2d4861a59ded7c19da84d0ca0e6ded9ddfe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394560"
---
# <a name="message-queuing-queues"></a><span data-ttu-id="33924-102">メッセージ キューのキュー</span><span class="sxs-lookup"><span data-stu-id="33924-102">Message Queuing Queues</span></span>
<span data-ttu-id="33924-103">このセクションでは、MSMQ アダプターを使用するときに、Microsoft メッセージ キュー (MSMQ とも呼ばれます) のキューを指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="33924-103">This section describes how to specify Microsoft Message Queuing (also known as MSMQ) queues when you use the MSMQ adapter.</span></span> <span data-ttu-id="33924-104">パスを指定する規則について説明し、キューの指定にパスを変換することで形式名の役割についても説明します。</span><span class="sxs-lookup"><span data-stu-id="33924-104">It describes the conventions for specifying paths and also describes the role that format names play in translating paths into queue designations.</span></span>  
  
## <a name="queue-path-naming-conventions"></a><span data-ttu-id="33924-105">キューのパスの名前付け規則</span><span class="sxs-lookup"><span data-stu-id="33924-105">Queue Path Naming Conventions</span></span>  
 <span data-ttu-id="33924-106">キュー名は、パスが参照されている場合は、次の表に、名前付け規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="33924-106">If the queue name refers to a path, use the naming conventions in the following table.</span></span>  
  
|<span data-ttu-id="33924-107">**[キューの種類]**</span><span class="sxs-lookup"><span data-stu-id="33924-107">**Queue type**</span></span>|<span data-ttu-id="33924-108">**パスの構文**</span><span class="sxs-lookup"><span data-stu-id="33924-108">**Syntax for path**</span></span>|  
|--------------------|-------------------------|  
|<span data-ttu-id="33924-109">パブリック キュー</span><span class="sxs-lookup"><span data-stu-id="33924-109">Public queue</span></span>|<span data-ttu-id="33924-110">*Computername*\QueueName</span><span class="sxs-lookup"><span data-stu-id="33924-110">*Computername*\QueueName</span></span>|  
|<span data-ttu-id="33924-111">専用キュー</span><span class="sxs-lookup"><span data-stu-id="33924-111">Private queue</span></span>|<span data-ttu-id="33924-112">*Computername*\Private$\QueueName</span><span class="sxs-lookup"><span data-stu-id="33924-112">*Computername*\Private$\QueueName</span></span>|  
|<span data-ttu-id="33924-113">ジャーナル キュー</span><span class="sxs-lookup"><span data-stu-id="33924-113">Journal queue</span></span>|<span data-ttu-id="33924-114">*Computername*\QueueName\Journal$</span><span class="sxs-lookup"><span data-stu-id="33924-114">*Computername*\QueueName\Journal$</span></span>|  
|<span data-ttu-id="33924-115">コンピューター ジャーナル キュー**に注意してください。** 受信キューにのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="33924-115">Computer journal queue **Note:**  Use for receive queue only.</span></span>|<span data-ttu-id="33924-116">*Computername*\Journal$</span><span class="sxs-lookup"><span data-stu-id="33924-116">*Computername*\Journal$</span></span>|  
|<span data-ttu-id="33924-117">コンピューター配信不能キュー**に注意してください。** 受信キューにのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="33924-117">Computer dead-letter queue **Note:**  Use for receive queue only.</span></span>|<span data-ttu-id="33924-118">*Computername*\Deadletter$</span><span class="sxs-lookup"><span data-stu-id="33924-118">*Computername*\Deadletter$</span></span>|  
|<span data-ttu-id="33924-119">コンピューター トランザクション配信不能キュー**に注意してください。** 受信キューにのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="33924-119">Computer transaction dead-letter queue **Note:**  Use for receive queue only.</span></span>|<span data-ttu-id="33924-120">*Computername*\XactDeadletter$</span><span class="sxs-lookup"><span data-stu-id="33924-120">*Computername*\XactDeadletter$</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="33924-121">キューのパスは一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="33924-121">The path of the queue must be unique.</span></span>  
  
 <span data-ttu-id="33924-122">キュー名は、形式名が参照されている場合を示すかどうか、キュー、パブリックまたはプライベート キューとその他の識別子の GUID を生成後に、必要に応じて文字列の形式になります。</span><span class="sxs-lookup"><span data-stu-id="33924-122">If the queue name refers to a format name, it takes the form of a string that indicates whether a queue is public or private, followed by a generated GUID for the queue and other identifiers as needed.</span></span> <span data-ttu-id="33924-123">次の表に、名前付け規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="33924-123">Use the naming conventions in the following table.</span></span>  
  
|<span data-ttu-id="33924-124">**形式の種類**</span><span class="sxs-lookup"><span data-stu-id="33924-124">**Format type**</span></span>|<span data-ttu-id="33924-125">**形式名の構文**</span><span class="sxs-lookup"><span data-stu-id="33924-125">**Syntax for format name**</span></span>|  
|---------------------|--------------------------------|  
|<span data-ttu-id="33924-126">パブリック</span><span class="sxs-lookup"><span data-stu-id="33924-126">Public</span></span>|<span data-ttu-id="33924-127">*FormatName*:Public=QueueGUID</span><span class="sxs-lookup"><span data-stu-id="33924-127">*FormatName*:Public=QueueGUID</span></span>|  
|<span data-ttu-id="33924-128">[直接]</span><span class="sxs-lookup"><span data-stu-id="33924-128">Direct</span></span>|<span data-ttu-id="33924-129">*FormatName*:DIRECT=SPX:NetworkNumber:HostNumber\QueueName</span><span class="sxs-lookup"><span data-stu-id="33924-129">*FormatName*:DIRECT=SPX:NetworkNumber:HostNumber\QueueName</span></span><br /><br /> <span data-ttu-id="33924-130">*FormatName*:DIRECT=TCP:IPAddress\QueueName</span><span class="sxs-lookup"><span data-stu-id="33924-130">*FormatName*: DIRECT=TCP:IPAddress\QueueName</span></span><br /><br /> <span data-ttu-id="33924-131">*FormatName*:DIRECT=OS:ComputerName\QueueName</span><span class="sxs-lookup"><span data-stu-id="33924-131">*FormatName*: DIRECT=OS:ComputerName\QueueName</span></span>|  
  
 <span data-ttu-id="33924-132">送信ポートのキューのパスが配布リストの場合は、キューのパスの構文は。</span><span class="sxs-lookup"><span data-stu-id="33924-132">If the send port queue path is a distribution list, then the queue path syntax is:</span></span>  
  
 <span data-ttu-id="33924-133">DL = DistributionListGUID</span><span class="sxs-lookup"><span data-stu-id="33924-133">DL=DistributionListGUID</span></span>  
  
 <span data-ttu-id="33924-134">場合、送信または受信キューのパスが、HTTP または HTTPS の URL では、構文。</span><span class="sxs-lookup"><span data-stu-id="33924-134">If the send or receive queue path is an HTTP or HTTPS URL, then the syntax is:</span></span>  
  
 <span data-ttu-id="33924-135">形式名:direct = http://\<クライアント名\>/msmq/\<キュー名\></span><span class="sxs-lookup"><span data-stu-id="33924-135">FormatName:DIRECT=http://\<client name\>/msmq/\<queue name\></span></span>  
  
 <span data-ttu-id="33924-136">形式名:direct = https://\<クライアント名\>/msmq/\<キュー名\></span><span class="sxs-lookup"><span data-stu-id="33924-136">FormatName:DIRECT=https://\<client name\>/msmq/\<queue name\></span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33924-137">"msmq"は、メッセージ キューでは、インターネット インフォメーション サービス (IIS) が作成される仮想フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="33924-137">"msmq" is the virtual folder that Message Queuing creates in Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33924-138">メッセージを送信するのにのみ HTTP を使用できます。</span><span class="sxs-lookup"><span data-stu-id="33924-138">You can only use HTTP to send messages.</span></span> <span data-ttu-id="33924-139">キューが HTTP の直接形式名を使用して開かれている場合は、リモート コンピューター上のキューでメッセージを読み取ることができません。</span><span class="sxs-lookup"><span data-stu-id="33924-139">You cannot read messages in a queue on a remote computer if the queue is opened using an HTTP direct format name.</span></span> <span data-ttu-id="33924-140">ただし、まだメッセージを受信できます SOAP (形式の) リモート キューから HTTP を使用しないプライベートまたはパブリック キューのパスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="33924-140">However, you can still receive SOAP (formatted) messages from a remote queue by using the private or public queue path without HTTP.</span></span>  
  
 <span data-ttu-id="33924-141">キュー名はわかりやすいテキストを参照している場合、キューの指定した管理者をラベル付けし、ラベルを参照するキューのパスの構文は。</span><span class="sxs-lookup"><span data-stu-id="33924-141">If the queue name refers to a descriptive text label that the administrator specified for the queue, then the syntax of the queue path referring to this label is:</span></span>  
  
 <span data-ttu-id="33924-142">ラベル: MyQueue</span><span class="sxs-lookup"><span data-stu-id="33924-142">LABEL:MyQueue</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33924-143">ラベルは常に一意ではありません。</span><span class="sxs-lookup"><span data-stu-id="33924-143">Labels are not always unique.</span></span> <span data-ttu-id="33924-144">そのため、そのラベルを使用して、特定のキューに接続しようとすると、名前の競合が存在する場合、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="33924-144">Therefore, you will receive an error if a name conflict exists when you try to connect to a specific queue by using its label.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33924-145">ラベルは、アダプターの必須のトランスポート フィールドです。</span><span class="sxs-lookup"><span data-stu-id="33924-145">The label is a required transport field for the adapter.</span></span>  
  
## <a name="role-of-the-format-name"></a><span data-ttu-id="33924-146">形式名の役割</span><span class="sxs-lookup"><span data-stu-id="33924-146">Role of the Format Name</span></span>  
 <span data-ttu-id="33924-147">メッセージ キューは、キューを識別するために、それにアクセスする方法を決定する、形式名を使用します。</span><span class="sxs-lookup"><span data-stu-id="33924-147">Message Queuing uses the format name to identify a queue and to determine how to access it.</span></span> <span data-ttu-id="33924-148">メッセージ キューは、キューに形式名を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="33924-148">Message Queuing assigns the format name to the queue.</span></span>  
  
 <span data-ttu-id="33924-149">たとえばパス名の構文を使用してキューを指定すると、myMachine\myQueue、メッセージ キューは関連付けられている形式名を検索するパスを検索します。</span><span class="sxs-lookup"><span data-stu-id="33924-149">When you specify a queue using the path name syntax, for example myMachine\myQueue, Message Queuing looks up the path to find the associated format name.</span></span> <span data-ttu-id="33924-150">後、メッセージ キューは、その形式名を使用して、キューにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="33924-150">Message Queuing then uses that format name to access the queue.</span></span> <span data-ttu-id="33924-151">形式名を指定する場合はメッセージ キューを使用する形式名を使用します。</span><span class="sxs-lookup"><span data-stu-id="33924-151">When you specify the format name, Message Queuing uses the format name you use.</span></span>  
  
 <span data-ttu-id="33924-152">形式名の詳細については、.NET Framework クラス ライブラリのヘルプ「「MessageQueue.FormatName プロパティ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33924-152">For more information about format names, see "MessageQueue.FormatName Property" in .NET Framework Class Library Help.</span></span>  
  
## <a name="troubleshooting-queue-paths"></a><span data-ttu-id="33924-153">キューのパスのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="33924-153">Troubleshooting Queue Paths</span></span>  
  
-   <span data-ttu-id="33924-154">例外は、指定されたキューのパスの構文は「キューのパスの名前付け規則」で既に説明した形式のいずれかが一致しない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="33924-154">An exception occurs if the syntax of the provided queue path does not match one of the formats described earlier in "Queue Path Naming Conventions."</span></span>  
  
-   <span data-ttu-id="33924-155">次に、いないキューのパスでコンピューター名の有効な文字。</span><span class="sxs-lookup"><span data-stu-id="33924-155">The following are not valid characters for computer names in the queue path:</span></span>  
  
     <span data-ttu-id="33924-156">\ ; , + "</span><span class="sxs-lookup"><span data-stu-id="33924-156">\ ; , + "</span></span>  
  
     <span data-ttu-id="33924-157">例外は、コンピューター名が数値の場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="33924-157">An exception occurs if the computer name is a number.</span></span> <span data-ttu-id="33924-158">例 :234\private$\queue.</span><span class="sxs-lookup"><span data-stu-id="33924-158">For example: 234\private$\queue.</span></span>  
  
-   <span data-ttu-id="33924-159">コンピューター配信不能メッセージ キュー、コンピュータ ジャーナル キュー、およびコンピューター トランザクション配信不能キューは、ユーザーの送信先のキューととしてシステム キューのいずれかが指定されている場合、例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="33924-159">For a computer dead-letter queue, computer journal queue, and computer transaction dead-letter queue, an exception occurs if the user specifies any one of the system queues as the destination queue for send.</span></span>  
  
-   <span data-ttu-id="33924-160">**System.Messaging.MessageQueue.Exists**リモート キューは機能しません。</span><span class="sxs-lookup"><span data-stu-id="33924-160">**System.Messaging.MessageQueue.Exists** does not work for remote queues.</span></span> <span data-ttu-id="33924-161">詳細については、.NET Framework クラス ライブラリのヘルプ「「MessageQueue.Exists メソッド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33924-161">For more information, see "MessageQueue.Exists Method" in .NET Framework Class Library Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33924-162">参照</span><span class="sxs-lookup"><span data-stu-id="33924-162">See Also</span></span>  
 [<span data-ttu-id="33924-163">MSMQ アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="33924-163">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)