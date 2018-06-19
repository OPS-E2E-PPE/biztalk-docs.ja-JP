---
title: '手順 7: を作成して、ポートの構成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating ports
- private process tutorial, configuring ports
ms.assetid: c00344c6-506a-4560-a948-e5fed2b9fd58
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44a9696f907928f31a740e4d8545567921a82df9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965240"
---
# <a name="step-7-creating-and-configuring-ports"></a><span data-ttu-id="01f51-102">手順 7: を作成して、ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="01f51-102">Step 7: Creating and Configuring Ports</span></span>
<span data-ttu-id="01f51-103">ここでは、ビジネス プロセスとの通信に使用するポートを作成し、構成します。</span><span class="sxs-lookup"><span data-stu-id="01f51-103">In this step, you create and configure the ports you use to communicate with business processes.</span></span> <span data-ttu-id="01f51-104">各ポートには、種類、方向、およびバインドのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="01f51-104">Each port has a type, direction, and binding property.</span></span> <span data-ttu-id="01f51-105">これらのプロパティにより、通信の方向と通信方式、メッセージの送信先と受信元、および通信の実行方法が決定されます。</span><span class="sxs-lookup"><span data-stu-id="01f51-105">These properties establish the direction and pattern of communication, the location of where the message is sent or received, and how the communication occurs.</span></span>  
  
### <a name="to-create-a-logical-send-port"></a><span data-ttu-id="01f51-106">論理送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="01f51-106">To create a logical send port</span></span>  
  
1.  <span data-ttu-id="01f51-107">Visual Studio で、ツールボックスからドラッグして、**ポート**図形をオーケストレーション デザイン画面にし、上にドロップ、**ポート画面**を開くには、**ポート構成ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="01f51-107">In Visual Studio, from the Toolbox, drag the **Port** shape to the orchestration design surface and drop it on the **Port Surface** to open the **Port Configuration Wizard**.</span></span>  
  
2.  <span data-ttu-id="01f51-108">**ポート構成ウィザード**] ページで [**次**です。</span><span class="sxs-lookup"><span data-stu-id="01f51-108">On the **Port Configuration Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="01f51-109">**ポートのプロパティ**] ページの [、**名前**ボックスに、入力**ContosoSQLReqResponsePort**、クリックして **[次へ]** です。</span><span class="sxs-lookup"><span data-stu-id="01f51-109">On the **Port Properties** page, in the **Name** box, type **ContosoSQLReqResponsePort**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="01f51-110">**ポートの種類を選択して**] ページの [、**ポートの種類名**ボックスに、入力**ContosoSQLReqResponsePortName**です。</span><span class="sxs-lookup"><span data-stu-id="01f51-110">On the **Select a Port Type** page, in the **Port Type Name** box, type **ContosoSQLReqResponsePortName**.</span></span>  
  
5.  <span data-ttu-id="01f51-111">**通信パターン****要求-応答**です。</span><span class="sxs-lookup"><span data-stu-id="01f51-111">For **Communication Pattern**, select **Request-Response**.</span></span>  
  
6.  <span data-ttu-id="01f51-112">**アクセス制限****内部 - このプロジェクト限定**、順にクリック**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="01f51-112">For **Access Restrictions**, select **Internal - limited to this project**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="01f51-113">**ポートのバインド** ページで、**要求の送信と応答の受信を行います**のままにして、**ポートのバインド**オプションに設定**後で**、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="01f51-113">On the **Port Binding** page, select **I'll be sending a request and receiving a response**, leave the **Port Binding** option set to **Specify Later**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="01f51-114">をクリックして**完了**ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="01f51-114">Click **Finish** to create the port.</span></span>  
  
### <a name="to-change-the-variable-type-for-the-orchestration-ports"></a><span data-ttu-id="01f51-115">オーケストレーション ポートに関するさまざまな種類を変更するには</span><span class="sxs-lookup"><span data-stu-id="01f51-115">To change the variable type for the orchestration ports</span></span>  
  
1.  <span data-ttu-id="01f51-116">オーケストレーション ビューで、展開**型**、展開**ポートの種類**、展開**ContosoSQLReqResponsePortName**、展開**Operation_1**、クリックして**要求**です。</span><span class="sxs-lookup"><span data-stu-id="01f51-116">In Orchestration View, expand **Types**, expand **Port Types**, expand **ContosoSQLReqResponsePortName**, expand **Operation_1**, and then select **Request**.</span></span>  
  
2.  <span data-ttu-id="01f51-117">プロパティ ウィンドウで、選択、**メッセージの種類**プロパティ、展開**スキーマ** をクリックし、 **\<参照されたアセンブリから選択\>**.</span><span class="sxs-lookup"><span data-stu-id="01f51-117">In the Properties window, select the **Message Type** property, expand **Schemas** and then click **\<Select from referenced assembly\>**.</span></span>  
  
3.  <span data-ttu-id="01f51-118">成果物の種類の選択 ダイアログ ボックスで、をクリックして**ContosoPriceAndAvailability**です。</span><span class="sxs-lookup"><span data-stu-id="01f51-118">In the Select Artifact Type dialog box, click **ContosoPriceAndAvailability**.</span></span>  
  
4.  <span data-ttu-id="01f51-119">右側のペインで選択**rootPriceRequest**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="01f51-119">In the right pane, select **rootPriceRequest**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="01f51-120">オーケストレーション ビューで、 **operation_1****応答**の**ContosoSQLReqResponsePortName**ポートの種類。</span><span class="sxs-lookup"><span data-stu-id="01f51-120">In Orchestration View, under **Operation_1**, select **Response** for the **ContosoSQLReqResponsePortName** port type.</span></span>  
  
6.  <span data-ttu-id="01f51-121">プロパティ ウィンドウで、選択、**メッセージの種類**プロパティ、展開**スキーマ** をクリックし、 \<**参照されたアセンブリから選択\>**.</span><span class="sxs-lookup"><span data-stu-id="01f51-121">In the Properties window, select the **Message Type** property, expand **Schemas** and then click \<**Select from referenced assembly\>**.</span></span>  
  
7.  <span data-ttu-id="01f51-122">**成果物の種類の選択**ダイアログ ボックスで、をクリックして**ContosoPriceAndAvailability**です。</span><span class="sxs-lookup"><span data-stu-id="01f51-122">In the **Select Artifact Type** dialog box, click **ContosoPriceAndAvailability**.</span></span>  
  
8.  <span data-ttu-id="01f51-123">右側のペインで選択 **[rootpriceresponse]**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="01f51-123">In the right pane, select **rootPriceResponse**, and then click **OK**.</span></span>  
  
### <a name="to-connect-the-ports-to-the-receive-shapes"></a><span data-ttu-id="01f51-124">受信側の図形にポートを接続するには</span><span class="sxs-lookup"><span data-stu-id="01f51-124">To connect the ports to the Receive shapes</span></span>  
  
1.  <span data-ttu-id="01f51-125">オーケストレーション デザイン画面で選択、 **Send_1**図形です。</span><span class="sxs-lookup"><span data-stu-id="01f51-125">On the orchestration design surface, select the **Send_1** shape.</span></span>  
  
2.  <span data-ttu-id="01f51-126">[プロパティ] ウィンドウで、選択、**メッセージ**プロパティ、および選択**Contoso3A2RequestMessage**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="01f51-126">In the Properties window, select the **Message** property, and then select **Contoso3A2RequestMessage** from the drop-down list.</span></span>  
  
3.  <span data-ttu-id="01f51-127">接続、 **ContosoSQLReqResponsePort**を横に緑色のハンドルを選択すると、**要求**ラベル上の緑のハンドルにドラッグし、 **Send_1**図形です。</span><span class="sxs-lookup"><span data-stu-id="01f51-127">Connect the **ContosoSQLReqResponsePort** by selecting the green handle next to the **Request** label and dragging it to the green handle on the **Send_1** shape.</span></span>  
  
4.  <span data-ttu-id="01f51-128">オーケストレーション デザイン画面で選択、 **Receive_1**図形です。</span><span class="sxs-lookup"><span data-stu-id="01f51-128">On the orchestration design surface, select the **Receive_1** shape.</span></span>  
  
5.  <span data-ttu-id="01f51-129">[プロパティ] ウィンドウで、選択、**メッセージ**プロパティ、および選択 **[contoso3a2responsemessage]** ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="01f51-129">In the Properties window, select the **Message** property, and then select **Contoso3A2ResponseMessage** from the drop-down list.</span></span>  
  
6.  <span data-ttu-id="01f51-130">接続、 **ContosoSQLReqResponsePort**を横に緑色のハンドルを選択すると、**応答**ラベル上の緑のハンドルにドラッグし、 **Receive_1**図形です。</span><span class="sxs-lookup"><span data-stu-id="01f51-130">Connect the **ContosoSQLReqResponsePort** by selecting the green handle next to the **Response** label and dragging it to the green handle on the **Receive_1** shape.</span></span>  
  
7.  <span data-ttu-id="01f51-131">**ファイル** メニューのをクリックして**すべて保存**です。</span><span class="sxs-lookup"><span data-stu-id="01f51-131">In the **File** Menu, click **Save All**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01f51-132">参照</span><span class="sxs-lookup"><span data-stu-id="01f51-132">See Also</span></span>  
 [<span data-ttu-id="01f51-133">手順 8: Contoso オーケストレーションのビルドと展開</span><span class="sxs-lookup"><span data-stu-id="01f51-133">Step 8: Building and Deploying the Contoso Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-8-building-and-deploying-the-contoso-orchestration.md)