---
title: スコープ Shape3 を追加する方法 |Microsoft Docs
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
ms.openlocfilehash: 85b022dc0335ccd3b247c5c2fcad0553fad2ede4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387339"
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="b86c8-102">スコープ図形を追加する方法</span><span class="sxs-lookup"><span data-stu-id="b86c8-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="b86c8-103">スコープ図形を追加するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="b86c8-103">Use the following procedure to add a Scope shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="b86c8-104">スコープ図形を追加するには</span><span class="sxs-lookup"><span data-stu-id="b86c8-104">To add a Scope Shape</span></span>  
  
1.  <span data-ttu-id="b86c8-105">下の矢印を右クリックし、**受信**ポートをポイントして、**図形の挿入**、し、**スコープ**します。</span><span class="sxs-lookup"><span data-stu-id="b86c8-105">Right-click the arrow below the **Receive** port, point to **Insert Shape**, and then select **Scope**.</span></span>  
  
     <span data-ttu-id="b86c8-106">![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")</span><span class="sxs-lookup"><span data-stu-id="b86c8-106">![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")</span></span>  
  
     <span data-ttu-id="b86c8-107">**スコープ**図形、エラーが発生する操作を設定します。</span><span class="sxs-lookup"><span data-stu-id="b86c8-107">In the **Scope** shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="b86c8-108">たとえば、SQLExecute オーケストレーション、送信ポート、受信と送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="b86c8-108">For example, add a send, a receive, and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="b86c8-109">この例では、サーバーにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="b86c8-109">In this example, you send a message to SERVER.</span></span> <span data-ttu-id="b86c8-110">サーバーは応答して、</span><span class="sxs-lookup"><span data-stu-id="b86c8-110">SERVER gives a response.</span></span> <span data-ttu-id="b86c8-111">これにより、オーケストレーションの残りの部分を実行し、outFile ポートに情報を返します。</span><span class="sxs-lookup"><span data-stu-id="b86c8-111">It runs the rest of the orchestration and returns information back to the outFile port.</span></span>  
  
2.  <span data-ttu-id="b86c8-112">**スコープ**図形は、設定、**トランザクション**に**None**します。</span><span class="sxs-lookup"><span data-stu-id="b86c8-112">In the **Scope** shape, set the **Transaction** to **None**.</span></span>  
  
3.  <span data-ttu-id="b86c8-113">内側を右クリックし、**スコープ**図形、および選択**新しい例外ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="b86c8-113">Right-click inside the **Scope** shape, and select **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="b86c8-114">![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")</span><span class="sxs-lookup"><span data-stu-id="b86c8-114">![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")</span></span>  
  
     <span data-ttu-id="b86c8-115">これを作成、**例外のキャッチ**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="b86c8-115">This creates the **Catch Exception** block.</span></span> <span data-ttu-id="b86c8-116">内でキャッチされますが、バックエンド システムから例外が発生した場合、**例外のキャッチ**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="b86c8-116">If an exception occurs from the back-end system, it is caught inside the **Catch Exception** block.</span></span>  
  
4.  <span data-ttu-id="b86c8-117">**例外のキャッチ**ブロックのロジックを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b86c8-117">In the **Catch Exception** block, you must add the logic.</span></span>  
  
     <span data-ttu-id="b86c8-118">設定する必要がある最も重要なロジックは、受信するエラー メッセージの種類です。</span><span class="sxs-lookup"><span data-stu-id="b86c8-118">The most important logic that you must set is the type of error message that you expect to receive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b86c8-119">参照</span><span class="sxs-lookup"><span data-stu-id="b86c8-119">See Also</span></span>  
 [<span data-ttu-id="b86c8-120">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="b86c8-120">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling1.md)