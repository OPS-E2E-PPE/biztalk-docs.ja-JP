---
title: "送信図形を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Send shape [Orchestration Designer], delivery notification
- send ports, delivery notifications
- configuring [Orchestration Designer], Send shapes
- Send shape [Orchestration Designer], configuring
- delivery notification
- messages, delivery notification
ms.assetid: 2cf4755b-1cfc-484e-bd9c-c9f3855af556
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c32711b841b915d793e5c8a22ffe9513e2ec28d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-send-shape"></a><span data-ttu-id="575cb-102">送信図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="575cb-102">How to Configure the Send Shape</span></span>
![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")  
<span data-ttu-id="575cb-103">送信図形</span><span class="sxs-lookup"><span data-stu-id="575cb-103">Send shape</span></span>  
  
 <span data-ttu-id="575cb-104">送信したメッセージへの応答を間接的または非同期的に受信する (要求 - 応答ポートを使用しないで受信する) 場合は、応答者が適切なインスタンスに応答できるように、送信したメッセージを現在実行中のオーケストレーションのインスタンスに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="575cb-104">If you expect to receive an indirect or asynchronous response (not using a request-response port) to the message that you have sent, you need to correlate the message with the currently running instance of the orchestration, so that the respondent can get the response to the correct instance.</span></span> <span data-ttu-id="575cb-105">次の関連付けに設定を適用することができます、**送信**既にイニシャライズするかの図形にイニシャライズ関連付けセットを適用できます。</span><span class="sxs-lookup"><span data-stu-id="575cb-105">You can apply a following correlation set to the **Send** shape for a previously initialized correlation, or you can apply an initializing correlation set.</span></span> <span data-ttu-id="575cb-106">詳細については、次を参照してください。[オーケストレーションでの相関関係を使用して](../core/using-correlations-in-orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="575cb-106">For more information, see [Using Correlations in Orchestrations](../core/using-correlations-in-orchestrations.md).</span></span>  
  
### <a name="to-configure-a-send-shape"></a><span data-ttu-id="575cb-107">送信図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="575cb-107">To configure a Send shape</span></span>  
  
1.  <span data-ttu-id="575cb-108">メッセージとポート操作を設定します。</span><span class="sxs-lookup"><span data-stu-id="575cb-108">Set a message and a port operation.</span></span>  
  
    1.  <span data-ttu-id="575cb-109">[オーケストレーションの種類] ウィンドウで、送信するマルチパート メッセージの種類に対して定義されているメッセージとポート操作の両方がオーケストレーションにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="575cb-109">In the Orchestration View window, verify that your orchestration has both a message and a port operation defined for the multi-part message type being sent.</span></span>  
  
    2.  <span data-ttu-id="575cb-110">[プロパティ] ウィンドウでから送信するメッセージを選択、**メッセージ**プロパティ ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="575cb-110">In the Properties window, select the message to send from the **Message** property drop-down list.</span></span>  
  
    3.  <span data-ttu-id="575cb-111">[プロパティ] ウィンドウでからメッセージを送信するポート操作を選択、**ポート操作**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="575cb-111">In the Properties window, select the port operation that sends the message from the **Port Operation** drop-down list.</span></span>  
  
         <span data-ttu-id="575cb-112">- または -</span><span class="sxs-lookup"><span data-stu-id="575cb-112">—Or—</span></span>  
  
         <span data-ttu-id="575cb-113">送信コネクタをドラッグして、**送信**メッセージを送信するポート ソケットに図形です。</span><span class="sxs-lookup"><span data-stu-id="575cb-113">Drag the send connector from the **Send** shape to the port socket that sends the message.</span></span>  
  
2.  <span data-ttu-id="575cb-114">メッセージの制限に相関関係のセットを指定する、**送信**図形が送信または関連付けセット内の値を初期化するためにします。</span><span class="sxs-lookup"><span data-stu-id="575cb-114">Specify correlation sets to restrict the messages the **Send** shape will send or to initialize the values in a correlation set.</span></span>  
  
    1.  <span data-ttu-id="575cb-115">各関連付けセットが使用する場合、ドロップダウン リストから設定の相関関係を確認して、**フォロー関連付けセット**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="575cb-115">For each correlation set you want to use, check a correlation set from the drop-down on the **Following Correlation Sets** property.</span></span>  
  
    2.  <span data-ttu-id="575cb-116">各関連付けセットを初期化する場合、ドロップダウン リストから設定の相関関係を確認して、**イニシャライズ関連付けセット**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="575cb-116">For each correlation set that you want to initialize, check a correlation set from the drop-down on the **Initializing Correlation Sets** property.</span></span>  
  
## <a name="delivery-notification"></a><span data-ttu-id="575cb-117">[配信通知]</span><span class="sxs-lookup"><span data-stu-id="575cb-117">Delivery Notification</span></span>  
 <span data-ttu-id="575cb-118">送信ポートでメッセージが正常に送信されたかどうかをテストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="575cb-118">To test whether you have successfully sent a message over a send port, complete the following steps:</span></span>  
  
1.  <span data-ttu-id="575cb-119">トランザクション以外のスコープ、長時間のスコープ、またはアトミックのスコープ内に送信図形を配置します。</span><span class="sxs-lookup"><span data-stu-id="575cb-119">Put your Send shape in a non-transactional, long-running or atomic scope.</span></span>  
  
2.  <span data-ttu-id="575cb-120">送信ポートで、DeliveryNotification プロパティを設定**送信**です。</span><span class="sxs-lookup"><span data-stu-id="575cb-120">On your send port, set the DeliveryNotification property to **Transmitted**.</span></span>  
  
3.  <span data-ttu-id="575cb-121">DeliveryFailureException を処理するスコープに catch ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="575cb-121">Add a catch handler to your scope to handle a DeliveryFailureException.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="575cb-122">送信図形は、アトミックのスコープ内に含まれる、DeliveryFailureException を引き続きキャッチできますは、トランザクションの種類に設定された外側のスコープ図形を追加する必要があります**長時間**または**None**.</span><span class="sxs-lookup"><span data-stu-id="575cb-122">If the Send shape is contained within an atomic scope, the DeliveryFailureException can still be caught, but will require an outer scope shape be added with a Transaction Type set to **Long Running** or **None**.</span></span> <span data-ttu-id="575cb-123">アトミックのスコープは、直接例外をキャッチすることはできません。</span><span class="sxs-lookup"><span data-stu-id="575cb-123">Atomic scopes are not able to catch exceptions directly.</span></span>  
  
 <span data-ttu-id="575cb-124">オーケストレーションは、囲んでいる非アトミックなスコープの最後、またはオーケストレーションの最後に、受信確認応答を受信するために待機します。</span><span class="sxs-lookup"><span data-stu-id="575cb-124">The orchestration waits for acknowledgment at the end of the enclosing non-atomic scope, or the end of the orchestration, to receive the acknowledgment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="575cb-125">これは一方向の処理のみに適用され、SoapException の双方向 (要求 - 応答) の処理 (否定受信確認) は、ポート属性が設定されていない場合でもエラーとなります。</span><span class="sxs-lookup"><span data-stu-id="575cb-125">This applies only to one-way operations; failure in two-way (request-response) operations results in a SoapException (negative acknowledgement) even without the port attribute being set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="575cb-126">配信通知では、直接バインドはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="575cb-126">Delivery notification is not supported for direct binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="575cb-127">参照</span><span class="sxs-lookup"><span data-stu-id="575cb-127">See Also</span></span>  
 [<span data-ttu-id="575cb-128">エラー処理</span><span class="sxs-lookup"><span data-stu-id="575cb-128">Error Handling</span></span>](../core/error-handling.md)