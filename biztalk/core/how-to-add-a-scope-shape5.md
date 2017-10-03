---
title: "スコープ Shape5 を追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adding, Scope shapes
- Scope shape, adding
ms.assetid: 1e16eda1-c4bd-4428-a477-78c453aeb1aa
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7bbe3f5fbb267fee618ac7f0b91c35ad33e1758
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="a5b8f-102">スコープ図形を追加する方法</span><span class="sxs-lookup"><span data-stu-id="a5b8f-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="a5b8f-103">次の手順を追加するに従って、**スコープ**図形です。</span><span class="sxs-lookup"><span data-stu-id="a5b8f-103">Follow these steps to add a **Scope**shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="a5b8f-104">スコープ図形を追加するには</span><span class="sxs-lookup"><span data-stu-id="a5b8f-104">To add a Scope shape</span></span>  
  
1.  <span data-ttu-id="a5b8f-105">下の矢印を右クリックし、 **ReceiveFromIn**ポートでは、順にポイント**図形の挿入**、クリックして**スコープ**です。</span><span class="sxs-lookup"><span data-stu-id="a5b8f-105">Right-click the arrow below the **ReceiveFromIn** port, point to **Insert Shape**, and then click **Scope**.</span></span>  
  
     <span data-ttu-id="a5b8f-106">**スコープ**図形、エラーが発生する操作を設定します。</span><span class="sxs-lookup"><span data-stu-id="a5b8f-106">In the **Scope** shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="a5b8f-107">たとえば、SQLExecute オーケストレーションで、送信、受信および送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="a5b8f-107">For example, add a send, a receive and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="a5b8f-108">この例では、SERVER にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="a5b8f-108">In this example, you send a message to SERVER.</span></span> <span data-ttu-id="a5b8f-109">SERVER は応答して、</span><span class="sxs-lookup"><span data-stu-id="a5b8f-109">SERVER gives a response.</span></span> <span data-ttu-id="a5b8f-110">オーケストレーションの残りの部分を実行し、OutFile ポートに情報を返します。</span><span class="sxs-lookup"><span data-stu-id="a5b8f-110">It runs the rest of the orchestration and returns information back to the OutFile port.</span></span>  
  
2.  <span data-ttu-id="a5b8f-111">**スコープ**図形は、設定、**トランザクション タイプ**に**なし**です。</span><span class="sxs-lookup"><span data-stu-id="a5b8f-111">In the **Scope** shape, set the **Transaction Type** to **None**.</span></span>  
  
3.  <span data-ttu-id="a5b8f-112">内部を右クリックし、**スコープ**の整形し、選択**新しい例外ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="a5b8f-112">Right-click inside the **Scope** shape and select **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="a5b8f-113">これを作成、`Catch Exception`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="a5b8f-113">This creates the `Catch Exception`block.</span></span> <span data-ttu-id="a5b8f-114">内でキャッチこれは、例外がバックエンドから発生する場合、`Catch Exception`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="a5b8f-114">If an exception occurs from the back-end, it is caught inside the `Catch Exception`block.</span></span>  
  
4.  <span data-ttu-id="a5b8f-115">`Catch Exception` ブロックには、ロジックを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5b8f-115">In the `Catch Exception` block, you must add the logic.</span></span>  
  
     <span data-ttu-id="a5b8f-116">この場合、設定する必要がある最も重要なロジックは、受信するエラー メッセージの種類についてです。</span><span class="sxs-lookup"><span data-stu-id="a5b8f-116">The most important logic that you must set is the type of error message that you expect to receive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5b8f-117">参照</span><span class="sxs-lookup"><span data-stu-id="a5b8f-117">See Also</span></span>  
 [<span data-ttu-id="a5b8f-118">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="a5b8f-118">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling5.md)