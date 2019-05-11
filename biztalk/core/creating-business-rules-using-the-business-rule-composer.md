---
title: ビジネス ルール作成ツールを使用してルールの作成 |Microsoft Docs
ms.custom: ''
ms.date: 02/01/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0600a2b2-36a2-4496-8ba1-c5f6e2fa4760
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e197557be5d5d5cf00fd7ca420d6886cdbb83166
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389946"
---
# <a name="create-business-rules-using-the-business-rule-composer"></a><span data-ttu-id="c9b0d-102">ビジネス ルール作成ツールを使用してビジネス ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="c9b0d-102">Create Business Rules Using the Business Rule Composer</span></span>

## <a name="overview"></a><span data-ttu-id="c9b0d-103">概要</span><span class="sxs-lookup"><span data-stu-id="c9b0d-103">Overview</span></span>
<span data-ttu-id="c9b0d-104">ビジネス ルール作成ツールでは、1 つまたは複数のビジネス ルールを持つビジネス ポリシーを作成できます。 および、これらのポリシーを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="c9b0d-104">The Business Rule Composer allows you to create business policies with one or more business rules, and it allows you to deploy these policies.</span></span> <span data-ttu-id="c9b0d-105">また、ファクト (XML、データベース、および .NET) を参照し、ビジネス ルールでファクトを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c9b0d-105">It also allows you to browse for facts (XML, database, and .NET), and use the facts in business rules.</span></span> <span data-ttu-id="c9b0d-106">さらに、ファクトに基づくビジネス ボキャブラリを作成し、ビジネス ルールでボキャブラリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9b0d-106">In addition, it allows you to create business vocabularies based on facts, and to use the vocabularies in business rules.</span></span>  
  
 <span data-ttu-id="c9b0d-107">このセクションは、ビジネス ルール作成ツールを使用して、ビジネス ルールを作成する方法のタスク固有の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c9b0d-107">This section provides task-specific information about using the Business Rule Composer to create business rules.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c9b0d-108">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c9b0d-108">Next steps</span></span>
  
-   [<span data-ttu-id="c9b0d-109">ビジネス ルール作成ツールを起動してポリシーを読み込む</span><span class="sxs-lookup"><span data-stu-id="c9b0d-109">Start the Business Rule Composer and Load a Policy</span></span>](../core/how-to-start-the-business-rule-composer-and-load-a-policy.md)  
  
-   [<span data-ttu-id="c9b0d-110">ビジネス ルール作成ツールのウィンドウ</span><span class="sxs-lookup"><span data-stu-id="c9b0d-110">Windows of the Business Rule Composer</span></span>](../core/windows-of-the-business-rule-composer.md)  
  
-   [<span data-ttu-id="c9b0d-111">ファクトの選択</span><span class="sxs-lookup"><span data-stu-id="c9b0d-111">Selecting Facts</span></span>](../core/selecting-facts.md)  
  
-   [<span data-ttu-id="c9b0d-112">ポリシーとルールの作成</span><span class="sxs-lookup"><span data-stu-id="c9b0d-112">Create Policies and Rules</span></span>](../core/how-to-create-policies-and-rules.md)  
  
-   [<span data-ttu-id="c9b0d-113">規則を変更します。</span><span class="sxs-lookup"><span data-stu-id="c9b0d-113">Modify Rules</span></span>](../core/how-to-modify-rules.md)  
  
-   [<span data-ttu-id="c9b0d-114">ポリシーのバージョンの管理</span><span class="sxs-lookup"><span data-stu-id="c9b0d-114">Maintain Policy Versions</span></span>](../core/how-to-maintain-policy-versions.md)  
  
-   [<span data-ttu-id="c9b0d-115">ポリシーのファクト取得コンポーネントの構成</span><span class="sxs-lookup"><span data-stu-id="c9b0d-115">Configure a Fact Retriever for a Policy</span></span>](../core/how-to-configure-a-fact-retriever-for-a-policy.md)  
  
-   [<span data-ttu-id="c9b0d-116">ボキャブラリの作成</span><span class="sxs-lookup"><span data-stu-id="c9b0d-116">Develop Vocabularies</span></span>](../core/how-to-develop-vocabularies.md)  
  
-   [<span data-ttu-id="c9b0d-117">Null および DBNull の処理</span><span class="sxs-lookup"><span data-stu-id="c9b0d-117">Handle Null and DBNull</span></span>](../core/how-to-handle-null-and-dbnull.md)  
  
-   [<span data-ttu-id="c9b0d-118">ビジネス ルールに含まれる同じ種類の複数のオブジェクトを分析する</span><span class="sxs-lookup"><span data-stu-id="c9b0d-118">Analyze Multiple Objects of the Same Type in a Business Rule</span></span>](../core/how-to-analyze-multiple-objects-of-the-same-type-in-a-business-rule.md)  
  
-   [<span data-ttu-id="c9b0d-119">ポリシーのテスト</span><span class="sxs-lookup"><span data-stu-id="c9b0d-119">Testing Policies</span></span>](../core/testing-policies.md)  
  
-   [<span data-ttu-id="c9b0d-120">展開解除ポリシーとボキャブラリを eploy および</span><span class="sxs-lookup"><span data-stu-id="c9b0d-120">eploy and Undeploy Policies and Vocabularies</span></span>](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)  
  
-   [<span data-ttu-id="c9b0d-121">算術演算子</span><span class="sxs-lookup"><span data-stu-id="c9b0d-121">Arithmetic Operators</span></span>](../core/arithmetic-operators.md)  
  
-   [<span data-ttu-id="c9b0d-122">論理演算子</span><span class="sxs-lookup"><span data-stu-id="c9b0d-122">Logical Operators</span></span>](../core/logical-operators.md)  
  
-   [<span data-ttu-id="c9b0d-123">別のポリシーからポリシーを呼び出す</span><span class="sxs-lookup"><span data-stu-id="c9b0d-123">Invoke a Policy from Another Policy</span></span>](../core/invoking-a-policy-from-another-policy.md)  
  
-   [<span data-ttu-id="c9b0d-124">ポリシーから True または False を返す</span><span class="sxs-lookup"><span data-stu-id="c9b0d-124">Return True or False from a Policy</span></span>](../core/how-to-return-true-or-false-from-a-policy.md)
