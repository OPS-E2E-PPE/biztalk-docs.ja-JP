---
title: 注文処理ステージでの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 698005da-1ba8-4972-83db-f5ae45fd6a83
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2cf62be2b8a4e11ce7a6acc5b9807207aea89d00
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299854"
---
# <a name="processing-in-the-order-processing-stages"></a>注文処理ステージでの処理
ビジネス プロセス管理ソリューションには、2 つの段階が含まれています、 **CableOrder1**と**CableOrder2**オーケストレーションは、注文処理アクションを実行します。 注文処理ステージに分割する方法の詳細については、次を参照してください。[処理ステージの数](../core/number-of-processing-stages.md)します。  
  
 どちらの処理ステージの開始、注文メッセージを受信して、状態メッセージで応答すると、 **OrderManager**オーケストレーションが開始されるとします。 同様に、メッセージを送信、 **OrderManager**をステージが完了またはエラーで終了したかどうかを示します。 詳細については、間の接続、 **OrderManager**オーケストレーションと処理ステージを参照してください。[逆の直接パートナー バインド](../core/inverse-direct-partner-binding.md)します。  
  
 どちらの処理ステージを使用して、自己関連付けを行う、情報を送信する動的ポートにバックアップ、 **OrderManger**します。 動的ポートでは、オーケストレーションは、メッセージの送信ポートからポート アドレスをコピーします。  
  
 作成された標準の正規化された注文メッセージをすべての注文メッセージを処理ステージが受信、 **OrderBroker**します。  
  
> [!NOTE]
>  長さのため、 **CableOrder1**と**CableOrder2**オーケストレーションと Microsoft Visual Studio でオーケストレーションを開いてこのセクションを参照する可能性があります。  
  
## <a name="the-cableorder1-orchestration"></a>CableOrder1 オーケストレーション  
 **CableOrder1**注文メッセージを受信すると、オーケストレーションが開始されます。 それにコピーされます返信アドレス メッセージからステージ完了ポート。 次に、受信確認メッセージを構築しへの応答として送信、 **BeginStagePort**ポート、およびローカル変数に、ルーティング情報を保存します。  
  
 次に、オーケストレーションは、SSO から構成情報を取得します。 ソリューションで SSO を使用する方法の詳細については、次を参照してください。[を使用して SSO の効率的なビジネス プロセス管理ソリューションで](../core/using-sso-efficiently-in-the-business-process-management-solution.md)します。  
  
 インスタンスを作成し、オーケストレーション、 **OrderHandler**バックエンド プロセスと通信するオブジェクト、メッセージの有効性を確認、メッセージを分析し、サービスの種類を決定し、実行するには、どのアクション。 呼び出し順序のアクションのオーケストレーションのいずれかによって実行するアクション、**アクティブ化**、**変更**、または**キャンセル**渡します、 **OrderHandler**オーケストレーションへのオブジェクト。  
  
 **CableOrder1**オーケストレーションし、バックアップを聞き、機能グループと待機するメッセージが送信されます、割り込みのチェック。 場合は、オーケストレーション機能グループからメッセージが返される、処理を続行します。 それ以外の場合、割り込みがある場合、オーケストレーションは割り込み例外をスローします。  
  
 完了メッセージを作成して、送信経由で、オーケストレーションが完了したら、 **StageCompletion**ポート。  
  
## <a name="the-cableorder2-orchestration"></a>CableOrder2 オーケストレーション  
 CableOrder2 オーケストレーションの実行、同じルーティング情報については、SSO 構成情報、CableOrder1 オーケストレーションとして手順を開始してのインスタンスを作成、 **OrderHandler**オブジェクト。  
  
 割り込みとパスを調べ、オーケストレーション、 **OrderHandler**オブジェクトへの呼び出しで、**完了**オーケストレーションします。 次に、オーケストレーション、注文のステータス メッセージを作成します。 注文履歴、更新とを介して完了メッセージを送信、 **StageCompletion**ポート。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションのバージョン管理](../core/versioning-the-business-process-management-solution.md)   
 [ビジネス プロセス管理ソリューションでの処理](../core/processing-in-the-business-process-management-solution.md)