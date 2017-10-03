---
title: "式を使用する図形 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e78ada2c69205a0201c4bae9f3c7fa5b0656fa7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="shapes-that-take-expressions"></a>式を使用する図形
オーケストレーション デザイナーで、複数の図形を含む**判断**と**ループ**、分岐を制御するルールを作成、ブール式を使用します。 他の図形は、それぞれ他の目的で式を使用します。 BizTalk 式エディターを使用して、これらの図形の式を作成または編集できます。  
  
 次の表は、オーケストレーション デザイナーで式を使用する図形とそれらの式に対して有効なデータ型を示しています。  
  
|図形|式の使用方法の説明|有効な式のデータ型|  
|-----------|-----------------------------------|---------------------------------|  
|**決定**|**決定**図形を含める**ルール**図形で、ブール式を使用します。|ブール値|  
|**受信**|**受信**、"アクティブ化"プロパティが設定された場合は True。 使用する図形、**フィルター式**受信メッセージをフィルター選択するプロパティです。 このプロパティの式は、ブール値として評価される必要があります。この値は、受信メッセージを受け付けるかどうかを決定します。<br /><br /> **フィルター式** ダイアログ ボックスを使用してフィルター式を作成します。|ブール値|  
|**ループ**|A**ループ**図形が必要です、**ルール**図形で、さらに、ブール式を含める必要があります。|ブール値|  
|**Rule**|**ルール**(「分岐」図形として処理領域に表示されます) 図形は、ブール式が含まれており、その他の (複雑な) 図形内で分岐を制御するために使用する単純な図形です。|ブール値|  
|**リッスン**|各分岐は**リッスン**図形が含まれているには、少なくともいずれか、**受信**のみのフィルター式はブール式を使用する図形 (のエントリを参照してください**受信**)、、または**遅延**図形を使用して、 **System.DateTime**オブジェクトまたは**System.TimeSpan**オブジェクト。|ブール値、System.DateTime、System.TimeSpan|  
|**遅延**|使用される式、**遅延**に図形を評価する必要があります、 **System.DateTime** 、期限のオブジェクトまたは**System.TimeSpan**期間を表すためのオブジェクト。|System.DateTime、System.TimeSpan|  
|**メッセージの割り当て**|内の式、**メッセージの割り当て**図形がメッセージに値を割り当てます。 割り当てられる値は、通常はメッセージですが、任意のデータ型も使用できます。|Any|  
|**[式]**|**式**図形では、オーケストレーションに任意の式を入力することができます。 たとえば、外部プログラムに対して .NET 呼び出しを行ったり、オーケストレーション変数の値を操作できます。|Any|  
  
## <a name="in-this-section"></a>このセクションの内容  
 [式図形を使用する方法](../core/how-to-use-expression-shape.md)  
  
## <a name="see-also"></a>参照  
 [式の要件と制限](../core/requirements-and-limitations-for-expressions.md)   
 [メッセージの構築](../core/constructing-messages.md)   
 [フロー制御図形を構成します。](../core/configuring-flow-control-shapes.md)