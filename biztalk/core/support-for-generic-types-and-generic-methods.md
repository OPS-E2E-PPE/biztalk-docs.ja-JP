---
title: ジェネリック型とジェネリック メソッドのサポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc6b5b51-e084-4828-ad25-9209aa74dc6f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65d8a17a9ac1f055312f0f1cdf3bc1231319842d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972320"
---
# <a name="support-for-generic-types-and-generic-methods"></a>ジェネリック型とジェネリック メソッドのサポート
ルール エンジンは、特殊なジェネリック型と特殊なジェネリック メソッドについて、ルール内での使用をサポートしています。 ジェネリック型とジェネリック メソッド自体については、ルール内での使用をサポートしていません。 たとえば、ビジネス ルールで行うこともできます**リスト**\<*int*\>、ではなく**リスト**\<T\> (、から**System.Collections.Generic** .NET クラス ライブラリの名前空間)。 現在、ビジネス ルール作成ツールは、特殊なジェネリック型と特殊なジェネリック メソッドを使用したルールの作成をサポートしていません。 ルール エンジン オブジェクト モデルを使用し、プログラムによってルールを作成する必要があります。 次のサンプル コードを使用する方法を示しています、**リスト**のビジネス ルールに汎用クラス。  
  
```  
  
// Create the condition list IF 1 == 1  
Equal eq = new Equal(new Constant(1), new Constant(1));  
  
// Create the action list List<int>.Add(3)  
ActionCollection ac = new ActionCollection();  
  
//Create class binding and class member bindings  
ClassBinding lstClass = new ClassBinding(typeof(System.Collections.Generic.List<int>));  
ArgumentCollection argc = new ArgumentCollection();  
argc.Add(new Constant(3));  
ClassMemberBinding add = new ClassMemberBinding("Add", lstClass, argc);  
  
// Wrapping the .NET binding as a user function  
UserFunction uf = new UserFunction(add);  
ac.Add(uf);  
  
// Create the rule  
Rule rl = new Rule("AddToList", eq, ac);  
  
// Create the policy  
RuleSet rs = new RuleSet("GenericTest");  
rs.Rules.Add(rl);  
  
// Create the .NET List object  
List<int> lst = new List<int>();  
lst.Add(1);  
lst.Add(2);  
  
// Print the list before executing the policy  
Console.WriteLine("Contents of the lists before executing the policy");  
foreach (int i in lst)  
    Console.WriteLine(i);  
  
PolicyTester pt = new PolicyTester(rs);  
pt.Execute(lst);  
  
// Print the list after executing the policy  
Console.WriteLine("Contents of the lists before executing the policy");  
foreach (int i in lst)  
    Console.WriteLine(i);  
```