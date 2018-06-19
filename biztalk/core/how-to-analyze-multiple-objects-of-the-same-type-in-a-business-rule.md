---
title: ビジネス ルールで同じ種類の複数のオブジェクトを分析する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 2a1e4d2fb01513b1d4d314264ab74b84d3a0223a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248434"
---
# <a name="how-to-analyze-multiple-objects-of-the-same-type-in-a-business-rule"></a>ビジネス ルールで同じ種類の複数のオブジェクトを分析する方法
多くのシナリオでは、さまざまな種類のビジネス ルールが作成されます。また、エンジンにアサートされる各インスタンスの種類が個別に分析され、ルールに従って処理されることが期待されます。 ただし、場合によっては、特定の種類の複数のインスタンスをルールで同時に分析することがあります。  
  
 インスタンスを使用するルールがかかるなど、 **FamilyMember**クラスです。  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember.Role == Son  
AND FamilyMember.Surname == FamilyMember.Surname  
THEN FamilyMember.AddChild(FamilyMember)  
```  
  
 ルールを識別、 **FamilyMember**インスタンス化されている、 **Father**とは別のインスタンス、 **Son**です。 インスタンスが姓で関連付けられている場合、 **Son**インスタンスが Father インスタンス上の子のコレクションに追加します。 各**FamilyMember**インスタンスがルールで個別に分析された、ため、このルールは起動しませんこのシナリオでは、 **FamilyMember**のみが 1 つのロール:**Father**または**Son**です。  
  
 このため、複数のインスタンスがルールでまとめて分析されることをエンジンに示す必要があります。また、ルールの各インスタンスの ID を区別する手段が必要です。 **インスタンス ID**プロパティを使用して、この機能を提供します。 このフィールドは、ファクト エクスプローラーでファクトを選択する際のプロパティ ウィンドウで使用できます。 ファクトまたはメンバーをルールにドラッグする前に、フィールドの値を変更する必要があります。  
  
 使用して、**インスタンス ID**プロパティ、ルールが再構築されます。 これらのルールの引数を使用するため、 **Son**のインスタンス**FamilyMember**、**インスタンス ID**フィールドが 0 ~ 1 の既定値から変更します。 インスタンス ID は 0 から変更し、ファクトまたはメンバーがルール エディターにドラッグされるときにインスタンス ID の値に表示されます、ルール、クラスの後にします。  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember(1).Role== Son  
AND FamilyMember.Surname == FamilyMember(1).Surname  
THEN FamilyMember.AddChild(FamilyMember(1))  
```  
  
 ここで、あると想定、 **Father**インスタンスおよび**Son**インスタンスはエンジンにアサートされます。 エンジンは、インスタンスのさまざまな組み合わせに対して、ルールを評価します。 想定されるので、 **Father**と**Son**インスタンスがある同じ姓で、 **Son**インスタンスに追加されます、 **Father**インスタンスとして対象としています。  
  
> [!NOTE]
>  **インスタンス ID**は、特定の規則の評価のコンテキスト内でのみ使用します。 インスタンス ID は、ポリシーの実行中にオブジェクトのインスタンスに添付されません。また、オブジェクトがアサートされる順番との関連性はありません。 各オブジェクト インスタンスは、この種類に対するすべてのルールの引数で評価されます。