---
title: BizTalk Server データベースの監視 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f137fc5-0e95-4952-8465-008771a1a377
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d0ad2f450a859bc7c56a4829ba5315745fbf80a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298922"
---
# <a name="monitor-the-biztalk-server-databases"></a>BizTalk Server データベースを監視します。
管理、メッセージ ボックスで、または DTA データベースにおける既知の問題を識別するモニターの BizTalk Server の SQL エージェント ジョブを実行することができます。 このジョブは、BizTalk Server 管理コンソールで BizTalk グループを構成するとき、または以前のバージョンから BizTalk をアップグレードするときに作成されます。  
  
## <a name="the-monitor-biztalk-server-job"></a>BizTalk Server ジョブの監視  
 Monitor BizTalk Server ジョブは、管理、メッセージ ボックス、および DTA データベースで次の問題をスキャンします。  
  
> [!NOTE]  
>  Monitor BizTalk Server ジョブは、問題のスキャンしか行いません。 検出された問題の修正は行いません。  
  
-   参照のないメッセージ  
  
-   参照カウントのないメッセージ  
  
-   0 未満の参照カウントのあるメッセージ  
  
-   スプール行のないメッセージ参照  
  
-   インスタンスのないメッセージ参照  
  
-   インスタンスのないインスタンス状態  
  
-   対応するインスタンスのないインスタンス サブスクリプション  
  
-   孤立した DTA サービス インスタンス  
  
-   孤立した DTA サービス インスタンスの例外  
  
-   グローバル追跡オプションが有効になっているときに、TDDS は任意のホスト インスタンスで実行されていません  
  
 Monitor BizTalk Server ジョブは、週に 1 回実行するよう構成および自動化されています。 ジョブがコンピューターに負荷がないため、ダウンタイムまたはトラフィックの少ない時間帯に実行するようにスケジュールすることをお勧めします。  
すべての問題が発生した場合、ジョブが失敗しました。返されるエラー文字列には、検出された問題の数が含まれています。 問題が見つからない場合は、正常に実行されます。 ジョブ履歴に詳細を表示できます。 管理者特権を持つジョブを実行する場合、エラー文字列は、ジョブ履歴と、SQL Server アプリケーション ログの両方に記録されます。  
  
> [!IMPORTANT]  
>  このジョブの障害は必ずしもなりませんの重要な問題が調査して、BizTalk Server データベースの定期的なメンテナンスの一環としてアドレス指定する必要がある問題ではなく、します。 このジョブは、上記の問題の 1 つは、検出イベントで、デザインによって失敗します。 上の問題に関する詳細情報の一覧に、これらの問題をトラブルシューティングするマイクロソフト製品サポート サービスでよく使用されるユーティリティにアクセスするには「」を参照してください。 [BizTalk によって特定された問題を解決するには BizTalk 終端記号の使用MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=210367) (http://go.microsoft.com/fwlink/?LinkId=210367)。