---
title: ビジネス プロセス管理ソリューションでの処理 |Microsoft Docs
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
ms.openlocfilehash: bf08892ff975348624eec4548d0895ef5f3221b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299828"
---
# <a name="processing-in-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションでの処理
このセクションでは、ビジネス プロセス管理ソリューションのしくみについて説明します。 注文の処理、割り込みとため例外を処理する方法を使用して、そのアクションは、その方法を再試行できます。  
  
 注文処理の 2 つの主なオーケストレーションが依存**OrderBroker**と**OrderManager**します。 **OrderBroker**注文の種類ごとに 1 つずつ、複数の注文マネージャー オーケストレーションができるようにするため、オーケストレーションが書き込まれます。 ソリューションは、1 つだけ**OrderManager**します。 、、が比較的一般的な注文の他の種類に対応できるようにします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [OrderBroker オーケストレーションの処理](../core/processing-in-the-orderbroker-orchestration.md)  
  
-   [プロセス マネージャーのロジック](../core/process-manager-logic.md)  
  
-   [注文処理ステージでの処理](../core/processing-in-the-order-processing-stages.md)  
  
-   [ビジネス プロセス管理ソリューションの割り込み処理](../core/interrupt-handling-in-the-business-process-management-solution.md)  
  
-   [ビジネス プロセス管理ソリューションでの例外処理](../core/exception-handling-in-the-business-process-management-solution.md)