---
title: スコープ Shape3 を追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
ms.assetid: 8068ce97-4409-4c88-89e8-6505b56cefc5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8231dfed1ea84ba5c11e0352f789b92cc38d0f83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="ba42e-102">スコープ図形を追加する方法</span><span class="sxs-lookup"><span data-stu-id="ba42e-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="ba42e-103">スコープ図形を追加するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ba42e-103">Use the following procedure to add a Scope shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="ba42e-104">スコープ図形を追加するには</span><span class="sxs-lookup"><span data-stu-id="ba42e-104">To add a Scope Shape</span></span>  
  
1.  <span data-ttu-id="ba42e-105">下の矢印を右クリックし、**受信**ポートでは、順にポイント**図形の挿入**、し、**スコープ**です。</span><span class="sxs-lookup"><span data-stu-id="ba42e-105">Right-click the arrow below the **Receive** port, point to **Insert Shape**, and then select **Scope**.</span></span>  
  
     ![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")  
  
     <span data-ttu-id="ba42e-106">**スコープ**図形、エラーが発生する操作を設定します。</span><span class="sxs-lookup"><span data-stu-id="ba42e-106">In the **Scope** shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="ba42e-107">たとえば、SQLExecute オーケストレーションに送信ポート、受信ポート、さらに送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="ba42e-107">For example, add a send, a receive, and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="ba42e-108">この例では、SERVER にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="ba42e-108">In this example, you send a message to SERVER.</span></span> <span data-ttu-id="ba42e-109">SERVER は応答して、</span><span class="sxs-lookup"><span data-stu-id="ba42e-109">SERVER gives a response.</span></span> <span data-ttu-id="ba42e-110">オーケストレーションの残りの部分を実行し、outFile ポートに情報を返します。</span><span class="sxs-lookup"><span data-stu-id="ba42e-110">It runs the rest of the orchestration and returns information back to the outFile port.</span></span>  
  
2.  <span data-ttu-id="ba42e-111">**スコープ**図形は、設定、**トランザクション**に**None**です。</span><span class="sxs-lookup"><span data-stu-id="ba42e-111">In the **Scope** shape, set the **Transaction** to **None**.</span></span>  
  
3.  <span data-ttu-id="ba42e-112">内部を右クリックし、**スコープ**図形、および選択**新しい例外ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="ba42e-112">Right-click inside the **Scope** shape, and select **New Exception Handler**.</span></span>  
  
     ![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")  
  
     <span data-ttu-id="ba42e-113">これを作成、**例外のキャッチ**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="ba42e-113">This creates the **Catch Exception** block.</span></span> <span data-ttu-id="ba42e-114">内でキャッチこれは、バックエンド システムから例外が発生した場合、**例外のキャッチ**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="ba42e-114">If an exception occurs from the back-end system, it is caught inside the **Catch Exception** block.</span></span>  
  
4.  <span data-ttu-id="ba42e-115">**例外のキャッチ**ブロック、ロジックを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba42e-115">In the **Catch Exception** block, you must add the logic.</span></span>  
  
     <span data-ttu-id="ba42e-116">この場合、設定する必要がある最も重要なロジックは、受信するエラー メッセージの種類についてです。</span><span class="sxs-lookup"><span data-stu-id="ba42e-116">The most important logic that you must set is the type of error message that you expect to receive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba42e-117">参照</span><span class="sxs-lookup"><span data-stu-id="ba42e-117">See Also</span></span>  
 [<span data-ttu-id="ba42e-118">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="ba42e-118">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling1.md)