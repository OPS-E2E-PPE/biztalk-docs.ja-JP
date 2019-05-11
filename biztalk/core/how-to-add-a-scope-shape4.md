---
title: スコープ Shape4 を追加する方法 |Microsoft Docs
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
ms.assetid: 4ed56ada-a656-40b1-b34a-0c0803c01216
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce1e97c941de98c700b549dfe6307794ca38fb31
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343411"
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="ea2c0-102">スコープ図形を追加する方法</span><span class="sxs-lookup"><span data-stu-id="ea2c0-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="ea2c0-103">追加する次の手順に従って、**スコープ**図形。</span><span class="sxs-lookup"><span data-stu-id="ea2c0-103">Follow these steps to add a **Scope** shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="ea2c0-104">スコープ図形を追加するには</span><span class="sxs-lookup"><span data-stu-id="ea2c0-104">To add a scope shape</span></span>  
  
1.  <span data-ttu-id="ea2c0-105">下の矢印を右クリックし、 **ReceiveFromIn**ポートをポイントして、**図形の挿入**、 をクリックし、**スコープ**。</span><span class="sxs-lookup"><span data-stu-id="ea2c0-105">Right-click the arrow below the **ReceiveFromIn** port, point to **Insert Shape**, and then click **Scope**.</span></span>  
  
     <span data-ttu-id="ea2c0-106">スコープ図形では、エラーが発生する操作を設定します。</span><span class="sxs-lookup"><span data-stu-id="ea2c0-106">In the Scope shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="ea2c0-107">たとえば、SQLExecute オーケストレーション、送信、受信および送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="ea2c0-107">For example, add a send, a receive and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="ea2c0-108">この例では、サーバーにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="ea2c0-108">In this example, you send a message to SERVER.</span></span> <span data-ttu-id="ea2c0-109">サーバーは応答して、</span><span class="sxs-lookup"><span data-stu-id="ea2c0-109">SERVER gives a response.</span></span> <span data-ttu-id="ea2c0-110">これにより、オーケストレーションの残りの部分を実行し、OutFile ポートに情報を返します。</span><span class="sxs-lookup"><span data-stu-id="ea2c0-110">It runs the rest of the orchestration and returns information back to the OutFile port.</span></span>  
  
2.  <span data-ttu-id="ea2c0-111">スコープ図形に、設定、**トランザクション**に**None**します。</span><span class="sxs-lookup"><span data-stu-id="ea2c0-111">In the Scope shape, set the **Transaction** to **None**.</span></span>  
  
3.  <span data-ttu-id="ea2c0-112">スコープ図形の内部を右クリックし、選択**新しい例外ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="ea2c0-112">Right-click inside the Scope shape and select **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="ea2c0-113">これを作成、**例外のキャッチ**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="ea2c0-113">This creates the **Catch Exception** block.</span></span> <span data-ttu-id="ea2c0-114">バック エンドから例外が発生した、内でキャッチされます、**例外のキャッチ**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="ea2c0-114">If an exception occurs from the back-end, it is caught inside the **Catch Exception** block.</span></span>  
  
4.  <span data-ttu-id="ea2c0-115">**例外のキャッチ**ブロックのロジックを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea2c0-115">In the **Catch Exception** block, you must add the logic.</span></span>  
    <span data-ttu-id="ea2c0-116">設定する必要がある最も重要なロジックは、受信するエラー メッセージの種類です。</span><span class="sxs-lookup"><span data-stu-id="ea2c0-116">The most important logic that you must set is the type of error message that you expect to receive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea2c0-117">参照</span><span class="sxs-lookup"><span data-stu-id="ea2c0-117">See Also</span></span>  
 [<span data-ttu-id="ea2c0-118">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="ea2c0-118">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling4.md)