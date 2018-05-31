---
title: 複数の注文のアイテムを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, multiple calls
- JD Edwards OneWorld adapters, multi-order numbers
- multiple edit line calls [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], multi-order numbers
- multi-order numbers [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], multiple calls
ms.assetid: 207ea92c-03f7-4117-8414-eb174e659d26
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 389e73ede2d1062c9907bd8640f38ce74ad6f316
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287258"
---
# <a name="using-multi-order-items"></a>複数の注文項目の使用
JD Edwards OneWorld API の構造により、BizTalk Server で複数の注文番号を使用する場合は、オーケストレーションで複数の編集行呼び出しを行い、それらの品目をオーケストレーションに追加する必要があります。 たとえば、複数の注文番号の品目には、1 つの注文番号のヘッダーと、複数品目の注文を含む詳細が含まれていることがあります (Toy 1EA、Gloves 2EA など)。  
  
 複数の編集行呼び出しを使用するには、BizTalk Server の開発者がそれらを構造化する必要があります。 開発者は、オーケストレーションで内部ループを作成して、この呼び出しを行います。  
  
 JD Edwards OneWorld システムでは、複数の編集行呼び出しがサポートされますが、API ではサポートされません。 編集行メソッドの構造を確認すると、シーケンス構造ではなくフラットな構造になっています。 したがって、品目を挿入するたびに関数を呼び出す必要があります。  
  
## <a name="see-also"></a>参照  
 [計画とアーキテクチャ](../core/planning-and-architecture17.md)