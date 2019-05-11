---
title: オーケストレーションでのトランザクションのプロパティを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- atomic transactions
- orchestrations, transactions
- transactions, long-running
- orchestrations, configuring
- transactions, atomic
ms.assetid: 8eec6019-4d96-4ed6-8a90-9403738d8af4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c999ca7c487cdcf59fd29e76b3d466194aa8ee21
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385782"
---
# <a name="how-to-configure-transactional-properties-on-an-orchestration"></a>オーケストレーションでのトランザクションのプロパティを構成する方法
オーケストレーションは、アトミック トランザクション、実行時間の長いトランザクションの場合、またはそのどちらもとして扱うことができます。  
  
### <a name="to-make-your-orchestration-an-atomic-transaction"></a>オーケストレーションのアトミックのトランザクションを作成するには  
  
1.  オーケストレーションの種類 ウィンドウで次のように選択します。**オーケストレーションのプロパティ**します。  
  
2.  [プロパティ] ウィンドウで次のように選択します。**アトミック**のドロップダウン リストで、**トランザクション タイプ**プロパティ。  
  
     **バッチ**、**補正**、**分離レベル**、**再試行**、**タイムアウト**、および**トランザクション識別子**の任意のスコープと同じように、[プロパティ] ウィンドウでプロパティとして表示されます。 これらのプロパティの詳細については、次を参照してください。[スコープ図形を構成する方法](../core/how-to-configure-the-scope-shape.md)します。  
  
### <a name="to-make-your-orchestration-a-long-running-transaction"></a>オーケストレーションの実行時間の長いトランザクションを作成するには  
  
1.  オーケストレーションの種類 ウィンドウで次のように選択します。**オーケストレーションのプロパティ**します。  
  
2.  [プロパティ] ウィンドウで次のように選択します。**長時間**のドロップダウン リストで、**トランザクション タイプ**プロパティ。  
  
     **補正**、**タイムアウト**、および**トランザクション識別子**プロパティ ウィンドウでプロパティとして表示されます。 詳細について、これらのプロパティの任意のスコープと同様です。 これらのプロパティの詳細については、次を参照してください。[スコープ図形を構成する方法](../core/how-to-configure-the-scope-shape.md)します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションのトランザクション化](../core/making-orchestrations-transactional.md)