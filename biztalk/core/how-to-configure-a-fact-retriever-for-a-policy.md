---
title: ポリシーのファクト取得コンポーネントを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, policies
- Business Rule Composer, facts
- policies, facts
ms.assetid: a7bcf3e5-3f28-4f0e-b112-8c97dee072a1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7095ae5a03b6c3aec2d4f66db2563e7a6986fb39
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342292"
---
# <a name="how-to-configure-a-fact-retriever-for-a-policy"></a><span data-ttu-id="1c8cc-102">ポリシーのファクト取得コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="1c8cc-102">How to Configure a Fact Retriever for a Policy</span></span>
<span data-ttu-id="1c8cc-103">多くの場合、変更されないファクトを保存して、ホスト アプリケーションの初回実行サイクル、前に、ストレージからこれらの情報を取得、キャッシュ、ルール エンジンに 1 度だけでき、複数の実行サイクルで再利用します。</span><span class="sxs-lookup"><span data-stu-id="1c8cc-103">You can store facts that do not change frequently, and then before the first execution cycle of your host application, you can retrieve these facts from storage, present them once to the rule engine for caching, and reuse them over multiple execution cycles.</span></span>  
  
 <span data-ttu-id="1c8cc-104">ファクト取得コンポーネントをポリシーに関連付ける 2 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="1c8cc-104">There are two ways to associate a fact retriever with a policy.</span></span> <span data-ttu-id="1c8cc-105">こうことをビジネス ルール作成ツールを使用するかを使用してプログラムで、 **RuleSetExecutionConfiguration**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1c8cc-105">You can do this by using the Business Rule Composer or programmatically by using the **RuleSetExecutionConfiguration** object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c8cc-106">1 つのみのファクト取得コンポーネントの実装は、ポリシーのバージョンを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="1c8cc-106">Only one fact retriever implementation can be associated with a policy version.</span></span>  
  
### <a name="to-associate-a-fact-retriever-with-a-policy-in-the-business-rule-composer"></a><span data-ttu-id="1c8cc-107">ビジネス ルール作成ツールでポリシーをファクト取得コンポーネントを関連付ける</span><span class="sxs-lookup"><span data-stu-id="1c8cc-107">To associate a fact retriever with a policy in the Business Rule Composer</span></span>  
  
1.  <span data-ttu-id="1c8cc-108">ポリシー エクスプ ローラー ウィンドウで、ファクト取得コンポーネントを関連付けるポリシー バージョンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c8cc-108">In the Policy Explorer window, click the policy version with which you want to associate the fact retriever.</span></span>  
  
2.  <span data-ttu-id="1c8cc-109">プロパティ ウィンドウで、**省略記号**ボタン (...)、 **FactRetriever**ファクト取得コンポーネントのオブジェクトのグローバル アセンブリ キャッシュに参照するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="1c8cc-109">In the Properties window, click the **ellipsis** button (…) in the **FactRetriever** property to browse in the global assembly cache for a fact retriever object.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="1c8cc-110">**省略記号**ボタン (…) をクリックするまでは表示されません、 **FactRetriever**プロパティ ウィンドウ内の行。</span><span class="sxs-lookup"><span data-stu-id="1c8cc-110">The **ellipsis** button (…) does not appear until you click the **FactRetriever** row in the Property Window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c8cc-111">参照</span><span class="sxs-lookup"><span data-stu-id="1c8cc-111">See Also</span></span>  
 [<span data-ttu-id="1c8cc-112">ファクト取得コンポーネントを作成する方法</span><span class="sxs-lookup"><span data-stu-id="1c8cc-112">How to Create a Fact Retriever</span></span>](../core/how-to-create-a-fact-retriever.md)