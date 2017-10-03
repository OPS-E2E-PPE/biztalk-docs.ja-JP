---
title: "補正ブロックを追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- compensations, compensation blocks
- compensation blocks, adding
ms.assetid: 1bdeed92-3144-44ef-ad0d-1c6976f46a36
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2dec4f4dd01c2bbf522dfff44ec8aaf0c2f5e89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-compensation-block"></a>補正ブロックを追加する方法
独自の補正コードを追加しなければ、ランタイム エンジンにより、現在のトランザクション内に入れ子にされたトランザクションの補正を呼び出す既定の補正が実行されます。 最初に最近完了したトランザクションの補正が呼び出され、すべての入れ子になったトランザクションが完了するまで、古いものへ順番に処理されます。  
  
 これは true を保持すると、補正が行われるループ図形内部の: 補正は逆の順序で実行されます。 最初にループの最後の繰り返し処理の補正が呼び出され、その次にその前の繰り返し処理の補正が呼び出され、その後も同様に続きます。  
  
> [!CAUTION]
>  データが処理のために補正の物理メモリに維持されるため、ループの内側で補正を使用すると、パフォーマンスに影響を与える可能性があり、繰り返し処理が大量に存在する場合は問題になる可能性があります。  
  
 既定の順序が要件に適合しない場合は、指定した順序で入れ子になったスコープの補正ハンドラーを明示的に呼び出す独自の補正ハンドラーを記述できます。  
  
### <a name="to-add-a-compensation-block"></a>補正ブロックを追加するには  
  
1.  右クリックし、**スコープ**図形を追加するトランザクションを**補正ブロック**、クリックして**新しい補正ブロック**です。  
  
    > [!NOTE]
    >  追加する、**補正ブロック**を**スコープ**図形、**トランザクション タイプ**のプロパティ、**スコープ**に図形を設定する必要があります**アトミック**または**実行時間が長い**です。  
  
     A**補正ブロック**が関連付けられている直後のオーケストレーションに追加**スコープ**図形です。  
  
2.  内部、**補正ブロック**図形の図形を追加して、コミットしたトランザクションを元に戻すためのプロセスを作成します。