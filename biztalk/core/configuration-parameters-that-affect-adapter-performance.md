---
title: アダプターのパフォーマンスに影響する構成パラメーター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 90bbb9fb-0b31-45f0-a54c-7b2025e653b9
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ba58e8f08b453c76ffcf0bc38bf2e75ebf07b20
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356469"
---
# <a name="configuration-parameters-that-affect-adapter-performance"></a>アダプターのパフォーマンスに影響する構成パラメーター
このセクションでは、BizTalk Server アダプターのパフォーマンスに影響する構成設定について説明します。  
  
## <a name="clr-hosting-thread-values-for-the-host"></a>ホスト用 CLR Hosting スレッド値  
 Windows スレッドは、Windows プロセスに使用できる最も基本的な実行可能単位なので、BizTalk ホストのインスタンスに関連付けられた .NET スレッド プールには十分なスレッドを割り当てて、スレッドが不足しないようにすることが重要です。 スレッドの不足が発生したときに、パフォーマンスに悪影響を与えることができますが、要求された作業を実行できる十分なスレッドはありませんがあります。 同時に、注意してください必要なは、ホストに関連付けられた .NET スレッド プールに多くのスレッドを割り当てないようにします。 ホストに関連付けられた .NET スレッド プール スレッドが多すぎるの割り当ては、全体的なパフォーマンスに悪影響が出ること影響を与えることができるコンテキストの切り替え増やすことができます。 コンテキストの切り替えには、いずれかの操作を実行しているから Windows カーネル スイッチは、別のスレッドをスレッドし、CPU 操作のコストとが発生します。  
  
 BizTalk Server 設定ダッシュ ボードで、適切な値を構成することで、BizTalk ホストのインスタンスに関連付けられた .NET スレッド プールで使用できる Windows スレッド数を変更します。 .NET CLR 値を変更する方法の詳細については、次を参照してください。 [.NET CLR 設定を変更する方法](http://msdn.microsoft.com/library/ff629681\(v=BTS.70\).aspx)します。  
  
## <a name="aspnet-settings-that-can-impact-http-or-soap-adapter-performance"></a>HTTP アダプタまたは SOAP アダプタのパフォーマンスに影響する ASP.NET の設定  
 次の設定は、HTTP または SOAP アダプターと通信する Web アプリケーションをホストする ASP.NET アプリケーションに適用できます。 これらのパラメーターは、Web アプリケーションをホストするサーバーの web.config または machine.config ファイルで設定されます。 HTTP によって生成される負荷に対応するためにこれらの設定を変更または SOAP アダプター送信ポート。 これらの設定の詳細については、次を参照してください。[競合、パフォーマンスの低下、および ASP.NET アプリケーションから Web サービス要求を行うときにデッドロック](http://go.microsoft.com/fwlink/p/?LinkId=196842)します。  
  
|**パラメーター**|**構成ファイルのセクション**|**既定値**|**推奨値**|  
|-------------------|---------------------------------------|-----------------------|---------------------------|  
|**minFreeThreads**<br /><br /> 新しい要求の実行を許可するフリー スレッドの最小数。 ASP.NET では、この数の追加のスレッドの処理を完了するを必要とする要求のフリー スレッドを保持します。|\<httpRuntime\>|8|88 * Web アプリケーションをホストするサーバー上のプロセッサの数。|  
|**minFreeLocalRequestFreeThreads**<br /><br /> ASP.NET は、新しいローカル要求の実行を許可する使用可能なフリー スレッドの最小数。 このスレッドの数は、これらの処理中に、ローカル ホストに子要求が発行要求がある場合に、ローカル ホストからの要求用に予約されて保持されます。 Web サーバーへの再帰的な再入可能なデッドロックを回避できます。|\<httpRuntime\>|4|76 * Web アプリケーションをホストするサーバー上のプロセッサの数。|  
|**executionTimeout**<br /><br /> 要求が ASP.NET によって自動的にシャット ダウンされる前に実行できる秒の最大数を示します。|\<httpRuntime\>|90|90|  
|**maxconnection**<br /><br /> 特定の IP アドレスに接続の数ができるかを決定します。|\<connectionManagement\>|2<br /><br /> この設定の 2 の値は、HTTP 1.1 仕様は IETF RFC に準拠しているはユーザー シナリオに適していて、高スループットについては最適化されません。|12 * Web アプリケーションをホストするサーバー上のプロセッサの数。|  
|**MaxWorkerThreads**<br /><br /> -CPU ごとにプロセスに使用するワーカー スレッドの最大量を構成します。|\<processModel\>|20|100**に注意してください。** この値は、暗黙的に、サーバー上のプロセッサの数は乗算されます。|  
|**MinWorkerThreads**|\<processModel\>|1|**maxWorkerThreads** /2**に注意してください。** MinWorkerThreads パラメーターは、既定では、構成ファイルではありません。 追加する必要があります。 **注:** この値は、暗黙的に、サーバー上のプロセッサの数は乗算されます。|  
|**maxIoThreads**<br /><br /> ASP.NET によって使用される完了スレッドの数を制限するために使用します。|\<processModel\>|20|100<br /><br /> この値は、暗黙的に、サーバー上のプロセッサの数は乗算されます。|  
  
 Web サービスをホストするコンピューターで ASP.NET 2.0 以降を実行し、設定することができるかどうか**autoConfig = true**を最適にするのには、次の設定を自動的に構成する Machine.config ファイルの processModel セクションマシンの構成に基づくパフォーマンス:  
  
-   **MaxWorkerThreads**属性。  
  
-   **MaxIoThreads**属性。  
  
-   **MinFreeThreads** httpRuntime 要素の属性です。  
  
-   **MinLocalRequestFreeThreads** httpRuntime 要素の属性です。  
  
-   **MaxConnection**の属性、 \<connectionManagement\>要素 (ネットワーク設定)。  
  
> [!NOTE]
>  **ProcessModel**セクションは Machine.config ファイル内でのみ設定でき、サーバーで実行されているすべての ASP.NET アプリケーションに影響します。  
  
 詳細については、 **processModel** machine.config ファイルの要素が、Microsoft MSDN Web サイトを参照して[ http://go.microsoft.com/fwlink/p/?LinkId=62307](http://go.microsoft.com/fwlink/p/?LinkId=62307)します。  
  
## <a name="registry-setting-that-governs-the-tcp-window-size"></a>TCP ウィンドウ サイズを制御するレジストリ設定  
 次のレジストリ設定である TCP ウィンドウ サイズを制御する量 (バイト単位) での接続中にバッファーできるデータを受信します。 このパラメーターは、最適な値に設定されていない場合は、アダプターのパフォーマンスを悪影響を及ぼす影響ことができます。 このレジストリの TCP ウィンドウ サイズを大きく設定を実装します。  
  
> [!WARNING]
>  レジストリ エディターを正しく使用する場合、オペレーティング システムを再インストールする必要があります深刻な問題が発生する可能性があります。 Microsoft では、レジストリ エディターの使用に起因する問題を解決できることを保証できません。 レジストリ エディターは、ご自身の責任で使用してください。 レジストリを変更する前に常に、レジストリをバックアップし、問題が発生した場合に、バックアップを復元する方法がわかっていることを確認します。  
  
 既定の TCP ウィンドウ サイズを増やすには、次の手順を実行します。  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**regedit.exe**、順にクリックします**ok**レジストリ エディターを起動します。  
  
     移動します**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\\**  
  
2.  で、**パラメーター**キーの値を持つ次の DWORD エントリを作成します。  
  
    |DWORD エントリ|既定値|推奨値|  
    |-----------------|-------------------|-----------------------|  
    |**TcpWindowSize**<br /><br /> この設定は、最大の TCP 受信ウィンドウ サイズが、コンピューターを決定します。 受信ウィンドウには、受信確認を受信せずに送信できるバイト数を指定します。 一般より大きな受信ウィンドウ高帯域幅のネットワーク経由でパフォーマンスが向上します。|17520|イーサネット最大セグメント サイズ (MSS) 値、最大 1460 の倍数に設定します。 Windows スケーリングを使用する場合は、最大 65535 に設定します。|  
  
    > [!NOTE]
    >  これらの変更を有効にするコンピューターを再起動する必要があります。  
  
3.  レジストリ エディターを閉じます。  
  
## <a name="see-also"></a>参照  
 [パフォーマンスおよび容量の計画](../core/performance-and-capacity-planning.md)