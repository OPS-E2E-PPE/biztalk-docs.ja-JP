---
title: メッセージ キューのキュー |Microsoft ドキュメント
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
ms.openlocfilehash: fa8d2521a8cf434c7a0ea56f749f9df3f032551e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971464"
---
# <a name="message-queuing-queues"></a><span data-ttu-id="052cb-102">メッセージ キューのキュー</span><span class="sxs-lookup"><span data-stu-id="052cb-102">Message Queuing Queues</span></span>
<span data-ttu-id="052cb-103">このセクションでは、Microsoft メッセージ キュー (MSMQ) アダプタを使用する際に、MSMQ キューを指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="052cb-103">This section describes how to specify Microsoft Message Queuing (also known as MSMQ) queues when you use the MSMQ adapter.</span></span> <span data-ttu-id="052cb-104">パスを指定するための名前付け規則、およびパスをキューの指定に変換するときの形式名の役割についても説明します。</span><span class="sxs-lookup"><span data-stu-id="052cb-104">It describes the conventions for specifying paths and also describes the role that format names play in translating paths into queue designations.</span></span>  
  
## <a name="queue-path-naming-conventions"></a><span data-ttu-id="052cb-105">キューのパスの名前付け規則</span><span class="sxs-lookup"><span data-stu-id="052cb-105">Queue Path Naming Conventions</span></span>  
 <span data-ttu-id="052cb-106">キュー名でパスを参照する場合、次の表の名前付け規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="052cb-106">If the queue name refers to a path, use the naming conventions in the following table.</span></span>  
  
|<span data-ttu-id="052cb-107">**[キューの種類]**</span><span class="sxs-lookup"><span data-stu-id="052cb-107">**Queue type**</span></span>|<span data-ttu-id="052cb-108">**パスの構文**</span><span class="sxs-lookup"><span data-stu-id="052cb-108">**Syntax for path**</span></span>|  
|--------------------|-------------------------|  
|<span data-ttu-id="052cb-109">パブリック キュー</span><span class="sxs-lookup"><span data-stu-id="052cb-109">Public queue</span></span>|<span data-ttu-id="052cb-110">*Computername*\QueueName</span><span class="sxs-lookup"><span data-stu-id="052cb-110">*Computername*\QueueName</span></span>|  
|<span data-ttu-id="052cb-111">専用キュー</span><span class="sxs-lookup"><span data-stu-id="052cb-111">Private queue</span></span>|<span data-ttu-id="052cb-112">*Computername*\Private$\QueueName</span><span class="sxs-lookup"><span data-stu-id="052cb-112">*Computername*\Private$\QueueName</span></span>|  
|<span data-ttu-id="052cb-113">ジャーナル キュー</span><span class="sxs-lookup"><span data-stu-id="052cb-113">Journal queue</span></span>|<span data-ttu-id="052cb-114">*Computername*\QueueName\Journal$</span><span class="sxs-lookup"><span data-stu-id="052cb-114">*Computername*\QueueName\Journal$</span></span>|  
|<span data-ttu-id="052cb-115">コンピューター ジャーナル キュー**注:** 受信キューにのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="052cb-115">Computer journal queue **Note:**  Use for receive queue only.</span></span>|<span data-ttu-id="052cb-116">*Computername*\Journal$</span><span class="sxs-lookup"><span data-stu-id="052cb-116">*Computername*\Journal$</span></span>|  
|<span data-ttu-id="052cb-117">コンピューターの配信不能キュー**注:** 受信キューにのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="052cb-117">Computer dead-letter queue **Note:**  Use for receive queue only.</span></span>|<span data-ttu-id="052cb-118">*Computername*\Deadletter$</span><span class="sxs-lookup"><span data-stu-id="052cb-118">*Computername*\Deadletter$</span></span>|  
|<span data-ttu-id="052cb-119">コンピューター トランザクション配信不能キュー**注:** 受信キューにのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="052cb-119">Computer transaction dead-letter queue **Note:**  Use for receive queue only.</span></span>|<span data-ttu-id="052cb-120">*Computername*\XactDeadletter$</span><span class="sxs-lookup"><span data-stu-id="052cb-120">*Computername*\XactDeadletter$</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="052cb-121">キューのパスは、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="052cb-121">The path of the queue must be unique.</span></span>  
  
 <span data-ttu-id="052cb-122">キュー名で形式名を参照する場合、形式名は、キューがパブリックかプライベートかを示す文字列から始まり、キューに対して生成された GUID、および必要に応じてその他の識別子が続きます。</span><span class="sxs-lookup"><span data-stu-id="052cb-122">If the queue name refers to a format name, it takes the form of a string that indicates whether a queue is public or private, followed by a generated GUID for the queue and other identifiers as needed.</span></span> <span data-ttu-id="052cb-123">次の表の名前付け規則を使用してください。</span><span class="sxs-lookup"><span data-stu-id="052cb-123">Use the naming conventions in the following table.</span></span>  
  
|<span data-ttu-id="052cb-124">**形式の種類**</span><span class="sxs-lookup"><span data-stu-id="052cb-124">**Format type**</span></span>|<span data-ttu-id="052cb-125">**形式名の構文**</span><span class="sxs-lookup"><span data-stu-id="052cb-125">**Syntax for format name**</span></span>|  
|---------------------|--------------------------------|  
|<span data-ttu-id="052cb-126">パブリック</span><span class="sxs-lookup"><span data-stu-id="052cb-126">Public</span></span>|<span data-ttu-id="052cb-127">*FormatName*: パブリック:public =</span><span class="sxs-lookup"><span data-stu-id="052cb-127">*FormatName*:Public=QueueGUID</span></span>|  
|<span data-ttu-id="052cb-128">[直接]</span><span class="sxs-lookup"><span data-stu-id="052cb-128">Direct</span></span>|<span data-ttu-id="052cb-129">*FormatName*: DIRECT = SPX:NetworkNumber:HostNumber\QueueName</span><span class="sxs-lookup"><span data-stu-id="052cb-129">*FormatName*:DIRECT=SPX:NetworkNumber:HostNumber\QueueName</span></span><br /><br /> <span data-ttu-id="052cb-130">*FormatName*: DIRECT = TCP:IPAddress\QueueName</span><span class="sxs-lookup"><span data-stu-id="052cb-130">*FormatName*: DIRECT=TCP:IPAddress\QueueName</span></span><br /><br /> <span data-ttu-id="052cb-131">*FormatName*: DIRECT = OS:ComputerName\QueueName</span><span class="sxs-lookup"><span data-stu-id="052cb-131">*FormatName*: DIRECT=OS:ComputerName\QueueName</span></span>|  
  
 <span data-ttu-id="052cb-132">送信ポートのキューのパスが同報リストである場合、キューのパスの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="052cb-132">If the send port queue path is a distribution list, then the queue path syntax is:</span></span>  
  
 <span data-ttu-id="052cb-133">DL=同報リストの GUID</span><span class="sxs-lookup"><span data-stu-id="052cb-133">DL=DistributionListGUID</span></span>  
  
 <span data-ttu-id="052cb-134">送信または受信キューのパスが、HTTP または HTTPS の URL である場合、構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="052cb-134">If the send or receive queue path is an HTTP or HTTPS URL, then the syntax is:</span></span>  
  
 <span data-ttu-id="052cb-135">形式名:direct = http://\<クライアント名\>/msmq/\<キュー名\></span><span class="sxs-lookup"><span data-stu-id="052cb-135">FormatName:DIRECT=http://\<client name\>/msmq/\<queue name\></span></span>  
  
 <span data-ttu-id="052cb-136">形式名:direct = https://\<クライアント名\>/msmq/\<キュー名\></span><span class="sxs-lookup"><span data-stu-id="052cb-136">FormatName:DIRECT=https://\<client name\>/msmq/\<queue name\></span></span>  
  
> [!NOTE]
>  <span data-ttu-id="052cb-137">"msmq" は、メッセージ キューによってインターネット インフォメーション サービス (IIS) に作成される仮想フォルダです。</span><span class="sxs-lookup"><span data-stu-id="052cb-137">"msmq" is the virtual folder that Message Queuing creates in Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="052cb-138">HTTP は、メッセージの送信のみに使用できます。</span><span class="sxs-lookup"><span data-stu-id="052cb-138">You can only use HTTP to send messages.</span></span> <span data-ttu-id="052cb-139">リモート コンピューターのキューのメッセージは、キューが HTTP の直接形式名を使用して開かれている場合は、読み取ることができません。</span><span class="sxs-lookup"><span data-stu-id="052cb-139">You cannot read messages in a queue on a remote computer if the queue is opened using an HTTP direct format name.</span></span> <span data-ttu-id="052cb-140">HTTP を使用しない専用キューまたはパブリック キューのパスを使用して、リモート キューの SOAP (形式の) メッセージを受信することはできます。</span><span class="sxs-lookup"><span data-stu-id="052cb-140">However, you can still receive SOAP (formatted) messages from a remote queue by using the private or public queue path without HTTP.</span></span>  
  
 <span data-ttu-id="052cb-141">管理者がキューに指定した説明的なテキスト ラベルをキュー名で参照している場合、そのラベルを参照するキューのパスの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="052cb-141">If the queue name refers to a descriptive text label that the administrator specified for the queue, then the syntax of the queue path referring to this label is:</span></span>  
  
 <span data-ttu-id="052cb-142">LABEL:MyQueue</span><span class="sxs-lookup"><span data-stu-id="052cb-142">LABEL:MyQueue</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="052cb-143">ラベルは一意とは限りません。</span><span class="sxs-lookup"><span data-stu-id="052cb-143">Labels are not always unique.</span></span> <span data-ttu-id="052cb-144">そのため、ラベルを使用して特定のキューに接続しようとしたときに名前の競合があると、エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="052cb-144">Therefore, you will receive an error if a name conflict exists when you try to connect to a specific queue by using its label.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="052cb-145">ラベルはアダプタの必須のトランスポート フィールドです。</span><span class="sxs-lookup"><span data-stu-id="052cb-145">The label is a required transport field for the adapter.</span></span>  
  
## <a name="role-of-the-format-name"></a><span data-ttu-id="052cb-146">形式名の役割</span><span class="sxs-lookup"><span data-stu-id="052cb-146">Role of the Format Name</span></span>  
 <span data-ttu-id="052cb-147">形式名は、キューを識別し、キューへのアクセス方法を特定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="052cb-147">Message Queuing uses the format name to identify a queue and to determine how to access it.</span></span> <span data-ttu-id="052cb-148">形式名はメッセージ キューによってキューに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="052cb-148">Message Queuing assigns the format name to the queue.</span></span>  
  
 <span data-ttu-id="052cb-149">"コンピュータ名\キュー名" など、パス名の構文を使用してキューを指定するとき、メッセージ キューはパスを検索して関連する形式名を検出します。</span><span class="sxs-lookup"><span data-stu-id="052cb-149">When you specify a queue using the path name syntax, for example myMachine\myQueue, Message Queuing looks up the path to find the associated format name.</span></span> <span data-ttu-id="052cb-150">その後、形式名を使用してキューにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="052cb-150">Message Queuing then uses that format name to access the queue.</span></span> <span data-ttu-id="052cb-151">形式名を指定すると、メッセージ キューではその形式名が使用されます。</span><span class="sxs-lookup"><span data-stu-id="052cb-151">When you specify the format name, Message Queuing uses the format name you use.</span></span>  
  
 <span data-ttu-id="052cb-152">形式名の詳細については、.NET Framework クラス ライブラリ ヘルプの「MessageQueue.FormatName プロパティ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="052cb-152">For more information about format names, see "MessageQueue.FormatName Property" in .NET Framework Class Library Help.</span></span>  
  
## <a name="troubleshooting-queue-paths"></a><span data-ttu-id="052cb-153">キューのパスに関するトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="052cb-153">Troubleshooting Queue Paths</span></span>  
  
-   <span data-ttu-id="052cb-154">指定したキューのパスの構文が、前半の「キューのパスの名前付け規則」に記載した形式のいずれとも一致しない場合、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="052cb-154">An exception occurs if the syntax of the provided queue path does not match one of the formats described earlier in "Queue Path Naming Conventions."</span></span>  
  
-   <span data-ttu-id="052cb-155">キューのパスのコンピュータ名には、以下の文字は無効です。</span><span class="sxs-lookup"><span data-stu-id="052cb-155">The following are not valid characters for computer names in the queue path:</span></span>  
  
     <span data-ttu-id="052cb-156">\ ; , + "</span><span class="sxs-lookup"><span data-stu-id="052cb-156">\ ; , + "</span></span>  
  
     <span data-ttu-id="052cb-157">コンピュータ名が数字である場合、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="052cb-157">An exception occurs if the computer name is a number.</span></span> <span data-ttu-id="052cb-158">例: 234\private$ \queue です。</span><span class="sxs-lookup"><span data-stu-id="052cb-158">For example: 234\private$\queue.</span></span>  
  
-   <span data-ttu-id="052cb-159">コンピュータの配信不能キュー、コンピュータ ジャーナル キュー、およびコンピュータのトランザクション配信不能キューを使用する場合、ユーザーが送信先のキューとしてシステム キューを指定すると、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="052cb-159">For a computer dead-letter queue, computer journal queue, and computer transaction dead-letter queue, an exception occurs if the user specifies any one of the system queues as the destination queue for send.</span></span>  
  
-   <span data-ttu-id="052cb-160">**System.Messaging.MessageQueue.Exists**リモート キューでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="052cb-160">**System.Messaging.MessageQueue.Exists** does not work for remote queues.</span></span> <span data-ttu-id="052cb-161">詳細については、.NET Framework クラス ライブラリ ヘルプの「MessageQueue.Exists メソッド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="052cb-161">For more information, see "MessageQueue.Exists Method" in .NET Framework Class Library Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="052cb-162">参照</span><span class="sxs-lookup"><span data-stu-id="052cb-162">See Also</span></span>  
 [<span data-ttu-id="052cb-163">MSMQ アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="052cb-163">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)