---
title: パフォーマンスしきい値ルールを使用して調整の監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc2c3024-a54b-4485-8110-c2ec9ec52721
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d5bf8f327cbdb12ebe0723941afd6e37b5d2409
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968051"
---
# <a name="monitoring-throttling-using-performance-threshold-rules"></a>パフォーマンスしきい値ルールを使用して調整の監視
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 回復不可能な状態から、システムを保護するために調整が初期化されます。 調整に問題があるし、そのソースの特定に役立てることができます。 制限の状態に基づいて、ボトルネックの原因を特定したら、問題の原因を絞り込むために他のパフォーマンス カウンターを分析します。  
  
 たとえば、メッセージ ボックス データベースで競合が増加高い CPU 使用率、ディスクで、さらに、メモリ不足の条件によって発生する可能性がありますに過剰なページングが原因が可能性があります。 メッセージ ボックス データベースで競合が増加が飽和状態のディスク ドライブが原因である可能性がある高のロックの競合によっても原因。  
  
 Message Delivery Throttling State と各ホスト インスタンスの Message Publishing Throttling State の監視は、調整をトラブルシューティングする場合にお勧めでは、通常は。 これらのカウンターの値が 0 でない場合に、BizTalk Server システム内で調整が行われていることと、さらに、ボトルネックの原因を分析することができますを示しています。 その他のパフォーマンス カウンターの説明については、次を参照してください。[データベース層のボトルネックを識別する](http://go.microsoft.com/fwlink/?LinkID=154678)(<http://go.microsoft.com/fwlink/?LinkID=154678>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
## <a name="biztalk-server-system-performance-counters"></a>BizTalk Server システムのパフォーマンス カウンターします。  
  
|オブジェクト|Instance|カウンター|監視の目的|  
|------------|--------------|-------------|------------------------|  
|プロセッサ|_Total|[% プロセッサ時間]|リソースの競合|  
|Process|BTSNTSvc|Virtual Bytes|メモリ リーク/メモリの肥大化|  
|Process|BTSNTSvc|Private Bytes|メモリ リーク/メモリの肥大化|  
|Process|BTSNTSvc|Handle Count|リソースの競合|  
|Process|BTSNTSvc|スレッド数|リソースの競合|  
|Physical Disk|_Total|% Idle Time|リソースの競合|  
|Physical Disk|_Total|Current Disk Queue Length|リソースの競合|  
  
## <a name="biztalk-application-counters"></a>BizTalk アプリケーション カウンター  
  
|オブジェクト|Instance|カウンター|説明|  
|------------|--------------|-------------|-----------------|  
|BizTalk Messaging|RxHost|Documents Received/Sec|受信速度|  
|BizTalk Messaging|TxHost|Documents Processed/Sec|送信速度|  
|XLANGs/オーケストレーション|PxHost|完了したオーケストレーションの数/秒|処理速度|  
|BizTalk: メッセージ ボックス: 一般的なカウンター|MsgBoxName|Spool Size|すべてのホスト キューの合計サイズ|  
|BizTalk: メッセージ ボックス: 一般的なカウンター|MsgBoxName|Tracking Data Size|メッセージ ボックスの TrackingData テーブルのサイズ|  
|BizTalk: メッセージ ボックス: ホスト カウンター|PxHost:MsgBoxName|Host Queue - Length|特定のホスト キューに存在するメッセージの数|  
|BizTalk: メッセージ ボックス: ホスト カウンター|TxHost:MsgBoxName|Host Queue - Length|特定のホスト キューに存在するメッセージの数|  
|BizTalk: メッセージ エージェント|RxHost|Database Size|公開 (PxHost) キューのサイズ|  
|BizTalk: メッセージ エージェント|PxHost|Database Size|公開 (TxHost) キューのサイズ|  
|BizTalk: メッセージ エージェント|HostName|Message Delivery Throttling State|XLANG と送信トランスポートに影響|  
|BizTalk: メッセージ エージェント|HostName|Message Publishing Throttling State|XLANG と受信トランスポートに影響|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [調整のための監視](../technical-guides/monitoring-for-throttling.md)