---
title: オーケストレーションで式の使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1947cd39-6ef2-4b2d-afeb-a0132b19db97
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f8c528254dc5acc853e7c1f3fb4fe412f6e3eff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247379"
---
# <a name="using-expressions-in-orchestrations"></a><span data-ttu-id="d7f01-102">オーケストレーションで式の使用</span><span class="sxs-lookup"><span data-stu-id="d7f01-102">Using Expressions in Orchestrations</span></span>
<span data-ttu-id="d7f01-103">BizTalk 式エディターを使用すると、操作およびメッセージとオーケストレーション変数の値をテストするのにロジックを追加するのに xlang/s 式を入力します。</span><span class="sxs-lookup"><span data-stu-id="d7f01-103">You can use BizTalk Expression Editor to enter XLANG/s expressions to add logic to manipulate and test the values of your orchestration variables and messages.</span></span> <span data-ttu-id="d7f01-104">ただし、使用可能であれば、オーケストレーション図面自体に表示される可能性のある高度なオーケストレーション ロジックを実行することはお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="d7f01-104">However, it is not a good practice to use it to perform high-level orchestration logic, which preferably would be visible in the orchestration drawing itself.</span></span> <span data-ttu-id="d7f01-105">ビジネス プロセスの透過性と再構成の簡単なは、単純なモジュール形式の式を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d7f01-105">For business process transparency and easy of reconfiguration, we recommend that you use simple and modular expressions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d7f01-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d7f01-106">In This Section</span></span>  
 [<span data-ttu-id="d7f01-107">式の要件と制限事項</span><span class="sxs-lookup"><span data-stu-id="d7f01-107">Requirements and Limitations for Expressions</span></span>](../core/requirements-and-limitations-for-expressions.md)  
  
 [<span data-ttu-id="d7f01-108">式を使用する図形</span><span class="sxs-lookup"><span data-stu-id="d7f01-108">Shapes that Take Expressions</span></span>](../core/shapes-that-take-expressions.md)  
  
 [<span data-ttu-id="d7f01-109">式を作成する方法</span><span class="sxs-lookup"><span data-stu-id="d7f01-109">How to Create Expressions</span></span>](../core/how-to-create-expressions.md)  
  
 [<span data-ttu-id="d7f01-110">式における演算子の使用</span><span class="sxs-lookup"><span data-stu-id="d7f01-110">Using Operators in Expressions</span></span>](../core/using-operators-in-expressions.md)  
  
 [<span data-ttu-id="d7f01-111">式を使用して、メッセージの割り当てを実行する方法</span><span class="sxs-lookup"><span data-stu-id="d7f01-111">How to Use Expressions to Perform Message Assignments</span></span>](../core/how-to-use-expressions-to-perform-message-assignments.md)  
  
 [<span data-ttu-id="d7f01-112">メッセージに動的に変換する式を使用する方法</span><span class="sxs-lookup"><span data-stu-id="d7f01-112">How to Use Expressions to Dynamic Transform Messages</span></span>](../core/how-to-use-expressions-to-dynamic-transform-messages.md)  
  
 [<span data-ttu-id="d7f01-113">パイプラインを実行する式を使用する方法</span><span class="sxs-lookup"><span data-stu-id="d7f01-113">How to Use Expressions to Execute Pipelines</span></span>](../core/how-to-use-expressions-to-execute-pipelines.md)  
  
 [<span data-ttu-id="d7f01-114">式を使用してオブジェクトを作成する方法と、オブジェクトのメソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="d7f01-114">How to Use Expressions to Create Objects and Call Object Methods</span></span>](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md)  
  
 [<span data-ttu-id="d7f01-115">動的ポートに値を割り当てる式を使用する方法</span><span class="sxs-lookup"><span data-stu-id="d7f01-115">How to Use Expressions to Assign Values to Dynamic Ports</span></span>](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md)  
  
## <a name="see-also"></a><span data-ttu-id="d7f01-116">参照</span><span class="sxs-lookup"><span data-stu-id="d7f01-116">See Also</span></span>  
 <span data-ttu-id="d7f01-117">[Xlang-s 言語](../core/xlang-s-language.md) </span><span class="sxs-lookup"><span data-stu-id="d7f01-117">[XLANG-s Language](../core/xlang-s-language.md) </span></span>  
 <span data-ttu-id="d7f01-118">[オーケストレーションでメッセージの使用](../core/using-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="d7f01-118">[Using Messages in Orchestrations](../core/using-messages-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="d7f01-119">オーケストレーションでの変数の使用</span><span class="sxs-lookup"><span data-stu-id="d7f01-119">Using Variables in Orchestrations</span></span>](../core/using-variables-in-orchestrations.md)