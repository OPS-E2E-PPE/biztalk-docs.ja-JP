---
title: Catch の例外 Block6 を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exception handling, Catch Exception block
- Catch Exception blocks
- exceptions, Catch Exception block
ms.assetid: 404312dd-773b-44fe-8b65-7de3d0af2f79
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a84b37953e05c83beff6853cd7143c7db2a36036
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387372"
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="125c4-102">例外のキャッチ ブロックを追加する方法</span><span class="sxs-lookup"><span data-stu-id="125c4-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="125c4-103">**例外のキャッチ**ブロックが例外ハンドラーを表します。</span><span class="sxs-lookup"><span data-stu-id="125c4-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="125c4-104">**例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーで図形。</span><span class="sxs-lookup"><span data-stu-id="125c4-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="125c4-105">BizTalk server の多くとして割り当てることができます**例外のキャッチ**ブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="125c4-105">In BizTalk Server, you can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="125c4-106">さまざまな種類の例外を処理するために、例外ハンドラーを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="125c4-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="125c4-107">各例外ハンドラーでエラー メッセージまたはクラスから派生したオブジェクトのいずれかにする必要があります例外の種類を指定する`System.Exception`します。</span><span class="sxs-lookup"><span data-stu-id="125c4-107">On each exception handler, you specify an exception type, which must be either a fault message or an object derived from the class `System.Exception`.</span></span> <span data-ttu-id="125c4-108">例外ブロックが、一般的な例外ハンドラーとして扱われから派生していない例外をキャッチできる例外の種類を指定しない場合`System.Exception`します。</span><span class="sxs-lookup"><span data-stu-id="125c4-108">If you do not specify an exception type, the exception block is treated as a general exception handler, and can catch exceptions that do not derive from `System.Exception`.</span></span>  
  
 <span data-ttu-id="125c4-109">例外ハンドラーで指定された型と一致する例外がスローされます、その例外ハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="125c4-109">If an exception is thrown that matches the specified type in an exception handler, that exception handler is called.</span></span> <span data-ttu-id="125c4-110">その他の例外がスローされた場合は、既定の例外ハンドラーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="125c4-110">If some other exception is thrown, it is handled by the default exception handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="125c4-111">追加する、**例外のキャッチ**へのブロックを**スコープ**、図形、**トランザクションの種類**のプロパティ、**スコープ**図形はか長を None に設定する必要があります実行中です。</span><span class="sxs-lookup"><span data-stu-id="125c4-111">To add a **Catch Exception** block to a **Scope** shape, the **Transaction Type** property of the **Scope** shape must be set to None or Long Running.</span></span>  
  
## <a name="adding-and-populating-a-catch-exception-block"></a><span data-ttu-id="125c4-112">追加と例外のキャッチ ブロックの設定</span><span class="sxs-lookup"><span data-stu-id="125c4-112">Adding and Populating a Catch Exception Block</span></span>  
  
#### <a name="to-add-and-populate-a-catch-exception-block"></a><span data-ttu-id="125c4-113">追加して例外のキャッチ ブロックを設定するには</span><span class="sxs-lookup"><span data-stu-id="125c4-113">To add and populate a catch exception block</span></span>  
  
1.  <span data-ttu-id="125c4-114">右クリックし、**スコープ**を追加する図形を**例外のキャッチ**、ブロックし、をクリックし、**新しい例外ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="125c4-114">Right-click the **Scope** shape that you want to add a **Catch Exception** block to, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="125c4-115">A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加されます**スコープ**図形。</span><span class="sxs-lookup"><span data-stu-id="125c4-115">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="125c4-116">**プロパティ**ウィンドウで、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="125c4-116">In the **Properties** window, specify the properties.</span></span> <span data-ttu-id="125c4-117">最も重要なプロパティは、**例外オブジェクト型**キャッチするメッセージの種類です。</span><span class="sxs-lookup"><span data-stu-id="125c4-117">The most important property is the **Exception Object Type** because this is the type of message it will catch.</span></span>  
  
    |<span data-ttu-id="125c4-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="125c4-118">Property</span></span>|<span data-ttu-id="125c4-119">説明</span><span class="sxs-lookup"><span data-stu-id="125c4-119">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="125c4-120">例外オブジェクト名</span><span class="sxs-lookup"><span data-stu-id="125c4-120">Exception Object Name</span></span>|<span data-ttu-id="125c4-121">例外ハンドラーによってキャッチされる例外オブジェクトに名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="125c4-121">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="125c4-122">例外オブジェクト型</span><span class="sxs-lookup"><span data-stu-id="125c4-122">Exception Object Type</span></span>|<span data-ttu-id="125c4-123">オブジェクトの種類 (System.Exception から派生) を決定します。 この例外ハンドラーでキャッチします。</span><span class="sxs-lookup"><span data-stu-id="125c4-123">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
3.  <span data-ttu-id="125c4-124">**プロパティ**ウィンドウで、をクリックして、**例外オブジェクト型**一覧。</span><span class="sxs-lookup"><span data-stu-id="125c4-124">In the **Properties** window, click the **Exception Object Type** list.</span></span> <span data-ttu-id="125c4-125">この一覧には、アダプターによってスローされる一般的な例外が含まれています。</span><span class="sxs-lookup"><span data-stu-id="125c4-125">This list contains the general exception that is thrown by the adapter.</span></span>  
  
     <span data-ttu-id="125c4-126">名前は PS. など、バックエンド システムへのポートで設定したエラーとして表示されます。SQLExecute.Fault します。</span><span class="sxs-lookup"><span data-stu-id="125c4-126">The name appears as the fault you set in the port to the back-end system, for example, PS.SQLExecute.Fault.</span></span>  
  
4.  <span data-ttu-id="125c4-127">名前を追加、**例外オブジェクト名**、たとえば、テストします。</span><span class="sxs-lookup"><span data-stu-id="125c4-127">Add a name for the **Exception Object Name**, for example, Test.</span></span>  
  
     <span data-ttu-id="125c4-128">内で、**例外のキャッチ**ブロックで例外を処理するプロセスを作成する図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="125c4-128">Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span>  
  
    1.  <span data-ttu-id="125c4-129">下を右クリック、**例外のキャッチ**、 をポイント**図形の挿入**、選び**メッセージの構築**します。</span><span class="sxs-lookup"><span data-stu-id="125c4-129">Right-click below the **Catch Exception**, point to **Insert Shape**, and select **Construct Message**.</span></span>  
  
         <span data-ttu-id="125c4-130">![](../core/media/siebeladapter-20-exceptionhandling-constructmessage.gif "SiebelAdapter_20_ExceptionHandling_ConstructMessage")</span><span class="sxs-lookup"><span data-stu-id="125c4-130">![](../core/media/siebeladapter-20-exceptionhandling-constructmessage.gif "SiebelAdapter_20_ExceptionHandling_ConstructMessage")</span></span>  
  
    2.  <span data-ttu-id="125c4-131">中をダブルクリックして**MessageAssignment**をテキスト エディターを開き、メッセージの割り当てを入力します。</span><span class="sxs-lookup"><span data-stu-id="125c4-131">Double-click inside **MessageAssignment** to open the Text Editor and enter the Message assignment.</span></span>  
  
         <span data-ttu-id="125c4-132">設定した名前を入力、**例外オブジェクト名**から、**例外のキャッチ**、およびエラー用に作成した新しいメッセージ。</span><span class="sxs-lookup"><span data-stu-id="125c4-132">Enter the name that you set in the **Exception Object Name** from the **Catch Exception**, and the new message you created for the fault.</span></span>  
  
         <span data-ttu-id="125c4-133">たとえば、「 `Message_3 = Test`」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="125c4-133">For example, type `Message_3 = Test`.</span></span>  
  
         <span data-ttu-id="125c4-134">![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")</span><span class="sxs-lookup"><span data-stu-id="125c4-134">![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="125c4-135">参照</span><span class="sxs-lookup"><span data-stu-id="125c4-135">See Also</span></span>  
 <span data-ttu-id="125c4-136">[スコープ図形を追加する方法](../core/how-to-add-a-scope-shape1.md) </span><span class="sxs-lookup"><span data-stu-id="125c4-136">[How to Add a Scope Shape](../core/how-to-add-a-scope-shape1.md) </span></span>  
 <span data-ttu-id="125c4-137">[例外完了メッセージ](../core/completing-the-exception-message3.md) </span><span class="sxs-lookup"><span data-stu-id="125c4-137">[Completing the Exception Message](../core/completing-the-exception-message3.md) </span></span>  
 [<span data-ttu-id="125c4-138">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="125c4-138">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling2.md)