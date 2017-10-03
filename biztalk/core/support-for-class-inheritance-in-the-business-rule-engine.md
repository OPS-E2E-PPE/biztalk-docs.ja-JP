---
title: "ビジネス ルール エンジンにおけるクラス継承のサポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code samples, Business Rules Engine
- Business Rules Engine, inheritance
- Business Rules Engine, code samples
- Business Rules Engine, examples
- examples, Business Rules Engine
ms.assetid: 50871f34-ccbe-4f77-8feb-5694e1b14837
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 930fc5591ce55f1a2ec988b307203a4154e85c2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="support-for-class-inheritance-in-the-business-rule-engine"></a>ビジネス ルール エンジンにおけるクラス継承のサポート
オブジェクト指向プログラミング (OOP) 言語の主要な機能の 1 つが、継承です。 継承では、既存のクラスの機能をすべて使用して、元のクラスを書き直すことなく、その機能を拡張できます。  
  
 ビジネス ルール フレームワークは、2 種類のクラスの継承をサポートしています: 実装とインターフェイスします。 実装の継承は、追加のコーディングなしで、基本クラスのプロパティおよびメソッドを使用する機能です。 インターフェイスの継承は、プロパティおよびメソッドの名前だけを使用しますが、子クラスは実装を提供する必要があります。  
  
 ルールは共通の基本クラスで記述できますが、エンジンにアサートされるオブジェクトはクラスから派生させることができます。 次の例では、 **RegularEmployee**と**ContractEmployee**基底クラスの派生クラスは、**従業員**です。  
  
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
  
 実行時に、ユーザーが 2 つのオブジェクトをアサートする場合、インスタンス 1 つの**ContractEmployee**と、その他のインスタンスの**RegularEmployee**、両方のオブジェクトのインスタンスが記述されたルールに対して評価されます先ほどの。  
  
 ユーザーを使用してアクション内の派生クラス オブジェクトをアサートできますも、 **Assert**です。 これにより、次の例に示すように、派生オブジェクトとその基本型を条件に含むルールは再評価されます。  
  
## <a name="rule-2"></a>規則 2  
  
```  
IF Employee.Status = "Contract"   
THEN Employee.Bonus = false  
Assert(new ContractEmployee())  
```  
  
 すべてのルールを含む、**従業員**型または**ContractEmployee**型を条件でアサーションの後に再評価されます。 この例では実装が継承されています。 派生クラスのみがアサートされる場合でも、派生クラスではなく基本クラスのメソッドを使用してルールが記述されると基本クラスもアサートされます。  
  
## <a name="see-also"></a>参照  
 [ルール エンジン](../core/rule-engine.md)