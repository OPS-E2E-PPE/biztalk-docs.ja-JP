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
ms.openlocfilehash: d5a4db14f9bdebc8d368a21d6955547d65e2eb7f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379450"
---
# <a name="monitor-the-biztalk-server-databases"></a>BizTalk Server データベースを監視します。
管理、メッセージ ボックス、または DTA データベースの既知の問題を識別するために、モニターの BizTalk Server の SQL エージェント ジョブを実行することができます。 BizTalk Server 管理コンソールで、BizTalk グループの構成または以前のバージョンから BizTalk をアップグレードするときに、ジョブが作成されます。  
  
## <a name="the-monitor-biztalk-server-job"></a>BizTalk Server ジョブの監視  
 Monitor BizTalk Server ジョブは、管理、メッセージ ボックス、および DTA データベースで、次の問題をスキャンできます。  
  
> [!NOTE]  
>  Monitor BizTalk Server ジョブは、のみの問題をスキャンします。 発見された問題の修正は行いません。  
  
- 参照のないメッセージ  
  
- 参照カウントのないメッセージ  
  
- メッセージ参照数は 0 より小さい  
  
- スプール行のないメッセージ参照  
  
- インスタンスのないメッセージ参照  
  
- インスタンスのないインスタンスの状態  
  
- 対応するインスタンスのないインスタンス サブスクリプション  
  
- 孤立した DTA サービス インスタンス  
  
- 孤立した DTA サービス インスタンスの例外  
  
- グローバル追跡オプションが有効な場合に、TDDS はホスト インスタンスで実行されていません  
  
  Monitor BizTalk Server ジョブが構成され、1 週間に 1 回実行する自動します。 ジョブがコンピューターに負荷がないため、ダウンタイムまたは低トラフィックの期間中に実行するようにスケジュールすることをお勧めします。  
  すべての問題が発生した場合、ジョブが失敗しました。返されるエラー文字列には、検出された問題の数が含まれています。 それ以外の場合、正常に実行します。 ジョブ履歴で詳細を確認できます。 管理者特権を持つジョブを実行する場合、エラー文字列がジョブ履歴と、SQL Server アプリケーション ログの両方に記録されます。  
  
> [!IMPORTANT]  
>  このジョブの障害とは限りませんものではありませんが、重要な問題、問題を調査して、BizTalk Server データベースの定期的なメンテナンスの一環としてアドレス指定する必要がありますではなく。 このジョブは、上記の問題のいずれかが検出された場合に、デザインによって失敗します。 上記の問題に関する詳細については、これらの問題のトラブルシューティングを行うマイクロソフト製品サポート サービスでよく使用されるユーティリティにアクセスするにを参照してください[BizTalk によって特定された問題を解決するには BizTalk 終端記号の使用。MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=210367) (http://go.microsoft.com/fwlink/?LinkId=210367)します。