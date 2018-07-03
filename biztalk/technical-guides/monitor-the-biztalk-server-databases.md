---
title: BizTalk Server データベースの監視 |Microsoft Docs
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
ms.openlocfilehash: b041822791b08890a34c39f3658de879062d9fb7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973819"
---
# <a name="monitor-the-biztalk-server-databases"></a>BizTalk Server データベースを監視します。
管理、メッセージ ボックス、または DTA データベースの既知の問題を識別するために、モニターの BizTalk Server の SQL エージェント ジョブを実行することができます。 このジョブは、BizTalk Server 管理コンソールで BizTalk グループを構成するとき、または以前のバージョンから BizTalk をアップグレードするときに作成されます。  
  
## <a name="the-monitor-biztalk-server-job"></a>BizTalk Server ジョブの監視  
 Monitor BizTalk Server ジョブは、管理、メッセージ ボックス、および DTA データベースで次の問題をスキャンします。  
  
> [!NOTE]  
>  Monitor BizTalk Server ジョブは、問題のスキャンしか行いません。 検出された問題の修正は行いません。  
  
- 参照のないメッセージ  
  
- 参照カウントのないメッセージ  
  
- 0 未満の参照カウントのあるメッセージ  
  
- スプール行のないメッセージ参照  
  
- インスタンスのないメッセージ参照  
  
- インスタンスのないインスタンス状態  
  
- 対応するインスタンスのないインスタンス サブスクリプション  
  
- 孤立した DTA サービス インスタンス  
  
- 孤立した DTA サービス インスタンスの例外  
  
- グローバル追跡オプションが有効な場合に、TDDS はホスト インスタンスで実行されていません  
  
  Monitor BizTalk Server ジョブは、週に 1 回実行するよう構成および自動化されています。 ジョブがコンピューターに負荷がないため、ダウンタイムまたは低トラフィックの期間中に実行するようにスケジュールすることをお勧めします。  
  すべての問題が発生した場合、ジョブが失敗しました。返されるエラー文字列には、検出された問題の数が含まれています。 問題が見つからない場合は、正常に実行されます。 ジョブ履歴に詳細を表示できます。 管理者特権を持つジョブを実行する場合、エラー文字列がジョブ履歴と、SQL Server アプリケーション ログの両方に記録されます。  
  
> [!IMPORTANT]  
>  このジョブの障害とは限りませんものではありませんが、重要な問題、問題を調査して、BizTalk Server データベースの定期的なメンテナンスの一環としてアドレス指定する必要がありますではなく。 このジョブは、上記の問題のいずれかが検出された場合に、デザインによって失敗します。 上記の問題に関する詳細については、これらの問題のトラブルシューティングを行うマイクロソフト製品サポート サービスでよく使用されるユーティリティにアクセスするにを参照してください[BizTalk によって特定された問題を解決するには BizTalk 終端記号の使用。MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=210367) (http://go.microsoft.com/fwlink/?LinkId=210367)します。