---
title: 短期間のファクトとします。長期間のファクト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- facts, short-term
- facts, long-term
- short-term facts
- business rules, facts
- long-term facts
ms.assetid: de020b20-1012-498a-969e-4adc4549918c
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8319f0836d20a09765bb22933c129065d5393317
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393218"
---
# <a name="short-term-facts-vs-long-term-facts"></a><span data-ttu-id="7a858-102">短期間のファクトとします。長期間のファクト</span><span class="sxs-lookup"><span data-stu-id="7a858-102">Short-Term Facts vs. Long-Term Facts</span></span>
<span data-ttu-id="7a858-103">2 つの種類のファクトがルール エンジンの作業メモリにアサートされます: 短い期間のファクトと長期間のファクト。</span><span class="sxs-lookup"><span data-stu-id="7a858-103">Two types of facts are asserted into the working memory of the rule engine—short-term facts and long-term facts.</span></span>  
  
## <a name="short-term-facts"></a><span data-ttu-id="7a858-104">短期間のファクト</span><span class="sxs-lookup"><span data-stu-id="7a858-104">Short-Term Facts</span></span>  
 <span data-ttu-id="7a858-105">短期間のファクトは、ルール エンジンを一度だけ実行するサイクルに特有です。</span><span class="sxs-lookup"><span data-stu-id="7a858-105">A short-term fact is specific to a single execution cycle of the rule engine.</span></span> <span data-ttu-id="7a858-106">短期間のファクトは、ポリシーが実行された後に、ルール エンジンの作業メモリから自動的に取り消されます。</span><span class="sxs-lookup"><span data-stu-id="7a858-106">Short-term facts are retracted automatically from the working memory of the rule engine after the policy executes.</span></span> <span data-ttu-id="7a858-107">ポリシーのルール エンジンの実行サイクル間でデータが変更される場合は、データを短期間のファクトとしてルール エンジンに送信します。</span><span class="sxs-lookup"><span data-stu-id="7a858-107">If your data changes between execution cycles of the rule engine for a policy, you submit the data as a short-term fact to the rule engine.</span></span>  
  
 <span data-ttu-id="7a858-108">短期間のファクトの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="7a858-108">Examples of short-term facts are:</span></span>  
  
-   <span data-ttu-id="7a858-109">パラメーターとして送信するファクト、 **Policy.Execute**メソッド。</span><span class="sxs-lookup"><span data-stu-id="7a858-109">The facts you submit as parameters to the **Policy.Execute** method.</span></span>  
  
-   <span data-ttu-id="7a858-110">パラメーターとして送信するファクト、**ルールの呼び出し**図形。</span><span class="sxs-lookup"><span data-stu-id="7a858-110">The facts you submit as parameters to the **Call Rules** shape.</span></span>  
  
-   <span data-ttu-id="7a858-111">使用してルールのアクションから送信するファクト、 **Assert**関数。</span><span class="sxs-lookup"><span data-stu-id="7a858-111">The facts you submit from an action of a rule using the **Assert** function.</span></span>  
  
## <a name="long-term-facts"></a><span data-ttu-id="7a858-112">長期間のファクト</span><span class="sxs-lookup"><span data-stu-id="7a858-112">Long-Term Facts</span></span>  
 <span data-ttu-id="7a858-113">長期間のファクトは、ルール エンジンの作業メモリに読み込まれ、任意の数の実行サイクルに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7a858-113">A long-term fact is loaded into the working memory of the rule engine for use over an arbitrary number of execution cycles.</span></span> <span data-ttu-id="7a858-114">通常、長期間のファクトは、一般的にはポリシーの実行の合間には変更されない、変化の遅いファクトです。</span><span class="sxs-lookup"><span data-stu-id="7a858-114">Typically, long-term facts are slowly changing facts that do not typically change between executions of a policy.</span></span> <span data-ttu-id="7a858-115">たとえば、データベース接続を 1 回だけ作成し、同じデータベース接続を使用してポリシーを複数回実行する必要がある場合が考えられます。</span><span class="sxs-lookup"><span data-stu-id="7a858-115">For example, you may want to create a database connection only once, and execute the policy several times by using the same database connection.</span></span> <span data-ttu-id="7a858-116">短期間のファクトと長期間のファクトの唯一の大きな違いは、その実装にあります。</span><span class="sxs-lookup"><span data-stu-id="7a858-116">The only real distinction between short-term facts and long-term facts is in implementation.</span></span>  
  
 <span data-ttu-id="7a858-117">ファクトを長期間のファクトとして送信するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a858-117">To submit a fact as a long-term fact, you need to perform the following steps:</span></span>  
  
1. <span data-ttu-id="7a858-118">実装するファクト取得コンポーネントを作成、 **IFactRetriever**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="7a858-118">Create a fact retriever component that implements the **IFactRetriever** interface.</span></span> <span data-ttu-id="7a858-119">作成し、ファクトをルールの作業メモリにアサート エンジン、 **UpdateFacts**最初の時刻、および更新の後続の呼び出しに必要な場合に、ファクトのメソッドが呼び出される、 **UpdateFacts**メソッド。</span><span class="sxs-lookup"><span data-stu-id="7a858-119">Create and assert the fact into the working memory of the rule engine when the **UpdateFacts** method is invoked for the first time, and update the fact when necessary on subsequent invocations of the **UpdateFacts** method.</span></span>  
  
2. <span data-ttu-id="7a858-120">ビジネス ルール作成ツールを使用して、ファクト取得コンポーネントを使用するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="7a858-120">Configure the policy to use the fact retriever component by using the Business Rule Composer.</span></span>  
  
   <span data-ttu-id="7a858-121">ファクト取得コンポーネントを作成して、ポリシーで使用する詳細については、次を参照してください。[ファクト取得コンポーネントを作成する方法](../core/how-to-create-a-fact-retriever.md)します。</span><span class="sxs-lookup"><span data-stu-id="7a858-121">For more information about creating a fact retriever and using it in a policy, see [How to Create a Fact Retriever](../core/how-to-create-a-fact-retriever.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a858-122">参照</span><span class="sxs-lookup"><span data-stu-id="7a858-122">See Also</span></span>  
 [<span data-ttu-id="7a858-123">ファクト</span><span class="sxs-lookup"><span data-stu-id="7a858-123">Facts</span></span>](../core/facts.md)