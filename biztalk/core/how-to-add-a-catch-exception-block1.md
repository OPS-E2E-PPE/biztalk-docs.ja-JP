---
title: Catch 例外 Block1 を追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions, adding Catch Exception block
- Catch Exception blocks, adding
- exception handling, Catch Exception blocks
ms.assetid: 8e4b264b-b3b0-4d83-81df-a14dc2ddeea2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7922a1527e0f6359427be992c4cc9963f8c7d93e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247026"
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="71d2b-102">例外のキャッチ ブロックを追加する方法</span><span class="sxs-lookup"><span data-stu-id="71d2b-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="71d2b-103">**例外のキャッチ**ブロックが例外ハンドラーを表します。</span><span class="sxs-lookup"><span data-stu-id="71d2b-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="71d2b-104">**例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーでの図形です。</span><span class="sxs-lookup"><span data-stu-id="71d2b-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="71d2b-105">数だけ接続できます**例外のキャッチ**ブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="71d2b-105">You can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="71d2b-106">例外ハンドラーを設定すると、各種の例外を処理することができます。</span><span class="sxs-lookup"><span data-stu-id="71d2b-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="71d2b-107">各例外ハンドラーでは、例外の種類を指定します。例外またはクラス `System` から派生したオブジェクトのいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71d2b-107">On each exception handler, you specify an exception type, which must be either an exception or an object derived from the class `System`.</span></span> <span data-ttu-id="71d2b-108">例外ハンドラーで指定した種類に一致する例外がスローされると、その例外ハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="71d2b-108">If an exception is thrown that matches the specified type in an exception handler, that exception handler will be called.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71d2b-109">追加する、**例外のキャッチ**へのブロック、**スコープ**図形のトランザクションの種類のプロパティ、**スコープ**に図形を設定する必要があります**None**または**実行時間が長い**です。</span><span class="sxs-lookup"><span data-stu-id="71d2b-109">To add a **Catch Exception** block to a **Scope** shape, the Transaction Type property of the **Scope** shape must be set to **None** or **Long Running**.</span></span>  
  
### <a name="to-add-and-populate-a-catch-exception-block"></a><span data-ttu-id="71d2b-110">追加して、例外のキャッチ ブロックを設定するには</span><span class="sxs-lookup"><span data-stu-id="71d2b-110">To add and populate a Catch Exception block</span></span>  
  
1.  <span data-ttu-id="71d2b-111">右クリックし、**スコープ**図形を追加する、**例外のキャッチ**をクリックして、ブロック**新しい例外ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="71d2b-111">Right-click the **Scope** shape to which you want to add a **Catch Exception** block, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="71d2b-112">A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加**スコープ**図形です。</span><span class="sxs-lookup"><span data-stu-id="71d2b-112">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="71d2b-113">**プロパティ**ウィンドウで、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="71d2b-113">In the **Properties** window, specify the properties.</span></span>  
  
     <span data-ttu-id="71d2b-114">最も重要なプロパティは、キャッチするメッセージの種類を表す "例外オブジェクト名" です。</span><span class="sxs-lookup"><span data-stu-id="71d2b-114">The most important property is the Exception Object Type; this is the type of message it will catch.</span></span>  
  
    |<span data-ttu-id="71d2b-115">プロパティ</span><span class="sxs-lookup"><span data-stu-id="71d2b-115">Property</span></span>|<span data-ttu-id="71d2b-116">Description</span><span class="sxs-lookup"><span data-stu-id="71d2b-116">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="71d2b-117">例外オブジェクト名</span><span class="sxs-lookup"><span data-stu-id="71d2b-117">Exception Object Name</span></span>|<span data-ttu-id="71d2b-118">例外ハンドラーでキャッチする例外オブジェクトに名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="71d2b-118">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="71d2b-119">例外オブジェクト型</span><span class="sxs-lookup"><span data-stu-id="71d2b-119">Exception Object Type</span></span>|<span data-ttu-id="71d2b-120">この例外ハンドラーでキャッチするオブジェクト型 (System.Exception から派生) を決定します。</span><span class="sxs-lookup"><span data-stu-id="71d2b-120">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
3.  <span data-ttu-id="71d2b-121">**プロパティ**] ウィンドウで、**例外オブジェクト型**一覧で、[、**一般例外**です。</span><span class="sxs-lookup"><span data-stu-id="71d2b-121">In the **Properties** window, in the **Exception Object Type** list, select the **General Exception**.</span></span>  
  
4.  <span data-ttu-id="71d2b-122">内部、**例外のキャッチ**をブロックする図形を追加して、例外を処理するためのプロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="71d2b-122">Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span>  
  
5.  <span data-ttu-id="71d2b-123">下を右クリックし、**例外のキャッチ**をブロックし、**図形の挿入**、し、**メッセージの構築**です。</span><span class="sxs-lookup"><span data-stu-id="71d2b-123">Right-click below the **Catch Exception** block, point to **Insert Shape**, and then select **Construct Message**.</span></span>  
  
6.  <span data-ttu-id="71d2b-124">内でダブルクリックして**MessageAssignment**をテキスト エディターをアクティブ化し、メッセージの割り当てを入力します。</span><span class="sxs-lookup"><span data-stu-id="71d2b-124">Double-click inside **MessageAssignment** to activate the Text Editor and enter the Message assignment.</span></span>  
  
     <span data-ttu-id="71d2b-125">たとえば、「 `Message_3 = Test`」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="71d2b-125">For example, type `Message_3 = Test`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71d2b-126">参照</span><span class="sxs-lookup"><span data-stu-id="71d2b-126">See Also</span></span>  
 <span data-ttu-id="71d2b-127">[例外完了メッセージ](../core/completing-the-exception-message5.md) </span><span class="sxs-lookup"><span data-stu-id="71d2b-127">[Completing the Exception Message](../core/completing-the-exception-message5.md) </span></span>  
 <span data-ttu-id="71d2b-128">[スコープ図形を追加する方法](../core/how-to-add-a-scope-shape2.md) </span><span class="sxs-lookup"><span data-stu-id="71d2b-128">[How to Add a Scope Shape](../core/how-to-add-a-scope-shape2.md) </span></span>  
 [<span data-ttu-id="71d2b-129">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="71d2b-129">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling3.md)