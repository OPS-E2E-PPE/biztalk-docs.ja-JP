---
title: "セキュリティに関する注意事項、ビジネス ルール エンジン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, store administrator
- Business Rule Composer, security
- business rules, security
- Denial of Service attacks
ms.assetid: 8972127a-5569-4b32-bc09-e9265efe9514
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a90090c55dcbb0f8e55296d2711d5e4b36cd346
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="important-security-notes-for-the-business-rule-engine"></a>ビジネス ルール エンジンの重要なセキュリティに関する注意事項
このトピックでは、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] の既知のセキュリティの問題点とセキュリティのリスクを軽減するために行う操作手順について説明します。  
  
## <a name="malicious-schema-input-causing-denial-of-service-attack"></a>サービス拒否の攻撃を発生させる悪質なスキーマ入力  
 ファクトをアサートすると、各ルールは、ポリシー内のサポートされている種類と一致する各オブジェクトを確認します。 セレクターによって渡されたスキーマに含まれる要素のいずれかを使用するポリシー内に、あるルールが存在すると仮定します。 この要素/属性がセレクターと一致する場合にこのインスタンスが数千回繰り返されると、このようなすべてのインスタンスがアサートされます。この結果、パフォーマンスが低下し、サービスの拒否攻撃 (DoS) が起こる可能性があります。  
  
 この潜在的な問題を緩和するには、ポリシーの実行中に渡されるあいまいな入力すべてを確認する必要があります。  
  
## <a name="ruleset-not-validating-objects-before-asserting-the-facts"></a>ファクトをアサートする前にオブジェクトを確認しないルール セット  
 ファクトとして渡された任意のスキーマのインスタンス、 **RuleSet**セレクターを使用してルールをアサートする前に、スキーマに対して検証されません。 ポリシーの実行中に渡されるすべての入力を確認する必要があります。  
  
## <a name="expected-behaviors-of-the-business-rule-composer-when-rulestore-security-is-on"></a>RuleStore セキュリティが有効な場合のビジネス ルール作成ツールの正常な動作  
 呼び出して、ルール ストアのロールベースのセキュリティ機能を有効にすることができます、 **EnableAuthorization**のメソッド、 **RuleStore**クラスです。 このセキュリティ機能が有効な場合、ビジネス ルール作成ツールは、次のように動作します。  
  
-   オブジェクト モデルは、ユーザーの読み取りアクセス権限がないルール セットおよびボキャブラリを除外します。 このため、これらはビジネス ルール作成ツールに表示されません。  
  
-   ポリシーまたはボキャブラリに対する書き込みアクセス権限を持たないユーザーがそれらを保存しようとすると、例外がスローされます。  
  
## <a name="user-types-for-rule-store-administrator"></a>ルール ストア管理者のユーザーの種類  
 ルール ストア管理者には、ルール ストアに保存されるアイテムの認証グループを定義する権限があります。 ただし、ルール ストア管理者が属する次の 2 つの種類のユーザーの違いに注意してください。  
  
-   ルール ストア管理者が Windows ユーザーの場合 (つまり、Windows 認証でルール ストアを接続する場合)、ルール ストア管理者は、ユーザーが Windows グループまたは Windows ユーザーとなる認証グループを定義できます。  
  
-   ルール ストア管理者が SQL ユーザーの場合 (つまり、SQL 認証でルール ストアを接続する場合)、ルール ストア管理者は、ユーザーが Windows グループとなる認証グループを定義できません。ただし、ユーザーが Windows ユーザーとなる認証グループは定義できます。  
  
## <a name="user-cannot-associate-an-authorization-group-with-an-artifact-without-sufficient-rights"></a>十分な権限を持たないユーザーは認証グループをアイテムに関連付けられない  
 SQL dbo ユーザーでも RE_ADMIN_USERS のメンバーでもなく、アイテムに対する MODIFY_DELETE アクセス許可のないアイテムの作成者は、新しい認証グループをアイテムに関連付けることができません。 次のシナリオは、この例を示しています。  
  
1.  ルール セットの作成者は、dbo ユーザーでも RE_ADMIN_USERS グループのユーザーでもありません。また、ルール セットを作成した後の MODIFY_DELETE アクセス許可がありません。  
  
2.  作成者がルール セットを作成します。  
  
3.  RE_ADMIN_USERS グループのメンバーが、MODIFY_DELETE アクセス許可を持つ認証 AG1 を User2 に対して作成します。  
  
4.  作成者が、AG1 をルール セットに関連付けます。  
  
5.  ルール ストアの認証を有効にします。  
  
6.  RE_ADMIN_USERS グループのメンバーが、READ_EXECUTE アクセス許可を持つ認証 AG2 を User2 に対して作成します。  
  
7.  作成者が、AG2 をルール セットに関連付けます。 作成者にはこの操作を行う十分な権限がありませんが、エラー メッセージは表示されません。  
  
8.  User2 によるルール セットの読み取りが失敗します。