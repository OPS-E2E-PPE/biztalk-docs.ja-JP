---
title: "Catch 例外 Block2 を追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Catch Exception blocks
- exceptions, Catch Exception blocks
ms.assetid: 7c8b6024-e8dc-4417-83f9-bf4032644b91
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e48ce1e6f0646acdf63ed33582f382f1baed797
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="8039b-102">例外のキャッチ ブロックを追加する方法</span><span class="sxs-lookup"><span data-stu-id="8039b-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="8039b-103">**例外のキャッチ**ブロックが例外ハンドラーを表します。</span><span class="sxs-lookup"><span data-stu-id="8039b-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="8039b-104">**例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーでの図形です。</span><span class="sxs-lookup"><span data-stu-id="8039b-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="8039b-105">数だけ接続できます**例外のキャッチ**ブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8039b-105">You can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="8039b-106">例外ハンドラーを設定すると、各種の例外を処理することができます。</span><span class="sxs-lookup"><span data-stu-id="8039b-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="8039b-107">各例外ハンドラーでは、例外の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="8039b-107">On each exception handler, you specify an exception type.</span></span> <span data-ttu-id="8039b-108">これには、例外またはクラス `System` から派生したオブジェクトのいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8039b-108">This must be either an exception or an object derived from the class `System`.</span></span> <span data-ttu-id="8039b-109">例外ハンドラーで指定した種類に一致する例外がスローされると、その例外ハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8039b-109">If an exception is thrown that matches the specified type in an exception handler, that exception handler will be called.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8039b-110">スコープ図形には、例外のキャッチ ブロックを追加するには、スコープ図形のトランザクションの種類プロパティに設定する必要があります**None**または**長時間**です。</span><span class="sxs-lookup"><span data-stu-id="8039b-110">To add a Catch Exception block to a Scope shape, the Transaction Type property of the Scope shape must be set to **None** or **Long Running**.</span></span>  
  
### <a name="to-add-and-populate-a-catch-exception-block"></a><span data-ttu-id="8039b-111">追加して、例外のキャッチ ブロックを設定するには</span><span class="sxs-lookup"><span data-stu-id="8039b-111">To add and populate a Catch Exception block</span></span>  
  
1.  <span data-ttu-id="8039b-112">右クリックし、**スコープ**図形を追加する、**例外のキャッチ**をクリックして、ブロック**新しい例外ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="8039b-112">Right-click the **Scope** shape to which you want to add a **Catch Exception** block, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="8039b-113">A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加**スコープ**図形です。</span><span class="sxs-lookup"><span data-stu-id="8039b-113">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="8039b-114">**プロパティ**ウィンドウで、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="8039b-114">In the **Properties** window, specify the properties.</span></span>  
  
     <span data-ttu-id="8039b-115">最も重要なプロパティは、**例外オブジェクト型**です。 これは、キャッチするメッセージの種類。</span><span class="sxs-lookup"><span data-stu-id="8039b-115">The most important property is the **Exception Object Type**; this is the type of message it will catch.</span></span>  
  
3.  <span data-ttu-id="8039b-116">**プロパティ**windows で、**例外オブジェクト型**一覧で、**一般例外**です。</span><span class="sxs-lookup"><span data-stu-id="8039b-116">In the **Properties** windows, in the **Exception Object Type** list, select  **General Exception**.</span></span>  
  
    |<span data-ttu-id="8039b-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8039b-117">Property</span></span>|<span data-ttu-id="8039b-118">Description</span><span class="sxs-lookup"><span data-stu-id="8039b-118">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="8039b-119">**例外オブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="8039b-119">**Exception Object Name**</span></span>|<span data-ttu-id="8039b-120">例外ハンドラーでキャッチする例外オブジェクトに名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8039b-120">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="8039b-121">**例外オブジェクト型**</span><span class="sxs-lookup"><span data-stu-id="8039b-121">**Exception Object Type**</span></span>|<span data-ttu-id="8039b-122">この例外ハンドラーでキャッチするオブジェクト型 (System.Exception から派生) を決定します。</span><span class="sxs-lookup"><span data-stu-id="8039b-122">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
4.  <span data-ttu-id="8039b-123">例外のキャッチ ブロックの内側で、図形を追加して、例外を処理するためのプロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8039b-123">Inside the Catch Exception block, add shapes to create the process for handling the exception.</span></span>  
  
    1.  <span data-ttu-id="8039b-124">下を右クリックし、 **CatchException**を指す**図形の挿入**、し、**メッセージの構築**です。</span><span class="sxs-lookup"><span data-stu-id="8039b-124">Right-click below the **CatchException** and point to **Insert Shape**, and then select **Construct Message**.</span></span>  
  
    2.  <span data-ttu-id="8039b-125">内でダブルクリックして**MessageAssignment**するテキスト エディターを開き、メッセージの割り当てを入力します。</span><span class="sxs-lookup"><span data-stu-id="8039b-125">Double-click inside **MessageAssignment** to open the Text Editor and enter the Message assignment.</span></span>  
  
         <span data-ttu-id="8039b-126">たとえば、「 `Message_3 = Test`」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8039b-126">For example, type `Message_3 = Test`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8039b-127">参照</span><span class="sxs-lookup"><span data-stu-id="8039b-127">See Also</span></span>  
 <span data-ttu-id="8039b-128">[例外完了メッセージ](../core/completing-the-exception-message4.md) </span><span class="sxs-lookup"><span data-stu-id="8039b-128">[Completing the Exception Message](../core/completing-the-exception-message4.md) </span></span>  
 <span data-ttu-id="8039b-129">[スコープ図形を追加する方法](../core/how-to-add-a-scope-shape4.md) </span><span class="sxs-lookup"><span data-stu-id="8039b-129">[How to Add a Scope Shape](../core/how-to-add-a-scope-shape4.md) </span></span>  
 [<span data-ttu-id="8039b-130">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="8039b-130">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling4.md)