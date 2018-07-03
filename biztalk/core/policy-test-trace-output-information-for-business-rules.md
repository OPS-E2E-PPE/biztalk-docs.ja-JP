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
ms.openlocfilehash: e8795e926d496f586d032bb85fe4a1fddb473ec5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005139"
---
# <a name="policy-test-trace-output-information-for-business-rules"></a>ビジネス ルールにおけるポリシー テストのトレース出力情報
このセクションでは、ビジネス ルール作成ツールでポリシーをテストする場合に表示される追跡情報について説明します。 [グループ ハブ] ページでメッセージ イベントとサービス インスタンスの追跡クエリを使用してポリシー実行の追跡結果を表示すると、同様の情報が表示されます。  
  
 追跡出力に表示されるステートメントの種類には、次の 4 つがあります。  
  
- ファクト アクティビティ  
  
- 条件の評価  
  
- 議題の更新  
  
- 実行されたルール  
  
  各ステートメントの種類を次に示します。  
  
## <a name="fact-activity"></a>ファクト アクティビティ  
 このステートメントは、エンジンの作業メモリに存在するファクトに対する変更を示します。 ファクト アクティビティのエントリの例を次に示します。  
  
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
 ルール セット (ポリシー) の名前です。  
  
### <a name="operation"></a>演算  
 ファクト アクティビティでは、3 種類の操作があります。  
  
 Filter  
  
 ファクトが作業メモリに追加されます。  
  
 更新  
  
 ファクトがルールによって更新されます。このファクトは、新しいデータおよび状態に基づいて、再評価するエンジンに再度アサートする必要があります。  
  
 取り消し  
  
 ファクトが作業メモリから削除されます。  
  
> [!NOTE]
>  型と一致しません、ポリシーで使用される型のいずれかのファクトがアサートされると場合、アサート操作は「アサート-認識されないファクト」で表示されます。  
  
### <a name="object-type"></a>[オブジェクトの種類]  
 特定のアクティビティのファクトの種類です。  
  
-   DataConnection  
  
-   TypedDataTable  
  
-   TypedDataRow  
  
     TypedDataTable がアサートされると、含まれるすべての行が TypedDataRows としてアサートされます。  DataConnection に関連付けられている TypedDataRows は、条件が評価され、結果のクエリが実行されるまで、アサートされません。  
  
-   TypedXmlDocument  
  
     親と子の TypedXmlDocument インスタンスにアサーションが表示されます。  
  
### <a name="object-instance-identifier"></a>オブジェクト インスタンス識別子  
 ファクト参照の一意のインスタンス ID。  
  
## <a name="condition-evaluation"></a>条件の評価  
 このアクティビティは、個別の述語の評価結果を示します。 条件の評価のエントリの例を次に示します。  
  
```  
CONDITION EVALUATION TEST (MATCH) 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Test Expression: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:Root.EmploymentType/TimeInMonths >= 18  
Left Operand Value: 31  
Right Operand Value: 18  
Test Result: True  
```  
  
 前の例に記されている用語について説明します。  
  
-   **式をテストします。** ルール内の簡単な式 (単項式または二項式)。  
  
-   **左側のオペランドの値。** 式の左側の条件値です。  
  
-   **右側のオペランドの値。** 式の右側の条件値です。  
  
-   **結果をテストします。** 評価の結果 (True または False のいずれか) です。  
  
## <a name="agenda-update"></a>議題の更新  
 このアクティビティは、以降の実行に使用するルール エンジンの議題に追加されるルールを示します。 議題の更新のエントリの例を次に示します。  
  
```  
AGENDA UPDATE 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Operation: Add  
Rule Name: Employment Status Rule  
Conflict Resolution Criteria: 0  
```  
  
 前の例に記されている用語について説明します。  
  
-   **操作です。** ルールを議題から追加または削除できます。  
  
-   **規則の名前。** 議題に追加されているルールの名前です。  
  
-   **競合解決条件。** アクションが実行される相対的な順序を決定するルールの優先順位 (優先順位の高いアクションが最初に実行されます)。  
  
## <a name="rule-fired"></a>実行されたルール  
 このアクティビティは、ルールのアクションの実行を示します。 実行されたルールのエントリの例を次に示します。  
  
```  
RULE FIRED 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Rule Name: Residency Status Rule  
Conflict Resolution Criteria: 10  
```