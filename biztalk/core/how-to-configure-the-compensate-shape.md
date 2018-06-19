---
title: 補正図形を構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Compensate shape [Orchestration Designer], about Compensate shape
- Compensate shape [Orchestration Designer]
- compensations, Compensate shape [Orchestration Designer]
- configuring [Orchestration Designer], Compensate shape
- Compensate shape [Orchestration Designer], configuring
ms.assetid: 9f06289e-4d11-4864-9851-c210276865a7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 059ac58d95d33234737033c00c4a6a2a36e256f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248282"
---
# <a name="how-to-configure-the-compensate-shape"></a>補正図形を構成する方法
追加できるかどうか、オーケストレーションで入れ子になったトランザクションを使っている場合、**補正**補正ブロックまたはトランザクション スコープの例外ブロックに図形です。 これにより、入れ子にされたトランザクションに対して、オーケストレーション内で明示的に補正を実行することができます。 補正するトランザクションを指定する、**補正**形状、および入れ子になったトランザクション内のすべての補正コードが実行される正常にコミットされたトランザクションを提供します。  
  
> [!NOTE]
>  **補正**プロパティは、トランザクション スコープの一意の識別子を参照; はスコープの名前を参照していません。  
  
 1 つ以上の入れ子になったトランザクションを補正する場合は、追加する**補正**トランザクションごとの図形です。  
  
 いいえ**補正**図形は外側のトランザクションに他の補正コードがない場合に必要です。 入れ子になったトランザクションの補正コードを自動的に実行されます。 **補正**図形を使用すると入れ子になったトランザクションを補正するかどうかを決定することにより、プロセスを制御します。  
  
### <a name="to-configure-a-compensate-shape"></a>補正図形を構成するには  
  
-   [プロパティ] ウィンドウでからを呼び出す補正ブロックを選択、**補正**ドロップダウン リスト。  
  
     ドロップダウン リストには、補正可能なすべてのトランザクションが表示されます。これには、現在のトランザクションと、現在のトランザクション直下の子トランザクションも含まれます。 目的のトランザクションが表示されない場合は、トランザクションの関係が原因である可能性があります。  
  
    > [!NOTE]
    >  現在のトランザクションの本体の中からトランザクションを補正することはできません。  補正は、トランザクションの補正ブロックまたは例外ブロックから行います。  
  
     現在のトランザクションの補正を選択した場合は、明示的な補正ブロックではなく (存在する場合)、既定のハンドラーが呼び出されます。 これは、直接入れ子にされている、正常に完了したトランザクションを、自動的に補正するためのメカニズムです。