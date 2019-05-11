---
title: 式を作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, expressions [Expression Editor]
- opening, Expression Editor [Orchestration Designer]
- Expression Editor, opening
- editing, expressions [Expression Editor]
- Expression Editor, editing expressions
- Expression Editor, creating expressions
ms.assetid: 48f8b00f-6ef1-4145-ad17-15c95518fc8a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c96769a50de1626550409ef7e86ce0460fc3dd4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385484"
---
# <a name="how-to-create-expressions"></a>式を作成する方法
BizTalk 式エディタでは、さまざまなオーケストレーション デザイナーの図形の機能を拡張する xlang/s 式を作成することができます。 意思決定、遅延の設定、.NET を呼び出して、while ループ条件をテストする xlang/s 式を作成することができます。  
  
 メッセージまたはメッセージの割り当て図形のメッセージ部分に値を割り当てる、.NET 呼び出しを行い、内の変数の値を操作することができます、**式**図形。 複雑なブール式の構築に使用することもできます、**ループ**と**判断**図形で遅延を設定して、**遅延**図形。  
  
### <a name="to-open-biztalk-expression-editor"></a>BizTalk 式エディターを開く  
  
1.  右クリックし、**式**図形、**ループ**図形、**メッセージの割り当て**、図形、**遅延**図形、または、の分岐**判断**図形。  
  
2.  クリックして**式の編集**します。  
  
3.  BizTalk 式エディターが表示されます。  
  
### <a name="to-create-or-edit-an-expression"></a>作成または式を編集するには  
  
1.  入力するか、BizTalk 式エディターのテキスト フィールドの式を編集します。  
  
2.  [OK] をクリックします。 これにより、式が保存され、選択した図形に適用されます。  
  
## <a name="see-also"></a>参照  
 [XLANG-s 言語](../core/xlang-s-language.md)