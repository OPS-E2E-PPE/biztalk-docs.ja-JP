---
title: メッセージ ボックス パフォーマンス カウンター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eafbd7b-f5fc-4942-a975-18154e6a7ee2
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 584cad0c850b85ef7c920da1611adbdc464d7250
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972784"
---
# <a name="message-box-performance-counters"></a>メッセージ ボックスのパフォーマンス カウンター
パフォーマンス カウンターを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。 パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。  
  
 次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできる、 **BizTalk:Message Box:general Counters**と**BizTalk:Message Box:host Counters**パフォーマンス オブジェクト カテゴリ:  
  
> [!NOTE]
>  SQL エージェント ジョブを参照するカウンターを有効にするには、BizTalk ホスト/NT サービスの実行に使用するサービス アカウントに対し、SQLAgentUserRole ロールを追加する必要があります。 代わりに、他のロールを使ってアクセス許可を付与するか、MSDB データベースの読み取りアクセス許可を明示的に付与してもかまいません。  
  
> [!NOTE]
>  BizTalk Server グループに新しいメッセージ ボックスを追加した場合は、以下に示すカウンターされるまでになりません、新しいメッセージ ボックスに使用できる、構成された**キャッシュ更新**(既定値は 60 を BizTalk Server グループの間隔が経過します秒単位)。  
  
|カテゴリ|カウンター|Description|  
|--------------|-------------|-----------------|  
|General Counters|Instances-Total Number|特定のメッセージ ボックス内に存在するインスタンスの合計数をホストごとに追跡します。|  
|General Counters|MsgBox Dead Processes Cleanup (Purge Jobs)|不要となった BizTalk プロセスに関連付けられたデータベース行を解放する SQL エージェント ジョブが最近実行されたときに要した時間 (秒単位)。|  
|General Counters|MsgBox Msg Cleanup (Purge Jobs)|時間 (秒) に関連付けられているメッセージ ボックス テーブルをクリーンアップする SQL エージェント ジョブの最近の実行は、メッセージを削除します。|  
|General Counters|MsgBox Parts Cleanup (Purge Jobs)|時間 (秒) に関連付けられているメッセージ ボックス テーブルをクリーンアップ メッセージ部分を削除する SQL エージェント ジョブが最近実行します。|  
|General Counters|MsgBox Purge Subscriptions Job (Purge Jobs)|使用されなくなったサブスクリプションを削除する SQL エージェント ジョブが最近実行されたときに要した時間 (秒単位)。|  
|General Counters|Spool Size|特定のサーバーの特定のメッセージ ボックス上のスプール サイズを追跡します。|  
|General Counters|Tracked Msgs Copy (Purge Jobs)|追跡メッセージの本文をコピーする SQL エージェント ジョブが最近実行されたときに要した時間 (秒単位)。|  
|General Counters|Tracking data size|特定のサーバー上の特定のメッセージ ボックスについて、追跡データ テーブルのサイズを追跡します。|  
|General Counters|Tracking Spool Cleanup (Purge Jobs)|非アクティブの追跡スプール テーブルを削除する SQL エージェント ジョブが最近実行されたときに要した時間 (秒単位)。|  
|ホスト カウンター|Host Queue - Instance State Msg Refs - Length|この特定のホストについて、インスタンスの状態キューに存在するメッセージの参照数を追跡します。|  
|ホスト カウンター|Host Queue - Length|特定のホスト キューに存在するメッセージの総数を追跡します。|  
|ホスト カウンター|Host Queue - Number of Instances|この特定のホストのインスタンス数を追跡します。|  
|ホスト カウンター|Host Queue - Suspended Msgs - Length|特定のホストで保留されているメッセージの総数を追跡します。|  
  
## <a name="to-access-performance-counters"></a>パフォーマンス カウンターにアクセスするには  
 パフォーマンス カウンターにアクセスするには、次の手順を実行します。  
  
#### <a name="if-you-are-using-windows-2008"></a>Windows 2008 を使用している場合  
  
1.  をクリックして**開始**、 をポイント**管理ツール**、順にクリック**パフォーマンス モニター**です。  
  
2.  **パフォーマンス モニター** ] ダイアログ ボックスで、展開**の監視ツールを**[**パフォーマンス モニター**、順にクリック**追加**です。  
  
3.  **カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、いずれかを選択**BizTalk:Message Box:general Counters**または**biztalk: メッセージ ボックス: ホスト カウンター**です。 選択したパフォーマンス カウンター オブジェクトを展開し、監視するカウンターを選択します。  
  
4.  **インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**です。  使用可能なカウンターのすべてのインスタンスを選択するには、次のように選択します。 \<**すべてのインスタンス**\>です。  
  
5.  カウンターを追加すると、をクリックして**OK**です。  
  
     選択したパフォーマンス カウンターが表示されます、**パフォーマンス モニター**画面。  
  
## <a name="see-also"></a>参照  
 [パフォーマンスのヒントとテクニック](../core/performance-tips-and-tricks.md)   
 [維持可能な最大のエンジン スループットの測定](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [維持可能な最大の追跡スループットの測定](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [ホスト制限によるリソース使用率の最適化](../core/optimizing-resource-usage-through-host-throttling.md)