---
title: 式を使用する図形 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Expression Editor, shapes
- Decide shape [Orchestration Designer], expressions
- Message Assignment shape [Orchestration Designer], expressions
- Filter Expression property
- Listen shape [Orchestration Designer], expressions
- Delay shape [Orchestration Designer], expressions
- shapes, expressions
- Receive shape [Orchestration Designer], expressions
- Loop shape [Orchestration Designer], expressions
- Rule shape [Orchestration Designer]
ms.assetid: 0d27f711-ff7c-422b-b231-aa3c9a42ed0c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 719ada151b3a9efaaea51fff84579b79579bd68d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393174"
---
# <a name="shapes-that-take-expressions"></a>式を使用する図形
オーケストレーション デザイナでいくつかの図形を含む**判断**と**ループ**、分岐を制御するルールを作成、ブール式を使用します。 その他の図形は、他の目的で式を使用します。 作成したり、BizTalk 式エディターを使用してこれらの図形の式を編集することができます。  
  
 次の表では、オーケストレーション デザイナーで式を使用する図形し、それらの式に対して有効なデータ型を示します。  
  
|図形|式の使用の説明|有効な式のデータ型|  
|-----------|-----------------------------------|---------------------------------|  
|**決定**|**決定**図形を含める**ルール**図形で、ブール式を使用します。|ブール値|  
|**受信**|**受信**アクティブ化プロパティが使用を True に設定されている図形、**フィルター式**受信メッセージをフィルター選択するプロパティ。 このプロパティの式は、受信メッセージをそのまま使用するかどうかを示す値を持つブール値に評価する必要があります。<br /><br /> **フィルター式** ダイアログ ボックスを使用してフィルター式を作成します。|ブール値|  
|**ループ**|A**ループ**図形が必要です、**ルール**図形で、さらに、ブール式を含める必要があります。|ブール値|  
|**Rule**|**ルール**図形 (「分岐」図形として処理領域に表示されます) には、単純な図形であり、ブール式を含み、他の (複雑な) 図形内で分岐を制御するために使用します。|ブール値|  
|**リッスン**|各分岐を**リッスン**図形が含まれている、少なくともいずれかを**受信**のみのフィルター式をブール式を使用して、図形 (エントリを参照**受信**)、または**遅延**図形が使用される、 **System.DateTime**オブジェクトまたは**System.TimeSpan**オブジェクト。|ブール値、System.DateTime、System.TimeSpan|  
|**遅延**|使用される式を**遅延**に図形を評価する必要があります、 **System.DateTime** 、期限を表現するオブジェクト、または**System.TimeSpan**期間のオブジェクト。|System.DateTime, System.TimeSpan|  
|**メッセージの割り当て**|内の式を**メッセージの割り当て**図形がメッセージに値を割り当てます。 割り当てられている値は、通常、メッセージが割り当てられているのに、任意の型を指定できます。|Any|  
|**[式]**|**式**図形では、オーケストレーションに任意の式を入力することができます。 たとえば、外部プログラムを実行する .NET 呼び出しを行うまたは単に、オーケストレーション変数の値を操作できます。|Any|  
  
## <a name="in-this-section"></a>このセクションの内容  
 [式図形を使用する方法](../core/how-to-use-expression-shape.md)  
  
## <a name="see-also"></a>参照  
 [式の要件と制限](../core/requirements-and-limitations-for-expressions.md)   
 [メッセージの構築](../core/constructing-messages.md)   
 [フロー制御図形の構成](../core/configuring-flow-control-shapes.md)