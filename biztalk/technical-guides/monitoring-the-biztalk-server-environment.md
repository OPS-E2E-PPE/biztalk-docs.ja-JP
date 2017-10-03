---
title: "BizTalk Server 環境の監視 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: baae51cf-0284-429b-8335-bc1ac3e63f4c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57abd599c10ead5084eae59c9f7dbe1746be346a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-the-biztalk-server-environment"></a>BizTalk Server 環境を監視します。
監視することができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インフラストラクチャとアプリケーションを手動または自動のプロセスおよび次の表に示すようにツールを使用して、2 つのメソッドの組み合わせ。  
  
|手動または自動の監視|ツール|  
|------------------------------------|-----------|  
|監視の自動化|Microsoft System Center Operations Manager (Operations Manager)|  
|手動の監視|-**グループ ハブ** ページで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール<br />ログ (PAL) のツールのパフォーマンス分析<br />イベント ビューアー|  
  
 監視アプリケーションを実装するかどうかを使用してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールのヘルスを監視、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションし、問題の根本原因を識別する根本原因分析を実行します。  
  
 監視する際に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、これらの点に注意しています。  
  
-   インフラストラクチャが正常でもアプリケーションは正常でない場合があります (アプリケーションが無効なメッセージを受信して処理できない場合など)。  
  
-   インフラストラクチャに異常があってもアプリケーションは正常に実行されている場合もあります (サーバーがダウンしても負荷を引き継ぐのに十分なサーバーがホストに割り当てられている場合など)。  
  
-   インフラストラクチャの問題がアプリケーションの問題のように見える場合があります (サーバーがダウンしているためにメッセージの処理が遅れている場合など)。  
  
## <a name="monitoring-types"></a>監視の種類  
 監視、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]し、アプリケーションは、次の 4 つの主なカテゴリに分類します。  
  
-   可用性の監視  
  
-   正常性の監視  
  
-   パフォーマンスの監視  
  
-   しきい値の監視  
  
### <a name="availability-monitoring"></a>可用性の監視  
 質問に答える可用性の監視"は、システムまたはアプリケーション リソースによって阻止が利用できない、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションを最適に実行しますか?" こうした問題は、ほぼ例外なくシステム レベルの問題 (サービスや接続の可用性の問題など) です。 たとえば、エンタープライズ シングル サインオン サービスが停止しているためにアダプターがエラーになる場合、それは可用性の問題です。 ホストに割り当てられているサーバーのいずれかでエラーが発生して、アプリケーションのメッセージ処理が遅れている場合も可用性の問題です。 同様に、アプリケーションが停止してメッセージを処理できない場合も可用性の問題です。 次の表は、可用性の監視ツールを一覧表示します。  
  
|ツール|タスク|  
|----------|----------|  
|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール|チェック、**グループ ハブ** ページで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをアプリケーションやそのコンポーネント (ポート/オーケストレーション) が停止したかどうかを参照してください。|  
|Operations Manager 2007|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプターなどの重要な低レベル サービスが利用できない場合の管理パックと Operations Manager オペレーション コンソールのアラートが表示されます。 効果的に監視[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、監視する必要があります以外[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースやサーバーなど、アプリケーションが依存するリソース。 さらに、インストールして、SQL Server、インターネット インフォメーション サービス、および Windows ベース オペレーティング システム管理パックを使用する必要がありますもします。 Operations Manager は、イベント ログ、WMI、およびその他のイベント プロバイダーから目的のイベントを統合します。 すべての関連する管理パックのインストールに関する詳細については、次を参照してください。[チェックリスト: Operations Manager 2007 での BizTalk Server の監視](../technical-guides/checklist-monitoring-biztalk-server-with-operations-manager-2007.md)です。|  
|イベント ビューアー|アダプターの接続の問題やサービスの停止などをチェックします。|  
  
### <a name="health-monitoring"></a>ヘルス状態の監視  
 稼働状況の監視では、"正常でないアプリケーションやリソースがないかどうか" を確認できます。 たとえば、アプリケーションやその構成アイテムで現在例外的な状態が発生していないかどうかや、 メッセージ ペイロードのデータが無効なために保留されているメッセージがないかどうかを確認できます。 次の表に、稼働状況の監視のためのツールを示します。  
  
|ツール|タスク|  
|----------|----------|  
|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール|使用する、**グループ ハブ**ページとクエリ ページで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール アプリケーションの正常性の問題を特定し、その原因を分析します。|  
|Operations Manager|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックは、メッセージが中断されたサービス インスタンスにしたりすることを通知する防御の最前線、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションです。 Operations Manager から通知を受信した後に移行することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを問題のトラブルシューティングをします。|  
|イベント ビューアー|メッセージやオーケストレーションの処理の間に発生した問題を検出します。|  
  
### <a name="performance-monitoring"></a>パフォーマンス監視  
 パフォーマンス監視では、"システムの処理がどのくらい効率的に行われているか" を確認できます。 この種の監視では、主にデータベースやディスクのような物理的リソースへの負荷が焦点になります。 たとえば、CPU 使用率が常に 90 ～ 100% になっていて、メッセージのバックログが発生している場合は、コンピューター レベルのパフォーマンスに問題があります。 次の表に、パフォーマンス監視のためのツールを示します。  
  
|ツール|タスク|  
|----------|----------|  
|SQL クエリ アナライザー|データベースのサイズと内容を監視して、システムの問題を診断します。|  
|Operations Manager|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]重要な場合にアラートを表示する管理パックと Operations Manager オペレーション コンソールを構成できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス キュー サイズやホスト キュー サイズなどのパフォーマンス カウンターが、定義されたしきい値を超えています。 以外のパフォーマンスを監視する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]リソース、アプリケーションが依存しているデータベース サーバーもインストールして、SQL Server、インターネット インフォメーション サービス、および Windows ベース OS 管理パックを使用する必要があります。 すべての関連する管理パックのインストールに関する詳細については、次を参照してください。[チェックリスト: Operations Manager 2007 での BizTalk Server の監視](../technical-guides/checklist-monitoring-biztalk-server-with-operations-manager-2007.md)です。<br /><br /> パフォーマンス分析のログ (PAL) のツールを使用して、スループットのしきい値規則で使用するテストのしきい値の値をキャプチャする、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パック。 PAL ツールの詳細については、次を参照してください。[パフォーマンス分析のログ (PAL) のツールを使用して](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)です。|  
|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール|**グループ ハブ**でなど退避、準備実行するにはスケジュールでは、中断、ページが現在アクティブなサービス インスタンスの数などの主要なパフォーマンス メトリックを表示、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションです。|  
|ビジネス アクティビティ監視 (BAM)|ビジネス アプリケーションに関係する主要業績評価指標を追跡するビジネス プロセスの特定のステージを指定できます。 BAM を使用して、IT メトリック (たとえば、SLA のや実行時間) とビジネス指標を監視できます。|  
  
### <a name="threshold-monitoring"></a>しきい値の監視  
 カスタマイズしたしきい値規則は、完成度の高い操作環境に不可欠な要素です。 これらのしきい値ルールの多くは、Operations Manager で作成できます。 これらのしきい値ルールは、通常、BizTalk アプリケーションの要件に基づいています。 パフォーマンス分析のログ (PAL) のツールは、環境にこれらのしきい値に適切な値を確認するプロセスを合理化できます。 Microsoft System Center Operations Manager に使用されるデータの中心として使用できるいくつかの基本のしきい値の値に、PAL ツールが付属します。 Operations Manager でのこれらのしきい値規則の実装では、自動監視します。 さらに、管理者は、通知規則をセットアップすることができ、スクリプトを実行して、.NET コードの呼び出し、電子メールなどの送信) などのしきい値ルールのトリガーに基づくアクションを実行できます。 次の表は、しきい値の監視ツールを示します。  
  
|ツール|タスク|  
|----------|----------|  
|パフォーマンス分析のログ (PAL) のツール|PAL ツールは、パフォーマンス カウンターのしきい値を超える場合に自動的に報告します。 しきい値は、サーバーの環境に適したものを動的に変更します。 たとえば、しきい値を変更する、カーネル メモリ プールは、ユーザーが 32 ビットまたは 64 ビット アーキテクチャ、物理メモリ、および 3 GB スイッチの量の概要が提供された回答に基づいています。 PAL ツールを無料でダウンロードできます[http://www.codeplex.com/PAL](http://www.codeplex.com/PAL)です。|  
|Operations Manager|重要な場合にアラートを表示する BizTalk Server 管理パックと Operation Manager のオペレーション コンソールを構成できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]カウンターが、定義されたしきい値を超えています。|  
  
## <a name="troubleshooting"></a>トラブルシューティング  
 正常性の問題が見つかったら、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用することができます、アプリケーション、**グループ ハブ**ページと**クエリ**ページの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]問題を分析する管理コンソールです。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールは、統合の構成、展開およびトラブルシューティングのエクスペリエンスを提供し、構成と展開を修正する関連の管理コンソールで問題がそれらの問題を特定した後にします。 一般に、アプリケーションの問題のほとんどは、正しく処理されないメッセージに起因しています (中断されたサービス インスタンス、再試行中のポート、再アクティブ化されていない退避済みインスタンスなどとして現れる場合もあります)。  
  
 使用することができます、**グループ ハブ**ページと**クエリ**サービス インスタンスをグループ化するページ (どのような状態に: 実行して、中断、退避済みなど) アプリケーション、エラーの種類、サービスの種類、ホストなど、。で、さまざまなエラーを特定するのには、1 つずつ、を調査し、それらを修正します。