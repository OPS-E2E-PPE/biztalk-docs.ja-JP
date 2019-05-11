---
title: 送信図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Send shape [Orchestration Designer], delivery notification
- send ports, delivery notifications
- configuring [Orchestration Designer], Send shapes
- Send shape [Orchestration Designer], configuring
- delivery notification
- messages, delivery notification
ms.assetid: 2cf4755b-1cfc-484e-bd9c-c9f3855af556
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c512b6346608105e1a67cce76c36b8fd705bcc5b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340344"
---
# <a name="how-to-configure-the-send-shape"></a><span data-ttu-id="5e6a1-102">送信図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="5e6a1-102">How to Configure the Send Shape</span></span>
<span data-ttu-id="5e6a1-103">![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")</span><span class="sxs-lookup"><span data-stu-id="5e6a1-103">![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")</span></span>  
<span data-ttu-id="5e6a1-104">送信図形</span><span class="sxs-lookup"><span data-stu-id="5e6a1-104">Send shape</span></span>  
  
 <span data-ttu-id="5e6a1-105">送信したメッセージへの応答を間接的または非同期的に受信する (要求 - 応答ポートを使用しないで受信する) 場合は、応答者が適切なインスタンスに応答できるように、送信したメッセージを現在実行中のオーケストレーションのインスタンスに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e6a1-105">If you expect to receive an indirect or asynchronous response (not using a request-response port) to the message that you have sent, you need to correlate the message with the currently running instance of the orchestration, so that the respondent can get the response to the correct instance.</span></span> <span data-ttu-id="5e6a1-106">フォロー関連付けセット適用することができます、**送信**既にイニシャライズするかの図形にイニシャライズ関連付けセットを適用できます。</span><span class="sxs-lookup"><span data-stu-id="5e6a1-106">You can apply a following correlation set to the **Send** shape for a previously initialized correlation, or you can apply an initializing correlation set.</span></span> <span data-ttu-id="5e6a1-107">詳細については、次を参照してください。[オーケストレーションでの相関関係を使用して](../core/using-correlations-in-orchestrations.md)します。</span><span class="sxs-lookup"><span data-stu-id="5e6a1-107">For more information, see [Using Correlations in Orchestrations](../core/using-correlations-in-orchestrations.md).</span></span>  
  
### <a name="to-configure-a-send-shape"></a><span data-ttu-id="5e6a1-108">送信図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="5e6a1-108">To configure a Send shape</span></span>  
  
1.  <span data-ttu-id="5e6a1-109">メッセージとポート操作を設定します。</span><span class="sxs-lookup"><span data-stu-id="5e6a1-109">Set a message and a port operation.</span></span>  
  
    1.  <span data-ttu-id="5e6a1-110">[オーケストレーションの種類] ウィンドウで、送信するマルチパート メッセージの種類に対して定義されているメッセージとポート操作の両方がオーケストレーションにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e6a1-110">In the Orchestration View window, verify that your orchestration has both a message and a port operation defined for the multi-part message type being sent.</span></span>  
  
    2.  <span data-ttu-id="5e6a1-111">[プロパティ] ウィンドウで選択から送信されるメッセージを**メッセージ**プロパティ ボックスの一覧。</span><span class="sxs-lookup"><span data-stu-id="5e6a1-111">In the Properties window, select the message to send from the **Message** property drop-down list.</span></span>  
  
    3.  <span data-ttu-id="5e6a1-112">[プロパティ] ウィンドウ内からメッセージを送信するポート操作を選択、**ポート操作**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="5e6a1-112">In the Properties window, select the port operation that sends the message from the **Port Operation** drop-down list.</span></span>  
  
         <span data-ttu-id="5e6a1-113">- または -</span><span class="sxs-lookup"><span data-stu-id="5e6a1-113">—Or—</span></span>  
  
         <span data-ttu-id="5e6a1-114">送信コネクタをドラッグして、**送信**図形にメッセージを送信するポート ソケットにします。</span><span class="sxs-lookup"><span data-stu-id="5e6a1-114">Drag the send connector from the **Send** shape to the port socket that sends the message.</span></span>  
  
2.  <span data-ttu-id="5e6a1-115">関連付けはメッセージを制限するセットを指定、**送信**図形が送信または関連付けセット内の値を初期化します。</span><span class="sxs-lookup"><span data-stu-id="5e6a1-115">Specify correlation sets to restrict the messages the **Send** shape will send or to initialize the values in a correlation set.</span></span>  
  
    1.  <span data-ttu-id="5e6a1-116">各関連付けセットを使用する、関連付けのドロップダウン リストからセットを確認してください、**フォロー関連付けセット**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="5e6a1-116">For each correlation set you want to use, check a correlation set from the drop-down on the **Following Correlation Sets** property.</span></span>  
  
    2.  <span data-ttu-id="5e6a1-117">各関連付けセットを初期化することは、ドロップダウン リストから 相関関係を確認してください。、**イニシャライズ関連付けセット**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="5e6a1-117">For each correlation set that you want to initialize, check a correlation set from the drop-down on the **Initializing Correlation Sets** property.</span></span>  
  
## <a name="delivery-notification"></a><span data-ttu-id="5e6a1-118">[配信通知]</span><span class="sxs-lookup"><span data-stu-id="5e6a1-118">Delivery Notification</span></span>  
 <span data-ttu-id="5e6a1-119">送信ポートでメッセージが正常に送信されたかどうかをテストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5e6a1-119">To test whether you have successfully sent a message over a send port, complete the following steps:</span></span>  
  
1. <span data-ttu-id="5e6a1-120">トランザクション以外のスコープ、長時間のスコープ、またはアトミックのスコープ内に送信図形を配置します。</span><span class="sxs-lookup"><span data-stu-id="5e6a1-120">Put your Send shape in a non-transactional, long-running or atomic scope.</span></span>  
  
2. <span data-ttu-id="5e6a1-121">DeliveryNotification プロパティを設定、送信ポートで**送信**します。</span><span class="sxs-lookup"><span data-stu-id="5e6a1-121">On your send port, set the DeliveryNotification property to **Transmitted**.</span></span>  
  
3. <span data-ttu-id="5e6a1-122">DeliveryFailureException を処理するスコープに catch ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="5e6a1-122">Add a catch handler to your scope to handle a DeliveryFailureException.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5e6a1-123">送信図形は、アトミックのスコープ内に含まれる、DeliveryFailureException を引き続きキャッチできますが、外側のスコープ図形を追加する、トランザクションの種類の設定が必要になります**長時間**または**None**.</span><span class="sxs-lookup"><span data-stu-id="5e6a1-123">If the Send shape is contained within an atomic scope, the DeliveryFailureException can still be caught, but will require an outer scope shape be added with a Transaction Type set to **Long Running** or **None**.</span></span> <span data-ttu-id="5e6a1-124">アトミックのスコープは、直接例外をキャッチすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5e6a1-124">Atomic scopes are not able to catch exceptions directly.</span></span>  
  
   <span data-ttu-id="5e6a1-125">オーケストレーションは、囲んでいる非アトミックなスコープの最後、またはオーケストレーションの最後に、受信確認応答を受信するために待機します。</span><span class="sxs-lookup"><span data-stu-id="5e6a1-125">The orchestration waits for acknowledgment at the end of the enclosing non-atomic scope, or the end of the orchestration, to receive the acknowledgment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e6a1-126">これは一方向の処理のみに適用され、SoapException の双方向 (要求 - 応答) の処理 (否定受信確認) は、ポート属性が設定されていない場合でもエラーとなります。</span><span class="sxs-lookup"><span data-stu-id="5e6a1-126">This applies only to one-way operations; failure in two-way (request-response) operations results in a SoapException (negative acknowledgement) even without the port attribute being set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e6a1-127">配信通知では、直接バインドはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="5e6a1-127">Delivery notification is not supported for direct binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e6a1-128">参照</span><span class="sxs-lookup"><span data-stu-id="5e6a1-128">See Also</span></span>  
 [<span data-ttu-id="5e6a1-129">エラー処理</span><span class="sxs-lookup"><span data-stu-id="5e6a1-129">Error Handling</span></span>](../core/error-handling.md)