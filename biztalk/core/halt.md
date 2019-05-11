---
title: 停止 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Halt function [Business Rules Engine]
ms.assetid: 468ba6dd-2bb2-4787-a824-1f5455508efd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcc7006581b3ccbf856d48d365cf6b003d97ec93
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344788"
---
# <a name="halt"></a><span data-ttu-id="b69e1-102">停止</span><span class="sxs-lookup"><span data-stu-id="b69e1-102">Halt</span></span>
<span data-ttu-id="b69e1-103">使用することができます、 **Halt**関数を現在のルール エンジン実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="b69e1-103">You can use the **Halt** function to halt the current rule engine execution.</span></span> <span data-ttu-id="b69e1-104">**Halt**関数は 1 つのパラメーター型の`Boolean`します。</span><span class="sxs-lookup"><span data-stu-id="b69e1-104">The **Halt** function takes one parameter of type `Boolean`.</span></span> <span data-ttu-id="b69e1-105">パラメーターの値を指定する場合`true`、ルール エンジンは保留候補ルールを含む議題もクリアします。</span><span class="sxs-lookup"><span data-stu-id="b69e1-105">If you specify the value for the parameter as `true`, the rule engine also clears the agenda that contains the pending candidate rules.</span></span>  
  
 <span data-ttu-id="b69e1-106">**Policy.Execute**メソッドは、ラッパーでは基本的に、 **RuleEngine.Execute**メソッド。</span><span class="sxs-lookup"><span data-stu-id="b69e1-106">The **Policy.Execute** method is basically a wrapper around the **RuleEngine.Execute** method.</span></span> <span data-ttu-id="b69e1-107">次のコードのようなコードがあります。</span><span class="sxs-lookup"><span data-stu-id="b69e1-107">It has code similar to the following code:</span></span>  
  
```  
RuleEngine.Assert(facts);   
RuleEngine.Execute();   
RuleEngine.Retract(facts);  
```  
  
 <span data-ttu-id="b69e1-108">使用する場合、 **Policy.Execute**ポリシー、ルール エンジンを実行するメソッドに制御が戻ります、 **Policy.Execute**メソッドと、 **Halt**関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="b69e1-108">If you use the **Policy.Execute** method to execute a policy, the rule engine returns control to the **Policy.Execute** method when the **Halt** function is executed.</span></span> <span data-ttu-id="b69e1-109">**Policy.Execute**メソッドはファクトを取り消して、呼び出し元にコントロールを返します。</span><span class="sxs-lookup"><span data-stu-id="b69e1-109">The **Policy.Execute** method retracts the facts and returns control to the caller.</span></span> <span data-ttu-id="b69e1-110">そのため、ここで、停止したポリシーの実行を再開できません。</span><span class="sxs-lookup"><span data-stu-id="b69e1-110">Therefore, the halted policy execution cannot be resumed in this case.</span></span> <span data-ttu-id="b69e1-111">同じ処理を使用するときの動作、**ルールの呼び出し**図形にポリシーを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b69e1-111">The same thing happens when you use the **Call Rules** shape to invoke the policy.</span></span>  
  
 <span data-ttu-id="b69e1-112">ただし、使用する場合、 **RuleEngine.Execute**メソッド呼び出すだけで、次のルールの実行を待機中、停止したポリシーの実行を再開する、ポリシーを実行するには、直接**RuleEngine.Execute**もう一度 (指定された 2 つの呼び出しの間に必要なオブジェクトを取り消していない)。</span><span class="sxs-lookup"><span data-stu-id="b69e1-112">However, if you use the **RuleEngine.Execute** method directly to execute the policy, you can resume the halted policy execution with the next pending rule firing by simply calling **RuleEngine.Execute** again (provided you did not retract any objects needed between the two calls).</span></span> <span data-ttu-id="b69e1-113">停止したポリシーの実行を再開するためのサンプル コードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b69e1-113">The sample code for resuming the halted policy execution is as follows:</span></span>  
  
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
  
 <span data-ttu-id="b69e1-114">なお、 **Policy.Execute**メソッドはパフォーマンス向上のためのルール エンジンのインスタンスをキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="b69e1-114">Note that the **Policy.Execute** method caches the rule engine instances for better performance.</span></span> <span data-ttu-id="b69e1-115">使用すると、 **RuleEngine.Execute**メソッドを直接、ルール エンジン インスタンスはキャッシュされません。</span><span class="sxs-lookup"><span data-stu-id="b69e1-115">When you use the **RuleEngine.Execute** method directly, the rule engine instances are not cached.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b69e1-116">参照</span><span class="sxs-lookup"><span data-stu-id="b69e1-116">See Also</span></span>  
 [<span data-ttu-id="b69e1-117">エンジン制御関数</span><span class="sxs-lookup"><span data-stu-id="b69e1-117">Engine Control Functions</span></span>](../core/engine-control-functions.md)