---
title: 基本的なオーケストレーション Design2 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, design
ms.assetid: fcdcb232-6a8f-41f3-b863-3b9e2cda28e3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 713d37d2736b8fac4563b098572dd9e49a3fd634
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="basic-orchestration-design"></a>基本的なオーケストレーション デザイン
基本的なオーケストレーションを作成すると、オーケストレーションの受信ポートで XML を受信します。 その XML をバックエンド システムに送信して処理します。 バックエンド システムで例外が発生した場合はオーケストレーションが停止されることがあります。 生成される例外には、完了しなかったオーケストレーションの情報が示されます。  
  
 障害が発生すると、呼び出しが中断されます。 イベント ビューアー ログで、エラーとその原因を表示できます。  
  
 オーケストレーションが中断状態にならないようにし、エラーをリダイレクトするには、CatchExpression を作成します。 バックエンドで生成される例外をトラップし、問題の原因の特定に役立てるには、オーケストレーションでスコープ図形を使用します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling3.md)