---
title: ポリシーを実行する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, policies
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: 90d28d9d-0204-47de-a927-26e284c886e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4eaf60193a3435808c0901ca1c441527a67884f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337817"
---
# <a name="how-to-execute-policies"></a><span data-ttu-id="6d293-102">ポリシーを実行する方法</span><span class="sxs-lookup"><span data-stu-id="6d293-102">How to Execute Policies</span></span>
<span data-ttu-id="6d293-103">次のサンプル コードを使用してポリシーをプログラムで実行するルール エンジンを呼び出す方法を示しています、**ポリシー**クラス、 **Microsoft.RuleEngine**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="6d293-103">The following sample code shows how to invoke the rule engine to execute a policy programmatically by using the **Policy** class in the **Microsoft.RuleEngine** assembly.</span></span>  
  
```  
xmlDocument = IncomingXMLMessage.XMLCase;  
typedXmlDocument = new Microsoft.RuleEngine.TypedXmlDocument("Microsoft.Samples.BizTalk.LoansProcessor.Case",xmlDocument);  
policy = new Microsoft.RuleEngine.Policy("LoanProcessing");  
policy.Execute(typedXmlDocument);  
OutgoingXMLMessage.XMLCase = xmlDocument;  
policy.Dispose();  
```  
  
## <a name="important-methods-of-the-policy-class"></a><span data-ttu-id="6d293-104">ポリシー クラスの重要なメソッド</span><span class="sxs-lookup"><span data-stu-id="6d293-104">Important methods of the Policy class</span></span>  
 <span data-ttu-id="6d293-105">Policy クラスとその説明の重要なメソッドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="6d293-105">Here are the important methods of the Policy class and their descriptions.</span></span>  
  
|<span data-ttu-id="6d293-106">ポリシー クラスのメソッド</span><span class="sxs-lookup"><span data-stu-id="6d293-106">Method in the Policy class</span></span>|<span data-ttu-id="6d293-107">説明</span><span class="sxs-lookup"><span data-stu-id="6d293-107">Description</span></span>|  
|--------------------------------|-----------------|  
|<span data-ttu-id="6d293-108">Execute</span><span class="sxs-lookup"><span data-stu-id="6d293-108">Execute</span></span>|<span data-ttu-id="6d293-109">指定した短期間のファクトをルール エンジンの作業メモリに追加し、一致-競合解決-アクションのアルゴリズムを使用してポリシーを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d293-109">Adds the specified short-term facts into the rule engine's working memory and executes the policy using Match-Conflict Resolution-Action algorithm.</span></span> <span data-ttu-id="6d293-110">一致-競合解決-アクションのアルゴリズムの詳細については、次を参照してください。[条件の評価とアクションの実行](../core/condition-evaluation-and-action-execution.md)します。</span><span class="sxs-lookup"><span data-stu-id="6d293-110">For more information on Match-Conflict Resolution-Action algorithm, see [Condition Evaluation and Action Execution](../core/condition-evaluation-and-action-execution.md) .</span></span>|  
|<span data-ttu-id="6d293-111">Dispose</span><span class="sxs-lookup"><span data-stu-id="6d293-111">Dispose</span></span>|<span data-ttu-id="6d293-112">ポリシーを実行するため、ルール エンジンによって使用されるリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="6d293-112">Releases the resources used by the rule engine for executing the policy.</span></span>|  
|<span data-ttu-id="6d293-113">Clear</span><span class="sxs-lookup"><span data-stu-id="6d293-113">Clear</span></span>|<span data-ttu-id="6d293-114">クリアまたは作業メモリと、ポリシーの実行用に作成されたルール エンジン インスタンスの議題をリセットします。</span><span class="sxs-lookup"><span data-stu-id="6d293-114">Clears or resets the working memory and the agenda of the rule engine instance created for executing the policy.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6d293-115">参照</span><span class="sxs-lookup"><span data-stu-id="6d293-115">See Also</span></span>  
 [<span data-ttu-id="6d293-116">Policy.Dispose メソッド</span><span class="sxs-lookup"><span data-stu-id="6d293-116">Policy.Dispose Method</span></span>](../core/policy-dispose-method.md)