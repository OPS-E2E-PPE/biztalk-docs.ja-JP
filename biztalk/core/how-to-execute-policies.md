---
title: "ポリシーを実行する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, policies
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: 90d28d9d-0204-47de-a927-26e284c886e4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b0aa834150f0d5c84ebb4c757769a2be38f3942
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-execute-policies"></a><span data-ttu-id="9b8a8-102">ポリシーを実行する方法</span><span class="sxs-lookup"><span data-stu-id="9b8a8-102">How to Execute Policies</span></span>
<span data-ttu-id="9b8a8-103">次のサンプル コードを使用してプログラムからポリシーを実行するルール エンジンを起動する方法を示しています、**ポリシー**クラス内で、 **Microsoft.RuleEngine**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="9b8a8-103">The following sample code shows how to invoke the rule engine to execute a policy programmatically by using the **Policy** class in the **Microsoft.RuleEngine** assembly.</span></span>  
  
```  
xmlDocument = IncomingXMLMessage.XMLCase;  
typedXmlDocument = new Microsoft.RuleEngine.TypedXmlDocument("Microsoft.Samples.BizTalk.LoansProcessor.Case",xmlDocument);  
policy = new Microsoft.RuleEngine.Policy("LoanProcessing");  
policy.Execute(typedXmlDocument);  
OutgoingXMLMessage.XMLCase = xmlDocument;  
policy.Dispose();  
```  
  
## <a name="important-methods-of-the-policy-class"></a><span data-ttu-id="9b8a8-104">Policy クラスの重要なメソッド</span><span class="sxs-lookup"><span data-stu-id="9b8a8-104">Important methods of the Policy class</span></span>  
 <span data-ttu-id="9b8a8-105">Policy クラスの重要なメソッドとその説明を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9b8a8-105">Here are the important methods of the Policy class and their descriptions.</span></span>  
  
|<span data-ttu-id="9b8a8-106">Policy クラスのメソッド</span><span class="sxs-lookup"><span data-stu-id="9b8a8-106">Method in the Policy class</span></span>|<span data-ttu-id="9b8a8-107">Description</span><span class="sxs-lookup"><span data-stu-id="9b8a8-107">Description</span></span>|  
|--------------------------------|-----------------|  
|<span data-ttu-id="9b8a8-108">Execute</span><span class="sxs-lookup"><span data-stu-id="9b8a8-108">Execute</span></span>|<span data-ttu-id="9b8a8-109">指定された短期間のファクトをルール エンジンの作業メモリに追加し、一致 - 競合解決 - アクションのアルゴリズムを使用してポリシーを実行します。</span><span class="sxs-lookup"><span data-stu-id="9b8a8-109">Adds the specified short-term facts into the rule engine's working memory and executes the policy using Match-Conflict Resolution-Action algorithm.</span></span> <span data-ttu-id="9b8a8-110">一致-競合解決-アクションのアルゴリズムの詳細については、次を参照してください。[条件の評価とアクションの実行](../core/condition-evaluation-and-action-execution.md)です。</span><span class="sxs-lookup"><span data-stu-id="9b8a8-110">For more information on Match-Conflict Resolution-Action algorithm, see [Condition Evaluation and Action Execution](../core/condition-evaluation-and-action-execution.md) .</span></span>|  
|<span data-ttu-id="9b8a8-111">Dispose</span><span class="sxs-lookup"><span data-stu-id="9b8a8-111">Dispose</span></span>|<span data-ttu-id="9b8a8-112">ポリシーを実行するためにルール エンジンで使用されているリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="9b8a8-112">Releases the resources used by the rule engine for executing the policy.</span></span>|  
|<span data-ttu-id="9b8a8-113">Clear</span><span class="sxs-lookup"><span data-stu-id="9b8a8-113">Clear</span></span>|<span data-ttu-id="9b8a8-114">ポリシーを実行するために作成されたルール エンジン インスタンスの作業メモリと議題をクリアまたはリセットします。</span><span class="sxs-lookup"><span data-stu-id="9b8a8-114">Clears or resets the working memory and the agenda of the rule engine instance created for executing the policy.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b8a8-115">参照</span><span class="sxs-lookup"><span data-stu-id="9b8a8-115">See Also</span></span>  
 [<span data-ttu-id="9b8a8-116">Policy.Dispose メソッド</span><span class="sxs-lookup"><span data-stu-id="9b8a8-116">Policy.Dispose Method</span></span>](../core/policy-dispose-method.md)