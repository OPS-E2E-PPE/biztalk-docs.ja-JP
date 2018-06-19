---
title: オーケストレーション図形 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Delay shape [Orchestration Designer]
- Loop shape [Orchestration Designer]
- Throw Exception shape [Orchestration Designer]
- Expression shape [Orchestration Designer]
- Decide shape [Orchestration Designer]
- Receive shape [Orchestration Designer]
- Compensate shape [Orchestration Designer]
- orchestrations, shapes
- Suspend shape [Orchestration Designer]
- Send shape [Orchestration Designer]
- Group shape [Orchestration Designer]
- Listen shape [Orchestration Designer]
- shapes, about shapes
- Construct Message shape [Orchestration Designer]
- Parallel Actions shape [Orchestration Designer]
- Call Rules shape [Orchestration Designer]
- Start Orchestration shape [Orchestration Designer]
- Transform shape [Orchestration Designer]
- Message Assignment shape [Orchestration Designer]
- Role Link shape [Orchestration Designer]
- Call Orchestration shape [Orchestration Designer]
- Port shape [Orchestration Designer]
- shapes
- Scope shape [Orchestration Designer]
- Terminate shape [Orchestration Designer]
- Orchestration Designer, shapes
- Insufficient Configuration Smart Tag [Orchestration Designer]
ms.assetid: a1d03baa-a267-499d-94fc-700b3e959458
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 181656208b757c595feb9d19ee786fe91f1b78f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264298"
---
# <a name="orchestration-shapes"></a>オーケストレーション図形
オーケストレーション デザイナーは、オーケストレーションを作成するためのビジュアル ツールです。 このツールで提供されている複数の図形を、基になる操作の視覚的な表現としてデザイン画面に配置することで、オーケストレーションを効率よくデザインし実装できます。  
  
 **不十分な構成アクション**  
  
 ![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")  
  
> [!NOTE]
>  オーケストレーション デザイナーでは、関連付けられた図形が完全に構成されていないことが検出された場合に、不十分な構成の操作が表示されます。 オーケストレーション内の図形が完全に構成されていないと、関連付けられたオーケストレーションはコンパイルされません。  
  
 次の表では、使用できる図形の一覧を示し、各図形の機能を簡単に説明します。  
  
|図形|図形の名前|用途|  
|-----------|----------------|-------------|  
|![](../core/media/ebiz-orch-callorchestrat.gif "ebiz_orch_callorchestrat")|**オーケストレーションを呼び出し**|オーケストレーションで、別のオーケストレーションを同期的に呼び出すことができます。|  
|![](../core/media/ebiz-orch-call-rules.gif "ebiz_orch_call_rules")|**呼び出し規則**|オーケストレーションで実行されるビジネス ルール ポリシーを構成できます。|  
|![](../core/media/ebiz-orch-compensate.gif "ebiz_orch_compensate")|**補正**|エラー発生時に、オーケストレーションで既に実行された操作を元に戻したり補正したりするためのコードを呼び出すことができます。|  
|![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")|**メッセージの構築**|メッセージを構築できます。|  
|![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")|**決定**|オーケストレーション内で条件に応じて分岐できます。|  
|![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")|**遅延**|タイムアウト間隔に基づいてオーケストレーションの遅延を設定できます。|  
|![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")|**[式]**|変数に値を割り当てるか、.NET を呼び出すことができます。|  
|![](../core/media/ebiz-orch-group.gif "ebiz_orch_group")|**[グループ]**|視覚的にわかりやすくなるように、折りたたみと展開が可能な 1 つの単位に操作をグループ化できます。|  
|![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")|**リッスン**|受信したメッセージやタイムアウト期間の終了などの条件に応じてオーケストレーションを分岐できます。|  
|![](../core/media/ebiz-orch-loop.gif "ebiz_orch_loop")|**ループ**|条件が満たされるまでオーケストレーションをループできます。|  
|![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")|**メッセージの割り当て**|メッセージの値を割り当てることができます。|  
|![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")|**並列アクション**|オーケストレーション内で複数の操作を互いに独立して実行できます。|  
|![](../core/media/ebiz-orch-port.gif "ebiz_orch_port")|**[ポート]**|メッセージの送信先と送信方法を定義します。|  
|![](../core/media/ebiz-orch-receive.gif "ebiz_orch_receive")|**受信**|オーケストレーションでメッセージを受信できます。|  
|![](../core/media/ebiz-orch-rolelink.gif "ebiz_orch_rolelink")|**ロール リンク**|複数の異なるトランスポートやエンドポイントを通じて同じ論理パートナーと通信するためのポートのコレクションを作成できます。|  
|![](../core/media/ebiz-orch-scope.gif "ebiz_orch_scope")|**スコープ**|トランザクションおよび例外処理のフレームワークを提供します。|  
|![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")|**送信**|オーケストレーションからメッセージを送信できます。|  
|![](../core/media/ebiz-orch-strtorchestrat.gif "ebiz_orch_strtorchestrat")|**オーケストレーションを開始します。**|オーケストレーションで、別のオーケストレーションを非同期的に呼び出すことができます。|  
|![](../core/media/ebiz-orch-suspend.gif "ebiz_orch_suspend")|**[中断]**|エラー発生時にオーケストレーションの操作を中断して介入できるようにします。|  
|![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")|**終了**|エラー発生時にオーケストレーションの操作を直ちに終了できます。|  
|![](../core/media/ebiz-orch-throwexcept.gif "ebiz_orch_throwexcept")|**例外をスローします。**|エラーが発生した場合に例外を明示的にスローできます。|  
|![](../core/media/ebiz-orch-transform.gif "ebiz_orch_transform")|**変換**|既存のメッセージから新しいメッセージにフィールドをマップできます。|