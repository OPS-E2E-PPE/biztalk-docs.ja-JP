---
title: "BizTalk Server の一般的な Optimizations1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8032553-bae3-440d-9197-b926160b0bdf
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e9e799822c63cb78eda1b989cb157c71fd357d8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="general-biztalk-server-optimizations"></a>BizTalk Server の一般的な最適化
BizTalk Server のパフォーマンスを向上させるのには、次の推奨事項を使用できます。 BizTalk Server をインストールして、構成後、このトピックで示した最適化が適用されます。  
  
## <a name="configure-msdtc"></a>MSDTC を構成します。  
 SQL Server と BizTalk Server の間でトランザクションを容易にするため、Microsoft 分散トランザクション コーディネーター (MS DTC) を有効にする必要があります。 BizTalk Server で MSDTC を構成するには、トピックを参照して[オペレーティング システムのパフォーマンスを向上させるための一般的なガイドライン](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)です。  
  
## <a name="recommendations-for-configuring-biztalk-server-hosts"></a>BizTalk Server ホストの構成に関する推奨事項  
 このセクションでは、BizTalk Server ホストの構成に関する推奨事項を説明します。  
  
### <a name="create-multiple-biztalk-server-hosts-and-separate-host-instances-by-functionality"></a>機能によって、複数の BizTalk Server ホストと別のホスト インスタンスを作成します。  
 複数の BizTalk Server ホストを作成し、それらのホスト間でワークロードを割り当てるにこれらのガイドラインに従います。  
  
-   送信、受信、処理、および追跡機能を別々 のホストを作成します。 複数の BizTalk ホストを作成する、BizTalk グループで、ワークロードを構成する際の柔軟性を複数の BizTalk グループに BizTalk Server を実行しているコンピューターで処理を分散する主な手段。 複数のホストを使用するには、他のホストに影響を与えずに 1 つのホストを停止することができます。 たとえば、停止できるようにメッセージを送信するキュー メッセージ ボックス データベースに受信メッセージを受信する受信アダプターを別のホスト インスタンスで実行されている状態のままする可能性があります。 機能別のホスト インスタンスを分離すると、次の利点も提供されます。  
  
    -   複数の BizTalk ホストを実行すると、各ホストには、メッセージ ボックス データベースに独自の作業キュー テーブルが割り当てられるために、メッセージ ボックス データベースのホスト キュー テーブルでの競合が軽減します。  
  
    -   制限については、ホスト レベルで BizTalk Server で実装されます。 これにより、ホストごとに異なる調整特性を設定することができます。  
  
    -   ホスト レベルでセキュリティが実装されています。各ホストは、個別の Windows id で実行されます。 たとえば、Host_A にアクセス FileShare_B、いずれかのファイル共有にアクセスするその他のホストを許可しない中にできます。  
  
-   各ホスト インスタンスでは、.NET スレッド プールでメモリ、ハンドル、およびスレッドなどのリソースの独自セットがあります。 ホスト間でワークロードを割り当てるときは、同じホスト上で同時にスケール アウトするリソースを配置することを検討してください。  
  
-   個別のアダプターとオーケストレーションを別のホスト リソースの別の優先順位を持ちます。 この手法は、専用の BizTalk Server コンピューター上の優先度の高いアプリケーションを実行しているホストの配置に対応します。  
  
> [!NOTE]  
>  追加のホスト インスタンスを作成する利点があるときに欠点がありますも潜在的な多数のホスト インスタンスが作成される場合。 各ホスト インスタンスは、メッセージ ボックス データベースに対して追加の負荷を生成し、コンピューターのリソース (CPU、メモリ、スレッド) などを使用する Windows サービス (BTSNTSvc.exe) です。  
  
 BizTalk Server を変更する方法についてのホストのプロパティを参照してください[ホストのプロパティを変更する方法](http://go.microsoft.com/fwlink/?LinkID=154359)(http://go.microsoft.com/fwlink/?LinkID=154359)、BizTalk Server 2010 ヘルプ。  
  
### <a name="configure-a-dedicated-tracking-host"></a>専用の追跡ホストを構成します。  
 BizTalk Server は、メインのオーケストレーションとメッセージング エンジンは実際に移動しないメッセージ、BizTalk 追跡または BAM データベースに直接ビジネス プロセスを実行するがプライマリ ジョブからこれらのエンジンをそらすこれは、スループット、に対して最適化されます。 代わりに、BizTalk Server は、メッセージ ボックス データベース、メッセージのままにし、BizTalk 追跡データベースへの移行を必須としてマークを付けます。 バック グラウンド プロセス (追跡ホスト) し、BizTalk 追跡データベースおよび BAM データベースにメッセージを移動します。 追跡はリソースを消費する操作のため、独立したホスト作成してください専用の追跡、追跡がメッセージの処理に専用ホストを持つことの影響を最小限に抑えること。 パフォーマンスを最適化する必要がありますがある少なくとも 1 つの追跡メッセージ ボックス データベースごとにホストのインスタンス。 追跡ホスト インスタンスの実際の数が n+1、する必要があります、N、メッセージ ボックス データベースの数を = です。 「+ 1」の追跡をホストしているコンピューターのいずれかに失敗した場合は、冗長性のため、します。  
  
 BizTalk Server 追跡を妨げることがなく他の BizTalk ホストを停止する専用の追跡ホストを使用できます。 追跡メッセージ ボックス データベースからデータの移動は、正常な BizTalk Server システムにとって重要です。 BizTalk グループ内の追跡データの移動を担当する BizTalk ホストを停止すると、データのデコードに追跡サービスは実行されません。 この効果は次のとおりです。  
  
-   HAT 追跡データは、BizTalk 追跡データベースにメッセージ ボックス データベースから移動されません。  
  
-   BAM の追跡データは、BAM プライマリ インポート データベースにメッセージ ボックス データベースから移動されません。  
  
-   データが移動されていないために、メッセージ ボックス データベースから削除できません。  
  
-   データのデコードに追跡サービスが停止したときに追跡インターセプターは引き続きファイア アンド メッセージ ボックス データベースに追跡データを書き込みます。 データが移動されていない場合は、一定期間のパフォーマンスに影響を与えるメッセージ ボックス データベースになります肥大化、これにより、します。 場合でも、カスタム プロパティは追跡されませんまたは BAM プロファイルが設定されていない、既定では一部のデータは、追跡 (など、パイプラインは、受信/送信イベントおよびオーケストレーションのイベント)。 データのデコードに追跡サービスを実行しないようにする場合は、すべての追跡インターセプターをデータベースにデータ保存しないようにオフにします。 グローバル追跡を無効にするを参照してください。[グローバル追跡を無効にする方法](http://go.microsoft.com/fwlink/?LinkID=154193)(http://go.microsoft.com/fwlink/?LinkID=154193) BizTalk Server 2010 ヘルプの「します。 選択的に追跡イベントを無効にするのにには、BizTalk Server 管理コンソールを使用します。  
  
 追跡ホストは、BizTalk サーバー (1 つが失敗した場合の冗長構成) を実行するには、少なくとも 2 台のコンピューターで実行する必要があります。 最適なパフォーマンスが必要には、少なくとも 1 つの追跡メッセージ ボックス データベースごとにホストのインスタンス。 追跡ホスト インスタンスの実際の数になります (N は + 1)、ここで N = メッセージ ボックス データベースの数。 「+ 1」の追跡をホストしているコンピューターのいずれかに失敗した場合は、冗長性のため、します。  
  
 追跡ホスト インスタンスが特定のメッセージ ボックス データベースの追跡データを移動しますが、されません 1 つ以上の追跡ホスト インスタンスの特定のメッセージ ボックス データベースのデータを移動します。 たとえば、3 つのメッセージ ボックス データベースと 2 つのホスト インスタンスの追跡がある場合は、そのホスト インスタンスのいずれかの必要があります、メッセージ ボックス データベースの 2 つのデータを移動します。 追跡を配布して、3 番目のホスト インスタンスの追跡を追加する BizTalk Server を実行している別のコンピューターへの作業をホストします。 このシナリオでは、複数の追跡ホストの配布と 4 つ目のホスト インスタンスの追跡を追加する機能しますが、余分なは、フォールト トレランスのホスト インスタンスを追跡します。  
  
 BAM イベント バス サービスの詳細については、BizTalk Server 2010 ヘルプで次のトピックを参照してください。  
  
-   [BAM イベント バス サービスを管理する](http://go.microsoft.com/fwlink/?LinkID=154194)(http://go.microsoft.com/fwlink/?LinkID=154194)。  
  
-   [BAM イベント バス サービスのインスタンスを作成する](http://go.microsoft.com/fwlink/?LinkID=154195)(http://go.microsoft.com/fwlink/?LinkID=154195)。  
  
### <a name="do-not-cluster-biztalk-hosts-unless-absolutely-necessary"></a>クラスター化しない BizTalk ホストしない限り、どうしても必要な  
 BizTalk Server 2010 では、BizTalk ホストをクラスター リソースとして構成することができます、中にのみ複数の BizTalk コンピューター間でホストされることはできません、リソースへの高可用性を提供する必要がある場合は、これを行うを考慮する必要があります。 例として、FTP アダプターを使用してポート必要がありますのみに存在する 1 つのホスト インスタンスでは、FTP プロトコルはファイルのロックを指定しないためです。 ただし、クラスタ リングからメリットを享受、障害の 1 つのポイントが生じます。 ホスト ファイル、SQL、HTTP ホストのみを処理などのアダプターを含めることができます内部的に負荷が複数のコンピューターで分散され、クラスター化から有効ではありません。  
  
## <a name="increase-the-number-of--http-concurrent-connections-allowed-by-changing-the-value-for-the-maxconnection-parameter"></a>Maxconnection パラメーターの値を変更することで許可される HTTP の同時接続の数を増やす  
 既定では、(WCF ベースの HTTP アダプターを含む)、HTTP アダプターは、特定の移行先サーバーに BizTalk Server を実行する各コンピューターから 2 つの同時実行 HTTP 接続を開きます。  
  
 この設定は、HTTP 1.1 仕様では、IETF RFC に準拠し、高スループットの最適化がいないですが、ユーザー シナリオに適した、します。 設定は、BizTalk Server を実行する各コンピューターから各サーバーに送信 HTTP 呼び出しを次の 2 つの同時送信効果的に調整されます。  
  
 同時接続数を増やすには、BTSNTSvc.exe.config (または BTSNTSvc64.exe.config の 64 ビット ホスト)、BizTalk Server ごとに、BizTalk Server 構成ファイルで maxconnection パラメーターの値を変更することができます。 これは、呼び出されている特定のサーバーに拡大できます。 原則として、として maxconnection パラメーターの値を 12 に設定する必要があります * Cpu または web アプリケーションをホストしているコンピューター上のコアの数。  
  
> [!NOTE]  
>  このような大きな値を HTTP 接続で呼び出されている Web サーバーの負荷が大きいこと maxconnection パラメーターの値を増やさないでください。 Maxconnection パラメーターの値を変更した後、ストレス maxconnection 良好なパフォーマンスと HTTP を提供するための値がターゲット Web をパンクさせることがなく送信を決定する各変換先の Web サーバーに要求を送信することによってテストを実行します。サーバー。  
  
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
  
 Maxconnection プロパティを設定するときに、HTTP、HTTPS、web サイトの IP アドレスおよびポート番号を指定することができます。 その他の例は次のとおりです。  
  
 **\<アドレスの追加"https://www.contoso.com"maxconnection を = =「24」/\>**   
**\<アドレスの追加"http://www.contoso.com:8080"maxconnection を = =「24」/\>**   
**\<アドレスを追加 ="http://*IPAddress*"maxconnection =「24」/\>* * Web サービスの IIS と ASP.NET の設定をチューニングの詳細については、「ASP.NET 設定 HTTP アダプターのパフォーマンスに影響する」を参照してくださいセクション。[アダプターのパフォーマンスに影響する構成パラメーター](http://go.microsoft.com/fwlink/?LinkID=154200) (http://go.microsoft.com/fwlink/?LinkID=154200) BizTalk Server 2010 ヘルプの「します。  
  
## <a name="manage-aspnet-thread-usage-or-concurrently-executing-requests-for-web-applications-that-can-host--isolated-received-locations-back-end-web-services-and-wcf-services"></a>ASP.NET スレッドの使用状況を管理または受信場所、バックエンド Web サービスと WCF サービスをホストする Web アプリケーションに対する要求を同時に実行される分離  
 ワーカーと I/O スレッド (IIS 7.5、およびクラシック モードの IIS 7.0) または同時に要求を実行する (IIS 7.5 および 7.0 統合モード) の ASP.NET Web アプリケーションの受信場所、バックエンド Web サービスと WCF サービス ホストを分離する数の数次の条件を変更する必要があります。  
  
-   CPU 使用率がホストする Web サーバー上のボトルネックではありません。  
  
-   値です。  
  
    -   **ASP.NET アプリ v4.0.30319 \Request Wait Time**または**ASP.NET アプリ v4.0.30319 \Request 実行時間**パフォーマンス カウンターが異常に高いです。  
  
    -   **ASP.NET アプリ v2.0.50727\Request Wait Time**または**ASP.NET アプリ v2.0.50727\Request 実行時間**パフォーマンス カウンターが異常に高いです。  
  
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
 ときに、 **autoConfig**クラシック モードで実行されている IIS 7.5、および IIS 7.0 サーバーの machine.config ファイル内の値に設定されて**true**、ASP.NET 2.0 および ASP.NET 4 は、ワーカー スレッドと I/O スレッドの数を管理します。関連付けられている IIS ワーカー プロセスに割り当てられます。  
  
```  
<processModel autoConfig="true" />  
```  
  
 ワーカー ロールと ASP.NET 2.0 および ASP.Net 4 Web アプリケーションの I/O スレッドの数を手動で変更するには、関連付けられている machine.config ファイルを開くし、新しい値を入力し、 **maxWorkerThreads**と**maxIoThreads**パラメーター。  
  
```  
<!-- <processModel autoConfig="true" /> -->  
    <processModel maxWorkerThreads="200" maxIoThreads="200" />  
```  
  
> [!NOTE]  
>  これらの値は、ガイダンスだけです。これらのパラメーターへの変更をテストすることを確認します。  
  
 ASP.NET 2.0 Web アプリケーションの machine.config ファイル内のパラメーターの調整の詳細については、Microsoft サポート技術情報の記事 821268 を参照してください。[競合、パフォーマンスの低下、およびデッドロック ASP から Web サービス要求を行うとします。NET アプリケーション](http://go.microsoft.com/fwlink/?LinkID=144169)(http://go.microsoft.com/fwlink/?LinkID=144169)。  
  
### <a name="manage-the-number-of-concurrently-executing-requests-for-aspnet-20-web-applications-that-can-host-isolated-received-locations-back-end-web-services-and-wcf-services-on-iis-75-and-iis-70-running-in-integrated-mode"></a>分離受信場所、バックエンド Web サービス、および IIS 7.5、および統合モードで実行されている IIS 7.0 での WCF サービスをホストする ASP.NET 2.0 Web アプリケーションに対する要求を同時に実行される数を管理します。  
 ASP.NET 2.0 が統合モードで IIS 7.5、および IIS 7.0 でホストされている場合のスレッドの使用が異なる方法よりも IIS 7.5、および IIS 7.0 でクラシック モードでします。 ASP.NET 2.0 が同時実行の数を制限して ASP.NET 2.0 が統合モードで IIS 7.5、および IIS 7.0 でホストされている場合**要求**の数ではなく**スレッド**同時実行要求します。 同期シナリオのこの直接が制限されましていないスレッドの数が非同期シナリオの要求およびスレッドの数が場合があります大きく異なります。 統合モードで IIS 7.5、および IIS 7.0 で ASP.NET 2.0 を実行すると、 **maxWorkerThreads**と**maxIoThreads** machine.config ファイル内のパラメーターが実行されているスレッドの数を制御するために使用されません。 指定された値を変更することで現在実行中の要求の数を CPU あたり 12 個の既定値から変更する代わりに、 **maxConcurrentRequestsPerCPU**です。 **MaxConcurrentRequestsPerCPU** reqistry または aspnet.config ファイルの構成セクションでは、値を指定することができます。 既定値を変更する次の手順に従って**maxConcurrentRequestsPerCPU**を現在実行中の要求の数を制御します。  
  
 **レジストリの maxConcurrentRequestsPerCPU 値を設定するには**  
  
> [!WARNING]  
>  レジストリ エディターの不適切な使用により問題が発生し、オペレーティング システムの再インストールが必要となることがあります。 レジストリ エディターは、ご自身の責任で使用してください。 バックアップ、復元、およびレジストリを変更する方法の詳細については、Microsoft サポート技術情報の記事 256986 を参照してください。[上級ユーザー向けの Windows レジストリ情報](http://go.microsoft.com/fwlink/?LinkId=62729)(http://go.microsoft.com/fwlink/?LinkId=62729)。  
  
> [!NOTE]  
>  この設定はグローバルであり、個々 のアプリケーション プールまたはアプリケーションに対しては変更できません。  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**regedit.exe**、順にクリック**ok**レジストリ エディターを起動します。  
  
2.  移動**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0**  
  
3.  次の手順に従って、キーを作成します。  
  
    1.  **編集** メニューのをクリックして**新規**、クリックして**キー**です。  
  
    2.  型**maxConcurrentRequestsPerCPU**、キーを押します**ENTER**です。  
  
    3.  下にある、 **maxConcurrentRequestsPerCPU**キー、maxConcurrentRequestsPerCPU の新しい値を持つ DWORD エントリを作成します。  
  
    4.  レジストリ エディターを閉じます。  
  
 **Aspnet.config ファイルの構成セクションで、アプリケーション プールの maxConcurrentRequestsPerCPU 値を設定するには**  
  
> [!NOTE]  
>  Microsoft .NET Framework 3.5 Service Pack 1 をインストールして、構成ファイルを使用して下の値の設定に対応する必要があります。 Microsoft .NET Framework 3.5 Service Pack 1 をダウンロードする[Microsoft .NET Framework 3.5 Service Pack 1](http://go.microsoft.com/fwlink/?LinkID=136345) (http://go.microsoft.com/fwlink/?LinkID=136345)。  
  
 アプリケーション プールの aspnet.config ファイルを開き、新しい値を入力し、 **maxConcurrentRequestsPerCPU**と**requestQueueLimit**パラメーター。  
  
```  
<system.web>  
    <applicationPool maxConcurrentRequestsPerCPU="12" requestQueueLimit="5000"/>  
</system.web>  
```  
  
> [!NOTE]  
>  この値に指定された値より優先**maxConcurrentRequestsPerCPU**レジストリにします。 Aspnet.config ファイルの設定は、machine.config ファイルで設定を上書きする点を除いて、requestQueueLimit 設定は、processModel/requestQueueLimit として同じです。  
  
 IIS 7.0 で ASP.NET スレッドの使用法を構成する方法の詳細については、次を参照してください。 [IIS 7.0 で ASP.NET スレッドの使用に関する Thomas Marquardt のブログ](http://go.microsoft.com/fwlink/?LinkId=157518)(http://go.microsoft.com/fwlink/?LinkId=157518)。  
  
### <a name="manage-the-number-of-concurrently-executing-requests-for-aspnet-4web-applications-that-can-host-isolated-received-locations-back-end-web-services-and-wcf-services-on-iis-75-and-70-running-in-integrated-mode"></a>分離受信場所、バックエンド Web サービス、および IIS 7.5、および統合モードで実行されている 7.0 での WCF サービスをホストする ASP.NET 4Web アプリケーションに対する要求を同時に実行される数を管理します。  
 .NET Framework 4、maxConcurrentRequestsPerCPU の既定の設定に膨大な数は 5000、したがってはのに十分な非同期要求を同時に実行します。 詳細については、次を参照してください。 [ \<applicationPool\>要素 (Web 設定)](http://go.microsoft.com/fwlink/?LinkID=205339) (http://go.microsoft.com/fwlink/?LinkID=205339)。  
  
 IIS 7.5、および IIS 7.0 統合モードの場合は、HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\4.0.30319.0 内の MaxConcurrentRequestsPerCPU をという名前の DWORD は CPU ごとの同時要求の数を決定します。 既定では、レジストリ キーが存在しないと、CPU あたりの要求の数は 5000 に制限されます。  
  
 **レジストリの maxConcurrentRequestsPerCPU 値を設定するには**  
  
> [!WARNING]  
>  レジストリ エディターの不適切な使用により問題が発生し、オペレーティング システムの再インストールが必要となることがあります。 レジストリ エディターは、ご自身の責任で使用してください。 バックアップ、復元、およびレジストリを変更する方法の詳細については、Microsoft サポート技術情報の記事 256986 を参照してください。[上級ユーザー向けの Windows レジストリ情報](http://go.microsoft.com/fwlink/?LinkId=62729)(http://go.microsoft.com/fwlink/?LinkId=62729)。  
  
> [!NOTE]  
>  この設定はグローバルであり、個々 のアプリケーション プールまたはアプリケーションに対しては変更できません。  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**regedit.exe**、順にクリック**ok**レジストリ エディターを起動します。  
  
2.  移動**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\4.0.30319.0**です。  
  
3.  次の手順に従って、キーを作成します。  
  
    1.  **編集** メニューのをクリックして**新規**、クリックして**キー**です。  
  
    2.  型**maxConcurrentRequestsPerCPU**、キーを押します**ENTER**です。  
  
    3.  下にある、 **maxConcurrentRequestsPerCPU**キー、maxConcurrentRequestsPerCPU の新しい値を持つ DWORD エントリを作成します。  
  
    4.  レジストリ エディターを閉じます。  
  
 **Aspnet.config ファイルの構成セクションで、アプリケーション プールの maxConcurrentRequestsPerCPU 値を設定するには**  
  
> [!NOTE]  
>  Microsoft .NET Framework 4 をインストールして、構成ファイルを使用して下の値の設定に対応する必要があります。 Microsoft .NET Framework 4 をダウンロードする[Microsoft .NET Framework 4 (Web インストーラー)](http://go.microsoft.com/fwlink/?LinkID=189318) (http://go.microsoft.com/fwlink/?LinkID=189318)。  
  
-   アプリケーション プールの aspnet.config ファイルを開き、新しい値を入力し、 **maxConcurrentRequestsPerCPU**と**requestQueueLimit**パラメーター。  
  
     次の例の値は、既定値です。  
  
    ```  
    <system.web>  
        <applicationPool maxConcurrentRequestsPerCPU="5000" requestQueueLimit="5000"/>  
    </system.web>  
    ```  
  
> [!NOTE]  
>  この値に指定された値より優先**maxConcurrentRequestsPerCPU**レジストリにします。 **RequestQueueLimit** aspnet.config ファイルの設定は、machine.config ファイルで設定を上書きする点を除いて設定は processModel/requestQueueLimit と同じです。  
  
## <a name="define-clr-hosting-thread-values-for-biztalk-host-instances"></a>CLR ホストの BizTalk ホスト インスタンスのスレッドの値を定義します。  
 Windows スレッドは、Windows プロセスに使用できる最も基本的な実行可能単位なので、BizTalk ホストのインスタンスに関連付けられた .NET スレッド プールには十分なスレッドを割り当てて、スレッドが不足しないようにすることが重要です。 スレッドの不足が発生すると場合、パフォーマンスに悪影響を及ぼす影響を与える、要求された作業を実行するための十分なスレッドはできませんがあります。 同時に、ホストに関連付けられた .NET スレッド プールに必要以上にスレッドを割り当てないよう注意する必要があります。 ホストに関連付けられた .NET スレッド プールに割り当てたスレッドが多すぎると、コンテキストの切り替えが増加する場合があります。 コンテキストの切り替えは、Windows カーネル切り替えるパフォーマンス コストが生じます別のスレッドを 1 つのスレッドを実行しているときに発生します。 過剰なスレッドの割り当てとなるコンテキストの過度の切り替え、全体的なパフォーマンスが低下します。 既定の BizTalk ホスト インスタンスの .NET スレッド プールに割り当てられているスレッド数は、インストールは、.NET Framework のバージョンに依存します。 .NET Framework 4 および .NET Framework 3.5 SP1 はの既定値は、BizTalk Server コンピューターと、メッセージ ボックス データベースの過剰なロックの競合に過剰なスレッドの割り当てが発生することができますを大幅に増加します。  
  
 使用して、 **BizTalk 設定ダッシュ ボード**.NET で使用できる Windows スレッド数のスレッド化された BizTalk ホストのインスタンスに関連付けられているプールの既定値を変更することができます。 .NET CLR 設定を変更する方法の詳細については、次を参照してください。 [.NET CLR 設定を変更する方法](http://go.microsoft.com/fwlink/?LinkID=205344)(http://go.microsoft.com/fwlink/?LinkID=205344)。 .NET CLR 設定は、コア CPU ごとに適用されます。  
  
> [!NOTE]  
>  **ワーカー スレッド**キューに置かれた作業項目の処理に使用して**I/O スレッド**専用のコールバック スレッドが完了した非同期 I/O 要求を処理する I/O 完了ポートに関連付けられています。  
  
|スレッドの設定|既定値|推奨値|  
|------------------------|-------------------|-----------------------|  
|最大 IO スレッド数|250|250|  
|ワーカー スレッド最大数|25|100**重要:** 100 よりもこの値を増やすと、BizTalk Server メッセージ ボックス データベースをホストする SQL Server コンピューターのパフォーマンスに悪影響が持つことができます。 この問題が発生した場合、SQL Server でデッドロック状態が発生することがあります。 このパラメーター値の 100 を超えるを増加していないことをお勧めします。|  
|最小 IO スレッド数|25|25|  
|最小ワーカー スレッド|5|25|  
  
> [!NOTE]  
>  推奨値は絶対的であり、BizTalk アプリケーションに応じて調整する必要があります。 一度に 1 つのパラメーターを変更し、追加の変更を加える前に、BizTalk プラットフォームの安定性とパフォーマンスに与える影響を測定します。  
  
> [!NOTE]  
>  これらの値は、サーバー上のプロセッサの数を掛けた暗黙的にします。 たとえば、設定、 **MaxWorkerThreads**エントリ 100 の値を効果的に設定値が 400 の 4 CPU サーバーでします。  
  
## <a name="disable-biztalk-server-group-level-tracking"></a>BizTalk Server グループ レベルの追跡を無効にします。  
 追跡のためデータには、メッセージ ボックス データベースに書き込み、その後、BizTalk 追跡データベースに非同期的に移動する BizTalk Server 内でオーバーヘッドがパフォーマンスが生じます。 運用環境の BizTalk Server 環境で追跡を構成するときに、次の考慮事項が適用されます。  
  
-   原則として、として追跡がビジネス要件でない場合は、無効になりますオーバーヘッドを削減してパフォーマンスを向上させるグループ レベルの追跡。  
  
     BizTalk Server グループ レベルの追跡を無効にするには、次の手順を実行します。  
  
    1.  **BizTalk Server 管理コンソール**、展開**BizTalk Server 管理コンソール**を右クリックして**BizTalk グループ**、クリックして**設定**.  
  
    2.  BizTalk 設定ダッシュ ボード] ダイアログ ボックスの [グループ] ページで、[、**グループ レベルの追跡を有効にする**チェック ボックスをオンします。  
  
    3.  をクリックして**OK**を変更を適用し、設定ダッシュ ボードを終了します。  
  
-   メッセージ本文の追跡に必要な場合に使用のみです。 メッセージのスループットとに応じてメッセージのサイズ、メッセージ本文の追跡に大きなオーバーヘッド可能性があります。 BizTalk の動作状況の追跡には、デバッグや、監査の明らかな利点がありますが、により、パフォーマンスとスケーラビリティの問題もあります。 そのため、デバッグ、セキュリティ上の理由から、必ずしも必要では、冗長な情報の追跡を回避できますデータのみを追跡する必要があります。  
  
-   既定では、次の追跡オプションが有効にするオーケストレーション。  
  
    -   オーケストレーションの開始と終了  
  
    -   メッセージの送信および受信  
  
    -   図形の開始と終了  
  
     追跡オプション「図形の開始と終了」オーケストレーションは、大幅なオーバーヘッドが発生し、高いスループットが必要な実稼働環境で有効にする必要がありますされません。 オーケストレーションの追跡オプションが、BizTalk 管理コンソールでアクセス可能な**追跡**オーケストレーションのプロパティ ダイアログ ボックスのページです。  
  
 追跡の構成の詳細については、次を参照してください。 [、BizTalk Server 管理コンソールを使用した追跡構成](http://go.microsoft.com/fwlink/?LinkId=158021)(http://go.microsoft.com/fwlink/?LinkId=158021)。  
  
## <a name="decrease-the-purging-period-for-the-dta-purge-and-archive-job-from-7-days-to-2-days-in-high-throughput-scenarios"></a>DTA Purge and Archive ジョブから 7 日間で高スループットのシナリオ 2 日間に、パージ period を短縮します。  
 既定では、BizTalk Server でのデータを追跡するため、パージ間隔は 7 日間に設定します。 高スループットのシナリオでは、メッセージ ボックスおよびさらに悪い影響メッセージの処理スループットのパフォーマンスに影響を与えるは最終的に追跡データベース内のデータを過剰なビルドではこのことがあります。  
  
 高スループットのシナリオでは、ハードとソフト 7 日間の既定値から 2 日間に間隔をパージを減らします。 削除間隔を構成する方法の詳細については、次を参照してください。 [DTA Purge and Archive ジョブを構成する方法](http://go.microsoft.com/fwlink/?LinkID=153814)(http://go.microsoft.com/fwlink/?LinkID=153814)、BizTalk Server 2010 ヘルプ。  
  
## <a name="configure-the-temp-path-for-the-biztalk-service-account-to-point-to-a-separate-disk-or-lun"></a>%Temp% へのパスを別のディスクまたは LUN を指す BizTalk サービス アカウントの構成します。  
 これは、BizTalk は、複雑なマッピング操作を実行するときにディスクにストリーム ファイルを一時的な場所を使用するために行う必要があります。  
  
## <a name="install-the-latest-service-packs"></a>最新のサービス パックをインストールします。  
 パフォーマンスの問題が発生する可能性を修正できる修正プログラムが含まれてとして、BizTalk Server と .NET Framework の両方の最新の service pack をインストールする必要があります。  
  
## <a name="performance-optimizations-in-the-biztalk-server-documentation"></a>BizTalk Server のマニュアルでパフォーマンスの最適化  
 必要に応じて、BizTalk Server のドキュメントから次の推奨事項が適用されます。  
  
-   [メッセージ ボックスの待機時間に関する問題のトラブルシューティング](http://go.microsoft.com/fwlink/?LinkId=158019)(http://go.microsoft.com/fwlink/?LinkId=158019)  
  
-   [パフォーマンスのボトルネックを特定する](http://go.microsoft.com/fwlink/?LinkID=154238)(http://go.microsoft.com/fwlink/?LinkID=154238)  
  
-   [DBNETLIB 例外の回避](http://go.microsoft.com/fwlink/?LinkID=155308)(http://go.microsoft.com/fwlink/?LinkID=155308)  
  
-   [TCP/IP ポートの枯渇を回避する](http://go.microsoft.com/fwlink/?LinkID=153240)(http://go.microsoft.com/fwlink/?LinkID=153240)  
  
-   [EPM スレッド プール サイズを設定](http://go.microsoft.com/fwlink/?LinkId=158020)(http://go.microsoft.com/fwlink/?LinkId=158020)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server パフォーマンスの最適化](../technical-guides/optimizing-biztalk-server-performance.md)