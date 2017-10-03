---
title: "パフォーマンスしきい値ルールの調整の監視 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc2c3024-a54b-4485-8110-c2ec9ec52721
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2aedf8040b821230b6541785426731f1cef32099
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-throttling-using-performance-threshold-rules"></a>パフォーマンスしきい値ルールの調整の監視
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]調整、回復不可能な状態に到達できない、システムの保護を初期化します。 調整、問題があるし、そのソースの識別に役立つことができます。 制限の状態に基づいて、ボトルネックの原因を識別した後は、問題の原因を絞り込む、他のパフォーマンス カウンターを分析します。  
  
 たとえば、メッセージ ボックス データベースで競合が増加高い CPU 使用率、ディスクで、さらに原因がでメモリ不足の状態への過剰なページングが考えられますが考えられます。 メッセージ ボックス データベースで競合が増加も考えられます高ロックの競合は、彩度の高いディスク ドライブの可能性があります。  
  
 Message Delivery Throttling State と各ホスト インスタンスに Message Publishing Throttling State の監視は、通常調整のトラブルシューティングを開始するに適しています。 これらのカウンターの値が 0 でない場合は、BizTalk Server システム内で調整が行われている、さらに、ボトルネックの原因を分析することがあることを示してです。 その他のパフォーマンス カウンターの説明については、次を参照してください。[データベース層のボトルネックを識別する](http://go.microsoft.com/fwlink/?LinkID=154678)(http://go.microsoft.com/fwlink/?LinkID=154678) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
## <a name="biztalk-server-system-performance-counters"></a>BizTalk Server システムのパフォーマンス カウンター  
  
|オブジェクト|Instance|カウンター|監視の目的|  
|------------|--------------|-------------|------------------------|  
|プロセッサ|_Total|[% プロセッサ時間]|リソースの競合|  
|[処理]|BTSNTSvc|Virtual Bytes|メモリ リーク/メモリの肥大化|  
|[処理]|BTSNTSvc|Private Bytes|メモリ リーク/メモリの肥大化|  
|[処理]|BTSNTSvc|Handle Count|リソースの競合|  
|[処理]|BTSNTSvc|スレッド数|リソースの競合|  
|Physical Disk|_Total|% Idle Time|リソースの競合|  
|Physical Disk|_Total|Current Disk Queue Length|リソースの競合|  
  
## <a name="biztalk-application-counters"></a>BizTalk アプリケーション カウンター  
  
|オブジェクト|Instance|カウンター|Description|  
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
  
-   [監視の調整](../technical-guides/monitoring-for-throttling.md)