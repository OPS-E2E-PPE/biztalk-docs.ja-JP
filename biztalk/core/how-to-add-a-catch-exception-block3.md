---
title: Catch 例外 Block3 を追加する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 1040a27a5e1273d2ad80a722deb421878de36c12
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247058"
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="103e3-102">例外のキャッチ ブロックを追加する方法</span><span class="sxs-lookup"><span data-stu-id="103e3-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="103e3-103">**例外のキャッチ**ブロックが例外ハンドラーを表します。</span><span class="sxs-lookup"><span data-stu-id="103e3-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="103e3-104">**例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーでの図形です。</span><span class="sxs-lookup"><span data-stu-id="103e3-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="103e3-105">数だけ接続できます**例外のキャッチ**ブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="103e3-105">You can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="103e3-106">例外ハンドラーを設定すると、各種の例外を処理することができます。</span><span class="sxs-lookup"><span data-stu-id="103e3-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="103e3-107">各例外ハンドラーでエラー メッセージまたはクラスから派生したオブジェクトのいずれかにする必要があります例外の種類を指定する**System.Exception**です。</span><span class="sxs-lookup"><span data-stu-id="103e3-107">On each exception handler, you specify an exception type, which must be either a fault message or an object derived from the class **System.Exception**.</span></span> <span data-ttu-id="103e3-108">例外ブロックが、一般的な例外ハンドラーとして扱われますおよびからは派生しません例外をキャッチすることができる場合は、例外の種類を指定しないと、 **System.Exception**です。</span><span class="sxs-lookup"><span data-stu-id="103e3-108">If you do not specify an exception type, the exception block will be treated as a general exception handler, and can catch exceptions that do not derive from **System.Exception**.</span></span>  
  
 <span data-ttu-id="103e3-109">例外ハンドラーで指定した種類に一致する例外がスローされると、その例外ハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="103e3-109">If an exception is thrown that matches the specified type in an exception handler, that exception handler will be called.</span></span> <span data-ttu-id="103e3-110">その他の型の例外がスローされた場合、その例外は既定の例外ハンドラーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="103e3-110">If some other exception is thrown, it will be handled by the default exception handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="103e3-111">追加する、**例外のキャッチ**へのブロック、**スコープ**図形、**トランザクション タイプ**のプロパティ、**スコープ**に図形を設定する必要があります**None**または**実行時間が長い**です。</span><span class="sxs-lookup"><span data-stu-id="103e3-111">To add a **Catch Exception** block to a **Scope** shape, the **Transaction Type** property of the **Scope** shape must be set to **None** or **Long Running**.</span></span>  
  
### <a name="to-add-a-catch-exception-block"></a><span data-ttu-id="103e3-112">例外のキャッチ ブロックを追加するには</span><span class="sxs-lookup"><span data-stu-id="103e3-112">To add a Catch Exception block</span></span>  
  
1.  <span data-ttu-id="103e3-113">右クリックし、**スコープ**図形を追加する、**例外のキャッチ**をクリックして、ブロック**新しい例外ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="103e3-113">Right-click the **Scope** shape to which you want to add a **Catch Exception** block, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="103e3-114">A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加**スコープ**図形です。</span><span class="sxs-lookup"><span data-stu-id="103e3-114">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="103e3-115">[プロパティ] ウィンドウで、次のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="103e3-115">In the Properties window, specify the following properties:</span></span>  
  
    |<span data-ttu-id="103e3-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="103e3-116">Property</span></span>|<span data-ttu-id="103e3-117">Description</span><span class="sxs-lookup"><span data-stu-id="103e3-117">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="103e3-118">例外オブジェクト名</span><span class="sxs-lookup"><span data-stu-id="103e3-118">Exception Object Name</span></span>|<span data-ttu-id="103e3-119">例外ハンドラーでキャッチする例外オブジェクトに名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="103e3-119">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="103e3-120">例外オブジェクト型</span><span class="sxs-lookup"><span data-stu-id="103e3-120">Exception Object Type</span></span>|<span data-ttu-id="103e3-121">この例外ハンドラーでキャッチするオブジェクト型 (System.Exception から派生) を決定します。</span><span class="sxs-lookup"><span data-stu-id="103e3-121">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
3.  <span data-ttu-id="103e3-122">内部、**例外のキャッチ**をブロックする図形を追加して、例外を処理するためのプロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="103e3-122">Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="103e3-123">汎用的な例外を指定する場合、**例外**オブジェクトの種類を**例外のキャッチ**ブロックから派生していないものも含め、すべての例外をインターセプトする**System.Exception**.</span><span class="sxs-lookup"><span data-stu-id="103e3-123">If you specify General Exception as the **Exception** object type, the **Catch Exception** block will intercept any exception, including those that are not derived from **System.Exception**.</span></span> <span data-ttu-id="103e3-124">この場合、例外オブジェクトにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="103e3-124">In such a case, you will not have access to an exception object.</span></span> <span data-ttu-id="103e3-125">使用する場合、このブロック内で、**例外のスロー**図形に、一般的な例外の種類がする効率的に再スロー例外をキャッチしました。</span><span class="sxs-lookup"><span data-stu-id="103e3-125">Within this block, if you use a **Throw Exception** shape with the General Exception type, you will be effectively rethrowing the caught exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="103e3-126">参照</span><span class="sxs-lookup"><span data-stu-id="103e3-126">See Also</span></span>  
 [<span data-ttu-id="103e3-127">例外</span><span class="sxs-lookup"><span data-stu-id="103e3-127">Exceptions</span></span>](../core/exceptions.md)