---
title: "BizTalk Server の一般的な Optimizations2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41b452e9-d94c-4bcb-8ef6-e9cea28fc0ab
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 622844e282b9b0206f92979827406a324cd2f86f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="general-biztalk-server-optimizations"></a>BizTalk Server の一般的な最適化
増やすには次の推奨事項を使用することができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンス。 このトピックで示した最適化が後に適用されます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をインストールして構成します。  
  
## <a name="create-multiple-biztalk-server-hosts-and-separate-host-instances-by-functionality"></a>機能によって、複数の BizTalk Server ホストと別のホスト インスタンスを作成します。  
 個別のホストは、送信、受信、処理、および追跡機能を作成してください。 複数の BizTalk ホストを作成する、BizTalk グループで、ワークロードを構成する際の柔軟性を BizTalk グループ内の BizTalk サーバー間での処理を分散する主な手段。 複数のホストを使用して、他のホストに影響を与えずに 1 つのホストを停止することもできます。 たとえば、停止できるようにメッセージを送信するキュー メッセージ ボックス データベースで発生するメッセージの受信の受信状態のままする可能性があります。 機能別のホスト インスタンスを分離すると、次の利点も提供されます。  
  
-   各ホスト インスタンスでは、.NET スレッド プールでメモリ、ハンドル、およびスレッドなどのリソースの独自セットがあります。  
  
-   複数の BizTalk ホストでは、各ホストには、メッセージ ボックス データベースに独自の作業キュー テーブルが割り当てられるために、メッセージ ボックス データベースのホスト キュー テーブルでの競合も減少します。  
  
-   制限については、ホスト レベルで BizTalk Server で実装されます。 これにより、ホストごとに異なる調整特性を設定することができます。  
  
-   ホスト レベルでセキュリティが実装されています。各ホストは、個別の Windows id で実行されます。 これは、ようにすると、たとえば、いずれかのファイル共有にアクセスするその他のホストを許可していませんしながら FileShare_B を host_a 上でアクセスできるようにします。  
  
> [!NOTE]  
>  追加のホスト インスタンスを作成する利点があるときに欠点がありますも潜在的な多数のホスト インスタンスが作成される場合。 各ホスト インスタンスは、メッセージ ボックス データベースに対して追加の負荷を生成し、コンピューターのリソース (CPU、メモリ、スレッド) などを使用する Windows サービス (BTSNTSvc.exe) です。  
  
 BizTalk Server ホストのプロパティの変更の詳細については、「どのようにするホスト プロパティの変更」、BizTalk Server ヘルプでを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=101588](http://go.microsoft.com/fwlink/?LinkId=101588)です。  
  
## <a name="configure-a-dedicated-tracking-host"></a>専用の追跡ホストを構成します。  
 BizTalk Server は、メインのオーケストレーションとメッセージング エンジンは実際に移動しないメッセージ、BizTalk 追跡または BAM データベースに直接ビジネス プロセスを実行するがプライマリ ジョブからこれらのエンジンをそらすこれは、スループット、に対して最適化されます。 代わりに、BizTalk Server は、メッセージ ボックス データベース、メッセージのままにし、BizTalk 追跡データベースへの移行を必須としてマークを付けます。 バック グラウンド プロセス (追跡ホスト) し、BizTalk 追跡データベースおよび BAM データベースにメッセージを移動します。 追跡はリソースの処理を要する操作のため、独立したホスト作成してください専用の追跡、追跡がメッセージの処理に専用ホストを持つことの影響を最小限に抑えること。  
  
 BizTalk Server 追跡を妨げることがなく他の BizTalk ホストを停止する専用の追跡ホストを使用できます。 追跡メッセージ ボックス データベースからデータの移動は、正常な BizTalk Server システムにとって重要です。 BizTalk グループ内の追跡データの移動を担当する BizTalk ホストを停止すると、データのデコードに追跡サービスは実行されません。 この効果は次のとおりです。  
  
-   HAT 追跡データは、BizTalk 追跡データベースにメッセージ ボックス データベースから移動されません。  
  
-   BAM の追跡データは、BAM プライマリ インポート データベースにメッセージ ボックス データベースから移動されません。  
  
-   データが移動されていないために、メッセージ ボックス データベースから削除できません。  
  
-   データのデコードに追跡サービスが停止したときに追跡インターセプターは引き続きファイア アンド メッセージ ボックス データベースに追跡データを書き込みます。 データが移動されていない場合は、一定期間のパフォーマンスに影響を与えるメッセージ ボックス データベースになります肥大化、これにより、します。 場合でも、カスタム プロパティは追跡されませんまたは BAM プロファイルが設定されていない、既定では一部のデータは、追跡 (など、パイプラインは、受信/送信イベントおよびオーケストレーションのイベント)。 データのデコードに追跡サービスを実行しないようにする場合は、すべての追跡インターセプターをデータベースにデータ保存しないようにオフにします。 グローバル追跡を無効にするを参照してください「にオフ グローバルの追跡の方法」BizTalk server でヘルプを[http://go.microsoft.com/fwlink/?LinkId=101589](http://go.microsoft.com/fwlink/?LinkId=101589)です。 選択的に追跡イベントを無効にするのにには、BizTalk Server 管理コンソールを使用します。  
  
 追跡ホストは、BizTalk サーバー (1 つが失敗した場合の冗長構成) を実行するには、少なくとも 2 台のコンピューターで実行する必要があります。 最適なパフォーマンスが必要には、少なくとも 1 つの追跡メッセージ ボックス データベースごとにホストのインスタンス。 追跡ホスト インスタンスの実際の数になります (N は + 1)、ここで N = メッセージ ボックス データベースの数。 「+ 1」の追跡をホストしているコンピューターのいずれかに失敗した場合は、冗長性のため、します。  
  
 追跡ホスト インスタンスが特定のメッセージ ボックス データベースの追跡データを移動しますが、されません 1 つ以上の追跡ホスト インスタンスの特定のメッセージ ボックス データベースのデータを移動します。 たとえば、3 つのメッセージ ボックス データベースと 2 つのホスト インスタンスの追跡がある場合は、そのホスト インスタンスのいずれかの必要があります、メッセージ ボックス データベースの 2 つのデータを移動します。 追跡を配布して、3 番目のホスト インスタンスの追跡を追加する BizTalk Server を実行している別のコンピューターへの作業をホストします。 このシナリオでは、複数の追跡ホストの配布と 4 つ目のホスト インスタンスの追跡を追加する機能しますが、余分なは、フォールト トレランスのホスト インスタンスを追跡します。  
  
 BAM イベント バス サービスの詳細については、BizTalk Server ヘルプの次のトピックを参照してください。  
  
-   「BAM イベント バス サービスを管理する」 [http://go.microsoft.com/fwlink/?LinkId=101590](http://go.microsoft.com/fwlink/?LinkId=101590)です。  
  
-   「BAM イベント バス サービスのインスタンスを作成する」 [http://go.microsoft.com/fwlink/?LinkId=101591](http://go.microsoft.com/fwlink/?LinkId=101591)です。  
  
## <a name="manage-aspnet-thread-usage-or-concurrently-executing-requests-for-web-applications-that-host-orchestrations-published-as-a-web-or-wcf-service"></a>ASP.NET スレッドの使用状況を管理またはホストのオーケストレーションが Web または WCF サービスとして公開する Web アプリケーションの要求に同時に実行します。  
 Web サービスを変更する必要があります、多数のワーカーと I/O スレッド (IIS 6.0 および IIS 7.0 でクラシック モード) またはオーケストレーションをホストする ASP.NET Web アプリケーションの要求 (統合モードの IIS 7.0) を同時実行の数に公開します次の条件。  
  
-   CPU 使用率がホストする Web サーバー上のボトルネックではありません。  
  
-   値、 **ASP.NET アプリ v2.0.50727\Request Wait Time**または**ASP.NET アプリ v2.0.50727\Request 実行時間**パフォーマンス カウンターが異常に高いです。  
  
-   Web アプリケーションをホストするコンピューターのアプリケーション ログに生成された次のようなエラー:  
  
    ```  
    Event Type: Warning  
    Event Source: W3SVC Event Category: None  
    Event ID: 1013  
    Date: 6/4/2009  
    Time: 1:03:47 PM  
    User: N/A  
    Computer: <ComputerName>  
    Description: A process serving application pool 'DefaultAppPool' exceeded time limits during shut down. The process id was '<xxxx>'  
    ```  
  
### <a name="manage-aspnet-thread-usage-for-web-applications-that-host-orchestrations-on-iis-60-and-on-iis-70-running-in-classic-mode"></a>クラシック モードで実行されている IIS 7.0 および IIS 6.0 でオーケストレーションをホストする Web アプリケーションの ASP.NET スレッドの使用状況を管理します。  
 ときに、 **autoConfig** IIS 6.0 サーバーまたはクラシック モードで実行されている IIS 7.0 サーバーの machine.config ファイル内の値に設定されて**true**、ASP.NET 2.0 がワーカー スレッドの数を管理し、I/O スレッドは、関連付けられている IIS ワーカー プロセスに割り当てられています。  
  
```  
<processModel autoConfig="true" />  
```  
  
 ワーカー ロールと ASP.NET 2.0 Web アプリケーションの I/O スレッドの数を手動で変更するには、関連付けられている machine.config ファイルを開くし、新しい値を入力し、 **maxWorkerThreads**と**maxIoThreads**パラメーター。  
  
```  
<!-- <processModel autoConfig="true" /> -->  
    <processModel maxWorkerThreads="200" maxIoThreads="200" />  
```  
  
> [!NOTE]  
>  これらの値は、ガイダンスだけです。これらのパラメーターへの変更をテストすることを確認します。  
  
 ASP.NET 2.0 Web アプリケーションの machine.config ファイル内のパラメーターの調整の詳細については、マイクロソフト サポート技術情報の記事を参照してください[821268"の競合、パフォーマンスの低下、および ASP.NET から Web サービス要求を作成するときにデッドロック。アプリケーション"](http://go.microsoft.com/fwlink/?LinkID=66483) (http://go.microsoft.com/fwlink/?LinkID=66483)。  
  
### <a name="manage-the-number-of-concurrently-executing-requests-for-web-applications-that-host-orchestrations-on-iis-70-running-in-integrated-mode"></a>統合モードで実行されている IIS 7.0 でオーケストレーションをホストする Web アプリケーションの要求を同時に実行する数を管理します。  
 ASP.NET 2.0 が統合モードで IIS 7.0 でホストされている場合のスレッドの使用が異なる方法よりも IIS 6.0 または IIS 7.0 でクラシック モードでします。 ASP.NET 2.0 が同時実行の数を制限して ASP.NET 2.0 が統合モードで IIS 7.0 でホストされている場合**要求**の数ではなく**スレッド**要求を同時に実行します。 同期シナリオのこの直接が制限されましていないスレッドの数が非同期シナリオの要求およびスレッドの数が場合があります大きく異なります。 統合モードでは、IIS 7.0 で ASP.NET 2.0 を実行するときに、 **maxWorkerThreads**と**maxIoThreads** machine.config ファイル内のパラメーターが実行されているスレッドの数を制御するために使用されません。 指定された値を変更することで現在実行中の要求の数を CPU あたり 12 個の既定値から変更する代わりに、 **maxConcurrentThreadsPerCPU**です。 **MaxConcurrentThreadsPerCPU** reqistry または aspnet.config ファイルの構成セクションでは、値を指定することができます。 既定値を変更する次の手順に従って**maxConcurrentThreadsPerCPU**を現在実行中の要求の数を制御します。  
  
 **レジストリに maxConcurrentThreadsPerCPU 値を設定するには**  
  
> [!WARNING]  
>  レジストリ エディターの不適切な使用により問題が発生し、オペレーティング システムの再インストールが必要となることがあります。 レジストリ エディターは、ご自身の責任で使用してください。 バックアップ、復元、およびレジストリを変更する方法の詳細についてで Microsoft サポート技術情報の資料「Microsoft Windows レジストリの説明」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=62729](http://go.microsoft.com/fwlink/?LinkId=62729)です。  
  
> [!NOTE]  
>  この設定はグローバルであり、個々 のアプリケーション プールまたはアプリケーションに対しては変更できません。  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**regedit.exe**、順にクリック**ok**レジストリ エディターを起動します。  
  
2.  移動**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0**  
  
3.  次の手順に従って、キーを作成します。  
  
    1.  **編集** メニューのをクリックして**新規**、クリックして**キー**です。  
  
    2.  型**maxConcurrentThreadsPerCPU**、キーを押します**ENTER**です。  
  
    3.  下にある、 **maxConcurrentThreadsPerCPU**キー、maxConcurrentThreadsPerCPU の新しい値を持つ DWORD エントリを作成します。  
  
    4.  レジストリ エディターを閉じます。  
  
 **Aspnet.config ファイルの構成セクションで、アプリケーション プールの maxConcurrentThreadsPerCPU 値を設定するには**  
  
> [!NOTE]  
>  Microsoft .NET Framework 3.5 Service Pack 1 をインストールして、構成ファイルを使用して下の値の設定に対応する必要があります。 Microsoft .NET Framework 3.5 Service Pack 1 をダウンロードする[http://go.microsoft.com/fwlink/?LinkID=136345](http://go.microsoft.com/fwlink/?LinkID=136345)です。  
  
-   アプリケーション プールの aspnet.config ファイルを開き、新しい値を入力し、 **maxConcurrentRequestsPerCPU**と**requestQueueLimit**パラメーター。  
  
```  
<system.web>  
    <applicationPool maxConcurrentRequestsPerCPU="12" requestQueueLimit="5000"/>  
</system.web>  
```  
  
> [!NOTE]  
>  この値に指定された値より優先**maxConcurrentThreadsPerCPU**レジストリにします。 Aspnet.config ファイルの設定は、machine.config ファイルで設定を上書きする点を除いて、requestQueueLimit 設定は、processModel/requestQueueLimit として同じです。  
  
## <a name="define-clr-hosting-thread-values-for-biztalk-host-instances"></a>CLR ホストの BizTalk ホスト インスタンスのスレッドの値を定義します。  
 Windows スレッドは、Windows プロセスに使用できる最も基本的な実行可能単位なので、BizTalk ホストのインスタンスに関連付けられた .NET スレッド プールには十分なスレッドを割り当てて、スレッドが不足しないようにすることが重要です。 スレッドの不足が発生すると場合、パフォーマンスに悪影響を及ぼす影響を与える、要求された作業を実行するための十分なスレッドはできませんがあります。 同時に、ホストに関連付けられた .NET スレッド プールに必要以上にスレッドを割り当てないよう注意する必要があります。 ホストに関連付けられた .NET スレッド プールに割り当てたスレッドが多すぎると、コンテキストの切り替えが増加する場合があります。 コンテキストの切り替えは、Windows カーネル切り替えるパフォーマンス コストが生じます別のスレッドを 1 つのスレッドを実行しているときに発生します。 過剰なスレッドの割り当てとなるコンテキストの過度の切り替え、全体的なパフォーマンスが低下します。  
  
 BizTalk Server のレジストリに適切な CLR Hosting 値を作成することで、BizTalk ホストのインスタンスに関連付けられた .NET スレッド プールで使用できる Windows スレッドの数を変更します。  
  
> [!WARNING]  
>  レジストリ エディターの不適切な使用により問題が発生し、オペレーティング システムの再インストールが必要となることがあります。 レジストリ エディターは、ご自身の責任で使用してください。 バックアップ、復元、およびレジストリを変更する方法の詳細についてで Microsoft サポート技術情報の資料「Microsoft Windows レジストリの説明」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=62729](http://go.microsoft.com/fwlink/?LinkId=62729)です。  
  
> [!NOTE]  
>  **ワーカー スレッド**キューに置かれた作業項目の処理に使用して**I/O スレッド**専用のコールバック スレッドが完了した非同期 I/O 要求を処理する I/O 完了ポートに関連付けられています。  
  
 **BizTalk ホストの各インスタンスに関連付けられた .NET スレッド プールで使用できるスレッドの数を変更するには、次の手順を実行します。**  
  
1.  BizTalk ホスト インスタンスを停止します。  
  
2.  をクリックして**開始**、 をクリックして**実行**、型**regedit.exe**、順にクリック**ok**レジストリ エディターを起動します。  
    移動**hkey_local_machine \system\currentcontrolset\services\btssvc$***hostname*] 場所*ホスト名*ホストに関連付けられているホストの名前を指定しますインスタンス。  
  
    > [!NOTE]  
    >  このレジストリ キーとして表すことができる場合、BizTalk Server 2004 から BizTalk Server 2006 インストールをアップグレードした**hkey_local_machine \system\currentcontrolset\services\btssvc***guid*]ここで*guid* GUID は一意では、BizTalk Server ホストの各インスタンスにします。  
  
3.  検索、 **CLR Hosting**キー。 このキーが存在しない場合は、次の手順に従って、キーを作成します。  
  
    1.  **編集** メニューのをクリックして**新規**、クリックして**キー**です。  
  
    2.  型**CLR Hosting**、キーを押します**ENTER**です。  
  
4.  下にある、 **CLR Hosting**キーを指定された値を使用して、次の DWORD エントリを作成します。  
  
    |DWORD エントリ|既定値|推奨値|  
    |-----------------|-------------------|-----------------------|  
    |MaxIOThreads|20|100|  
    |MaxWorkerThreads|25|100**重要:** 100 よりもこの値を増やすと、BizTalk Server メッセージ ボックス データベースをホストする SQL Server コンピューターのパフォーマンスに悪影響が持つことができます。 この問題が発生した場合、SQL Server でデッドロック状態が発生することがあります。 このパラメーターは 100 の値を超えて増加しませんをお勧めします。|  
    |MinIOThreads|1|25|  
    |MinWorkerThreads|1|25|  
  
    > [!NOTE]  
    >  上記の推奨値は、ほとんどのシナリオになりますが、各ホスト インスタンスで実行しているアダプター ハンドラーまたはオーケストレーションの数に応じて大きく必要があります。  
  
    > [!NOTE]  
    >  これらの値は、サーバー上のプロセッサの数を掛けた暗黙的にします。 たとえば、MaxWorkerThreads のエントリを 100 の値に設定すると、4 台の CPU を持つサーバーでは 400 の値が実質的に設定されます。  
  
5.  レジストリ エディターを閉じます。  
  
6.  BizTalk ホスト インスタンスを再起動します。  
  
## <a name="disable-tracking-for-orchestrations-send-ports-receive-ports-and-pipelines-when-tracking-is-not-required"></a>オーケストレーションの追跡を無効にする、送信ポート、受信ポート、およびパイプラインを追跡が必要ないです。  
 追跡のためデータには、メッセージ ボックス データベースに書き込み、その後、BizTalk 追跡データベースに非同期的に移動する BizTalk Server 内でオーバーヘッドがパフォーマンスが生じます。 追跡は、ビジネス要件ではない場合は、オーバーヘッドを削減し、パフォーマンスが向上するための追跡を無効になります。 追跡の構成の詳細については、「を構成する追跡を使用して、BizTalk Server 管理コンソール」BizTalk Server でのヘルプを参照してください。 [http://go.microsoft.com/fwlink/?LinkID=106742](http://go.microsoft.com/fwlink/?LinkID=106742)です。  
  
## <a name="decrease-the-purging-period-for-the-dta-purge-and-archive-job-from-7-days-to-2-days-in-high-throughput-scenarios"></a>DTA Purge and Archive ジョブから 7 日間で高スループットのシナリオ 2 日間に、パージ period を短縮します。  
 既定では、BizTalk Server でのデータを追跡するため、パージ間隔は 7 日間に設定します。 高スループットのシナリオでは、メッセージ ボックスおよびさらに悪い影響メッセージの処理スループットのパフォーマンスに影響を与えるは最終的に追跡データベース内のデータを過剰なビルドではこのことがあります。  
  
 高スループットのシナリオでは、ハードとソフト 7 日間の既定値から 2 日間に間隔をパージを減らします。 削除間隔を構成する方法の詳細については、「方法を構成、DTA Purge とアーカイブ ジョブ」BizTalk Server でヘルプを参照してください[http://go.microsoft.com/fwlink/?LinkID=104908](http://go.microsoft.com/fwlink/?LinkID=104908)です。  
  
## <a name="install-the-latest-service-packs"></a>最新のサービス パックをインストールします。  
 パフォーマンスの問題が発生する可能性を修正できる修正プログラムが含まれてとして、BizTalk Server と .NET Framework の両方の最新の service pack をインストールする必要があります。  
  
## <a name="do-not-cluster-biztalk-hosts-unless-absolutely-necessary"></a>クラスター化しない BizTalk ホストしない限り、どうしても必要な  
 中に[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]およびそれ以降のバージョンの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk ホストをクラスター リソースとして構成することを許可する必要がありますだけを考慮した複数の BizTalk 間でホストされることはできません、リソースへの高可用性を提供する必要がある場合は、これを行うコンピューターです。 例は、FTP アダプターを使用するポートはのみに存在する 1 つのホスト インスタンスでは、FTP プロトコルはファイルのロックを指定しないため、としてただし、この場合、単一点障害クラスタ リングからメリットを享受します。 ホスト ファイル、SQL、HTTP ホストのみを処理などのアダプターを含めることができます内部的に負荷は、コンピューター間で分散され、クラスター化から有効ではありません。  
  
## <a name="performance-optimizations-in-the-biztalk-server-documentation"></a>BizTalk Server のマニュアルでパフォーマンスの最適化  
 必要に応じて、BizTalk Server のドキュメントから次の推奨事項が適用されます。  
  
-   「メッセージ ボックスの遅延の問題のトラブルシューティング」 [http://go.microsoft.com/fwlink/?LinkId=114747](http://go.microsoft.com/fwlink/?LinkId=114747)  
  
-   「パフォーマンスのボトルネックを識別する」 [http://go.microsoft.com/fwlink/?LinkID=104418](http://go.microsoft.com/fwlink/?LinkID=104418)  
  
-   「DBNETLIB 例外の回避」 [http://go.microsoft.com/fwlink/?LinkID=108787](http://go.microsoft.com/fwlink/?LinkID=108787)  
  
-   「TCP/IP ポートの枯渇を回避する」 [http://go.microsoft.com/fwlink/?LinkID=101610](http://go.microsoft.com/fwlink/?LinkID=101610)  
  
-   「EPM スレッド プール サイズを設定」 [http://go.microsoft.com/fwlink/?LinkId=114748](http://go.microsoft.com/fwlink/?LinkId=114748)