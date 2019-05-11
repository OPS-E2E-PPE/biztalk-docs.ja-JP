---
title: 基本的なオーケストレーション Design1 |Microsoft Docs
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
ms.openlocfilehash: 6bfe5f4bce42fbffb7a0496b296f95b20be429d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358380"
---
# <a name="basic-orchestration-design"></a>基本的なオーケストレーション デザイン
基本的なオーケストレーションを作成するときに、オーケストレーションの受信ポートに XML が表示されます。 XML は、処理するバックエンド システムに送信されます。 バックエンド システムで、例外が発生する可能性があります、オーケストレーションを停止し、エラーが生成される可能性があります。 生成される例外は、オーケストレーションが完了しなかった情報を提供します。  
  
 ![](../core/media/jdeoneworld-01.gif "JdeOneWorld_01")  
例外処理  
  
 エラーが発生したときに、呼び出しは中断されます。 イベント ビューアー ログでは、エラーと失敗の理由を表示できます。  
  
 中断状態からオーケストレーションをしないようにして、エラーをリダイレクトする、CatchExpression を作成できます。 使用できる、バックエンド システムによって生成された例外をトラップして、問題の原因の特定を支援する、**スコープ**オーケストレーションの図形。  
  
 ![](../core/media/jdeoneworld-02.gif "JdeOneWorld_02")  
例外処理の合計  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling1.md)