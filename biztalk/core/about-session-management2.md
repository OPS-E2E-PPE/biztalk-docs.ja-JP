---
title: セッション Management2 について |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3ecdb4f-d384-42ac-9776-e7ad14d5f151
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b316a1a145f6f5d6d839febcc02c1fe2056b9579
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362294"
---
# <a name="about-session-management"></a><span data-ttu-id="259a3-102">セッション管理について</span><span class="sxs-lookup"><span data-stu-id="259a3-102">About Session Management</span></span>
<span data-ttu-id="259a3-103">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne では、JD Edwards EnterpriseOne サーバーへの呼び出しを送信する接続セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="259a3-103">The Microsoft BizTalk Adapter for JD Edwards EnterpriseOne creates a connection session to send a call to the JD Edwards EnterpriseOne server.</span></span> <span data-ttu-id="259a3-104">呼び出しが終了すると、セッションは、後続の呼び出しで再利用するプールに格納されます。</span><span class="sxs-lookup"><span data-stu-id="259a3-104">When the call terminates, the session is put in a pool to be re-used by a subsequent call.</span></span> <span data-ttu-id="259a3-105">アダプターは、JD Edwards EnterpriseOne サーバーに対する同時呼び出しを処理する複数の接続セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="259a3-105">The adapter creates multiple connection sessions to handle concurrent calls to the JD Edwards EnterpriseOne server.</span></span> <span data-ttu-id="259a3-106">プールが不要になったセッションを削除する定期的にクリーンアップされます。</span><span class="sxs-lookup"><span data-stu-id="259a3-106">The pool is periodically cleaned to remove sessions that are no longer necessary.</span></span>  
  
 <span data-ttu-id="259a3-107">Microsoft BizTalk Adapter JD Edwards EnterpriseOne は、呼び出しする必要があります、同じセッション内で発生したときに制御する 2 つのメッセージ コンテキスト プロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="259a3-107">The Microsoft BizTalk Adapter JD Edwards EnterpriseOne provides two message context properties to control when calls must occur within the same session.</span></span>  
  
|<span data-ttu-id="259a3-108">名前</span><span class="sxs-lookup"><span data-stu-id="259a3-108">Name</span></span>|<span data-ttu-id="259a3-109">型</span><span class="sxs-lookup"><span data-stu-id="259a3-109">Type</span></span>|<span data-ttu-id="259a3-110">既定</span><span class="sxs-lookup"><span data-stu-id="259a3-110">Default</span></span>|  
|----------|----------|-------------|  
|<span data-ttu-id="259a3-111">JDE します。セッション Id</span><span class="sxs-lookup"><span data-stu-id="259a3-111">JDE.SessionID</span></span>|<span data-ttu-id="259a3-112">Int</span><span class="sxs-lookup"><span data-stu-id="259a3-112">Int</span></span>|<span data-ttu-id="259a3-113">0</span><span class="sxs-lookup"><span data-stu-id="259a3-113">0</span></span>|  
|<span data-ttu-id="259a3-114">JDE します。ReserveSession</span><span class="sxs-lookup"><span data-stu-id="259a3-114">JDE.ReserveSession</span></span>|<span data-ttu-id="259a3-115">boolean</span><span class="sxs-lookup"><span data-stu-id="259a3-115">boolean</span></span>|<span data-ttu-id="259a3-116">false</span><span class="sxs-lookup"><span data-stu-id="259a3-116">false</span></span>|  
  
 <span data-ttu-id="259a3-117">セッション管理は、ビジネス関数には、JD Edwards EnterpriseOne サーバーを 1 回の呼び出しが必要な場合に必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="259a3-117">Session management is unnecessary if the business function requires a single call to the JD Edwards EnterpriseOne server.</span></span> <span data-ttu-id="259a3-118">アダプターが使用可能なセッションを選択し、セッションは後続の呼び出しでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="259a3-118">The adapter can pick any available session and the session remains available for any following calls.</span></span> <span data-ttu-id="259a3-119">このシナリオで、既定値は適切なメッセージ コンテキスト プロパティを無視できます。</span><span class="sxs-lookup"><span data-stu-id="259a3-119">In this scenario, you can ignore the message context properties as the defaults are appropriate.</span></span>  
  
 <span data-ttu-id="259a3-120">一部の JD Edwards EnterpriseOne 機能が、JD Edwards EnterpriseOne サーバーを複数回呼び出す必要があります。たとえば、SalesOrder の作成です。</span><span class="sxs-lookup"><span data-stu-id="259a3-120">Some JD Edwards EnterpriseOne functionality requires multiple calls to the JD Edwards EnterpriseOne server; for example, the creation of a SalesOrder.</span></span> <span data-ttu-id="259a3-121">BeginDoc の最初の呼び出しは、空の SalesOrder を作成します。</span><span class="sxs-lookup"><span data-stu-id="259a3-121">The first call to BeginDoc creates an empty SalesOrder.</span></span> <span data-ttu-id="259a3-122">その後の EditLine の呼び出しでは、SalesOrder を 1 つの行項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="259a3-122">Each subsequent call to EditLine adds one line item to the SalesOrder.</span></span> <span data-ttu-id="259a3-123">最後に EndDoc 呼び出しでは、SalesOrder が閉じられます。</span><span class="sxs-lookup"><span data-stu-id="259a3-123">Finally the call to EndDoc closes the SalesOrder.</span></span>  
  
```  
BeginDoc  
   EditLine  
   EditLine  
   ...  
EndDoc  
```  
  
 <span data-ttu-id="259a3-124">成功するには、同じセッションで 1 つの SalesOrder に対するすべての呼び出しを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="259a3-124">To be successful, all the calls for a single SalesOrder must be sent on the same session.</span></span> <span data-ttu-id="259a3-125">これを行うには、セッションに対して何を行うアダプターを指示するメッセージ コンテキスト プロパティを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="259a3-125">To do this, assign message context properties to instruct the adapter what to do with the session.</span></span> <span data-ttu-id="259a3-126">SalesOrder の例では、JD Edwards EnterpriseOne セッションを処理するために、メッセージ コンテキスト プロパティに割り当てられる値は、これらは。</span><span class="sxs-lookup"><span data-stu-id="259a3-126">For the SalesOrder example, these are the values that would be assigned to the message context properties to handle the JD Edwards EnterpriseOne session:</span></span>  
  
|<span data-ttu-id="259a3-127">関数</span><span class="sxs-lookup"><span data-stu-id="259a3-127">Function</span></span>|<span data-ttu-id="259a3-128">SessionID</span><span class="sxs-lookup"><span data-stu-id="259a3-128">SessionID</span></span>|<span data-ttu-id="259a3-129">ReserveSession</span><span class="sxs-lookup"><span data-stu-id="259a3-129">ReserveSession</span></span>|  
|--------------|---------------|--------------------|  
|<span data-ttu-id="259a3-130">BeginDoc</span><span class="sxs-lookup"><span data-stu-id="259a3-130">BeginDoc</span></span>|<span data-ttu-id="259a3-131">0</span><span class="sxs-lookup"><span data-stu-id="259a3-131">0</span></span>|<span data-ttu-id="259a3-132">true</span><span class="sxs-lookup"><span data-stu-id="259a3-132">true</span></span>|  
|<span data-ttu-id="259a3-133">EditLine</span><span class="sxs-lookup"><span data-stu-id="259a3-133">EditLine</span></span>|<span data-ttu-id="259a3-134">BeginDoc 応答からコピー</span><span class="sxs-lookup"><span data-stu-id="259a3-134">Copied from BeginDoc reply</span></span>|<span data-ttu-id="259a3-135">true</span><span class="sxs-lookup"><span data-stu-id="259a3-135">true</span></span>|  
|<span data-ttu-id="259a3-136">EditLine</span><span class="sxs-lookup"><span data-stu-id="259a3-136">EditLine</span></span>|<span data-ttu-id="259a3-137">BeginDoc 応答からコピー</span><span class="sxs-lookup"><span data-stu-id="259a3-137">Copied from BeginDoc reply</span></span>|<span data-ttu-id="259a3-138">true</span><span class="sxs-lookup"><span data-stu-id="259a3-138">true</span></span>|  
|<span data-ttu-id="259a3-139">EndDoc</span><span class="sxs-lookup"><span data-stu-id="259a3-139">EndDoc</span></span>|<span data-ttu-id="259a3-140">BeginDoc 応答からコピー</span><span class="sxs-lookup"><span data-stu-id="259a3-140">Copied from  BeginDoc reply</span></span>|<span data-ttu-id="259a3-141">false</span><span class="sxs-lookup"><span data-stu-id="259a3-141">false</span></span>|  
  
- <span data-ttu-id="259a3-142">最初の呼び出しでは、アダプターが自由に (SessionID がゼロであるため)、使用可能なセッションを選択します。</span><span class="sxs-lookup"><span data-stu-id="259a3-142">For the first call, the adapter is free to choose any available session (because the SessionID is zero).</span></span>  
  
- <span data-ttu-id="259a3-143">アダプターは、使用された SessionID を BeginDoc 応答で返します。</span><span class="sxs-lookup"><span data-stu-id="259a3-143">The adapter returns the SessionID that was used in the BeginDoc reply.</span></span>  
  
- <span data-ttu-id="259a3-144">ReserveSession プロパティは、このセッションを明示的に要求する次の呼び出しのためには、このセッションを予約するアダプターを指示します。</span><span class="sxs-lookup"><span data-stu-id="259a3-144">The ReserveSession property tells the adapter to reserve this session for following calls that explicitly requests this session.</span></span> <span data-ttu-id="259a3-145">その他の呼び出し誤って再利用しないセッションは予約されています。</span><span class="sxs-lookup"><span data-stu-id="259a3-145">No other calls can accidentally re-use the session because it is reserved.</span></span>  
  
- <span data-ttu-id="259a3-146">後続の呼び出しでは、SessionID を BeginDoc で返される値に設定して、セッションを要求します。</span><span class="sxs-lookup"><span data-stu-id="259a3-146">Subsequent calls request the session by setting the SessionID to the value returned in BeginDoc.</span></span>  
  
- <span data-ttu-id="259a3-147">ReserveSession プロパティは true、少なくとも、シリーズの最後の呼び出しまでに設定します。</span><span class="sxs-lookup"><span data-stu-id="259a3-147">The ReserveSession property is set to true, at least until the last call in the series.</span></span>  
  
- <span data-ttu-id="259a3-148">最後の呼び出しは、ReserveSession をセッションを任意の呼び出しを使用できるようにする場合は false に設定します。</span><span class="sxs-lookup"><span data-stu-id="259a3-148">The last call sets ReserveSession to false to make the session available to any following call.</span></span> <span data-ttu-id="259a3-149">ただし、オーケストレーションより多くの呼び出しのセッションを維持することができます。</span><span class="sxs-lookup"><span data-stu-id="259a3-149">However, the orchestration can elect to keep the session for more calls.</span></span>  
  
  <span data-ttu-id="259a3-150">しばらくの間、セッションを使用しない場合にガベージ コレクト プールで、セッションが誤ってまだ予約されている場合でもです。</span><span class="sxs-lookup"><span data-stu-id="259a3-150">If the session is not used for a while, it will be garbage-collected by the pool, even if the session is still reserved by mistake.</span></span>  
  
  <span data-ttu-id="259a3-151">メッセージ コンテキスト プロパティの詳細については、BizTalk Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="259a3-151">Refer to BizTalk Server documentation for more details on message context properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="259a3-152">参照</span><span class="sxs-lookup"><span data-stu-id="259a3-152">See Also</span></span>  
 [<span data-ttu-id="259a3-153">メッセージ コンテキストのプロパティの使用</span><span class="sxs-lookup"><span data-stu-id="259a3-153">Using Message Context Properties</span></span>](../core/using-message-context-properties1.md)