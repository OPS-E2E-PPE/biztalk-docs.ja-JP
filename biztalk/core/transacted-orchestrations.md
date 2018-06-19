---
title: オーケストレーションをトランザクション |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, compensations
- orchestrations, transactional
- Transaction Type property
ms.assetid: c4f0b6ca-d939-4d3a-b7ef-53c6aafdea9c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8c6fb466e0c3cc5cae4a076237d1dbc970b5794
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278738"
---
# <a name="transacted-orchestrations"></a>トランザクション オーケストレーション
オーケストレーションは、スコープと同様にトランザクションになることができます。 実際、オーケストレーションそのものをスコープと見なすことができます。 一般的に、トランザクションの対象であるオーケストレーションには、トランザクションの対象であるスコープと同じルールが適用されます。  
  
> [!NOTE]
>  オーケストレーションとその他のスコープの違いとして、オーケストレーションには例外ハンドラーがないという点があります。  
  
## <a name="orchestration-compensation"></a>オーケストレーションの補正  
 場合、**トランザクション タイプ**、オーケストレーションのプロパティが長時間またはアトミック、選択することも、値を**補正**プロパティで、既定またはカスタム指定できます。  
  
 選択した場合**カスタム**、補正、**補正**と共に、オーケストレーション デザイン画面にタブが表示されます。 このタブの表示はオーケストレーション デザイン画面と同じで、図形やポートも同じように追加できます。  
  
 補正は、他のオーケストレーションから呼び出された場合にのみオーケストレーションで実行されます。 使用して特定のオーケストレーション インスタンスを補うことができます、**識別子**プロパティを**オーケストレーションの呼び出し**図形です。  
  
> [!IMPORTANT]
>  最上位のオーケストレーションに存在する補正は、ランタイム エンジンにより無視されます。  
  
## <a name="see-also"></a>参照  
 [トランザクション オーケストレーションを行う](../core/making-orchestrations-transactional.md)   
 [トランザクションを使用して、例外の処理](../core/using-transactions-and-handling-exceptions.md)