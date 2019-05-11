---
title: スコープ Shape2 を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
- adding, Scope shapes
ms.assetid: 9449210f-1f29-4b86-a14b-148caa06ac6b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be9f3aaab2843ad77a1103155239277e0ec72e4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343615"
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="2436c-102">スコープ図形を追加する方法</span><span class="sxs-lookup"><span data-stu-id="2436c-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="2436c-103">追加する、次の手順を使用して、**スコープ**図形。</span><span class="sxs-lookup"><span data-stu-id="2436c-103">Use the following procedure to add a **Scope** shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="2436c-104">スコープ図形を追加するには</span><span class="sxs-lookup"><span data-stu-id="2436c-104">To add a scope shape</span></span>  
  
1.  <span data-ttu-id="2436c-105">下の矢印を右クリックし、 **ReceiveFromIn**ポートをポイントして、**図形の挿入**、選択と**スコープ**します。</span><span class="sxs-lookup"><span data-stu-id="2436c-105">Right-click the arrow below the **ReceiveFromIn** port, point to **Insert Shape**, and select **Scope**.</span></span>  
  
     <span data-ttu-id="2436c-106">**スコープ**図形、エラーが発生する操作を設定します。</span><span class="sxs-lookup"><span data-stu-id="2436c-106">In the **Scope** shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="2436c-107">たとえば、SQLExecute オーケストレーション、送信、受信および送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="2436c-107">For example, add a send, a receive and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="2436c-108">この例では、サーバーにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="2436c-108">In this example, you send a message to SERVER.</span></span> <span data-ttu-id="2436c-109">サーバーは応答して、</span><span class="sxs-lookup"><span data-stu-id="2436c-109">SERVER gives a response.</span></span> <span data-ttu-id="2436c-110">これにより、オーケストレーションの残りの部分を実行し、OutFile ポートに情報を返します。</span><span class="sxs-lookup"><span data-stu-id="2436c-110">It runs the rest of the orchestration and returns information back to the OutFile port.</span></span>  
  
2.  <span data-ttu-id="2436c-111">**スコープ**図形は、設定、**トランザクションの種類**に**None**します。</span><span class="sxs-lookup"><span data-stu-id="2436c-111">In the **Scope** shape, set the **Transaction Type** to **None**.</span></span>  
  
3.  <span data-ttu-id="2436c-112">内側を右クリックし、**スコープ**図形し、選択**新しい例外ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="2436c-112">Right-click inside the **Scope** shape and select **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="2436c-113">これを作成、**例外のキャッチ**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="2436c-113">This creates the **Catch Exception** block.</span></span> <span data-ttu-id="2436c-114">内でキャッチされますが、バックエンド システムから例外が発生した場合、**例外のキャッチ**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="2436c-114">If an exception occurs from the back-end system, it is caught inside the **Catch Exception** block.</span></span>  
  
4.  <span data-ttu-id="2436c-115">**例外のキャッチ**ブロックのロジックを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2436c-115">In the **Catch Exception** block, you must add the logic.</span></span>  
  
     <span data-ttu-id="2436c-116">設定する必要がある最も重要なロジックは、受信するエラー メッセージの種類です。</span><span class="sxs-lookup"><span data-stu-id="2436c-116">The most important logic that you must set is the type of error message that you expect to receive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2436c-117">参照</span><span class="sxs-lookup"><span data-stu-id="2436c-117">See Also</span></span>  
 [<span data-ttu-id="2436c-118">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="2436c-118">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling3.md)