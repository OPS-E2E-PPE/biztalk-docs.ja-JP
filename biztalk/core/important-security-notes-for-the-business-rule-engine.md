---
title: セキュリティに関する注意事項、ビジネス ルール エンジン |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, store administrator
- Business Rule Composer, security
- business rules, security
- Denial of Service attacks
ms.assetid: 8972127a-5569-4b32-bc09-e9265efe9514
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e54a532d33e4f84eb5f1ecea67f957d415344a7c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007067"
---
# <a name="important-security-notes-for-the-business-rule-engine"></a><span data-ttu-id="989a4-102">ビジネス ルール エンジンの重要なセキュリティに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="989a4-102">Important Security Notes for the Business Rule Engine</span></span>
<span data-ttu-id="989a4-103">このトピックでは、Microsoft BizTalk Server とセキュリティ上のリスクを軽減するために行う手順の既知のセキュリティ問題についてまとめます。</span><span class="sxs-lookup"><span data-stu-id="989a4-103">This topic summarizes known security issues in Microsoft BizTalk Server and the steps you must take to mitigate the security risks.</span></span>  
  
## <a name="malicious-schema-input-causing-denial-of-service-attack"></a><span data-ttu-id="989a4-104">サービス拒否の攻撃を発生させる悪質なスキーマ入力</span><span class="sxs-lookup"><span data-stu-id="989a4-104">Malicious schema input causing Denial of Service attack</span></span>  
 <span data-ttu-id="989a4-105">ファクトをアサートすると、各ルールは、ポリシー内のサポートされている種類と一致する各オブジェクトを確認します。</span><span class="sxs-lookup"><span data-stu-id="989a4-105">While asserting facts, each rule is verified against every object that matches the supported types within a policy.</span></span> <span data-ttu-id="989a4-106">セレクターによって渡されたスキーマに含まれる要素のいずれかを使用するポリシー内に、あるルールが存在すると仮定します。</span><span class="sxs-lookup"><span data-stu-id="989a4-106">Suppose there is a rule in a policy that uses one of the elements in a schema passed by using a selector.</span></span> <span data-ttu-id="989a4-107">この要素/属性がセレクターと一致する場合にこのインスタンスが数千回繰り返されると、このようなすべてのインスタンスがアサートされます。この結果、パフォーマンスが低下し、サービスの拒否攻撃 (DoS) が起こる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="989a4-107">Now if the instance if this element/attribute that matches the selector is repeated thousands of times, every such instance is asserted, causing performance degradation and subsequent possible Denial of Service (DoS).</span></span>  
  
 <span data-ttu-id="989a4-108">この潜在的な問題を緩和するには、ポリシーの実行中に渡されるあいまいな入力すべてを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="989a4-108">To mitigate this potential issue, you need to validate all ambiguous input that is passed while executing a policy.</span></span>  
  
## <a name="ruleset-not-validating-objects-before-asserting-the-facts"></a><span data-ttu-id="989a4-109">ファクトをアサートする前にオブジェクトを確認しないルール セット</span><span class="sxs-lookup"><span data-stu-id="989a4-109">RuleSet not validating objects before asserting the facts</span></span>  
 <span data-ttu-id="989a4-110">ファクトとして渡された任意のスキーマのインスタンス、 **RuleSet**セレクターを使用してルールをアサートする前に、スキーマに対して検証されません。</span><span class="sxs-lookup"><span data-stu-id="989a4-110">Any schema instance passed as a fact to the **RuleSet** is not validated against the schema before asserting any rules using selectors.</span></span> <span data-ttu-id="989a4-111">ポリシーの実行中に渡されるすべての入力を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="989a4-111">You should validate all input that is passed while executing a policy.</span></span>  
  
## <a name="expected-behaviors-of-the-business-rule-composer-when-rulestore-security-is-on"></a><span data-ttu-id="989a4-112">RuleStore セキュリティが有効な場合のビジネス ルール作成ツールの正常な動作</span><span class="sxs-lookup"><span data-stu-id="989a4-112">Expected behaviors of the Business Rule Composer when RuleStore security is on</span></span>  
 <span data-ttu-id="989a4-113">呼び出して、ルール ストアのロールベースのセキュリティ機能を有効にすることができます、 **EnableAuthorization**のメソッド、 **RuleStore**クラスです。</span><span class="sxs-lookup"><span data-stu-id="989a4-113">You can enable the role-based security feature for the rule store by calling the **EnableAuthorization** method of the **RuleStore** class.</span></span> <span data-ttu-id="989a4-114">このセキュリティ機能が有効な場合、ビジネス ルール作成ツールは、次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="989a4-114">When this security feature is enabled, the expected behaviors in the Business Rule Composer are as follows:</span></span>  
  
-   <span data-ttu-id="989a4-115">オブジェクト モデルは、ユーザーの読み取りアクセス権限がないルール セットおよびボキャブラリを除外します。</span><span class="sxs-lookup"><span data-stu-id="989a4-115">The object model filters out rule sets and vocabularies to which the user does not have read access.</span></span> <span data-ttu-id="989a4-116">このため、これらはビジネス ルール作成ツールに表示されません。</span><span class="sxs-lookup"><span data-stu-id="989a4-116">Therefore, they do not appear in the Business Rule Composer.</span></span>  
  
-   <span data-ttu-id="989a4-117">ポリシーまたはボキャブラリに対する書き込みアクセス権限を持たないユーザーがそれらを保存しようとすると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="989a4-117">If the user does not have write access to a policy or a vocabulary, any save attempt causes an exception to be thrown.</span></span>  
  
## <a name="user-types-for-rule-store-administrator"></a><span data-ttu-id="989a4-118">ルール ストア管理者のユーザーの種類</span><span class="sxs-lookup"><span data-stu-id="989a4-118">User types for rule store administrator</span></span>  
 <span data-ttu-id="989a4-119">ルール ストア管理者には、ルール ストアに保存されるアイテムの認証グループを定義する権限があります。</span><span class="sxs-lookup"><span data-stu-id="989a4-119">The rule store administrator has the privilege to define an authorization group for artifacts saved in the rule store.</span></span> <span data-ttu-id="989a4-120">ただし、ルール ストア管理者が属する次の 2 つの種類のユーザーの違いに注意してください。</span><span class="sxs-lookup"><span data-stu-id="989a4-120">However, note the following differences between two types of user to which the rule store administrator can belong:</span></span>  
  
-   <span data-ttu-id="989a4-121">ルール ストア管理者が Windows ユーザーの場合 (つまり、Windows 認証でルール ストアを接続する場合)、ルール ストア管理者は、ユーザーが Windows グループまたは Windows ユーザーとなる認証グループを定義できます。</span><span class="sxs-lookup"><span data-stu-id="989a4-121">When the rule store administrator is a Windows user, which means using Windows authentication to connect the rule store, the rule store administrator can define an authorization group whose user is a Windows group or a Windows user.</span></span>  
  
-   <span data-ttu-id="989a4-122">ルール ストア管理者が SQL ユーザーの場合 (つまり、SQL 認証でルール ストアを接続する場合)、ルール ストア管理者は、ユーザーが Windows グループとなる認証グループを定義できません。ただし、ユーザーが Windows ユーザーとなる認証グループは定義できます。</span><span class="sxs-lookup"><span data-stu-id="989a4-122">When the rule store administrator is a SQL user, which means using SQL authentication to connect the rule store, the rule store administrator cannot define an authorization group whose user is a Windows group, but can define an authorization group whose user is a Windows user.</span></span>  
  
## <a name="user-cannot-associate-an-authorization-group-with-an-artifact-without-sufficient-rights"></a><span data-ttu-id="989a4-123">十分な権限を持たないユーザーは認証グループをアイテムに関連付けられない</span><span class="sxs-lookup"><span data-stu-id="989a4-123">User cannot associate an authorization group with an artifact without sufficient rights</span></span>  
 <span data-ttu-id="989a4-124">SQL dbo ユーザーでも RE_ADMIN_USERS のメンバーでもなく、アイテムに対する MODIFY_DELETE アクセス許可のないアイテムの作成者は、新しい認証グループをアイテムに関連付けることができません。</span><span class="sxs-lookup"><span data-stu-id="989a4-124">An artifact creator that is neither a SQL dbo user nor a member of RE_ADMIN_USERS, and does not have MODIFY_DELETE permission to an artifact, cannot associate a new authorization group with the artifact.</span></span> <span data-ttu-id="989a4-125">次のシナリオは、この例を示しています。</span><span class="sxs-lookup"><span data-stu-id="989a4-125">The following scenario is an example of this behavior:</span></span>  
  
1.  <span data-ttu-id="989a4-126">ルール セットの作成者は、dbo ユーザーでも RE_ADMIN_USERS グループのユーザーでもありません。また、ルール セットを作成した後の MODIFY_DELETE アクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="989a4-126">Rule set creator is not dbo, is not in the RE_ADMIN_USERS group, and does not have MODIFY_DELETE permission after the rule set is created.</span></span>  
  
2.  <span data-ttu-id="989a4-127">作成者がルール セットを作成します。</span><span class="sxs-lookup"><span data-stu-id="989a4-127">Creator creates a rule set.</span></span>  
  
3.  <span data-ttu-id="989a4-128">RE_ADMIN_USERS グループのメンバーが、MODIFY_DELETE アクセス許可を持つ認証 AG1 を User2 に対して作成します。</span><span class="sxs-lookup"><span data-stu-id="989a4-128">Member of the RE_ADMIN_USERS group creates authorization AG1 with MODIFY_DELETE permission to User2.</span></span>  
  
4.  <span data-ttu-id="989a4-129">作成者が、AG1 をルール セットに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="989a4-129">Creator associates AG1 with the rule set.</span></span>  
  
5.  <span data-ttu-id="989a4-130">ルール ストアの認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="989a4-130">Enable the rule store authorization.</span></span>  
  
6.  <span data-ttu-id="989a4-131">RE_ADMIN_USERS グループのメンバーが、READ_EXECUTE アクセス許可を持つ認証 AG2 を User2 に対して作成します。</span><span class="sxs-lookup"><span data-stu-id="989a4-131">Member of the RE_ADMIN_USERS group creates authorization AG2 with READ_EXECUTE permission to User2.</span></span>  
  
7.  <span data-ttu-id="989a4-132">作成者が、AG2 をルール セットに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="989a4-132">Creator associates AG2 with the rule set.</span></span> <span data-ttu-id="989a4-133">作成者にはこの操作を行う十分な権限がありませんが、エラー メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="989a4-133">Although the creator does not have sufficient right to do so, no error message appears.</span></span>  
  
8.  <span data-ttu-id="989a4-134">User2 によるルール セットの読み取りが失敗します。</span><span class="sxs-lookup"><span data-stu-id="989a4-134">Attempt to read the rule set by User2 fails.</span></span>