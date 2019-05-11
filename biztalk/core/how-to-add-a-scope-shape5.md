---
title: スコープ Shape5 を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adding, Scope shapes
- Scope shape, adding
ms.assetid: 1e16eda1-c4bd-4428-a477-78c453aeb1aa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35301e9e3cd66ab26d06208501c535b73305f5a6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343396"
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="85400-102">スコープ図形を追加する方法</span><span class="sxs-lookup"><span data-stu-id="85400-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="85400-103">追加する次の手順に従って、**スコープ**図形。</span><span class="sxs-lookup"><span data-stu-id="85400-103">Follow these steps to add a **Scope**shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="85400-104">スコープ図形を追加するには</span><span class="sxs-lookup"><span data-stu-id="85400-104">To add a Scope shape</span></span>  
  
1.  <span data-ttu-id="85400-105">下の矢印を右クリックし、 **ReceiveFromIn**ポートをポイントして、**図形の挿入**、 をクリックし、**スコープ**。</span><span class="sxs-lookup"><span data-stu-id="85400-105">Right-click the arrow below the **ReceiveFromIn** port, point to **Insert Shape**, and then click **Scope**.</span></span>  
  
     <span data-ttu-id="85400-106">**スコープ**図形、エラーが発生する操作を設定します。</span><span class="sxs-lookup"><span data-stu-id="85400-106">In the **Scope** shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="85400-107">たとえば、SQLExecute オーケストレーション、送信、受信および送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="85400-107">For example, add a send, a receive and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="85400-108">この例では、サーバーにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="85400-108">In this example, you send a message to SERVER.</span></span> <span data-ttu-id="85400-109">サーバーは応答して、</span><span class="sxs-lookup"><span data-stu-id="85400-109">SERVER gives a response.</span></span> <span data-ttu-id="85400-110">これにより、オーケストレーションの残りの部分を実行し、OutFile ポートに情報を返します。</span><span class="sxs-lookup"><span data-stu-id="85400-110">It runs the rest of the orchestration and returns information back to the OutFile port.</span></span>  
  
2.  <span data-ttu-id="85400-111">**スコープ**図形は、設定、**トランザクションの種類**に**None**します。</span><span class="sxs-lookup"><span data-stu-id="85400-111">In the **Scope** shape, set the **Transaction Type** to **None**.</span></span>  
  
3.  <span data-ttu-id="85400-112">内側を右クリックし、**スコープ**図形し、選択**新しい例外ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="85400-112">Right-click inside the **Scope** shape and select **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="85400-113">これを作成、`Catch Exception`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="85400-113">This creates the `Catch Exception`block.</span></span> <span data-ttu-id="85400-114">バック エンドから例外が発生した、内でキャッチされます、`Catch Exception`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="85400-114">If an exception occurs from the back-end, it is caught inside the `Catch Exception`block.</span></span>  
  
4.  <span data-ttu-id="85400-115">`Catch Exception`ブロックのロジックを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85400-115">In the `Catch Exception` block, you must add the logic.</span></span>  
  
     <span data-ttu-id="85400-116">設定する必要がある最も重要なロジックは、受信するエラー メッセージの種類です。</span><span class="sxs-lookup"><span data-stu-id="85400-116">The most important logic that you must set is the type of error message that you expect to receive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85400-117">参照</span><span class="sxs-lookup"><span data-stu-id="85400-117">See Also</span></span>  
 [<span data-ttu-id="85400-118">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="85400-118">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling5.md)