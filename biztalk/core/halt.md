---
title: "停止 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Halt function [Business Rules Engine]
ms.assetid: 468ba6dd-2bb2-4787-a824-1f5455508efd
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07ca8091d4ff4405704314d72939758c7600a71a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="halt"></a><span data-ttu-id="cbe1c-102">停止</span><span class="sxs-lookup"><span data-stu-id="cbe1c-102">Halt</span></span>
<span data-ttu-id="cbe1c-103">使用することができます、**停止**ルール エンジンの現在の実行を停止するように機能します。</span><span class="sxs-lookup"><span data-stu-id="cbe1c-103">You can use the **Halt** function to halt the current rule engine execution.</span></span> <span data-ttu-id="cbe1c-104">**停止**関数型のパラメーターを 1 つ取ります`Boolean`です。</span><span class="sxs-lookup"><span data-stu-id="cbe1c-104">The **Halt** function takes one parameter of type `Boolean`.</span></span> <span data-ttu-id="cbe1c-105">パラメーターの値を `true` に指定すると、ルール エンジンは保留候補ルールを含む議題もクリアします。</span><span class="sxs-lookup"><span data-stu-id="cbe1c-105">If you specify the value for the parameter as `true`, the rule engine also clears the agenda that contains the pending candidate rules.</span></span>  
  
 <span data-ttu-id="cbe1c-106">**Policy.Execute**メソッドがラップするラッパーでは基本的に、 **RuleEngine.Execute**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="cbe1c-106">The **Policy.Execute** method is basically a wrapper around the **RuleEngine.Execute** method.</span></span> <span data-ttu-id="cbe1c-107">これは、次のようなコードになります。</span><span class="sxs-lookup"><span data-stu-id="cbe1c-107">It has code similar to the following code:</span></span>  
  
```  
RuleEngine.Assert(facts);   
RuleEngine.Execute();   
RuleEngine.Retract(facts);  
```  
  
 <span data-ttu-id="cbe1c-108">使用する場合、 **Policy.Execute** 、ポリシーをルール エンジンを実行するメソッドに制御が戻ります、 **Policy.Execute**メソッドと、**停止**関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="cbe1c-108">If you use the **Policy.Execute** method to execute a policy, the rule engine returns control to the **Policy.Execute** method when the **Halt** function is executed.</span></span> <span data-ttu-id="cbe1c-109">**Policy.Execute**メソッドはファクトを取り消して、呼び出し元にコントロールを返します。</span><span class="sxs-lookup"><span data-stu-id="cbe1c-109">The **Policy.Execute** method retracts the facts and returns control to the caller.</span></span> <span data-ttu-id="cbe1c-110">したがって、この場合停止したポリシーの実行は再開できません。</span><span class="sxs-lookup"><span data-stu-id="cbe1c-110">Therefore, the halted policy execution cannot be resumed in this case.</span></span> <span data-ttu-id="cbe1c-111">同じ処理を使用するときの動作、**ルールの呼び出し**図形をポリシーを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cbe1c-111">The same thing happens when you use the **Call Rules** shape to invoke the policy.</span></span>  
  
 <span data-ttu-id="cbe1c-112">ただし、使用する場合、 **RuleEngine.Execute**メソッドだけ呼び出すことによって、次のルールの実行を待機中、停止したポリシーの実行を再開する、ポリシーを実行するには、直接**RuleEngine.Execute**もう一度 (2 つの呼び出しの間に必要なオブジェクトを取り消していない) 提供します。</span><span class="sxs-lookup"><span data-stu-id="cbe1c-112">However, if you use the **RuleEngine.Execute** method directly to execute the policy, you can resume the halted policy execution with the next pending rule firing by simply calling **RuleEngine.Execute** again (provided you did not retract any objects needed between the two calls).</span></span> <span data-ttu-id="cbe1c-113">停止したポリシーの実行を再開するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cbe1c-113">The sample code for resuming the halted policy execution is as follows:</span></span>  
  
```  
//assert facts into working memory of the rule engine instance  
RuleEngine.Assert(facts);   
//execute the policy  
RuleEngine.Execute();   
//policy invokes the Halt method when executing actions.   
//control is returned to here when the Halt method is invoked  
  
//when engine is halted do the following  
//Add your code here  
  
//To resume the halted rule engine execution  
RuleEngine.Execute();  
//retract or remove facts frm the working memory of the rule engine  
RuleEngine.Retract(facts);  
```  
  
 <span data-ttu-id="cbe1c-114">なお、 **Policy.Execute**メソッドは、パフォーマンス向上のためのルール エンジンのインスタンスをキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="cbe1c-114">Note that the **Policy.Execute** method caches the rule engine instances for better performance.</span></span> <span data-ttu-id="cbe1c-115">使用すると、 **RuleEngine.Execute**メソッドを直接、ルール エンジンのインスタンスはキャッシュされません。</span><span class="sxs-lookup"><span data-stu-id="cbe1c-115">When you use the **RuleEngine.Execute** method directly, the rule engine instances are not cached.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbe1c-116">参照</span><span class="sxs-lookup"><span data-stu-id="cbe1c-116">See Also</span></span>  
 [<span data-ttu-id="cbe1c-117">エンジン制御関数</span><span class="sxs-lookup"><span data-stu-id="cbe1c-117">Engine Control Functions</span></span>](../core/engine-control-functions.md)