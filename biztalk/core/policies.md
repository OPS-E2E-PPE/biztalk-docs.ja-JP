---
title: ポリシー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Engine, policies
- policies, about policies
- policies, deploying
- policies, Business Rules Engine
- policies
- business rules, policies
- policies, versioning
- policies, testing
- policies, creating
- policies, updating
ms.assetid: 2e0ae081-938d-4e2a-947e-1c0ecfebb4b8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4d46929ab985008e826bab36ab6e1648d8602e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394976"
---
# <a name="policies"></a><span data-ttu-id="ba4e1-102">ポリシー</span><span class="sxs-lookup"><span data-stu-id="ba4e1-102">Policies</span></span>
<span data-ttu-id="ba4e1-103">ポリシーは、ルールの論理的なグループです。</span><span class="sxs-lookup"><span data-stu-id="ba4e1-103">A policy is a logical grouping of rules.</span></span> <span data-ttu-id="ba4e1-104">ポリシーのバージョンを作成、保存、ファクトに適用してテストを結果に満足したら、発行し、運用環境にデプロイします。</span><span class="sxs-lookup"><span data-stu-id="ba4e1-104">You compose a version of a policy, save it, test it by applying it to facts, and, when you are satisfied with the results, publish it and deploy it to a production environment.</span></span>  
  
## <a name="policy-composition"></a><span data-ttu-id="ba4e1-105">ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="ba4e1-105">Policy Composition</span></span>  
 <span data-ttu-id="ba4e1-106">ファクトと定義からルールを構築して、ビジネス ルール作成ツールでポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ba4e1-106">You can compose policies in the Business Rule Composer by constructing rules from facts and definitions.</span></span> <span data-ttu-id="ba4e1-107">ポリシーは、サイズの大きい任意の規則のセットを含めることができますが、通常、ポリシーを使用するアプリケーションのコンテキスト内で特定のビジネス ドメインに関連するルールからポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ba4e1-107">A policy can contain an arbitrarily large set of rules, but typically you compose a policy from rules that pertain to a specific business domain within the context of the application that will be using the policy.</span></span>  
  
## <a name="policy-testing"></a><span data-ttu-id="ba4e1-108">ポリシーのテスト</span><span class="sxs-lookup"><span data-stu-id="ba4e1-108">Policy Testing</span></span>  
 <span data-ttu-id="ba4e1-109">ポリシーのテストの実行は、公開および実稼働環境に展開する前に効果的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ba4e1-109">You can effectively perform a test run of your policy before it is published and deployed in a production environment.</span></span> <span data-ttu-id="ba4e1-110">ビジネス ルール作成ツールは、ポリシーのファクトのインスタンスを指定することができます、ポリシーを実行し、その出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="ba4e1-110">The Business Rule Composer allows you to supply instances of facts to a policy, run the policy, and view its output.</span></span> <span data-ttu-id="ba4e1-111">出力には、ファクト アクティビティ、ルールの実行、条件の評価、および議題への更新が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ba4e1-111">The output includes fact activity, rule execution, condition evaluation, and updates to the agenda.</span></span>  
  
## <a name="policy-versions"></a><span data-ttu-id="ba4e1-112">ポリシーのバージョン</span><span class="sxs-lookup"><span data-stu-id="ba4e1-112">Policy Versions</span></span>  
 <span data-ttu-id="ba4e1-113">ポリシーでは、すべてのルールを定義した後は、ポリシーのバージョンを発行できます。</span><span class="sxs-lookup"><span data-stu-id="ba4e1-113">After you have defined all the rules in your policy, you can publish the policy version.</span></span> <span data-ttu-id="ba4e1-114">この方法で、ポリシーがロック ダウンされてし、その動作は明確に定義します。</span><span class="sxs-lookup"><span data-stu-id="ba4e1-114">In this way the policy is locked down, and its behavior is well-defined.</span></span>  
  
 <span data-ttu-id="ba4e1-115">特定のポリシー バージョンを特定のビジネス環境での状況で使用し、条件が変化したときに、別のバージョンで置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="ba4e1-115">A given policy version can be used under a given set of circumstances in your business environment, and replaced by another version when those circumstances change.</span></span> <span data-ttu-id="ba4e1-116">また、新旧両方のバージョンは、さまざまなアプリケーションで同時に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ba4e1-116">Also, both new and old versions can be used simultaneously by different applications.</span></span>  
  
## <a name="policy-deployment"></a><span data-ttu-id="ba4e1-117">ポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="ba4e1-117">Policy Deployment</span></span>  
 <span data-ttu-id="ba4e1-118">ポリシーの運用環境で実行する準備ができたら、ホストするアプリケーションで使用できるようにするデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="ba4e1-118">When your policy is ready to be run in a production environment, you can deploy it to make it available to a hosting application.</span></span>  
  
## <a name="dynamic-policy-updates"></a><span data-ttu-id="ba4e1-119">ポリシーの動的更新</span><span class="sxs-lookup"><span data-stu-id="ba4e1-119">Dynamic Policy Updates</span></span>  
 <span data-ttu-id="ba4e1-120">ポリシーの動的更新が、実行中とは別にポリシーを変更することを許可するビジネス プロセス。</span><span class="sxs-lookup"><span data-stu-id="ba4e1-120">Dynamic policy updates allow you to modify policies independently of a running business process.</span></span> <span data-ttu-id="ba4e1-121">作成して、ポリシーの更新バージョンを展開し、ホスト アプリケーションは、ほぼリアルタイムで更新プログラムを組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="ba4e1-121">You can create and deploy an updated version of the policy, and the hosting application can incorporate the update in near real time.</span></span> <span data-ttu-id="ba4e1-122">この更新プログラム、コードの変更は不要し、そのため、再開発およびアプリケーションを再展開のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="ba4e1-122">This update does not require you to change any code, and thus you can avoid the overhead of redeveloping and redeploying the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba4e1-123">参照</span><span class="sxs-lookup"><span data-stu-id="ba4e1-123">See Also</span></span>  
 [<span data-ttu-id="ba4e1-124">ビジネス ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="ba4e1-124">Business Rules Engine</span></span>](../core/business-rules-engine.md)