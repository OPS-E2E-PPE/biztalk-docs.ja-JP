---
title: "ポリシー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bd05d6cf67d89ee811cac45ac3950697db74f59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="policies"></a><span data-ttu-id="308fa-102">ポリシー</span><span class="sxs-lookup"><span data-stu-id="308fa-102">Policies</span></span>
<span data-ttu-id="308fa-103">ポリシーはルールの論理的なグループです。</span><span class="sxs-lookup"><span data-stu-id="308fa-103">A policy is a logical grouping of rules.</span></span> <span data-ttu-id="308fa-104">あるバージョンのポリシーを作成し、保存し、ファクトに適用してテストし、目的の結果が得られた場合には、公開して実稼働環境に展開することができます。</span><span class="sxs-lookup"><span data-stu-id="308fa-104">You compose a version of a policy, save it, test it by applying it to facts, and, when you are satisfied with the results, publish it and deploy it to a production environment.</span></span>  
  
## <a name="policy-composition"></a><span data-ttu-id="308fa-105">ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="308fa-105">Policy Composition</span></span>  
 <span data-ttu-id="308fa-106">ビジネス ルール作成ツールで、ファクトおよび定義からルールを構築することによりポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="308fa-106">You can compose policies in the Business Rule Composer by constructing rules from facts and definitions.</span></span> <span data-ttu-id="308fa-107">ポリシーには、任意の大きさのルールのセットを含めることができますが、通常は、ポリシーを使用するアプリケーションのコンテキスト内で特定のビジネス ドメインに関連するポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="308fa-107">A policy can contain an arbitrarily large set of rules, but typically you compose a policy from rules that pertain to a specific business domain within the context of the application that will be using the policy.</span></span>  
  
## <a name="policy-testing"></a><span data-ttu-id="308fa-108">ポリシーのテスト</span><span class="sxs-lookup"><span data-stu-id="308fa-108">Policy Testing</span></span>  
 <span data-ttu-id="308fa-109">ポリシーを実稼働環境で公開および展開する前に、ポリシーのテスト実行を効果的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="308fa-109">You can effectively perform a test run of your policy before it is published and deployed in a production environment.</span></span> <span data-ttu-id="308fa-110">ビジネス ルール作成ツールを使用して、ファクトのインスタンスをポリシーに提供し、ポリシーを実行し、その出力を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="308fa-110">The Business Rule Composer allows you to supply instances of facts to a policy, run the policy, and view its output.</span></span> <span data-ttu-id="308fa-111">出力に含まれるのは、ファクト アクティビティ、ルールの実行、条件の評価、および議題への更新です。</span><span class="sxs-lookup"><span data-stu-id="308fa-111">The output includes fact activity, rule execution, condition evaluation, and updates to the agenda.</span></span>  
  
## <a name="policy-versions"></a><span data-ttu-id="308fa-112">ポリシー バージョン</span><span class="sxs-lookup"><span data-stu-id="308fa-112">Policy Versions</span></span>  
 <span data-ttu-id="308fa-113">ポリシーのルールをすべて定義した後で、ポリシー バージョンを公開できます。</span><span class="sxs-lookup"><span data-stu-id="308fa-113">After you have defined all the rules in your policy, you can publish the policy version.</span></span> <span data-ttu-id="308fa-114">この方法では、ポリシーがロック ダウンされ、動作が厳密に定義されます。</span><span class="sxs-lookup"><span data-stu-id="308fa-114">In this way the policy is locked down, and its behavior is well-defined.</span></span>  
  
 <span data-ttu-id="308fa-115">ビジネス環境の特定の条件セットの下で、特定のポリシー バージョンを使用できます、条件が変化した場合には別のバージョンで置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="308fa-115">A given policy version can be used under a given set of circumstances in your business environment, and replaced by another version when those circumstances change.</span></span> <span data-ttu-id="308fa-116">また、新旧バージョンの両方を異なるアプリケーションで同時に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="308fa-116">Also, both new and old versions can be used simultaneously by different applications.</span></span>  
  
## <a name="policy-deployment"></a><span data-ttu-id="308fa-117">ポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="308fa-117">Policy Deployment</span></span>  
 <span data-ttu-id="308fa-118">ポリシーを実稼働環境で実行する準備が整ったら、ポリシーを展開し、ホストするアプリケーションで利用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="308fa-118">When your policy is ready to be run in a production environment, you can deploy it to make it available to a hosting application.</span></span>  
  
## <a name="dynamic-policy-updates"></a><span data-ttu-id="308fa-119">ポリシーの動的更新</span><span class="sxs-lookup"><span data-stu-id="308fa-119">Dynamic Policy Updates</span></span>  
 <span data-ttu-id="308fa-120">ポリシーの動的更新により、実行中のビジネス プロセスとは別にポリシーを修正できます。</span><span class="sxs-lookup"><span data-stu-id="308fa-120">Dynamic policy updates allow you to modify policies independently of a running business process.</span></span> <span data-ttu-id="308fa-121">ポリシーの更新済みバージョンを作成および展開できます。ホストするアプリケーションは、ほとんどリアルタイムで更新を組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="308fa-121">You can create and deploy an updated version of the policy, and the hosting application can incorporate the update in near real time.</span></span> <span data-ttu-id="308fa-122">この更新ではコードを変更する必要がないため、アプリケーションの再開発および再展開のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="308fa-122">This update does not require you to change any code, and thus you can avoid the overhead of redeveloping and redeploying the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="308fa-123">参照</span><span class="sxs-lookup"><span data-stu-id="308fa-123">See Also</span></span>  
 [<span data-ttu-id="308fa-124">ビジネス ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="308fa-124">Business Rules Engine</span></span>](../core/business-rules-engine.md)