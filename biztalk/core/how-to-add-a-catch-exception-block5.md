---
title: Catch の例外 Block5 を追加する方法 |Microsoft Docs
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
ms.assetid: 4875060c-976c-40e7-830a-ffd1a47ba68a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60e2674823ff92b1ffe59a304b8cbe766c8e7e0d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343943"
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="9178e-102">例外のキャッチ ブロックを追加する方法</span><span class="sxs-lookup"><span data-stu-id="9178e-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="9178e-103">追加する、**例外のキャッチ**へのブロック、**スコープ**図形、**トランザクションの種類**のプロパティ、**スコープ**に図形を設定する必要があります**None**または**実行時間が長い**します。</span><span class="sxs-lookup"><span data-stu-id="9178e-103">To add a **Catch Exception** block to a **Scope** shape, the **Transaction Type** property of the **Scope** shape must be set to **None** or **Long Running**.</span></span>  
  
### <a name="to-add-a-catch-exception-block"></a><span data-ttu-id="9178e-104">例外のキャッチ ブロックを追加するには</span><span class="sxs-lookup"><span data-stu-id="9178e-104">To add a catch exception block</span></span>  
  
1.  <span data-ttu-id="9178e-105">右クリックし、**スコープ**図形をクリックして**新しい例外ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="9178e-105">Right-click the **Scope** shape, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="9178e-106">A**例外のキャッチ**ブロックが関連付けられている直後のオーケストレーションに追加されます**スコープ**図形。</span><span class="sxs-lookup"><span data-stu-id="9178e-106">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="9178e-107">**プロパティ**ウィンドウで、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="9178e-107">In the **Properties** window, specify the properties.</span></span>  
  
     <span data-ttu-id="9178e-108">最も重要なプロパティは、**例外オブジェクト型**; これは、キャッチするメッセージの種類。</span><span class="sxs-lookup"><span data-stu-id="9178e-108">The most important property is the **Exception Object Type**; this is the type of message it will catch.</span></span>  
  
    |<span data-ttu-id="9178e-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9178e-109">Property</span></span>|<span data-ttu-id="9178e-110">説明</span><span class="sxs-lookup"><span data-stu-id="9178e-110">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="9178e-111">**例外オブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="9178e-111">**Exception Object Name**</span></span>|<span data-ttu-id="9178e-112">例外ハンドラーによってキャッチされる例外オブジェクトに名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9178e-112">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="9178e-113">**例外オブジェクト型**</span><span class="sxs-lookup"><span data-stu-id="9178e-113">**Exception Object Type**</span></span>|<span data-ttu-id="9178e-114">オブジェクトの種類 (System.Exception から派生) を決定します。 この例外ハンドラーでキャッチします。</span><span class="sxs-lookup"><span data-stu-id="9178e-114">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
3.  <span data-ttu-id="9178e-115">**プロパティ**ウィンドウで、**例外オブジェクト型**一覧で、**一般例外**します。</span><span class="sxs-lookup"><span data-stu-id="9178e-115">In the **Properties** window, in the **Exception Object Type** list, select **General Exception**.</span></span>  
  
4.  <span data-ttu-id="9178e-116">内で、**例外のキャッチ**ブロックで例外を処理するプロセスを作成する図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="9178e-116">Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span>  
  
    1.  <span data-ttu-id="9178e-117">下を右クリック、 **CatchException** ] をポイント**図形の挿入**、し、[**メッセージの構築**します。</span><span class="sxs-lookup"><span data-stu-id="9178e-117">Right-click below the **CatchException** and point to **Insert Shape**, and then select **Construct Message**.</span></span>  
  
    2.  <span data-ttu-id="9178e-118">中をダブルクリックして**MessageAssignment**をテキスト エディターを開き、メッセージの割り当てを入力します。</span><span class="sxs-lookup"><span data-stu-id="9178e-118">Double-click inside **MessageAssignment** to open the Text Editor and enter the Message assignment.</span></span>  
  
         <span data-ttu-id="9178e-119">たとえば、「 `Message_3 = Test`」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9178e-119">For example, type `Message_3 = Test`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9178e-120">参照</span><span class="sxs-lookup"><span data-stu-id="9178e-120">See Also</span></span>  
 <span data-ttu-id="9178e-121">[例外完了メッセージ](../core/completing-the-exception-message1.md) </span><span class="sxs-lookup"><span data-stu-id="9178e-121">[Completing the Exception Message](../core/completing-the-exception-message1.md) </span></span>  
 <span data-ttu-id="9178e-122">[スコープ図形を追加する方法](../core/how-to-add-a-scope-shape5.md) </span><span class="sxs-lookup"><span data-stu-id="9178e-122">[How to Add a Scope Shape](../core/how-to-add-a-scope-shape5.md) </span></span>  
 [<span data-ttu-id="9178e-123">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="9178e-123">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling5.md)