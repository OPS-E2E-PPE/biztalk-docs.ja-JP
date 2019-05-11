---
title: ルール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, actions
- Business Rules Engine, business rules
- business rules, about business rules
- business rules, conditions
- business rules, facts
- business rules
ms.assetid: b288dd07-33f1-42fe-bbfb-02674ef3b3ca
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d51492beb69b2789100f7328e84323cfff7ae2c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254623"
---
# <a name="rules"></a><span data-ttu-id="c3b22-102">ルール</span><span class="sxs-lookup"><span data-stu-id="c3b22-102">Rules</span></span>
<span data-ttu-id="c3b22-103">ビジネス ルールは、ビジネス プロセスの運営を管理する宣言ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="c3b22-103">Business rules are declarative statements that govern the conduct of business processes.</span></span> <span data-ttu-id="c3b22-104">ルールは、条件とアクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="c3b22-104">A rule consists of a condition and actions.</span></span> <span data-ttu-id="c3b22-105">条件が評価されに評価されると、 **true**、ルール エンジンは、1 つまたは複数のアクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="c3b22-105">The condition is evaluated, and if it evaluates to **true**, the rule engine initiates one or more actions.</span></span>  
  
 <span data-ttu-id="c3b22-106">ビジネス ルール フレームワークでのルールは、次の形式を使用して定義されます。</span><span class="sxs-lookup"><span data-stu-id="c3b22-106">Rules in the Business Rules Framework are defined by using the following format:</span></span>  
  
 <span data-ttu-id="c3b22-107">IF`condition`し`action`</span><span class="sxs-lookup"><span data-stu-id="c3b22-107">IF`condition` THEN`action`</span></span>  
  
 <span data-ttu-id="c3b22-108">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c3b22-108">Consider the following example:</span></span>  
  
 <span data-ttu-id="c3b22-109">IF 金額が使用可能な資金以下</span><span class="sxs-lookup"><span data-stu-id="c3b22-109">IF amount is less than or equal to available funds</span></span>  
  
 <span data-ttu-id="c3b22-110">取引を行い、レシートを印刷し、</span><span class="sxs-lookup"><span data-stu-id="c3b22-110">THEN conduct transaction and print receipt</span></span>  
  
 <span data-ttu-id="c3b22-111">このルールは、データまたはトランザクションの量と使用可能な資金の形式で、ファクトの 2 つの通貨値の比較の形式でのビジネス ロジックを適用することで、トランザクションを実施するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="c3b22-111">This rule determines whether a transaction will be conducted by applying business logic, in the form of a comparison of two monetary values, to data or facts, in the form of a transaction amount and available funds.</span></span>  
  
 <span data-ttu-id="c3b22-112">作成、変更、バージョンについては、ビジネス ルール作成ツールを使用して、ビジネス ルールを展開できます。</span><span class="sxs-lookup"><span data-stu-id="c3b22-112">You can use the Business Rule Composer to create, modify, version, and deploy business rules.</span></span> <span data-ttu-id="c3b22-113">前のタスクをプログラムで実行することができます。</span><span class="sxs-lookup"><span data-stu-id="c3b22-113">Alternatively, you can perform the preceding tasks programmatically.</span></span>  
  
## <a name="conditions"></a><span data-ttu-id="c3b22-114">条件</span><span class="sxs-lookup"><span data-stu-id="c3b22-114">Conditions</span></span>  
 <span data-ttu-id="c3b22-115">条件は、true または false のファクトに適用される 1 つまたは複数の述語から成る (ブール) 式です。</span><span class="sxs-lookup"><span data-stu-id="c3b22-115">A condition is a true/false (Boolean) expression that consists of one or more predicates that are applied to facts.</span></span>  
  
 <span data-ttu-id="c3b22-116">この例では、述語**に等しいまたはそれよりも小さい**ファクトに適用される**量**と**使用可能な資金**します。</span><span class="sxs-lookup"><span data-stu-id="c3b22-116">In our example, the predicate **less than or equal to** is applied to the facts **amount** and **available funds**.</span></span> <span data-ttu-id="c3b22-117">この条件がいずれかに評価されることは常に**true**または**false**します。</span><span class="sxs-lookup"><span data-stu-id="c3b22-117">This condition will always evaluate to either **true** or **false**.</span></span>  
  
 <span data-ttu-id="c3b22-118">論理演算子と述語を組み合わせることができます**AND**、**または**、および**いない**は可能性のある非常に大きく、論理式は常に評価するフォームにいずれか**true**または**false**します。</span><span class="sxs-lookup"><span data-stu-id="c3b22-118">Predicates can be combined with the logical operators **AND**, **OR**, and **NOT** to form a logical expression that is potentially quite large, but will always evaluate to either **true** or **false**.</span></span>  
  
## <a name="actions"></a><span data-ttu-id="c3b22-119">アクション</span><span class="sxs-lookup"><span data-stu-id="c3b22-119">Actions</span></span>  
 <span data-ttu-id="c3b22-120">アクションは、条件の評価の機能的な結果です。</span><span class="sxs-lookup"><span data-stu-id="c3b22-120">Actions are the functional consequences of condition evaluation.</span></span> <span data-ttu-id="c3b22-121">ルールの条件が満たされた場合は、対応するアクションが開始されます。</span><span class="sxs-lookup"><span data-stu-id="c3b22-121">If a rule condition is met, a corresponding action or actions are initiated.</span></span>  
  
 <span data-ttu-id="c3b22-122">この例では「取引を行う」と「レシートを印刷」は状況、および条件 (この場合は、"量が少ない場合に使用可能な資金以下") の指定が true の場合のみが実行されるアクションです。</span><span class="sxs-lookup"><span data-stu-id="c3b22-122">In our example, "conduct transaction" and "print receipt" are actions that are carried out when, and only when, the condition (in this case, "IF amount is less than or equal to available funds") is true.</span></span>  
  
 <span data-ttu-id="c3b22-123">アクションは、メソッドの呼び出しによって、オブジェクトのプロパティを設定または XML ドキュメントやデータベース テーブルに対する集合演算によって、ビジネス ルール フレームワークで表現されます。</span><span class="sxs-lookup"><span data-stu-id="c3b22-123">Actions are represented in the Business Rules Framework by invoking methods or setting properties on objects, or by performing set operations on XML documents or database tables.</span></span>  
  
## <a name="facts"></a><span data-ttu-id="c3b22-124">ファクト</span><span class="sxs-lookup"><span data-stu-id="c3b22-124">Facts</span></span>  
 <span data-ttu-id="c3b22-125">ファクトは、ルールを適用するデータです。</span><span class="sxs-lookup"><span data-stu-id="c3b22-125">Facts are the data upon which rules operate.</span></span> <span data-ttu-id="c3b22-126">この例では、「金額」と「使用可能な資金」がファクトです。</span><span class="sxs-lookup"><span data-stu-id="c3b22-126">In our example, "amount" and "available funds" are facts.</span></span> <span data-ttu-id="c3b22-127">詳細については、次を参照してください。[ファクト](../core/facts.md)します。</span><span class="sxs-lookup"><span data-stu-id="c3b22-127">For more information, see [Facts](../core/facts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3b22-128">参照</span><span class="sxs-lookup"><span data-stu-id="c3b22-128">See Also</span></span>  
 [<span data-ttu-id="c3b22-129">ポリシーとルールを作成する方法</span><span class="sxs-lookup"><span data-stu-id="c3b22-129">How to Create Policies and Rules</span></span>](../core/how-to-create-policies-and-rules.md)