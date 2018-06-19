---
title: ビジネス プロセス管理ソリューションでの処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, process management solutions
ms.assetid: 0b26447e-d8f1-4084-aa34-6e7f8ffccea5
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 145dd8e616048f1caaa1a59ec41d099e93e47880
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264602"
---
# <a name="processing-in-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションでの処理
このセクションでは、ビジネス プロセス管理ソリューションのしくみについて説明します。、注文の処理方法、割り込みとため例外を処理する方法を使用するその操作方法により再試行できます。  
  
 注文処理は、2 つの主なオーケストレーションに依存しています**OrderBroker**と**OrderManager**です。 **OrderBroker**複数の ordermanager オーケストレーション、注文の種類ごとに 1 つができるように、オーケストレーションが書き込まれます。 ソリューション内に 1 つだけ**OrderManager**です。 他の種類の注文に適応させる方法としても比較的一般的です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [OrderBroker オーケストレーションでの処理](../core/processing-in-the-orderbroker-orchestration.md)  
  
-   [プロセス マネージャのロジック](../core/process-manager-logic.md)  
  
-   [注文処理ステージでの処理](../core/processing-in-the-order-processing-stages.md)  
  
-   [ビジネス プロセス管理ソリューションでの処理を中断します。](../core/interrupt-handling-in-the-business-process-management-solution.md)  
  
-   [ビジネス プロセス管理ソリューションでの例外処理](../core/exception-handling-in-the-business-process-management-solution.md)