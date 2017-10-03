---
title: "注文処理ステージで処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 698005da-1ba8-4972-83db-f5ae45fd6a83
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a8eae6b814af36d0ea07065726ca66518984703
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="processing-in-the-order-processing-stages"></a>注文処理ステージでの処理
ビジネス プロセス管理ソリューションには、2 つの段階が含まれています、 **CableOrder1**と**CableOrder2**注文処理アクションを実行するオーケストレーションです。 注文処理ステージに分割する方法の詳細については、次を参照してください。[処理ステージの番号](../core/number-of-processing-stages.md)です。  
  
 どちらの処理ステージは、注文メッセージを受信すると、状態メッセージで応答を開始、 **OrderManager**オーケストレーションが開始されるとします。 同様に、メッセージがバックアップに、送信、 **OrderManager**ステージが完了またはエラーで終了したかどうかを示すためにします。 間の接続の詳細について、 **OrderManager**オーケストレーションと処理ステージを参照してください。[逆パートナーの直接バインド](../core/inverse-direct-partner-binding.md)です。  
  
 自己関連付けを行う処理ステージを使用して、情報を送信する動的ポートにバックアップの両方、 **OrderManger**です。 動的なポートを使用して、ポート アドレスがメッセージから送信ポートにコピーされます。  
  
 作成された正規化された標準の注文メッセージは、すべての注文メッセージを処理ステージが受信、 **OrderBroker**です。  
  
> [!NOTE]
>  長さのため、 **CableOrder1**と**CableOrder2**オーケストレーション、オーケストレーションを Microsoft Visual Studio で開いてこのセクションを参照する場合があります。  
  
## <a name="the-cableorder1-orchestration"></a>CableOrder1 オーケストレーション  
 **CableOrder1**注文メッセージを受信したときに、オーケストレーションが開始します。 まず、このオーケストレーションでは、返信アドレスをメッセージからステージ完了ポートにコピーします。 次に、受信確認メッセージを構築しへの応答として送信、 **BeginStagePort**ポート、およびローカル変数に、ルーティング情報が保存されます。  
  
 次に、SSO から構成情報を取得します。 ソリューションが SSO を使用する方法に関する詳細については、次を参照してください。[を使用して SSO の効率的なビジネス プロセス管理ソリューションで](../core/using-sso-efficiently-in-the-business-process-management-solution.md)です。  
  
 インスタンスを作成し、オーケストレーション、 **OrderHandler**バックエンド プロセスと通信するためにオブジェクト、メッセージの有効性を確認、メッセージを分析して、サービスの種類を決定および対処します。 呼び出し順序のアクションのオーケストレーションのいずれかによっては、実行するアクション、 **Activate**、**変更**、または**キャンセル**渡します、 **OrderHandler**オーケストレーションへのオブジェクト。  
  
 **CableOrder1**し、オーケストレーション、バックアップ、割り込みを聞くに待機し、機能グループにメッセージが送信をチェックします。 機能グループからメッセージが返されると、処理を続行します。 割り込みがあった場合、オーケストレーションは割り込み例外をスローします。  
  
 作成して、完了のメッセージと経由の送信が完了すると、オーケストレーション、 **StageCompletion**ポートです。  
  
## <a name="the-cableorder2-orchestration"></a>CableOrder2 オーケストレーション  
 CableOrder2 オーケストレーションが同じを実行、CableOrder1 オーケストレーション、ルーティングについては、SSO 構成情報と手順を開始してのインスタンスを作成する、 **OrderHandler**オブジェクト。  
  
 割り込みとパスを調べ、オーケストレーション、 **OrderHandler**オブジェクトへの呼び出しで、**完了**オーケストレーションです。 次に、オーケストレーション注文ステータス メッセージを作成、注文履歴を更新し、を通じて、完了のメッセージを送信、 **StageCompletion**ポートです。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションのバージョン管理](../core/versioning-the-business-process-management-solution.md)   
 [ビジネス プロセス管理ソリューションでの処理](../core/processing-in-the-business-process-management-solution.md)