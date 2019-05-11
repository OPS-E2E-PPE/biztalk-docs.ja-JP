---
title: IIS の構成設定の適用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d638f83-e1c8-4e35-b345-361d5a3093fa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1cca51b10386f27066d2839817c6fbfef9db5d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401337"
---
# <a name="apply-iis-configuration-settings"></a>IIS 構成設定を適用します。
既定では、SOAP、HTTP、HTTP ベースで WCF アダプター (および一般に .NET) を開きます. 2 つの同時 HTTP 接続各 BizTalk ホスト インスタンスからの特定の移行先サーバーに などがある場合、SOAP 送信ポートを送信するメッセージを**<http://www.contoso.com/SomeWebService.asmx>**、各ホスト インスタンスのそれぞれで実行されている既定で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]への 2 つの同時 HTTP 接続を開く<strong>www.contoso.com</strong>、送信する必要があるメッセージの数に関係なく。  
  
 この設定は、HTTP 1.1 仕様は IETF RFC に準拠しているサーバー間通信の高スループットの最適化がいないユーザー シナリオに最適ですが、. 既定の設定は、送信 SOAP および HTTP 呼び出しのそれぞれから 2 つの同時実行するには、それぞれに移行先サーバーに送信を効果的に調整[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホストのインスタンス。  
  
## <a name="configure-aspnet-maxconcurrentrequests-for-iis-70-integrated-mode"></a>IIS 7.0 統合モード用の ASP.NET MaxConcurrentRequests を構成します。  
 ASP.NET 2.0 は、統合モードでの IIS 7.0 でホストされている、ときにスレッドの使用は異なる方法で処理よりも IIS 6.0 または IIS 7.0 でクラシック モード。 ASP.NET 2.0 が統合モードで IIS 7.0 でホストされている場合、ASP.NET 2.0 は、同時に実行される要求を同時に実行するスレッドの数ではなく要求の数を制限します。 同期のシナリオでこれ直接制限されましていないスレッドの数ため、要求の数には、スレッドの数と同じになります。 非同期のシナリオでは、要求とスレッドの数は可能性があります非常に異なるスレッドよりもはるかに要求する可能性があるためです。 統合モードの IIS 7.0 で ASP.NET 2.0 を実行するときに、minFreeThreads と machine.config ファイル内の"httpRuntime"要素の minLocalRequestFreeThreads は無視されます。 IIS 7.0 の Integrated モードは、HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0 内 MaxConcurrentRequestsPerCPU をという名前の DWORD CPU あたりの同時要求の数を決定します。 既定では、レジストリ キーが存在しないと、CPU あたりの要求の数は 12 に制限されます。 .NET framework 3.5 SP1 には、aspnet.config ファイルを使用して、構成の IIS アプリケーション プールをサポートする v2.0 バイナリに更新プログラムが含まれています。 この構成は、統合モードのみに適用されます (クラシックまたは ISAPI モードでは、これらの設定を無視します)。既定値を持つ新しい aspnet.config 構成セクションは、次に示します。  
  
```  
<system.web>  
   <applicationPool maxConcurrentRequestsPerCPU="12" maxConcurrentThreadsPerCPU="0" requestQueueLimit="5000"/>  
</system.web>  
```  
  
 経験上、として MaxConcurrentRequestsPerCPU を 5000 などの非常に大きな値に設定してください。  
  
 IIS 7.0 統合モードでは、maxWorkerThreads と maxIoThreads パラメーター、machine.config ファイルの"processModel"セクションでは、本質的に、要求の実行の数を制御するのには使用されませんがでも CLR スレッド プールのサイズの制御に使用されます。ASP.NET によって使用されます。 ときに、machine.config の"processModel"セクションが"autoConfig = true"(既定の設定では、) アプリケーション プールを論理 CPU あたりの最大 100 個のワーカー スレッド (MaxWorkerThreads) この付与されます。 したがって 2 つのデュアル コア Cpu で共通の汎用的なサーバーは 400 MaxWorkerThreads になります。 要件の高いアプリケーションを除くすべてのための十分な場合があります。  
  
 IIS 7.0 および 6.0 で ASP.NET のスレッドの使用量を構成する方法の詳細については、次を参照してください。 [ASP.NET IIS 7.0 および 6.0 のスレッドの使用状況に関する Thomas Marquardt のブログ](http://go.microsoft.com/fwlink/?LinkId=157518)(http://go.microsoft.com/fwlink/?LinkId=157518)します。  
  
## <a name="log-only-essential-information-or-completely-disable-iis-logging"></a>重要な情報のみを記録または IIS のログ記録を完全に無効にします。  
 IIS ログを最小化または運用環境でも無効にする必要があります。 ログ記録を無効にするには、これらの手順に従います。  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
2.  **接続** ウィンドウをクリックして展開**サイト**をクリックしてログ記録を無効にするをクリックして選択する Web サイトを選択**機能ビュー**、し、ダブルクリックして、**ログ**機能します。  
  
3.  クリックして**を無効にする**で、**アクション**この Web サイトのログ記録を無効にするウィンドウ。  
  
## <a name="disable-iis-asp-debugging-in-production-environments"></a>運用環境で IIS ASP デバッグを無効にします。  
 運用環境で IIS ASP デバッグを無効にする必要があります。 ASP デバッグを IIS を無効にするには、これらの手順に従います。  
  
1. クリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
2. **接続** ウィンドウをクリックして展開**サイト**、ASP デバッグを無効にするには、選択を web サイトを選択する をクリックします**機能ビュー**、し、。ダブルクリックして、 **ASP**機能します。  
  
3. クリックして展開**コンパイル**をクリックして展開**デバッグ プロパティ**、ことを確認します両方**クライアント側のデバッグを有効にする**と**サーバー側を有効にします。デバッグ**に設定されている**False**します。  
  
4. 必要に応じて、**適用**で、**アクション**ウィンドウ。  
  
   指定することで、ASP.NET アプリケーションおよび Web サービスのデバッグを無効にする、\<コンパイル デバッグ ="false"\> web アプリケーションの web.config ファイルのセクション。  
  
## <a name="tune-the-value-of-the-asp-threads-per-processor-limit-property"></a>プロセッサ数あたりのスレッドの ASP 上限プロパティの値を調整します。  
 ASP**スレッドあたりプロセッサ数の上限**プロパティを IIS に作成するプロセッサあたりのワーカー スレッドの最大数を指定します。 プロセッサ使用率が 50% 以上を満たすまで、またはの上に、プロセッサごとのスレッド制限の値を増やします。 この設定に大きな影響を Web アプリケーションのスケーラビリティおよび、サーバーのパフォーマンス一般にします。 このプロパティは、同時に実行可能な ASP 要求の最大数を定義するため、この設定は、ASP アプリケーションが外部コンポーネントへの拡張の呼び出しを行う場合を除いて既定値に残る必要があります。 この場合、スレッドあたりプロセッサ数の上限の値を増やすことができます。 これによりより多くの同時要求を処理する複数のスレッドを作成するサーバー。 スレッドあたりプロセッサ数の上限の既定値は、25 です。 このプロパティの最大の推奨値は、100 です。  
  
 高めるためにプロセッサごとのスレッド制限の値は次の手順に従います。  
  
1. クリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
2. **接続**ウィンドウで、web サーバーを選択して、クリックして選択**機能ビュー**、し、ダブルクリック、 **ASP**機能します。  
  
3. クリックして展開**制限プロパティ**[**動作**、] をクリックして**スレッドあたりプロセッサ数の上限**、目的の値を入力します**スレッドあたりプロセッサ数の上限。** クリック**適用**で、**アクション**ウィンドウ。  
  
   プロパティを変更する方法について、\<制限\>要素は、IIS 7.0 の\<asp\>要素を参照してください[ASP 制限\<制限\>](http://go.microsoft.com/fwlink/?LinkId=157483) (http://go.microsoft.com/fwlink/?LinkId=157483).  
  
> [!NOTE]  
>  このプロパティは、サーバー レベルでのみ適用できる、このプロパティの変更は、サーバー上で実行されるすべての Web サイトに影響します。  
  
> [!NOTE]  
>  ASP**スレッドあたりプロセッサ数の上限**プロパティを IIS 7.0、IIS 6.0 の置換**ASPProcessorThreadMax** ASP メタベースの設定。 IIS 6.0 ASPProcessorThreadMax ASP メタベースの設定については、次を参照してください。 [ASP メタベースの設定のチューニング](http://go.microsoft.com/fwlink/?LinkId=158834)(http://go.microsoft.com/fwlink/?LinkId=158834) msdn です。  
  
## <a name="tune-the-value-of-the-asp-queue-length-property"></a>ASP のキューの長さのプロパティの値を調整します。  
 このプロパティのチューニングの目的では、ASP 要求のキューがいっぱいになったとき、サーバーで HTTP 503 (サーバーがビジー状態です) エラーをクライアントに送信する頻度を最小限に抑えながら、良好な応答時間を確認します。 ASP のキューの長さのプロパティの値が小さすぎる場合、サーバーはより高い頻度で HTTP 503 エラーを送信します。 ASP のキューの長さのプロパティの値が高すぎる場合、サーバーが応答していないことと実際の要求がキューで待機しているユーザーが感じる可能性があります。 高トラフィックの期間中に、キューを視聴するには、web 要求の山と谷のパターンを識別する必要があります。 ピーク時の値をメモし、ピーク時の値のすぐ上の ASP キューの長さのプロパティの値を設定します。 キューを使用して短期的な急増を処理、応答時間、ことを確認し、維持、予期しないスパイクが発生したときにオーバー ロードを回避するためにシステムを調整します。 ASP キューの長さのプロパティを調整するためのデータがない場合、適切な開始点は、スレッドの合計にキューの 1 対 1 の比率を設定するになります。 たとえば、4 つのプロセッサを使用して ASP スレッドごとのプロセッサ制限プロパティを 25 に設定されている場合 (4 * 25 = 100 スレッド)、ASP キューの長さのプロパティを 100 に設定し、そこから調整します。  
  
 キューの長さのプロパティの値を増やすには、次の手順を実行します。  
  
1. クリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
2. **接続**ウィンドウで、Web サーバーを選択して、クリックして選択**機能ビュー**、し、ダブルクリック、 **ASP**機能します。  
  
3. クリックして展開**制限プロパティ**[**動作**、] をクリックして**キューの長さ**、目的の値を入力します**キューの長さ**し。クリックして**適用**で、**アクション**ウィンドウ。  
  
   プロパティを変更する方法について、\<制限\>要素は、IIS 7.0 の\<asp\>要素を参照してください[ASP 制限\<制限\>](http://go.microsoft.com/fwlink/?LinkId=157483) (http://go.microsoft.com/fwlink/?LinkId=157483).  
  
> [!NOTE]  
>  このプロパティは、サーバー レベルでのみ適用できる、このプロパティの変更は、サーバー上で実行されるすべての Web サイトに影響します。  
  
> [!NOTE]  
>  ASP**キューの長さ**プロパティを IIS 7.0、IIS 6.0 の置換**AspRequestQueueMax** ASP メタベースの設定。 IIS 6.0 AspRequestQueueMax ASP メタベースの設定については、次を参照してください。 [ASP メタベースの設定のチューニング](http://go.microsoft.com/fwlink/?LinkId=158834)(http://go.microsoft.com/fwlink/?LinkId=158834) msdn です。  
  
## <a name="tune-the-maxpoolthreads-registry-entry"></a>MaxPoolThreads のレジストリ エントリを調整します。  
 この設定では、プロセッサごとに作成するプールのスレッドの数を指定します。 プールのスレッドでは、ネットワーク要求と受信要求の処理をご覧ください。 MaxPoolThreads 数では ISAPI アプリケーションで使用されるスレッドは含まれません。 一般に、プロセッサごとに 20 個を超えるスレッドを作成しないでください。 MaxPoolThreads では、既定値は 4 の HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\InetInfo\Parameters\ にある REG_DWORD レジストリ エントリです。  
  
## <a name="disable-wcf-services-tracing"></a>WCF サービスのトレースを無効にします。  
 WCF サービスの運用環境でのトレースを無効にするには、構成エディター ツール (SvcConfigEditor.exe) を使用します。 構成エディター ツールの詳細については、次を参照してください。[構成エディター ツール (SvcConfigEditor.exe)](http://go.microsoft.com/fwlink/?LinkID=127070) (http://go.microsoft.com/fwlink/?LinkID=127070)します。  
  
## <a name="see-also"></a>参照  
 [チェックリスト:BizTalk Server の構成](../technical-guides/checklist-configuring-biztalk-server.md)