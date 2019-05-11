---
title: ビジネス ルールで同じ種類の複数のオブジェクトを分析する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, multiple types
- Business Rules Framework, programming
ms.assetid: ff9790c1-13b0-4eee-8cac-d4f25ef5f0b7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1060de077a8b526db6c226786b23781da1f7421
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342938"
---
# <a name="how-to-analyze-multiple-objects-of-the-same-type-in-a-business-rule"></a>ビジネス ルールで同じ種類の複数のオブジェクトを分析する方法
多くのシナリオでは、型に対してビジネス ルールを作成し、個別に分析され、ルールによって処理するエンジンにアサートされる型の各インスタンスします。 一部のシナリオでただし、することをルールで同時に指定された型の複数のインスタンスを分析します。  
  
 インスタンスを使用するルールを例にとってみましょう、 **FamilyMember**クラス。  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember.Role == Son  
AND FamilyMember.Surname == FamilyMember.Surname  
THEN FamilyMember.AddChild(FamilyMember)  
```  
  
 ルールを識別、 **FamilyMember**インスタンス化されている、**父親**とは別のインスタンスを**Son**します。 インスタンスが姓で関連付けられている場合、 **Son**インスタンスが Father インスタンス上の子オブジェクトのコレクションに追加されます。 各**FamilyMember**インスタンスがルールで個別に分析された、ため、このルールは起動しませんこのシナリオで、 **FamilyMember**は 1 つのロール:**父親**または**Son**します。  
  
 そのため、複数のインスタンスは、ルールでまとめて分析される必要がありますをルール内の各インスタンスの id を区別する手段が必要、エンジンに示す必要があります。 **インスタンス ID**プロパティを使用して、この機能を提供します。 このフィールドはファクトをファクト エクスプ ローラーで選択した場合、[プロパティ] ウィンドウで使用します。 ルールにファクトまたはメンバーをドラッグする前に、フィールドの値を変更する必要があります。  
  
 使用して、**インスタンス ID**プロパティ、ルールが再構築されます。 使用して、それらのルールの引数の**Son**のインスタンス**FamilyMember**、**インスタンス ID**フィールドが 0 ~ 1 の既定値から変更します。 インスタンス ID が 0 から変更された、ファクトまたはメンバーがルール エディターにドラッグされると、インスタンス ID の値に表示、ルール、クラスを。  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember(1).Role== Son  
AND FamilyMember.Surname == FamilyMember(1).Surname  
THEN FamilyMember.AddChild(FamilyMember(1))  
```  
  
 ここで、ある、**父親**インスタンスと**Son**インスタンスはエンジンにアサートされます。 エンジンのインスタンスのさまざまな組み合わせに対して、ルールが評価されます。 仮定すると、**父親**と**Son**インスタンスがある同じ姓で、 **Son**インスタンスに追加されます、**父親**インスタンスとして対象としています。  
  
> [!NOTE]
>  **インスタンス ID**は特定の規則の評価のコンテキスト内でのみ使用します。 ポリシーの実行の間でオブジェクトのインスタンスにいない貼付されているし、オブジェクトがアサートされる順序は無関係です。 各オブジェクトのインスタンスは、その型のすべてのルールの引数で評価されます。