---
title: "ルール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, actions
- Business Rules Engine, business rules
- business rules, about business rules
- business rules, conditions
- business rules, facts
- business rules
ms.assetid: b288dd07-33f1-42fe-bbfb-02674ef3b3ca
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35f398cf98181d17833be79fbe9d282e8515e052
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="rules"></a><span data-ttu-id="b8eef-102">ルール</span><span class="sxs-lookup"><span data-stu-id="b8eef-102">Rules</span></span>
<span data-ttu-id="b8eef-103">ビジネス ルールはビジネス プロセスの運営を管理する宣言型ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="b8eef-103">Business rules are declarative statements that govern the conduct of business processes.</span></span> <span data-ttu-id="b8eef-104">ルールは条件とアクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="b8eef-104">A rule consists of a condition and actions.</span></span> <span data-ttu-id="b8eef-105">条件を評価するに評価されると、 **true**、ルール エンジンは、1 つまたは複数のアクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="b8eef-105">The condition is evaluated, and if it evaluates to **true**, the rule engine initiates one or more actions.</span></span>  
  
 <span data-ttu-id="b8eef-106">ビジネス ルール フレームワークのルールは次の形式で定義されます。</span><span class="sxs-lookup"><span data-stu-id="b8eef-106">Rules in the Business Rules Framework are defined by using the following format:</span></span>  
  
 <span data-ttu-id="b8eef-107">IF`condition`し、`action`</span><span class="sxs-lookup"><span data-stu-id="b8eef-107">IF`condition` THEN`action`</span></span>  
  
 <span data-ttu-id="b8eef-108">次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8eef-108">Consider the following example:</span></span>  
  
 <span data-ttu-id="b8eef-109">金額が使用可能な資金以下である</span><span class="sxs-lookup"><span data-stu-id="b8eef-109">IF amount is less than or equal to available funds</span></span>  
  
 <span data-ttu-id="b8eef-110">取引を行い、レシートを印刷する</span><span class="sxs-lookup"><span data-stu-id="b8eef-110">THEN conduct transaction and print receipt</span></span>  
  
 <span data-ttu-id="b8eef-111">このルールはビジネス ロジックを適用して、データまたはファクトの 2 つの金額、ここでは取り引き金額と使用可能な資金を比較し、取り引きを行うかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="b8eef-111">This rule determines whether a transaction will be conducted by applying business logic, in the form of a comparison of two monetary values, to data or facts, in the form of a transaction amount and available funds.</span></span>  
  
 <span data-ttu-id="b8eef-112">ビジネス ルールの作成、変更、バージョン管理、展開にはビジネス ルール作成ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8eef-112">You can use the Business Rule Composer to create, modify, version, and deploy business rules.</span></span> <span data-ttu-id="b8eef-113">プログラムを記述する方法もあります。</span><span class="sxs-lookup"><span data-stu-id="b8eef-113">Alternatively, you can perform the preceding tasks programmatically.</span></span>  
  
## <a name="conditions"></a><span data-ttu-id="b8eef-114">[条件]</span><span class="sxs-lookup"><span data-stu-id="b8eef-114">Conditions</span></span>  
 <span data-ttu-id="b8eef-115">条件はファクトについての述語から成る true/false (ブール値) 式です。</span><span class="sxs-lookup"><span data-stu-id="b8eef-115">A condition is a true/false (Boolean) expression that consists of one or more predicates that are applied to facts.</span></span>  
  
 <span data-ttu-id="b8eef-116">この例では、述語**以下に**ファクトに適用される**量**と**使用可能な資金**です。</span><span class="sxs-lookup"><span data-stu-id="b8eef-116">In our example, the predicate **less than or equal to** is applied to the facts **amount** and **available funds**.</span></span> <span data-ttu-id="b8eef-117">この条件は常にいずれかの評価**true**または**false**です。</span><span class="sxs-lookup"><span data-stu-id="b8eef-117">This condition will always evaluate to either **true** or **false**.</span></span>  
  
 <span data-ttu-id="b8eef-118">論理演算子と述語を組み合わせることができます**AND**、**または**、および**いない**フォーム可能性のある非常に大きく、論理式ですが評価が常にいずれか**true**または**false**です。</span><span class="sxs-lookup"><span data-stu-id="b8eef-118">Predicates can be combined with the logical operators **AND**, **OR**, and **NOT** to form a logical expression that is potentially quite large, but will always evaluate to either **true** or **false**.</span></span>  
  
## <a name="actions"></a><span data-ttu-id="b8eef-119">アクション</span><span class="sxs-lookup"><span data-stu-id="b8eef-119">Actions</span></span>  
 <span data-ttu-id="b8eef-120">アクションは条件評価の機能的な結果です。</span><span class="sxs-lookup"><span data-stu-id="b8eef-120">Actions are the functional consequences of condition evaluation.</span></span> <span data-ttu-id="b8eef-121">ルールの条件が満たされると、対応するアクションが開始されます。</span><span class="sxs-lookup"><span data-stu-id="b8eef-121">If a rule condition is met, a corresponding action or actions are initiated.</span></span>  
  
 <span data-ttu-id="b8eef-122">例では、"取り引きを行う" と "レシートを印刷する" というアクションが、条件 (金額が使用可能な資金以下である) が true の場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="b8eef-122">In our example, "conduct transaction" and "print receipt" are actions that are carried out when, and only when, the condition (in this case, "IF amount is less than or equal to available funds") is true.</span></span>  
  
 <span data-ttu-id="b8eef-123">ビジネス ルール フレームワークでは、アクションはメソッドの呼び出しやオブジェクトのプロパティ設定、XML ドキュメントやデータベース テーブルに対する集合演算という形で表現されます。</span><span class="sxs-lookup"><span data-stu-id="b8eef-123">Actions are represented in the Business Rules Framework by invoking methods or setting properties on objects, or by performing set operations on XML documents or database tables.</span></span>  
  
## <a name="facts"></a><span data-ttu-id="b8eef-124">ファクト</span><span class="sxs-lookup"><span data-stu-id="b8eef-124">Facts</span></span>  
 <span data-ttu-id="b8eef-125">ファクトはルールを適用するデータです。</span><span class="sxs-lookup"><span data-stu-id="b8eef-125">Facts are the data upon which rules operate.</span></span> <span data-ttu-id="b8eef-126">この例では、"金額" と "使用可能な資金" がファクトです。</span><span class="sxs-lookup"><span data-stu-id="b8eef-126">In our example, "amount" and "available funds" are facts.</span></span> <span data-ttu-id="b8eef-127">詳細については、次を参照してください。[ファクト](../core/facts.md)です。</span><span class="sxs-lookup"><span data-stu-id="b8eef-127">For more information, see [Facts](../core/facts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8eef-128">参照</span><span class="sxs-lookup"><span data-stu-id="b8eef-128">See Also</span></span>  
 [<span data-ttu-id="b8eef-129">ポリシーとルールを作成する方法</span><span class="sxs-lookup"><span data-stu-id="b8eef-129">How to Create Policies and Rules</span></span>](../core/how-to-create-policies-and-rules.md)