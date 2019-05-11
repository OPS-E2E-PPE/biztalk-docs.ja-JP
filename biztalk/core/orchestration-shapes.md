---
title: オーケストレーション図形 |Microsoft Docs
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
ms.openlocfilehash: 5ad225737b806991a0633019dcf91b683f726bca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322638"
---
# <a name="orchestration-shapes"></a>オーケストレーション図形
オーケストレーション デザイナーは、オーケストレーションを作成するためのビジュアル ツールです。 基になる操作は、の視覚表現としてデザイン サーフェイスに配置できるいくつかの図形および効率よくデザインし、オーケストレーションを実装することができます。  
  
 **不十分な構成アクション**  
  
 ![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")  
  
> [!NOTE]
>  不足している構成の操作は、オーケストレーション デザイナーは、関連付けられた図形が完全に構成されていないことを検出すると、オーケストレーション デザイナーに表示されます。 オーケストレーションの図形が完全に構成されていない場合、関連付けられたオーケストレーションはコンパイルされません。  
  
 次の表では、各図形の機能の簡単な説明と共に、使用可能な図形を示します。  
  
|図形|図形の名前|目的|  
|-----------|----------------|-------------|  
|![](../core/media/ebiz-orch-callorchestrat.gif "ebiz_orch_callorchestrat")|**オーケストレーションを呼び出し**|オーケストレーションを別のオーケストレーションを同期的に呼び出すできます。|  
|![](../core/media/ebiz-orch-call-rules.gif "ebiz_orch_call_rules")|**ルールの呼び出し**|オーケストレーションで実行されるビジネス ルール ポリシーを構成できます。|  
|![](../core/media/ebiz-orch-compensate.gif "ebiz_orch_compensate")|**補正**|元に戻すまたはエラーが発生したときに、オーケストレーションによって実行された操作を補正するコードを呼び出すことができます。|  
|![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")|**メッセージの構築**|メッセージを構築できます。|  
|![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")|**決定**|オーケストレーション内で条件に応じて分岐できます。|  
|![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")|**遅延**|タイムアウト間隔に基づき、オーケストレーションでの遅延を設定できます。|  
|![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")|**[式]**|変数に値を割り当てるまたは .NET 呼び出しのことができます。|  
|![](../core/media/ebiz-orch-group.gif "ebiz_orch_group")|**[グループ]**|Visual 便宜上 1 つの展開と折りたたみ可能な単位に操作をグループ化できます。|  
|![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")|**リッスン**|オーケストレーションに受信したメッセージによって分岐に条件付きで、またはタイムアウト期間の有効期限を有効にします。|  
|![](../core/media/ebiz-orch-loop.gif "ebiz_orch_loop")|**ループ**|オーケストレーションをループ条件が満たされるまで有効にします。|  
|![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")|**メッセージの割り当て**|メッセージの値を割り当てることができます。|  
|![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")|**並列アクション**|オーケストレーションをそれぞれ個別に 2 つ以上の操作を実行できます。|  
|![](../core/media/ebiz-orch-port.gif "ebiz_orch_port")|**[ポート]**|メッセージを送信する場所と方法を定義します。|  
|![](../core/media/ebiz-orch-receive.gif "ebiz_orch_receive")|**受信**|オーケストレーションでメッセージを受信できます。|  
|![](../core/media/ebiz-orch-rolelink.gif "ebiz_orch_rolelink")|**ロール リンク**|複数の異なるトランスポートやエンドポイントを通じて同じ論理パートナーと通信するポートのコレクションを作成できます。|  
|![](../core/media/ebiz-orch-scope.gif "ebiz_orch_scope")|**Scope**|トランザクションと例外処理のフレームワークを提供します。|  
|![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")|**送信**|オーケストレーションからメッセージを送信できます。|  
|![](../core/media/ebiz-orch-strtorchestrat.gif "ebiz_orch_strtorchestrat")|**オーケストレーションを開始します。**|別のオーケストレーションを非同期的に呼び出すオーケストレーションをできます。|  
|![](../core/media/ebiz-orch-suspend.gif "ebiz_orch_suspend")|**[中断]**|何らかのエラー状態が発生した場合の操作を有効にするオーケストレーションの操作を中断します。|  
|![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")|**終了**|何らかのエラー状態が発生した場合、オーケストレーションの操作をすぐに終了できます。|  
|![](../core/media/ebiz-orch-throwexcept.gif "ebiz_orch_throwexcept")|**例外をスローします。**|明示的にエラーが発生した場合、例外をスローできます。|  
|![](../core/media/ebiz-orch-transform.gif "ebiz_orch_transform")|**変換**|新しいメッセージに既存のメッセージからフィールドをマップできます。|