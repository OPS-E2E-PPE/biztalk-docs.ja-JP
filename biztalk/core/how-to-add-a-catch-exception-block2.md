---
title: Catch の例外 Block2 を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Catch Exception blocks
- exceptions, Catch Exception blocks
ms.assetid: 7c8b6024-e8dc-4417-83f9-bf4032644b91
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e16fb42f9b8814ab816f64f6cf2b3a8b482fbb58
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387416"
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="4ea9a-102">例外のキャッチ ブロックを追加する方法</span><span class="sxs-lookup"><span data-stu-id="4ea9a-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="4ea9a-103">**例外のキャッチ**ブロックが例外ハンドラーを表します。</span><span class="sxs-lookup"><span data-stu-id="4ea9a-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="4ea9a-104">**例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーで図形。</span><span class="sxs-lookup"><span data-stu-id="4ea9a-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="4ea9a-105">多くとしてアタッチすることができます**例外のキャッチ**ブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ea9a-105">You can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="4ea9a-106">さまざまな種類の例外を処理するために、例外ハンドラーを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="4ea9a-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="4ea9a-107">各例外ハンドラーでは、例外の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ea9a-107">On each exception handler, you specify an exception type.</span></span> <span data-ttu-id="4ea9a-108">例外またはクラスから派生したオブジェクトのいずれかにあるこの必要があります`System`します。</span><span class="sxs-lookup"><span data-stu-id="4ea9a-108">This must be either an exception or an object derived from the class `System`.</span></span> <span data-ttu-id="4ea9a-109">例外がスローされた例外ハンドラーで指定された型と一致する場合は、その例外ハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4ea9a-109">If an exception is thrown that matches the specified type in an exception handler, that exception handler will be called.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ea9a-110">例外のキャッチ ブロックをスコープ図形を追加するにスコープ図形のトランザクションの種類のプロパティを設定**None**または**長時間**します。</span><span class="sxs-lookup"><span data-stu-id="4ea9a-110">To add a Catch Exception block to a Scope shape, the Transaction Type property of the Scope shape must be set to **None** or **Long Running**.</span></span>  
  
### <a name="to-add-and-populate-a-catch-exception-block"></a><span data-ttu-id="4ea9a-111">追加して、例外のキャッチ ブロックを設定するには</span><span class="sxs-lookup"><span data-stu-id="4ea9a-111">To add and populate a Catch Exception block</span></span>  
  
1.  <span data-ttu-id="4ea9a-112">右クリックし、**スコープ**図形を追加する、**例外のキャッチ**ブロックし、クリックして**新しい例外ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="4ea9a-112">Right-click the **Scope** shape to which you want to add a **Catch Exception** block, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="4ea9a-113">A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加されます**スコープ**図形。</span><span class="sxs-lookup"><span data-stu-id="4ea9a-113">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="4ea9a-114">**プロパティ**ウィンドウで、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="4ea9a-114">In the **Properties** window, specify the properties.</span></span>  
  
     <span data-ttu-id="4ea9a-115">最も重要なプロパティは、**例外オブジェクト型**; これは、キャッチするメッセージの種類。</span><span class="sxs-lookup"><span data-stu-id="4ea9a-115">The most important property is the **Exception Object Type**; this is the type of message it will catch.</span></span>  
  
3.  <span data-ttu-id="4ea9a-116">**プロパティ**windows で、**例外オブジェクト型**一覧で、**一般例外**します。</span><span class="sxs-lookup"><span data-stu-id="4ea9a-116">In the **Properties** windows, in the **Exception Object Type** list, select  **General Exception**.</span></span>  
  
    |<span data-ttu-id="4ea9a-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4ea9a-117">Property</span></span>|<span data-ttu-id="4ea9a-118">説明</span><span class="sxs-lookup"><span data-stu-id="4ea9a-118">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="4ea9a-119">**例外オブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="4ea9a-119">**Exception Object Name**</span></span>|<span data-ttu-id="4ea9a-120">例外ハンドラーによってキャッチされる例外オブジェクトに名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4ea9a-120">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="4ea9a-121">**例外オブジェクト型**</span><span class="sxs-lookup"><span data-stu-id="4ea9a-121">**Exception Object Type**</span></span>|<span data-ttu-id="4ea9a-122">オブジェクトの種類 (System.Exception から派生) を決定します。 この例外ハンドラーでキャッチします。</span><span class="sxs-lookup"><span data-stu-id="4ea9a-122">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
4.  <span data-ttu-id="4ea9a-123">例外のキャッチ ブロック内では、例外を処理するプロセスを作成する図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="4ea9a-123">Inside the Catch Exception block, add shapes to create the process for handling the exception.</span></span>  
  
    1.  <span data-ttu-id="4ea9a-124">下を右クリック、 **CatchException** ] をポイント**図形の挿入**、し、[**メッセージの構築**します。</span><span class="sxs-lookup"><span data-stu-id="4ea9a-124">Right-click below the **CatchException** and point to **Insert Shape**, and then select **Construct Message**.</span></span>  
  
    2.  <span data-ttu-id="4ea9a-125">中をダブルクリックして**MessageAssignment**をテキスト エディターを開き、メッセージの割り当てを入力します。</span><span class="sxs-lookup"><span data-stu-id="4ea9a-125">Double-click inside **MessageAssignment** to open the Text Editor and enter the Message assignment.</span></span>  
  
         <span data-ttu-id="4ea9a-126">たとえば、「 `Message_3 = Test`」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4ea9a-126">For example, type `Message_3 = Test`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ea9a-127">参照</span><span class="sxs-lookup"><span data-stu-id="4ea9a-127">See Also</span></span>  
 <span data-ttu-id="4ea9a-128">[例外完了メッセージ](../core/completing-the-exception-message4.md) </span><span class="sxs-lookup"><span data-stu-id="4ea9a-128">[Completing the Exception Message](../core/completing-the-exception-message4.md) </span></span>  
 <span data-ttu-id="4ea9a-129">[スコープ図形を追加する方法](../core/how-to-add-a-scope-shape4.md) </span><span class="sxs-lookup"><span data-stu-id="4ea9a-129">[How to Add a Scope Shape](../core/how-to-add-a-scope-shape4.md) </span></span>  
 [<span data-ttu-id="4ea9a-130">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="4ea9a-130">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling4.md)