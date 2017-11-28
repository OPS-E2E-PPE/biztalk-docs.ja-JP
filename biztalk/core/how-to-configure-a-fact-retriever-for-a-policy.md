---
title: "ポリシーのファクト取得コンポーネントを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, policies
- Business Rule Composer, facts
- policies, facts
ms.assetid: a7bcf3e5-3f28-4f0e-b112-8c97dee072a1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18572af1323de817b3c934866af917d2601332f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-fact-retriever-for-a-policy"></a><span data-ttu-id="c24d8-102">ポリシーのファクト取得コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="c24d8-102">How to Configure a Fact Retriever for a Policy</span></span>
<span data-ttu-id="c24d8-103">変更される頻度の低いファクトを保存しておくことができます。ホスト アプリケーションの初回実行サイクルの前に、これらのファクトをストレージから取得し、1 度だけルール エンジンに適用することにより、それ以降の複数の実行サイクルで、キャッシュされたファクトが再利用されます。</span><span class="sxs-lookup"><span data-stu-id="c24d8-103">You can store facts that do not change frequently, and then before the first execution cycle of your host application, you can retrieve these facts from storage, present them once to the rule engine for caching, and reuse them over multiple execution cycles.</span></span>  
  
 <span data-ttu-id="c24d8-104">ファクト取得コンポーネントとポリシーは、2 つの方法で関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="c24d8-104">There are two ways to associate a fact retriever with a policy.</span></span> <span data-ttu-id="c24d8-105">ことができますか、このビジネス ルール作成ツールを使用してプログラムを使用して、 **RuleSetExecutionConfiguration**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c24d8-105">You can do this by using the Business Rule Composer or programmatically by using the **RuleSetExecutionConfiguration** object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c24d8-106">1 つのポリシー バージョンには、ファクト取得コンポーネントの実装を 1 つだけ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="c24d8-106">Only one fact retriever implementation can be associated with a policy version.</span></span>  
  
### <a name="to-associate-a-fact-retriever-with-a-policy-in-the-business-rule-composer"></a><span data-ttu-id="c24d8-107">ビジネス ルール作成ツールを使用してファクト取得コンポーネントをポリシーに関連付けるには</span><span class="sxs-lookup"><span data-stu-id="c24d8-107">To associate a fact retriever with a policy in the Business Rule Composer</span></span>  
  
1.  <span data-ttu-id="c24d8-108">[ポリシー エクスプローラー] ウィンドウで、ファクト取得コンポーネントを関連付けるポリシー バージョンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c24d8-108">In the Policy Explorer window, click the policy version with which you want to associate the fact retriever.</span></span>  
  
2.  <span data-ttu-id="c24d8-109">[プロパティ] ウィンドウ、**省略記号**ボタン ([...]) で、 **FactRetriever**ファクト取得コンポーネント オブジェクトのグローバル アセンブリ キャッシュ内で参照するプロパティです。</span><span class="sxs-lookup"><span data-stu-id="c24d8-109">In the Properties window, click the **ellipsis** button (…) in the **FactRetriever** property to browse in the global assembly cache for a fact retriever object.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c24d8-110">**省略記号**ボタン (...) をクリックするまでは表示されません、 **FactRetriever**プロパティ ウィンドウ内の行。</span><span class="sxs-lookup"><span data-stu-id="c24d8-110">The **ellipsis** button (…) does not appear until you click the **FactRetriever** row in the Property Window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c24d8-111">参照</span><span class="sxs-lookup"><span data-stu-id="c24d8-111">See Also</span></span>  
 [<span data-ttu-id="c24d8-112">ファクト取得コンポーネントを作成する方法</span><span class="sxs-lookup"><span data-stu-id="c24d8-112">How to Create a Fact Retriever</span></span>](../core/how-to-create-a-fact-retriever.md)