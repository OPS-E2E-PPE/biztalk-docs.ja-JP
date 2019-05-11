---
title: 並列アクション図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Parallel Actions shape [Orchestration Designer], Terminate shape [Orchestration Designer]
- Parallel Actions shape [Orchestration Designer], synchronizing data access
- Parallel Actions shape [Orchestration Designer]
- configuring [Orchestration Designer], Parallel Actions shapes
- Parallel Actions shape [Orchestration Designer], branching
- Parallel Actions shape [Orchestration Designer], about Parallel Actions shape
- Terminate shape [Orchestration Designer], Parallel Actions shape [Orchestration Designer]
- Parallel Actions shape [Orchestration Designer], configuring
ms.assetid: 396d6182-f5dd-4aab-9edc-92efe236fd3e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3179995031ea91243f602d554808c198863f2c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386018"
---
# <a name="how-to-configure-the-parallel-actions-shape"></a>並列アクション図形を構成する方法
![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")  
並列アクション図形  
  
> [!CAUTION]
>  配置した場合、 **Terminate**図形内、**並列アクション**形状、および分岐を**Terminate**で実行されて、インスタンスが、すぐに完了に関係なくかどうか他の分岐の実行が完了します。 設計によって結果予測できないここでします。  
  
## <a name="synchronization-of-data-access"></a>データ アクセスの同期  
 その 1 つ以上のブランチの**並列アクション**図形は、同じデータにアクセスしようとしています。 エラーを回避するには、同期スコープ内のデータにアクセスするすべての図形を配置します。 プロパティで指定することができます、**スコープ**同期または同期されていない、という図形。 詳細については、次を参照してください。[スコープ](../core/scopes.md)します。  
  
#### <a name="to-add-a-branch-to-a-parallel-actions-shape"></a>並列アクション図形に分岐を追加するには  
  
1.  右クリックし、**並列アクション**図形をクリックして**新しい並列分岐**します。  
  
     - または -  
  
2.  既存の 2 つの分岐の間には、新しい図形をドラッグします。  
  
> [!NOTE]
>  分岐を削除する、**並列アクション**図形を削除するをクリックする分岐を右クリックして**削除**します。