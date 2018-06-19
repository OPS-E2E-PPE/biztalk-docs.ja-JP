---
title: オーケストレーションでのトランザクションのプロパティを構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 9164a9f5670a996a62450a19d802c97b89d8e242
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248818"
---
# <a name="how-to-configure-transactional-properties-on-an-orchestration"></a>オーケストレーションでのトランザクションのプロパティを構成する方法
オーケストレーションは、アトミック トランザクション、長時間トランザクション、またはそのどちらでもないものとして扱うことができます。  
  
### <a name="to-make-your-orchestration-an-atomic-transaction"></a>オーケストレーションをアトミック トランザクションにするには  
  
1.  オーケストレーションの種類 ウィンドウで、選択**オーケストレーションのプロパティ**です。  
  
2.  [プロパティ] ウィンドウで選択**Atomic**のドロップダウン リストで、**トランザクション タイプ**プロパティです。  
  
     **バッチ**、**補正**、**分離レベル**、**再試行**、**タイムアウト**、および**トランザクション識別子**任意のスコープの場合と同様に、[プロパティ] ウィンドウでプロパティとして表示されます。 これらのプロパティの詳細については、次を参照してください。[スコープ図形を構成する方法](../core/how-to-configure-the-scope-shape.md)です。  
  
### <a name="to-make-your-orchestration-a-long-running-transaction"></a>オーケストレーションを長時間トランザクションにするには  
  
1.  オーケストレーションの種類 ウィンドウで、選択**オーケストレーションのプロパティ**です。  
  
2.  [プロパティ] ウィンドウで選択**長時間**のドロップダウン リストで、**トランザクション タイプ**プロパティです。  
  
     **補正**、**タイムアウト**、および**トランザクション識別子**プロパティ ウィンドウでプロパティとして表示されます。 これらのプロパティは、スコープと同様です。 これらのプロパティの詳細については、次を参照してください。[スコープ図形を構成する方法](../core/how-to-configure-the-scope-shape.md)です。  
  
## <a name="see-also"></a>参照  
 [トランザクション オーケストレーションを行う](../core/making-orchestrations-transactional.md)