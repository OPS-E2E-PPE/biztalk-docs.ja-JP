---
title: "ビジネス ルール作成ツールを使用してビジネス ルールの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, business rules
- business rules, creating
ms.assetid: 0600a2b2-36a2-4496-8ba1-c5f6e2fa4760
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b5b1281acab139159dd837f63cf80af56d388c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-business-rules-using-the-business-rule-composer"></a><span data-ttu-id="aca91-102">ビジネス ルール作成ツールを使用してビジネス ルールの作成</span><span class="sxs-lookup"><span data-stu-id="aca91-102">Creating Business Rules Using the Business Rule Composer</span></span>
<span data-ttu-id="aca91-103">ビジネス ルール作成ツールを使用すると、1 つ以上のビジネス ルールを持つビジネス ポリシーを作成し、作成したポリシーを展開できます。</span><span class="sxs-lookup"><span data-stu-id="aca91-103">The Business Rule Composer allows you to create business policies with one or more business rules, and it allows you to deploy these policies.</span></span> <span data-ttu-id="aca91-104">また、ファクト (XML、データベース、および .NET) を参照して、ビジネス ルールでファクトを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="aca91-104">It also allows you to browse for facts (XML, database, and .NET), and use the facts in business rules.</span></span> <span data-ttu-id="aca91-105">さらに、ファクトに基づくビジネス ボキャブラリを作成し、作成したボキャブラリをビジネス ルールで使用できます。</span><span class="sxs-lookup"><span data-stu-id="aca91-105">In addition, it allows you to create business vocabularies based on facts, and to use the vocabularies in business rules.</span></span>  
  
 <span data-ttu-id="aca91-106">ここでは、ビジネス ルール作成ツールを使用してビジネス ルールを作成する場合の、タスク固有の情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="aca91-106">This section provides task-specific information about using the Business Rule Composer to create business rules.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aca91-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="aca91-107">In This Section</span></span>  
  
-   [<span data-ttu-id="aca91-108">ビジネス ルール作成ツールを起動し、ポリシーの読み込みする方法</span><span class="sxs-lookup"><span data-stu-id="aca91-108">How to Start the Business Rule Composer and Load a Policy</span></span>](../core/how-to-start-the-business-rule-composer-and-load-a-policy.md)  
  
-   [<span data-ttu-id="aca91-109">ビジネス ルール作成ツールの Windows</span><span class="sxs-lookup"><span data-stu-id="aca91-109">Windows of the Business Rule Composer</span></span>](../core/windows-of-the-business-rule-composer.md)  
  
-   [<span data-ttu-id="aca91-110">ファクトの選択</span><span class="sxs-lookup"><span data-stu-id="aca91-110">Selecting Facts</span></span>](../core/selecting-facts.md)  
  
-   [<span data-ttu-id="aca91-111">ポリシーとルールを作成する方法</span><span class="sxs-lookup"><span data-stu-id="aca91-111">How to Create Policies and Rules</span></span>](../core/how-to-create-policies-and-rules.md)  
  
-   [<span data-ttu-id="aca91-112">規則を変更する方法</span><span class="sxs-lookup"><span data-stu-id="aca91-112">How to Modify Rules</span></span>](../core/how-to-modify-rules.md)  
  
-   [<span data-ttu-id="aca91-113">ポリシー バージョンを管理する方法</span><span class="sxs-lookup"><span data-stu-id="aca91-113">How to Maintain Policy Versions</span></span>](../core/how-to-maintain-policy-versions.md)  
  
-   [<span data-ttu-id="aca91-114">ポリシーのファクト取得コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="aca91-114">How to Configure a Fact Retriever for a Policy</span></span>](../core/how-to-configure-a-fact-retriever-for-a-policy.md)  
  
-   [<span data-ttu-id="aca91-115">ボキャブラリを作成する方法</span><span class="sxs-lookup"><span data-stu-id="aca91-115">How to Develop Vocabularies</span></span>](../core/how-to-develop-vocabularies.md)  
  
-   [<span data-ttu-id="aca91-116">Null および DBNull を処理する方法</span><span class="sxs-lookup"><span data-stu-id="aca91-116">How to Handle Null and DBNull</span></span>](../core/how-to-handle-null-and-dbnull.md)  
  
-   [<span data-ttu-id="aca91-117">ビジネス ルールで同じ種類の複数のオブジェクトを分析する方法</span><span class="sxs-lookup"><span data-stu-id="aca91-117">How to Analyze Multiple Objects of the Same Type in a Business Rule</span></span>](../core/how-to-analyze-multiple-objects-of-the-same-type-in-a-business-rule.md)  
  
-   [<span data-ttu-id="aca91-118">ポリシーのテスト</span><span class="sxs-lookup"><span data-stu-id="aca91-118">Testing Policies</span></span>](../core/testing-policies.md)  
  
-   [<span data-ttu-id="aca91-119">展開およびポリシーとボキャブラリを展開解除する方法</span><span class="sxs-lookup"><span data-stu-id="aca91-119">How to Deploy and Undeploy Policies and Vocabularies</span></span>](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)  
  
-   [<span data-ttu-id="aca91-120">算術演算子</span><span class="sxs-lookup"><span data-stu-id="aca91-120">Arithmetic Operators</span></span>](../core/arithmetic-operators.md)  
  
-   [<span data-ttu-id="aca91-121">論理演算子</span><span class="sxs-lookup"><span data-stu-id="aca91-121">Logical Operators</span></span>](../core/logical-operators.md)  
  
-   [<span data-ttu-id="aca91-122">ポリシー別のポリシーからを呼び出す</span><span class="sxs-lookup"><span data-stu-id="aca91-122">Invoking a Policy from Another Policy</span></span>](../core/invoking-a-policy-from-another-policy.md)  
  
-   [<span data-ttu-id="aca91-123">ポリシーから True または False を返す方法</span><span class="sxs-lookup"><span data-stu-id="aca91-123">How to Return True or False from a Policy</span></span>](../core/how-to-return-true-or-false-from-a-policy.md)