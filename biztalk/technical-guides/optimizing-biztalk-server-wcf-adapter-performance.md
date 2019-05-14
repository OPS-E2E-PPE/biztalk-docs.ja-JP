---
title: BizTalk Server WCF Adapter パフォーマンスの最適化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2900c845-15be-4466-8fa0-b51b2486842f
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 500ad07a47285b2a73b3bf6a768b5a722568807f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393496"
---
# <a name="optimizing-biztalk-server-wcf-adapter-performance"></a>BizTalk Server WCF Adapter パフォーマンスの最適化
このトピックでは、適切な WCF アダプターまたはバインドの種類とさまざまな WCF アダプターの構成オプションを適用するためのガイダンスを選択するための推奨事項を提供します。  
  
## <a name="considerations-when-choosing-which-wcf-adapter-to-use-or-which-wcf-customwcf-customisolated-binding-type-to-use"></a>どの WCF アダプターを使用するかを使用するどの WCF カスタム WCF CustomIsolated バインドの種類を選択する際の考慮事項  
  
-   厳密にはメッセージのサイズが増えるために必要な場合、メッセージ レベルのセキュリティを使わないでください。 これは、さらに、ソリューションの全体的なスループットを最小限です。  
  
-   どの WCF アダプターを使用する、またはカスタム/WCF-Wcf-customisolated を選択するときに**バインドの種類**を使用する十分に検討、アプリケーションの要件など、互換性、パフォーマンス、ホスティング プラットフォーム、セキュリティ、およびサポートトランスポート。 次のガイドラインは一般に、WCF に適用できますし、BizTalk Server に固有ではないです。  
  
    -   **BasicHttpBinding** WCF サービスは、WebSphere の Web サービスや ASMX Web サービスを必要とする .NET 1.1 アプリケーションなどのレガシ クライアントをサポートする必要がある場合に使用する必要があります。 メッセージまたはトランスポート セキュリティを必要とする場合、BasicHttpBinding は、既定では、任意のセキュリティを実装できません、ために、明示的にこのバインディングで構成する必要があります。 BasicHttpBinding を使用して、ASMX ベースの Web サービスとクライアント、および、WS に準拠するその他のサービスと通信できるエンドポイントを公開する-基本プロファイル 1.1。 トランスポート セキュリティを構成するときに BasicHttpBinding の既定値は、同じ資格情報を使用しないなどの従来の ASMX Web サービス。 BasicHttpBinding を使用すると、IIS 7.5 または 7.0 の IIS で WCF サービスをホストできます。  
  
    -   **WsHttpBinding**インターネット経由で WCF クライアントが WCF サービスが呼び出された場合に使用する必要があります。 WsHttpBinding は、ASMX Web サービスを期待する従来のクライアントをサポートする必要はありませんし、WsHttpBinding では、IIS 7.5 または 7.0 の IIS で WCF サービスをホストできます。 インターネットのシナリオに最適です。 レガシ クライアントをサポートする場合は、BasicHttpBinding を使用する代わりに検討してください。   
        WCF 受信場所の公開または ws-をサポートする送信ポートを採用する必要があるときに、WsHttpBinding を使用する必要があります * Ws-security や WS AtomicTransactions などのプロトコル。  
  
    -   **NetTcpBinding**優れた選択肢は、イントラネット内のクライアントをサポートする必要がある場合。 NetTcpBinding では、イントラネットのシナリオに適しては転送のパフォーマンスが、重要な場合ありの代わりに IIS での Windows サービスでサービスをホストすることができますできます。 セキュリティで保護された信頼できるバインド環境を提供する場合は、このバインディングを使用します.NET へのネットワーク コンピューター間の通信。 NetTcpBinding は、Windows サービスまたは IIS 7.5 または 7.0 でホストされる必要がありますに注意してください。  
  
    -   **NetNamedPipeBinding**サービスと同じコンピューターに WCF クライアントをサポートする必要がある場合に使用する必要があります。 このバインディングでは、プロセスの間、同じコンピューターの通信をセキュリティで保護された信頼できるバインド環境を提供します。 このバインドは、名前付きパイプを使用する場合に使用してプロトコル。 Windows サービスまたは IIS 7.5 または 7.0 に対応した NetNamedPipeBinding をホストする必要がありますに注意してください。  
  
    -   **NetMsmqBinding**切断されているキューをサポートする必要がある場合に使用する必要があります。 キューは、メッセージ キュー (MSMQ とも呼ばれます) を使用して、トランスポートは、非接続操作モード、障害の分離、負荷平準化をサポートできるようにとして提供されます。 クライアントとサービスが同時にオンラインであるがない場合に、NetMsmqBinding を使用できます。 負荷平準化を使用して、受信メッセージの任意の数を管理することもできます。 メッセージ キューは、障害の分離を使用して、他のメッセージの処理の影響を与えずにメッセージが失敗する場所をサポートします。 NetMsmqBinding は、Windows サービスまたは IIS 7.5 または 7.0 でホストされる必要がありますに注意してください。  
  
    -   **WsDualHttpBinding**双方向サービスをサポートする必要がある場合に使用する必要があります。 双方向サービスは、コールバックを使用してクライアントに通信するためにサービスの機能を提供するための双方向メッセージ パターンを使用するサービスです。 WsDualHttpBinding は、Windows サービスまたは IIS 7.5 または 7.0 でホストされる必要がありますに注意してください。  
  
## <a name="wcf-binding-comparison"></a>WCF バインドの比較  
 バインドは、チャネル スタックを構成するためのメカニズムを提供します。 バインディングはトランスポート チャネル、メッセージ エンコーダー、および一連のプロトコル チャネルを使用してチャネル スタックを構築するプロセスを作成します。 Windows Communication Foundation は、最も一般的な通信シナリオに対処する事前構成済みの付属している多数の組み込みバインドで出荷されます。  
  
|クラス名のバインド|[Transport]|メッセージのエンコード|セキュリティ モード|信頼性の高いメッセージング|トランザクション フロー (既定で無効)|  
|------------------------|---------------|----------------------|-------------------|------------------------|----------------------------------------------|  
|BasicHttpBinding|HTTP|テキスト|なし|サポートされていません|サポートされていません|  
|WSHttpBinding|HTTP|テキスト|メッセージ|Disabled|WS AtomicTransactions|  
|NetTcpBinding|TCP|Binary|[Transport]|Disabled|OleTransactions|  
|NetNamedPipesBinding|名前付きパイプ|Binary|[Transport]|サポートされていません|OleTransactions|  
|NetMsmqBinding|MSMQ (MSMQ)|Binary|メッセージ|サポートされていません|サポートされていません|  
|customBinding|決定します。|決定します。|決定します。|決定します。|決定します。|  
  
 通信ニーズに基づいて特定のバインディングを選択することができます。 以下に例を示します。  
  
-   **BasicHttpBinding**単純な Web サービスとの相互運用に適しています。 BasicHttpBinding では、HTTP をトランスポートとメッセージ エンコーディングにテキストを使用します。  
  
-   **WSHttpBinding**のさまざまな ws-利用することがより高度な Web サービスとの相互運用に適しています * プロトコル。  WSHttpBinding では、トランスポートとメッセージ エンコーディングにテキストを HTTP も使用します。  
  
-   **NetTcpBinding**と**NetNamedPipeBinding**用に設計された効率的なまたはを実行およびその他の WCF アプリケーションとの通信を ant マシン間で同じコンピューターにそれぞれします。  
  
-   使用することが実行時に 1 つまたは複数のカスタム プロトコル チャネルを使用して、最大限の柔軟性を必要がある場合、 **CustomBinding**バインド要素、バインドの作成を決定する可能性を提供します。  
  
> [!NOTE]  
>  バインドには、応答時間とスループットに関してさまざまな特性があります。 そのため、NetTcpBindind と NetNamesPipeBinding 可能であればパフォーマンスを向上する一般的なアドバイスが使用しています。  
  
## <a name="use-the-tcp-transport-and-binary-message-encoding-to-maximize-wcf-adapter-throughput-and-minimize-wcf-adapter-latency"></a>TCP トランスポートとバイナリ メッセージを WCF アダプターのスループットを最大化し、WCF アダプターの待機時間を最小限に抑えるエンコーディングを使用して、  
 スループットを最大化するときに Wcf-nettcp アダプターを使用します。 TCP/IP トランスポート プロトコルおよびバイナリ メッセージ エンコーディングと比較してその他の WCF - パフォーマンスの向上をまとめて提供する、Wcf-nettcp アダプターを使用して * アダプター。  
  
 Wcf-custom (または Wcf-customisolated アダプターの受信場所) を構成にする代わりに、 **customBinding**バインドの種類。 次に、追加、 **binaryMessageEncoding**バインド バイナリ メッセージ エンコーディングを実装する拡張機能と**tcpTransport**バインドのメッセージのトランスポート プロトコルとして TCP/IP を実装する拡張機能。 このアプローチを選択し、必要なバインド要素のみを構成して、BizTalk メッセージング エンジンの既定の動作を拡張するカスタム チャネルを作成することを許容するため非常に柔軟性があります。 WCF カスタム アダプターを実装する場合、 **customBinding**バインドの種類、バインド拡張機能の構成パラメーターをスループットを最大化し、待機時間を最小限に抑えるのため、これらの値を指定します。  
  
 **送信ポートの構成値。**  
  
|設定|既定値|推奨値|  
|-------------|-------------------|-----------------------|  
|**TcpTransportBindingElement.ConnectionPoolSettings.maxOutboundConnectionsPerEndpoint** - を取得または接続プールにキャッシュされている各エンドポイントの発信接続の最大数を設定します。 これによって、一意のリモート エンドポイントのそれぞれに対してキャッシュされる接続数が制限されます。 アクティブなクライアント接続することでこの値を超えた場合、サービスが、クライアントに応答しないように表示され、予想される一意の各リモート エンドポイントに対してキャッシュされる接続の最大数に対応するために、この値を調整する必要があります。 このプロパティの詳細については、次を参照してください。 [TcpConnectionPoolSettings.MaxOutboundConnectionsPerEndpoint プロパティ](http://go.microsoft.com/fwlink/?LinkId=157737)(http://go.microsoft.com/fwlink/?LinkId=157737) msdn です。|10|お試しください > = 20|  
  
 **ポートの構成値が表示されます。**  
  
|設定|.NET Framework 4 の既定値|.NET Framework 4 の推奨値|.NET Framework 3.5 用の既定値|.NET Framework 3.5 の推奨値|  
|-------------|----------------------------------------|--------------------------------------------|------------------------------------------|----------------------------------------------|  
|**TcpTransportBindingElement.MaxPendingAccepts** - を取得または設定の最大保留中の非同期受け入れ操作数、サービスへの着信接続を処理するために使用できます。 高レベルの同時接続が開始される場合は、この値は十分でない可能性があります、と共に調整する必要があります、 **MaxPendingConnections**より高いレベルの同時クライアント接続を処理するためにプロパティしようとします。 このプロパティをサービスをホストするコンピューターに存在するプロセッサの数より大きい値に設定する必要します。 このプロパティの詳細については、次を参照してください。 [ConnectionOrientedTransportBindingElement.MaxPendingAccepts プロパティ](http://go.microsoft.com/fwlink/?LinkId=157738)(http://go.microsoft.com/fwlink/?LinkId=157738) msdn です。|1|2 * は ProcessorCount|1|お試しください > = 20|  
|**TcpTransportBindingElement.MaxPendingConnections** - を取得またはサービスでのディスパッチを待機している接続の最大数を設定します。 これにより、ディスパッチを待機している同時クライアント接続の数が制限されます。 この値が小さすぎる場合は、クライアント接続の試行がサービスによって拒否されます。 高すぎる場合は、サービスは負荷が高い期間中またはクライアントに応答が遅いを表示可能性があります。 このプロパティは、サービスを実行し、最大容量、それを超えないようにする値に設定する必要があります。 スタックの上位層**AcceptDispatch**、その接続は、ディスパッチ待機接続のキューから削除します。 このプロパティの詳細については、次を参照してください。 [ConnectionOrientedTransportBindingElement.MaxPendingConnections プロパティ](http://go.microsoft.com/fwlink/?LinkId=157735)(http://go.microsoft.com/fwlink/?LinkId=157735) msdn です。|10|16 * は ProcessorCount|10|お試しください > = 20|  
|**TcpTransportBindingElement.ListenBacklog** - を取得または保留可能なキュー内の接続要求の最大数を設定します。 **ListenBacklog** 「受入保留」の数を記述するソケット レベルのプロパティは、キューに入れられる要求。 基になるソケット キューが同時接続の最大数を超えていないことを確認します。 このプロパティの詳細については、次を参照してください。 [TcpTransportBindingElement.ListenBacklog プロパティ](http://go.microsoft.com/fwlink/?LinkId=157734)(http://go.microsoft.com/fwlink/?LinkId=157734) msdn です。|10|16 * は ProcessorCount|10|お試しください > = 20|  
  
 **Wcf-custom または Wcf-customisolated 受信場所にサービスのための ServiceThrottlingBehavior の動作を追加し、次の設定を使用します。**  
  
> [!NOTE]  
>  最初に追加する必要があるための ServiceThrottlingBehavior のサービス動作のいずれの要素を変更することができます、前に、 **serviceThrottling**する動作拡張機能、**動作**のタブ、 **WCF カスタム\*トランスポートのプロパティ** ダイアログ ボックス。 ServiceThrottling を動作のリストに追加するには、選択、**動作**のタブ、 **Wcf-custom\*トランスポートのプロパティ**ダイアログ ボックスで、右クリックして**ServiceBehavior** [**動作**、] をクリックして**拡張機能の追加**を選択します**serviceThrottling**、順にクリックします**OK**します。 使用可能なプロパティを選択するには、をクリック**ServiceThrottlingElement**必要に応じて、プロパティの値を変更します。  
  
|設定|.NET Framework 4 の既定値|.NET Framework 4 の推奨値|.NET Framework 3.5 用の既定値|推奨値を .net Framework 3.5|  
|-------------|----------------------------------------|--------------------------------------------|------------------------------------------|----------------------------------------------|  
|**ServiceThrottlingBehavior.MaxConcurrentCalls** - を取得または設定でアクティブに処理されるメッセージの最大数を指定する値を**ServiceHost**します。 **MaxConcurrentCalls**プロパティでアクティブに処理されるメッセージの最大数を指定します、 **ServiceHost**オブジェクト。 各チャネルがメッセージの値に対してカウントされませんが保留中のいずれかを指定できます**MaxConcurrentCalls**まで WCF は、その処理を開始します。 このプロパティの詳細については、次を参照してください。 [ServiceThrottlingBehavior.MaxConcurrentCalls](http://go.microsoft.com/fwlink/?LinkId=157838) (http://go.microsoft.com/fwlink/?LinkId=157838) msdn です。 BizTalk Wcf-custom と Wcf-customisolated の既定値は受信アダプター **MaxConcurrentCalls**プロパティは**16** CPU ごと。 **注:** BizTalk Server WCF 受信アダプター以外は、Wcf-custom および Wcf-customisolated アダプター公開、**同時呼び出しの最大**プロパティを**バインド**のタブ、 **WCF\*トランスポートのプロパティ** ダイアログ ボックスに、この動作を構成します。 既定値、**同時呼び出しの最大**動作は**200**します。|16 * は ProcessorCount|16 * は ProcessorCount|-16 BizTalk Wcf-custom と Wcf-customisolated の受信アダプターです。<br />~ 200、他の WCF 受信アダプターです。|-お試しください > Wcf-custom および Wcf-customisolated 受信アダプター用に 200 を = です。<br />-> の 200 を再試行してください、**同時呼び出しの最大**プロパティを**バインド**のタブ、 **wcf-\*トランスポートのプロパティ**BizTalk Server WCF の ダイアログ ボックスWcf-custom および Wcf-customisolated アダプター以外のアダプターが表示されます。|  
|**ServiceThrottlingBehavior.maxConcurrentInstances** - を取得または設定の最大数を指定する値**InstanceContext**一度に実行できるサービス内のオブジェクト。 **MaxConcurrentInstances**プロパティの最大数を指定する**InstanceContext**サービス内のオブジェクト。 間のリレーションシップに留意することが重要、 **MaxConcurrentInstances**プロパティおよび**InstanceContextMode**プロパティ。 場合**InstanceContextMode** PerSession には、結果の値はセッションの合計数。 場合**InstanceContextMode** PerCall は、結果として得られる値は、同時呼び出しの数。 最大数の中にメッセージを受信した場合**InstanceContext**オブジェクトが既に存在、まで、メッセージが保持されている、 **InstanceContext**オブジェクトを閉じる。 このプロパティの詳細については、次を参照してください。 [ServiceThrottlingBehavior.MaxConcurrentInstances プロパティ](http://go.microsoft.com/fwlink/?LinkId=157897)(http://go.microsoft.com/fwlink/?LinkId=157897) msdn です。 Wcf-custom および Wcf-customisolated 受信アダプター MaxConcurrentInstances プロパティの既定値は**116** CPU ごと。 **注:** WCF 受信場所はこのクラスが ServiceBehavior(InstanceContextMode= としてマークされているためと Microsoft.BizTalk.Adapter.Wcf.Runtime.dll アセンブリに含まれる BizTalkServiceInstance クラスのインスタンスとして実装します。InstanceContextMode.Single、ConcurrencyMode=ConcurrencyMode.Multiple)。 すべての着信要求は同じシングルトン オブジェクトによって管理され、このパラメーターは無視されます。 受信場所の特定の WCF カスタムに maxConcurrentInstances プロパティを設定できるようにも何も起こりません、アクティブなインスタンスの数は常に 1 に等しいためです。|116 * は ProcessorCount|116 * は ProcessorCount|26|お試しください > = 200|  
|**ServiceThrottlingBehavior.MaxConcurrentSessions** - **MaxConcurrentSessions**プロパティを取得またはセッションの最大数を設定、 **ServiceHost**オブジェクトが同時に受け入れることができます。 理解することが重要、セッションではここでは信頼できるセッションをサポートするチャネルのみに限定されません。 各リスナー オブジェクトは、保留中の値に対してカウントされませんチャネル セッションのいずれかを指定できます**MaxConcurrentSessions**まで WCF チャネル セッションを受け入れるし、チャネル セッションのメッセージの処理を開始します。 このプロパティで最も役に立つは、セッションを使用するシナリオ。 このプロパティがクライアント スレッドの数よりも小さい値に設定されている場合、複数のクライアントからの要求は、同じソケット接続でキューに登録を取得可能性があります。 サービスでセッションを作成していないクライアントからの要求がブロックされます。 これらはブロックされたまま、サービスの他のクライアントとのセッションが閉じるまで、サービスで開いているセッションの数に指定された値に達した場合**MaxConcurrentSessions**します。 提供されないクライアントの要求が、タイムアウトしたか、およびサービスがセッションを閉じます。 このような状況を避けるためには、クライアントを実行するスレッドの異なるアプリケーション ドメインから別のソケット接続で要求メッセージを受け入れるように検討してください。 このプロパティの詳細については、次を参照してください。 [ServiceThrottlingBehavior.MaxConcurrentSessions プロパティ](http://go.microsoft.com/fwlink/?LinkID=157864)(http://go.microsoft.com/fwlink/?LinkId=157864) msdn です。|100 * は ProcessorCount|100 * は ProcessorCount|10|お試しください > = 200|  
  
 ポートの構成設定の変更が適用されます、系統的; 変更各パラメーターを個別に変更し、パフォーマンスと全体的な安定性の変更の効果をテストします。 常に、適切な値を適用するか、特定のシナリオに依存します。 値の設定が低すぎる場合、スケーラビリティを削減できます。一方、値の設定が高すぎると、アプリケーションの要件は、コンピューター上の物理リソースの容量を超える可能性があります。 さらに、これらのプロパティが関連するのでは、首尾一貫した方法で、設定する必要があります。 WCF サービスのパフォーマンスを制御するための ServiceThrottlingBehavior の使用に関する詳細については、次を参照してください。[パフォーマンスを制御する WCF サービスを使用して ServiceThrottlingBehavior](http://go.microsoft.com/fwlink/?LinkId=157908) (http://go.microsoft.com/fwlink/?LinkId=157908) msdn です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server パフォーマンスの最適化](../technical-guides/optimizing-biztalk-server-performance.md)