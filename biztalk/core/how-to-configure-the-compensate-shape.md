---
title: 補正図形を構成する方法 |Microsoft Docs
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
ms.openlocfilehash: e04ffee84b47a6a4e5520ece823575b030ccd6ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341018"
---
# <a name="how-to-configure-the-compensate-shape"></a>補正図形を構成する方法
追加できるかどうか、オーケストレーションで入れ子になったトランザクションを使っている場合、**補正**補正ブロックまたはトランザクション スコープの例外ブロックに図形。 これにより、オーケストレーションを明示的に補正を入れ子になったトランザクションを実行できます。 補正するトランザクションを指定する、**補正**図形、および入れ子になったトランザクションの補正コードが動作する、正常にコミットされたトランザクションを提供します。  
  
> [!NOTE]
>  **補正**プロパティは、トランザクション スコープの一意の識別子を参照; はスコープの名前を参照していません。  
  
 さらに追加する 1 つ以上の入れ子になったトランザクションを補正する場合は、**補正**トランザクションごとの図形。  
  
 いいえ**補正**図形が必要なは、外側のトランザクションに他の補正コードがない場合は、入れ子になったトランザクションの補正コードを自動的に実行されます。 **補正**図形で入れ子になったトランザクションを補正するかどうかを決定することにより、プロセスを細かく制御できます。  
  
### <a name="to-configure-a-compensate-shape"></a>補正図形を構成するには  
  
-   [プロパティ] ウィンドウから呼び出す補正ブロックを選択します。、**補正**ドロップダウン リスト。  
  
     すべての現在のトランザクションと、現在のトランザクション直下の子トランザクションを含むトランザクション、補正可能がドロップダウン リストが表示されます。 予想されるトランザクションを表示されない場合は、トランザクションの関係が原因が考えられます。  
  
    > [!NOTE]
    >  トランザクションの本体内から現在のトランザクションを補正することはできません。  補正ブロックまたはトランザクションの例外ブロックからそれを補うことができます。  
  
     (1 つである) 場合、既定のハンドラーが呼び出されることを表す、現在のトランザクションと明示的な補正ブロックではないを補正する場合。 これは、自動的に正常に完了した直接入れ子になったトランザクションを補正するためのメカニズムです。