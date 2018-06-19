---
title: データベース テーブルの大きな成長 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f30372f7-ab90-4ebb-9022-ac3ae3309459
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1253f57a38ea0658d15e536a4f7b614cc52aed7f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014201"
---
# <a name="large-growing-biztalk-server-database-tables"></a>BizTalk Server データベース テーブルの大規模な成長
次の表、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通常が大きいものを拡大するテーブル。 このデータを使用すると、潜在的な問題が存在する場所を特定します。  

## <a name="tables-list"></a>テーブルの一覧
|テーブル|Description|コメント|  
|-----------|-----------------|--------------|  
|*HostNameQ*_Suspended テーブル|このテーブルには、特定のホストの中断されたインスタンスに関連付けられている、スプール テーブル内のメッセージへの参照が含まれています。 次の表は、BizTalkMsgBoxDb データベースでです。|場合、 *HostNameQ*_Suspended テーブルの多くのレコードがある、テーブルに有効な中断されたインスタンスに表示される可能性がありますを含んでいる、**グループ ハブ**ページ。 これらのインスタンスを終了することができます。 これらのインスタンスが表示されない場合、**グループ ハブ**インスタンスはインスタンスをキャッシュして可能性がありますまたはルーティング エラー報告を孤立します。 中断されたインスタンスを終了したときに、このテーブル内の項目と、スプール テーブルおよびインスタンス テーブルに関連付けられている行をクリーンアップします。|  
|*HostNameQ*テーブル|このテーブルには、特定のホストに関連付けられは中断されていないスプール テーブル内のメッセージへの参照が含まれています。 次の表は、BizTalkMsgBoxDb データベースでです。|場合、 *HostNameQ*テーブルの多くのレコードがある、次の種類のインスタンスが存在する可能性があります。<br /><br /> インスタンスの準備完了の実行<br />アクティブなインスタンス<br />退避済みのインスタンス<br /><br /> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]「遅延を解消する」とインスタンスの処理に時間が必要です。 次の表に、処理の着信レート outpaces、送信速度の処理時に拡張できます。 このシナリオにも大きな BizTalkDTADb データベースや SQL Server ディスク遅延がないのために発生します。|  
|スプール、部品、およびテーブルをフラグメント化|これらのテーブルでは、BizTalkMsgBoxDb データベースの実際のメッセージ データを格納します。|大量のメッセージがあることを意味する多数のレコードを含む Spool、パーツ、およびフラグメントのテーブルは、退避または中断している現在アクティブなです。 サイズの部分の数およびこれらのテーブルの断片化の設定に応じて、1 つのメッセージはこれらすべてのテーブルを生成可能性があります。 各メッセージは、スプール テーブルに 1 行および Parts テーブルに少なくとも 1 つの行にします。|  
|インスタンス テーブル|次の表は、BizTalkMsgBoxDb データベース内のすべてのインスタンスとその現在の状態を格納します。|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インスタンス テーブル内に存続する多くの中断されたインスタンスの管理者が許可する必要があります。 多くの退避済みインスタンスのみおく必要があるビジネス ロジックは、長時間のオーケストレーションを必要とする場合。 その 1 つのサービス インスタンスは、スプール テーブルに多数のメッセージを関連付けることができますに注意してください。|  
|TrackingData *_x_x*テーブル|このテーブルは、BizTalkMsgBoxDb データベースの Tracking Data Decode Service (TDDS) BizTalkDTADb データベースにイベントを移動する、追跡したイベントを格納します。|場合、TrackingData_*x_x*テーブルが大きい場合、いずれか、TDDS が実行されていないかが正常に実行されていません。 TDDS が実行されている場合は、イベント ログとエラー情報は、BizTalkDTADb データベースに TDDS_FailedTrackingData テーブルを確認します。|  
|Tracking_Fragments*x*、Tracking_Parts*x*、Tracking_Spool*x*テーブル|これらの各テーブルの 2 つは、BizTalkMsgBoxDb と BizTalkDTADb データベースです。 1 つがオンラインで、もう一方はオフラインです。|**TrackedMessages_Copy_BizTalkMsgBoxDb** SQL Server エージェント ジョブは、これらのテーブルに、BizTalkDTADb データベースに直接追跡されたメッセージ本文を移動します。|  
|dta_ServiceInstances テーブル|このテーブルは、BizTalkDTADb データベース内のサービス インスタンス追跡したイベントを格納します。|このテーブルが大きい場合、BizTalkDTADb データベースが大きい可能性があります。|  
|dta_DebugTrace テーブル|このテーブルは、BizTalkDTADb データベース内のオーケストレーション デバッガーのイベントを格納します。|Dta_DebugTrace テーブルに多数のレコードがある場合は、オーケストレーション図形の追跡が使用されているまたは使用されています。 オーケストレーションのデバッグが通常の操作に必要でない場合は、オーケストレーション図形のすべてのオーケストレーションの追跡を無効にします。 オーケストレーション図形の追跡が既に無効になって、BizTalkMsgBoxDb データベースにバックログが存在する場合は、dta_DebugTrace テーブルは、TDDS が dta_DebugTrace テーブルに、このデータを移動し続けるためにを増大し続けることがあります。<br /><br /> BizTalkDTADb の追跡データベースのサイズを制御するには、グローバル追跡を無効にすることもできます。 参照してください[グローバル追跡を無効にする方法](../core/how-to-turn-off-global-tracking.md)と[追跡データベースのサイズに関するガイドライン](../core/tracking-database-sizing-guidelines.md)です。|  
|dta_MessageInOutEvents テーブル|次の表は、BizTalkDTADb データベースに追跡イベント メッセージを格納します。 これらの追跡対象のイベント メッセージには、メッセージのコンテキスト情報が含まれます。|Dta_DebugTrace テーブルと BizTalkTrackingDb データベースで dta_MessageInOutEvents テーブルが大きすぎる場合は、追跡ホストを停止した後に手動でテーブルを切り捨てることができます。 テーブルを切り捨てる方法については、"dta_DebugTrace table"の詳細を参照してください[KB 952555: を維持し、BizTalk Server データベースのトラブルシューティングを行う方法](https://support.microsoft.com/help/952555/how-to-maintain-and-troubleshoot-biztalk-server-databases)です。|  
|dta_ServiceInstanceExceptions テーブル|次の表は、BizTalkDTADb データベースの中断されたサービス インスタンスのエラー情報を格納します。|Dta_ServiceInstanceExceptions の表は、通常が大きくなると定期的に、インスタンスが中断された環境でします。|
