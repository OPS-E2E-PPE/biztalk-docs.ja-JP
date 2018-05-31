---
title: Catch 例外 block4 などを追加する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: b409f25fc32c609bb4c1a80c0582cdb1c363e965
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246826"
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="d306c-102">例外のキャッチ ブロックを追加する方法</span><span class="sxs-lookup"><span data-stu-id="d306c-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="d306c-103">**例外のキャッチ**ブロックが例外ハンドラーを表します。</span><span class="sxs-lookup"><span data-stu-id="d306c-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="d306c-104">**例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーでの図形です。</span><span class="sxs-lookup"><span data-stu-id="d306c-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="d306c-105">数だけ接続できます**例外のキャッチ**ブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d306c-105">You can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="d306c-106">例外ハンドラーを設定すると、各種の例外を処理することができます。</span><span class="sxs-lookup"><span data-stu-id="d306c-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="d306c-107">各例外ハンドラーでは、例外の種類を指定します。例外またはクラス System から派生したオブジェクトのいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d306c-107">On each exception handler, you specify an exception type, which must be either an exception or an object derived from the class System.</span></span> <span data-ttu-id="d306c-108">例外ハンドラで指定した型に一致する例外がスローされると、該当する例外ハンドラが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d306c-108">If an exception is thrown that matches the specified type in an exception handler, that exception handler is called.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d306c-109">追加する、**例外のキャッチ**へのブロック、**スコープ**図形のトランザクションの種類のプロパティ、**スコープ**に図形を設定する必要があります**None**または**実行時間が長い**です。</span><span class="sxs-lookup"><span data-stu-id="d306c-109">To add a **Catch Exception** block to a **Scope** shape, the Transaction Type property of the **Scope** shape must be set to **None** or **Long Running**.</span></span>  
  
|<span data-ttu-id="d306c-110">追加して、例外のキャッチ ブロックを設定します。</span><span class="sxs-lookup"><span data-stu-id="d306c-110">Adding and populating a Catch Exception block</span></span>|  
|---------------------------------------------------|  
|<span data-ttu-id="d306c-111">1.右クリックし、**スコープ**を追加する図形、**例外のキャッチ**、ブロックし、をクリックして**新しい例外ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="d306c-111">1.  Right-click the **Scope** shape that you want to add a **Catch Exception** block to, and click **New Exception Handler**.</span></span><br />     <span data-ttu-id="d306c-112">A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加**スコープ**図形です。</span><span class="sxs-lookup"><span data-stu-id="d306c-112">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span><br /><span data-ttu-id="d306c-113">2.**プロパティ**ウィンドウで、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="d306c-113">2.  In the **Properties** window, specify the properties.</span></span> <span data-ttu-id="d306c-114">最も重要なは、**例外オブジェクト型**です。 これは、キャッチするメッセージの種類。</span><span class="sxs-lookup"><span data-stu-id="d306c-114">The most important is the **Exception Object Type**; this is the type of message it will catch.</span></span><br />     <span data-ttu-id="d306c-115">**例外オブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="d306c-115">**Exception Object Name**</span></span><br />     <span data-ttu-id="d306c-116">-例外ハンドラーによってキャッチされた例外オブジェクトに名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d306c-116">- Assigns a name to the exception object caught by the exception handler.</span></span><br />     <span data-ttu-id="d306c-117">**例外オブジェクト型**</span><span class="sxs-lookup"><span data-stu-id="d306c-117">**Exception Object Type**</span></span><br />     <span data-ttu-id="d306c-118">-(System.Exception から派生) オブジェクトの種類を判別します。 この例外ハンドラーでキャッチします。</span><span class="sxs-lookup"><span data-stu-id="d306c-118">- Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span><br /><span data-ttu-id="d306c-119">3.**プロパティ**ウィンドウを開いた、**例外オブジェクト型** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="d306c-119">3.  In the **Properties** window, open the **Exception Object Type** list.</span></span> <span data-ttu-id="d306c-120">この一覧には、**一般例外**です。</span><span class="sxs-lookup"><span data-stu-id="d306c-120">This list contains the **General Exception**.</span></span><br /><span data-ttu-id="d306c-121">4.内部、**例外のキャッチ**をブロックする図形を追加して、例外を処理するためのプロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d306c-121">4.  Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span><br /><span data-ttu-id="d306c-122">5.下を右クリックし、**例外のキャッチ**、 をポイント**図形の挿入**を選択して**メッセージの構築**です。</span><span class="sxs-lookup"><span data-stu-id="d306c-122">5.  Right-click below the **Catch Exception**, point to **Insert Shape**, and select **Construct Message**.</span></span><br /><span data-ttu-id="d306c-123">6.内でダブルクリックして**MessageAssignment**をテキスト エディターをアクティブ化し、メッセージの割り当てを入力します。</span><span class="sxs-lookup"><span data-stu-id="d306c-123">6.  Double-click inside **MessageAssignment** to activate the Text Editor, and enter the Message assignment.</span></span><br />     <span data-ttu-id="d306c-124">たとえば、「Message_3 = Test」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d306c-124">For example, type in Message_3 = Test.</span></span><br />     ![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")|  
  
## <a name="see-also"></a><span data-ttu-id="d306c-125">参照</span><span class="sxs-lookup"><span data-stu-id="d306c-125">See Also</span></span>  
 <span data-ttu-id="d306c-126">[例外完了メッセージ](../core/completing-the-exception-message2.md) </span><span class="sxs-lookup"><span data-stu-id="d306c-126">[Completing the Exception Message](../core/completing-the-exception-message2.md) </span></span>  
 <span data-ttu-id="d306c-127">[スコープ図形を追加する方法](../core/how-to-add-a-scope-shape3.md) </span><span class="sxs-lookup"><span data-stu-id="d306c-127">[How to Add a Scope Shape](../core/how-to-add-a-scope-shape3.md) </span></span>  
 [<span data-ttu-id="d306c-128">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="d306c-128">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling1.md)