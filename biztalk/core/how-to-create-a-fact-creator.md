---
title: ファクト作成コンポーネントを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- GetFactTypes method
- CreateFacts method
- IFactCreator interface
- Business Rules Framework, code samples
- Business Rules Framework, fact creator
- Business Rules Framework, programming
ms.assetid: 0589be8e-34d6-4e55-b678-c1f8436d1f61
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9784be0a26fd6f5b60cf68401faf36e816b54c08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340045"
---
# <a name="how-to-create-a-fact-creator"></a><span data-ttu-id="5965e-102">ファクト作成コンポーネントを作成する方法</span><span class="sxs-lookup"><span data-stu-id="5965e-102">How to Create a Fact Creator</span></span>
<span data-ttu-id="5965e-103">ファクトのインスタンスを作成するファクト作成コンポーネントを記述することができます。</span><span class="sxs-lookup"><span data-stu-id="5965e-103">You can write a fact creator to create instances of your facts.</span></span> <span data-ttu-id="5965e-104">ファクト作成コンポーネントを実装する必要があります**IFactCreator**とその**CreateFacts**メソッドと**GetFactTypes**メソッド。</span><span class="sxs-lookup"><span data-stu-id="5965e-104">Your fact creator must implement **IFactCreator** and its **CreateFacts** method and **GetFactTypes** method.</span></span> <span data-ttu-id="5965e-105">ファクト作成コンポーネントの dll を作成した後、ポリシー テスター内から参照できます。</span><span class="sxs-lookup"><span data-stu-id="5965e-105">After you have created your fact creator dll, you can browse to it from within the policy tester.</span></span> <span data-ttu-id="5965e-106">次は、ファクトの作成者の実装の例です。</span><span class="sxs-lookup"><span data-stu-id="5965e-106">The following is an example of a fact creator implementation.</span></span>  
  
```  
public class MyFactCreator : IFactCreator  
{  
   private object[] myFacts;  
   public MyFactCreator()  
   {  
   }  
   public object[] CreateFacts ( RuleSetInfo rulesetInfo )  
   {  
      myFacts = new object[1];  
      myFacts.SetValue(new MySampleBusinessObject(),0);  
      return myFacts;  
   }  
   public Type[] GetFactTypes (RuleSetInfo rulesetInfo)  
   {  
      return null;  
   }  
}  
```