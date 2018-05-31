---
title: スコープ Shape1 を追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
- Scope shapes, Catch Exception blocks
- Catch Exception blocks, Scope shapes
- adding, Scope shapes
ms.assetid: dfe039d1-4c4a-4e21-ae03-7ca534aafec3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 094f744f7d4d6d1c405ea50d222beb8c0a67920e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247186"
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="8b78b-102">スコープ図形を追加する方法</span><span class="sxs-lookup"><span data-stu-id="8b78b-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="8b78b-103">以下の手順に従ってスコープ図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="8b78b-103">Follow these steps to add a Scope shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="8b78b-104">スコープ図形を追加するには</span><span class="sxs-lookup"><span data-stu-id="8b78b-104">To add a Scope Shape</span></span>  
  
1.  <span data-ttu-id="8b78b-105">下の矢印を右クリックし、 **ReceiveFromIn**ポートでは、順にポイント**図形の挿入**、クリックして**スコープ**です。</span><span class="sxs-lookup"><span data-stu-id="8b78b-105">Right-click the arrow below the **ReceiveFromIn** port, point to **Insert Shape**, and then click **Scope**.</span></span>  
  
     ![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")  
  
     <span data-ttu-id="8b78b-106">スコープ図形に、エラーが発生するような操作を設定します。</span><span class="sxs-lookup"><span data-stu-id="8b78b-106">In the Scope shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="8b78b-107">たとえば、SQLExecute オーケストレーションに送信ポート、受信ポート、さらに送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="8b78b-107">For example, add a send, a receive, and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="8b78b-108">この例では、DB2 にメッセージを送信しています。</span><span class="sxs-lookup"><span data-stu-id="8b78b-108">In this example, we are sending a message to DB2.</span></span> <span data-ttu-id="8b78b-109">DB2 は応答して、</span><span class="sxs-lookup"><span data-stu-id="8b78b-109">DB2 gives a response.</span></span> <span data-ttu-id="8b78b-110">オーケストレーションの残りの部分を実行し、OutFile ポートに情報を返します。</span><span class="sxs-lookup"><span data-stu-id="8b78b-110">It runs the rest of the orchestration and returns information back to the OutFile port.</span></span>  
  
2.  <span data-ttu-id="8b78b-111">スコープ図形で、設定、**トランザクション**に**None**です。</span><span class="sxs-lookup"><span data-stu-id="8b78b-111">In the Scope shape, set the **Transaction** to **None**.</span></span>  
  
3.  <span data-ttu-id="8b78b-112">スコープ図形の内側を右クリックし、選択**新しい例外ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="8b78b-112">Right-click inside the Scope shape, and select **New Exception Handler**.</span></span>  
  
     ![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")  
  
     <span data-ttu-id="8b78b-113">これにより、例外のキャッチ ブロックが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8b78b-113">This creates the Catch Exception block.</span></span> <span data-ttu-id="8b78b-114">例外がバックエンドから発生する場合、例外のキャッチ ブロック内でキャッチされます。</span><span class="sxs-lookup"><span data-stu-id="8b78b-114">If an exception occurs from the back-end, it is caught inside the Catch Exception block.</span></span>  
  
4.  <span data-ttu-id="8b78b-115">例外のキャッチ ブロックには、ロジックを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b78b-115">In the Catch Exception block, you must add the logic.</span></span>  
  
     <span data-ttu-id="8b78b-116">この場合、設定することが必要となる最も重要なロジックは、想定する種類のエラー メッセージに関するものになります。</span><span class="sxs-lookup"><span data-stu-id="8b78b-116">The most important logic you must set is the type of error message you are expecting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b78b-117">参照</span><span class="sxs-lookup"><span data-stu-id="8b78b-117">See Also</span></span>  
 [<span data-ttu-id="8b78b-118">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="8b78b-118">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling2.md)