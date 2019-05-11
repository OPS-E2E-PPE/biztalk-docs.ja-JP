---
title: Catch 例外 block4 などを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Catch Exception blocks, adding
- exception handling, Catch Exception blocks
ms.assetid: 632fa089-a1af-4126-b32b-68d4d8942387
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cf27fd031f5887eed499eb1b10418fa911a127c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387365"
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="d839e-102">例外のキャッチ ブロックを追加する方法</span><span class="sxs-lookup"><span data-stu-id="d839e-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="d839e-103">**例外のキャッチ**ブロックが例外ハンドラーを表します。</span><span class="sxs-lookup"><span data-stu-id="d839e-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="d839e-104">**例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーで図形。</span><span class="sxs-lookup"><span data-stu-id="d839e-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="d839e-105">多くとしてアタッチすることができます**例外のキャッチ**ブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d839e-105">You can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="d839e-106">さまざまな種類の例外を処理するために、例外ハンドラーを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="d839e-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="d839e-107">各例外ハンドラーでは、例外またはクラス System から派生したオブジェクトのいずれかにする必要があります例外の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="d839e-107">On each exception handler, you specify an exception type, which must be either an exception or an object derived from the class System.</span></span> <span data-ttu-id="d839e-108">例外ハンドラーで指定された型と一致する例外がスローされます、その例外ハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d839e-108">If an exception is thrown that matches the specified type in an exception handler, that exception handler is called.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d839e-109">追加する、**例外のキャッチ**へのブロックを**スコープ**図形のトランザクションの種類のプロパティ、**スコープ**に図形を設定する必要があります**None**または**実行時間が長い**します。</span><span class="sxs-lookup"><span data-stu-id="d839e-109">To add a **Catch Exception** block to a **Scope** shape, the Transaction Type property of the **Scope** shape must be set to **None** or **Long Running**.</span></span>  
  
|<span data-ttu-id="d839e-110">追加と例外のキャッチ ブロックの設定</span><span class="sxs-lookup"><span data-stu-id="d839e-110">Adding and populating a Catch Exception block</span></span>|  
|---------------------------------------------------|  
|<span data-ttu-id="d839e-111">1.右クリックし、**スコープ**を追加する図形を**例外のキャッチ**をブロックし、をクリックして**新しい例外ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="d839e-111">1.  Right-click the **Scope** shape that you want to add a **Catch Exception** block to, and click **New Exception Handler**.</span></span><br />     <span data-ttu-id="d839e-112">A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加されます**スコープ**図形。</span><span class="sxs-lookup"><span data-stu-id="d839e-112">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span><br /><span data-ttu-id="d839e-113">2.**プロパティ**ウィンドウで、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="d839e-113">2.  In the **Properties** window, specify the properties.</span></span> <span data-ttu-id="d839e-114">最も重要なは、**例外オブジェクト型**; これは、キャッチするメッセージの種類。</span><span class="sxs-lookup"><span data-stu-id="d839e-114">The most important is the **Exception Object Type**; this is the type of message it will catch.</span></span><br />     <span data-ttu-id="d839e-115">**例外オブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="d839e-115">**Exception Object Name**</span></span><br />     <span data-ttu-id="d839e-116">-例外ハンドラーによってキャッチされる例外オブジェクトに名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d839e-116">- Assigns a name to the exception object caught by the exception handler.</span></span><br />     <span data-ttu-id="d839e-117">**例外オブジェクト型**</span><span class="sxs-lookup"><span data-stu-id="d839e-117">**Exception Object Type**</span></span><br />     <span data-ttu-id="d839e-118">-(System.Exception から派生) オブジェクトの種類を決定します。 この例外ハンドラーでキャッチします。</span><span class="sxs-lookup"><span data-stu-id="d839e-118">- Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span><br /><span data-ttu-id="d839e-119">3.**プロパティ**ウィンドウを開いて、**例外オブジェクト型**一覧。</span><span class="sxs-lookup"><span data-stu-id="d839e-119">3.  In the **Properties** window, open the **Exception Object Type** list.</span></span> <span data-ttu-id="d839e-120">このリストには、**一般例外**します。</span><span class="sxs-lookup"><span data-stu-id="d839e-120">This list contains the **General Exception**.</span></span><br /><span data-ttu-id="d839e-121">4.内で、**例外のキャッチ**ブロックで例外を処理するプロセスを作成する図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="d839e-121">4.  Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span><br /><span data-ttu-id="d839e-122">5.下を右クリック、**例外のキャッチ**、 をポイント**図形の挿入**、選び**メッセージの構築**します。</span><span class="sxs-lookup"><span data-stu-id="d839e-122">5.  Right-click below the **Catch Exception**, point to **Insert Shape**, and select **Construct Message**.</span></span><br /><span data-ttu-id="d839e-123">6.中をダブルクリックして**MessageAssignment**をテキスト エディターをアクティブ化して、メッセージの割り当てを入力します。</span><span class="sxs-lookup"><span data-stu-id="d839e-123">6.  Double-click inside **MessageAssignment** to activate the Text Editor, and enter the Message assignment.</span></span><br />     <span data-ttu-id="d839e-124">たとえば、メッセージ _ 3 で入力テストを = です。</span><span class="sxs-lookup"><span data-stu-id="d839e-124">For example, type in Message_3 = Test.</span></span><br />     <span data-ttu-id="d839e-125">![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")</span><span class="sxs-lookup"><span data-stu-id="d839e-125">![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d839e-126">参照</span><span class="sxs-lookup"><span data-stu-id="d839e-126">See Also</span></span>  
 <span data-ttu-id="d839e-127">[例外完了メッセージ](../core/completing-the-exception-message2.md) </span><span class="sxs-lookup"><span data-stu-id="d839e-127">[Completing the Exception Message](../core/completing-the-exception-message2.md) </span></span>  
 <span data-ttu-id="d839e-128">[スコープ図形を追加する方法](../core/how-to-add-a-scope-shape3.md) </span><span class="sxs-lookup"><span data-stu-id="d839e-128">[How to Add a Scope Shape](../core/how-to-add-a-scope-shape3.md) </span></span>  
 [<span data-ttu-id="d839e-129">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="d839e-129">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling1.md)