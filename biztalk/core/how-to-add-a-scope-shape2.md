---
title: "スコープ Shape2 を追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
- adding, Scope shapes
ms.assetid: 9449210f-1f29-4b86-a14b-148caa06ac6b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef67618c553702ae32cd0a88f6d2f77eb1ff053
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="8f708-102">スコープ図形を追加する方法</span><span class="sxs-lookup"><span data-stu-id="8f708-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="8f708-103">追加する、次の手順を使用して、**スコープ**図形です。</span><span class="sxs-lookup"><span data-stu-id="8f708-103">Use the following procedure to add a **Scope** shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="8f708-104">スコープ図形を追加するには</span><span class="sxs-lookup"><span data-stu-id="8f708-104">To add a scope shape</span></span>  
  
1.  <span data-ttu-id="8f708-105">下の矢印を右クリックし、 **ReceiveFromIn**ポートでは、順にポイント**図形の挿入**を選択して**スコープ**です。</span><span class="sxs-lookup"><span data-stu-id="8f708-105">Right-click the arrow below the **ReceiveFromIn** port, point to **Insert Shape**, and select **Scope**.</span></span>  
  
     <span data-ttu-id="8f708-106">**スコープ**図形、エラーが発生する操作を設定します。</span><span class="sxs-lookup"><span data-stu-id="8f708-106">In the **Scope** shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="8f708-107">たとえば、SQLExecute オーケストレーションで、送信、受信および送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="8f708-107">For example, add a send, a receive and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="8f708-108">この例では、SERVER にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="8f708-108">In this example, you send a message to SERVER.</span></span> <span data-ttu-id="8f708-109">SERVER は応答して、</span><span class="sxs-lookup"><span data-stu-id="8f708-109">SERVER gives a response.</span></span> <span data-ttu-id="8f708-110">オーケストレーションの残りの部分を実行し、OutFile ポートに情報を返します。</span><span class="sxs-lookup"><span data-stu-id="8f708-110">It runs the rest of the orchestration and returns information back to the OutFile port.</span></span>  
  
2.  <span data-ttu-id="8f708-111">**スコープ**図形は、設定、**トランザクション タイプ**に**なし**です。</span><span class="sxs-lookup"><span data-stu-id="8f708-111">In the **Scope** shape, set the **Transaction Type** to **None**.</span></span>  
  
3.  <span data-ttu-id="8f708-112">内部を右クリックし、**スコープ**の整形し、選択**新しい例外ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="8f708-112">Right-click inside the **Scope** shape and select **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="8f708-113">これを作成、**例外のキャッチ**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="8f708-113">This creates the **Catch Exception** block.</span></span> <span data-ttu-id="8f708-114">内でキャッチこれは、バックエンド システムから例外が発生した場合、**例外のキャッチ**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="8f708-114">If an exception occurs from the back-end system, it is caught inside the **Catch Exception** block.</span></span>  
  
4.  <span data-ttu-id="8f708-115">**例外のキャッチ**ブロック、ロジックを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f708-115">In the **Catch Exception** block, you must add the logic.</span></span>  
  
     <span data-ttu-id="8f708-116">この場合、設定する必要がある最も重要なロジックは、受信するエラー メッセージの種類についてです。</span><span class="sxs-lookup"><span data-stu-id="8f708-116">The most important logic that you must set is the type of error message that you expect to receive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f708-117">参照</span><span class="sxs-lookup"><span data-stu-id="8f708-117">See Also</span></span>  
 [<span data-ttu-id="8f708-118">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="8f708-118">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling3.md)