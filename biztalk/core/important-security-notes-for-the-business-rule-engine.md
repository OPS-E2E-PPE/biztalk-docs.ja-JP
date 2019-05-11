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
# <a name="important-security-notes-for-the-business-rule-engine"></a>ビジネス ルール エンジンに関する重要なセキュリティ メモ
このトピックでは、Microsoft BizTalk Server とセキュリティ リスクを軽減するために行う手順の既知のセキュリティ問題をまとめたものです。  
  
## <a name="malicious-schema-input-causing-denial-of-service-attack"></a>サービス拒否攻撃の原因とする悪意のあるスキーマ入力  
 ファクトをアサートするには、各ルールは、ポリシー内でサポートされている型と一致するすべてのオブジェクトに対して検証されます。 セレクターによって渡されたスキーマでは、要素の 1 つをポリシーにルールがあるとします。 ここで、セレクターに一致するこの要素/属性がある場合、インスタンスが数千回の繰り返し発生する場合このようなすべてのインスタンスをアサートすると、パフォーマンスが低下し後続可能なサービス拒否 (DoS)。  
  
 この潜在的な問題を軽減するには、ポリシーの実行中に渡されるすべてのあいまいな入力を検証する必要があります。  
  
## <a name="ruleset-not-validating-objects-before-asserting-the-facts"></a>ファクトをアサートする前にオブジェクトを確認しないルール セット  
 ファクトとして渡される任意のスキーマのインスタンス、 **RuleSet**セレクターを使用してルールをアサートする前に、スキーマに対して検証されません。 ポリシーの実行中に渡されるすべての入力を検証する必要があります。  
  
## <a name="expected-behaviors-of-the-business-rule-composer-when-rulestore-security-is-on"></a>RuleStore セキュリティがビジネス ルール作成ツールの動作  
 呼び出すことによって、ルール ストアのロールベースのセキュリティ機能を有効にすることができます、 **EnableAuthorization**のメソッド、 **RuleStore**クラス。 このセキュリティ機能を有効にすると、ビジネス ルール作成ツールで予期される動作は、します。  
  
-   オブジェクト モデルは、ルール セットおよびボキャブラリをユーザーが読み取りアクセス権によって除外されます。 そのため、ビジネス ルール作成ツールが表示されません。  
  
-   ユーザーは、ポリシーまたはボキャブラリへの書き込みアクセスを持っていない場合いずれかを保存しようと原因がスローされる例外。  
  
## <a name="user-types-for-rule-store-administrator"></a>ルール ストア管理者のユーザーの種類  
 ルール ストア管理者は、ルール ストアに保存されるアイテムの認証グループを定義するための権限を持ちます。 ただし、次の 2 つの種類はルール ストア管理者が所属するユーザーの違いに注意してください。  
  
-   ルール ストア管理者が Windows 認証を使用して、ルール ストアを接続するには、Windows ユーザーの場合、ルール ストア管理者は認証グループを持つユーザーが Windows グループまたは Windows ユーザーを定義できます。  
  
-   ルール ストア管理者が認証グループを持つユーザーは、Windows グループを定義することはできませんが、ユーザーが認証グループを定義できますルール ストア管理者が、SQL 認証を使用して、ルール ストアを接続するには、SQL ユーザーである場合、Windows ユーザーです。  
  
## <a name="user-cannot-associate-an-authorization-group-with-an-artifact-without-sufficient-rights"></a>ユーザーは認証グループを十分な権限がない場合、成果物に関連付けることはできません。  
 SQL dbo ユーザーでも RE_ADMIN_USERS のメンバーと、アイテムに対する MODIFY_DELETE アクセス許可がないアイテムの作成者は、新しい承認グループを成果物に関連付けることはできません。 次のシナリオでは、この動作の例を示します。  
  
1.  ルール セットの作成者は、dbo ではありません、RE_ADMIN_USERS グループ内にないし、MODIFY_DELETE アクセス許可を持たない規則セットを作成した後。  
  
2.  作成者は、ルール セットを作成します。  
  
3.  RE_ADMIN_USERS グループのメンバーでは、user2 MODIFY_DELETE アクセス許可を持つ認証 AG1 を作成します。  
  
4.  作成者は、AG1 をルール セットに関連付けます。  
  
5.  ルール ストアの認証を有効にします。  
  
6.  RE_ADMIN_USERS グループのメンバーでは、user2 READ_EXECUTE アクセス許可を持つ認証 AG2 を作成します。  
  
7.  作成者は、AG2 をルール セットに関連付けます。 作成者では、そのためには十分な権限はありませんが、エラー メッセージは表示されません。  
  
8.  User2 によるルール セットが失敗した読み取りを試みます。