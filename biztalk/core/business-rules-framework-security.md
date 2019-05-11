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
# <a name="business-rules-framework-security"></a>ビジネス ルール フレームワークのセキュリティ
ビジネス ルール エンジンは、ホスト アプリケーションのセキュリティ コンテキストで動作します。 実行中にルール エンジン インスタンスの id は、スレッド コンテキストを呼び出す、 **Policy.Execute**メソッド。  
  
## <a name="default-security-configuration"></a>既定のセキュリティ構成  
 Microsoft をインストールするときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、2 つの管理者とユーザーの既定で Microsoft Windows グループが作成されます。「BizTalk Server 管理者」と"BizTalk Application Users" これら 2 つの Windows グループは、BTS_ADMIN_USERS および BTS_HOST_USERS SQL ロールの RE_ADMIN_USERS および RE_HOST_USERS SQL ロールのメンバーは、それぞれのメンバーです。  
  
 ルール ストアが作成されるたびに、既定の SQL ロールが作成されます。BTS_ADMIN_USERS、BTS_HOST_USERS、RE_ADMIN_USERS および RE_HOST_USERS します。  
  
|既定の Windows グループ|SQL ロール|  
|----------------------------|---------------|  
|BizTalk Server 管理者|RE_ADMIN_USERS|  
|BizTalk Application Users|RE_HOST_USERS|  
  
 RE_ADMIN_USERS ロールのユーザーだけでは、展開とエンティティへのアクセスの保護構成のテーブルを更新するストアド プロシージャを実行できます。 つまり、展開、展開解除、および保護の構成がすべて行われること、ルール エンジン管理者だけです。 RE_HOST_USERS ロールのユーザーは、SQL ルール ストアで他のストアド プロシージャを実行できます。  
  
 ルール エンジンのインストールの順序に関係なく、ルール エンジンの構成プロセスは、それが既にデータベース アクセスできない場合、RE_HOST_USERS SQL ロールにルール エンジン更新サービスのアカウント メンバシップを付与します。 ただし、ルール エンジンがインストールされている場合、最初 BizTalk のインストール後、BizTalk、ホスト固有のユーザー グループは追加されませんルール エンジン データベースの BTS_HOST_USERS SQL ロールにホストの作成が既に完了したためです。 この手順を手動で実行する必要があります。  
  
## <a name="artifact-level-security"></a>アイテム レベルのセキュリティ  
 既定のセキュリティ構成だけでなく、ビジネス ルール エンジンはまた、成果物でセキュリティを提供、ポリシーおよびボキャブラリ レベル。  
  
 各ポリシーまたはボキャブラリのバージョンでは、関連付けられている 1 つまたは複数の認証グループがあります。 認証グループでは、Microsoft Windows ユーザー、SQL ユーザー、SQL ロール、および各種類で特定のアクセス レベルでの Windows グループの名前付きの一覧を示します。  
  
 新しいポリシーまたはボキャブラリがルール ストアに作成されると、し、ルール エンジン管理者を作成したユーザーのみが読み取り/実行と既定のアクセスの変更/削除します。 (プロセスは、ユーザーの資格情報で動作) ユーザーは、アクセス レベルやさまざまな操作を実行するための権限がある、ルール エンジン管理者を構成できます: 読み取り/実行、変更/削除、完全なアクセス許可、またはアクセス許可がありません。  
  
 既定では、アイテム固有のセキュリティが有効になっていません。 アイテム レベルのセキュリティを設定することは、現在使用できるユーザー インターフェイスではありません。 ただし、設定できますプログラムでビジネス ルール エンジン管理者の資格情報を使用します。 次のコード フラグメントでは、新しい承認を作成してルール セットにグループを関連付ける方法を示します。  
  
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
>  成果物レベル l のセキュリティを使用したことができます、ポリシーをルール エンジンのインスタンスを返す前に、アプリケーションのアクセス レベルを評価するには、各実行でデータベースの検索を行う必要があるために、パフォーマンスが低下します。  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール エンジンに関する重要なセキュリティ メモ](../core/important-security-notes-for-the-business-rule-engine.md)