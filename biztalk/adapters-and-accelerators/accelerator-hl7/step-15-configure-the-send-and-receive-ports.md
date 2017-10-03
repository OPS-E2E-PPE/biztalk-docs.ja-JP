---
title: "手順 15 は、送信を構成し、受信ポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: message enrichment tutorial, ports
ms.assetid: d532b196-473e-4c8f-b4ed-acef674fc698
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 020d83db1db86f9ff9ce116578cf58f19ba08241
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-15-configure-the-send-and-receive-ports"></a><span data-ttu-id="c36bc-102">手順 15 は、送信を構成し、受信ポート</span><span class="sxs-lookup"><span data-stu-id="c36bc-102">Step 15: Configure the Send and Receive Ports</span></span>
<span data-ttu-id="c36bc-103">前の手順で作成論理送信および受信ポートをオーケストレーション デザイナーを使用し、「後で」ポートのバインドの設定。</span><span class="sxs-lookup"><span data-stu-id="c36bc-103">In previous steps, you created a logical send and receive port using Orchestration Designer and set the port binding to "Specify Later".</span></span> <span data-ttu-id="c36bc-104">このステップでは、物理的な送信元と送信先の場所を定義して、オーケストレーションで作成した論理ポートを物理ポートをバインドして、ポートの構成を確定するのに BizTalk エクスプ ローラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c36bc-104">In this step, you use BizTalk Explorer to finalize the port configuration by defining the physical source and destination locations and binding the physical ports to the logical ports that you created in the orchestration.</span></span>  
  
## <a name="configure-the-send-and-receive-ports"></a><span data-ttu-id="c36bc-105">構成、送信ポートと受信ポート</span><span class="sxs-lookup"><span data-stu-id="c36bc-105">Configure the send and receive ports</span></span>  
  
1.  <span data-ttu-id="c36bc-106">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**の順に展開および**BizTalk アプリケーション 1**です。</span><span class="sxs-lookup"><span data-stu-id="c36bc-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
2.  <span data-ttu-id="c36bc-107">右クリック**送信ポート**、新規作成 をポイントし、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="c36bc-107">Right-click **Send Ports**, point to New, and then click **Static One-way Send Port**.</span></span>  
  
3.  <span data-ttu-id="c36bc-108">送信ポートのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**MLLPSendPort**です。</span><span class="sxs-lookup"><span data-stu-id="c36bc-108">In the Send Port Properties dialog box, in the **Name** box, type **MLLPSendPort**.</span></span>  
  
4.  <span data-ttu-id="c36bc-109">**型** **MLLP**です。</span><span class="sxs-lookup"><span data-stu-id="c36bc-109">For **Type**, select **MLLP**.</span></span>  
  
5.  <span data-ttu-id="c36bc-110">クリックして、**構成**の右側にあるボタン、**型**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="c36bc-110">Click the **Configure** button to the right of the **Type** field.</span></span>  
  
6.  <span data-ttu-id="c36bc-111">MLLP トランスポートのプロパティ ダイアログ ボックスの**接続名**入力**MLLPConnection**です。</span><span class="sxs-lookup"><span data-stu-id="c36bc-111">In the MLLP Transport Properties dialog box, for **Connection Name** enter **MLLPConnection**.</span></span> <span data-ttu-id="c36bc-112">**ホスト**入力**localhost**です。</span><span class="sxs-lookup"><span data-stu-id="c36bc-112">For **Host** enter **localhost**.</span></span> <span data-ttu-id="c36bc-113">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c36bc-113">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="c36bc-114">送信ポートのプロパティ ダイアログ ボックスでの**送信パイプライン**を選択**BTAHL72XPipelines.BTAHL72XSendPipeline**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c36bc-114">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="c36bc-115">管理コンソールで、右クリック**MLLPSendPort**ポート、およびクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="c36bc-115">In the Administration Console, right-click **MLLPSendPort** port, and then click **Start**.</span></span>  
  
9. <span data-ttu-id="c36bc-116">展開**プラットフォームの設定**、 をクリックして**ホスト インスタンス**を右クリックして**BizTalkServerApplication**、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="c36bc-116">Expand **Platform Settings**, click **Host Instances**, right-click **BizTalkServerApplication**, and then click **Start**.</span></span> <span data-ttu-id="c36bc-117">ホストが既に実行されている場合にクリックして**再起動**です。</span><span class="sxs-lookup"><span data-stu-id="c36bc-117">If the host is already running, click **Restart**.</span></span>  
  
10. <span data-ttu-id="c36bc-118">をクリックして**オーケストレーション**を右クリックして**BTAHL7_Project.Doorbell_Orchestration**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="c36bc-118">Click **Orchestrations**, right-click **BTAHL7_Project.Doorbell_Orchestration**, and then click **Properties**.</span></span>  
  
11. <span data-ttu-id="c36bc-119">[オーケストレーションのプロパティ] ダイアログ ボックスのコンソール ツリーで、**バインド**です。</span><span class="sxs-lookup"><span data-stu-id="c36bc-119">In the Orchestration Properties dialog box, in the console tree, click **Bindings**.</span></span>  
  
12. <span data-ttu-id="c36bc-120">**バインド**] ウィンドウの**ホスト**[ **BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="c36bc-120">In the **Bindings** pane, for **Host**, select **BizTalkServerApplication**.</span></span>  
  
13. <span data-ttu-id="c36bc-121">**SOAPReceivePort** **WebPort_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**で、**受信ポート**列です。</span><span class="sxs-lookup"><span data-stu-id="c36bc-121">For **SOAPReceivePort**, select **WebPort_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort** in the **Receive Ports** column.</span></span>  
  
14. <span data-ttu-id="c36bc-122">**MLLPSendPort** **MLLPSendPort**で、**送信ポート/送信ポート グループ**列です。</span><span class="sxs-lookup"><span data-stu-id="c36bc-122">For **MLLPSendPort**, select **MLLPSendPort** in the **Send Ports/Send Port Groups** column.</span></span>  
  
15. <span data-ttu-id="c36bc-123">をクリックして**OK**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c36bc-123">Click **OK** to save the changes.</span></span>  
  
## <a name="msh-5-and-msh-6"></a><span data-ttu-id="c36bc-124">MSH 5 と MSH 6</span><span class="sxs-lookup"><span data-stu-id="c36bc-124">MSH 5 and MSH 6</span></span>  
 <span data-ttu-id="c36bc-125">MSH 5 および 6 の MSH ヘッダー フィールドでは、コピー先のアプリケーションと機能をそれぞれ含まれます。</span><span class="sxs-lookup"><span data-stu-id="c36bc-125">The MSH 5 and MSH 6 header fields contain the destination application and facility, respectively.</span></span> <span data-ttu-id="c36bc-126">構成エクスプ ローラーで、MSH 5 と MSH 6 の 3 つのコンポーネントを変更するメッセージの送信先の情報が必要な場合の各値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c36bc-126">In Configuration Explorer, you can specify the values for each of the three components of MSH 5 and MSH 6, in cases when you want the destination information in the message to be changed.</span></span> <span data-ttu-id="c36bc-127">これは、元のメッセージがパーティに固有の情報が含まれない場合に可能性の高いシナリオです。</span><span class="sxs-lookup"><span data-stu-id="c36bc-127">This is a likely scenario when the original message does not include party-specific information.</span></span> <span data-ttu-id="c36bc-128">この手順では、宣言 (パブリッシャー/サブスクライバー) モデルに該当します。</span><span class="sxs-lookup"><span data-stu-id="c36bc-128">This step is applicable in the declarative (publisher/subscriber) model.</span></span> <span data-ttu-id="c36bc-129">環境内で適切である場合は、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c36bc-129">You perform this step if it is applicable in your environment.</span></span> <span data-ttu-id="c36bc-130">これらの値の設定の詳細については、次を参照してください。 [BTAHL7 構成エクスプ ローラーの パーティ -](parties-tab.md)です。</span><span class="sxs-lookup"><span data-stu-id="c36bc-130">For more information about setting these values, see [Parties - BTAHL7 Configuration Explorer](parties-tab.md).</span></span>  
  
 <span data-ttu-id="c36bc-131">進みます[手順 16.: オーケストレーションを開始](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md)です。</span><span class="sxs-lookup"><span data-stu-id="c36bc-131">Proceed to [Step 16: Start the Orchestration](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c36bc-132">参照</span><span class="sxs-lookup"><span data-stu-id="c36bc-132">See Also</span></span>  
 [<span data-ttu-id="c36bc-133">メッセージの強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="c36bc-133">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)