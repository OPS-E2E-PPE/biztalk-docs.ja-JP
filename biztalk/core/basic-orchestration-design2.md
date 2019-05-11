---
title: 基本的なオーケストレーション Design2 |Microsoft Docs
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
ms.openlocfilehash: 4d9374606dcc1387c5ea18e420b894a1e85bef75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358343"
---
# <a name="basic-orchestration-design"></a>基本的なオーケストレーション デザイン
基本的なオーケストレーションを作成するときに、オーケストレーションの受信ポートで XML が表示されます。 XML は、処理するバックエンド システムに送信されます。 例外が発生する、バックエンド システムで、オーケストレーションを停止する可能性があります。 生成される例外は、オーケストレーションが完了しなかったの情報を提供します。  
  
 エラーが発生したときに、呼び出しは中断されます。 イベント ビューアー ログでは、エラーと失敗の理由を表示できます。  
  
 中断状態からオーケストレーションをしないようにして、エラーをリダイレクトする、CatchExpression を作成できます。 バック エンドによって生成された例外をトラップし、問題の原因の特定に役立てるには、オーケストレーションでスコープ図形を使用します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling3.md)