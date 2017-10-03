---
title: "オーケストレーション エラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Catch Exception block [Orchestration Designer], suspended orchestrations
- HAT, Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer], HAT
- orchestrations, troubleshooting [HAT]
- orchestrations, errors
- HAT, Orchestration Debugger
- Orchestration Debugger
- errors, orchestrations
- HAT, troubleshooting orchestrations
- orchestrations, HAT
- HAT, orchestrations
ms.assetid: d0a799fb-7859-4774-b444-979f22f04215
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d95cab903ae9bf5faacdf385f667c33f9a2d5a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-failures"></a>オーケストレーション エラー
各オーケストレーションの複雑さは異なります。たとえば、.NET オブジェクトを呼び出すオーケストレーションもあれば、変換図形と割り当て図形を経由してメッセージを構築するオーケストレーションもあります。 このように、オーケストレーションの内容やカスタマイズ レベルはさまざまなので、発生する可能性のあるすべてのエラーを列挙することはできません。 ただし、オーケストレーションで発生するすべてのエラーは例外として表示されます。  
  
 いずれかのオーケストレーションが含まれない場合**CatchException**例外、例外の図形により、オーケストレーションが中断、再開できません。 これは、メッセージおよびサービス インスタンスの追跡や WMI スクリプトではインスタンスを修復できないことを意味します。 ただし、診断や手動での再試行用に、追跡 (または WMI スクリプト) を使用して、中断された (再開できない) インスタンスに関連付けられたすべてのメッセージを保存できます。  
  
 問題を診断するには、オーケストレーション デバッガーを使用して、インスタンスが中断される直前に実行された図形を確認します。 また、オーケストレーション デバッガーを使用して、例外の詳細を表示することもできます。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション、ポート、およびメッセージのエラーの調査](../core/investigating-orchestration-port-and-message-failures.md)   
 [オーケストレーションのデバッグ](../core/debugging-an-orchestration.md)