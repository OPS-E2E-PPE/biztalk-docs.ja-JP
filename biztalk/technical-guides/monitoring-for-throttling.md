---
title: "監視の調整を |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d1d4c72-6942-4572-b27f-c58d37c94062
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d60b9f3deb77df927eb055b4504b809b421ae663
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-for-throttling"></a>監視の調整
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックの制限の状態を示すパフォーマンス カウンターを監視する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 制限について理解するいくつかの重要な要因は次のとおりです。  
  
-   割合に基づく制限はホストごとに、メッセージの数に基づいてメッセージの送信と受信します。  
  
-   配信の制限 (**MsgBox では、送信ポートやオーケストレーション]-> [**)、受信レートは、メッセージ ボックスからのメッセージが受信される数。 送信速度は、メッセージを正常にアダプター経由で配信するレートです。  
  
-   公開の制限 (**受信アダプター**または**オーケストレーション MsgBox]-> [)、**受信レートは、アダプターからメッセージが受信される速度、送信速度レート メッセージは、メッセージ ボックスに接続します。  
  
-   データベース内の合計メッセージ以外のホスト間では、制限メカニズムは存在しません。  
  
 追加の背景情報については、トピックを参照してください[どのように BizTalk Server を実装してホスト Throttling](http://go.microsoft.com/fwlink/?LinkID=155286) (http://go.microsoft.com/fwlink/?LinkID=155286) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、自己制限が組み込まれているため、さまざまなパラメーターに基づいてサーバーのオーバーロードを回避できます。 制限の発生原因となるようなオーバーロードが一時的なものであれば、運用上の問題としてそれほど大きくはありません。 ただし、永続的な制限が発生するようでは、安定した環境とはいえません。永続的な制限はインフラストラクチャ レベルの基本的な問題を示している可能性があります。 管理パックは、このような永続的な制限の条件のパフォーマンスしきい値ルールのプロアクティブな監視を提供します。  
  
 ルールの監視の 4 つの使用率/パフォーマンス追跡では、次の表に示すように、次の 4 つの異なる条件による制限の期間を拡張します。  
  
|条件|Rule|  
|---------------|----------|  
|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービス プロセス メモリ|警告: BizTalk Throttled かなりの時間、高のプロセス メモリに|  
|処理されるメッセージの数|警告: BizTalk Throttled で高 Inprocess メッセージ数のかなりの時間|  
|内のスレッドの数、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセス|警告: BizTalk Throttled にかなりの時間、高のスレッド数|  
|サイズ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースのキュー|警告: BizTalk Throttled on、かなり時間 High Database Size|  
  
 これらのしきい値ルールは、制限状態インジケーター パフォーマンス カウンターに基づくデータ プロバイダーを使用します。 これらのパフォーマンス カウンターの詳細については、セクションを参照してください[パフォーマンス カウンター](http://go.microsoft.com/fwlink/?LinkId=157269) (http://go.microsoft.com/fwlink/?LinkId=157269) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
 サンプルの一定数の平均値が特定のしきい値を超えた場合にアラートを生成するこれらの規則が構成されている (既定値は 30 になります)。 たとえば、"警告: BizTalk Throttled on High Database Size for、かなり時間"のすべての制限の状態を監視するルールは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]特定のコンピューターのプロセスです。 このルールは、調整状態インジケーター パフォーマンス カウンター「BizTalk:Message Agent-High データベースのサイズです」に基づいてデータ プロバイダーを使用してください。 このパフォーマンス カウンター値が 1 の場合、関連付けられたプロセスは、データベース サイズが大きいという理由で制限されます。  
  
 上記の規則が 30 のサンプルの平均を行い、サンプルの平均値が 0.6 を超えた場合にアラートを生成するように構成します。 各サンプルは、1 分間隔で取得は、以降は、過去 30 分間、経由では、時間の 60% の高いデータベース サイズが原因でそのコンピューターには、少なくとも 1 つまたは複数の BizTalk Server プロセスが制限されたことを意味します。  
  
 この方法は、アプリケーションのシナリオによっては適合しない場合があります。 前に説明したように、環境内の従来の動作に基づき、する必要がありますを構成するこれらのルールを適切な値でいずれか。  
  
-   サンプルを調整します。  
  
-   しきい値を調整します。  
  
-   必要に応じて、プロバイダーのサンプリングの間隔を変更します。