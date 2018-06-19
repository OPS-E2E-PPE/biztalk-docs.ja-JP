---
title: タスクの監視ルーチン |Microsoft ドキュメント
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
ms.openlocfilehash: d91a49393e2b43c9cf39add35e06c5bd864782e8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22301906"
---
# <a name="routine-monitoring-tasks"></a>日常的な監視タスク
定期的なスケジュールに従ってを次の監視タスクを実行することは、支援残して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションとインフラストラクチャを運用できる状態です。  
  
## <a name="daily-monitoring-tasks"></a>日常的な監視タスク  
  
-   すべてのオープン アラートを確認する。  
  
-   使用して、**グループ ハブ** ページで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーション、ポート、およびメッセージのエラーを調査するために管理コンソールです。 **グループ ハブ**ページは、メッセージ ボックス データベース内のデータにアクセスする、システムの現在のリアルタイムの状態へのアクセスを提供します。 オーケストレーション、ポート、メッセージングなどのすべてのサービス インスタンスと、それに関連するメッセージを表示できます。 使用して、**グループ ハブ**ページは次のアクティビティを実行することができます。  
  
    -   現在実行中のオーケストレーションなどのサービス インスタンスとメッセージ、および関連付けられているメッセージを参照してください。  
  
    -   現在のデータおよびシステムのリアルタイムの状態について、メッセージ ボックス データベースを調べます。  
  
    -   サービス インスタンスを中断、終了、および再開します。  
  
     使用しての詳細については、**グループ ハブ** ページを参照してください[http://go.microsoft.com/fwlink/?LinkId=155281](http://go.microsoft.com/fwlink/?LinkId=155281)です。  
  
-   警告を見直す (省略可)。  
  
 詳細については、次を参照してください。[チェックリスト: メンテナンスを毎日チェックを実行する](../technical-guides/checklist-performing-daily-maintenance-checks.md)です。  
  
## <a name="weekly-monitoring-tasks"></a>毎週監視タスク  
  
-   毎週 1 回以上のイベント ログを確認します。 このタスクに対する理由見逃さ DBNetLib エラーなどの問題を回避するためです。 非常に低い待機時間システムがない限り、サービスの中断が気付かない場合があります。 ただし、これらのエラーのいくつか (例が多すぎますホストまたはメッセージ ボックス、SQL ボックスなどのパフォーマンスの問題の数の BizTalk Server サーバー) の問題が大きくを示すことができます。  
  
 詳細については、次を参照してください。[チェックリスト: 毎週の保守チェックを実行して](../technical-guides/checklist-performing-weekly-maintenance-checks.md)です。  
  
## <a name="as-needed-tasks"></a>必要なタスク  
  
-   監視をカスタマイズする規則を変更する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションとインフラストラクチャです。  
  
-   ログのパフォーマンス分析ツール (PAL) を実行します。 場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開はかなり定数 (たとえば、新しい取引先は日常的に、追加された新しいコードが展開されていない)、可能性がありますを実行するパフォーマンス モニターと PAL 四半期に 1 回ごと、またはでもは 6 か月です。 場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置の変更より多くの場合は、可能性があるパフォーマンス モニターを実行し、だれか月間、ベースラインと比較する 2 ~ 3 おきです。 PAL の詳細については、次を参照してください。[パフォーマンス分析のログ (PAL) のツールを使用して](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)です。  
  
-   発生するパフォーマンス モニターの実行の数か月ごと、変更の数に基づいて四半期に 1 回ごと、またはでもは 6 か月に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開します。  
  
-   BizTalk Server ベスト プラクティス アナライザーを実行するときに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置の変更 (たとえば、新しいアプリケーションの追加)、または新しいホストを作成します。 BizTalk Server ベスト プラクティス アナライザーでダウンロードできます[http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317)です。  
  
-   実行、 [BizTalk MsgBoxViewer ツール](http://go.microsoft.com/fwlink/?LinkId=151930)(http://go.microsoft.com/fwlink/?LinkId=151930)。 このツールでは、BizTalk メッセージ ボックス データベースとその他のデータベースを分析し、その他の情報がデータベースに関連している場合、警告を含む HTML レポートを生成します。  
  
    > [!TIP]  
    >  後で使用できるレポートを保存することもできます。 これらのレポートは、BizTalk アプリケーションの問題のトラブルシューティングを行うときに役立ちます可能性があります。  
  
    > [!NOTE]  
    >  、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。  
  
-   実行、[ターミネータ ツール](http://go.microsoft.com/fwlink/?LinkId=151931)(http://go.microsoft.com/fwlink/?LinkId=151931)。 このツールでは、簡単に BizTalk MsgBoxViewer ツールによって識別される問題を解決することができます。 ターミネータ ツールが、BizTalk MsgBoxViewer ツールと統合する方法の詳細については、次を参照してください。 [BizTalk MsgBoxViewer によって特定された問題を解決するには BizTalk のターミネータを使用して](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932)。  
  
    > [!NOTE]  
    >  、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。  
  
## <a name="annual-monitoring-tasks"></a>年間の監視タスク  
  
-   監視の有効性を確認、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションとインフラストラクチャです。  
  
-   変更を加える必要な監視の計画を作成します。  
  
## <a name="see-also"></a>参照  
 [定期的なメンテナンスのチェックリスト](../technical-guides/routine-maintenance-checklists.md)