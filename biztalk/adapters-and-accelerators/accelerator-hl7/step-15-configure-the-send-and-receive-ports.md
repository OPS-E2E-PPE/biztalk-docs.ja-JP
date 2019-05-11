---
title: 手順 15:構成、送信ポートと受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, ports
ms.assetid: d532b196-473e-4c8f-b4ed-acef674fc698
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efb16b8222e3ef2c6afebe0aaf63a0e203afc73e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289032"
---
# <a name="step-15-configure-the-send-and-receive-ports"></a><span data-ttu-id="411b5-102">手順 15:構成、送信ポートと受信ポート</span><span class="sxs-lookup"><span data-stu-id="411b5-102">Step 15: Configure the Send and Receive Ports</span></span>
<span data-ttu-id="411b5-103">前の手順で作成論理送信と受信ポートをオーケストレーション デザイナーを使用し、「後で指定」をポートのバインドを設定します。</span><span class="sxs-lookup"><span data-stu-id="411b5-103">In previous steps, you created a logical send and receive port using Orchestration Designer and set the port binding to "Specify Later".</span></span> <span data-ttu-id="411b5-104">この手順では、物理のソースと変換先の場所を定義して、オーケストレーションで作成した論理ポートを物理ポートをバインドして、ポートの構成を確定するのに BizTalk エクスプ ローラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="411b5-104">In this step, you use BizTalk Explorer to finalize the port configuration by defining the physical source and destination locations and binding the physical ports to the logical ports that you created in the orchestration.</span></span>  
  
## <a name="configure-the-send-and-receive-ports"></a><span data-ttu-id="411b5-105">構成、送信ポートと受信ポート</span><span class="sxs-lookup"><span data-stu-id="411b5-105">Configure the send and receive ports</span></span>  
  
1.  <span data-ttu-id="411b5-106">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**を展開し**BizTalk アプリケーション 1**します。</span><span class="sxs-lookup"><span data-stu-id="411b5-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
2.  <span data-ttu-id="411b5-107">右クリックして**送信ポート**に新規作成 をポイントしてクリックして**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="411b5-107">Right-click **Send Ports**, point to New, and then click **Static One-way Send Port**.</span></span>  
  
3.  <span data-ttu-id="411b5-108">送信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに「 **MLLPSendPort**します。</span><span class="sxs-lookup"><span data-stu-id="411b5-108">In the Send Port Properties dialog box, in the **Name** box, type **MLLPSendPort**.</span></span>  
  
4.  <span data-ttu-id="411b5-109">**型**、 **MLLP**します。</span><span class="sxs-lookup"><span data-stu-id="411b5-109">For **Type**, select **MLLP**.</span></span>  
  
5.  <span data-ttu-id="411b5-110">をクリックして、**構成**ボタンの右側に、**型**フィールド。</span><span class="sxs-lookup"><span data-stu-id="411b5-110">Click the **Configure** button to the right of the **Type** field.</span></span>  
  
6.  <span data-ttu-id="411b5-111">MLLP トランスポートのプロパティ ダイアログ ボックスでの**接続名**入力**MLLPConnection**します。</span><span class="sxs-lookup"><span data-stu-id="411b5-111">In the MLLP Transport Properties dialog box, for **Connection Name** enter **MLLPConnection**.</span></span> <span data-ttu-id="411b5-112">**ホスト**入力**localhost**します。</span><span class="sxs-lookup"><span data-stu-id="411b5-112">For **Host** enter **localhost**.</span></span> <span data-ttu-id="411b5-113">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="411b5-113">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="411b5-114">送信ポートのプロパティ ダイアログ ボックスでの**送信パイプライン**を選択します**BTAHL72XPipelines.BTAHL72XSendPipeline**、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="411b5-114">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="411b5-115">管理コンソールで、右クリック**MLLPSendPort**ポート、およびクリックして**開始**します。</span><span class="sxs-lookup"><span data-stu-id="411b5-115">In the Administration Console, right-click **MLLPSendPort** port, and then click **Start**.</span></span>  
  
9. <span data-ttu-id="411b5-116">展開**プラットフォームの設定**、 をクリックして**ホスト インスタンス**を右クリックして**BizTalkServerApplication**、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="411b5-116">Expand **Platform Settings**, click **Host Instances**, right-click **BizTalkServerApplication**, and then click **Start**.</span></span> <span data-ttu-id="411b5-117">ホストが既に実行されている場合はクリックして**再起動**します。</span><span class="sxs-lookup"><span data-stu-id="411b5-117">If the host is already running, click **Restart**.</span></span>  
  
10. <span data-ttu-id="411b5-118">をクリックして**オーケストレーション**を右クリックして**BTAHL7_Project.Doorbell_Orchestration**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="411b5-118">Click **Orchestrations**, right-click **BTAHL7_Project.Doorbell_Orchestration**, and then click **Properties**.</span></span>  
  
11. <span data-ttu-id="411b5-119">オーケストレーションのプロパティ] ダイアログ ボックスのコンソール ツリーで [**バインド**します。</span><span class="sxs-lookup"><span data-stu-id="411b5-119">In the Orchestration Properties dialog box, in the console tree, click **Bindings**.</span></span>  
  
12. <span data-ttu-id="411b5-120">**バインド**ウィンドウの**ホスト**を選択します**BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="411b5-120">In the **Bindings** pane, for **Host**, select **BizTalkServerApplication**.</span></span>  
  
13. <span data-ttu-id="411b5-121">**SOAPReceivePort**、 **WebPort_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**で、**受信ポート**列。</span><span class="sxs-lookup"><span data-stu-id="411b5-121">For **SOAPReceivePort**, select **WebPort_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort** in the **Receive Ports** column.</span></span>  
  
14. <span data-ttu-id="411b5-122">**MLLPSendPort**、 **MLLPSendPort**で、**送信ポート/送信ポート グループ**列。</span><span class="sxs-lookup"><span data-stu-id="411b5-122">For **MLLPSendPort**, select **MLLPSendPort** in the **Send Ports/Send Port Groups** column.</span></span>  
  
15. <span data-ttu-id="411b5-123">**[OK]** をクリックして変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="411b5-123">Click **OK** to save the changes.</span></span>  
  
## <a name="msh-5-and-msh-6"></a><span data-ttu-id="411b5-124">MSH 5 および MSH 6</span><span class="sxs-lookup"><span data-stu-id="411b5-124">MSH 5 and MSH 6</span></span>  
 <span data-ttu-id="411b5-125">MSH 5 および MSH 6 ヘッダー フィールドでは、コピー先のアプリケーションと機能をそれぞれ含まれます。</span><span class="sxs-lookup"><span data-stu-id="411b5-125">The MSH 5 and MSH 6 header fields contain the destination application and facility, respectively.</span></span> <span data-ttu-id="411b5-126">構成エクスプ ローラーで変更するメッセージの変換先の情報を表示する場合の MSH 5 および MSH 6、3 つのコンポーネントの各値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="411b5-126">In Configuration Explorer, you can specify the values for each of the three components of MSH 5 and MSH 6, in cases when you want the destination information in the message to be changed.</span></span> <span data-ttu-id="411b5-127">これは、元のメッセージがパーティに固有の情報が含まれない場合、可能性の高いシナリオです。</span><span class="sxs-lookup"><span data-stu-id="411b5-127">This is a likely scenario when the original message does not include party-specific information.</span></span> <span data-ttu-id="411b5-128">この手順は、宣言型 (パブリッシャー/サブスクライバー) モデルに適用できます。</span><span class="sxs-lookup"><span data-stu-id="411b5-128">This step is applicable in the declarative (publisher/subscriber) model.</span></span> <span data-ttu-id="411b5-129">環境内で該当する場合は、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="411b5-129">You perform this step if it is applicable in your environment.</span></span> <span data-ttu-id="411b5-130">これらの値を設定する方法についての詳細については、次を参照してください。[パーティー - BTAHL7 構成エクスプ ローラー](parties-tab.md)します。</span><span class="sxs-lookup"><span data-stu-id="411b5-130">For more information about setting these values, see [Parties - BTAHL7 Configuration Explorer](parties-tab.md).</span></span>  
  
 <span data-ttu-id="411b5-131">続行する[手順 16。オーケストレーションを開始](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md)します。</span><span class="sxs-lookup"><span data-stu-id="411b5-131">Proceed to [Step 16: Start the Orchestration](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="411b5-132">参照</span><span class="sxs-lookup"><span data-stu-id="411b5-132">See Also</span></span>  
 [<span data-ttu-id="411b5-133">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="411b5-133">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)