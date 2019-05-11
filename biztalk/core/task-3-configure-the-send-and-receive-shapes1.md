---
title: タスク 3:Shapes1 の受信し、送信の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e258d22-755b-48a4-9f9e-e9398f6b68b1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8621f5d4aa6cb9d15caf708b7089ca2c1aab82c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399249"
---
# <a name="task-3-configure-the-send-and-receive-shapes"></a><span data-ttu-id="25720-102">タスク 3:受信図形と送信の構成</span><span class="sxs-lookup"><span data-stu-id="25720-102">Task 3: Configure the Send and Receive Shapes</span></span>
<span data-ttu-id="25720-103">受信図形と送信を構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="25720-103">Use the following procedure to configure the Send and Receive shapes.</span></span>  
  
### <a name="to-configure-the-send-and-receive-shapes"></a><span data-ttu-id="25720-104">受信図形と送信を構成するには</span><span class="sxs-lookup"><span data-stu-id="25720-104">To configure the Send and Receive shapes</span></span>  
  
1.  <span data-ttu-id="25720-105">送信をドラッグし、受信図形をツールボックスから、次の順序でオーケストレーションの中心にします。</span><span class="sxs-lookup"><span data-stu-id="25720-105">Drag Send and Receive shapes from the tool box into the center of the orchestration in the following order.</span></span>  
  
2.  <span data-ttu-id="25720-106">次のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="25720-106">Set the following parameters:</span></span>  
  
    |<span data-ttu-id="25720-107">図形</span><span class="sxs-lookup"><span data-stu-id="25720-107">Shape</span></span>|<span data-ttu-id="25720-108">名前</span><span class="sxs-lookup"><span data-stu-id="25720-108">Name</span></span>|<span data-ttu-id="25720-109">設定</span><span class="sxs-lookup"><span data-stu-id="25720-109">Setting</span></span>|  
    |-----------|----------|-------------|  
    |<span data-ttu-id="25720-110">[Receive1]</span><span class="sxs-lookup"><span data-stu-id="25720-110">Receive1</span></span>|<span data-ttu-id="25720-111">Activate</span><span class="sxs-lookup"><span data-stu-id="25720-111">Activate</span></span>|<span data-ttu-id="25720-112">True</span><span class="sxs-lookup"><span data-stu-id="25720-112">True</span></span>|  
    ||<span data-ttu-id="25720-113">メッセージ</span><span class="sxs-lookup"><span data-stu-id="25720-113">Message</span></span>|<span data-ttu-id="25720-114">BeginDocMsg</span><span class="sxs-lookup"><span data-stu-id="25720-114">BeginDocMsg</span></span>|  
    ||<span data-ttu-id="25720-115">名前</span><span class="sxs-lookup"><span data-stu-id="25720-115">Name</span></span>|<span data-ttu-id="25720-116">ReceiveBeginDoc</span><span class="sxs-lookup"><span data-stu-id="25720-116">ReceiveBeginDoc</span></span>|  
    ||<span data-ttu-id="25720-117">操作</span><span class="sxs-lookup"><span data-stu-id="25720-117">Operation</span></span>|<span data-ttu-id="25720-118">BeginDoc.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="25720-118">BeginDoc.Operation_1.Request</span></span>|  
    |<span data-ttu-id="25720-119">[Send1]</span><span class="sxs-lookup"><span data-stu-id="25720-119">Send1</span></span>|<span data-ttu-id="25720-120">メッセージ</span><span class="sxs-lookup"><span data-stu-id="25720-120">Message</span></span>|<span data-ttu-id="25720-121">BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="25720-121">BeginDocSessionMsg</span></span>|  
    ||<span data-ttu-id="25720-122">名前</span><span class="sxs-lookup"><span data-stu-id="25720-122">Name</span></span>|<span data-ttu-id="25720-123">SendBeginDoc</span><span class="sxs-lookup"><span data-stu-id="25720-123">SendBeginDoc</span></span>|  
    ||<span data-ttu-id="25720-124">操作</span><span class="sxs-lookup"><span data-stu-id="25720-124">Operation</span></span>|<span data-ttu-id="25720-125">JDEPort.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="25720-125">JDEPort.Operation_1.Request</span></span>|  
    |<span data-ttu-id="25720-126">Receive2</span><span class="sxs-lookup"><span data-stu-id="25720-126">Receive2</span></span>|<span data-ttu-id="25720-127">Activate</span><span class="sxs-lookup"><span data-stu-id="25720-127">Activate</span></span>|<span data-ttu-id="25720-128">False</span><span class="sxs-lookup"><span data-stu-id="25720-128">False</span></span>|  
    ||<span data-ttu-id="25720-129">メッセージ</span><span class="sxs-lookup"><span data-stu-id="25720-129">Message</span></span>|<span data-ttu-id="25720-130">BeginDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="25720-130">BeginDocResponseMsg</span></span>|  
    ||<span data-ttu-id="25720-131">名前</span><span class="sxs-lookup"><span data-stu-id="25720-131">Name</span></span>|<span data-ttu-id="25720-132">ReceiveBeginDocResponse</span><span class="sxs-lookup"><span data-stu-id="25720-132">ReceiveBeginDocResponse</span></span>|  
    ||<span data-ttu-id="25720-133">操作</span><span class="sxs-lookup"><span data-stu-id="25720-133">Operation</span></span>|<span data-ttu-id="25720-134">JDEPort.Operation_1.Response</span><span class="sxs-lookup"><span data-stu-id="25720-134">JDEPort.Operation_1.Response</span></span>|  
    |<span data-ttu-id="25720-135">[Send2]</span><span class="sxs-lookup"><span data-stu-id="25720-135">Send2</span></span>|<span data-ttu-id="25720-136">メッセージ</span><span class="sxs-lookup"><span data-stu-id="25720-136">Message</span></span>|<span data-ttu-id="25720-137">EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="25720-137">EditLineSessionMsg</span></span>|  
    ||<span data-ttu-id="25720-138">名前</span><span class="sxs-lookup"><span data-stu-id="25720-138">Name</span></span>|<span data-ttu-id="25720-139">SendEditLine</span><span class="sxs-lookup"><span data-stu-id="25720-139">SendEditLine</span></span>|  
    ||<span data-ttu-id="25720-140">操作</span><span class="sxs-lookup"><span data-stu-id="25720-140">Operation</span></span>|<span data-ttu-id="25720-141">JDEPort.Operation_2.Request</span><span class="sxs-lookup"><span data-stu-id="25720-141">JDEPort.Operation_2.Request</span></span>|  
    |<span data-ttu-id="25720-142">Receive3</span><span class="sxs-lookup"><span data-stu-id="25720-142">Receive3</span></span>|<span data-ttu-id="25720-143">Activate</span><span class="sxs-lookup"><span data-stu-id="25720-143">Activate</span></span>|<span data-ttu-id="25720-144">False</span><span class="sxs-lookup"><span data-stu-id="25720-144">False</span></span>|  
    ||<span data-ttu-id="25720-145">メッセージ</span><span class="sxs-lookup"><span data-stu-id="25720-145">Message</span></span>|<span data-ttu-id="25720-146">EditLineResponseMsg</span><span class="sxs-lookup"><span data-stu-id="25720-146">EditLineResponseMsg</span></span>|  
    ||<span data-ttu-id="25720-147">名前</span><span class="sxs-lookup"><span data-stu-id="25720-147">Name</span></span>|<span data-ttu-id="25720-148">ReceiveEditLine</span><span class="sxs-lookup"><span data-stu-id="25720-148">ReceiveEditLine</span></span>|  
    ||<span data-ttu-id="25720-149">操作</span><span class="sxs-lookup"><span data-stu-id="25720-149">Operation</span></span>|<span data-ttu-id="25720-150">JDEPort.Operation_2.Response</span><span class="sxs-lookup"><span data-stu-id="25720-150">JDEPort.Operation_2.Response</span></span>|  
    |<span data-ttu-id="25720-151">[Send3]</span><span class="sxs-lookup"><span data-stu-id="25720-151">Send3</span></span>|<span data-ttu-id="25720-152">メッセージ</span><span class="sxs-lookup"><span data-stu-id="25720-152">Message</span></span>|<span data-ttu-id="25720-153">EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="25720-153">EndDocSessionMsg</span></span>|  
    ||<span data-ttu-id="25720-154">名前</span><span class="sxs-lookup"><span data-stu-id="25720-154">Name</span></span>|<span data-ttu-id="25720-155">SendEndDoc</span><span class="sxs-lookup"><span data-stu-id="25720-155">SendEndDoc</span></span>|  
    ||<span data-ttu-id="25720-156">操作</span><span class="sxs-lookup"><span data-stu-id="25720-156">Operation</span></span>|<span data-ttu-id="25720-157">JDEPort.Operation_3.Request</span><span class="sxs-lookup"><span data-stu-id="25720-157">JDEPort.Operation_3.Request</span></span>|  
    |<span data-ttu-id="25720-158">Receive4</span><span class="sxs-lookup"><span data-stu-id="25720-158">Receive4</span></span>|<span data-ttu-id="25720-159">Activate</span><span class="sxs-lookup"><span data-stu-id="25720-159">Activate</span></span>|<span data-ttu-id="25720-160">False</span><span class="sxs-lookup"><span data-stu-id="25720-160">False</span></span>|  
    ||<span data-ttu-id="25720-161">メッセージ</span><span class="sxs-lookup"><span data-stu-id="25720-161">Message</span></span>|<span data-ttu-id="25720-162">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="25720-162">EndDocResponseMsg</span></span>|  
    ||<span data-ttu-id="25720-163">名前</span><span class="sxs-lookup"><span data-stu-id="25720-163">Name</span></span>|<span data-ttu-id="25720-164">ReceiveEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="25720-164">ReceiveEndDocResponse</span></span>|  
    ||<span data-ttu-id="25720-165">操作</span><span class="sxs-lookup"><span data-stu-id="25720-165">Operation</span></span>|<span data-ttu-id="25720-166">JDEPort.Operation_3.Response</span><span class="sxs-lookup"><span data-stu-id="25720-166">JDEPort.Operation_3.Response</span></span>|  
    |<span data-ttu-id="25720-167">Send4</span><span class="sxs-lookup"><span data-stu-id="25720-167">Send4</span></span>|<span data-ttu-id="25720-168">メッセージ</span><span class="sxs-lookup"><span data-stu-id="25720-168">Message</span></span>|<span data-ttu-id="25720-169">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="25720-169">EndDocResponseMsg</span></span>|  
    ||<span data-ttu-id="25720-170">名前</span><span class="sxs-lookup"><span data-stu-id="25720-170">Name</span></span>|<span data-ttu-id="25720-171">SendEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="25720-171">SendEndDocResponse</span></span>|  
    ||<span data-ttu-id="25720-172">操作</span><span class="sxs-lookup"><span data-stu-id="25720-172">Operation</span></span>|<span data-ttu-id="25720-173">EndDocOut.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="25720-173">EndDocOut.Operation_1.Request</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25720-174">参照</span><span class="sxs-lookup"><span data-stu-id="25720-174">See Also</span></span>  
 <span data-ttu-id="25720-175">[タスク 1:ポートを作成します。](../core/task-1-create-the-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="25720-175">[Task 1: Create the Ports](../core/task-1-create-the-ports2.md) </span></span>  
 <span data-ttu-id="25720-176">[タスク 2:メッセージを作成します。](../core/task-2-create-the-messages1.md) </span><span class="sxs-lookup"><span data-stu-id="25720-176">[Task 2: Create the Messages](../core/task-2-create-the-messages1.md) </span></span>  
 <span data-ttu-id="25720-177">[タスク 4:メッセージの構築図形を構成します。](../core/task-4-configure-the-construct-message-shape2.md) </span><span class="sxs-lookup"><span data-stu-id="25720-177">[Task 4: Configure the Construct Message Shape](../core/task-4-configure-the-construct-message-shape2.md) </span></span>  
 [<span data-ttu-id="25720-178">タスク 5:変換図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="25720-178">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape1.md)