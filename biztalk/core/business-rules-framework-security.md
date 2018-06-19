---
title: ビジネス ルール フレームワークのセキュリティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, code samples
- security, business rules
- artifacts, security
- security, artifacts
- business rules, security
ms.assetid: 86582d3a-259e-47f2-9f72-8dbbe0051503
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2c3a38190d242c85b134a791a8c2cd05c208050
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232690"
---
# <a name="business-rules-framework-security"></a><span data-ttu-id="7d955-102">ビジネス ルール フレームワークのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="7d955-102">Business Rules Framework Security</span></span>
<span data-ttu-id="7d955-103">ビジネス ルール エンジンは、ホスト アプリケーションのセキュリティ コンテキストで動作します。</span><span class="sxs-lookup"><span data-stu-id="7d955-103">The Business Rule Engine operates in the security context of the hosting application.</span></span> <span data-ttu-id="7d955-104">実行中にルール エンジン インスタンスの id は、スレッド コンテキストを呼び出す、 **Policy.Execute**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="7d955-104">The identity of the rule engine instance during execution is that of the thread context that invokes the **Policy.Execute** method.</span></span>  
  
## <a name="default-security-configuration"></a><span data-ttu-id="7d955-105">既定のセキュリティ構成</span><span class="sxs-lookup"><span data-stu-id="7d955-105">Default security configuration</span></span>  
 <span data-ttu-id="7d955-106">Microsoft をインストールするときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2、Microsoft Windows グループは、default、管理者およびユーザーによって作成されます:「BizTalk Server 管理者」と"BizTalk Application Users"</span><span class="sxs-lookup"><span data-stu-id="7d955-106">When you install Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], two Microsoft Windows groups are created by default, one for administrators and one for users: "BizTalk Server Administrators" and "BizTalk Application Users."</span></span> <span data-ttu-id="7d955-107">BTS_ADMIN_USERS および BTS_HOST_USERS は、それぞれ SQL ロールの RE_ADMIN_USERS および RE_HOST_USERS のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="7d955-107">These two Windows groups are members of BTS_ADMIN_USERS and BTS_HOST_USERS SQL Roles which are members of RE_ADMIN_USERS and RE_HOST_USERS SQL Roles respectively.</span></span>  
  
 <span data-ttu-id="7d955-108">ルール ストアが作成されるたびに既定の SQL ロールが作成されます: BTS_ADMIN_USERS、BTS_HOST_USERS、RE_ADMIN_USERS および RE_HOST_USERS です。</span><span class="sxs-lookup"><span data-stu-id="7d955-108">The default SQL roles are created whenever a rule store is created: BTS_ADMIN_USERS, BTS_HOST_USERS, RE_ADMIN_USERS and RE_HOST_USERS.</span></span>  
  
|<span data-ttu-id="7d955-109">既定の Windows グループ</span><span class="sxs-lookup"><span data-stu-id="7d955-109">Default Windows groups</span></span>|<span data-ttu-id="7d955-110">SQL ロール</span><span class="sxs-lookup"><span data-stu-id="7d955-110">SQL roles</span></span>|  
|----------------------------|---------------|  
|<span data-ttu-id="7d955-111">BizTalk Server 管理者</span><span class="sxs-lookup"><span data-stu-id="7d955-111">BizTalk Server Administrators</span></span>|<span data-ttu-id="7d955-112">RE_ADMIN_USERS</span><span class="sxs-lookup"><span data-stu-id="7d955-112">RE_ADMIN_USERS</span></span>|  
|<span data-ttu-id="7d955-113">BizTalk Application Users</span><span class="sxs-lookup"><span data-stu-id="7d955-113">BizTalk Application Users</span></span>|<span data-ttu-id="7d955-114">RE_HOST_USERS</span><span class="sxs-lookup"><span data-stu-id="7d955-114">RE_HOST_USERS</span></span>|  
  
 <span data-ttu-id="7d955-115">RE_ADMIN_USERS ロールのユーザーだけが、展開とエンティティ アクセスの保護に関する構成テーブルを更新するストアド プロシージャを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7d955-115">Only users in the RE_ADMIN_USERS role can execute the stored procedures that update the deployment and entity access protection configuration tables.</span></span> <span data-ttu-id="7d955-116">つまり、ルール エンジンの管理者によってのみ、展開、展開解除、および保護の構成が行われます。</span><span class="sxs-lookup"><span data-stu-id="7d955-116">This means that the deployment, undeployment, and protection configuration are all done only by rule engine administrators.</span></span> <span data-ttu-id="7d955-117">RE_HOST_USERS ロールのユーザーは、SQL ルール ストアの他のストアド プロシージャを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7d955-117">Users in the RE_HOST_USERS role can execute the other stored procedures in the SQL rule store.</span></span>  
  
 <span data-ttu-id="7d955-118">ルール エンジンのインストールの順序に関係なく、データベース アクセスがまだ許可されていない場合に、ルール エンジン構成のプロセスは、ルール エンジン更新サービスのアカウント メンバーシップに RE_HOST_USERS SQL ロールを与えます。</span><span class="sxs-lookup"><span data-stu-id="7d955-118">Regardless of the order of installation of the rule engine, the rule engine configuration process grants the Rule Engine Update Service account membership to the RE_HOST_USERS SQL role, if it does not already have database access.</span></span> <span data-ttu-id="7d955-119">ただし、BizTalk を最初にインストールした後にルール エンジンをインストールすると、ホストの作成が既に行われているため、ホスト固有のユーザー グループは、ルール エンジン データベースの BTS_HOST_USERS SQL ロールに追加されません。</span><span class="sxs-lookup"><span data-stu-id="7d955-119">However, if the rule engine is installed after the initial BizTalk installation the BizTalk, host-specific users group is not added to the BTS_HOST_USERS SQL role in the Rule Engine database because host creation has already been completed.</span></span> <span data-ttu-id="7d955-120">この手順を手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d955-120">You need to perform this step manually.</span></span>  
  
## <a name="artifact-level-security"></a><span data-ttu-id="7d955-121">アイテム レベルのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="7d955-121">Artifact level security</span></span>  
 <span data-ttu-id="7d955-122">既定のセキュリティ構成に加えて、ビジネス ルール エンジンも成果物でセキュリティを提供、ポリシーおよびボキャブラリ レベル。</span><span class="sxs-lookup"><span data-stu-id="7d955-122">In addition to the default security configuration, the Business Rule Engine can also provide security at the artifact—policy and vocabulary level.</span></span>  
  
 <span data-ttu-id="7d955-123">各ポリシーのバージョンまたは各ボキャブラリのバージョンには、関連する 1 つ以上の認証グループがあります。</span><span class="sxs-lookup"><span data-stu-id="7d955-123">Each policy or vocabulary version has one or more authorization groups associated with it.</span></span> <span data-ttu-id="7d955-124">認証グループは、Microsoft Windows ユーザー、SQL ユーザー、SQL ロール、および Windows グループの名前付きのリストです。それぞれ特定のアクセス レベルを持っています。</span><span class="sxs-lookup"><span data-stu-id="7d955-124">An Authorization group is a named list of Microsoft Windows users, SQL users, SQL roles, and Windows groups, with a particular access level on each type.</span></span>  
  
 <span data-ttu-id="7d955-125">新しいポリシーまたはボキャブラリがルール ストアに作成されると、既定で、ポリシーまたはボキャブラリを作成したユーザーとルール エンジン管理者だけが、読み取り/実行および変更/削除の処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7d955-125">When a new policy or vocabulary is created in the rule store, only the user who created it and the rule engine administrator have both read/execute and modify/delete access by default.</span></span> <span data-ttu-id="7d955-126">ルール エンジン管理者がある (プロセスは、ユーザーの資格情報で動作) ユーザーは、アクセス レベル、または別の操作を実行するための権限を構成することができます: 読み取り/実行、変更/削除、完全なアクセス許可、またはアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="7d955-126">The rule engine administrator can configure which users (processes operate under user credentials) have the access level, or rights, to perform different operations—read/execute, modify/delete, full permission, or no permission.</span></span>  
  
 <span data-ttu-id="7d955-127">既定では、アイテム固有のセキュリティは無効です。</span><span class="sxs-lookup"><span data-stu-id="7d955-127">Artifact specific security is not enabled by default.</span></span> <span data-ttu-id="7d955-128">アイテム レベルのセキュリティは、現在、ユーザー インターフェイスを通じては設定できません。</span><span class="sxs-lookup"><span data-stu-id="7d955-128">Setting artifact level security is not currently available through the user interface.</span></span> <span data-ttu-id="7d955-129">ただし、ビジネス ルール エンジン管理者の資格情報を使用して、プログラムによって設定できます。</span><span class="sxs-lookup"><span data-stu-id="7d955-129">However, it can be set programmatically with the Business Rule Engine administrator credential.</span></span> <span data-ttu-id="7d955-130">次のコードは、新しい認証を作成してグループをルール セットに関連付ける方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7d955-130">The following code fragment shows how to create a new authorization and associate the group to a rule set.</span></span>  
  
```  
RuleSet rs;  
string RSName;     
  
// Create new user  
AuthorizationGroupEntry newuser = new AuthorizationGroupEntry(UserName, UID);  
AuthorizationGroupEntryCollection AGEC = new AuthorizationGroupEntryCollection();  
AGEC.Add(newuser);  
  
// Define new authorization group collection  
AuthorizationGroupCollection AGC = new AuthorizationGroupCollection();  
  
// Create new authorization group  
AuthorizationGroup AG = new AuthorizationGroup(GroupName, AccessPermit, AGEC);  
  
//add the authorization group to the authorization group collection  
AGC.Add(AG);  
  
//saving the authorization group collection to the rule store  
m_sqlRS.SaveAuthorizationGroups(AGC);  
  
rs = m_sqlRS.GetRuleSet(rsInfo[0]);                 
RSName = rs.Name;  
  
// Associate authorization group to the ruleset  
m_sqlRS.SetRuleSetAuthorizations(RSName, AGC);  
  
// Get ruleset by name from SQL rule store  
RuleSetInfoCollection rsInfo = m_sqlRS.GetRuleSets("myRuleSet", RuleStore.Filter.All);  
```  
  
> [!NOTE]
>  <span data-ttu-id="7d955-131">アイテム レベル 1 のセキュリティを使用すると、パフォーマンスが低下することがあります。ルール エンジンのインスタンスを返す前に、ポリシーが実行ごとにデータベース検索を行い、アプリケーションのアクセス レベルを評価する必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="7d955-131">The use of artifact level l security can diminish performance, because the policy will have to do a database lookup on each execution to evaluate the application's access level before returning an instance of the rule engine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d955-132">参照</span><span class="sxs-lookup"><span data-stu-id="7d955-132">See Also</span></span>  
 [<span data-ttu-id="7d955-133">ビジネス ルール エンジンの重要なセキュリティに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="7d955-133">Important Security Notes for the Business Rule Engine</span></span>](../core/important-security-notes-for-the-business-rule-engine.md)