---
title: 型キャストのサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6af46e34-5e33-4f61-8c19-4348f1bb4d4a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9517a398dbdd75ac2a31bad6d92c82922ad64510
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398919"
---
# <a name="support-for-type-casting"></a><span data-ttu-id="56279-102">型キャストのサポート</span><span class="sxs-lookup"><span data-stu-id="56279-102">Support for Type Casting</span></span>
<span data-ttu-id="56279-103">使用することができます、**キャスト**のメソッド、 **ClassMemberBinding**クラスを 1 つの型のオブジェクトを別の互換性のある型のオブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="56279-103">You can use the **Cast** method of the **ClassMemberBinding** class to convert an object of one type to an object of another compatible type.</span></span> <span data-ttu-id="56279-104">現在、ビジネス ルール作成ツールはサポートされていませんルールの作成を使用して、**キャスト**メソッド。</span><span class="sxs-lookup"><span data-stu-id="56279-104">Currently, the Business Rule Composer tool does not support creating rules by using the **Cast** method.</span></span> <span data-ttu-id="56279-105">この機能を活用するために、ルール エンジン オブジェクト モデルを使用してプログラムによってルールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56279-105">You must create the rules programmatically by using the rule engine object model to take advantage of this feature.</span></span>  
  
 <span data-ttu-id="56279-106">次のサンプル コードを使用する方法を示します、**キャスト**のインスタンスに変換するメソッド、 **System.Object**クラスのインスタンスを**Cls2**クラス。</span><span class="sxs-lookup"><span data-stu-id="56279-106">The following sample code demonstrates how to use the **Cast** method to convert an instance of the **System.Object** class to an instance of the **Cls2** class.</span></span> <span data-ttu-id="56279-107">このサンプルは」の説明に従って、クラスの入れ子になったメンバーにアクセスする方法も示します[クラスの入れ子になったメンバーのアクセス](../core/accessing-nested-members-of-a-class.md)します。</span><span class="sxs-lookup"><span data-stu-id="56279-107">This sample also demonstrates how to access a nested member of a class as described in [Accessing Nested Members of a Class](../core/accessing-nested-members-of-a-class.md).</span></span>  
  
```  
using Microsoft.RuleEngine;  
  
namespace RuleTypeCasting  
{  
    class Cls1  
    {  
        //Note that return type is 'object', not Cls2  
        public object GetCls2Obj()  
        {  
            return new Cls2();  
        }  
    }  
  
    class Cls2  
    {  
        public void Log()  
        {  
            Console.WriteLine("In Cls2.Log method");  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            //Create the condition list IF 1 == 1  
            Equal eq = new Equal(new Constant(1), new Constant(1));  
  
            //Create the action collection  
            ActionCollection ac = new ActionCollection();  
  
            //Create the class binding for the Cls1 class  
            ClassBinding cbCls1 = new ClassBinding(typeof(Cls1));  
  
            //Create the class member binding for the GetCls2Obj method in the Cls1 class  
            ClassMemberBinding cmGetCls2Obj = new ClassMemberBinding("GetCls2Obj", cbCls1);  
  
            //Type casting the return value of GetCls2Obj method (object) to Cls2 type  
            cmGetCls2Obj.Cast(typeof(Cls2));  
  
            //Create the class member binding to the Log method of Cls2 type   
            ClassMemberBinding cmLog = new ClassMemberBinding("Log", cmGetCls2Obj);  
  
            //Create a user function based on cmLog and add it to the action collection  
            UserFunction ufLog = new UserFunction(cmLog);  
            ac.Add(ufLog);  
  
            // Create the rule  
            Rule rl = new Rule("InvokeLogRule", eq, ac);  
  
            // Create the rule set or policy  
            RuleSet rs = new RuleSet("InvokeLogPolicy");  
            rs.Rules.Add(rl);  
  
            //Create the facts  
            Cls1 Cls1Obj = new Cls1();  
  
            //Execute the policy  
            PolicyTester tester = new PolicyTester(rs);  
            tester.Execute(Cls1Obj);  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="56279-108">参照</span><span class="sxs-lookup"><span data-stu-id="56279-108">See Also</span></span>  
 <span data-ttu-id="56279-109">[ビジネス ルール エンジンにおけるクラス継承のサポート](../core/support-for-class-inheritance-in-the-business-rule-engine.md) </span><span class="sxs-lookup"><span data-stu-id="56279-109">[Support for Class Inheritance in the Business Rule Engine](../core/support-for-class-inheritance-in-the-business-rule-engine.md) </span></span>  
 [<span data-ttu-id="56279-110">クラスの入れ子メンバーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="56279-110">Accessing Nested Members of a Class</span></span>](../core/accessing-nested-members-of-a-class.md)