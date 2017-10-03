---
title: "チェックリスト: 月単位のパフォーマンス チェックの実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa103777-af4d-480d-abc7-3c4718f493c1
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3c1c84248fc3f5a7efdcc7e4df3f62b23bfcc82
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-performing-monthly-performance-checks"></a>チェックリスト: を実行する毎月パフォーマンス チェック
このトピックは月単位のパフォーマンスの問題を避けるために従う必要のあるベスト プラクティスの一覧、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムです。  
  
|手順|リファレンス|  
|-----------|---------------|  
|計画時に追跡するために必要な情報を決定します。|プロジェクトを展開した後に追跡オプションを指定し、追跡データの量を制限して必要な情報だけを取得するために、計画段階中に追跡する情報を決定する必要があります。 **注:**追跡に関連するベスト プラクティスに関する詳細については、次を参照してください[追跡の計画](../technical-guides/planning-for-tracking.md)このガイドでと[状態と動作状況の追跡](http://go.microsoft.com/fwlink/?LinkId=154187)(http://go.microsoft.com/fwlink/。?LinkId = 154187) で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ドキュメント。|  
|すべてのメッセージを追跡しません。|お勧めできませんのすべてのメッセージを追跡するたびに、メッセージがブラウザーであるため[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]別のコピーを作成します。 特定のポートのみを追跡すると、代わりにスコープを絞ることができます。 これにより、システムのパフォーマンスを最大限にし、データベースをきちんと整頓します。|  
|オーケストレーションのすべてのイベントを追跡しません。|オーケストレーションのすべてのイベントを追跡すると、dta_DebugTrace および dta_MessageInoutEvents テーブルのサイズが高まる可能性があります。 オーケストレーションの追跡を無効にする方法については、次を参照してください。[オーケストレーションの追跡を無効にする](../technical-guides/how-to-disable-tracking.md#BKMK_DisableOrchTracking)です。|  
|送信ポートの追跡を設定し、受信パイプラインでの代わりにポート|パイプラインに追跡オプションを設定すると、パイプラインを使用するすべてのポートに対してグローバルに追跡オプションも設定されます。 これは、順番が原因でより多くのデータが意図したものと追跡されているシステムのパフォーマンスが低下します。 代わりに、ポートの送信に追跡オプションを設定し、ポートを受信できます。|  
|リソース使用率に基づいた制限を調整します。|調整[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]既定では、システムの適切な保護を提供するように構成します。 かどうかの調整を実行して状態の調整のパフォーマンス カウンターを監視し、自分のゲージの調整のリソースが基づいている場合 (たとえば、データベースのサイズまたはメモリ使用率) の下または過大使用は、調整を調整ししきい値は切り上げまたは切り捨てです。 詳細については、次を参照してください。[制限のしきい値の調整: タイミングと理由](http://go.microsoft.com/fwlink/?LinkId=154188)(http://go.microsoft.com/fwlink/?LinkId=154188)。|  
|可能であれば、PassThruTransmit パイプラインを使用します。|宛先にメッセージを送信する前に、ドキュメント処理は必要ありません、XML 送信パイプラインではなく、PassThruTransmit パイプラインを使用します。|  
|BizTalk 追跡データベースのサイズを変更するとき、さまざまな要因を考慮します。|-ときは、BizTalk 追跡データベースのサイズ変更、コンティンジェンシー乗数を計算の結果に追加することで、インデックス サイズなど、SQL Server の要因を考慮してください。<br />-ときは、BizTalk 追跡データベース内のメッセージのサイズを特定するには、追加メッセージ コンテキストの平均サイズ メッセージのサイズに重要である場合メッセージ サイズと比較します。<br />、BizTalk 追跡データベース内のメッセージのサイズを制限するためには昇格したプロパティの数を制限します。<br />オーケストレーション デバッガーのオプションが有効になっている場合は、オーケストレーション内の各図形の状態は、BizTalk 追跡データベースに保存されているを考慮します。|  
|ディスクの競合を回避するためのハードウェア ソリューションを適用します。|メッセージ ボックス データベース内のディスクの競合を回避するのには、次の操作を行います。<br /><br /> -高速なディスクを使用します。<br />-高速な SAN 上のデータベースを展開します。<br />-分離は、追跡データベースから別の専用のサーバーにメッセージ ボックス データベース<br />-Cpu を拡大して、専用のメッセージ ボックス データベース サーバーに複数の Cpu を追加<br />-別のドライブに、ページファイルや MSDTC のログを移動します。<br /><br /> データベースの競合の回避の詳細については、次を参照してください。[ディスクの競合を回避する方法](http://go.microsoft.com/fwlink/?LinkId=158809)(http://go.microsoft.com/fwlink/?LinkId=158809)。|  
  
## <a name="see-also"></a>参照  
 [日常的なパフォーマンスのチェックリスト](../technical-guides/routine-performance-checklists.md)   
 [チェックリスト: 毎週のパフォーマンス チェックの実行](../technical-guides/checklist-performing-weekly-performance-checks.md)