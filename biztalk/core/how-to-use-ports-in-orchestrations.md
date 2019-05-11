---
title: オーケストレーションでポートを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, adding ports
- Port Configuration Wizard [Orchestration Designer], configuring ports
- ports, operations
- operations, adding to ports
- configuring, ports
- ports, deleting
- deleting, ports
- ports, Port Configuration Wizard [Orchestration Designer]
- ports, adding to orchestrations
- ports, configuring
ms.assetid: da8665cd-ccde-4949-b5f5-01f9f8be5ce8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c076195aa9893dc4bb1c42a9b6a659422e3ec263
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333272"
---
# <a name="how-to-use-ports-in-orchestrations"></a><span data-ttu-id="d3a19-102">オーケストレーションでポートを使用する方法</span><span class="sxs-lookup"><span data-stu-id="d3a19-102">How to Use Ports in Orchestrations</span></span>
<span data-ttu-id="d3a19-103">ポートを追加でオーケストレーションを Web フォームまたは Windows フォーム コントロールを追加することと同じ方法。</span><span class="sxs-lookup"><span data-stu-id="d3a19-103">You add ports to an orchestration in much the same way that you add controls to a Web Form or Windows Form.</span></span> <span data-ttu-id="d3a19-104">オーケストレーションの種類 ウィンドウを使用してポートを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="d3a19-104">You can also add ports by using the Orchestration View window.</span></span>  
  
### <a name="to-add-a-new-port"></a><span data-ttu-id="d3a19-105">新しいポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="d3a19-105">To add a new port</span></span>  
  
-   <span data-ttu-id="d3a19-106">右クリックし、**ポート画面**または**ロール リンク**、 をクリックし、**新しいポート**。</span><span class="sxs-lookup"><span data-stu-id="d3a19-106">Right-click a **Port Surface** or a **Role Link**, and then click **New Port**.</span></span>  
  
     <span data-ttu-id="d3a19-107">- または -</span><span class="sxs-lookup"><span data-stu-id="d3a19-107">—Or—</span></span>  
  
     <span data-ttu-id="d3a19-108">オーケストレーションの種類 ウィンドウで、右クリック**ポート** をクリックし、**新しいポート**します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-108">In the Orchestration View window, right-click **Ports** and then click **New Port**.</span></span>  
  
     <span data-ttu-id="d3a19-109">まだ完全に構成されていないポートに [designtip] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3a19-109">A DesignTip appears on ports that are not yet fully configured.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="d3a19-110">ポートをドラッグすることも、**ロール リンク**します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-110">You can also drag ports into a **Role Link**.</span></span>  
  
### <a name="to-add-and-configure-a-new-port"></a><span data-ttu-id="d3a19-111">追加して、新しいポートの構成</span><span class="sxs-lookup"><span data-stu-id="d3a19-111">To add and configure a new port</span></span>  
  
1.  <span data-ttu-id="d3a19-112">**BizTalk オーケストレーション**、ツールボックスのタブ、**ポート**に図形を**ポート画面**または**ロール リンク**します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-112">From the **BizTalk Orchestrations** tab of the Toolbox, drag the **Port** shape onto a **Port Surface** or a **Role Link**.</span></span>  
  
     <span data-ttu-id="d3a19-113">- または -</span><span class="sxs-lookup"><span data-stu-id="d3a19-113">—Or—</span></span>  
  
     <span data-ttu-id="d3a19-114">右クリックし、**ポート画面**または**ロール リンク**、順にクリックします**新しい構成済みポート**します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-114">Right-click a **Port Surface** or a **Role Link**, and then click **New Configured Port**.</span></span>  
  
     <span data-ttu-id="d3a19-115">- または -</span><span class="sxs-lookup"><span data-stu-id="d3a19-115">—Or—</span></span>  
  
     <span data-ttu-id="d3a19-116">オーケストレーションの種類 ウィンドウで、右クリック**ポート** をクリックし、**新しい構成済みポート**します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-116">In the Orchestration View window, right-click **Ports** and then click **New Configured Port**.</span></span>  
  
     <span data-ttu-id="d3a19-117">ポート構成ウィザードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3a19-117">The Port Configuration Wizard appears.</span></span>  
  
2.  <span data-ttu-id="d3a19-118">ポート構成ウィザードの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d3a19-118">Follow the steps in the wizard to configure the port.</span></span> <span data-ttu-id="d3a19-119">詳細については、次を参照してください。[ポート構成ウィザードを実行する方法](../core/how-to-run-the-port-configuration-wizard.md)します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-119">For more information, see [How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md).</span></span>  
  
### <a name="to-remove-a-port"></a><span data-ttu-id="d3a19-120">ポートを削除するには</span><span class="sxs-lookup"><span data-stu-id="d3a19-120">To remove a port</span></span>  
  
-   <span data-ttu-id="d3a19-121">クリックして削除するには、ポートを右クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-121">Right-click the port to remove, and then click **Delete**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d3a19-122">接続された後は、ポートを削除するかどうか、**送信**または**受信**コンパイルされたオーケストレーション図形にポート operations の図形を削除できませんが、およびエラーが発生する場合コンパイルしようとします。</span><span class="sxs-lookup"><span data-stu-id="d3a19-122">If you delete a port after it has been connected to a **Send** or **Receive** shape in an orchestration that has been compiled, the port operations on the shape will not be deleted, and you will receive errors when you try to compile.</span></span> <span data-ttu-id="d3a19-123">図形を別のポートに接続し、ポート operations を再構成します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-123">Connect the shape to another port and reconfigure the port operations.</span></span>  
  
### <a name="to-configure-a-port-by-using-the-port-configuration-wizard"></a><span data-ttu-id="d3a19-124">ポート構成ウィザードを使用してポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="d3a19-124">To configure a port by using the Port Configuration Wizard</span></span>  
  
1.  <span data-ttu-id="d3a19-125">クリックして構成するには、ポートを右クリックして**ポートの構成**します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-125">Right-click the port to configure, and then click **Configure Port**.</span></span>  
  
2.  <span data-ttu-id="d3a19-126">ポートを構成するポート構成ウィザードの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d3a19-126">Follow the steps in the Port Configuration Wizard to configure the port.</span></span> <span data-ttu-id="d3a19-127">詳細については、次を参照してください。[ポート構成ウィザードを実行する方法](../core/how-to-run-the-port-configuration-wizard.md)します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-127">For more information, see [How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md).</span></span>  
  
### <a name="to-configure-a-port-manually-by-using-the-properties-window"></a><span data-ttu-id="d3a19-128">[プロパティ] ウィンドウを使用して手動でポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="d3a19-128">To configure a port manually by using the Properties window</span></span>  
  
1.  <span data-ttu-id="d3a19-129">構成するポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-129">Select the port to configure.</span></span>  
  
2.  <span data-ttu-id="d3a19-130">[プロパティ] ウィンドウでは、次のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-130">In the Properties window, specify the following properties:</span></span>  
  
    |<span data-ttu-id="d3a19-131">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d3a19-131">Property</span></span>|<span data-ttu-id="d3a19-132">説明</span><span class="sxs-lookup"><span data-stu-id="d3a19-132">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="d3a19-133">ポートの種類</span><span class="sxs-lookup"><span data-stu-id="d3a19-133">Port Type</span></span>|<span data-ttu-id="d3a19-134">通信方式、操作、およびポートに関連付けられているマルチパート メッセージの種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-134">Determines the communication pattern, operations, and multi-part message types associated with a port.</span></span>|  
    |<span data-ttu-id="d3a19-135">通信方向</span><span class="sxs-lookup"><span data-stu-id="d3a19-135">Communication Direction</span></span>|<span data-ttu-id="d3a19-136">このオーケストレーションが、送信者またはこの通信の受信者であるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-136">Determines whether this orchestration is the sender or the receiver for this communication.</span></span>|  
    |<span data-ttu-id="d3a19-137">通信方式</span><span class="sxs-lookup"><span data-stu-id="d3a19-137">Communication Pattern</span></span>|<span data-ttu-id="d3a19-138">このポートは要求-応答または一方向の通信に使用されているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-138">Determines if this port is used for request-response or one-way communication.</span></span> <span data-ttu-id="d3a19-139">(このプロパティはによって決定されます、**ポートの種類**プロパティは読み取り専用であるとします)。</span><span class="sxs-lookup"><span data-stu-id="d3a19-139">(This property is determined by the **Port Type** property and is read-only.)</span></span>|  
    |<span data-ttu-id="d3a19-140">Binding</span><span class="sxs-lookup"><span data-stu-id="d3a19-140">Binding</span></span>|<span data-ttu-id="d3a19-141">宛先にメッセージを取得する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-141">Determines how a message gets to its destination:</span></span><br /><br /> <span data-ttu-id="d3a19-142">直接-別のオーケストレーションとの通信です。</span><span class="sxs-lookup"><span data-stu-id="d3a19-142">Direct—Communication is with another orchestration.</span></span><br /><br /> <span data-ttu-id="d3a19-143">動的: 実行時に決定されるエンドポイントとの通信です。</span><span class="sxs-lookup"><span data-stu-id="d3a19-143">Dynamic—Communication is with an endpoint that is determined at run time.</span></span><br /><br /> <span data-ttu-id="d3a19-144">後で指定する、構成時に、管理者によって決定されるエンドポイントとの通信です。</span><span class="sxs-lookup"><span data-stu-id="d3a19-144">Specify later—Communication is with an endpoint that is determined by an administrator at configuration time.</span></span><br /><br /> <span data-ttu-id="d3a19-145">今指定する: デザイン時に特定されるエンドポイントとの通信です。</span><span class="sxs-lookup"><span data-stu-id="d3a19-145">Specify now—Communication is with an endpoint that is known at design time.</span></span>|  
    |<span data-ttu-id="d3a19-146">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="d3a19-146">Identifier</span></span>|<span data-ttu-id="d3a19-147">このポート、オーケストレーションで使用される名前。</span><span class="sxs-lookup"><span data-stu-id="d3a19-147">The name used for this port in the orchestration.</span></span>|  
    |<span data-ttu-id="d3a19-148">順次配送</span><span class="sxs-lookup"><span data-stu-id="d3a19-148">Ordered Delivery</span></span>|<span data-ttu-id="d3a19-149">受信ポートの場合は、特定の順序でメッセージ ボックス データベースに公開されたメッセージがメッセージ ボックスに公開されたときと同じ順序で一致する各サブスクライバーに配信されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-149">For receive ports, ensures that messages that are published to the MessageBox database in a given order are delivered to each matching subscriber in the same order in which they were published to the message box.</span></span> <span data-ttu-id="d3a19-150">詳細については、次を参照してください。[のメッセージ配信の順序付けられた](../core/ordered-delivery-of-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-150">For more information, see [Ordered Delivery of Messages](../core/ordered-delivery-of-messages.md).</span></span>|  
    |<span data-ttu-id="d3a19-151">[配信通知]</span><span class="sxs-lookup"><span data-stu-id="d3a19-151">Delivery Notification</span></span>|<span data-ttu-id="d3a19-152">送信ポートの場合は、次のように決定します。 メッセージが正常に送信されるときに、受信確認を受信するかどうか。</span><span class="sxs-lookup"><span data-stu-id="d3a19-152">For send ports, determines whether want to receive an acknowledgment when a message is sent successfully.</span></span> <span data-ttu-id="d3a19-153">詳細についてを参照してください「配信通知」[送信図形を構成する方法](../core/how-to-configure-the-send-shape.md)します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-153">For more information, see "Delivery Notification" in [How to Configure the Send Shape](../core/how-to-configure-the-send-shape.md).</span></span>|  
  
3.  <span data-ttu-id="d3a19-154">指定する残りのプロパティによって決定されます、**バインド**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d3a19-154">The remaining properties to specify are determined by the **Binding** property:</span></span>  
  
    -   <span data-ttu-id="d3a19-155">直接バインド: 別のオーケストレーションと直接通信するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-155">Direct binding—Used when communicating directly with another orchestration.</span></span>  
  
        |<span data-ttu-id="d3a19-156">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d3a19-156">Property</span></span>|<span data-ttu-id="d3a19-157">説明</span><span class="sxs-lookup"><span data-stu-id="d3a19-157">Description</span></span>|  
        |--------------|-----------------|  
        |<span data-ttu-id="d3a19-158">パートナー オーケストレーションのポート</span><span class="sxs-lookup"><span data-stu-id="d3a19-158">Partner Orchestration Port</span></span>|<span data-ttu-id="d3a19-159">パートナー オーケストレーションが直接バインドされるポートを決定します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-159">Determines to which port the partner orchestrations will be directly bound.</span></span>|  
  
    -   <span data-ttu-id="d3a19-160">動的バインド: 実行時に決定されるエンドポイントと通信するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-160">Dynamic binding—Used when communicating with an endpoint that is determined at run time.</span></span>  
  
        |<span data-ttu-id="d3a19-161">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d3a19-161">Property</span></span>|<span data-ttu-id="d3a19-162">説明</span><span class="sxs-lookup"><span data-stu-id="d3a19-162">Description</span></span>|  
        |--------------|-----------------|  
        |<span data-ttu-id="d3a19-163">[受信パイプライン]</span><span class="sxs-lookup"><span data-stu-id="d3a19-163">Receive Pipeline</span></span>|<span data-ttu-id="d3a19-164">受信メッセージに使用するパイプラインを決定します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-164">Determines which pipeline to use for incoming messages.</span></span>|  
        |<span data-ttu-id="d3a19-165">送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="d3a19-165">Send Pipeline</span></span>|<span data-ttu-id="d3a19-166">送信メッセージに使用するパイプラインを決定します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-166">Determines which pipeline to use for outgoing messages.</span></span>|  
  
    -   <span data-ttu-id="d3a19-167">後で指定する: 管理者によって構成されているエンドポイントと通信するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-167">Specify later—Used when communicating with an endpoint that is configured by an administrator.</span></span>  
  
    -   <span data-ttu-id="d3a19-168">今指定する: デザイン時に特定されるエンドポイントと通信するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-168">Specify now—Used when communicating with an endpoint that is known at design time.</span></span>  
  
        |<span data-ttu-id="d3a19-169">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d3a19-169">Property</span></span>|<span data-ttu-id="d3a19-170">説明</span><span class="sxs-lookup"><span data-stu-id="d3a19-170">Description</span></span>|  
        |--------------|-----------------|  
        |<span data-ttu-id="d3a19-171">[受信パイプライン]</span><span class="sxs-lookup"><span data-stu-id="d3a19-171">Receive Pipeline</span></span>|<span data-ttu-id="d3a19-172">受信メッセージに使用するパイプラインを決定します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-172">Determines which pipeline to use for incoming messages.</span></span>|  
        |<span data-ttu-id="d3a19-173">送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="d3a19-173">Send Pipeline</span></span>|<span data-ttu-id="d3a19-174">送信メッセージに使用するパイプラインを決定します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-174">Determines which pipeline to use for outgoing messages.</span></span>|  
        |<span data-ttu-id="d3a19-175">[Transport]</span><span class="sxs-lookup"><span data-stu-id="d3a19-175">Transport</span></span>|<span data-ttu-id="d3a19-176">メッセージの送信に使用するトランスポートを決定します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-176">Determines which transport to use for sending messages.</span></span>|  
        |<span data-ttu-id="d3a19-177">URI</span><span class="sxs-lookup"><span data-stu-id="d3a19-177">URI</span></span>|<span data-ttu-id="d3a19-178">メッセージを送信する場所を決定します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-178">Determines where to send messages.</span></span>|  
  
### <a name="to-add-a-port-operation"></a><span data-ttu-id="d3a19-179">ポート操作を追加するには</span><span class="sxs-lookup"><span data-stu-id="d3a19-179">To add a port operation</span></span>  
  
-   <span data-ttu-id="d3a19-180">クリックして、操作を追加するポートを右クリックして**新しい操作**します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-180">Right-click the port to which you want to add an operation, and then click **New Operation**.</span></span>  
  
### <a name="to-remove-a-port-operation"></a><span data-ttu-id="d3a19-181">ポート操作を削除するには</span><span class="sxs-lookup"><span data-stu-id="d3a19-181">To remove a port operation</span></span>  
  
-   <span data-ttu-id="d3a19-182">クリックして削除するには、ポート操作を右クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="d3a19-182">Right-click the port operation to remove, and then click **Delete**.</span></span>