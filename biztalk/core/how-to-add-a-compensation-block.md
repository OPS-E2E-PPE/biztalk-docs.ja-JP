---
title: 補正ブロックを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- compensations, compensation blocks
- compensation blocks, adding
ms.assetid: 1bdeed92-3144-44ef-ad0d-1c6976f46a36
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ef3cce71a85b41ccfc4291f82c5736d77f15162
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343866"
---
# <a name="how-to-add-a-compensation-block"></a>補正ブロックを追加する方法
独自の補正を追加しない場合、ランタイム エンジンは、現在のトランザクション内で入れ子になったトランザクションの補正を呼び出す既定の補正を実行します。 まず、最近完了したトランザクションの補正が呼び出さし、すべての入れ子になったトランザクションが補正されてまで順番します。  
  
 これは true を保持すると、補正が行われるループ図形内部の: 補正を逆の順序で実行されます。 最初に、ループの最後の反復の補正が呼び出される、し、前のイテレーションの補正します。  
  
> [!CAUTION]
>  作業を補正の物理メモリにデータが永続化するためには、大きな反復数を指定します。 問題がありますパフォーマンスに影響ループ内で補正を使用して可能性があります。  
  
 既定の順序が、要件が収まらない場合を明示的に指定した順序で入れ子になったスコープの補正ハンドラーを呼び出す独自の補正ハンドラーを記述できます。  
  
### <a name="to-add-a-compensation-block"></a>補正ブロックを追加するには  
  
1.  右クリックし、**スコープ**図形を追加するトランザクションを**補正ブロック**、 をクリックし、**新しい補正ブロック**します。  
  
    > [!NOTE]
    >  追加する、**補正ブロック**を**スコープ**図形、**トランザクションの種類**のプロパティ、**スコープ**に図形を設定する必要があります**アトミック**または**実行時間が長い**します。  
  
     A**補正ブロック**が関連付けられている直後のオーケストレーションに追加**スコープ**図形。  
  
2.  内で、**補正ブロック**図形をトランザクションのコミットを元に戻すためのプロセスを作成する図形を追加します。