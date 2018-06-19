---
title: オーケストレーションで式の使用 |Microsoft ドキュメント
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
ms.openlocfilehash: 880e1ee08a232aca3a04763c5d5c1797fd238fbe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287138"
---
# <a name="using-expressions-in-orchestrations"></a><span data-ttu-id="f853b-102">オーケストレーションでの式の使用</span><span class="sxs-lookup"><span data-stu-id="f853b-102">Using Expressions in Orchestrations</span></span>
<span data-ttu-id="f853b-103">BizTalk 式エディターを使用して XLANG/s 式を入力してロジックを追加し、オーケストレーションの変数およびメッセージの値を操作またはテストできます。</span><span class="sxs-lookup"><span data-stu-id="f853b-103">You can use BizTalk Expression Editor to enter XLANG/s expressions to add logic to manipulate and test the values of your orchestration variables and messages.</span></span> <span data-ttu-id="f853b-104">ただし、式図形を使用して高度なオーケストレーション ロジックを実行することはお勧めしません。高度なオーケストレーション ロジックは多くの場合、オーケストレーション図面自体に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f853b-104">However, it is not a good practice to use it to perform high-level orchestration logic, which preferably would be visible in the orchestration drawing itself.</span></span> <span data-ttu-id="f853b-105">ビジネス プロセスの透明性を保ち、再構築を簡単にするため、単純なモジュール形式の式を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f853b-105">For business process transparency and easy of reconfiguration, we recommend that you use simple and modular expressions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f853b-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f853b-106">In This Section</span></span>  
 [<span data-ttu-id="f853b-107">式の要件と制限</span><span class="sxs-lookup"><span data-stu-id="f853b-107">Requirements and Limitations for Expressions</span></span>](../core/requirements-and-limitations-for-expressions.md)  
  
 [<span data-ttu-id="f853b-108">式を使用する図形</span><span class="sxs-lookup"><span data-stu-id="f853b-108">Shapes that Take Expressions</span></span>](../core/shapes-that-take-expressions.md)  
  
 [<span data-ttu-id="f853b-109">式を作成する方法</span><span class="sxs-lookup"><span data-stu-id="f853b-109">How to Create Expressions</span></span>](../core/how-to-create-expressions.md)  
  
 [<span data-ttu-id="f853b-110">式における演算子の使用</span><span class="sxs-lookup"><span data-stu-id="f853b-110">Using Operators in Expressions</span></span>](../core/using-operators-in-expressions.md)  
  
 [<span data-ttu-id="f853b-111">式を使用して、メッセージの割り当てを実行する方法</span><span class="sxs-lookup"><span data-stu-id="f853b-111">How to Use Expressions to Perform Message Assignments</span></span>](../core/how-to-use-expressions-to-perform-message-assignments.md)  
  
 [<span data-ttu-id="f853b-112">メッセージを動的に変換する式を使用する方法</span><span class="sxs-lookup"><span data-stu-id="f853b-112">How to Use Expressions to Dynamic Transform Messages</span></span>](../core/how-to-use-expressions-to-dynamic-transform-messages.md)  
  
 [<span data-ttu-id="f853b-113">式を使用してパイプラインを実行する方法</span><span class="sxs-lookup"><span data-stu-id="f853b-113">How to Use Expressions to Execute Pipelines</span></span>](../core/how-to-use-expressions-to-execute-pipelines.md)  
  
 [<span data-ttu-id="f853b-114">式を使用してオブジェクトを作成する方法とオブジェクトのメソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="f853b-114">How to Use Expressions to Create Objects and Call Object Methods</span></span>](../core/how-to-use-expressions-to-create-objects-and-call-object-methods.md)  
  
 [<span data-ttu-id="f853b-115">動的ポートに値を代入する式を使用する方法</span><span class="sxs-lookup"><span data-stu-id="f853b-115">How to Use Expressions to Assign Values to Dynamic Ports</span></span>](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md)  
  
## <a name="see-also"></a><span data-ttu-id="f853b-116">参照</span><span class="sxs-lookup"><span data-stu-id="f853b-116">See Also</span></span>  
 <span data-ttu-id="f853b-117">[XLANG の言語](../core/xlang-s-language.md) </span><span class="sxs-lookup"><span data-stu-id="f853b-117">[XLANG-s Language](../core/xlang-s-language.md) </span></span>  
 <span data-ttu-id="f853b-118">[オーケストレーションでメッセージの使用](../core/using-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="f853b-118">[Using Messages in Orchestrations](../core/using-messages-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="f853b-119">オーケストレーションで変数の使用</span><span class="sxs-lookup"><span data-stu-id="f853b-119">Using Variables in Orchestrations</span></span>](../core/using-variables-in-orchestrations.md)