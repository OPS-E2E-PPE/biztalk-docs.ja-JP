---
title: "セッション Management1 に関する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1848619-d97a-4f1e-ba94-59861bd7aedf
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 336deb34e5587e64c5177cd0a439c756cf0f2b61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="about-session-management"></a><span data-ttu-id="d6e66-102">セッション管理について</span><span class="sxs-lookup"><span data-stu-id="d6e66-102">About Session Management</span></span>
<span data-ttu-id="d6e66-103">Microsoft BizTalk Adapter for JD Edwards OneWorld は、JD Edwards OneWorld サーバーの呼び出しを送信する接続セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d6e66-103">The Microsoft BizTalk Adapter for JD Edwards OneWorld creates a connection session to send a call to the JD Edwards OneWorld server.</span></span> <span data-ttu-id="d6e66-104">呼び出しが終了すると、セッションはプールに格納され、その後の呼び出しで再利用されます。</span><span class="sxs-lookup"><span data-stu-id="d6e66-104">When the call terminates, the session is put in a pool to be re-used by a subsequent call.</span></span> <span data-ttu-id="d6e66-105">このアダプターは、JD Edwards OneWorld サーバーの同時呼び出しを処理する複数の接続セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d6e66-105">The adapter creates multiple connection sessions to handle concurrent calls to the JD Edwards OneWorld server.</span></span> <span data-ttu-id="d6e66-106">プールは不要になったセッションを削除するために定期的に消去されます。</span><span class="sxs-lookup"><span data-stu-id="d6e66-106">The pool is periodically cleaned to remove sessions that are no longer necessary.</span></span>  
  
 <span data-ttu-id="d6e66-107">Microsoft BizTalk Adapter for JD Edwards OneWorld には、1 つのセッション内で呼び出しがいつ発生する必要があるかを制御するメッセージ コンテキスト プロパティが 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="d6e66-107">The Microsoft BizTalk Adapter for JD Edwards OneWorld provides two message context properties to control when calls must occur within the same session.</span></span>  
  
|<span data-ttu-id="d6e66-108">名前</span><span class="sxs-lookup"><span data-stu-id="d6e66-108">Name</span></span>|<span data-ttu-id="d6e66-109">型</span><span class="sxs-lookup"><span data-stu-id="d6e66-109">Type</span></span>|<span data-ttu-id="d6e66-110">既定値</span><span class="sxs-lookup"><span data-stu-id="d6e66-110">Default</span></span>|  
|----------|----------|-------------|  
|<span data-ttu-id="d6e66-111">JDE.SessionID</span><span class="sxs-lookup"><span data-stu-id="d6e66-111">JDE.SessionID</span></span>|<span data-ttu-id="d6e66-112">int</span><span class="sxs-lookup"><span data-stu-id="d6e66-112">Int</span></span>|<span data-ttu-id="d6e66-113">0</span><span class="sxs-lookup"><span data-stu-id="d6e66-113">0</span></span>|  
|<span data-ttu-id="d6e66-114">JDE.ReserveSession</span><span class="sxs-lookup"><span data-stu-id="d6e66-114">JDE.ReserveSession</span></span>|<span data-ttu-id="d6e66-115">boolean</span><span class="sxs-lookup"><span data-stu-id="d6e66-115">boolean</span></span>|<span data-ttu-id="d6e66-116">オプション</span><span class="sxs-lookup"><span data-stu-id="d6e66-116">false</span></span>|  
  
 <span data-ttu-id="d6e66-117">ビジネス関数で JD Edwards OneWorld サーバーを 1 回だけ呼び出す必要がある場合、セッション管理は不要です。</span><span class="sxs-lookup"><span data-stu-id="d6e66-117">Session management is unnecessary if the business function requires a single call to the JD Edwards OneWorld server.</span></span> <span data-ttu-id="d6e66-118">このアダプタは使用可能なセッションを選択でき、そのセッションは後続の呼び出しでも使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="d6e66-118">The adapter can pick any available session and the session remains available for any following calls.</span></span> <span data-ttu-id="d6e66-119">このシナリオでは、既定値のままで適切であるため、メッセージ コンテキスト プロパティは無視できます。</span><span class="sxs-lookup"><span data-stu-id="d6e66-119">In this scenario, you can ignore the message context properties as the defaults are appropriate.</span></span>  
  
 <span data-ttu-id="d6e66-120">一部の JD Edwards OneWorld 機能では、JD Edwards OneWorld サーバーを複数回呼び出す必要があります (SalesOrder の作成など)。</span><span class="sxs-lookup"><span data-stu-id="d6e66-120">Some JD Edwards OneWorld functionality requires multiple calls to the JD Edwards OneWorld server; for example, the creation of a SalesOrder.</span></span> <span data-ttu-id="d6e66-121">最初に BeginDoc を呼び出したときに、空の SalesOrder が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d6e66-121">The first call to BeginDoc creates an empty SalesOrder.</span></span> <span data-ttu-id="d6e66-122">その後の EditLine の呼び出しでは、1 行の項目が SalesOrder に追加されます。</span><span class="sxs-lookup"><span data-stu-id="d6e66-122">Each subsequent call to EditLine adds one line item to the SalesOrder.</span></span> <span data-ttu-id="d6e66-123">最後に EndDoc を呼び出したときに、SalesOrder が閉じられます。</span><span class="sxs-lookup"><span data-stu-id="d6e66-123">Finally the call to EndDoc closes the SalesOrder.</span></span>  
  
```  
BeginDoc  
   EditLine  
   EditLine  
   ...  
EndDoc  
```  
  
 <span data-ttu-id="d6e66-124">1 つの SalesOrder に対するすべての呼び出しは、1 回のセッションで送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6e66-124">To be successful, all the calls for a single SalesOrder must be sent on the same session.</span></span> <span data-ttu-id="d6e66-125">この操作を行うには、セッションの処理方法をアダプタに指示するために、メッセージ コンテキスト プロパティを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d6e66-125">To do this, assign message context properties to instruct the adapter what to do with the session.</span></span> <span data-ttu-id="d6e66-126">SalesOrder の例では、次の表の値が JD OneWorld セッションを処理するためにメッセージ コンテキスト プロパティに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d6e66-126">For the SalesOrder example, these are the values that would be assigned to the message context properties to handle the JD OneWorld session:</span></span>  
  
|<span data-ttu-id="d6e66-127">関数</span><span class="sxs-lookup"><span data-stu-id="d6e66-127">Function</span></span>|<span data-ttu-id="d6e66-128">SessionID</span><span class="sxs-lookup"><span data-stu-id="d6e66-128">SessionID</span></span>|<span data-ttu-id="d6e66-129">ReserveSession</span><span class="sxs-lookup"><span data-stu-id="d6e66-129">ReserveSession</span></span>|  
|--------------|---------------|--------------------|  
|<span data-ttu-id="d6e66-130">BeginDoc</span><span class="sxs-lookup"><span data-stu-id="d6e66-130">BeginDoc</span></span>|<span data-ttu-id="d6e66-131">0</span><span class="sxs-lookup"><span data-stu-id="d6e66-131">0</span></span>|<span data-ttu-id="d6e66-132">true</span><span class="sxs-lookup"><span data-stu-id="d6e66-132">true</span></span>|  
|<span data-ttu-id="d6e66-133">EditLine</span><span class="sxs-lookup"><span data-stu-id="d6e66-133">EditLine</span></span>|<span data-ttu-id="d6e66-134">BeginDoc 応答からのコピー</span><span class="sxs-lookup"><span data-stu-id="d6e66-134">Copied from BeginDoc reply</span></span>|<span data-ttu-id="d6e66-135">true</span><span class="sxs-lookup"><span data-stu-id="d6e66-135">true</span></span>|  
|<span data-ttu-id="d6e66-136">EditLine</span><span class="sxs-lookup"><span data-stu-id="d6e66-136">EditLine</span></span>|<span data-ttu-id="d6e66-137">BeginDoc 応答からのコピー</span><span class="sxs-lookup"><span data-stu-id="d6e66-137">Copied from BeginDoc reply</span></span>|<span data-ttu-id="d6e66-138">true</span><span class="sxs-lookup"><span data-stu-id="d6e66-138">true</span></span>|  
|<span data-ttu-id="d6e66-139">EndDoc</span><span class="sxs-lookup"><span data-stu-id="d6e66-139">EndDoc</span></span>|<span data-ttu-id="d6e66-140">BeginDoc 応答からのコピー</span><span class="sxs-lookup"><span data-stu-id="d6e66-140">Copied from BeginDoc reply</span></span>|<span data-ttu-id="d6e66-141">オプション</span><span class="sxs-lookup"><span data-stu-id="d6e66-141">false</span></span>|  
  
-   <span data-ttu-id="d6e66-142">最初の呼び出しについては、アダプタは任意の使用可能なセッションを自由に選択できます (SessionID がゼロであるため)。</span><span class="sxs-lookup"><span data-stu-id="d6e66-142">For the first call, the adapter is free to choose any available session (because the SessionID is zero).</span></span>  
  
-   <span data-ttu-id="d6e66-143">アダプタは、BeginDoc 応答で使用された SessionID を返します。</span><span class="sxs-lookup"><span data-stu-id="d6e66-143">The adapter returns the SessionID that was used in the BeginDoc reply.</span></span>  
  
-   <span data-ttu-id="d6e66-144">ReserveSession プロパティは、このセッションを明示的に要求する後続の呼び出しのためにこのセッションを予約しておくようにアダプタに指示します。</span><span class="sxs-lookup"><span data-stu-id="d6e66-144">The ReserveSession property tells the adapter to reserve this session for following calls that explicitly requests this session.</span></span> <span data-ttu-id="d6e66-145">このセッションは予約済みであるため、他の呼び出しによって誤って再利用されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d6e66-145">No other calls can accidentally re-use the session because it is reserved.</span></span>  
  
-   <span data-ttu-id="d6e66-146">後続の呼び出しでは、SessionID を BeginDoc で返された値に設定することにより、このセッションが要求されます。</span><span class="sxs-lookup"><span data-stu-id="d6e66-146">Subsequent calls request the session by setting the SessionID to the value returned in BeginDoc.</span></span>  
  
-   <span data-ttu-id="d6e66-147">ReserveSession プロパティは、少なくとも、一連の呼び出しの最後までは、true に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d6e66-147">The ReserveSession property is set to true, at least until the last call in the series.</span></span>  
  
-   <span data-ttu-id="d6e66-148">最後の呼び出しで、ReserveSession が false に設定され、その後の任意の呼び出しでこのセッションが使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="d6e66-148">The last call sets ReserveSession to false to make the session available to any following call.</span></span> <span data-ttu-id="d6e66-149">ただし、オーケストレーションではその後の呼び出しでもこのセッションを保持することができます。</span><span class="sxs-lookup"><span data-stu-id="d6e66-149">However, the orchestration can elect to keep the session for more calls.</span></span>  
  
 <span data-ttu-id="d6e66-150">セッションがしばらく使用されない場合は、セッションが誤ってまだ予約されている場合であっても、プールによるガベージ コレクションが行われます。</span><span class="sxs-lookup"><span data-stu-id="d6e66-150">If the session is not used for a while, it will be garbage-collected by the pool, even if the session is still reserved by mistake.</span></span>  
  
 <span data-ttu-id="d6e66-151">メッセージ コンテキスト プロパティの詳細については、BizTalk Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6e66-151">Refer to BizTalk Server documentation for more details on message context properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6e66-152">参照</span><span class="sxs-lookup"><span data-stu-id="d6e66-152">See Also</span></span>  
 <span data-ttu-id="d6e66-153">[メッセージ コンテキスト プロパティの使用](../core/using-message-context-properties2.md) </span><span class="sxs-lookup"><span data-stu-id="d6e66-153">[Using Message Context Properties](../core/using-message-context-properties2.md) </span></span>  
 <span data-ttu-id="d6e66-154">[メッセージ コンテキスト プロパティの値を割り当てる方法](../core/how-to-assign-message-context-property-values2.md) </span><span class="sxs-lookup"><span data-stu-id="d6e66-154">[How to Assign Message Context Property Values](../core/how-to-assign-message-context-property-values2.md) </span></span>  
 [<span data-ttu-id="d6e66-155">チュートリアル: BizTalk アダプターを使用して JD Edwards OneWorld の</span><span class="sxs-lookup"><span data-stu-id="d6e66-155">Tutorial: Using the BizTalk Adapter for JD Edwards OneWorld</span></span>](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld.md)