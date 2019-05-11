---
title: ビジネス ルール エンジンにおけるクラス継承のサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- code samples, Business Rules Engine
- Business Rules Engine, inheritance
- Business Rules Engine, code samples
- Business Rules Engine, examples
- examples, Business Rules Engine
ms.assetid: 50871f34-ccbe-4f77-8feb-5694e1b14837
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a21d9d300bf01e2ab792ca86f8a52b9b5831695c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321908"
---
# <a name="support-for-class-inheritance-in-the-business-rule-engine"></a>ビジネス ルール エンジンにおけるクラス継承のサポート
オブジェクト指向プログラミング (OOP) 言語の主な機能の 1 つは、継承です。 継承は、すべての既存のクラスの機能を使用し、元のクラスを書き直すことがなくそれらの機能を拡張する機能です。  
  
 ビジネス ルール フレームワークは、2 種類のクラスの継承をサポートしています: 実装とインターフェイス。 実装の継承は、追加のコーディングなしで基本クラスのプロパティとメソッドを使用する機能を指します。 インターフェイスの継承は、プロパティおよびメソッドの名前だけを使用する機能が、子クラスは、実装を提供する必要があります。  
  
 共通の基本クラスでは、ルールを記述できますが、エンジンにアサートされるオブジェクトがクラスから派生させることができます。 次の例では、 **RegularEmployee**と**ContractEmployee**基底クラスの派生クラスは**従業員**します。  
  
```  
class Employee  
   {  
      public string Status()  
      {   
         // member definition  
      }  
      public string TimeInMonths()        
      {   
         // member definition  
      }  
   }  
  
class ContractEmployee : Employee  
{  
   // class definition  
}  
class RegularEmployee : Employee  
{  
   // class definition  
}  
```  
  
 次の規則があると仮定します。  
  
## <a name="rule-1"></a>ルール 1  
  
```  
IF Employee.TimeInMonths < 12  
THEN Employee.Status = "New"  
```  
  
 実行時に、ユーザーが 2 つのオブジェクトをアサートしている場合、インスタンス 1 つの**ContractEmployee**と、その他のインスタンスの**RegularEmployee**、両方のオブジェクトのインスタンスは、ルールに対して評価されます先ほどの。  
  
 ユーザーを使用して派生クラス オブジェクトをアサートできますも、 **Assert**します。 これにより、ルールと、次の例に示すように、派生オブジェクトとその基本型の条件の再評価されることが含まれています。  
  
## <a name="rule-2"></a>Rule 2  
  
```  
IF Employee.Status = "Contract"   
THEN Employee.Bonus = false  
Assert(new ContractEmployee())  
```  
  
 含むすべてのルール、**従業員**型または**ContractEmployee**アサーション後型を条件で再評価されます。 この例では、継承の種類は、実装です。 場合でも、派生クラスのみがアサートされると、基本クラスも取得アサート メソッドを使用して、派生クラスではなく、基本ルールが記述されている場合。  
  
## <a name="see-also"></a>参照  
 [ルール エンジン](../core/rule-engine.md)