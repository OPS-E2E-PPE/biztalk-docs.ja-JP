---
title: "並列アクション図形を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 125d479a09eefb6771a884d2cddbfa98f34aeb36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-parallel-actions-shape"></a>並列アクション図形を構成する方法
![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")  
並列アクション図形  
  
> [!CAUTION]
>  配置した場合、 **Terminate**図形内、**並列アクション**図形とで、分岐、 **Terminate**では、実行、インスタンスが、すぐに完了に関係なくかどうか、他の分岐の実行が完了します。 デザイン方法によっては、この場合の結果が予測できないものになる可能性があります。  
  
## <a name="synchronization-of-data-access"></a>データ アクセスの同期  
 可能であればその複数の 1 つの分岐、**並列アクション**図形は、同じデータにアクセスしようとしています。 エラーを回避するため、データにアクセスする図形を同期スコープ内に配置します。 プロパティで指定できます、**スコープ**図形ことが同期されているまたは同期されていません。 詳細については、次を参照してください。[スコープ](../core/scopes.md)です。  
  
#### <a name="to-add-a-branch-to-a-parallel-actions-shape"></a>並列アクション図形に分岐を追加するには  
  
1.  右クリックし、**並列アクション**図形をクリックして**新しい並列分岐**です。  
  
     - または -  
  
2.  新しい図形を既存の 2 つの分岐の間にドラッグします。  
  
> [!NOTE]
>  分岐を削除する、**並列アクション**図形をクリックして、削除する分岐を右クリックして**削除**です。