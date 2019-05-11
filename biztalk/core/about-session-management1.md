---
title: セッション Management1 について |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1848619-d97a-4f1e-ba94-59861bd7aedf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1aac0705bc4c9b90b73249a0806aa4b0a8b1aa48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362313"
---
# <a name="about-session-management"></a><span data-ttu-id="ab630-102">セッション管理について</span><span class="sxs-lookup"><span data-stu-id="ab630-102">About Session Management</span></span>
<span data-ttu-id="ab630-103">Microsoft BizTalk Adapter for JD Edwards OneWorld は、JD Edwards OneWorld サーバーへの呼び出しを送信する接続セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab630-103">The Microsoft BizTalk Adapter for JD Edwards OneWorld creates a connection session to send a call to the JD Edwards OneWorld server.</span></span> <span data-ttu-id="ab630-104">呼び出しが終了すると、セッションは、後続の呼び出しで再利用するプールに格納されます。</span><span class="sxs-lookup"><span data-stu-id="ab630-104">When the call terminates, the session is put in a pool to be re-used by a subsequent call.</span></span> <span data-ttu-id="ab630-105">アダプターは、JD Edwards OneWorld サーバーへの同時呼び出しを処理する複数の接続セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab630-105">The adapter creates multiple connection sessions to handle concurrent calls to the JD Edwards OneWorld server.</span></span> <span data-ttu-id="ab630-106">プールが不要になったセッションを削除する定期的にクリーンアップされます。</span><span class="sxs-lookup"><span data-stu-id="ab630-106">The pool is periodically cleaned to remove sessions that are no longer necessary.</span></span>  
  
 <span data-ttu-id="ab630-107">Microsoft BizTalk Adapter for JD Edwards OneWorld は、呼び出しする必要があります、同じセッション内で発生したときに制御する 2 つのメッセージ コンテキスト プロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="ab630-107">The Microsoft BizTalk Adapter for JD Edwards OneWorld provides two message context properties to control when calls must occur within the same session.</span></span>  
  
|<span data-ttu-id="ab630-108">名前</span><span class="sxs-lookup"><span data-stu-id="ab630-108">Name</span></span>|<span data-ttu-id="ab630-109">型</span><span class="sxs-lookup"><span data-stu-id="ab630-109">Type</span></span>|<span data-ttu-id="ab630-110">既定</span><span class="sxs-lookup"><span data-stu-id="ab630-110">Default</span></span>|  
|----------|----------|-------------|  
|<span data-ttu-id="ab630-111">JDE します。セッション Id</span><span class="sxs-lookup"><span data-stu-id="ab630-111">JDE.SessionID</span></span>|<span data-ttu-id="ab630-112">Int</span><span class="sxs-lookup"><span data-stu-id="ab630-112">Int</span></span>|<span data-ttu-id="ab630-113">0</span><span class="sxs-lookup"><span data-stu-id="ab630-113">0</span></span>|  
|<span data-ttu-id="ab630-114">JDE します。ReserveSession</span><span class="sxs-lookup"><span data-stu-id="ab630-114">JDE.ReserveSession</span></span>|<span data-ttu-id="ab630-115">boolean</span><span class="sxs-lookup"><span data-stu-id="ab630-115">boolean</span></span>|<span data-ttu-id="ab630-116">false</span><span class="sxs-lookup"><span data-stu-id="ab630-116">false</span></span>|  
  
 <span data-ttu-id="ab630-117">セッション管理は、ビジネス関数には、JD Edwards OneWorld サーバーを 1 回の呼び出しが必要な場合に必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="ab630-117">Session management is unnecessary if the business function requires a single call to the JD Edwards OneWorld server.</span></span> <span data-ttu-id="ab630-118">アダプターが使用可能なセッションを選択し、セッションは後続の呼び出しでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="ab630-118">The adapter can pick any available session and the session remains available for any following calls.</span></span> <span data-ttu-id="ab630-119">このシナリオで、既定値は適切なメッセージ コンテキスト プロパティを無視できます。</span><span class="sxs-lookup"><span data-stu-id="ab630-119">In this scenario, you can ignore the message context properties as the defaults are appropriate.</span></span>  
  
 <span data-ttu-id="ab630-120">一部の JD Edwards OneWorld 機能が、JD Edwards OneWorld サーバーを複数回呼び出す必要があります。たとえば、SalesOrder の作成です。</span><span class="sxs-lookup"><span data-stu-id="ab630-120">Some JD Edwards OneWorld functionality requires multiple calls to the JD Edwards OneWorld server; for example, the creation of a SalesOrder.</span></span> <span data-ttu-id="ab630-121">BeginDoc の最初の呼び出しは、空の SalesOrder を作成します。</span><span class="sxs-lookup"><span data-stu-id="ab630-121">The first call to BeginDoc creates an empty SalesOrder.</span></span> <span data-ttu-id="ab630-122">その後の EditLine の呼び出しでは、SalesOrder を 1 つの行項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="ab630-122">Each subsequent call to EditLine adds one line item to the SalesOrder.</span></span> <span data-ttu-id="ab630-123">最後に EndDoc 呼び出しでは、SalesOrder が閉じられます。</span><span class="sxs-lookup"><span data-stu-id="ab630-123">Finally the call to EndDoc closes the SalesOrder.</span></span>  
  
```  
BeginDoc  
   EditLine  
   EditLine  
   ...  
EndDoc  
```  
  
 <span data-ttu-id="ab630-124">成功するには、同じセッションで 1 つの SalesOrder に対するすべての呼び出しを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab630-124">To be successful, all the calls for a single SalesOrder must be sent on the same session.</span></span> <span data-ttu-id="ab630-125">これを行うには、セッションに対して何を行うアダプターを指示するメッセージ コンテキスト プロパティを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ab630-125">To do this, assign message context properties to instruct the adapter what to do with the session.</span></span> <span data-ttu-id="ab630-126">SalesOrder の例では、次が JD OneWorld セッションを処理するために、メッセージ コンテキスト プロパティに割り当てられる値。</span><span class="sxs-lookup"><span data-stu-id="ab630-126">For the SalesOrder example, these are the values that would be assigned to the message context properties to handle the JD OneWorld session:</span></span>  
  
|<span data-ttu-id="ab630-127">関数</span><span class="sxs-lookup"><span data-stu-id="ab630-127">Function</span></span>|<span data-ttu-id="ab630-128">SessionID</span><span class="sxs-lookup"><span data-stu-id="ab630-128">SessionID</span></span>|<span data-ttu-id="ab630-129">ReserveSession</span><span class="sxs-lookup"><span data-stu-id="ab630-129">ReserveSession</span></span>|  
|--------------|---------------|--------------------|  
|<span data-ttu-id="ab630-130">BeginDoc</span><span class="sxs-lookup"><span data-stu-id="ab630-130">BeginDoc</span></span>|<span data-ttu-id="ab630-131">0</span><span class="sxs-lookup"><span data-stu-id="ab630-131">0</span></span>|<span data-ttu-id="ab630-132">true</span><span class="sxs-lookup"><span data-stu-id="ab630-132">true</span></span>|  
|<span data-ttu-id="ab630-133">EditLine</span><span class="sxs-lookup"><span data-stu-id="ab630-133">EditLine</span></span>|<span data-ttu-id="ab630-134">BeginDoc 応答からコピー</span><span class="sxs-lookup"><span data-stu-id="ab630-134">Copied from BeginDoc reply</span></span>|<span data-ttu-id="ab630-135">true</span><span class="sxs-lookup"><span data-stu-id="ab630-135">true</span></span>|  
|<span data-ttu-id="ab630-136">EditLine</span><span class="sxs-lookup"><span data-stu-id="ab630-136">EditLine</span></span>|<span data-ttu-id="ab630-137">BeginDoc 応答からコピー</span><span class="sxs-lookup"><span data-stu-id="ab630-137">Copied from BeginDoc reply</span></span>|<span data-ttu-id="ab630-138">true</span><span class="sxs-lookup"><span data-stu-id="ab630-138">true</span></span>|  
|<span data-ttu-id="ab630-139">EndDoc</span><span class="sxs-lookup"><span data-stu-id="ab630-139">EndDoc</span></span>|<span data-ttu-id="ab630-140">BeginDoc 応答からコピー</span><span class="sxs-lookup"><span data-stu-id="ab630-140">Copied from BeginDoc reply</span></span>|<span data-ttu-id="ab630-141">false</span><span class="sxs-lookup"><span data-stu-id="ab630-141">false</span></span>|  
  
- <span data-ttu-id="ab630-142">最初の呼び出しでは、アダプターが自由に (SessionID がゼロであるため)、使用可能なセッションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ab630-142">For the first call, the adapter is free to choose any available session (because the SessionID is zero).</span></span>  
  
- <span data-ttu-id="ab630-143">アダプターは、使用された SessionID を BeginDoc 応答で返します。</span><span class="sxs-lookup"><span data-stu-id="ab630-143">The adapter returns the SessionID that was used in the BeginDoc reply.</span></span>  
  
- <span data-ttu-id="ab630-144">ReserveSession プロパティは、このセッションを明示的に要求する次の呼び出しのためには、このセッションを予約するアダプターを指示します。</span><span class="sxs-lookup"><span data-stu-id="ab630-144">The ReserveSession property tells the adapter to reserve this session for following calls that explicitly requests this session.</span></span> <span data-ttu-id="ab630-145">その他の呼び出し誤って再利用しないセッションは予約されています。</span><span class="sxs-lookup"><span data-stu-id="ab630-145">No other calls can accidentally re-use the session because it is reserved.</span></span>  
  
- <span data-ttu-id="ab630-146">後続の呼び出しでは、SessionID を BeginDoc で返される値に設定して、セッションを要求します。</span><span class="sxs-lookup"><span data-stu-id="ab630-146">Subsequent calls request the session by setting the SessionID to the value returned in BeginDoc.</span></span>  
  
- <span data-ttu-id="ab630-147">ReserveSession プロパティは true、少なくとも、シリーズの最後の呼び出しまでに設定します。</span><span class="sxs-lookup"><span data-stu-id="ab630-147">The ReserveSession property is set to true, at least until the last call in the series.</span></span>  
  
- <span data-ttu-id="ab630-148">最後の呼び出しは、ReserveSession をセッションを任意の呼び出しを使用できるようにする場合は false に設定します。</span><span class="sxs-lookup"><span data-stu-id="ab630-148">The last call sets ReserveSession to false to make the session available to any following call.</span></span> <span data-ttu-id="ab630-149">ただし、オーケストレーションより多くの呼び出しのセッションを維持することができます。</span><span class="sxs-lookup"><span data-stu-id="ab630-149">However, the orchestration can elect to keep the session for more calls.</span></span>  
  
  <span data-ttu-id="ab630-150">しばらくの間、セッションを使用しない場合にガベージ コレクト プールで、セッションが誤ってまだ予約されている場合でもです。</span><span class="sxs-lookup"><span data-stu-id="ab630-150">If the session is not used for a while, it will be garbage-collected by the pool, even if the session is still reserved by mistake.</span></span>  
  
  <span data-ttu-id="ab630-151">メッセージ コンテキスト プロパティの詳細については、BizTalk Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab630-151">Refer to BizTalk Server documentation for more details on message context properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab630-152">参照</span><span class="sxs-lookup"><span data-stu-id="ab630-152">See Also</span></span>  
 <span data-ttu-id="ab630-153">[メッセージ コンテキスト プロパティの使用](../core/using-message-context-properties2.md) </span><span class="sxs-lookup"><span data-stu-id="ab630-153">[Using Message Context Properties](../core/using-message-context-properties2.md) </span></span>  
 <span data-ttu-id="ab630-154">[メッセージ コンテキスト プロパティの値を割り当てる方法](../core/how-to-assign-message-context-property-values2.md) </span><span class="sxs-lookup"><span data-stu-id="ab630-154">[How to Assign Message Context Property Values](../core/how-to-assign-message-context-property-values2.md) </span></span>  
 [<span data-ttu-id="ab630-155">チュートリアル: BizTalk Adapter for JD Edwards OneWorld の使用</span><span class="sxs-lookup"><span data-stu-id="ab630-155">Tutorial: Using the BizTalk Adapter for JD Edwards OneWorld</span></span>](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld.md)