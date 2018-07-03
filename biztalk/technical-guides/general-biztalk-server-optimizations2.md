---
title: BizTalk Server の一般的な Optimizations2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41b452e9-d94c-4bcb-8ef6-e9cea28fc0ab
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af09f938d93377a6463926fad3725c9f9dace294
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022184"
---
# <a name="general-biztalk-server-optimizations"></a>BizTalk Server の一般的な最適化
次の推奨事項は、向上に使用できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンス。 このトピックで示した最適化が後に適用されます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をインストールして構成します。  
  
## <a name="create-multiple-biztalk-server-hosts-and-separate-host-instances-by-functionality"></a>機能によって複数の BizTalk Server ホストと別のホスト インスタンスを作成します。  
 送信、受信、処理、および追跡機能の個別のホストを作成する必要があります。 複数の BizTalk ホストを作成して、柔軟に、BizTalk グループで、ワークロードを構成するときに、BizTalk グループ内の BizTalk サーバーの間での処理の分散の主要な手段は。 複数のホストでは、他のホストに影響を与えずに 1 つのホストを停止することもできます。 たとえば、停止できるようにメッセージを送信するキュー メッセージ ボックス データベースで発生するメッセージの受信の受信を許可する一方する可能性があります。 機能別のホスト インスタンスを分離することでは、次の利点も用意されています。  
  
-   各ホスト インスタンスでは、.NET スレッド プールでメモリ、ハンドル、スレッドなどのリソースの独自セットがあります。  
  
-   複数の BizTalk ホストは、各ホストには、独自の作業キュー テーブル、メッセージ ボックス データベースが割り当てられるために、メッセージ ボックス データベースのホスト キュー テーブルでの競合も軽減されます。  
  
-   調整は、ホスト レベルで BizTalk Server に実装されます。 これにより、各ホストの制限は異なる特性を設定することができます。  
  
-   ホスト レベルでセキュリティが実装されています。各ホストは、個別の Windows id の下で実行されます。 これは、ようにすると、たとえば、Host_A のアクセスを許可していないファイル共有にアクセスする他のホストのいずれかの中に FileShare_B を付与します。  
  
> [!NOTE]  
>  追加のホスト インスタンスを作成する利点はありますも潜在的な欠点が多すぎるのホスト インスタンスが作成された場合です。 各ホスト インスタンスは、メッセージ ボックス データベースに対して追加の負荷を生成およびコンピューターのリソース (CPU、メモリ、スレッド) などを利用する Windows サービス (BTSNTSvc.exe) です。  
  
 BizTalk Server ホストのプロパティを変更する方法の詳細については、「どのようにするホスト プロパティの変更」、BizTalk Server ヘルプでを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=101588](http://go.microsoft.com/fwlink/?LinkId=101588)します。  
  
## <a name="configure-a-dedicated-tracking-host"></a>専用の追跡ホストを構成します。  
 メインのオーケストレーションとメッセージング エンジンは実際には移動メッセージ、BizTalk 追跡または BAM データベースに直接実行しているビジネス プロセスの主な仕事からこれらのエンジンをそらすこれは、ために、スループットを BizTalk Server が最適化されています。 代わりに、BizTalk Server は、メッセージ、メッセージ ボックス データベースに残りますされ、BizTalk 追跡データベースへの移行を必要とするとしてマークを付けます。 バック グラウンド プロセス (追跡ホスト) し、BizTalk の追跡と BAM データベースにメッセージを移動します。 追跡がリソースの処理を要する操作であるため、個別のホストを作成してください専用の追跡、追跡メッセージの処理を専用のホスト上に影響を最小限に抑えます。  
  
 専用の追跡ホストを使用してでは BizTalk Server 追跡を妨げることがなく他の BizTalk ホストを停止することもできます。 追跡メッセージ ボックス データベースからデータの移動は、正常な BizTalk Server システムにとって重要です。 BizTalk グループ内の追跡データの移動を行う BizTalk ホストが停止している場合、データのデコードに追跡サービスは実行されません。 この効果は次のとおりです。  
  
- HAT 追跡データは、BizTalk 追跡データベースにメッセージ ボックス データベースから移動されません。  
  
- BAM の追跡データは、BAM プライマリ インポート データベースにメッセージ ボックス データベースから移動されません。  
  
- データが移動されていないために、メッセージ ボックス データベースから削除できません。  
  
- データのデコードに追跡サービスを停止すると、追跡インターセプタはまだ起動追跡データを書き込むメッセージ ボックス データベースにします。 データが移動されていない場合、メッセージ ボックス データベース、いっぱいになる時間の経過と共にパフォーマンスに影響できるようになります。 場合でも、カスタム プロパティは追跡されませんまたは BAM プロファイルが設定されていない、既定ではいくつかのデータが追跡 (など、パイプラインは、受信/送信イベントおよびオーケストレーションのイベント)。 データのデコードに追跡サービスを実行しない場合は、すべての追跡インターセプターをデータベースにデータ保存しないようにオフにします。 グローバル追跡を無効にするには、"有効にするオフ グローバルの追跡方法、BizTalk Server でのヘルプをご覧ください。 [ http://go.microsoft.com/fwlink/?LinkId=101589](http://go.microsoft.com/fwlink/?LinkId=101589)します。 BizTalk Server 管理コンソールを使用して、選択的に追跡イベントを無効にします。  
  
  追跡ホストは、BizTalk サーバー (1 つが失敗した場合の冗長性) を実行するには少なくとも 2 台のコンピューターで実行する必要があります。 最適なパフォーマンスを少なくとも 1 つの追跡がある必要がありますメッセージ ボックス データベースごとにホストのインスタンス。 追跡ホスト インスタンスの実際の数があります (N + 1)、N = メッセージ ボックス データベースの数。 「+ 1」の追跡をホストするコンピューターのいずれかが失敗した場合、冗長性のためです。  
  
  追跡ホスト インスタンスが特定のメッセージ ボックス データベースの追跡データを移動しますが、されません 1 つ以上の追跡ホスト インスタンスの特定のメッセージ ボックス データベースのデータを移動します。 たとえば、3 つのメッセージ ボックス データベースとホスト インスタンスを追跡するだけの 2 つある場合は、そのホスト インスタンスの 1 つ必要があります、メッセージ ボックス データベースの 2 つのデータを移動します。 追跡ホスト インスタンスを追跡する 3 つ目の追加は分散作業を BizTalk Server を実行している別のコンピューターをホストします。 このシナリオで、4 つ目のホスト インスタンスの追跡は、複数の追跡ホストを配布できませんを追加するが提供されます余分なフォールト トレランスのホスト インスタンスを追跡します。  
  
  BAM イベント バス サービスの詳細については、BizTalk Server ヘルプの次のトピックを参照してください。  
  
- 「に、BAM イベント バス サービスを管理」 [ http://go.microsoft.com/fwlink/?LinkId=101590](http://go.microsoft.com/fwlink/?LinkId=101590)します。  
  
- 「BAM イベント バス サービスのインスタンスを作成する」 [ http://go.microsoft.com/fwlink/?LinkId=101591](http://go.microsoft.com/fwlink/?LinkId=101591)します。  
  
## <a name="manage-aspnet-thread-usage-or-concurrently-executing-requests-for-web-applications-that-host-orchestrations-published-as-a-web-or-wcf-service"></a>ASP.NET スレッドの使用状況を管理またはホストのオーケストレーションを Web または WCF サービスとして公開されたことを Web アプリケーションの要求に同時に実行します。  
 Web サービスを変更する必要がありますに公開された worker と I/O スレッド (IIS 6.0 および IIS 7.0 でクラシック モード)、または同時に実行される、オーケストレーションをホストする ASP.NET Web アプリケーションの要求 (IIS 7.0 統合モード) の数の数、次の条件:  
  
-   CPU 使用率は、ホストする Web サーバー上のボトルネックではありません。  
  
-   値、 **ASP.NET アプリ v2.0.50727\Request Wait Time**または**ASP.NET アプリ v2.0.50727\Request 実行時間**パフォーマンス カウンターが著しく大きいです。  
  
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
  
### <a name="manage-aspnet-thread-usage-for-web-applications-that-host-orchestrations-on-iis-60-and-on-iis-70-running-in-classic-mode"></a>クラシック モードで実行されている IIS 7.0 と IIS 6.0 でオーケストレーションをホストする Web アプリケーションの ASP.NET スレッドの使用状況を管理します。  
 ときに、 **autoConfig** IIS 6.0 サーバーまたはクラシック モードで実行している IIS 7.0 サーバーの machine.config ファイル内の値に設定されて**true**、ASP.NET 2.0 は、ワーカー スレッドの数を管理し、I/O スレッドが関連付けられている IIS ワーカー プロセスに割り当てられます。  
  
```  
<processModel autoConfig="true" />  
```  
  
 ワーカー スレッドと ASP.NET 2.0 Web アプリケーションの I/O スレッドの数を手動で変更するには、関連付けられている machine.config ファイルを開くし、の新しい値を入力し、 **maxWorkerThreads**と**maxIoThreads**パラメーター。  
  
```  
<!-- <processModel autoConfig="true" /> -->  
    <processModel maxWorkerThreads="200" maxIoThreads="200" />  
```  
  
> [!NOTE]  
>  これらの値は、ガイダンスのためだけです。これらのパラメーターへの変更をテストすることを確認します。  
  
 ASP.NET 2.0 Web アプリケーションの machine.config ファイル内のパラメーターをチューニングの詳細については、マイクロソフト サポート技術情報の記事を参照してください[821268"の競合、パフォーマンスの低下、および ASP.NET から Web サービス要求を行うときにデッドロック。アプリケーション"](http://go.microsoft.com/fwlink/?LinkID=66483) (http://go.microsoft.com/fwlink/?LinkID=66483)します。  
  
### <a name="manage-the-number-of-concurrently-executing-requests-for-web-applications-that-host-orchestrations-on-iis-70-running-in-integrated-mode"></a>同時に実行される統合モードで実行されている IIS 7.0 でオーケストレーションをホストする Web アプリケーションの要求数を管理します。  
 ASP.NET 2.0 が統合モードで IIS 7.0 でホストされている場合のスレッド処理が異なりますよりも IIS 6.0 または IIS 7.0 でクラシック モード。 ASP.NET 2.0 が同時に実行の数を制限する ASP.NET 2.0 が統合モードで IIS 7.0 でホストされている場合**要求**の数ではなく**スレッド**要求を同時に実行します。 同期のシナリオのこの直接が制限されましていないスレッドの数が非同期のシナリオの要求とスレッドの数は可能性があります非常に異なります。 統合モードで IIS 7.0 で ASP.NET 2.0 を実行すると、 **maxWorkerThreads**と**maxIoThreads**実行中のスレッド数を管理する、machine.config ファイルでパラメーターを使用しません。 指定された値を変更することで同時に実行される要求の数を CPU あたり 12 個の既定値から変更する代わりに、 **maxConcurrentThreadsPerCPU**します。 **MaxConcurrentThreadsPerCPU** reqistry または aspnet.config ファイルの構成セクションでは、値を指定することができます。 既定値を変更する次の手順に従って**maxConcurrentThreadsPerCPU**同時に実行される要求の数を管理します。  
  
 **レジストリで maxConcurrentThreadsPerCPU 値を設定するには**  
  
> [!WARNING]  
>  レジストリ エディターの不適切な使用により問題が発生し、オペレーティング システムの再インストールが必要となることがあります。 レジストリ エディターは、ご自身の責任で使用してください。 バックアップ、復元、およびレジストリを変更する方法の詳細についてで、マイクロソフト サポート技術情報記事「Microsoft Windows レジストリの説明」を参照して[ http://go.microsoft.com/fwlink/?LinkId=62729](http://go.microsoft.com/fwlink/?LinkId=62729)します。  
  
> [!NOTE]  
>  この設定はグローバルであり、個々 のアプリケーション プールまたはアプリケーションは変更できません。  
  
1. をクリックして**開始**、 をクリックして**実行**、型**regedit.exe**、順にクリックします**ok**レジストリ エディターを起動します。  
  
2. 移動します**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0**  
  
3. 次の手順に従って、キーを作成します。  
  
   1.  **編集** メニューのをクリックして**新規**、 をクリックし、**キー**します。  
  
   2.  型**maxConcurrentThreadsPerCPU**、し、キーを押します**ENTER**します。  
  
   3.  で、 **maxConcurrentThreadsPerCPU**キー、maxConcurrentThreadsPerCPU の新しい値で DWORD エントリを作成します。  
  
   4.  レジストリ エディターを閉じます。  
  
   **Aspnet.config ファイルの構成セクションでは、アプリケーション プールの maxConcurrentThreadsPerCPU 値を設定するには**  
  
> [!NOTE]  
>  構成ファイルを使用して次の値の設定を対応するためには、Microsoft .NET Framework 3.5 Service Pack 1 をインストールする必要があります。 Microsoft .NET Framework 3.5 Service Pack 1 をダウンロードする[ http://go.microsoft.com/fwlink/?LinkID=136345](http://go.microsoft.com/fwlink/?LinkID=136345)します。  
  
-   アプリケーション プールの aspnet.config ファイルを開き、新しい値を入力し、 **maxConcurrentRequestsPerCPU**と**requestQueueLimit**パラメーター。  
  
```  
<system.web>  
    <applicationPool maxConcurrentRequestsPerCPU="12" requestQueueLimit="5000"/>  
</system.web>  
```  
  
> [!NOTE]  
>  この値に指定された値よりも優先されます**maxConcurrentThreadsPerCPU**レジストリにします。 RequestQueueLimit 設定では、aspnet.config ファイルの設定は、machine.config ファイルで設定を上書きする点を除いて processModel/requestQueueLimit の場合と同じです。  
  
## <a name="define-clr-hosting-thread-values-for-biztalk-host-instances"></a>CLR ホストの BizTalk ホスト インスタンス用のスレッド値の定義します。  
 Windows スレッドは、Windows プロセスに使用できる最も基本的な実行可能単位なので、BizTalk ホストのインスタンスに関連付けられた .NET スレッド プールには十分なスレッドを割り当てて、スレッドが不足しないようにすることが重要です。 スレッドの不足が発生したときに、パフォーマンスが低下する、要求された作業を実行できる十分なスレッドはありませんがあります。 同時に、ホストに関連付けられた .NET スレッド プールに必要以上にスレッドを割り当てないよう注意する必要があります。 ホストに関連付けられた .NET スレッド プールに割り当てたスレッドが多すぎると、コンテキストの切り替えが増加する場合があります。 コンテキストの切り替えには、パフォーマンス コストが生じますが、別のスレッドを 1 つのスレッドを実行してから、Windows カーネルが切り替わるときに発生します。 過剰なスレッドの割り当ては、全体的なパフォーマンスに悪影響を与えるが、過剰なコンテキストの切り替えことができます。  
  
 BizTalk Server のレジストリで適切な CLR Hosting 値を作成して、BizTalk ホストのインスタンスに関連付けられた .NET スレッド プールで使用できる Windows スレッド数を変更します。  
  
> [!WARNING]  
>  レジストリ エディターの不適切な使用により問題が発生し、オペレーティング システムの再インストールが必要となることがあります。 レジストリ エディターは、ご自身の責任で使用してください。 バックアップ、復元、およびレジストリを変更する方法の詳細についてで、マイクロソフト サポート技術情報記事「Microsoft Windows レジストリの説明」を参照して[ http://go.microsoft.com/fwlink/?LinkId=62729](http://go.microsoft.com/fwlink/?LinkId=62729)します。  
  
> [!NOTE]  
>  **ワーカー スレッド**キューに置かれた作業項目の処理に使用し、 **I/O スレッド**専用のコールバック スレッドが完了した非同期 I/O 要求を処理するために、I/O 完了ポートに関連付けられています。  
  
 **BizTalk ホストの各インスタンスに関連付けられた .NET スレッド プールで使用できるスレッドの数を変更するには、次の手順を実行します。**  
  
1. BizTalk ホスト インスタンスを停止します。  
  
2. をクリックして**開始**、 をクリックして**実行**、型**regedit.exe**、順にクリックします**ok**レジストリ エディターを起動します。  
   移動します**hkey_local_machine \system\currentcontrolset\services\btssvc$**<em>hostname</em>] 場所*ホスト名*ホストに関連付けられているホストの名前を指定しますインスタンス。  
  
   > [!NOTE]  
   >  このレジストリ キーとして表すことが BizTalk Server 2004 から BizTalk Server 2006 インストールをアップグレードした場合 **hkey_local_machine \system\currentcontrolset\services\btssvc * * * guid*] 場所*guid* GUID を BizTalk Server ホストの各インスタンスに固有です。  
  
3. 検索、 **CLR Hosting**キー。 このキーが存在しない場合は、次の手順に従って、キーを作成します。  
  
   1.  **編集** メニューのをクリックして**新規**、 をクリックし、**キー**します。  
  
   2.  型**CLR Hosting**、押します **」と入力**します。  
  
4. 下、 **CLR Hosting**キーの値を持つ、次の DWORD エントリを作成します。  
  
   |DWORD エントリ|既定値|推奨値|  
   |-----------------|-------------------|-----------------------|  
   |MaxIOThreads|20|100|  
   |MaxWorkerThreads|25|100**重要:** 100 よりも、この値を増やす、BizTalk Server メッセージ ボックス データベースをホストする SQL Server コンピューターのパフォーマンスに悪影響を与えることができます。 この問題が発生した場合、SQL Server でデッドロック状態が発生することがあります。 このパラメーターは 100 の値を超えて増加しませんをお勧めします。|  
   |MinIOThreads|1|25|  
   |MinWorkerThreads|1|25|  
  
   > [!NOTE]  
   >  上記の推奨値は、ほとんどのシナリオだけで十分ですが、各ホスト インスタンスで実行中の数のアダプター ハンドラーまたはオーケストレーションによって大きく必要があります。  
  
   > [!NOTE]  
   >  これらの値は、サーバー上のプロセッサの数を掛けた暗黙的にします。 たとえば、MaxWorkerThreads のエントリを 100 の値に設定すると、4 台の CPU を持つサーバーでは 400 の値が実質的に設定されます。  
  
5. レジストリ エディターを閉じます。  
  
6. BizTalk ホスト インスタンスを再起動します。  
  
## <a name="disable-tracking-for-orchestrations-send-ports-receive-ports-and-pipelines-when-tracking-is-not-required"></a>オーケストレーションの追跡を無効化、送信ポート、追跡が必要な場合に、ポート、およびパイプラインの受信  
 追跡では、データがメッセージ ボックス データベースに書き込まれ、BizTalk 追跡データベースに非同期に移動するのには、BizTalk Server 内でオーバーヘッドのパフォーマンスが発生します。 追跡がビジネス要件でない場合は、オーバーヘッドを削減し、パフォーマンスを向上させる追跡を無効になります。 追跡を構成する方法の詳細については、「を構成する追跡を使用して、BizTalk Server 管理コンソール」BizTalk Server でのヘルプを参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=106742](http://go.microsoft.com/fwlink/?LinkID=106742)します。  
  
## <a name="decrease-the-purging-period-for-the-dta-purge-and-archive-job-from-7-days-to-2-days-in-high-throughput-scenarios"></a>DTA Purge and Archive ジョブから 7 日間で高スループットのシナリオ 2 日間に、削除期間を短縮します。  
 既定では、BizTalk Server でのデータを追跡するため、削除間隔は 7 日間に設定します。 高スループットのシナリオでは、メッセージ ボックスとさらに悪い影響メッセージの処理スループットのパフォーマンスに影響が最終的に、追跡データベース内のデータを過剰なビルドではこのことがあります。  
  
 高スループットのシナリオでは、ハードおよびソフトの既定の 7 日から 2 日間に間隔をパージを減らします。 削除間隔を構成する方法の詳細については、"方法を構成、DTA の消去とアーカイブ ジョブ"BizTalk Server でのヘルプを参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=104908](http://go.microsoft.com/fwlink/?LinkID=104908)します。  
  
## <a name="install-the-latest-service-packs"></a>最新のサービス パックをインストールします。  
 パフォーマンスの問題が発生する可能性を修正できる修正プログラムが含まれているこれらの両方の BizTalk Server と .NET Framework の最新のサービス パックをインストールしてください。  
  
## <a name="do-not-cluster-biztalk-hosts-unless-absolutely-necessary"></a>しない限り、BizTalk ホストをクラスターは絶対に必要な  
 中に[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]およびそれ以降のバージョンの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をクラスター リソースとして BizTalk ホストを構成するためにのみ検討間での複数の BizTalk ホストできないリソースへの高可用性を提供する必要がある場合は、これを行うコンピューター。 FTP プロトコルはファイルのロックを指定しないために、たとえば、FTP アダプターを使用してポートは、1 つのホスト インスタンスに存在のみする必要があります、ためただし、これは、1 つはクラスタ リングからメリットが得られる障害点です。 アダプターには、ファイル、SQL、HTTP のみのホストの処理などが含まれているホストは、負荷がコンピューター間で分散され、クラスタ リングの利点は、内部的に指定できます。  
  
## <a name="performance-optimizations-in-the-biztalk-server-documentation"></a>BizTalk Server のドキュメントでパフォーマンスの最適化  
 適切な BizTalk Server のドキュメントの次の推奨事項が適用されます。  
  
-   「メッセージ ボックスの待機時間に関する問題のトラブルシューティング」 [http://go.microsoft.com/fwlink/?LinkId=114747](http://go.microsoft.com/fwlink/?LinkId=114747)  
  
-   「パフォーマンスのボトルネックを識別する」 [http://go.microsoft.com/fwlink/?LinkID=104418](http://go.microsoft.com/fwlink/?LinkID=104418)  
  
-   「DBNETLIB 例外の回避」 [http://go.microsoft.com/fwlink/?LinkID=108787](http://go.microsoft.com/fwlink/?LinkID=108787)  
  
-   「TCP/IP ポートの枯渇を回避する」 [http://go.microsoft.com/fwlink/?LinkID=101610](http://go.microsoft.com/fwlink/?LinkID=101610)  
  
-   「EPM スレッド プールのサイズを設定する」 [http://go.microsoft.com/fwlink/?LinkId=114748](http://go.microsoft.com/fwlink/?LinkId=114748)