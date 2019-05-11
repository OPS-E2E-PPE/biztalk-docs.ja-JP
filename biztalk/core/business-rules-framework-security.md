---
title: ビジネス ルール フレームワークのセキュリティ |Microsoft Docs
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
ms.openlocfilehash: 078c4671fbc587b56ce1dafed0e9676ddadbd7d0
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530427"
---
# <a name="business-rules-framework-security"></a><span data-ttu-id="a5aa7-102">ビジネス ルール フレームワークのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="a5aa7-102">Business Rules Framework Security</span></span>
<span data-ttu-id="a5aa7-103">ビジネス ルール エンジンは、ホスト アプリケーションのセキュリティ コンテキストで動作します。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-103">The Business Rule Engine operates in the security context of the hosting application.</span></span> <span data-ttu-id="a5aa7-104">実行中にルール エンジン インスタンスの id は、スレッド コンテキストを呼び出す、 **Policy.Execute**メソッド。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-104">The identity of the rule engine instance during execution is that of the thread context that invokes the **Policy.Execute** method.</span></span>  
  
## <a name="default-security-configuration"></a><span data-ttu-id="a5aa7-105">既定のセキュリティ構成</span><span class="sxs-lookup"><span data-stu-id="a5aa7-105">Default security configuration</span></span>  
 <span data-ttu-id="a5aa7-106">Microsoft をインストールするときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、2 つの管理者とユーザーの既定で Microsoft Windows グループが作成されます。「BizTalk Server 管理者」と"BizTalk Application Users"</span><span class="sxs-lookup"><span data-stu-id="a5aa7-106">When you install Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], two Microsoft Windows groups are created by default, one for administrators and one for users: "BizTalk Server Administrators" and "BizTalk Application Users."</span></span> <span data-ttu-id="a5aa7-107">これら 2 つの Windows グループは、BTS_ADMIN_USERS および BTS_HOST_USERS SQL ロールの RE_ADMIN_USERS および RE_HOST_USERS SQL ロールのメンバーは、それぞれのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-107">These two Windows groups are members of BTS_ADMIN_USERS and BTS_HOST_USERS SQL Roles which are members of RE_ADMIN_USERS and RE_HOST_USERS SQL Roles respectively.</span></span>  
  
 <span data-ttu-id="a5aa7-108">ルール ストアが作成されるたびに、既定の SQL ロールが作成されます。BTS_ADMIN_USERS、BTS_HOST_USERS、RE_ADMIN_USERS および RE_HOST_USERS します。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-108">The default SQL roles are created whenever a rule store is created: BTS_ADMIN_USERS, BTS_HOST_USERS, RE_ADMIN_USERS and RE_HOST_USERS.</span></span>  
  
|<span data-ttu-id="a5aa7-109">既定の Windows グループ</span><span class="sxs-lookup"><span data-stu-id="a5aa7-109">Default Windows groups</span></span>|<span data-ttu-id="a5aa7-110">SQL ロール</span><span class="sxs-lookup"><span data-stu-id="a5aa7-110">SQL roles</span></span>|  
|----------------------------|---------------|  
|<span data-ttu-id="a5aa7-111">BizTalk Server 管理者</span><span class="sxs-lookup"><span data-stu-id="a5aa7-111">BizTalk Server Administrators</span></span>|<span data-ttu-id="a5aa7-112">RE_ADMIN_USERS</span><span class="sxs-lookup"><span data-stu-id="a5aa7-112">RE_ADMIN_USERS</span></span>|  
|<span data-ttu-id="a5aa7-113">BizTalk Application Users</span><span class="sxs-lookup"><span data-stu-id="a5aa7-113">BizTalk Application Users</span></span>|<span data-ttu-id="a5aa7-114">RE_HOST_USERS</span><span class="sxs-lookup"><span data-stu-id="a5aa7-114">RE_HOST_USERS</span></span>|  
  
 <span data-ttu-id="a5aa7-115">RE_ADMIN_USERS ロールのユーザーだけでは、展開とエンティティへのアクセスの保護構成のテーブルを更新するストアド プロシージャを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-115">Only users in the RE_ADMIN_USERS role can execute the stored procedures that update the deployment and entity access protection configuration tables.</span></span> <span data-ttu-id="a5aa7-116">つまり、展開、展開解除、および保護の構成がすべて行われること、ルール エンジン管理者だけです。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-116">This means that the deployment, undeployment, and protection configuration are all done only by rule engine administrators.</span></span> <span data-ttu-id="a5aa7-117">RE_HOST_USERS ロールのユーザーは、SQL ルール ストアで他のストアド プロシージャを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-117">Users in the RE_HOST_USERS role can execute the other stored procedures in the SQL rule store.</span></span>  
  
 <span data-ttu-id="a5aa7-118">ルール エンジンのインストールの順序に関係なく、ルール エンジンの構成プロセスは、それが既にデータベース アクセスできない場合、RE_HOST_USERS SQL ロールにルール エンジン更新サービスのアカウント メンバシップを付与します。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-118">Regardless of the order of installation of the rule engine, the rule engine configuration process grants the Rule Engine Update Service account membership to the RE_HOST_USERS SQL role, if it does not already have database access.</span></span> <span data-ttu-id="a5aa7-119">ただし、ルール エンジンがインストールされている場合、最初 BizTalk のインストール後、BizTalk、ホスト固有のユーザー グループは追加されませんルール エンジン データベースの BTS_HOST_USERS SQL ロールにホストの作成が既に完了したためです。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-119">However, if the rule engine is installed after the initial BizTalk installation the BizTalk, host-specific users group is not added to the BTS_HOST_USERS SQL role in the Rule Engine database because host creation has already been completed.</span></span> <span data-ttu-id="a5aa7-120">この手順を手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-120">You need to perform this step manually.</span></span>  
  
## <a name="artifact-level-security"></a><span data-ttu-id="a5aa7-121">アイテム レベルのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="a5aa7-121">Artifact level security</span></span>  
 <span data-ttu-id="a5aa7-122">既定のセキュリティ構成だけでなく、ビジネス ルール エンジンはまた、成果物でセキュリティを提供、ポリシーおよびボキャブラリ レベル。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-122">In addition to the default security configuration, the Business Rule Engine can also provide security at the artifact—policy and vocabulary level.</span></span>  
  
 <span data-ttu-id="a5aa7-123">各ポリシーまたはボキャブラリのバージョンでは、関連付けられている 1 つまたは複数の認証グループがあります。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-123">Each policy or vocabulary version has one or more authorization groups associated with it.</span></span> <span data-ttu-id="a5aa7-124">認証グループでは、Microsoft Windows ユーザー、SQL ユーザー、SQL ロール、および各種類で特定のアクセス レベルでの Windows グループの名前付きの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-124">An Authorization group is a named list of Microsoft Windows users, SQL users, SQL roles, and Windows groups, with a particular access level on each type.</span></span>  
  
 <span data-ttu-id="a5aa7-125">新しいポリシーまたはボキャブラリがルール ストアに作成されると、し、ルール エンジン管理者を作成したユーザーのみが読み取り/実行と既定のアクセスの変更/削除します。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-125">When a new policy or vocabulary is created in the rule store, only the user who created it and the rule engine administrator have both read/execute and modify/delete access by default.</span></span> <span data-ttu-id="a5aa7-126">(プロセスは、ユーザーの資格情報で動作) ユーザーは、アクセス レベルやさまざまな操作を実行するための権限がある、ルール エンジン管理者を構成できます: 読み取り/実行、変更/削除、完全なアクセス許可、またはアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-126">The rule engine administrator can configure which users (processes operate under user credentials) have the access level, or rights, to perform different operations—read/execute, modify/delete, full permission, or no permission.</span></span>  
  
 <span data-ttu-id="a5aa7-127">既定では、アイテム固有のセキュリティが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-127">Artifact specific security is not enabled by default.</span></span> <span data-ttu-id="a5aa7-128">アイテム レベルのセキュリティを設定することは、現在使用できるユーザー インターフェイスではありません。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-128">Setting artifact level security is not currently available through the user interface.</span></span> <span data-ttu-id="a5aa7-129">ただし、設定できますプログラムでビジネス ルール エンジン管理者の資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-129">However, it can be set programmatically with the Business Rule Engine administrator credential.</span></span> <span data-ttu-id="a5aa7-130">次のコード フラグメントでは、新しい承認を作成してルール セットにグループを関連付ける方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-130">The following code fragment shows how to create a new authorization and associate the group to a rule set.</span></span>  
  
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
>  <span data-ttu-id="a5aa7-131">成果物レベル l のセキュリティを使用したことができます、ポリシーをルール エンジンのインスタンスを返す前に、アプリケーションのアクセス レベルを評価するには、各実行でデータベースの検索を行う必要があるために、パフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="a5aa7-131">The use of artifact level l security can diminish performance, because the policy will have to do a database lookup on each execution to evaluate the application's access level before returning an instance of the rule engine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5aa7-132">参照</span><span class="sxs-lookup"><span data-stu-id="a5aa7-132">See Also</span></span>  
 [<span data-ttu-id="a5aa7-133">ビジネス ルール エンジンに関する重要なセキュリティ メモ</span><span class="sxs-lookup"><span data-stu-id="a5aa7-133">Important Security Notes for the Business Rule Engine</span></span>](../core/important-security-notes-for-the-business-rule-engine.md)