---
title: Null 許容型のサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a5ea191-09d5-47ab-a197-390fbbcf6306
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c468df33b522f14608fbe001f4ce4be52ba524e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254424"
---
# <a name="support-for-nullable-types"></a>Null 許容型のサポート
ルール エンジンは、ビジネス ルールで null 許容型の使用をサポートします。 .NET クラス バインド、XML バインド、およびデータベース バインドで null 許容型を使用することができます。 現時点では、ビジネス ルール作成ツールでは、ビジネス ルールで null 許容型の使用はできません。 プログラムで規則を作成するときに、null 許容型を使用できます。  
  
## <a name="using-nullable-types-in-net-class-bindings"></a>.NET クラス バインドで null 許容型の使用  
 プロパティまたは null 許容型のフィールドにバインドするクラスのメンバーを作成することができます。 クラス メンバーを null 許容型のパラメーターを受け取るまたは null 許容型の値を取得するメソッドにバインドを作成することもできます。 次のサンプル コードでは、ビジネス ルールのメソッドから null 許容型の戻り値にアクセスする方法と、null 許容フィールドにアクセスする方法を示します。 表示されますが、コンソール アプリケーションを次のコードを実行する場合の値、 **prop**フィールドが 5 に設定します。 初期化しない場合、 **prop**クラスのフィールドまたは null に設定し、コードを実行する初期化ことがわかりますの値、 **prop**フィールドが 1 に設定します。  
  
```  
using Microsoft.RuleEngine;  
namespace UseNullableAsm  
{  
    class Program  
    {  
        public class Class1  
        {  
            public int? prop = 1;  
            private int? prop2 = 4;  
            public int? GetProp2()  
            {  
                return prop2;  
            }  
        }  
  
        static void Main(string[] args)  
        {  
            //Create the class binding for the Class1 class  
            ClassBinding cbCls1 = new ClassBinding(typeof(Class1));  
  
            //Create the class member binding to the GetProp2 method of Cls1 class  
            ClassMemberBinding cmGetProp2 = new ClassMemberBinding("GetProp2", cbCls1);  
  
            //Create the class member binding to the to GET the value of prop  
            ClassMemberBinding cmGetProp = new ClassMemberBinding("prop", cbCls1);  
  
            //Create arguments for the prop1 field, which is prop1 + GetProp2()  
            UserFunction ufGetProp = new UserFunction(cmGetProp);  
            Add addArg = new Add(ufGetProp, new UserFunction(cmGetProp2));  
            ArgumentCollection al1 = new ArgumentCollection();  
            al1.Add(addArg);  
  
            //Set the value of prop to prop1 + cmGetPro2()  
            ClassMemberBinding cmProp = new ClassMemberBinding("prop", cbCls1, al1);  
  
            //Create a userfunction based on cmProp and add to the action collection  
            UserFunction ufProp = new UserFunction(cmProp);  
            ActionCollection ac = new ActionCollection();  
            ac.Add(ufProp);  
  
            //Create the condition list IF prop == 1  
            Equal eq = new Equal(ufGetProp, new Constant(1));  
  
            //Create the rule   
            // If (prop == 1)  
            // Then prop = prop + GetProp2()  
            Rule rl = new Rule("NullableTestRule", eq, ac);  
  
            //Create the condition list IF prop != 1  
            NotEqual neq = new NotEqual(ufGetProp, new Constant(1));  
  
            //Set the value of prop to prop to 1  
            Constant ct = new Constant(1);  
            ArgumentCollection al2 = new ArgumentCollection();  
            al2.Add(ct);  
  
            //Create class member binding to prop field with argument value 1  
            ClassMemberBinding cmSetProp = new ClassMemberBinding("prop", cbCls1, al2);  
  
            //Create a userfunction based on cmSetProp and add to the action collection  
            UserFunction ufSetProp = new UserFunction(cmSetProp);  
            ActionCollection ac2 = new ActionCollection();  
            ac2.Add(ufSetProp);  
  
            //Create the second rule   
            // If (prop != 1)  
            // Then prop = 1  
            Rule rl2 = new Rule("NullableTestRule2", neq, ac2);  
  
            //Create the policy and add both the rules to the policy  
            RuleSet rs = new RuleSet("NulableTestPolicy");  
            rs.Rules.Add(rl);  
            rs.Rules.Add(rl2);  
  
            //Create the .NET object fact  
            Class1 cls1Obj = new Class1();  
  
            //Print the value of the field prop before executing the policy  
            Console.WriteLine("Value of the prop field is " + cls1Obj.prop);  
  
            //Execute the policy  
            PolicyTester pt = new PolicyTester(rs);  
            pt.Execute(cls1Obj);  
  
            //Print the value of the field prop after executing the policy  
            Console.WriteLine("Value of the prop field is " + cls1Obj.prop);  
        }  
    }  
}  
```  
  
## <a name="using-nullable-types-in-database-bindings"></a>データベース バインドで null 許容型の使用  
 データベース バインドで null 許容型を使用することもできます。 次のサンプル コードでは、データベース バインドで null 許容型を使用する方法を示します。  
  
```  
DataColumnBinding dcBinding = new DataColumnBinding(“col”, typeof(int?), dbBinding);  
```  
  
 値をチェックする条件を持つルールがあるとするかどうかをデータベース列が 3 に等しい。 列の値が null の場合、式が false に評価されます。 これには、例外は発生しません。  
  
## <a name="using-nullable-types-in-xml-bindings"></a>XML バインドで null 許容型の使用  
 同様に、XML バインドで null 許容型を使用することができます。 次のサンプル コードでは、XML バインドで null 許容型を使用する方法を示します。  
  
```  
XMLDocumentFieldBinding xfb1 = new XMLDocumentFieldBinding(typeof(int?),"ID",xdb);  
```