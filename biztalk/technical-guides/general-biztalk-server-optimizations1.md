---
title: BizTalk Server の一般的な Optimizations1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8032553-bae3-440d-9197-b926160b0bdf
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2605a7acd9610b0b5417e8c5d7c875f67f22f30c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006715"
---
# <a name="general-biztalk-server-optimizations"></a>BizTalk Server の一般的な最適化
BizTalk Server のパフォーマンスを向上させるのには、次の推奨事項を使用できます。 BizTalk Server をインストールして、構成後、このトピックで示した最適化が適用されます。  
  
## <a name="configure-msdtc"></a>MSDTC を構成します。  
 SQL Server と BizTalk Server 間のトランザクションを促進するには、Microsoft 分散トランザクション コーディネーター (MS DTC) を有効にする必要があります。 BizTalk Server 上で MSDTC を構成するには、トピックを参照して[オペレーティング システムのパフォーマンスを向上させるための一般的なガイドライン](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)します。  
  
## <a name="recommendations-for-configuring-biztalk-server-hosts"></a>BizTalk Server ホストの構成に関する推奨事項  
 このセクションでは、BizTalk Server ホストの構成に関する推奨事項を提供します。  
  
### <a name="create-multiple-biztalk-server-hosts-and-separate-host-instances-by-functionality"></a>機能によって複数の BizTalk Server ホストと別のホスト インスタンスを作成します。  
 複数の BizTalk Server ホストを作成し、それらのホスト間でワークロードを割り当てるにこれらのガイドラインに従います。  
  
-   送信、受信、処理、および追跡機能の個別のホストを作成します。 複数の BizTalk ホストを作成して、柔軟に、BizTalk グループで、ワークロードを構成するときに、BizTalk グループに BizTalk Server を実行しているコンピューター間での処理の分散の主要な手段は。 複数のホストを使用して他のホストに影響を与えずに 1 つのホストを停止することができます。 たとえば、停止できるようにメッセージを送信するキュー メッセージ ボックス データベースに別のホスト インスタンスで実行されている受信メッセージを受信する受信アダプターを許可する一方する可能性があります。 機能別のホスト インスタンスを分離することでは、次の利点も用意されています。  
  
    -   各ホストには、独自の作業キュー テーブル、メッセージ ボックス データベースが割り当てられるために、メッセージ ボックス データベースのホスト キュー テーブル競合を少なく複数の BizTalk ホストを実行します。  
  
    -   調整は、ホスト レベルで BizTalk Server に実装されます。 これにより、各ホストの制限は異なる特性を設定することができます。  
  
    -   ホスト レベルでセキュリティが実装されています。各ホストは、個別の Windows id の下で実行されます。 これによりなどのいずれかのファイル共有にアクセスするその他のホストを許可していないときに、FileShare_B を Host_A のアクセス権を付与することができます。  
  
-   各ホスト インスタンスでは、.NET スレッド プールでメモリ、ハンドル、スレッドなどのリソースの独自セットがあります。 ホスト間でワークロードを割り当てるときは、同じホスト上での規模をまとめてリソースを配置することを検討してください。  
  
-   個別のアダプターとオーケストレーションを別のホスト リソースのさまざまな優先順位を持ちます。 この手法は、専用の BizTalk Server コンピューター上の優先度の高いアプリケーションを実行しているホストの配置に対応します。  
  
> [!NOTE]  
>  追加のホスト インスタンスを作成する利点はありますも潜在的な欠点が多すぎるのホスト インスタンスが作成された場合です。 各ホスト インスタンスは、メッセージ ボックス データベースに対して追加の負荷を生成およびコンピューターのリソース (CPU、メモリ、スレッド) などを利用する Windows サービス (BTSNTSvc.exe) です。  
  
 BizTalk Server の変更の詳細については、ホストのプロパティを参照してください[ホスト プロパティを変更する方法](http://go.microsoft.com/fwlink/?LinkID=154359)(http://go.microsoft.com/fwlink/?LinkID=154359) BizTalk Server 2010 のヘルプ。  
  
### <a name="configure-a-dedicated-tracking-host"></a>専用の追跡ホストを構成します。  
 メインのオーケストレーションとメッセージング エンジンは実際には移動メッセージ、BizTalk 追跡または BAM データベースに直接実行しているビジネス プロセスの主な仕事からこれらのエンジンをそらすこれは、ために、スループットを BizTalk Server が最適化されています。 代わりに、BizTalk Server は、メッセージ、メッセージ ボックス データベースに残りますされ、BizTalk 追跡データベースへの移行を必要とするとしてマークを付けます。 バック グラウンド プロセス (追跡ホスト) し、BizTalk の追跡と BAM データベースにメッセージを移動します。 追跡がリソースを消費する操作であるため、個別のホストを作成してください専用の追跡、追跡メッセージの処理を専用のホスト上に影響を最小限に抑えます。 パフォーマンスを最適化する必要がありますがある少なくとも 1 つの追跡メッセージ ボックス データベースごとにホストのインスタンス。 追跡ホスト インスタンスの実際の数が n+1 にする必要があります、N = メッセージ ボックス データベースの数。 「+ 1」の追跡をホストするコンピューターのいずれかが失敗した場合、冗長性のためです。  
  
 専用の追跡ホストを使用してでは BizTalk Server 追跡を妨げることがなく他の BizTalk ホストを停止することもできます。 追跡メッセージ ボックス データベースからデータの移動は、正常な BizTalk Server システムにとって重要です。 BizTalk グループ内の追跡データの移動を行う BizTalk ホストが停止している場合、データのデコードに追跡サービスは実行されません。 この効果は次のとおりです。  
  
- HAT 追跡データは、BizTalk 追跡データベースにメッセージ ボックス データベースから移動されません。  
  
- BAM の追跡データは、BAM プライマリ インポート データベースにメッセージ ボックス データベースから移動されません。  
  
- データが移動されていないために、メッセージ ボックス データベースから削除できません。  
  
- データのデコードに追跡サービスを停止すると、追跡インターセプタはまだ起動追跡データを書き込むメッセージ ボックス データベースにします。 データが移動されていない場合、メッセージ ボックス データベース、いっぱいになる時間の経過と共にパフォーマンスに影響できるようになります。 場合でも、カスタム プロパティは追跡されませんまたは BAM プロファイルが設定されていない、既定ではいくつかのデータが追跡 (など、パイプラインは、受信/送信イベントおよびオーケストレーションのイベント)。 データのデコードに追跡サービスを実行しない場合は、すべての追跡インターセプターをデータベースにデータ保存しないようにオフにします。 グローバル追跡を無効にするを参照してください。[グローバル追跡をオフにする方法](http://go.microsoft.com/fwlink/?LinkID=154193)(http://go.microsoft.com/fwlink/?LinkID=154193) BizTalk Server 2010 のヘルプ。 BizTalk Server 管理コンソールを使用して、選択的に追跡イベントを無効にします。  
  
  追跡ホストは、BizTalk サーバー (1 つが失敗した場合の冗長性) を実行するには少なくとも 2 台のコンピューターで実行する必要があります。 最適なパフォーマンスを少なくとも 1 つの追跡がある必要がありますメッセージ ボックス データベースごとにホストのインスタンス。 追跡ホスト インスタンスの実際の数があります (N + 1)、N = メッセージ ボックス データベースの数。 「+ 1」の追跡をホストするコンピューターのいずれかが失敗した場合、冗長性のためです。  
  
  追跡ホスト インスタンスが特定のメッセージ ボックス データベースの追跡データを移動しますが、されません 1 つ以上の追跡ホスト インスタンスの特定のメッセージ ボックス データベースのデータを移動します。 たとえば、3 つのメッセージ ボックス データベースとホスト インスタンスを追跡するだけの 2 つある場合は、そのホスト インスタンスの 1 つ必要があります、メッセージ ボックス データベースの 2 つのデータを移動します。 追跡ホスト インスタンスを追跡する 3 つ目の追加は分散作業を BizTalk Server を実行している別のコンピューターをホストします。 このシナリオで、4 つ目のホスト インスタンスの追跡は、複数の追跡ホストを配布できませんを追加するが提供されます余分なフォールト トレランスのホスト インスタンスを追跡します。  
  
  BAM イベント バス サービスの詳細については、BizTalk Server 2010 ヘルプの次のトピックを参照してください。  
  
- [BAM イベント バス サービスの管理](http://go.microsoft.com/fwlink/?LinkID=154194)(http://go.microsoft.com/fwlink/?LinkID=154194)します。  
  
- [BAM イベント バス サービスのインスタンスを作成する](http://go.microsoft.com/fwlink/?LinkID=154195)(http://go.microsoft.com/fwlink/?LinkID=154195)します。  
  
### <a name="do-not-cluster-biztalk-hosts-unless-absolutely-necessary"></a>しない限り、BizTalk ホストをクラスターは絶対に必要な  
 BizTalk Server 2010、BizTalk ホストをクラスター リソースとして構成することができます、中に複数の BizTalk コンピューターでホストできないリソースへの高可用性を提供する必要がある場合は、これを行うを検討する必要がありますのみ。 例としては、FTP プロトコルはファイルのロックを指定しないため、FTP アダプターを使用してポートを 1 つのホストのインスタンスに格納する必要がありますのみ。 ただし、クラスタ リング メリットが得、障害の 1 つのポイントをについて説明します。 アダプターには、ファイル、SQL、HTTP のみのホストの処理などが含まれているホストは、負荷が複数のコンピューターで分散され、クラスタ リングの利点は、内部的に指定できます。  
  
## <a name="increase-the-number-of--http-concurrent-connections-allowed-by-changing-the-value-for-the-maxconnection-parameter"></a>Maxconnection パラメーターの値を変更することで許可される HTTP 同時接続の数を増やす  
 既定では、(WCF ベースの HTTP アダプターを含む)、HTTP アダプターは、特定の移行先サーバーに BizTalk Server を実行している各コンピューターから 2 つの同時 HTTP 接続を開きます。  
  
 この設定は、HTTP 1.1 仕様は IETF RFC に準拠しているし、高スループットの最適化がいないユーザーのシナリオに最適ですが、します。 設定は、BizTalk Server を実行している各コンピューターから各サーバーに送信 HTTP 呼び出しを 2 つの同時送信効果的に調整します。  
  
 同時接続数を増やすには、BTSNTSvc.exe.config (または BTSNTSvc64.exe.config 64 ビットのホスト用)、各 BizTalk サーバーで、BizTalk Server 構成ファイルで maxconnection パラメーターの値を変更できます。 呼び出されている特定のサーバーを大きくことができます。 経験上、として maxconnection パラメーターの値を 12 に設定する必要があります * Cpu または web アプリケーションをホストしているコンピューター上のコアの数。  
  
> [!NOTE]  
>  大きな値が呼び出される Web サーバーが HTTP 接続で負荷が大きいことを maxconnection パラメーターの値を増やさないでください。 Maxconnection パラメーターの値を変更した後に、ストレス テストを確認せず Web ターゲットを過負荷に良好なパフォーマンスと HTTP を提供する maxconnection の値を送信する各送信先の Web サーバーに要求を送信して、実行します。サーバー。  
  
 "最大接続数" プロパティの構成例を次に示します。  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address="http://www.contoso.com" maxconnection="24" />  
      <add address="*" maxconnection="48" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
 Maxconnection プロパティを設定するときに HTTP、HTTPS、web サイトの IP アドレスおよびポート番号を指定することができます。 その他の例は次のとおりです。  
  
 **\<アドレスを追加 ="<https://www.contoso.com>"maxconnection =「24」/\>**   
**\<アドレスを追加 ="<http://www.contoso.com:8080>"maxconnection =「24」/\>**   
**\<アドレスを追加 ="http://*IPAddress*"maxconnection =「24」/\>**  Web サービスの IIS と ASP.NET の設定のチューニングに関する詳細については、HTTP アダプターに影響する"ASP.NET 設定を参照してください。パフォーマンス"セクション[構成パラメーターを アダプターのパフォーマンスの影響を与える](http://go.microsoft.com/fwlink/?LinkID=154200)(<http://go.microsoft.com/fwlink/?LinkID=154200>) BizTalk Server 2010 のヘルプ。  
  
## <a name="manage-aspnet-thread-usage-or-concurrently-executing-requests-for-web-applications-that-can-host--isolated-received-locations-back-end-web-services-and-wcf-services"></a>ASP.NET スレッドの使用状況を管理または受信場所、バックエンド Web サービスと WCF サービスを分離することができますをホストする Web アプリケーションに対する要求を同時に実行  
 作業者と I/O スレッド (IIS 7.5、およびクラシック モードでの IIS 7.0) または同時に実行される要求 (IIS 7.5 および 7.0 統合モード)、ASP.NET Web アプリケーションのホストには、受信場所、バックエンド Web サービスと WCF サービスが分離された数の数次の条件を変更する必要があります。  
  
-   CPU 使用率は、ホストする Web サーバー上のボトルネックではありません。  
  
-   値です。  
  
    -   **ASP.NET Apps v4.0.30319 \Request Wait Time** or **ASP.NET Apps v4.0.30319 \Request Execution Time** performance counters is unusually high.  
  
    -   **ASP.NET アプリ v2.0.50727\Request Wait Time**または**ASP.NET アプリ v2.0.50727\Request 実行時間**パフォーマンス カウンターが著しく大きいです。  
  
-   Web アプリケーションをホストするコンピューターのアプリケーション ログには、次のようなエラーが生成されます。  
  
    ```  
    Event Type: Warning  
    Event Source: W3SVC Event Category: None  
    Event ID: 1013  
    Date: 11/4/2010  
    Time: 1:03:47 PM  
    User: N/A  
    Computer: <ComputerName>  
    Description: A process serving application pool 'DefaultAppPool' exceeded time limits during shut down. The process id was '<xxxx>'  
    ```  
  
### <a name="manage-aspnet-thread-usage-for-web-applications-that-can-host-isolated-received-locations-back-end-web-services-and-wcf-services-on-iis-75-and-iis-70-running-in-classic-mode"></a>分離受信場所、バックエンド Web サービス、および IIS 7.5、およびクラシック モードで実行されている IIS 7.0 での WCF サービスをホストする Web アプリケーションの ASP.NET スレッドの使用状況を管理します。  
 ときに、 **autoConfig**クラシック モードで実行されている IIS 7.5、および IIS 7.0 サーバーの machine.config ファイル内の値に設定されて**true**、ASP.NET 2.0 および ASP.NET 4 ワーカー スレッドと I/O スレッドの数を管理します。関連付けられている IIS ワーカー プロセスを割り当てられます。  
  
```  
<processModel autoConfig="true" />  
```  
  
 ワーカー スレッドと ASP.NET 2.0 および ASP.Net 4 Web アプリケーションの I/O スレッドの数を手動で変更するには、関連付けられている machine.config ファイルを開くし、の新しい値を入力し、 **maxWorkerThreads**と**maxIoThreads**パラメーター。  
  
```  
<!-- <processModel autoConfig="true" /> -->  
    <processModel maxWorkerThreads="200" maxIoThreads="200" />  
```  
  
> [!NOTE]  
>  これらの値は、ガイダンスのためだけです。これらのパラメーターへの変更をテストすることを確認します。  
  
 ASP.NET 2.0 Web アプリケーションの machine.config ファイル内のパラメーターをチューニングの詳細については、マイクロソフト サポート技術情報記事 821268 を参照してください。[競合、パフォーマンスの低下、および ASP から Web サービス要求を行うときのデッドロック。NET アプリケーション](http://go.microsoft.com/fwlink/?LinkID=144169)(http://go.microsoft.com/fwlink/?LinkID=144169)します。  
  
### <a name="manage-the-number-of-concurrently-executing-requests-for-aspnet-20-web-applications-that-can-host-isolated-received-locations-back-end-web-services-and-wcf-services-on-iis-75-and-iis-70-running-in-integrated-mode"></a>同時に実行される分離受信場所、バックエンド Web サービス、および IIS 7.5 統合モードで実行されている IIS 7.0 での WCF サービスをホストする ASP.NET 2.0 Web アプリケーションの要求数を管理します。  
 ASP.NET 2.0 が統合モードで IIS 7.5、および IIS 7.0 でホストされている場合のスレッド処理が異なりますよりも IIS 7.5、および IIS 7.0 でクラシック モードで。 ASP.NET 2.0 が同時に実行の数を制限する ASP.NET 2.0 が統合モードで IIS 7.5、および IIS 7.0 でホストされている場合**要求**の数ではなく**スレッド**同時に実行されます。要求します。 同期のシナリオのこの直接が制限されましていないスレッドの数が非同期のシナリオの要求とスレッドの数は可能性があります非常に異なります。 統合モードで IIS 7.5、および IIS 7.0 で ASP.NET 2.0 を実行すると、 **maxWorkerThreads**と**maxIoThreads**実行中のスレッド数を管理する、machine.config ファイルでパラメーターを使用しません。 指定された値を変更することで同時に実行される要求の数を CPU あたり 12 個の既定値から変更する代わりに、 **maxConcurrentRequestsPerCPU**します。 **MaxConcurrentRequestsPerCPU** reqistry または aspnet.config ファイルの構成セクションでは、値を指定することができます。 既定値を変更する次の手順に従って**maxConcurrentRequestsPerCPU**同時に実行される要求の数を管理します。  
  
 **レジストリの maxConcurrentRequestsPerCPU 値を設定するには**  
  
> [!WARNING]  
>  レジストリ エディターの不適切な使用により問題が発生し、オペレーティング システムの再インストールが必要となることがあります。 レジストリ エディターは、ご自身の責任で使用してください。 バックアップ、復元、およびレジストリを変更する方法の詳細については、Microsoft サポート技術情報 256986 を参照してください。[上級ユーザー向けの Windows レジストリ情報](http://go.microsoft.com/fwlink/?LinkId=62729)(http://go.microsoft.com/fwlink/?LinkId=62729)します。  
  
> [!NOTE]  
>  この設定はグローバルであり、個々 のアプリケーション プールまたはアプリケーションは変更できません。  
  
1. をクリックして**開始**、 をクリックして**実行**、型**regedit.exe**、順にクリックします**ok**レジストリ エディターを起動します。  
  
2. 移動します**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0**  
  
3. 次の手順に従って、キーを作成します。  
  
   1.  **編集** メニューのをクリックして**新規**、 をクリックし、**キー**します。  
  
   2.  型**maxConcurrentRequestsPerCPU**、し、キーを押します**ENTER**します。  
  
   3.  で、 **maxConcurrentRequestsPerCPU**キー、maxConcurrentRequestsPerCPU の新しい値で DWORD エントリを作成します。  
  
   4.  レジストリ エディターを閉じます。  
  
   **Aspnet.config ファイルの構成セクションでは、アプリケーション プールの maxConcurrentRequestsPerCPU 値を設定するには**  
  
> [!NOTE]  
>  構成ファイルを使用して次の値の設定を対応するためには、Microsoft .NET Framework 3.5 Service Pack 1 をインストールする必要があります。 Microsoft .NET Framework 3.5 Service Pack 1 をダウンロードする[Microsoft .NET Framework 3.5 Service Pack 1](http://go.microsoft.com/fwlink/?LinkID=136345) (http://go.microsoft.com/fwlink/?LinkID=136345)します。  
  
 アプリケーション プールの aspnet.config ファイルを開き、新しい値を入力し、 **maxConcurrentRequestsPerCPU**と**requestQueueLimit**パラメーター。  
  
```  
<system.web>  
    <applicationPool maxConcurrentRequestsPerCPU="12" requestQueueLimit="5000"/>  
</system.web>  
```  
  
> [!NOTE]  
>  この値に指定された値よりも優先されます**maxConcurrentRequestsPerCPU**レジストリにします。 RequestQueueLimit 設定では、aspnet.config ファイルの設定は、machine.config ファイルで設定を上書きする点を除いて processModel/requestQueueLimit の場合と同じです。  
  
 IIS 7.0 で ASP.NET のスレッドの使用量を構成する方法の詳細については、次を参照してください。 [Thomas Marquardt のブログを IIS 7.0 で ASP.NET スレッドの使用に関する](http://go.microsoft.com/fwlink/?LinkId=157518)(http://go.microsoft.com/fwlink/?LinkId=157518)します。  
  
### <a name="manage-the-number-of-concurrently-executing-requests-for-aspnet-4web-applications-that-can-host-isolated-received-locations-back-end-web-services-and-wcf-services-on-iis-75-and-70-running-in-integrated-mode"></a>同時に実行される分離受信場所、バックエンド Web サービス、および IIS 7.5 および 7.0 統合モードで実行されている WCF サービスをホストできる ASP.NET 4Web アプリケーションに対する要求の数を管理します。  
 .NET Framework 4 で maxConcurrentRequestsPerCPU の既定の設定は 5000、これは非常に大きな数、したがってにより、多数の非同期の要求を同時に実行 詳細については、次を参照してください。 [ \<applicationPool\>要素 (Web 設定)](http://go.microsoft.com/fwlink/?LinkID=205339) (http://go.microsoft.com/fwlink/?LinkID=205339)します。  
  
 IIS 7.5、および IIS 7.0 の Integrated モードの場合は、HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\4.0.30319.0 内 MaxConcurrentRequestsPerCPU をという名前の DWORD は、CPU あたりの同時要求の数を決定します。 既定では、レジストリ キーが存在しないと、CPU あたりの要求の数が 5000 に制限されています。  
  
 **レジストリの maxConcurrentRequestsPerCPU 値を設定するには**  
  
> [!WARNING]  
>  レジストリ エディターの不適切な使用により問題が発生し、オペレーティング システムの再インストールが必要となることがあります。 レジストリ エディターは、ご自身の責任で使用してください。 バックアップ、復元、およびレジストリを変更する方法の詳細については、Microsoft サポート技術情報 256986 を参照してください。[上級ユーザー向けの Windows レジストリ情報](http://go.microsoft.com/fwlink/?LinkId=62729)(http://go.microsoft.com/fwlink/?LinkId=62729)します。  
  
> [!NOTE]  
>  この設定はグローバルであり、個々 のアプリケーション プールまたはアプリケーションは変更できません。  
  
1. をクリックして**開始**、 をクリックして**実行**、型**regedit.exe**、順にクリックします**ok**レジストリ エディターを起動します。  
  
2. 移動します**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\4.0.30319.0**します。  
  
3. 次の手順に従って、キーを作成します。  
  
   1.  **編集** メニューのをクリックして**新規**、 をクリックし、**キー**します。  
  
   2.  型**maxConcurrentRequestsPerCPU**、し、キーを押します**ENTER**します。  
  
   3.  で、 **maxConcurrentRequestsPerCPU**キー、maxConcurrentRequestsPerCPU の新しい値で DWORD エントリを作成します。  
  
   4.  レジストリ エディターを閉じます。  
  
   **Aspnet.config ファイルの構成セクションでは、アプリケーション プールの maxConcurrentRequestsPerCPU 値を設定するには**  
  
> [!NOTE]  
>  構成ファイルを使用して次の値の設定を対応するためには、Microsoft .NET Framework 4 をインストールする必要があります。 Microsoft .NET Framework 4 をダウンロードする[Microsoft .NET Framework 4 (Web インストーラー)](http://go.microsoft.com/fwlink/?LinkID=189318) (http://go.microsoft.com/fwlink/?LinkID=189318)します。  
  
-   アプリケーション プールの aspnet.config ファイルを開き、新しい値を入力し、 **maxConcurrentRequestsPerCPU**と**requestQueueLimit**パラメーター。  
  
     次の例の値は、既定値です。  
  
    ```  
    <system.web>  
        <applicationPool maxConcurrentRequestsPerCPU="5000" requestQueueLimit="5000"/>  
    </system.web>  
    ```  
  
> [!NOTE]  
>  この値に指定された値よりも優先されます**maxConcurrentRequestsPerCPU**レジストリにします。 **RequestQueueLimit** aspnet.config ファイルの設定は、machine.config ファイルで設定を上書きする点を除いて同じ processModel/requestQueueLimit 設定です。  
  
## <a name="define-clr-hosting-thread-values-for-biztalk-host-instances"></a>CLR ホストの BizTalk ホスト インスタンス用のスレッド値の定義します。  
 Windows スレッドは、Windows プロセスに使用できる最も基本的な実行可能単位なので、BizTalk ホストのインスタンスに関連付けられた .NET スレッド プールには十分なスレッドを割り当てて、スレッドが不足しないようにすることが重要です。 スレッドの不足が発生したときに、パフォーマンスが低下する、要求された作業を実行できる十分なスレッドはありませんがあります。 同時に、ホストに関連付けられた .NET スレッド プールに必要以上にスレッドを割り当てないよう注意する必要があります。 ホストに関連付けられた .NET スレッド プールに割り当てたスレッドが多すぎると、コンテキストの切り替えが増加する場合があります。 コンテキストの切り替えには、パフォーマンス コストが生じますが、別のスレッドを 1 つのスレッドを実行してから、Windows カーネルが切り替わるときに発生します。 過剰なスレッドの割り当ては、全体的なパフォーマンスに悪影響を与えるが、過剰なコンテキストの切り替えことができます。 BizTalk ホスト インスタンスの .NET スレッド プールに割り当てられるスレッドの既定の数は、インストールされているバージョンの .NET Framework に依存します。 .NET Framework 4 および .NET Framework 3.5 SP1 は、の既定値は、BizTalk Server コンピューターと、メッセージ ボックス データベースの過剰なロックの競合に対して過剰なスレッドの割り当てを引き起こす可能性が大幅に増加します。  
  
 使用して、 **BizTalk 設定ダッシュ ボード**.NET で使用できる Windows スレッド数のスレッド プールの BizTalk ホストのインスタンスに関連付けられているは、既定値を変更できます。 .NET CLR 設定を変更する方法の詳細については、次を参照してください。 [.NET CLR 設定を変更する方法](http://go.microsoft.com/fwlink/?LinkID=205344)(http://go.microsoft.com/fwlink/?LinkID=205344)します。 .NET CLR 設定は、コア CPU ごとに適用されます。  
  
> [!NOTE]  
>  **ワーカー スレッド**キューに置かれた作業項目の処理に使用し、 **I/O スレッド**専用のコールバック スレッドが完了した非同期 I/O 要求を処理するために、I/O 完了ポートに関連付けられています。  
  
|スレッドの設定|既定値|推奨値|  
|------------------------|-------------------|-----------------------|  
|最大 IO スレッドの数|250|250|  
|ワーカー スレッド最大数|25|100**重要:** 100 よりも、この値を増やす、BizTalk Server メッセージ ボックス データベースをホストする SQL Server コンピューターのパフォーマンスに悪影響を与えることができます。 この問題が発生した場合、SQL Server でデッドロック状態が発生することがあります。 このパラメーターは 100 の値を上回る値を増加しないことをお勧めします。|  
|最小 IO スレッドの数|25|25|  
|最小ワーカー スレッド|5|25|  
  
> [!NOTE]  
>  推奨値は絶対的でないし、BizTalk アプリケーションに応じて調整する必要があります。 一度に 1 つのパラメーターを変更し、追加の変更を加える前に、BizTalk プラットフォームの安定性とパフォーマンスに影響を測定します。  
  
> [!NOTE]  
>  これらの値は、サーバー上のプロセッサの数を掛けた暗黙的にします。 たとえば、設定、 **MaxWorkerThreads**エントリ 100 の値を 4 CPU サーバーで 400 の値を設定が効果的にします。  
  
## <a name="disable-biztalk-server-group-level-tracking"></a>BizTalk Server グループ レベルの追跡を無効にします。  
 追跡では、データがメッセージ ボックス データベースに書き込まれ、BizTalk 追跡データベースに非同期に移動するのには、BizTalk Server 内でオーバーヘッドのパフォーマンスが発生します。 運用環境の BizTalk Server 環境で追跡を構成するときに、次の考慮事項が適用されます。  
  
- として一般に、追跡は、ビジネス要件ではありません、し、無効にするオーバーヘッドを削減し、パフォーマンスを向上させるグループ レベルの追跡。  
  
   BizTalk Server グループ レベルの追跡を無効にするには、次の手順を実行します。  
  
  1.  **BizTalk Server 管理コンソール**、展開**BizTalk Server 管理**を右クリックして**BizTalk グループ**、 をクリックし、**設定**.  
  
  2.  BizTalk 設定ダッシュ ボード] ダイアログ ボックスの [グループ] ページで、[、**グループ レベルの追跡を有効にする**チェック ボックスをオンします。  
  
  3.  をクリックして**OK**変更を適用し、設定ダッシュ ボードを終了します。  
  
- メッセージ本文の追跡のために必要な場合のみを使用します。 メッセージのスループットとメッセージのサイズに応じてメッセージ本文の追跡に大きなオーバーヘッドが可能性があります。 BizTalk 動作状況の追跡には、デバッグ、および監査の明らかな利点がありますが、大幅なパフォーマンスとスケーラビリティの影響もあります。 そのため、デバッグとセキュリティ上の理由から、厳密に必要なは、冗長な情報の追跡を回避するデータのみを追跡する必要があります。  
  
- 既定では、次の追跡オプションはオーケストレーションを有効になっています。  
  
  - オーケストレーションの開始と終了  
  
  - メッセージの送信および受信  
  
  - 図形の開始と終了  
  
    追跡オプション「図形の開始と終了」オーケストレーションは、大きなオーバーヘッドが発生し、高スループットが必要な場合、運用環境で有効にする必要がありますされません。 オーケストレーション追跡オプションは、BizTalk 管理コンソールでアクセス可能な**追跡**オーケストレーションのプロパティ ダイアログ ボックスのページ。  
  
  追跡を構成する方法の詳細については、次を参照してください。 [、BizTalk Server 管理コンソールを使用した追跡構成](http://go.microsoft.com/fwlink/?LinkId=158021)(http://go.microsoft.com/fwlink/?LinkId=158021)します。  
  
## <a name="decrease-the-purging-period-for-the-dta-purge-and-archive-job-from-7-days-to-2-days-in-high-throughput-scenarios"></a>DTA Purge and Archive ジョブから 7 日間で高スループットのシナリオ 2 日間に、削除期間を短縮します。  
 既定では、BizTalk Server でのデータを追跡するため、削除間隔は 7 日間に設定します。 高スループットのシナリオでは、メッセージ ボックスとさらに悪い影響メッセージの処理スループットのパフォーマンスに影響が最終的に、追跡データベース内のデータを過剰なビルドではこのことがあります。  
  
 高スループットのシナリオでは、ハードおよびソフトの既定の 7 日から 2 日間に間隔をパージを減らします。 削除間隔を構成する方法の詳細については、次を参照してください。 [DTA Purge and Archive ジョブを構成する方法](http://go.microsoft.com/fwlink/?LinkID=153814)(http://go.microsoft.com/fwlink/?LinkID=153814) 、BizTalk Server 2010 のヘルプ。  
  
## <a name="configure-the-temp-path-for-the-biztalk-service-account-to-point-to-a-separate-disk-or-lun"></a>別のディスクまたは LUN をポイントする BizTalk サービス アカウントに対する % % の一時パスを構成します。  
 これは、BizTalk は、複雑なマッピング操作を実行するときにディスクにストリームのファイルに、一時的な場所を使用するために実行する必要があります。  
  
## <a name="install-the-latest-service-packs"></a>最新のサービス パックをインストールします。  
 パフォーマンスの問題が発生する可能性を修正できる修正プログラムが含まれているこれらの両方の BizTalk Server と .NET Framework の最新のサービス パックをインストールしてください。  
  
## <a name="performance-optimizations-in-the-biztalk-server-documentation"></a>BizTalk Server のドキュメントでパフォーマンスの最適化  
 適切な BizTalk Server のドキュメントの次の推奨事項が適用されます。  
  
-   [メッセージ ボックスの待機時間に関する問題のトラブルシューティング](http://go.microsoft.com/fwlink/?LinkId=158019)(http://go.microsoft.com/fwlink/?LinkId=158019)  
  
-   [パフォーマンスのボトルネックを特定する](http://go.microsoft.com/fwlink/?LinkID=154238)(http://go.microsoft.com/fwlink/?LinkID=154238)  
  
-   [DBNETLIB 例外の回避](http://go.microsoft.com/fwlink/?LinkID=155308)(http://go.microsoft.com/fwlink/?LinkID=155308)  
  
-   [TCP/IP ポートの枯渇を回避する](http://go.microsoft.com/fwlink/?LinkID=153240)(http://go.microsoft.com/fwlink/?LinkID=153240)  
  
-   [EPM スレッド プールのサイズを設定](http://go.microsoft.com/fwlink/?LinkId=158020)(http://go.microsoft.com/fwlink/?LinkId=158020)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server パフォーマンスの最適化](../technical-guides/optimizing-biztalk-server-performance.md)