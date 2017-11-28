---
title: "タスク 3: が Shapes1 を受信および送信の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e258d22-755b-48a4-9f9e-e9398f6b68b1
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c730cc6bc5cb11c27152613f331bda6b15be390
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="task-3-configure-the-send-and-receive-shapes"></a><span data-ttu-id="7090e-102">タスク 3: 送信、受信図形と構成</span><span class="sxs-lookup"><span data-stu-id="7090e-102">Task 3: Configure the Send and Receive Shapes</span></span>
<span data-ttu-id="7090e-103">送信図形と受信図形を構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7090e-103">Use the following procedure to configure the Send and Receive shapes.</span></span>  
  
### <a name="to-configure-the-send-and-receive-shapes"></a><span data-ttu-id="7090e-104">送信図形と受信図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="7090e-104">To configure the Send and Receive shapes</span></span>  
  
1.  <span data-ttu-id="7090e-105">次の順序に従って、送信図形と受信図形をツールボックスからオーケストレーションの中心にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="7090e-105">Drag Send and Receive shapes from the tool box into the center of the orchestration in the following order.</span></span>  
  
2.  <span data-ttu-id="7090e-106">以下のパラメータを設定します。</span><span class="sxs-lookup"><span data-stu-id="7090e-106">Set the following parameters:</span></span>  
  
    |<span data-ttu-id="7090e-107">図形</span><span class="sxs-lookup"><span data-stu-id="7090e-107">Shape</span></span>|<span data-ttu-id="7090e-108">名前</span><span class="sxs-lookup"><span data-stu-id="7090e-108">Name</span></span>|<span data-ttu-id="7090e-109">設定</span><span class="sxs-lookup"><span data-stu-id="7090e-109">Setting</span></span>|  
    |-----------|----------|-------------|  
    |<span data-ttu-id="7090e-110">Receive1</span><span class="sxs-lookup"><span data-stu-id="7090e-110">Receive1</span></span>|<span data-ttu-id="7090e-111">Activate</span><span class="sxs-lookup"><span data-stu-id="7090e-111">Activate</span></span>|<span data-ttu-id="7090e-112">True</span><span class="sxs-lookup"><span data-stu-id="7090e-112">True</span></span>|  
    ||<span data-ttu-id="7090e-113">メッセージ</span><span class="sxs-lookup"><span data-stu-id="7090e-113">Message</span></span>|<span data-ttu-id="7090e-114">BeginDocMsg</span><span class="sxs-lookup"><span data-stu-id="7090e-114">BeginDocMsg</span></span>|  
    ||<span data-ttu-id="7090e-115">名前</span><span class="sxs-lookup"><span data-stu-id="7090e-115">Name</span></span>|<span data-ttu-id="7090e-116">ReceiveBeginDoc</span><span class="sxs-lookup"><span data-stu-id="7090e-116">ReceiveBeginDoc</span></span>|  
    ||<span data-ttu-id="7090e-117">操作</span><span class="sxs-lookup"><span data-stu-id="7090e-117">Operation</span></span>|<span data-ttu-id="7090e-118">BeginDoc.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="7090e-118">BeginDoc.Operation_1.Request</span></span>|  
    |<span data-ttu-id="7090e-119">Send1</span><span class="sxs-lookup"><span data-stu-id="7090e-119">Send1</span></span>|<span data-ttu-id="7090e-120">メッセージ</span><span class="sxs-lookup"><span data-stu-id="7090e-120">Message</span></span>|<span data-ttu-id="7090e-121">BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="7090e-121">BeginDocSessionMsg</span></span>|  
    ||<span data-ttu-id="7090e-122">名前</span><span class="sxs-lookup"><span data-stu-id="7090e-122">Name</span></span>|<span data-ttu-id="7090e-123">SendBeginDoc</span><span class="sxs-lookup"><span data-stu-id="7090e-123">SendBeginDoc</span></span>|  
    ||<span data-ttu-id="7090e-124">操作</span><span class="sxs-lookup"><span data-stu-id="7090e-124">Operation</span></span>|<span data-ttu-id="7090e-125">JDEPort.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="7090e-125">JDEPort.Operation_1.Request</span></span>|  
    |<span data-ttu-id="7090e-126">Receive2</span><span class="sxs-lookup"><span data-stu-id="7090e-126">Receive2</span></span>|<span data-ttu-id="7090e-127">Activate</span><span class="sxs-lookup"><span data-stu-id="7090e-127">Activate</span></span>|<span data-ttu-id="7090e-128">False</span><span class="sxs-lookup"><span data-stu-id="7090e-128">False</span></span>|  
    ||<span data-ttu-id="7090e-129">メッセージ</span><span class="sxs-lookup"><span data-stu-id="7090e-129">Message</span></span>|<span data-ttu-id="7090e-130">BeginDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="7090e-130">BeginDocResponseMsg</span></span>|  
    ||<span data-ttu-id="7090e-131">名前</span><span class="sxs-lookup"><span data-stu-id="7090e-131">Name</span></span>|<span data-ttu-id="7090e-132">ReceiveBeginDocResponse</span><span class="sxs-lookup"><span data-stu-id="7090e-132">ReceiveBeginDocResponse</span></span>|  
    ||<span data-ttu-id="7090e-133">操作</span><span class="sxs-lookup"><span data-stu-id="7090e-133">Operation</span></span>|<span data-ttu-id="7090e-134">JDEPort.Operation_1.Response</span><span class="sxs-lookup"><span data-stu-id="7090e-134">JDEPort.Operation_1.Response</span></span>|  
    |<span data-ttu-id="7090e-135">Send2</span><span class="sxs-lookup"><span data-stu-id="7090e-135">Send2</span></span>|<span data-ttu-id="7090e-136">メッセージ</span><span class="sxs-lookup"><span data-stu-id="7090e-136">Message</span></span>|<span data-ttu-id="7090e-137">EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="7090e-137">EditLineSessionMsg</span></span>|  
    ||<span data-ttu-id="7090e-138">名前</span><span class="sxs-lookup"><span data-stu-id="7090e-138">Name</span></span>|<span data-ttu-id="7090e-139">SendEditLine</span><span class="sxs-lookup"><span data-stu-id="7090e-139">SendEditLine</span></span>|  
    ||<span data-ttu-id="7090e-140">操作</span><span class="sxs-lookup"><span data-stu-id="7090e-140">Operation</span></span>|<span data-ttu-id="7090e-141">JDEPort.Operation_2.Request</span><span class="sxs-lookup"><span data-stu-id="7090e-141">JDEPort.Operation_2.Request</span></span>|  
    |<span data-ttu-id="7090e-142">Receive3</span><span class="sxs-lookup"><span data-stu-id="7090e-142">Receive3</span></span>|<span data-ttu-id="7090e-143">Activate</span><span class="sxs-lookup"><span data-stu-id="7090e-143">Activate</span></span>|<span data-ttu-id="7090e-144">False</span><span class="sxs-lookup"><span data-stu-id="7090e-144">False</span></span>|  
    ||<span data-ttu-id="7090e-145">メッセージ</span><span class="sxs-lookup"><span data-stu-id="7090e-145">Message</span></span>|<span data-ttu-id="7090e-146">EditLineResponseMsg</span><span class="sxs-lookup"><span data-stu-id="7090e-146">EditLineResponseMsg</span></span>|  
    ||<span data-ttu-id="7090e-147">名前</span><span class="sxs-lookup"><span data-stu-id="7090e-147">Name</span></span>|<span data-ttu-id="7090e-148">ReceiveEditLine</span><span class="sxs-lookup"><span data-stu-id="7090e-148">ReceiveEditLine</span></span>|  
    ||<span data-ttu-id="7090e-149">操作</span><span class="sxs-lookup"><span data-stu-id="7090e-149">Operation</span></span>|<span data-ttu-id="7090e-150">JDEPort.Operation_2.Response</span><span class="sxs-lookup"><span data-stu-id="7090e-150">JDEPort.Operation_2.Response</span></span>|  
    |<span data-ttu-id="7090e-151">Send3</span><span class="sxs-lookup"><span data-stu-id="7090e-151">Send3</span></span>|<span data-ttu-id="7090e-152">メッセージ</span><span class="sxs-lookup"><span data-stu-id="7090e-152">Message</span></span>|<span data-ttu-id="7090e-153">EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="7090e-153">EndDocSessionMsg</span></span>|  
    ||<span data-ttu-id="7090e-154">名前</span><span class="sxs-lookup"><span data-stu-id="7090e-154">Name</span></span>|<span data-ttu-id="7090e-155">SendEndDoc</span><span class="sxs-lookup"><span data-stu-id="7090e-155">SendEndDoc</span></span>|  
    ||<span data-ttu-id="7090e-156">操作</span><span class="sxs-lookup"><span data-stu-id="7090e-156">Operation</span></span>|<span data-ttu-id="7090e-157">JDEPort.Operation_3.Request</span><span class="sxs-lookup"><span data-stu-id="7090e-157">JDEPort.Operation_3.Request</span></span>|  
    |<span data-ttu-id="7090e-158">Receive4</span><span class="sxs-lookup"><span data-stu-id="7090e-158">Receive4</span></span>|<span data-ttu-id="7090e-159">Activate</span><span class="sxs-lookup"><span data-stu-id="7090e-159">Activate</span></span>|<span data-ttu-id="7090e-160">False</span><span class="sxs-lookup"><span data-stu-id="7090e-160">False</span></span>|  
    ||<span data-ttu-id="7090e-161">メッセージ</span><span class="sxs-lookup"><span data-stu-id="7090e-161">Message</span></span>|<span data-ttu-id="7090e-162">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="7090e-162">EndDocResponseMsg</span></span>|  
    ||<span data-ttu-id="7090e-163">名前</span><span class="sxs-lookup"><span data-stu-id="7090e-163">Name</span></span>|<span data-ttu-id="7090e-164">ReceiveEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="7090e-164">ReceiveEndDocResponse</span></span>|  
    ||<span data-ttu-id="7090e-165">操作</span><span class="sxs-lookup"><span data-stu-id="7090e-165">Operation</span></span>|<span data-ttu-id="7090e-166">JDEPort.Operation_3.Response</span><span class="sxs-lookup"><span data-stu-id="7090e-166">JDEPort.Operation_3.Response</span></span>|  
    |<span data-ttu-id="7090e-167">Send4</span><span class="sxs-lookup"><span data-stu-id="7090e-167">Send4</span></span>|<span data-ttu-id="7090e-168">メッセージ</span><span class="sxs-lookup"><span data-stu-id="7090e-168">Message</span></span>|<span data-ttu-id="7090e-169">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="7090e-169">EndDocResponseMsg</span></span>|  
    ||<span data-ttu-id="7090e-170">名前</span><span class="sxs-lookup"><span data-stu-id="7090e-170">Name</span></span>|<span data-ttu-id="7090e-171">SendEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="7090e-171">SendEndDocResponse</span></span>|  
    ||<span data-ttu-id="7090e-172">操作</span><span class="sxs-lookup"><span data-stu-id="7090e-172">Operation</span></span>|<span data-ttu-id="7090e-173">EndDocOut.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="7090e-173">EndDocOut.Operation_1.Request</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7090e-174">参照</span><span class="sxs-lookup"><span data-stu-id="7090e-174">See Also</span></span>  
 <span data-ttu-id="7090e-175">[タスク 1: ポートを作成します。](../core/task-1-create-the-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="7090e-175">[Task 1: Create the Ports](../core/task-1-create-the-ports2.md) </span></span>  
 <span data-ttu-id="7090e-176">[タスク 2: メッセージを作成します。](../core/task-2-create-the-messages1.md) </span><span class="sxs-lookup"><span data-stu-id="7090e-176">[Task 2: Create the Messages](../core/task-2-create-the-messages1.md) </span></span>  
 <span data-ttu-id="7090e-177">[タスク 4: メッセージの構築図形を構成します。](../core/task-4-configure-the-construct-message-shape2.md) </span><span class="sxs-lookup"><span data-stu-id="7090e-177">[Task 4: Configure the Construct Message Shape](../core/task-4-configure-the-construct-message-shape2.md) </span></span>  
 [<span data-ttu-id="7090e-178">タスク 5: 変換図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="7090e-178">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape1.md)