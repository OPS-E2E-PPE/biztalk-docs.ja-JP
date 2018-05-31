---
title: 基本的なオーケストレーション Design1 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, design
ms.assetid: fd2e1d89-6230-4634-8a33-1cda26fd55f5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d302428cd713b826e7c4629ea75eb6f6268d7400
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230698"
---
# <a name="basic-orchestration-design"></a>基本的なオーケストレーション デザイン
基本的なオーケストレーションを作成するときに、オーケストレーションの受信ポートに XML が表示されます。 その XML をバックエンド システムに送信して処理します。 バックエンド システムで例外が発生した場合はオーケストレーションが停止し、エラーが生成されます。 生成される例外は、オーケストレーションが完了しませんでした情報を提供します。  
  
 ![](../core/media/jdeoneworld-01.gif "JdeOneWorld_01")  
例外処理  
  
 障害が発生すると、呼び出しが中断されます。 イベント ビューアー ログで、エラーとその原因を表示できます。  
  
 オーケストレーションが中断状態にならないようにし、エラーをリダイレクトするには、CatchExpression を作成します。 バックエンド システムによって生成される例外をトラップし、問題の原因の特定に役立てるにすることができますを使用する、**スコープ**オーケストレーションの図形です。  
  
 ![](../core/media/jdeoneworld-02.gif "JdeOneWorld_02")  
例外処理の全体図  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling1.md)