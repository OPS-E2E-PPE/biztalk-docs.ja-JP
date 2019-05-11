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
# <a name="support-for-nullable-types"></a><span data-ttu-id="3e985-102">Null 許容型のサポート</span><span class="sxs-lookup"><span data-stu-id="3e985-102">Support for Nullable Types</span></span>
<span data-ttu-id="3e985-103">ルール エンジンは、ビジネス ルールで null 許容型の使用をサポートします。</span><span class="sxs-lookup"><span data-stu-id="3e985-103">The rule engine supports using nullable types in a business rule.</span></span> <span data-ttu-id="3e985-104">.NET クラス バインド、XML バインド、およびデータベース バインドで null 許容型を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="3e985-104">You can use nullable types in .NET class bindings, XML bindings, and database bindings.</span></span> <span data-ttu-id="3e985-105">現時点では、ビジネス ルール作成ツールでは、ビジネス ルールで null 許容型の使用はできません。</span><span class="sxs-lookup"><span data-stu-id="3e985-105">Currently, the Business Rule Composer tool does not support using nullable types in a business rule.</span></span> <span data-ttu-id="3e985-106">プログラムで規則を作成するときに、null 許容型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e985-106">You can use the nullable types when creating rules programmatically.</span></span>  
  
## <a name="using-nullable-types-in-net-class-bindings"></a><span data-ttu-id="3e985-107">.NET クラス バインドで null 許容型の使用</span><span class="sxs-lookup"><span data-stu-id="3e985-107">Using Nullable Types in .NET Class Bindings</span></span>  
 <span data-ttu-id="3e985-108">プロパティまたは null 許容型のフィールドにバインドするクラスのメンバーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="3e985-108">You can create a class member binding to a property or a field whose type is a nullable type.</span></span> <span data-ttu-id="3e985-109">クラス メンバーを null 許容型のパラメーターを受け取るまたは null 許容型の値を取得するメソッドにバインドを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3e985-109">You can also create a class member binding to a method that takes a parameter of nullable type and/or returns a value of nullable type.</span></span> <span data-ttu-id="3e985-110">次のサンプル コードでは、ビジネス ルールのメソッドから null 許容型の戻り値にアクセスする方法と、null 許容フィールドにアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3e985-110">The following sample code demonstrates how to access a nullable field, and how to access a return value of nullable type from a method in a business rule.</span></span> <span data-ttu-id="3e985-111">表示されますが、コンソール アプリケーションを次のコードを実行する場合の値、 **prop**フィールドが 5 に設定します。</span><span class="sxs-lookup"><span data-stu-id="3e985-111">If you execute a console application with the following code as it is, you will see that the value of the **prop** field is set to 5.</span></span> <span data-ttu-id="3e985-112">初期化しない場合、 **prop**クラスのフィールドまたは null に設定し、コードを実行する初期化ことがわかりますの値、 **prop**フィールドが 1 に設定します。</span><span class="sxs-lookup"><span data-stu-id="3e985-112">If you do not initialize the **prop** field in the class or initialize it to null and run the code, you will see that the value of the **prop** field is set to 1.</span></span>  
  
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
  
## <a name="using-nullable-types-in-database-bindings"></a><span data-ttu-id="3e985-113">データベース バインドで null 許容型の使用</span><span class="sxs-lookup"><span data-stu-id="3e985-113">Using Nullable Types in Database Bindings</span></span>  
 <span data-ttu-id="3e985-114">データベース バインドで null 許容型を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="3e985-114">You can also use nullable types in database bindings.</span></span> <span data-ttu-id="3e985-115">次のサンプル コードでは、データベース バインドで null 許容型を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3e985-115">The following sample code fragment shows you how to use a nullable type in database bindings.</span></span>  
  
```  
DataColumnBinding dcBinding = new DataColumnBinding(“col”, typeof(int?), dbBinding);  
```  
  
 <span data-ttu-id="3e985-116">値をチェックする条件を持つルールがあるとするかどうかをデータベース列が 3 に等しい。</span><span class="sxs-lookup"><span data-stu-id="3e985-116">Suppose you have a rule with a condition that checks the value of a database column to see if equals 3.</span></span> <span data-ttu-id="3e985-117">列の値が null の場合、式が false に評価されます。</span><span class="sxs-lookup"><span data-stu-id="3e985-117">If the value of the column is null, the expression evaluates to false.</span></span> <span data-ttu-id="3e985-118">これには、例外は発生しません。</span><span class="sxs-lookup"><span data-stu-id="3e985-118">It does not cause an exception.</span></span>  
  
## <a name="using-nullable-types-in-xml-bindings"></a><span data-ttu-id="3e985-119">XML バインドで null 許容型の使用</span><span class="sxs-lookup"><span data-stu-id="3e985-119">Using Nullable Types in XML Bindings</span></span>  
 <span data-ttu-id="3e985-120">同様に、XML バインドで null 許容型を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="3e985-120">Similarly, you can use nullable types in XML bindings.</span></span> <span data-ttu-id="3e985-121">次のサンプル コードでは、XML バインドで null 許容型を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3e985-121">The following sample code fragment shows how to use a nullable type in XML bindings.</span></span>  
  
```  
XMLDocumentFieldBinding xfb1 = new XMLDocumentFieldBinding(typeof(int?),"ID",xdb);  
```