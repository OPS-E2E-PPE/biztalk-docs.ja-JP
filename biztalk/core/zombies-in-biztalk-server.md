---
title: BizTalk Server のゾンビ |Microsoft ドキュメント
description: BizTalk Server でゾンビ メッセージの一般的な原因
ms.custom: ''
ms.date: 03/23/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c684891-e984-442f-b5fd-de5f7cf32b44
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9764522d2ff5265b6f28f2f125cb33b2982a7605
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290546"
---
# <a name="zombies-in-biztalk-server"></a>BizTalk Server のゾンビ

## <a name="what-is-a-zombie"></a>ゾンビとは  
  
-   ゾンビ メッセージとは、メッセージ ボックスから実行中のオーケストレーションに渡され、オーケストレーションの終了時に "インフライト" であったメッセージのことです。 "インフライト" メッセージとは、サービス インスタンスに回送され、そのサービス インスタンス宛てのメッセージ ボックス キューに入っているメッセージのことです。 このメッセージは、サブスクライブを行なうオーケストレーション インスタンスによって処理されません。そのため、メッセージが中断され、メッセージの ServiceInstance/状態値が "中断 (再開不可)" になります。  
  
-   ゾンビ サービス インスタンスとは、メッセージ ボックスからオーケストレーション インスタンスに回送されたメッセージがまだ "インフライト" であったときに終了したオーケストレーション インスタンスのことです。 オーケストレーション インスタンスが既に終了しているため、"インフライト" メッセージは処理されません。そのため、メッセージが中断され、メッセージの ServiceInstance/状態値が "中断 (再開不可)" になります。  
  
## <a name="typical-causes"></a>一般的な原因
ゾンビの発生は一般的に、次のカテゴリのいずれかに分類されます。  
  
1.  **終了コントロール メッセージ**– オーケストレーション エンジンは、特定のオーケストレーション インスタンスで現在実行されているすべての処理を取り消すコントロール メッセージの使用を許可します。 コントロール メッセージを使用すると、実行中のオーケストレーションが直ちに終了するため、ゾンビ インスタンスが発生する可能性があります。 このメカニズムは、ヒューマン ワークフロー関連の設計で頻繁に使用される傾向があります。また、その他の設計でも使用される場合があります。  
  
2.  **並列待機受信**– このシナリオでは、サービス インスタンスが待機の n 個のメッセージの 1 と特定のメッセージを受信したときに何らかの処理を終了します。 サービス インスタンスの終了時に並列分岐でメッセージが受信された場合、ゾンビが発生します。  
  
3.  **非決定的なエンドポイントを含むシーケンシャルなコンボイ**– このシナリオでは、何らかの種類のシステム設計要件を満たすために、特定の種類のすべてのメッセージを処理するマスター オーケストレーション スケジュールが設計されています。 こうした設計要件の例として、順次配送、リソース ディスペンサー、バッチ処理などがあります。 このシナリオでは、傾向が while の定義を受信と、他の while ループをことを示すためにいくつかの変数を設定するか、コンストラクト続けて遅延図形を持つ 1 つの分岐でリッスンを囲むループを停止する必要があります。 これは非決定的です。なぜなら、メッセージが配信可能な場合でも遅延が発生する可能性があるからです。 このような非決定的なエンドポイントでは、ゾンビが発生する可能性が高くなります。  
  
 ゾンビ サービス インスタンスが中断されると、次のエラー メッセージが生成されます。  
  
`0xC0C01B4C The instance completed without consuming all of its messages. The instance and its unconsumed messages have been suspended.`  
  
 使用することができます、 [BizTalk 終端記号](https://www.microsoft.com/download/details.aspx?id=2846)ゾンビを削除します。  
  
## <a name="see-also"></a>参照  
 **中断されたサービス インスタンスを削除する**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]