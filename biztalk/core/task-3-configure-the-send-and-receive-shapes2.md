---
title: 'タスク 3: が Shapes2 を受信および送信の構成 |Microsoft ドキュメント'
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
ms.openlocfilehash: 6923a90b43d1bdc3004a03ac588dd2410d81a3cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279026"
---
# <a name="task-3-configure-the-send-and-receive-shapes"></a><span data-ttu-id="d8b78-102">タスク 3: 送信、受信図形と構成</span><span class="sxs-lookup"><span data-stu-id="d8b78-102">Task 3: Configure the Send and Receive Shapes</span></span>
<span data-ttu-id="d8b78-103">送信図形と受信図形を構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d8b78-103">Use the following procedure to configure the Send and Receive shapes.</span></span>  
  
### <a name="to-configure-the-send-and-receive-shapes"></a><span data-ttu-id="d8b78-104">送信図形と受信図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="d8b78-104">To configure the Send and Receive shapes</span></span>  
  
1.  <span data-ttu-id="d8b78-105">次の順序に従って、送信図形と受信図形をツールボックスからオーケストレーションの中心にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d8b78-105">Drag Send and Receive shapes from the tool box into the center of the orchestration in the following order.</span></span>  
  
2.  <span data-ttu-id="d8b78-106">以下のパラメータを設定します。</span><span class="sxs-lookup"><span data-stu-id="d8b78-106">Set the following parameters:</span></span>  
  
    |<span data-ttu-id="d8b78-107">図形</span><span class="sxs-lookup"><span data-stu-id="d8b78-107">Shape</span></span>|<span data-ttu-id="d8b78-108">名前</span><span class="sxs-lookup"><span data-stu-id="d8b78-108">Name</span></span>|<span data-ttu-id="d8b78-109">設定</span><span class="sxs-lookup"><span data-stu-id="d8b78-109">Setting</span></span>|  
    |-----------|----------|-------------|  
    |<span data-ttu-id="d8b78-110">Receive1</span><span class="sxs-lookup"><span data-stu-id="d8b78-110">Receive1</span></span>|<span data-ttu-id="d8b78-111">Activate</span><span class="sxs-lookup"><span data-stu-id="d8b78-111">Activate</span></span>|<span data-ttu-id="d8b78-112">True</span><span class="sxs-lookup"><span data-stu-id="d8b78-112">True</span></span>|  
    ||<span data-ttu-id="d8b78-113">メッセージ</span><span class="sxs-lookup"><span data-stu-id="d8b78-113">Message</span></span>|<span data-ttu-id="d8b78-114">BeginDocMsg</span><span class="sxs-lookup"><span data-stu-id="d8b78-114">BeginDocMsg</span></span>|  
    ||<span data-ttu-id="d8b78-115">名前</span><span class="sxs-lookup"><span data-stu-id="d8b78-115">Name</span></span>|<span data-ttu-id="d8b78-116">ReceiveBeginDoc</span><span class="sxs-lookup"><span data-stu-id="d8b78-116">ReceiveBeginDoc</span></span>|  
    ||<span data-ttu-id="d8b78-117">操作</span><span class="sxs-lookup"><span data-stu-id="d8b78-117">Operation</span></span>|<span data-ttu-id="d8b78-118">BeginDoc.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="d8b78-118">BeginDoc.Operation_1.Request</span></span>|  
    |<span data-ttu-id="d8b78-119">Send1</span><span class="sxs-lookup"><span data-stu-id="d8b78-119">Send1</span></span>|<span data-ttu-id="d8b78-120">メッセージ</span><span class="sxs-lookup"><span data-stu-id="d8b78-120">Message</span></span>|<span data-ttu-id="d8b78-121">BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="d8b78-121">BeginDocSessionMsg</span></span>|  
    ||<span data-ttu-id="d8b78-122">名前</span><span class="sxs-lookup"><span data-stu-id="d8b78-122">Name</span></span>|<span data-ttu-id="d8b78-123">SendBeginDoc</span><span class="sxs-lookup"><span data-stu-id="d8b78-123">SendBeginDoc</span></span>|  
    ||<span data-ttu-id="d8b78-124">操作</span><span class="sxs-lookup"><span data-stu-id="d8b78-124">Operation</span></span>|<span data-ttu-id="d8b78-125">JDEPort.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="d8b78-125">JDEPort.Operation_1.Request</span></span>|  
    |<span data-ttu-id="d8b78-126">Receive2</span><span class="sxs-lookup"><span data-stu-id="d8b78-126">Receive2</span></span>|<span data-ttu-id="d8b78-127">Activate</span><span class="sxs-lookup"><span data-stu-id="d8b78-127">Activate</span></span>|<span data-ttu-id="d8b78-128">False</span><span class="sxs-lookup"><span data-stu-id="d8b78-128">False</span></span>|  
    ||<span data-ttu-id="d8b78-129">メッセージ</span><span class="sxs-lookup"><span data-stu-id="d8b78-129">Message</span></span>|<span data-ttu-id="d8b78-130">BeginDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="d8b78-130">BeginDocResponseMsg</span></span>|  
    ||<span data-ttu-id="d8b78-131">名前</span><span class="sxs-lookup"><span data-stu-id="d8b78-131">Name</span></span>|<span data-ttu-id="d8b78-132">ReceiveBeginDocResponse</span><span class="sxs-lookup"><span data-stu-id="d8b78-132">ReceiveBeginDocResponse</span></span>|  
    ||<span data-ttu-id="d8b78-133">操作</span><span class="sxs-lookup"><span data-stu-id="d8b78-133">Operation</span></span>|<span data-ttu-id="d8b78-134">JDEPort.Operation_1.Response</span><span class="sxs-lookup"><span data-stu-id="d8b78-134">JDEPort.Operation_1.Response</span></span>|  
    |<span data-ttu-id="d8b78-135">Send2</span><span class="sxs-lookup"><span data-stu-id="d8b78-135">Send2</span></span>|<span data-ttu-id="d8b78-136">メッセージ</span><span class="sxs-lookup"><span data-stu-id="d8b78-136">Message</span></span>|<span data-ttu-id="d8b78-137">EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="d8b78-137">EditLineSessionMsg</span></span>|  
    ||<span data-ttu-id="d8b78-138">名前</span><span class="sxs-lookup"><span data-stu-id="d8b78-138">Name</span></span>|<span data-ttu-id="d8b78-139">SendEditLine</span><span class="sxs-lookup"><span data-stu-id="d8b78-139">SendEditLine</span></span>|  
    ||<span data-ttu-id="d8b78-140">操作</span><span class="sxs-lookup"><span data-stu-id="d8b78-140">Operation</span></span>|<span data-ttu-id="d8b78-141">JDEPort.Operation_2.Request</span><span class="sxs-lookup"><span data-stu-id="d8b78-141">JDEPort.Operation_2.Request</span></span>|  
    |<span data-ttu-id="d8b78-142">Receive3</span><span class="sxs-lookup"><span data-stu-id="d8b78-142">Receive3</span></span>|<span data-ttu-id="d8b78-143">Activate</span><span class="sxs-lookup"><span data-stu-id="d8b78-143">Activate</span></span>|<span data-ttu-id="d8b78-144">False</span><span class="sxs-lookup"><span data-stu-id="d8b78-144">False</span></span>|  
    ||<span data-ttu-id="d8b78-145">メッセージ</span><span class="sxs-lookup"><span data-stu-id="d8b78-145">Message</span></span>|<span data-ttu-id="d8b78-146">EditLineResponseMsg</span><span class="sxs-lookup"><span data-stu-id="d8b78-146">EditLineResponseMsg</span></span>|  
    ||<span data-ttu-id="d8b78-147">名前</span><span class="sxs-lookup"><span data-stu-id="d8b78-147">Name</span></span>|<span data-ttu-id="d8b78-148">ReceiveEditLine</span><span class="sxs-lookup"><span data-stu-id="d8b78-148">ReceiveEditLine</span></span>|  
    ||<span data-ttu-id="d8b78-149">操作</span><span class="sxs-lookup"><span data-stu-id="d8b78-149">Operation</span></span>|<span data-ttu-id="d8b78-150">JDEPort.Operation_2.Response</span><span class="sxs-lookup"><span data-stu-id="d8b78-150">JDEPort.Operation_2.Response</span></span>|  
    |<span data-ttu-id="d8b78-151">Send3</span><span class="sxs-lookup"><span data-stu-id="d8b78-151">Send3</span></span>|<span data-ttu-id="d8b78-152">メッセージ</span><span class="sxs-lookup"><span data-stu-id="d8b78-152">Message</span></span>|<span data-ttu-id="d8b78-153">EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="d8b78-153">EndDocSessionMsg</span></span>|  
    ||<span data-ttu-id="d8b78-154">名前</span><span class="sxs-lookup"><span data-stu-id="d8b78-154">Name</span></span>|<span data-ttu-id="d8b78-155">SendEndDoc</span><span class="sxs-lookup"><span data-stu-id="d8b78-155">SendEndDoc</span></span>|  
    ||<span data-ttu-id="d8b78-156">操作</span><span class="sxs-lookup"><span data-stu-id="d8b78-156">Operation</span></span>|<span data-ttu-id="d8b78-157">JDEPort.Operation_3.Request</span><span class="sxs-lookup"><span data-stu-id="d8b78-157">JDEPort.Operation_3.Request</span></span>|  
    |<span data-ttu-id="d8b78-158">Receive4</span><span class="sxs-lookup"><span data-stu-id="d8b78-158">Receive4</span></span>|<span data-ttu-id="d8b78-159">Activate</span><span class="sxs-lookup"><span data-stu-id="d8b78-159">Activate</span></span>|<span data-ttu-id="d8b78-160">False</span><span class="sxs-lookup"><span data-stu-id="d8b78-160">False</span></span>|  
    ||<span data-ttu-id="d8b78-161">メッセージ</span><span class="sxs-lookup"><span data-stu-id="d8b78-161">Message</span></span>|<span data-ttu-id="d8b78-162">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="d8b78-162">EndDocResponseMsg</span></span>|  
    ||<span data-ttu-id="d8b78-163">名前</span><span class="sxs-lookup"><span data-stu-id="d8b78-163">Name</span></span>|<span data-ttu-id="d8b78-164">ReceiveEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="d8b78-164">ReceiveEndDocResponse</span></span>|  
    ||<span data-ttu-id="d8b78-165">操作</span><span class="sxs-lookup"><span data-stu-id="d8b78-165">Operation</span></span>|<span data-ttu-id="d8b78-166">JDEPort.Operation_3.Response</span><span class="sxs-lookup"><span data-stu-id="d8b78-166">JDEPort.Operation_3.Response</span></span>|  
    |<span data-ttu-id="d8b78-167">Send4</span><span class="sxs-lookup"><span data-stu-id="d8b78-167">Send4</span></span>|<span data-ttu-id="d8b78-168">メッセージ</span><span class="sxs-lookup"><span data-stu-id="d8b78-168">Message</span></span>|<span data-ttu-id="d8b78-169">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="d8b78-169">EndDocResponseMsg</span></span>|  
    ||<span data-ttu-id="d8b78-170">名前</span><span class="sxs-lookup"><span data-stu-id="d8b78-170">Name</span></span>|<span data-ttu-id="d8b78-171">SendEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="d8b78-171">SendEndDocResponse</span></span>|  
    ||<span data-ttu-id="d8b78-172">操作</span><span class="sxs-lookup"><span data-stu-id="d8b78-172">Operation</span></span>|<span data-ttu-id="d8b78-173">EndDocOut.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="d8b78-173">EndDocOut.Operation_1.Request</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8b78-174">参照</span><span class="sxs-lookup"><span data-stu-id="d8b78-174">See Also</span></span>  
 <span data-ttu-id="d8b78-175">[タスク 1: ポートを作成します。](../core/task-1-create-the-ports1.md) </span><span class="sxs-lookup"><span data-stu-id="d8b78-175">[Task 1: Create the Ports](../core/task-1-create-the-ports1.md) </span></span>  
 <span data-ttu-id="d8b78-176">[タスク 2: メッセージを作成します。](../core/task-2-create-the-messages2.md) </span><span class="sxs-lookup"><span data-stu-id="d8b78-176">[Task 2: Create the Messages](../core/task-2-create-the-messages2.md) </span></span>  
 <span data-ttu-id="d8b78-177">[タスク 4: メッセージの構築図形を構成します。](../core/task-4-configure-the-construct-message-shape1.md) </span><span class="sxs-lookup"><span data-stu-id="d8b78-177">[Task 4: Configure the Construct Message Shape](../core/task-4-configure-the-construct-message-shape1.md) </span></span>  
 [<span data-ttu-id="d8b78-178">タスク 5: 変換図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="d8b78-178">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape2.md)