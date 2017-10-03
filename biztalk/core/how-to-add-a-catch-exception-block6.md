---
title: "Catch 例外 Block6 を追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exception handling, Catch Exception block
- Catch Exception blocks
- exceptions, Catch Exception block
ms.assetid: 404312dd-773b-44fe-8b65-7de3d0af2f79
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4be60ddbe45ef4b4f293d7959dc774254e7cd3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="5cbac-102">例外のキャッチ ブロックを追加する方法</span><span class="sxs-lookup"><span data-stu-id="5cbac-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="5cbac-103">**例外のキャッチ**ブロックが例外ハンドラーを表します。</span><span class="sxs-lookup"><span data-stu-id="5cbac-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="5cbac-104">**例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーでの図形です。</span><span class="sxs-lookup"><span data-stu-id="5cbac-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="5cbac-105">BizTalk Server では、数だけ接続できます**例外のキャッチ**ブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cbac-105">In BizTalk Server, you can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="5cbac-106">例外ハンドラーを設定すると、各種の例外を処理することができます。</span><span class="sxs-lookup"><span data-stu-id="5cbac-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="5cbac-107">各例外ハンドラでは、例外の種類を指定します。エラー メッセージまたはクラス `System.Exception` から派生したオブジェクトのいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cbac-107">On each exception handler, you specify an exception type, which must be either a fault message or an object derived from the class `System.Exception`.</span></span> <span data-ttu-id="5cbac-108">例外の種類を指定しなかった場合、その例外ブロックは一般的な例外ハンドラとして扱われ、`System.Exception` からの派生ではない例外をキャッチする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5cbac-108">If you do not specify an exception type, the exception block is treated as a general exception handler, and can catch exceptions that do not derive from `System.Exception`.</span></span>  
  
 <span data-ttu-id="5cbac-109">例外ハンドラで指定した型に一致する例外がスローされると、該当する例外ハンドラが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5cbac-109">If an exception is thrown that matches the specified type in an exception handler, that exception handler is called.</span></span> <span data-ttu-id="5cbac-110">その他の型の例外がスローされた場合、その例外は既定の例外ハンドラによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="5cbac-110">If some other exception is thrown, it is handled by the default exception handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5cbac-111">追加する、**例外のキャッチ**へのブロック、**スコープ**図形、**トランザクションの種類**のプロパティ、**スコープ**か長を None に図形を設定する必要があります実行中です。</span><span class="sxs-lookup"><span data-stu-id="5cbac-111">To add a **Catch Exception** block to a **Scope** shape, the **Transaction Type** property of the **Scope** shape must be set to None or Long Running.</span></span>  
  
## <a name="adding-and-populating-a-catch-exception-block"></a><span data-ttu-id="5cbac-112">例外のキャッチ ブロックの追加と設定</span><span class="sxs-lookup"><span data-stu-id="5cbac-112">Adding and Populating a Catch Exception Block</span></span>  
  
#### <a name="to-add-and-populate-a-catch-exception-block"></a><span data-ttu-id="5cbac-113">例外のキャッチ ブロックを追加して設定するには</span><span class="sxs-lookup"><span data-stu-id="5cbac-113">To add and populate a catch exception block</span></span>  
  
1.  <span data-ttu-id="5cbac-114">右クリックし、**スコープ**を追加する図形、**例外のキャッチ**、ブロックし、をクリックして**新しい例外ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="5cbac-114">Right-click the **Scope** shape that you want to add a **Catch Exception** block to, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="5cbac-115">A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加**スコープ**図形です。</span><span class="sxs-lookup"><span data-stu-id="5cbac-115">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="5cbac-116">**プロパティ**ウィンドウで、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="5cbac-116">In the **Properties** window, specify the properties.</span></span> <span data-ttu-id="5cbac-117">最も重要なプロパティは、**例外オブジェクト型**キャッチするメッセージの種類は、このためです。</span><span class="sxs-lookup"><span data-stu-id="5cbac-117">The most important property is the **Exception Object Type** because this is the type of message it will catch.</span></span>  
  
    |<span data-ttu-id="5cbac-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5cbac-118">Property</span></span>|<span data-ttu-id="5cbac-119">Description</span><span class="sxs-lookup"><span data-stu-id="5cbac-119">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="5cbac-120">例外オブジェクト名</span><span class="sxs-lookup"><span data-stu-id="5cbac-120">Exception Object Name</span></span>|<span data-ttu-id="5cbac-121">例外ハンドラーでキャッチする例外オブジェクトに名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5cbac-121">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="5cbac-122">例外オブジェクト型</span><span class="sxs-lookup"><span data-stu-id="5cbac-122">Exception Object Type</span></span>|<span data-ttu-id="5cbac-123">この例外ハンドラーでキャッチするオブジェクト型 (System.Exception から派生) を決定します。</span><span class="sxs-lookup"><span data-stu-id="5cbac-123">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
3.  <span data-ttu-id="5cbac-124">**プロパティ**ウィンドウで、をクリックして、**例外オブジェクト型** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="5cbac-124">In the **Properties** window, click the **Exception Object Type** list.</span></span> <span data-ttu-id="5cbac-125">この一覧には、アダプタによってスローされる一般的な例外が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5cbac-125">This list contains the general exception that is thrown by the adapter.</span></span>  
  
     <span data-ttu-id="5cbac-126">名前は、バックエンド システムへのポートで設定したエラーとして表示されます (たとえば PS.SQLExecute.Fault)。</span><span class="sxs-lookup"><span data-stu-id="5cbac-126">The name appears as the fault you set in the port to the back-end system, for example, PS.SQLExecute.Fault.</span></span>  
  
4.  <span data-ttu-id="5cbac-127">名前を追加、**例外オブジェクト名**、たとえば、テストします。</span><span class="sxs-lookup"><span data-stu-id="5cbac-127">Add a name for the **Exception Object Name**, for example, Test.</span></span>  
  
     <span data-ttu-id="5cbac-128">内部、**例外のキャッチ**をブロックする図形を追加して、例外を処理するためのプロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5cbac-128">Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span>  
  
    1.  <span data-ttu-id="5cbac-129">下を右クリックし、**例外のキャッチ**、 をポイント**図形の挿入**を選択して**メッセージの構築**です。</span><span class="sxs-lookup"><span data-stu-id="5cbac-129">Right-click below the **Catch Exception**, point to **Insert Shape**, and select **Construct Message**.</span></span>  
  
         ![](../core/media/siebeladapter-20-exceptionhandling-constructmessage.gif "SiebelAdapter_20_ExceptionHandling_ConstructMessage")  
  
    2.  <span data-ttu-id="5cbac-130">内でダブルクリックして**MessageAssignment**するテキスト エディターを開き、メッセージの割り当てを入力します。</span><span class="sxs-lookup"><span data-stu-id="5cbac-130">Double-click inside **MessageAssignment** to open the Text Editor and enter the Message assignment.</span></span>  
  
         <span data-ttu-id="5cbac-131">設定した名前を入力、**例外オブジェクト名**から、**例外のキャッチ**、およびエラー用に作成した新しいメッセージ。</span><span class="sxs-lookup"><span data-stu-id="5cbac-131">Enter the name that you set in the **Exception Object Name** from the **Catch Exception**, and the new message you created for the fault.</span></span>  
  
         <span data-ttu-id="5cbac-132">たとえば、「 `Message_3 = Test`」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5cbac-132">For example, type `Message_3 = Test`.</span></span>  
  
         ![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")  
  
## <a name="see-also"></a><span data-ttu-id="5cbac-133">参照</span><span class="sxs-lookup"><span data-stu-id="5cbac-133">See Also</span></span>  
 <span data-ttu-id="5cbac-134">[スコープ図形を追加する方法](../core/how-to-add-a-scope-shape1.md) </span><span class="sxs-lookup"><span data-stu-id="5cbac-134">[How to Add a Scope Shape](../core/how-to-add-a-scope-shape1.md) </span></span>  
 <span data-ttu-id="5cbac-135">[例外完了メッセージ](../core/completing-the-exception-message3.md) </span><span class="sxs-lookup"><span data-stu-id="5cbac-135">[Completing the Exception Message](../core/completing-the-exception-message3.md) </span></span>  
 [<span data-ttu-id="5cbac-136">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="5cbac-136">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling2.md)