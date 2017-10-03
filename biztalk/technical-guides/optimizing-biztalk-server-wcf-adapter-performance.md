---
title: "BizTalk Server WCF アダプターのパフォーマンスを最適化する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2900c845-15be-4466-8fa0-b51b2486842f
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d5ce620e7d9da984081b0f0874985bfe762eeae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-biztalk-server-wcf-adapter-performance"></a>BizTalk Server WCF アダプターのパフォーマンスを最適化します。
このトピックでは、適切な WCF アダプターまたはバインドの種類とさまざまな WCF アダプターの構成オプションを適用するためのガイダンスを選択するための推奨事項を説明します。  
  
## <a name="considerations-when-choosing-which-wcf-adapter-to-use-or-which-wcf-customwcf-customisolated-binding-type-to-use"></a>どの WCF アダプターを使用するかを使用するどの WCF カスタム/Wcf-customisolated バインディングの種類を選択する際の考慮事項  
  
-   厳密にはメッセージのサイズが増えるために必要な場合、メッセージ レベルのセキュリティを使用しません。 これは、順番が最小限に、ソリューションの全体的なスループット。  
  
-   選択する際どの WCF アダプターを使用するかされる WCF のカスタム/Wcf-customisolated**バインドの種類**を使用するのに十分に検討互換性、パフォーマンス、ホスティングのプラットフォーム、セキュリティなど、アプリケーションの要件およびサポートトランスポート。 次のガイドラインは一般に、WCF には適用し、BizTalk Server に固有ではないです。  
  
    -   **BasicHttpBinding** WCF サービスは、WebSphere Web services や ASMX Web サービスを必要とする .NET 1.1 アプリケーションなどのレガシ クライアントをサポートする必要がある場合に使用する必要があります。 メッセージまたはトランスポート セキュリティを必要とする場合、BasicHttpBinding は既定では、すべてのセキュリティを実装されていません、でこのバインディングで、これを明示的に構成してください。 BasicHttpBinding を使用して、ASMX ベースの Web サービスとクライアント、および、WS に準拠するその他のサービスと通信できるエンドポイントを公開する-基本プロファイル 1.1 です。 BasicHttpBinding の既定値は、同じ資格情報を使用しないなどクラシック ASMX Web サービスのトランスポート セキュリティを構成するとします。 BasicHttpBinding では、IIS 7.5 または 7.0 の IIS で WCF サービスをホストすることができます。  
  
    -   **WsHttpBinding**インターネット経由で WCF クライアントで、WCF サービスが呼び出された場合に使用する必要があります。 WsHttpBinding は、ASMX Web サービスを期待するレガシ クライアントをサポートする必要はありませんし、WsHttpBinding では、IIS 7.5 または 7.0 の IIS で WCF サービスをホストすることができます、イントラネットのシナリオに適しています。 レガシ クライアントをサポートする必要がある場合は、BasicHttpBinding を代わりに使用を検討してください。   
        WCF 受信場所を公開するか、または ws-をサポートする送信ポートを採用する必要がある場合、WsHttpBinding を使用する必要があります * Ws-security や WS AtomicTransactions などのプロトコルです。  
  
    -   **NetTcpBinding**イントラネット内のクライアントをサポートする必要がある場合に最適な選択肢がします。 NetTcpBinding をお勧めのイントラネット シナリオ トランスポート パフォーマンスが、使用する重要な場合、および IIS ではなく、Windows サービスでサービスをホストすることができます。 セキュリティで保護された信頼できるバインド環境を提供する場合は、このバインディングを使用します。.NET へのネットワーク コンピューター間通信します。 NetTcpBinding は、Windows サービスまたは IIS 7.5 または 7.0 でホストされる必要がありますに注意してください。  
  
    -   **NetNamedPipeBinding**サービスと同じコンピューターに WCF クライアントをサポートする必要がある場合に使用する必要があります。 このバインディングでは、プロセスの間、同じコンピューターの通信をセキュリティで保護された信頼できるバインド環境を提供します。 名前付きパイプを使用するときに、このバインディングを使用するプロトコル。 Windows サービスまたは IIS 7.5 または 7.0、NetNamedPipeBinding をホストする必要がありますに注意してください。  
  
    -   **NetMsmqBinding**切断されているキューをサポートする必要がある場合に使用する必要があります。 キューは、メッセージ キュー (MSMQ とも呼ばれます) を使用して、トランスポートは、切断操作、失敗の切り分け、および負荷平準化のサポートを有効として提供されます。 クライアントとサービスが同時にオンラインにすることを持っていない場合に、NetMsmqBinding を使用することができます。 受信メッセージの任意の数は、負荷平準化を使用して管理することもできます。 メッセージ キューは、失敗の切り分け、他のメッセージの処理の影響を与えずにメッセージが失敗する可能性をサポートします。 NetMsmqBinding は、Windows サービスまたは IIS 7.5 または 7.0 でホストされる必要がありますに注意してください。  
  
    -   **WsDualHttpBinding**双方向サービスをサポートする必要がある場合に使用する必要があります。 双方向サービスは、したがってはコールバック経由でクライアントに通信するためにサービスの機能を提供する、双方向メッセージ パターンを使用するサービスです。 WsDualHttpBinding は、Windows サービスまたは IIS 7.5 または 7.0 でホストされる必要がありますに注意してください。  
  
## <a name="wcf-binding-comparison"></a>WCF バインディングの比較  
 バインディングは、チャネル スタックを構成するためのメカニズムを提供します。 バインディングでは、トランスポート チャネル、メッセージ エンコーダーで一連のプロトコル チャネルを使用してチャネル スタックを作成するプロセスを作成します。 最も一般的な通信シナリオに対応する構成済み付属している多数の組み込みのバインディングで Windows Communication Foundation が同梱されています。  
  
|クラス名のバインド|[Transport]|メッセージのエンコード|セキュリティ モード|信頼できるメッセージング|トランザクション フロー (既定で無効)|  
|------------------------|---------------|----------------------|-------------------|------------------------|----------------------------------------------|  
|BasicHttpBinding|HTTP|テキスト|なし|サポートされていません|サポートされていません|  
|WSHttpBinding|HTTP|テキスト|メッセージ|Disabled|WS AtomicTransactions|  
|NetTcpBinding|TCP|Binary|[Transport]|Disabled|OleTransactions|  
|NetNamedPipesBinding|名前付きパイプ|Binary|[Transport]|サポートされていません|OleTransactions|  
|NetMsmqBinding|MSMQ (MSMQ)|Binary|メッセージ|サポートされていません|サポートされていません|  
|CustomBinding|決定します。|決定します。|決定します。|決定します。|決定します。|  
  
 通信ニーズに基づく特定のバインディングを選択することができます。 例:  
  
-   **BasicHttpBinding**単純な Web サービスとの相互運用に適しています。 BasicHttpBinding では、トランスポートとメッセージ エンコーディングのテキストに HTTP を使用します。  
  
-   **WSHttpBinding**のさまざまな ws-利用することがより高度な Web サービスとの相互運用に適しています * プロトコルです。  WSHttpBinding は、トランスポートとメッセージ エンコーディングのテキストも HTTP を使用します。  
  
-   **NetTcpBinding**と**NetNamedPipeBinding**向けに設計された効率的なまたはを実行およびその他の WCF アプリケーションとの通信を ant マシン間で同じコンピューターにそれぞれします。  
  
-   使用することが実行時に 1 つまたは複数のカスタム プロトコル チャネルを使用して、最大限の柔軟性を必要がある場合、 **CustomBinding**バインディング要素に、バインディングの作成を決定する可能性を示しています。  
  
> [!NOTE]  
>  バインディングは、応答時間とスループットの観点から異なる特性を持ちます。 そのため、NetTcpBindind と NetNamesPipeBinding 可能な場合は、パフォーマンスを向上する一般的なアドバイスは使用されています。  
  
## <a name="use-the-tcp-transport-and-binary-message-encoding-to-maximize-wcf-adapter-throughput-and-minimize-wcf-adapter-latency"></a>使用して、TCP トランスポートとバイナリ メッセージ エンコーディングを WCF アダプタのスループットを最大化し、WCF アダプターの待機時間を最小限に抑える  
 スループットを最大化可能な場合は、Wcf-nettcp アダプターを使用します。 Wcf-nettcp アダプターは TCP/IP トランスポート プロトコルおよびエンコーディングと比較してその他の WCF のパフォーマンスの向上を一緒に提供するバイナリ メッセージ * アダプター。  
  
 代わりに、または構成できます、Wcf-custom (の受信場所が Wcf-customisolated アダプタ) で、 **customBinding**バインドの種類。 次に、追加、 **binaryMessageEncoding**バインド バイナリ メッセージ エンコーディングを実装する拡張機能と**tcpTransport**バインド、メッセージのトランスポート プロトコルとして TCP/IP を実装する拡張機能です。 この方法は、ことができますを選択し、必要なバインド要素のみを構成して、BizTalk メッセージング エンジンの既定の動作を拡張するカスタム チャネルを作成するために非常に柔軟性があります。 WCF カスタム アダプターを実装する場合、 **customBinding**バインドの種類、スループットを最大化し、待機時間を最小限に抑えるバインド拡張機能の構成パラメーターの値を指定します。  
  
 **ポートの構成値を送信するには。**  
  
|設定|既定値|推奨値|  
|-------------|-------------------|-----------------------|  
|**TcpTransportBindingElement.ConnectionPoolSettings.maxOutboundConnectionsPerEndpoint** - を取得または接続プールにキャッシュされている各エンドポイントの発信接続の最大数を設定します。 これによって、一意のリモート エンドポイントのそれぞれに対してキャッシュされる接続数が制限されます。 この値を超えた場合よりも多くのアクティブなクライアント接続、サービスは、クライアントに応答しないように見える可能性があり、この値は一意の各リモート エンドポイントに対してキャッシュされると予想される接続の最大数に合わせて調整する必要があります。 このプロパティの詳細については、次を参照してください。 [TcpConnectionPoolSettings.MaxOutboundConnectionsPerEndpoint プロパティ](http://go.microsoft.com/fwlink/?LinkId=157737)(http://go.microsoft.com/fwlink/?LinkId=157737) MSDN のです。|10|再試行してください > = 20|  
  
 **ポートの構成値が表示されます。**  
  
|設定|.NET Framework 4 の既定値|.NET Framework 4 の推奨値|.NET Framework 3.5 用の既定値|.NET Framework 3.5 用の推奨値|  
|-------------|----------------------------------------|--------------------------------------------|------------------------------------------|----------------------------------------------|  
|**TcpTransportBindingElement.MaxPendingAccepts**を取得または設定の最大値 - 保留中の非同期受け入れ数、サービスへの着信接続を処理するために使用可能な操作です。 シナリオについては、高レベルの同時接続が開始される、この値は適切でない可能性があります、と共に調整する必要があります、 **MaxPendingConnections**より高いレベルの同時クライアント接続を処理するプロパティしようとします。 使用しないで、サービスをホストしているコンピューターに存在するプロセッサの数より大きい値にこのプロパティを設定するために必要です。 このプロパティの詳細については、次を参照してください。 [ConnectionOrientedTransportBindingElement.MaxPendingAccepts プロパティ](http://go.microsoft.com/fwlink/?LinkId=157738)(http://go.microsoft.com/fwlink/?LinkId=157738) MSDN のです。|1|2 * ProcessorCount|1|再試行してください > = 20|  
|**TcpTransportBindingElement.MaxPendingConnections** - を取得またはサービスでのディスパッチを待機している接続の最大数を設定します。 これにより、ディスパッチを待機している同時クライアント接続の数が制限されます。 この値が低すぎる場合は、クライアント接続の試行をサービスによって拒否される可能性があります。 高すぎる場合は、サービスは負荷が高い期間中に低速またはクライアントに応答しないようにを表示可能性があります。 このプロパティは、すべての容量と速くありませんを実行するサービスを許可する値に設定する必要があります。 スタックの呼び出しで上位層**AcceptDispatch**、ディスパッチ待機接続のキューからの接続が削除されます。 このプロパティの詳細については、次を参照してください。 [ConnectionOrientedTransportBindingElement.MaxPendingConnections プロパティ](http://go.microsoft.com/fwlink/?LinkId=157735)(http://go.microsoft.com/fwlink/?LinkId=157735) MSDN のです。|10|16 * ProcessorCount|10|再試行してください > = 20|  
|**TcpTransportBindingElement.ListenBacklog** - を取得または保留可能なキュー内の接続要求の最大数を設定します。 **ListenBacklog** 「受入保留」の数を記述するソケット レベルのプロパティはキューに置かれた要求。 基になるソケット キューが同時接続の最大数を超えていないことを確認します。 このプロパティの詳細については、次を参照してください。 [TcpTransportBindingElement.ListenBacklog プロパティ](http://go.microsoft.com/fwlink/?LinkId=157734)(http://go.microsoft.com/fwlink/?LinkId=157734) MSDN のです。|10|16 * ProcessorCount|10|再試行してください > = 20|  
  
 **Wcf-custom または Wcf-customisolated 受信場所に ServiceThrottlingBehavior サービス動作を追加し、次の設定を使用します。**  
  
> [!NOTE]  
>  最初に追加する必要がある ServiceThrottlingBehavior サービス動作のいずれの要素を変更することができます、前に、 **serviceThrottling**動作拡張機能を**動作**のタブ、 **WCF カスタム\*トランスポートのプロパティ** ダイアログ ボックス。 ServiceThrottling を動作のリストに追加するには、選択、**動作**のタブ、 **Wcf-custom\*トランスポートのプロパティ**] ダイアログ ボックスを右クリックして**ServiceBehavior** [**動作**、] をクリックして**拡張機能を追加**[ **serviceThrottling**、順にクリック**[ok]**です。 使用可能なプロパティを選択するには、をクリック**ServiceThrottlingElement**し、必要に応じて、プロパティの値を変更します。  
  
|設定|.NET Framework 4 の既定値|.NET Framework 4 の推奨値|.NET Framework 3.5 用の既定値|推奨値を .net Framework 3.5|  
|-------------|----------------------------------------|--------------------------------------------|------------------------------------------|----------------------------------------------|  
|**ServiceThrottlingBehavior.MaxConcurrentCalls** - を取得またはでアクティブに処理されるメッセージの最大数を指定する値を設定、 **ServiceHost**です。 **MaxConcurrentCalls**プロパティでアクティブに処理されるメッセージの最大数を指定する、 **ServiceHost**オブジェクト。 各チャネルは保留中のメッセージの値に対してカウントされない**MaxConcurrentCalls**まで WCF は、その処理を開始します。 このプロパティの詳細については、次を参照してください。 [ServiceThrottlingBehavior.MaxConcurrentCalls](http://go.microsoft.com/fwlink/?LinkId=157838) (http://go.microsoft.com/fwlink/?LinkId=157838) MSDN のです。 BizTalk Wcf-custom と Wcf-customisolated の既定値は受信アダプター **MaxConcurrentCalls**プロパティは**16** CPU ごとです。 **注:** BizTalk Server WCF 受信アダプター Wcf-custom および Wcf-customisolated アダプター公開以外、**同時呼び出しの最大**プロパティを**バインド**のタブ**WCF の\*トランスポートのプロパティ**ダイアログ ボックスをこの動作を構成します。 既定値、**同時呼び出しの最大**動作は**200**です。|16 * ProcessorCount|16 * ProcessorCount|BizTalk Wcf-custom と Wcf-customisolated の 16 では、アダプターが表示されます。<br />~ 200、他の WCF 受信アダプターです。|-再試行してください > Wcf-custom および Wcf-customisolated 受信アダプター用に 200 を = です。<br />-> の 200 を再試行してください、**同時呼び出しの最大**プロパティを**バインド**のタブ、 **WCF -\*トランスポートのプロパティ**BizTalk Server WCF のダイアログ ボックスWcf-custom および Wcf-customisolated アダプター以外のアダプターが表示されます。|  
|**ServiceThrottlingBehavior.maxConcurrentInstances** - を取得または設定の最大数を指定する値**InstanceContext**を一度に実行できるサービス内のオブジェクト。 **MaxConcurrentInstances**プロパティの最大数を指定する**InstanceContext**サービス内のオブジェクト。 間のリレーションシップを留意することが重要、 **MaxConcurrentInstances**プロパティおよび**InstanceContextMode**プロパティです。 場合**InstanceContextMode** PerSession は、結果の値は、セッションの合計数。 場合**InstanceContextMode** PerCall は、結果として得られる値は、同時呼び出しの数。 最大数の中にメッセージを受信した場合**InstanceContext**オブジェクトが既に存在して、まで、メッセージが保持されている、 **InstanceContext**オブジェクトを閉じる。 このプロパティの詳細については、次を参照してください。 [ServiceThrottlingBehavior.MaxConcurrentInstances プロパティ](http://go.microsoft.com/fwlink/?LinkId=157897)(http://go.microsoft.com/fwlink/?LinkId=157897) MSDN のです。 Wcf-custom および Wcf-customisolated 受信アダプター MaxConcurrentInstances プロパティの既定値は**116** CPU ごとです。 **注:** WCF 受信場所はこのクラスは ServiceBehavior (InstanceContextMode としてマークされているためと Microsoft.BizTalk.Adapter.Wcf.Runtime.dll アセンブリに含まれる BizTalkServiceInstance クラスのインスタンスとして実装= = InstanceContextMode.Single、ConcurrencyMode=ConcurrencyMode.Multiple)。 すべての受信要求は、同じシングルトン オブジェクトによって管理され、このパラメーターは無視されます。 受信場所の特定の WCF カスタムに maxConcurrentInstances プロパティを設定、効果はありません、アクティブなインスタンスの数は常に 1 に等しいため。|116 * ProcessorCount|116 * ProcessorCount|26|再試行してください > = 200|  
|**ServiceThrottlingBehavior.MaxConcurrentSessions** - **MaxConcurrentSessions**プロパティを取得またはセッションの最大数を設定、 **ServiceHost**オブジェクトを同時に受け入れることができます. 理解することが重要セッションがここでは、信頼できるセッションをサポートするチャネルのみに限定されません。 各リスナー オブジェクトは保留チャネル セッションの値に対してカウントされない**MaxConcurrentSessions** WCF チャネル セッションを受け入れるし、チャネル セッションのメッセージの処理が開始されるまでです。 このプロパティで最も役に立つのセッションを使用するシナリオです。 このプロパティがクライアントのスレッドの数よりも小さい値に設定されている場合、複数のクライアントからの要求は、同じソケット接続でキューに置かれる可能性があります。 サービスとのセッションを作成していないクライアントからの要求がブロックされます。 ブロックされたままサービスが、他のクライアントと、そのセッションを閉じるまで、サービスで開いているセッションの数に指定された値に達した場合**MaxConcurrentSessions**です。 処理されないクライアント要求が、タイムアウトしたか、およびサービスがセッションを閉じます。 このような状況を回避するのには、クライアントを実行して、スレッド別のアプリケーション ドメインから別のソケット接続で要求メッセージを受け入れるようにを検討してください。 このプロパティの詳細については、次を参照してください。 [ServiceThrottlingBehavior.MaxConcurrentSessions プロパティ](http://go.microsoft.com/fwlink/?LinkID=157864)(http://go.microsoft.com/fwlink/?LinkId=157864) MSDN のです。|100 * ProcessorCount|100 * ProcessorCount|10|再試行してください > = 200|  
  
 ときに変更を適用ポートの構成設定の変更」です。各パラメーターを個別に変更し、パフォーマンスと全体の安定性に変更の効果をテストします。 常に、適切な値を適用するによって異なります、特定のシナリオとします。 値の設定が低すぎると、がスケーラビリティが低下することができます。一方、値の設定が高すぎると、アプリケーションの要件は、コンピューター上の物理リソースの容量を超える可能性があります。 さらに、これらのプロパティは、関連するのでは、首尾一貫した方法で、設定する必要があります。 ServiceThrottlingBehavior を使用して WCF サービスのパフォーマンスを制御する方法の詳細については、次を参照してください。 [WCF サービスのパフォーマンスを制御するのを使用して ServiceThrottlingBehavior](http://go.microsoft.com/fwlink/?LinkId=157908) (http://go.microsoft.com/fwlink/?LinkId=157908) MSDN のです。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のパフォーマンスを最適化します。](../technical-guides/optimizing-biztalk-server-performance.md)