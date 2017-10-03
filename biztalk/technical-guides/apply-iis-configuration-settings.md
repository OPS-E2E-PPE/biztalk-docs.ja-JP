---
title: "IIS 構成設定を適用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d638f83-e1c8-4e35-b345-361d5a3093fa
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a032070876df6bea0579a159d527a6ad903e2ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="apply-iis-configuration-settings"></a>IIS 構成設定を適用します。
既定では、SOAP、HTTP、HTTP ベース WCF アダプター (および通常の .NET) を開きます. のみに 2 つの同時実行 HTTP 接続各 BizTalk ホスト インスタンスからの特定の移行先サーバーに たとえばがある場合、SOAP 送信ポートを送信するメッセージを**http://www.contoso.com/SomeWebService.asmx**、し、既定で各ホスト インスタンスで実行されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]に2つの同時実行HTTP接続を開く**www.contoso.com**、送信する必要があるメッセージの数に関係なく。  
  
 この設定は、HTTP 1.1 仕様では、IETF RFC に準拠しているされ、スループットの高いサーバー間通信のため、最適化されていないユーザー シナリオに適したですが、します。 既定の設定は、送信 SOAP および HTTP 呼び出しのそれぞれから 2 つの同時実行するには、各移行先サーバーに送信を効果的に調整[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト インスタンス。  
  
## <a name="configure-aspnet-maxconcurrentrequests-for-iis-70-integrated-mode"></a>IIS 7.0 統合モード用 ASP.NET MaxConcurrentRequests を構成します。  
 ASP.NET 2.0 が統合モードでの IIS 7.0 でホストされている場合のスレッドの使用が異なる方法よりも IIS 6.0 または IIS 7.0 でクラシック モードでします。 ASP.NET 2.0 が統合モードで IIS 7.0 でホストされている場合、ASP.NET 2.0 は、現在実行中の要求を同時に実行するスレッドの数ではなく要求の数を制限します。 同期のシナリオでは、これは直接制限いないスレッドの数要求の数は、スレッドの数と同じになるためします。 非同期のシナリオでの要求とスレッド数可能性があることが非常に異なるスレッドよりもはるかに多くの要求をする可能性があるためです。 統合モードの IIS 7.0 で ASP.NET 2.0 を実行するときに minFreeThreads および machine.config 内の"httpRuntime"要素の minLocalRequestFreeThreads は無視されます。 IIS 7.0 統合モードでは、HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0 内の MaxConcurrentRequestsPerCPU をという名前の DWORD は CPU ごとの同時要求の数を決定します。 既定では、レジストリ キーが存在しないと、CPU あたりの要求の数は 12 に制限されます。 .NET framework 3.5 SP1 には、aspnet.config ファイルを使用して、構成の IIS アプリケーション プールをサポートするバージョン 2.0 のバイナリに更新プログラムが含まれています。 この構成は統合モードのみに適用されます (ISAPI/クラシック モードでは、これらの設定を無視します)。新しい aspnet.config config セクションには、既定値は次のとおりです。  
  
```  
<system.web>  
   <applicationPool maxConcurrentRequestsPerCPU="12" maxConcurrentThreadsPerCPU="0" requestQueueLimit="5000"/>  
</system.web>  
```  
  
 原則として、として MaxConcurrentRequestsPerCPU を 5000 などの非常に大きな値に設定してください。  
  
 IIS 7.0、統合モードで、maxWorkerThreads と、""ファイルの processModel セクションは machine.config で maxIoThreads パラメーターは、要求を本質的に実行中の数を制御するために使用されませんが、CLR スレッド プールのサイズを制御するためには使用されます。ASP.NET によって使用されます。 ときに、machine.config の"processModel"セクションが"autoConfig = true"(既定の設定は)、これにより、アプリケーション プールの論理 CPU ごとの最大 100 個のワーカー スレッド (MaxWorkerThreads)。 その 2 つのデュアル コア Cpu で共通の汎用的なサーバーは 400 MaxWorkerThreads があります。 最も高いアプリケーションを除くすべてのための十分な場合があります。  
  
 IIS 7.0 および 6.0 に ASP.NET スレッドの使用法を構成する方法の詳細については、次を参照してください。 [ASP.NET IIS 7.0 および 6.0 のスレッドの使用量に Thomas Marquardt のブログ](http://go.microsoft.com/fwlink/?LinkId=157518)(http://go.microsoft.com/fwlink/?LinkId=157518)。  
  
## <a name="log-only-essential-information-or-completely-disable-iis-logging"></a>重要な情報のみをログまたは IIS のログを完全に無効にします。  
 IIS ログを最小化または実稼働環境でも無効にする必要があります。 ログ記録を無効にするには、これらの手順に従います。  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**管理ツール**、クリックして**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
2.  **接続** ウィンドウをクリックして展開**サイト**をクリックしてログ記録を無効をクリックして選択する Web サイトを選択**機能ビュー**、し、ダブルクリックして、**ログ**機能します。  
  
3.  をクリックして**を無効にする**で、**アクション**をこの Web サイトのログ記録を無効にするウィンドウです。  
  
## <a name="disable-iis-asp-debugging-in-production-environments"></a>実稼働環境で IIS の ASP のデバッグを無効にします。  
 運用環境で IIS の ASP のデバッグを無効にする必要があります。 ASP デバッグを IIS を無効にするには、これらの手順に従います。  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**管理ツール**、クリックして**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
2.  **接続** ウィンドウをクリックして展開**サイト**、ASP のデバッグを無効にするをクリックして選択する web サイトを選択する をクリックします**機能ビュー**、し、。ダブルクリックして、 **ASP**機能します。  
  
3.  クリックして展開**コンパイル**をクリックして展開**デバッグ プロパティ**、いることを確認し、両方**クライアント側のデバッグを有効にする**と**サーバー側を有効にします。デバッグ**に設定されている**False**です。  
  
4.  必要に応じてをクリックして**適用**で、**アクション**ウィンドウです。  
  
 ASP.NET アプリケーションおよび Web サービスを指定することでデバッグを無効にする、\<コンパイル デバッグ ="false"/> の web アプリケーションの web.config ファイルでセクションです。  
  
## <a name="tune-the-value-of-the-asp-threads-per-processor-limit-property"></a>ASP スレッドごとのプロセッサ制限プロパティの値を調整します。  
 ASP**スレッドあたりプロセッサ数の上限**プロパティは、IIS を作成できる 1 プロセッサあたりのワーカー スレッドの最大数を指定します。 プロセッサ使用率が 50% 以上を満たすまで以上のプロセッサあたりのスレッド制限に対して、値を増やします。 この設定できるに大きな影響を Web アプリケーションのスケーラビリティと、サーバーのパフォーマンス一般にします。 このプロパティは、同時に実行できる ASP 要求の最大数を定義するため、ASP アプリケーションが外部コンポーネントへの拡張の呼び出しを行う場合を除いて、既定値にこの設定する必要がありますしたまま。 この場合、スレッドあたりプロセッサ数の上限の値を大きくことがあります。 これにより、サーバーへの同時要求を処理するスレッドを作成できます。 スレッドあたりプロセッサ数の上限の既定値は 25 です。 このプロパティの推奨最大値は 100 です。  
  
 増やすにはプロセッサごとのスレッド制限の値は次の手順に従います。  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**管理ツール**、クリックして**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
2.  **接続**ウィンドウで、web サーバーを選択して、クリックして選択**機能ビュー**、順にダブルクリックし、 **ASP**機能します。  
  
3.  クリックして展開**制限プロパティ****動作**、 をクリックして**スレッドあたりプロセッサ数の上限**、目的の値を入力**スレッドあたりプロセッサ数の上限**  をクリック**適用**で、**アクション**ウィンドウです。  
  
 プロパティを変更する方法について、\<制限 > 要素は、IIS 7.0 の\<asp > 要素を参照してください[ASP 制限\<制限 >](http://go.microsoft.com/fwlink/?LinkId=157483) (http://go.microsoft.com/fwlink/?LinkId=157483)。  
  
> [!NOTE]  
>  このプロパティは、サーバー レベルでのみ適用できる、このプロパティの変更は、サーバー上で実行されるすべての Web サイトに影響します。  
  
> [!NOTE]  
>  ASP**スレッドあたりプロセッサ数の上限**IIS 7.0 のプロパティを置き換える、IIS 6.0 **ASPProcessorThreadMax** ASP メタベースの設定。 IIS 6.0 ASPProcessorThreadMax ASP メタベース設定の詳細については、次を参照してください。 [ASP メタベースの設定のチューニング](http://go.microsoft.com/fwlink/?LinkId=158834)(http://go.microsoft.com/fwlink/?LinkId=158834) MSDN のです。  
  
## <a name="tune-the-value-of-the-asp-queue-length-property"></a>ASP キューの長さのプロパティの値を調整します。  
 このプロパティをチューニングの目的は、ASP 要求キューがいっぱいになったとき、サーバーで、HTTP 503 (サーバーがビジー状態) エラーをクライアントに送信する頻度を最小限に抑えながら良好な応答時間のことです。 ASP キューの長さのプロパティの値が低すぎる場合は、サーバーは、HTTP 503 エラーをより高い頻度で送信します。 ASP キューの長さのプロパティの値が高すぎる場合は、ユーザーは、サーバーが応答していないことと実際の要求がキューで待機しているを感じる可能性があります。 大量のトラフィックの期間中に、キューを監視して、web 要求のピーク時とオフのパターンを識別できる必要があります。 ピーク時の値をメモを行い、ピーク時の値の真上 ASP キューの長さのプロパティの値を設定します。 キューを使用して短期的な急増に対応、応答時間を確認および維持、予期しないスパイクが発生したときにオーバー ロードを避けるためにシステムを調整します。 ASP キューの長さのプロパティを調整するためのデータがない、適切な開始点のスレッドの合計にキューの 1 対 1 の比率を設定するされます。 たとえば、ASP スレッドごとのプロセッサ制限プロパティは 25 に設定され、4 つのプロセッサがある場合 (4 * 25 = 100 スレッド) を 100 に ASP キューの長さのプロパティを設定、およびそこからチューニングします。  
  
 キューの長さのプロパティの値を増やすには、次の手順を実行します。  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**管理ツール**、クリックして**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
2.  **接続**ウィンドウで、Web サーバーを選択して、クリックして選択**機能ビュー**、順にダブルクリックし、 **ASP**機能します。  
  
3.  クリックして展開**制限プロパティ**[**動作**、] をクリックして**キューの長さ**、目的の値を入力**キューの長さ**し、をクリックして**適用**で、**アクション**ウィンドウです。  
  
 プロパティを変更する方法について、\<制限 > 要素は、IIS 7.0 の\<asp > 要素を参照してください[ASP 制限\<制限 >](http://go.microsoft.com/fwlink/?LinkId=157483) (http://go.microsoft.com/fwlink/?LinkId=157483)。  
  
> [!NOTE]  
>  このプロパティは、サーバー レベルでのみ適用できる、このプロパティの変更は、サーバー上で実行されるすべての Web サイトに影響します。  
  
> [!NOTE]  
>  ASP **Queue Length** IIS 7.0 のプロパティを置き換える、IIS 6.0 **AspRequestQueueMax** ASP メタベースの設定。 IIS 6.0 AspRequestQueueMax ASP メタベース設定の詳細については、次を参照してください。 [ASP メタベースの設定のチューニング](http://go.microsoft.com/fwlink/?LinkId=158834)(http://go.microsoft.com/fwlink/?LinkId=158834) MSDN のです。  
  
## <a name="tune-the-maxpoolthreads-registry-entry"></a>MaxPoolThreads レジストリ エントリをチューニングします。  
 この設定は、プロセッサごとに作成するプールのスレッドの数を指定します。 プールのスレッドは、ネットワークの要求および着信要求の処理を監視します。 MaxPoolThreads 数では ISAPI アプリケーションで使用されるスレッドは含まれません。 一般に、プロセッサごとに 20 を超えるスレッドを作成しないでください。 MaxPoolThreads は、既定値は 4 で HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\InetInfo\Parameters\ にある REG_DWORD レジストリ エントリです。  
  
## <a name="disable-wcf-services-tracing"></a>WCF サービスのトレースを無効にします。  
 WCF サービスが実稼働環境でトレースを無効にするには、構成エディター ツール (SvcConfigEditor.exe) を使用します。 構成エディター ツールの詳細については、次を参照してください。[構成エディター ツール (SvcConfigEditor.exe)](http://go.microsoft.com/fwlink/?LinkID=127070) (http://go.microsoft.com/fwlink/?LinkID=127070)。  
  
## <a name="see-also"></a>参照  
 [チェックリスト: BizTalk Server を構成します。](../technical-guides/checklist-configuring-biztalk-server.md)