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
# <a name="how-to-create-a-fact-creator"></a>ファクト作成コンポーネントを作成する方法
ファクトのインスタンスを作成するファクト作成コンポーネントを記述することができます。 ファクト作成コンポーネントを実装する必要があります**IFactCreator**とその**CreateFacts**メソッドと**GetFactTypes**メソッド。 ファクト作成コンポーネントの dll を作成した後、ポリシー テスター内から参照できます。 次は、ファクトの作成者の実装の例です。  
  
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