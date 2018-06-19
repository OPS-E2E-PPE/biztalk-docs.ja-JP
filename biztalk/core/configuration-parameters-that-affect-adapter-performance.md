---
title: アダプターのパフォーマンスに影響する構成パラメーター |Microsoft ドキュメント
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
ms.openlocfilehash: e48eb329a50dda26555e76dd54dd4f4d33cb2c98
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972088"
---
# <a name="configuration-parameters-that-affect-adapter-performance"></a>アダプターのパフォーマンスに影響する構成パラメーター
このセクションでは、BizTalk Server アダプターのパフォーマンスに影響する可能性のある構成設定について説明します。  
  
## <a name="clr-hosting-thread-values-for-the-host"></a>ホスト用の CLR Hosting スレッド値  
 Windows スレッドは、Windows プロセスに使用できる最も基本的な実行可能単位なので、BizTalk ホストのインスタンスに関連付けられた .NET スレッド プールには十分なスレッドを割り当てて、スレッドが不足しないようにすることが重要です。 スレッドが不足した場合、要求された作業を実行できるほど十分なスレッドが存在しないので、パフォーマンスが低下することがあります。 同時に、ホストに関連付けられた .NET スレッド プールに必要以上にスレッドを割り当てないように注意する必要があります。 ホストに関連付けられた .NET スレッド プールに割り当てたスレッドが多すぎると、コンテキストの切り替えが増加する場合があるので、この場合もパフォーマンスが低下することがあります。 Windows カーネルによって実行中の特定のスレッドから別のスレッドへ切り替えられると、CPU 操作のコストが発生し、コンテキストの切り替えが行われます。  
  
 BizTalk Server 設定ダッシュボードで適切な値を設定することにより、BizTalk ホストのインスタンスに関連付けられた .NET スレッド プールで使用できる Windows スレッド数を変更します。 .NET CLR 値の変更の詳細については、次を参照してください。 [.NET CLR 設定を変更する方法](http://msdn.microsoft.com/library/ff629681\(v=BTS.70\).aspx)です。  
  
## <a name="aspnet-settings-that-can-impact-http-or-soap-adapter-performance"></a>HTTP アダプターまたは SOAP アダプターのパフォーマンスに影響する可能性がある ASP.NET 設定  
 次の設定は、HTTP または SOAP アダプターと通信する Web アプリケーションをホストする ASP.NET アプリケーションに適用できます。 これらのパラメーターは、Web アプリケーションをホストしているサーバーの web.config ファイルまたは machine.config ファイルで設定されています。 これらの設定を変更して、HTTP アダプター送信ポートまたは SOAP アダプター送信ポートによって生成される負荷に対処します。 これらの設定の詳細については、次を参照してください。[競合、パフォーマンスの低下、および ASP.NET アプリケーションから Web サービス要求を行うときにデッドロック](http://go.microsoft.com/fwlink/p/?LinkId=196842)です。  
  
|**パラメーター**|**構成ファイルのセクション**|**既定値**|**推奨値**|  
|-------------------|---------------------------------------|-----------------------|---------------------------|  
|**minFreeThreads**<br /><br /> 新しい要求を実行できるようにするフリー スレッドの最小数。 ASP.NET は、処理の完了に追加のスレッドが必要な要求のために、この数のフリー スレッドを維持します。|\<httpRuntime\>|8|88 * Web アプリケーションをホストしているサーバー上のプロセッサ数。|  
|**minFreeLocalRequestFreeThreads**<br /><br /> 新しいローカル要求を実行できるようにするために、ASP.NET で保持できるフリー スレッドの最小数。 処理中にローカル ホストに対して子要求が発行される場合に備えて、ローカル ホストから着信する要求のために、この数のスレッドが予約されます。 これにより、Web サーバーへの再帰的な再入でデッドロックが発生するのを防ぐことができます。|\<httpRuntime\>|4|76 * Web アプリケーションをホストしているサーバー上のプロセッサの数。|  
|**executionTimeout**<br /><br /> ASP.NET によって自動的にシャットダウンされるまでに要求を実行できる最大秒数を示します。|\<httpRuntime\>|90|90|  
|**maxconnection**<br /><br /> 特定の IP アドレスに対して作成できる接続数を決定します。|\<connectionManagement\>|2<br /><br /> これを 2 の値に設定すると、HTTP 1.1 用 IETF RFC の仕様に準拠し、ユーザー シナリオに適しますが、高スループットには適していません。|12 * Web アプリケーションをホストしているサーバー上のプロセッサの数。|  
|**maxWorkerThreads**<br /><br /> プロセスで使用される、CPU ごとのワーカー スレッドの最大数を構成します。|\<processModel\>|20|100**注:** この値が暗黙的に乗算サーバー上のプロセッサの数。|  
|**minWorkerThreads**|\<processModel\>|1|**maxWorkerThreads** /2**注:** minWorkerThreads パラメーターが既定では、構成ファイルではありません。 追加する必要があります。 **注:** この値が暗黙的に乗算サーバー上のプロセッサの数。|  
|**maxIoThreads**<br /><br /> 使用される完了スレッド数を制限するために ASP.NET によって使用されます。|\<processModel\>|20|100<br /><br /> この値にはサーバー上のプロセッサの数が暗黙的に乗算されます。|  
  
 Web サービスをホストしているコンピューターで ASP.NET 2.0 以降を実行し、設定することができるかどうか**autoConfig = true**で最適にするのには、次の設定を自動的に構成を Machine.config ファイルの processModel セクションマシン構成に基づいたパフォーマンス:  
  
-   **MaxWorkerThreads**属性。  
  
-   **MaxIoThreads**属性。  
  
-   **MinFreeThreads** httpRuntime 要素の属性です。  
  
-   **MinLocalRequestFreeThreads** httpRuntime 要素の属性です。  
  
-   **MaxConnection**の属性、 \<connectionManagement\>要素 (ネットワーク設定)。  
  
> [!NOTE]
>  **ProcessModel**セクションでは、Machine.config ファイル内でのみ設定することができ、サーバーで実行されているすべての ASP.NET アプリケーションに影響します。  
  
 詳細については、 **processModel** machine.config ファイルの要素は、Microsoft MSDN Web サイトを参照してください[http://go.microsoft.com/fwlink/p/?LinkId=62307](http://go.microsoft.com/fwlink/p/?LinkId=62307)です。  
  
## <a name="registry-setting-that-governs-the-tcp-window-size"></a>TCP ウィンドウ サイズを管理するレジストリ設定  
 次のレジストリ設定は、接続中にバッファーに格納できる受信データ量 (バイト単位) である TCP ウィンドウ サイズを管理します。 このパラメーターに最適な値を設定していないと、アダプターのパフォーマンスに悪影響を及ぼす可能性があります。 TCP ウィンドウ サイズを増やすには、次のレジストリ設定を実装します。  
  
> [!WARNING]
>  レジストリ エディターの操作を誤ると重大な問題が発生し、オペレーティング システムの再インストールが必要になる場合があります。 レジストリ エディターの不適切な使用によって生じた問題については、解決を保証できません。 レジストリ エディターは、ご自身の責任で使用してください。 レジストリを変更する前に常に、レジストリをバックアップし、問題が発生した場合、バックアップを復元する方法がわかっていることを確認します。  
  
 既定の TCP ウィンドウ サイズを増やすには、次の手順を実行します。  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**regedit.exe**、順にクリック**ok**レジストリ エディターを起動します。  
  
     移動**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\\**  
  
2.  下にある、**パラメーター**キーを指定された値で、次の DWORD エントリを作成します。  
  
    |DWORD エントリ|既定値|推奨値|  
    |-----------------|-------------------|-----------------------|  
    |**TcpWindowSize**<br /><br /> この設定は、コンピューターの最大の TCP 受信ウィンドウ サイズを決定します。 受信ウィンドウでは、送信者が受信確認メッセージを受信せずに送信できるバイト数を指定します。 一般に、広帯域幅のネットワークでは、受信ウィンドウ サイズを大きくするとパフォーマンスが向上します。|17520|イーサネット最大セグメント サイズ (MSS) である 1460 の倍数に設定します。最大値は 64240 です。 Windows スケーリングを使用している場合は、最大値である 65535 に設定します。|  
  
    > [!NOTE]
    >  変更内容を有効にするには、コンピューターを再起動する必要があります。  
  
3.  レジストリ エディターを閉じます。  
  
## <a name="see-also"></a>参照  
 [パフォーマンスおよび容量の計画](../core/performance-and-capacity-planning.md)