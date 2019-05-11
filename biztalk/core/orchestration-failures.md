---
title: オーケストレーション エラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d3eaebe4244dfd1e7ad60cf6541c4573a9f2158
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263003"
---
# <a name="orchestration-failures"></a>オーケストレーション エラー
オーケストレーションの複雑さ; が異なりますたとえば、オーケストレーションは、.NET オブジェクトを呼び出す可能性があります。 またはトランス フォームと割り当て図形を使用してメッセージを構築します。 その結果、レベルのカスタマイズと同様に、さまざまなコンテンツのためのすべての可能性のあるエラーを列挙することはできません。 ただし、例外として、オーケストレーションで発生したすべてのエラーが表示されます。  
  
 いずれかのオーケストレーションが含まれない場合**CatchException**図形例外、例外の原因を中断、再開できないするオーケストレーションです。 これはメッセージとサービス インスタンスの追跡、または WMI スクリプトでは、インスタンスを修復できないことを意味します。 ただし、中断されたに関連付けられているすべてのメッセージを保存することができます (再開できない) インスタンスの診断や手動の再試行の追跡 (または WMI スクリプト) を使用します。  
  
 問題を診断するには、オーケストレーション デバッガーを使用して、インスタンスが中断される前に実行される直前に図形を参照してください。 オーケストレーション デバッガーを使用して例外の詳細を表示することもできます。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション、ポート、およびメッセージのエラーの調査](../core/investigating-orchestration-port-and-message-failures.md)   
 [オーケストレーションのデバッグ](../core/debugging-an-orchestration.md)