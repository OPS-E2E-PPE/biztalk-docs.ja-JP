---
title: タスク 3:Shapes2 の受信し、送信の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ebe7141-f2bd-4e6a-9204-d61bd64286af
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea0f66b7604f2cc03596bcf8d9c458b40349c9ed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399240"
---
# <a name="task-3-configure-the-send-and-receive-shapes"></a><span data-ttu-id="9be64-102">タスク 3:受信図形と送信の構成</span><span class="sxs-lookup"><span data-stu-id="9be64-102">Task 3: Configure the Send and Receive Shapes</span></span>
<span data-ttu-id="9be64-103">受信図形と送信を構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="9be64-103">Use the following procedure to configure the Send and Receive shapes.</span></span>  
  
### <a name="to-configure-the-send-and-receive-shapes"></a><span data-ttu-id="9be64-104">受信図形と送信を構成するには</span><span class="sxs-lookup"><span data-stu-id="9be64-104">To configure the Send and Receive shapes</span></span>  
  
1.  <span data-ttu-id="9be64-105">送信をドラッグし、受信図形をツールボックスから、次の順序でオーケストレーションの中心にします。</span><span class="sxs-lookup"><span data-stu-id="9be64-105">Drag Send and Receive shapes from the tool box into the center of the orchestration in the following order.</span></span>  
  
2.  <span data-ttu-id="9be64-106">次のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="9be64-106">Set the following parameters:</span></span>  
  
    |<span data-ttu-id="9be64-107">図形</span><span class="sxs-lookup"><span data-stu-id="9be64-107">Shape</span></span>|<span data-ttu-id="9be64-108">名前</span><span class="sxs-lookup"><span data-stu-id="9be64-108">Name</span></span>|<span data-ttu-id="9be64-109">設定</span><span class="sxs-lookup"><span data-stu-id="9be64-109">Setting</span></span>|  
    |-----------|----------|-------------|  
    |<span data-ttu-id="9be64-110">[Receive1]</span><span class="sxs-lookup"><span data-stu-id="9be64-110">Receive1</span></span>|<span data-ttu-id="9be64-111">Activate</span><span class="sxs-lookup"><span data-stu-id="9be64-111">Activate</span></span>|<span data-ttu-id="9be64-112">True</span><span class="sxs-lookup"><span data-stu-id="9be64-112">True</span></span>|  
    ||<span data-ttu-id="9be64-113">メッセージ</span><span class="sxs-lookup"><span data-stu-id="9be64-113">Message</span></span>|<span data-ttu-id="9be64-114">BeginDocMsg</span><span class="sxs-lookup"><span data-stu-id="9be64-114">BeginDocMsg</span></span>|  
    ||<span data-ttu-id="9be64-115">名前</span><span class="sxs-lookup"><span data-stu-id="9be64-115">Name</span></span>|<span data-ttu-id="9be64-116">ReceiveBeginDoc</span><span class="sxs-lookup"><span data-stu-id="9be64-116">ReceiveBeginDoc</span></span>|  
    ||<span data-ttu-id="9be64-117">操作</span><span class="sxs-lookup"><span data-stu-id="9be64-117">Operation</span></span>|<span data-ttu-id="9be64-118">BeginDoc.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="9be64-118">BeginDoc.Operation_1.Request</span></span>|  
    |<span data-ttu-id="9be64-119">[Send1]</span><span class="sxs-lookup"><span data-stu-id="9be64-119">Send1</span></span>|<span data-ttu-id="9be64-120">メッセージ</span><span class="sxs-lookup"><span data-stu-id="9be64-120">Message</span></span>|<span data-ttu-id="9be64-121">BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="9be64-121">BeginDocSessionMsg</span></span>|  
    ||<span data-ttu-id="9be64-122">名前</span><span class="sxs-lookup"><span data-stu-id="9be64-122">Name</span></span>|<span data-ttu-id="9be64-123">SendBeginDoc</span><span class="sxs-lookup"><span data-stu-id="9be64-123">SendBeginDoc</span></span>|  
    ||<span data-ttu-id="9be64-124">操作</span><span class="sxs-lookup"><span data-stu-id="9be64-124">Operation</span></span>|<span data-ttu-id="9be64-125">JDEPort.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="9be64-125">JDEPort.Operation_1.Request</span></span>|  
    |<span data-ttu-id="9be64-126">Receive2</span><span class="sxs-lookup"><span data-stu-id="9be64-126">Receive2</span></span>|<span data-ttu-id="9be64-127">Activate</span><span class="sxs-lookup"><span data-stu-id="9be64-127">Activate</span></span>|<span data-ttu-id="9be64-128">False</span><span class="sxs-lookup"><span data-stu-id="9be64-128">False</span></span>|  
    ||<span data-ttu-id="9be64-129">メッセージ</span><span class="sxs-lookup"><span data-stu-id="9be64-129">Message</span></span>|<span data-ttu-id="9be64-130">BeginDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="9be64-130">BeginDocResponseMsg</span></span>|  
    ||<span data-ttu-id="9be64-131">名前</span><span class="sxs-lookup"><span data-stu-id="9be64-131">Name</span></span>|<span data-ttu-id="9be64-132">ReceiveBeginDocResponse</span><span class="sxs-lookup"><span data-stu-id="9be64-132">ReceiveBeginDocResponse</span></span>|  
    ||<span data-ttu-id="9be64-133">操作</span><span class="sxs-lookup"><span data-stu-id="9be64-133">Operation</span></span>|<span data-ttu-id="9be64-134">JDEPort.Operation_1.Response</span><span class="sxs-lookup"><span data-stu-id="9be64-134">JDEPort.Operation_1.Response</span></span>|  
    |<span data-ttu-id="9be64-135">[Send2]</span><span class="sxs-lookup"><span data-stu-id="9be64-135">Send2</span></span>|<span data-ttu-id="9be64-136">メッセージ</span><span class="sxs-lookup"><span data-stu-id="9be64-136">Message</span></span>|<span data-ttu-id="9be64-137">EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="9be64-137">EditLineSessionMsg</span></span>|  
    ||<span data-ttu-id="9be64-138">名前</span><span class="sxs-lookup"><span data-stu-id="9be64-138">Name</span></span>|<span data-ttu-id="9be64-139">SendEditLine</span><span class="sxs-lookup"><span data-stu-id="9be64-139">SendEditLine</span></span>|  
    ||<span data-ttu-id="9be64-140">操作</span><span class="sxs-lookup"><span data-stu-id="9be64-140">Operation</span></span>|<span data-ttu-id="9be64-141">JDEPort.Operation_2.Request</span><span class="sxs-lookup"><span data-stu-id="9be64-141">JDEPort.Operation_2.Request</span></span>|  
    |<span data-ttu-id="9be64-142">Receive3</span><span class="sxs-lookup"><span data-stu-id="9be64-142">Receive3</span></span>|<span data-ttu-id="9be64-143">Activate</span><span class="sxs-lookup"><span data-stu-id="9be64-143">Activate</span></span>|<span data-ttu-id="9be64-144">False</span><span class="sxs-lookup"><span data-stu-id="9be64-144">False</span></span>|  
    ||<span data-ttu-id="9be64-145">メッセージ</span><span class="sxs-lookup"><span data-stu-id="9be64-145">Message</span></span>|<span data-ttu-id="9be64-146">EditLineResponseMsg</span><span class="sxs-lookup"><span data-stu-id="9be64-146">EditLineResponseMsg</span></span>|  
    ||<span data-ttu-id="9be64-147">名前</span><span class="sxs-lookup"><span data-stu-id="9be64-147">Name</span></span>|<span data-ttu-id="9be64-148">ReceiveEditLine</span><span class="sxs-lookup"><span data-stu-id="9be64-148">ReceiveEditLine</span></span>|  
    ||<span data-ttu-id="9be64-149">操作</span><span class="sxs-lookup"><span data-stu-id="9be64-149">Operation</span></span>|<span data-ttu-id="9be64-150">JDEPort.Operation_2.Response</span><span class="sxs-lookup"><span data-stu-id="9be64-150">JDEPort.Operation_2.Response</span></span>|  
    |<span data-ttu-id="9be64-151">[Send3]</span><span class="sxs-lookup"><span data-stu-id="9be64-151">Send3</span></span>|<span data-ttu-id="9be64-152">メッセージ</span><span class="sxs-lookup"><span data-stu-id="9be64-152">Message</span></span>|<span data-ttu-id="9be64-153">EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="9be64-153">EndDocSessionMsg</span></span>|  
    ||<span data-ttu-id="9be64-154">名前</span><span class="sxs-lookup"><span data-stu-id="9be64-154">Name</span></span>|<span data-ttu-id="9be64-155">SendEndDoc</span><span class="sxs-lookup"><span data-stu-id="9be64-155">SendEndDoc</span></span>|  
    ||<span data-ttu-id="9be64-156">操作</span><span class="sxs-lookup"><span data-stu-id="9be64-156">Operation</span></span>|<span data-ttu-id="9be64-157">JDEPort.Operation_3.Request</span><span class="sxs-lookup"><span data-stu-id="9be64-157">JDEPort.Operation_3.Request</span></span>|  
    |<span data-ttu-id="9be64-158">Receive4</span><span class="sxs-lookup"><span data-stu-id="9be64-158">Receive4</span></span>|<span data-ttu-id="9be64-159">Activate</span><span class="sxs-lookup"><span data-stu-id="9be64-159">Activate</span></span>|<span data-ttu-id="9be64-160">False</span><span class="sxs-lookup"><span data-stu-id="9be64-160">False</span></span>|  
    ||<span data-ttu-id="9be64-161">メッセージ</span><span class="sxs-lookup"><span data-stu-id="9be64-161">Message</span></span>|<span data-ttu-id="9be64-162">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="9be64-162">EndDocResponseMsg</span></span>|  
    ||<span data-ttu-id="9be64-163">名前</span><span class="sxs-lookup"><span data-stu-id="9be64-163">Name</span></span>|<span data-ttu-id="9be64-164">ReceiveEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="9be64-164">ReceiveEndDocResponse</span></span>|  
    ||<span data-ttu-id="9be64-165">操作</span><span class="sxs-lookup"><span data-stu-id="9be64-165">Operation</span></span>|<span data-ttu-id="9be64-166">JDEPort.Operation_3.Response</span><span class="sxs-lookup"><span data-stu-id="9be64-166">JDEPort.Operation_3.Response</span></span>|  
    |<span data-ttu-id="9be64-167">Send4</span><span class="sxs-lookup"><span data-stu-id="9be64-167">Send4</span></span>|<span data-ttu-id="9be64-168">メッセージ</span><span class="sxs-lookup"><span data-stu-id="9be64-168">Message</span></span>|<span data-ttu-id="9be64-169">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="9be64-169">EndDocResponseMsg</span></span>|  
    ||<span data-ttu-id="9be64-170">名前</span><span class="sxs-lookup"><span data-stu-id="9be64-170">Name</span></span>|<span data-ttu-id="9be64-171">SendEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="9be64-171">SendEndDocResponse</span></span>|  
    ||<span data-ttu-id="9be64-172">操作</span><span class="sxs-lookup"><span data-stu-id="9be64-172">Operation</span></span>|<span data-ttu-id="9be64-173">EndDocOut.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="9be64-173">EndDocOut.Operation_1.Request</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9be64-174">参照</span><span class="sxs-lookup"><span data-stu-id="9be64-174">See Also</span></span>  
 <span data-ttu-id="9be64-175">[タスク 1:ポートを作成します。](../core/task-1-create-the-ports1.md) </span><span class="sxs-lookup"><span data-stu-id="9be64-175">[Task 1: Create the Ports](../core/task-1-create-the-ports1.md) </span></span>  
 <span data-ttu-id="9be64-176">[タスク 2:メッセージを作成します。](../core/task-2-create-the-messages2.md) </span><span class="sxs-lookup"><span data-stu-id="9be64-176">[Task 2: Create the Messages](../core/task-2-create-the-messages2.md) </span></span>  
 <span data-ttu-id="9be64-177">[タスク 4:メッセージの構築図形を構成します。](../core/task-4-configure-the-construct-message-shape1.md) </span><span class="sxs-lookup"><span data-stu-id="9be64-177">[Task 4: Configure the Construct Message Shape](../core/task-4-configure-the-construct-message-shape1.md) </span></span>  
 [<span data-ttu-id="9be64-178">タスク 5:変換図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="9be64-178">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape2.md)