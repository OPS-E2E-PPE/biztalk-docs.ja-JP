---
title: スコープ図形の 1 を追加する方法 |Microsoft Docs
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
ms.openlocfilehash: faabba82196f7e595427f36c0d07d66769bafd18
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387320"
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="c8edd-102">スコープ図形を追加する方法</span><span class="sxs-lookup"><span data-stu-id="c8edd-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="c8edd-103">スコープ図形を追加するこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c8edd-103">Follow these steps to add a Scope shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="c8edd-104">スコープ図形を追加するには</span><span class="sxs-lookup"><span data-stu-id="c8edd-104">To add a Scope Shape</span></span>  
  
1.  <span data-ttu-id="c8edd-105">下の矢印を右クリックし、 **ReceiveFromIn**ポートをポイントして、**図形の挿入**、 をクリックし、**スコープ**。</span><span class="sxs-lookup"><span data-stu-id="c8edd-105">Right-click the arrow below the **ReceiveFromIn** port, point to **Insert Shape**, and then click **Scope**.</span></span>  
  
     <span data-ttu-id="c8edd-106">![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")</span><span class="sxs-lookup"><span data-stu-id="c8edd-106">![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")</span></span>  
  
     <span data-ttu-id="c8edd-107">スコープ図形では、エラーが発生する操作を設定します。</span><span class="sxs-lookup"><span data-stu-id="c8edd-107">In the Scope shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="c8edd-108">たとえば、SQLExecute オーケストレーション、送信ポート、受信と送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="c8edd-108">For example, add a send, a receive, and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="c8edd-109">この例では、DB2 にメッセージを送信しました。</span><span class="sxs-lookup"><span data-stu-id="c8edd-109">In this example, we are sending a message to DB2.</span></span> <span data-ttu-id="c8edd-110">DB2 は応答です。</span><span class="sxs-lookup"><span data-stu-id="c8edd-110">DB2 gives a response.</span></span> <span data-ttu-id="c8edd-111">これにより、オーケストレーションの残りの部分を実行し、OutFile ポートに情報を返します。</span><span class="sxs-lookup"><span data-stu-id="c8edd-111">It runs the rest of the orchestration and returns information back to the OutFile port.</span></span>  
  
2.  <span data-ttu-id="c8edd-112">スコープ図形に、設定、**トランザクション**に**None**します。</span><span class="sxs-lookup"><span data-stu-id="c8edd-112">In the Scope shape, set the **Transaction** to **None**.</span></span>  
  
3.  <span data-ttu-id="c8edd-113">スコープ図形内で右クリックして**新しい例外ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="c8edd-113">Right-click inside the Scope shape, and select **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="c8edd-114">![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")</span><span class="sxs-lookup"><span data-stu-id="c8edd-114">![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")</span></span>  
  
     <span data-ttu-id="c8edd-115">これは、例外のキャッチ ブロックを作成します。</span><span class="sxs-lookup"><span data-stu-id="c8edd-115">This creates the Catch Exception block.</span></span> <span data-ttu-id="c8edd-116">バック エンドから例外が発生した場合は、例外のキャッチ ブロック内でキャッチされます。</span><span class="sxs-lookup"><span data-stu-id="c8edd-116">If an exception occurs from the back-end, it is caught inside the Catch Exception block.</span></span>  
  
4.  <span data-ttu-id="c8edd-117">例外のキャッチ ブロックでは、ロジックを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8edd-117">In the Catch Exception block, you must add the logic.</span></span>  
  
     <span data-ttu-id="c8edd-118">最も重要なロジックを設定する必要がありますが、予期したエラー メッセージの種類です。</span><span class="sxs-lookup"><span data-stu-id="c8edd-118">The most important logic you must set is the type of error message you are expecting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8edd-119">参照</span><span class="sxs-lookup"><span data-stu-id="c8edd-119">See Also</span></span>  
 [<span data-ttu-id="c8edd-120">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="c8edd-120">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling2.md)