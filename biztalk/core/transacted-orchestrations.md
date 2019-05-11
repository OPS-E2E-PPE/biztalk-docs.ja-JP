---
title: オーケストレーションのトランザクション |Microsoft Docs
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
ms.openlocfilehash: 2607c6619391481870baa19b5cda07d7419f9dca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313292"
---
# <a name="transacted-orchestrations"></a>トランザクション オーケストレーション
オーケストレーションがトランザクション スコープと同じようにできます。 実際には、オーケストレーション自体と見なすスコープ。 一般に、トランザクションのスコープとオーケストレーションがトランザクションの場合と同じ規則が適用されます。  
  
> [!NOTE]
>  オーケストレーションとその他のスコープには 1 つの違いは、オーケストレーションに例外ハンドラーがないことです。  
  
## <a name="orchestration-compensation"></a>オーケストレーションの補正  
 場合、**トランザクション タイプ**プロパティ、オーケストレーションの実行時間の長いに設定されてまたはアトミックで選択することも、値、**補正**プロパティで、既定またはカスタムを指定できます。  
  
 選択した場合**カスタム**、補正、**補正** タブは、オーケストレーション デザイン画面と並んで表示されます。 クラスでは、オーケストレーション デザイン画面としての同じを参照し、追加できます図形とポートを同じ方法でします。  
  
 補正では、他のオーケストレーションによって呼び出されるオーケストレーションにのみ実行します。 使用して特定のオーケストレーション インスタンスを補うことができます、**識別子**プロパティを**オーケストレーションの呼び出し**図形。  
  
> [!IMPORTANT]
>  最上位のオーケストレーションの補正が存在する場合は、ランタイム エンジンによって無視されます。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションのトランザクション化](../core/making-orchestrations-transactional.md)   
 [トランザクションの使用と例外の処理](../core/using-transactions-and-handling-exceptions.md)