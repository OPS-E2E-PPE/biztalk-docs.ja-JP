---
title: "基本的なオーケストレーション Design5 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, design
- exception handling, orchestration design
ms.assetid: 0941d617-e30c-4ca7-852f-193e16781ca7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 224b8e507fc9319a2a4b66006914b3ebc27a8421
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="basic-orchestration-design"></a>基本的なオーケストレーション デザイン
BizTalk Adapter for PeopleSoft Enterprise で基本的なオーケストレーションを作成する場合、XML の受信はオーケストレーションの受信ポートで行います。 次に、その XML をバックエンド システムに送信して処理します。 バックエンド システムで、例外が発生する可能性がありますはオーケストレーションを停止し、エラーが生成されます。 生成されるエラーには、完了しなかったオーケストレーションの情報が示されます。 エラーの原因をデバッグする際、この情報はあまり役に立ちません。  
  
 ![](../core/media/siebeladapter-15-exceptionhandling-start.gif "SiebelAdapter_15_ExceptionHandling_Start")  
例外処理  
  
 エラーが発生すると、呼び出しは中断されます。 監査ログで、その呼び出しは [FAILED] に設定されます。 監査ログで [FAILED] を右クリックすると、失敗した呼び出しからポップアップ メッセージが表示されます。 レポートの選択項目をクリックすると、バックエンド システムからのエラーに対し、エラーの内容と原因が表示されます。  
  
 オーケストレーションが中断状態にならないようにし、エラーをリダイレクトするには、CatchExpression を作成します。 バックエンドで生成される例外をトラップし、エラーの原因の特定に役立てるには、オーケストレーションでスコープ図形を使用します。  
  
 ![](../core/media/siebeladapter-16-exceptionhandling-total.gif "SiebelAdapter_16_ExceptionHandling_Total")  
例外処理の全体図  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling2.md)