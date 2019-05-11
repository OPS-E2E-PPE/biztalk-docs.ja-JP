---
title: 基本的なオーケストレーション Design5 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, design
- exception handling, orchestration design
ms.assetid: 0941d617-e30c-4ca7-852f-193e16781ca7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96606eac3ed552dfb07d82630d1ae82830b040c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358319"
---
# <a name="basic-orchestration-design"></a>基本的なオーケストレーション デザイン
BizTalk adapter for PeopleSoft Enterprise の基本的なオーケストレーションを作成するときに、オーケストレーションの受信ポートに XML が表示されます。 XML は、処理するバックエンド システムに送信されます。 バックエンド システムで例外が発生する可能性をオーケストレーションを停止し、エラーが生成です。 生成されるエラーは、オーケストレーションが完了しなかったの情報を提供します。 これは、エラーの原因のデバッグに便利ではありません。  
  
 ![](../core/media/siebeladapter-15-exceptionhandling-start.gif "SiebelAdapter_15_ExceptionHandling_Start")  
例外処理  
  
 エラーが発生した場合、呼び出しは中断されます。 監査ログには、呼び出しが失敗に設定されます。 監査ログで失敗を右クリックすると、失敗した呼び出しは、ポップアップ メッセージを開きます。 レポートの選択範囲をクリックすると、障害ドメインとバックエンド システムからエラーの原因が表示されます。  
  
 中断状態からオーケストレーションをしないようにして、エラーをリダイレクトする、CatchExpression を作成できます。 バック エンドによって生成された例外をトラップし、エラーの原因の特定に役立てるには、オーケストレーションでスコープ図形を使用できます。  
  
 ![](../core/media/siebeladapter-16-exceptionhandling-total.gif "SiebelAdapter_16_ExceptionHandling_Total")  
例外処理の合計  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling2.md)