---
title: メッセージとインスタンスの追跡の計画 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HAT, planning
- planning, HAT
ms.assetid: 69b0d30e-77df-4847-9a59-6dd806152b71
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 506dcd8342b016b325544f63f95c76c87dcc0772
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263562"
---
# <a name="planning-for-message-and-instance-tracking"></a>メッセージとインスタンスの追跡の計画
プロジェクトを展開した後に追跡オプションを指定し、追跡データの量を制限して必要な情報だけを取得するために、計画段階中に追跡する情報を決定する必要があります。  
  
 メッセージにアクセスするたびに BizTalk Server のメッセージとサーバー インスタンスの追跡により別のコピーが作成されるので、すべてのメッセージを追跡するのは避けることをお勧めします。 たとえば、特定のポートだけを追跡して、範囲を絞り込むことができます。 これにより、システムのパフォーマンスを最大限に高め、データベースの整合性を維持できます。  
  
## <a name="see-also"></a>参照  
 [管理と追跡アーキテクチャ](../core/management-and-tracking-architecture.md)