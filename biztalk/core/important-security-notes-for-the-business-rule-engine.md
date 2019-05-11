---
title: ルール エンジンのビジネスの重要なセキュリティ メモ |Microsoft Docs
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
ms.openlocfilehash: 3d369299dc767a24eb636f495c91f4278fe544e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332191"
---
# <a name="important-security-notes-for-the-business-rule-engine"></a><span data-ttu-id="c8f2a-102">ビジネス ルール エンジンに関する重要なセキュリティ メモ</span><span class="sxs-lookup"><span data-stu-id="c8f2a-102">Important Security Notes for the Business Rule Engine</span></span>
<span data-ttu-id="c8f2a-103">このトピックでは、Microsoft BizTalk Server とセキュリティ リスクを軽減するために行う手順の既知のセキュリティ問題をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-103">This topic summarizes known security issues in Microsoft BizTalk Server and the steps you must take to mitigate the security risks.</span></span>  
  
## <a name="malicious-schema-input-causing-denial-of-service-attack"></a><span data-ttu-id="c8f2a-104">サービス拒否攻撃の原因とする悪意のあるスキーマ入力</span><span class="sxs-lookup"><span data-stu-id="c8f2a-104">Malicious schema input causing Denial of Service attack</span></span>  
 <span data-ttu-id="c8f2a-105">ファクトをアサートするには、各ルールは、ポリシー内でサポートされている型と一致するすべてのオブジェクトに対して検証されます。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-105">While asserting facts, each rule is verified against every object that matches the supported types within a policy.</span></span> <span data-ttu-id="c8f2a-106">セレクターによって渡されたスキーマでは、要素の 1 つをポリシーにルールがあるとします。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-106">Suppose there is a rule in a policy that uses one of the elements in a schema passed by using a selector.</span></span> <span data-ttu-id="c8f2a-107">ここで、セレクターに一致するこの要素/属性がある場合、インスタンスが数千回の繰り返し発生する場合このようなすべてのインスタンスをアサートすると、パフォーマンスが低下し後続可能なサービス拒否 (DoS)。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-107">Now if the instance if this element/attribute that matches the selector is repeated thousands of times, every such instance is asserted, causing performance degradation and subsequent possible Denial of Service (DoS).</span></span>  
  
 <span data-ttu-id="c8f2a-108">この潜在的な問題を軽減するには、ポリシーの実行中に渡されるすべてのあいまいな入力を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-108">To mitigate this potential issue, you need to validate all ambiguous input that is passed while executing a policy.</span></span>  
  
## <a name="ruleset-not-validating-objects-before-asserting-the-facts"></a><span data-ttu-id="c8f2a-109">ファクトをアサートする前にオブジェクトを確認しないルール セット</span><span class="sxs-lookup"><span data-stu-id="c8f2a-109">RuleSet not validating objects before asserting the facts</span></span>  
 <span data-ttu-id="c8f2a-110">ファクトとして渡される任意のスキーマのインスタンス、 **RuleSet**セレクターを使用してルールをアサートする前に、スキーマに対して検証されません。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-110">Any schema instance passed as a fact to the **RuleSet** is not validated against the schema before asserting any rules using selectors.</span></span> <span data-ttu-id="c8f2a-111">ポリシーの実行中に渡されるすべての入力を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-111">You should validate all input that is passed while executing a policy.</span></span>  
  
## <a name="expected-behaviors-of-the-business-rule-composer-when-rulestore-security-is-on"></a><span data-ttu-id="c8f2a-112">RuleStore セキュリティがビジネス ルール作成ツールの動作</span><span class="sxs-lookup"><span data-stu-id="c8f2a-112">Expected behaviors of the Business Rule Composer when RuleStore security is on</span></span>  
 <span data-ttu-id="c8f2a-113">呼び出すことによって、ルール ストアのロールベースのセキュリティ機能を有効にすることができます、 **EnableAuthorization**のメソッド、 **RuleStore**クラス。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-113">You can enable the role-based security feature for the rule store by calling the **EnableAuthorization** method of the **RuleStore** class.</span></span> <span data-ttu-id="c8f2a-114">このセキュリティ機能を有効にすると、ビジネス ルール作成ツールで予期される動作は、します。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-114">When this security feature is enabled, the expected behaviors in the Business Rule Composer are as follows:</span></span>  
  
-   <span data-ttu-id="c8f2a-115">オブジェクト モデルは、ルール セットおよびボキャブラリをユーザーが読み取りアクセス権によって除外されます。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-115">The object model filters out rule sets and vocabularies to which the user does not have read access.</span></span> <span data-ttu-id="c8f2a-116">そのため、ビジネス ルール作成ツールが表示されません。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-116">Therefore, they do not appear in the Business Rule Composer.</span></span>  
  
-   <span data-ttu-id="c8f2a-117">ユーザーは、ポリシーまたはボキャブラリへの書き込みアクセスを持っていない場合いずれかを保存しようと原因がスローされる例外。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-117">If the user does not have write access to a policy or a vocabulary, any save attempt causes an exception to be thrown.</span></span>  
  
## <a name="user-types-for-rule-store-administrator"></a><span data-ttu-id="c8f2a-118">ルール ストア管理者のユーザーの種類</span><span class="sxs-lookup"><span data-stu-id="c8f2a-118">User types for rule store administrator</span></span>  
 <span data-ttu-id="c8f2a-119">ルール ストア管理者は、ルール ストアに保存されるアイテムの認証グループを定義するための権限を持ちます。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-119">The rule store administrator has the privilege to define an authorization group for artifacts saved in the rule store.</span></span> <span data-ttu-id="c8f2a-120">ただし、次の 2 つの種類はルール ストア管理者が所属するユーザーの違いに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-120">However, note the following differences between two types of user to which the rule store administrator can belong:</span></span>  
  
-   <span data-ttu-id="c8f2a-121">ルール ストア管理者が Windows 認証を使用して、ルール ストアを接続するには、Windows ユーザーの場合、ルール ストア管理者は認証グループを持つユーザーが Windows グループまたは Windows ユーザーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-121">When the rule store administrator is a Windows user, which means using Windows authentication to connect the rule store, the rule store administrator can define an authorization group whose user is a Windows group or a Windows user.</span></span>  
  
-   <span data-ttu-id="c8f2a-122">ルール ストア管理者が認証グループを持つユーザーは、Windows グループを定義することはできませんが、ユーザーが認証グループを定義できますルール ストア管理者が、SQL 認証を使用して、ルール ストアを接続するには、SQL ユーザーである場合、Windows ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-122">When the rule store administrator is a SQL user, which means using SQL authentication to connect the rule store, the rule store administrator cannot define an authorization group whose user is a Windows group, but can define an authorization group whose user is a Windows user.</span></span>  
  
## <a name="user-cannot-associate-an-authorization-group-with-an-artifact-without-sufficient-rights"></a><span data-ttu-id="c8f2a-123">ユーザーは認証グループを十分な権限がない場合、成果物に関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-123">User cannot associate an authorization group with an artifact without sufficient rights</span></span>  
 <span data-ttu-id="c8f2a-124">SQL dbo ユーザーでも RE_ADMIN_USERS のメンバーと、アイテムに対する MODIFY_DELETE アクセス許可がないアイテムの作成者は、新しい承認グループを成果物に関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-124">An artifact creator that is neither a SQL dbo user nor a member of RE_ADMIN_USERS, and does not have MODIFY_DELETE permission to an artifact, cannot associate a new authorization group with the artifact.</span></span> <span data-ttu-id="c8f2a-125">次のシナリオでは、この動作の例を示します。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-125">The following scenario is an example of this behavior:</span></span>  
  
1.  <span data-ttu-id="c8f2a-126">ルール セットの作成者は、dbo ではありません、RE_ADMIN_USERS グループ内にないし、MODIFY_DELETE アクセス許可を持たない規則セットを作成した後。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-126">Rule set creator is not dbo, is not in the RE_ADMIN_USERS group, and does not have MODIFY_DELETE permission after the rule set is created.</span></span>  
  
2.  <span data-ttu-id="c8f2a-127">作成者は、ルール セットを作成します。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-127">Creator creates a rule set.</span></span>  
  
3.  <span data-ttu-id="c8f2a-128">RE_ADMIN_USERS グループのメンバーでは、user2 MODIFY_DELETE アクセス許可を持つ認証 AG1 を作成します。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-128">Member of the RE_ADMIN_USERS group creates authorization AG1 with MODIFY_DELETE permission to User2.</span></span>  
  
4.  <span data-ttu-id="c8f2a-129">作成者は、AG1 をルール セットに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-129">Creator associates AG1 with the rule set.</span></span>  
  
5.  <span data-ttu-id="c8f2a-130">ルール ストアの認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-130">Enable the rule store authorization.</span></span>  
  
6.  <span data-ttu-id="c8f2a-131">RE_ADMIN_USERS グループのメンバーでは、user2 READ_EXECUTE アクセス許可を持つ認証 AG2 を作成します。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-131">Member of the RE_ADMIN_USERS group creates authorization AG2 with READ_EXECUTE permission to User2.</span></span>  
  
7.  <span data-ttu-id="c8f2a-132">作成者は、AG2 をルール セットに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-132">Creator associates AG2 with the rule set.</span></span> <span data-ttu-id="c8f2a-133">作成者では、そのためには十分な権限はありませんが、エラー メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-133">Although the creator does not have sufficient right to do so, no error message appears.</span></span>  
  
8.  <span data-ttu-id="c8f2a-134">User2 によるルール セットが失敗した読み取りを試みます。</span><span class="sxs-lookup"><span data-stu-id="c8f2a-134">Attempt to read the rule set by User2 fails.</span></span>