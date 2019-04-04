---
title: タスクの監視ルーチン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2f9f56a-c839-4108-933d-69b00a1e3817
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d500e79cdf20c6a1914708976101715c2f00ae69
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001659"
---
# <a name="routine-monitoring-tasks"></a>定期的な監視タスク
定期的なスケジュールごとに次の監視タスクを実行する際に役立つを管理することで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションとインフラストラクチャを運用できる状態です。  
  
## <a name="daily-monitoring-tasks"></a>毎日の監視タスク  
  
- すべてのオープン アラートを確認する。  
  
- 使用して、**グループ ハブ**ページで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをオーケストレーション、ポート、およびメッセージのエラーを調査します。 **グループ ハブ**ページがメッセージ ボックス データベース内のデータにアクセスする、システムの現在のリアルタイムの状態へのアクセスを提供します。 オーケストレーション、ポート、メッセージングなどのすべてのサービス インスタンスと、それに関連するメッセージを表示できます。 使用して、**グループ ハブ**ページは次のアクティビティを実行することができます。  
  
  - 現在実行中のオーケストレーションなどのサービス インスタンスとメッセージング、およびその関連するメッセージを参照してください。  
  
  - 現在のデータおよびシステムのリアルタイムの状態について、メッセージ ボックス データベースを調べます。  
  
  - サービス インスタンスを中断、終了、および再開します。  
  
    使用しての詳細については、**グループ ハブ**ページを参照してください[ http://go.microsoft.com/fwlink/?LinkId=155281](http://go.microsoft.com/fwlink/?LinkId=155281)します。  
  
- 警告を見直す (省略可)。  
  
  詳細については、[チェックリスト: 毎日のメンテナンス チェックを実行する](../technical-guides/checklist-performing-daily-maintenance-checks.md)を参照してください。  
  
## <a name="weekly-monitoring-tasks"></a>週単位の監視タスク  
  
- 1 週間あたり 1 回以上のイベント ログを確認します。 このタスクの理由は、DBNetLib エラーが検出漏れなどの問題を防ぐためです。 非常に低待機時間システムがない限り、サービスの中断が気付かない場合があります。 ただし、これらのエラーのいくつか (例が多すぎるホストまたはメッセージ ボックス SQL ボックスなどのパフォーマンスの問題の数の BizTalk Server サーバー) の問題が大きくを示すことができます。  
  
  詳細については、[チェックリスト: 毎週のメンテナンス チェックを実行する](../technical-guides/checklist-performing-weekly-maintenance-checks.md)を参照してください。  
  
## <a name="as-needed-tasks"></a>必要に応じてタスク  
  
- 監視をカスタマイズする規則を変更する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションとインフラストラクチャ。  
  
- ログのパフォーマンス分析ツール (PAL) を実行します。 場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]デプロイがかなり高く (たとえば、新しい取引先パートナーは、定期的に追加されていない新しいコードが展開されていない)、実行する Perfmon および PAL 四半期に 1 回またはごとの 6 か月です。 場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置の変更より頻繁にすることもパフォーマンス モニターを実行して、PAL の数を基準と比較するか月ごと。 PAL の詳細については、[パフォーマンス分析のログ (PAL) ツールを使用して](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)を参照してください。  
  
- 実行のパフォーマンス モニターで変更の数によっては四半期に 1 回または回 6 か月に、すべての数か月に発生する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開します。  
  
- BizTalk Server のベスト プラクティス アナライザーを実行するときに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置の変更 (新しいアプリケーションの追加など) や、新しいホストの作成。 BizTalk Server ベスト プラクティス アナライザーでダウンロードできます[ http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317)します。  
  
- 実行、 [BizTalk MsgBoxViewer ツール](http://go.microsoft.com/fwlink/?LinkId=151930)(http://go.microsoft.com/fwlink/?LinkId=151930)します。 このツールは、BizTalk メッセージ ボックスとその他のデータベースを分析し、その他の情報がデータベースに関連している場合、警告を含む、HTML レポートが生成されます。  
  
  > [!TIP]  
  >  後で使用できるレポートを保存することもできます。 これらのレポートは、BizTalk アプリケーションの問題のトラブルシューティングを行う便利な可能性があります。  
  
  > [!NOTE]  
  >  、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関する保証をいたしません。 このプログラムは、ユーザー自身の責任で使用してください。  
  
- 実行、[ターミネータ ツール](http://go.microsoft.com/fwlink/?LinkId=151931)(http://go.microsoft.com/fwlink/?LinkId=151931)します。 このツールでは、簡単に BizTalk MsgBoxViewer ツールによって特定された問題を解決することができます。 BizTalk MsgBoxViewer ツールを使用して、終端記号のツールを統合する方法の詳細については、[BizTalk MsgBoxViewer によって特定された問題を解決するには BizTalk 終端記号のを使用して](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932)を参照してください。  
  
  > [!NOTE]  
  >  、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関する保証をいたしません。 このプログラムは、ユーザー自身の責任で使用してください。  
  
## <a name="annual-monitoring-tasks"></a>年間の監視タスク  
  
- 監視の有効性を確認して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションとインフラストラクチャ。  
  
- 監視に必要な変更を加えるための計画を作成します。  
  
## <a name="see-also"></a>参照  
 [定期メンテナンスのチェックリスト](../technical-guides/routine-maintenance-checklists.md)