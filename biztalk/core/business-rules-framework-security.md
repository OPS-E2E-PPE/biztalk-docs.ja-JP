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
# <a name="business-rules-framework-security"></a>ビジネス ルール フレームワークのセキュリティ
ビジネス ルール エンジンは、ホスト アプリケーションのセキュリティ コンテキストで動作します。 実行中にルール エンジン インスタンスの id は、スレッド コンテキストを呼び出す、 **Policy.Execute**メソッドです。  
  
## <a name="default-security-configuration"></a>既定のセキュリティ構成  
 Microsoft をインストールするときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2、Microsoft Windows グループは、default、管理者およびユーザーによって作成されます:「BizTalk Server 管理者」と"BizTalk Application Users" BTS_ADMIN_USERS および BTS_HOST_USERS は、それぞれ SQL ロールの RE_ADMIN_USERS および RE_HOST_USERS のメンバーです。  
  
 ルール ストアが作成されるたびに既定の SQL ロールが作成されます: BTS_ADMIN_USERS、BTS_HOST_USERS、RE_ADMIN_USERS および RE_HOST_USERS です。  
  
|既定の Windows グループ|SQL ロール|  
|----------------------------|---------------|  
|BizTalk Server 管理者|RE_ADMIN_USERS|  
|BizTalk Application Users|RE_HOST_USERS|  
  
 RE_ADMIN_USERS ロールのユーザーだけが、展開とエンティティ アクセスの保護に関する構成テーブルを更新するストアド プロシージャを実行できます。 つまり、ルール エンジンの管理者によってのみ、展開、展開解除、および保護の構成が行われます。 RE_HOST_USERS ロールのユーザーは、SQL ルール ストアの他のストアド プロシージャを実行できます。  
  
 ルール エンジンのインストールの順序に関係なく、データベース アクセスがまだ許可されていない場合に、ルール エンジン構成のプロセスは、ルール エンジン更新サービスのアカウント メンバーシップに RE_HOST_USERS SQL ロールを与えます。 ただし、BizTalk を最初にインストールした後にルール エンジンをインストールすると、ホストの作成が既に行われているため、ホスト固有のユーザー グループは、ルール エンジン データベースの BTS_HOST_USERS SQL ロールに追加されません。 この手順を手動で実行する必要があります。  
  
## <a name="artifact-level-security"></a>アイテム レベルのセキュリティ  
 既定のセキュリティ構成に加えて、ビジネス ルール エンジンも成果物でセキュリティを提供、ポリシーおよびボキャブラリ レベル。  
  
 各ポリシーのバージョンまたは各ボキャブラリのバージョンには、関連する 1 つ以上の認証グループがあります。 認証グループは、Microsoft Windows ユーザー、SQL ユーザー、SQL ロール、および Windows グループの名前付きのリストです。それぞれ特定のアクセス レベルを持っています。  
  
 新しいポリシーまたはボキャブラリがルール ストアに作成されると、既定で、ポリシーまたはボキャブラリを作成したユーザーとルール エンジン管理者だけが、読み取り/実行および変更/削除の処理を行うことができます。 ルール エンジン管理者がある (プロセスは、ユーザーの資格情報で動作) ユーザーは、アクセス レベル、または別の操作を実行するための権限を構成することができます: 読み取り/実行、変更/削除、完全なアクセス許可、またはアクセス許可がありません。  
  
 既定では、アイテム固有のセキュリティは無効です。 アイテム レベルのセキュリティは、現在、ユーザー インターフェイスを通じては設定できません。 ただし、ビジネス ルール エンジン管理者の資格情報を使用して、プログラムによって設定できます。 次のコードは、新しい認証を作成してグループをルール セットに関連付ける方法を示しています。  
  
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
>  アイテム レベル 1 のセキュリティを使用すると、パフォーマンスが低下することがあります。ルール エンジンのインスタンスを返す前に、ポリシーが実行ごとにデータベース検索を行い、アプリケーションのアクセス レベルを評価する必要があるためです。  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール エンジンの重要なセキュリティに関する注意事項](../core/important-security-notes-for-the-business-rule-engine.md)