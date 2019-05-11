---
title: 基本的なオーケストレーション Design4 |Microsoft Docs
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
ms.openlocfilehash: 01c2bf6a1a3fc74b27a0dadd7ce7ad0185a51a12
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529152"
---
# <a name="basic-orchestration-design"></a>基本的なオーケストレーション デザイン
基本的なオーケストレーションを作成するときに、オーケストレーションの受信ポートで XML が表示されます。 XML は、処理するバックエンド システムに送信されます。 例外が発生する、バックエンド システムで、オーケストレーションを停止する可能性があります。 生成される例外は、オーケストレーションが完了しなかったの情報を提供します。  
  
 エラーが発生したときに、呼び出しは中断されます。 イベント ビューアー ログでは、エラーと失敗の理由を表示できます。  
  
 中断状態からオーケストレーションをしないようにして、エラーをリダイレクトする、CatchExpression を作成できます。 バック エンドによって生成された例外をトラップし、問題の原因の特定に役立てるには、オーケストレーションでスコープ図形を使用します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling4.md)