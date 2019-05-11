---
title: Catch の例外 Block3 を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer], creating
- Catch Exception block [Orchestration Designer], exception handler
- Catch Exception block [Orchestration Designer], about Catch Exception blocks
- Orchestration Designer, errors
ms.assetid: 63ca4a60-b657-452a-86fd-78968ccf2933
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35746e0bc8e9bbadb8deffb5287943a95fd77e77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343951"
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="b52a2-102">例外のキャッチ ブロックを追加する方法</span><span class="sxs-lookup"><span data-stu-id="b52a2-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="b52a2-103">**例外のキャッチ**ブロックが例外ハンドラーを表します。</span><span class="sxs-lookup"><span data-stu-id="b52a2-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="b52a2-104">**例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーで図形。</span><span class="sxs-lookup"><span data-stu-id="b52a2-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="b52a2-105">多くとしてアタッチすることができます**例外のキャッチ**ブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b52a2-105">You can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="b52a2-106">さまざまな種類の例外を処理するために、例外ハンドラーを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="b52a2-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="b52a2-107">各例外ハンドラーでエラー メッセージまたはクラスから派生したオブジェクトのいずれかにする必要があります例外の種類を指定する**System.Exception**します。</span><span class="sxs-lookup"><span data-stu-id="b52a2-107">On each exception handler, you specify an exception type, which must be either a fault message or an object derived from the class **System.Exception**.</span></span> <span data-ttu-id="b52a2-108">例外ブロックは、一般的な例外ハンドラーとして扱われますから派生していない例外をキャッチできる例外の種類を指定しない場合**System.Exception**します。</span><span class="sxs-lookup"><span data-stu-id="b52a2-108">If you do not specify an exception type, the exception block will be treated as a general exception handler, and can catch exceptions that do not derive from **System.Exception**.</span></span>  
  
 <span data-ttu-id="b52a2-109">例外がスローされた例外ハンドラーで指定された型と一致する場合は、その例外ハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b52a2-109">If an exception is thrown that matches the specified type in an exception handler, that exception handler will be called.</span></span> <span data-ttu-id="b52a2-110">その他の例外がスローされた場合は、既定の例外ハンドラーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="b52a2-110">If some other exception is thrown, it will be handled by the default exception handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b52a2-111">追加する、**例外のキャッチ**へのブロック、**スコープ**図形、**トランザクションの種類**のプロパティ、**スコープ**に図形を設定する必要があります**None**または**実行時間が長い**します。</span><span class="sxs-lookup"><span data-stu-id="b52a2-111">To add a **Catch Exception** block to a **Scope** shape, the **Transaction Type** property of the **Scope** shape must be set to **None** or **Long Running**.</span></span>  
  
### <a name="to-add-a-catch-exception-block"></a><span data-ttu-id="b52a2-112">例外のキャッチ ブロックを追加するには</span><span class="sxs-lookup"><span data-stu-id="b52a2-112">To add a Catch Exception block</span></span>  
  
1.  <span data-ttu-id="b52a2-113">右クリックし、**スコープ**図形を追加する、**例外のキャッチ**ブロックし、クリックして**新しい例外ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="b52a2-113">Right-click the **Scope** shape to which you want to add a **Catch Exception** block, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="b52a2-114">A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加されます**スコープ**図形。</span><span class="sxs-lookup"><span data-stu-id="b52a2-114">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="b52a2-115">[プロパティ] ウィンドウでは、次のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="b52a2-115">In the Properties window, specify the following properties:</span></span>  
  
    |<span data-ttu-id="b52a2-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b52a2-116">Property</span></span>|<span data-ttu-id="b52a2-117">説明</span><span class="sxs-lookup"><span data-stu-id="b52a2-117">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="b52a2-118">例外オブジェクト名</span><span class="sxs-lookup"><span data-stu-id="b52a2-118">Exception Object Name</span></span>|<span data-ttu-id="b52a2-119">例外ハンドラーによってキャッチされる例外オブジェクトに名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b52a2-119">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="b52a2-120">例外オブジェクト型</span><span class="sxs-lookup"><span data-stu-id="b52a2-120">Exception Object Type</span></span>|<span data-ttu-id="b52a2-121">オブジェクトの種類 (System.Exception から派生) を決定します。 この例外ハンドラーでキャッチします。</span><span class="sxs-lookup"><span data-stu-id="b52a2-121">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
3.  <span data-ttu-id="b52a2-122">内で、**例外のキャッチ**ブロックで例外を処理するプロセスを作成する図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="b52a2-122">Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b52a2-123">汎用的な例外を指定する場合、**例外**オブジェクトの種類を**例外のキャッチ**ブロックから派生していないものも含め、すべての例外をインターセプトする**System.Exception**.</span><span class="sxs-lookup"><span data-stu-id="b52a2-123">If you specify General Exception as the **Exception** object type, the **Catch Exception** block will intercept any exception, including those that are not derived from **System.Exception**.</span></span> <span data-ttu-id="b52a2-124">このような場合は、例外オブジェクトへのアクセスを必要するはありません。</span><span class="sxs-lookup"><span data-stu-id="b52a2-124">In such a case, you will not have access to an exception object.</span></span> <span data-ttu-id="b52a2-125">使用する場合、このブロック内で、**例外のスロー**図形に、一般的な例外の種類が効率的に再スロー例外をキャッチしました。</span><span class="sxs-lookup"><span data-stu-id="b52a2-125">Within this block, if you use a **Throw Exception** shape with the General Exception type, you will be effectively rethrowing the caught exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b52a2-126">参照</span><span class="sxs-lookup"><span data-stu-id="b52a2-126">See Also</span></span>  
 [<span data-ttu-id="b52a2-127">例外</span><span class="sxs-lookup"><span data-stu-id="b52a2-127">Exceptions</span></span>](../core/exceptions.md)