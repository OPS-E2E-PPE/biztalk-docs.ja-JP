---
title: 調整の監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d1d4c72-6942-4572-b27f-c58d37c94062
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c175c2668a3d2f8bdf0d4088d51bfd76d43ca8d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305546"
---
# <a name="monitoring-for-throttling"></a>調整の監視
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックの制限の状態を示すパフォーマンス カウンターを監視する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 調整を理解するためにいくつかの重要な要因は、以下に示します。  
  
- 割合に基づく制限は 1 つのホストとメッセージの数に基づいてメッセージの送信と受信します。  
  
- 配信の制限 (**MsgBox では、送信ポートまたはオーケストレーション]-> [**)、受信レートは、メッセージ ボックスからメッセージが受信される数。 送信レートとは、メッセージを正常にアダプター経由で配信される速度です。  
  
- 公開の制限 (**受信アダプター**または**オーケストレーション MsgBox]-> [)、** 受信レートは、アダプターから受信されるメッセージ数とレート メッセージは送信レートは、MsgBox に接続します。  
  
- データベースの合計メッセージ以外のホスト間では、制限メカニズムは存在しません。  
  
  追加の背景情報については、トピックを参照してください[どのように BizTalk Server 実装ホスト Throttling](http://go.microsoft.com/fwlink/?LinkID=155286) (<http://go.microsoft.com/fwlink/?LinkID=155286>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 自己調整、さまざまなパラメーターに基づいて、サーバーの過負荷を防ぐに役立ちますが組み込まれています。 スロットルが発生する原因となる一時的なオーバー ロードは、運用上あまり大きなイベントではありません。 永続的な調整、ただし、安定した環境がないと、インフラストラクチャ レベルの基になる問題がある可能性があります。 管理パックでは、このような永続的な制限の条件でパフォーマンスしきい値ルールのプロアクティブな監視を提供します。  
  
  ルールは監視の 4 つの使用率/パフォーマンス追跡では、次の表に記載されている 4 つの異なる条件による制限の期間を拡張します。  
  
|                                                     条件                                                     |                                        Rule                                         |
|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|
|     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービス プロセス メモリ     |     警告:BizTalk は、かなりの時間の高いプロセス メモリの調整      |
|                                        処理されるメッセージの数                                         | 警告:BizTalk で高い Inprocess メッセージ数の重要な期間を調整します。 |
| スレッドの数、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセス |      警告:BizTalk がかなりの時間の高いスレッドの数を調整       |
|  サイズ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースのキュー   |      警告:BizTalk が High Database Size for 重要な期間の調整      |
  
 これらのしきい値ルールは、制限状態インジケーター パフォーマンス カウンターに基づくデータ プロバイダーを使用します。 これらのパフォーマンス カウンターの詳細については、セクションを参照してください[パフォーマンス カウンター](http://go.microsoft.com/fwlink/?LinkId=157269) (<http://go.microsoft.com/fwlink/?LinkId=157269>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
 サンプル数の平均が特定のしきい値を超えた場合にアラートを生成するこれらの規則が構成されている (既定値は 30 になります)。 たとえば、"警告。すべての制限の状態を監視するルールは、BizTalk 調整 High Database Size for a significant period"[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]特定のコンピューターでプロセス。 このルールで制限状態インジケーター パフォーマンス カウンター「BizTalk:Message Agent-High データベースのサイズ」に基づくデータ プロバイダー このパフォーマンス カウンターの値が 1 の場合は、データベース サイズが大きいため、関連付けられたプロセスが調整されます。  
  
 30 のサンプルの平均値を取得して、サンプルの平均値が 0.6 を超えた場合にアラートを発生させる前のルールが構成されます。 各サンプルは 1 分間隔で実行される、ため、過去 30 分以内は 60% の時間、高のデータベースのサイズが原因で、そのコンピューターには少なくとも 1 つまたは複数の BizTalk Server プロセスが制限されたことを意味します。  
  
 このヒューリスティックでは、特定のアプリケーション シナリオが適していない可能性があります。 前に説明したように、環境内で従来の動作に基づき、する必要がありますを構成するこれらの規則が正しい値でいずれかで。  
  
-   サンプルを調整します。  
  
-   しきい値の値を調整します。  
  
-   必要に応じて、プロバイダーのサンプリングの間隔を変更します。