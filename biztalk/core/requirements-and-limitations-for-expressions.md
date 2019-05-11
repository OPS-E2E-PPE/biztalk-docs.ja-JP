---
title: 式の要件と制限 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Expression Editor, about Expression Editor
- Expression Editor, requirements
- Orchestration Designer, Expression Editor
- Expression Editor, limitations
- Expression Editor
- Expression Editor, Orchestration Designer
ms.assetid: 1e0353d3-c2f3-4c10-86e3-8620e62dd0d5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 250e262470325318a62236630542fd96ff0d4b52
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394830"
---
# <a name="requirements-and-limitations-for-expressions"></a>式の要件と制限
オーケストレーション デザイナーの BizTalk 式エディターは、IntelliSense を備えた標準の Visual Studio テキスト エディターです。 BizTalk 式エディターは、テキスト形式で式を入力するために使用します。  
  
 テキスト形式で 1 つの式を入力するには、テキスト ボックスを使用します。 1 つの式を複数行に記述できますが、行を 1 つのセミコロンで終了する必要があります。  
  
 以下は、BizTalk 式エディターで式を使用するときの制限事項の一覧です。  
  
- "+="、"-="、"*=" などの複合代入はサポートされていません。  
  
- 1 つのステートメントでの複数の代入演算子の使用は、サポートされていません。  
  
- "if" または "while" の述語内での代入は、サポートされていません。  
  
- インクリメントおよびデクリメントはサポートされていません。 たとえば、"++" や "--" などです。  
  
- メッセージ部分の場合、パブリック メソッド、入れ子になっている型、静的データ フィールド、Microsoft.XLANGs.BaseTypes.DistinguishedFieldAttribute によって注釈が付けられた読み取り専用の .NET プロパティ、すべてのパブリック データ フィールド、および読み取り専用ではない .NET プロパティについては、メンバー アクセスが許可されます。  
  
- インデクサーまたはパラメーター化された .NET プロパティはサポートされていません。  
  
- デリゲートおよびイベントはサポートされていません。  
  
- ジェネリックはサポートされていません。  
  
- "foreach"、"for"、"do-while"、"break"、"continue" などのフロー制御構文は、サポートされていません。  
  
- 三項演算はサポートされていません。 たとえば、"?:" などです。  
  
- 式図形にコメントを追加できますが、式図形には少なくとも 1 つのステートメントが含まれている必要があります。  
  
- 配列はサポートされていません。  
  
- 式図形をメッセージの構築図形の中に配置するときは、制御フローを実行できません。 たとえば、"if-then-else" や "while" などです。  
  
- すべての有効な式ステートメントの形式は以下のとおりです。  
  
  -   ドット形式の名前 = 式;  
  
  -   ドット形式の名前 = 式;  
  
  BizTalk 式エディターを使用すると複雑な式を簡単かつすばやく入力できますが、任意の大きさのコードを入力することはできません。 これは、ビジネス プロセスのコードを実装コードから分離しておくためです。