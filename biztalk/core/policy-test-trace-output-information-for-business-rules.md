---
title: ビジネス ルールにおけるポリシー テストのトレース出力の情報 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, business rules
- testing, policies
- business rules, testing
- policies, testing
ms.assetid: 26ff584e-97a1-4d76-a8a9-a55b4c99231f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 427eb9f1a7cae3cd6a1c9a6fe9a5ecac82e60c80
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394946"
---
# <a name="policy-test-trace-output-information-for-business-rules"></a>ビジネス ルールにおけるポリシー テストのトレース出力情報
このセクションでは、ビジネス ルール作成ツールでポリシーをテストするときに表示される追跡情報について説明します。 グループ ハブ ページでクエリを追跡メッセージ イベントおよびサービス インスタンスを使用してポリシーの実行の追跡結果を表示するときによく似ています情報が表示されます。  
  
 追跡出力に表示される 4 つのステートメントの種類があります。  
  
- ファクト アクティビティ  
  
- 条件の評価  
  
- 議題の更新  
  
- 実行されたルール  
  
  各ステートメントの種類を以下に示します。  
  
## <a name="fact-activity"></a>ファクト アクティビティ  
 このステートメントでは、エンジンの作業メモリに存在するファクトに対する変更を示します。 ファクト アクティビティのエントリの例を次に示します。  
  
```  
FACT ACTIVITY 3/16/2004 9:50:28 AM  
Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7  
Ruleset Name: LoanProcessing  
Operation: Assert  
Object Type: MyTest.test  
Object Instance Identifier: 872  
```  
  
### <a name="rule-engine-instance-identifier"></a>ルール エンジン インスタンス識別子  
 一意の識別子、 **RuleEngine**実行されているルールの実行環境を提供するインスタンス。  
  
### <a name="ruleset-name"></a>ルール セット名  
 ルール セット (ポリシー) の名前。  
  
### <a name="operation"></a>操作  
 ファクト アクティビティで発生する操作の 3 つの種類があります。  
  
 Filter  
  
 作業メモリに追加されるという事実です。  
  
 更新  
  
 という事実は、ルールによって更新されると、新しいデータと状態に基づいて、再評価するエンジンにアサートする必要があります。  
  
 取り消し  
  
 事実を作業メモリから削除しています。  
  
> [!NOTE]
>  型と一致しません、ポリシーで使用される型のいずれかのファクトがアサートされると場合、アサート操作は「アサート-認識されないファクト」で表示されます。  
  
### <a name="object-type"></a>[オブジェクトの種類]  
 特定のアクティビティのファクトの種類:  
  
-   DataConnection  
  
-   TypedDataTable  
  
-   TypedDataRow  
  
     すべての含まれる行の TypedDataTable がアサートされる場合は、TypedDataRows としてアサートされます。  条件が評価され、結果として得られるクエリが実行されるまで、DataConnection に関連付けられている TypedDataRows はアサートされません。  
  
-   TypedXmlDocument  
  
     アサーションが親と子の TypedXmlDocument インスタンスに表示されます。  
  
### <a name="object-instance-identifier"></a>オブジェクト インスタンス識別子  
 ファクト参照の一意のインスタンス ID。  
  
## <a name="condition-evaluation"></a>条件の評価  
 このアクティビティでは、個々 の述語を評価した結果を示します。 条件評価のエントリの例を次に示します。  
  
```  
CONDITION EVALUATION TEST (MATCH) 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Test Expression: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:Root.EmploymentType/TimeInMonths >= 18  
Left Operand Value: 31  
Right Operand Value: 18  
Test Result: True  
```  
  
 上記の例では用語の一部の説明は次のとおりです。  
  
-   **式をテストします。** ルールに含まれる (単項式または二) 単純な式です。  
  
-   **左側のオペランドの値。** 式の左側にある用語の値。  
  
-   **右側のオペランドの値。** 式の右側にある用語の値。  
  
-   **結果をテストします。** True であると、評価の結果または False。  
  
## <a name="agenda-update"></a>議題の更新  
 このアクティビティでは、後続の実行のルール エンジンの議題に追加される規則を示します。 議題の更新プログラムのエントリの例を次に示します。  
  
```  
AGENDA UPDATE 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Operation: Add  
Rule Name: Employment Status Rule  
Conflict Resolution Criteria: 0  
```  
  
 上記の例では用語の一部の説明は次のとおりです。  
  
-   **操作です。** ルールの追加または議題から削除できます。  
  
-   **規則の名前。** 議題に追加されている規則の名前。  
  
-   **競合解決条件。** アクションが実行される相対的な順序を決定するルールの優先順位 (優先順位の高いアクションが最初に実行されます)。  
  
## <a name="rule-fired"></a>実行されたルール  
 このアクティビティでは、ルールのアクションの実行を示します。 実行されたルールのエントリの例を次に示します。  
  
```  
RULE FIRED 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Rule Name: Residency Status Rule  
Conflict Resolution Criteria: 10  
```