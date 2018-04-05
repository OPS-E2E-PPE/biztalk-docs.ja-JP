---
title: 基本的なオーケストレーション Design4 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, design
ms.assetid: 53f90bba-5786-49ca-b4d0-21601ec04045
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80a1ed1359370c6b048ed7e0753cd32f4ff787c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="basic-orchestration-design"></a>基本的なオーケストレーション デザイン
基本的なオーケストレーションを作成すると、オーケストレーションの受信ポートで XML を受信します。 次に、その XML をバックエンド システムに送信して処理します。 バックエンド システムで例外が発生した場合はオーケストレーションが停止されることがあります。 生成される例外には、完了しなかったオーケストレーションの情報が示されます。  
  
 障害が発生すると、呼び出しが中断されます。 イベント ビューアー ログで、エラーとその原因を表示できます。  
  
 オーケストレーションが中断状態にならないようにし、エラーをリダイレクトするには、CatchExpression を作成します。 バックエンドで生成される例外をトラップし、問題の原因の特定に役立てるには、オーケストレーションでスコープ図形を使用します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling4.md)