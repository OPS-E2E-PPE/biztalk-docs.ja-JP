---
title: スケール アウト受信ホスト |Microsoft ドキュメント
ms.custom: ''
ms.date: 2016-03-17
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, receive adapters
- high availability
- HTTP adapters, scaling
- receive adapters, scaling
- POP3 adapters, scaling
- MSMQ adapters, scaling
- EDI adapters, scaling
- Web services, scaling
- hosts, multiple
- MQSeries adapters, scaling
- adapters, Windows SharePoint Services
- scaling, hosts
- scaling, adapters
- SAP adapters
- FTP adapters
- scaling, receive adapters
- hosts, receiving
- adapters, Web services
- hosts, scaling
- SOAP adapters, scaling
- adapters, scaling
- SQL adapters, scaling
- Web services, adapters
- File adapters, scaling
- clustering
ms.assetid: 94f35426-37fa-4ad2-8e35-d82fdca02262
caps.latest.revision: 54
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b9bc048de978a6dfd7c28505c54cdaaaef64064
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22272554"
---
# <a name="scaled-out-receiving-hosts"></a>受信ホストのスケールアウト
受信機能 (受信場所やパイプラインなど) をつかさどるホストはセキュリティの処理境界として機能し、メッセージのデコードや復号化は、そのホスト内のパイプラインで行われます。 受信ホストの高可用性を確保するためには、それぞれが受信ホストのインスタンスを実行する複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターを用意する必要があります。 受信ホストをスケール アウトすることにより、メッセージ処理の負荷の大きい [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境で可用性を確保できます。 こうすることで、受信ホストが実行するオーケストレーション処理を最小限に抑えながら、さまざまなタイプのメッセージを高速かつ高い信頼性でルーティングさせることができます。  
  
 オーケストレーション処理やメッセージ送信を行うホストから受信ホストを分離することは、環境のセキュリティとスケーラビリティ強化にもつながります。各ホストのセキュリティやスケーラビリティを他のホストと切り離して捉えることができるためです。 たとえば、処理ホストや送信ホストには一切コンピューターを追加することなく、受信ホストにのみ 2 台のコンピューター (ホスト インスタンス) を追加することもできます。  
  
## <a name="multiple-hosts-for-receiving-messages"></a>複数ホストによるメッセージの受信  
 次の図は、受信ホストのインスタンスを実行する 2 台のコンピューターを使用して、受信ホストの高可用性を実現した [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境を示しています。 この図に示されている処理ホストおよび送信ホストの可用性は高くないことに注意してください。  
  
 ![メッセージを受信するための複数のホスト](../core/media/tdi-ha-scalereceive.gif "TDI_HA_ScaleReceive")  
  
 複数の取引先とやりとりする場合や、異なるプロトコルを使用する場合など、環境の規模が大きい場合は、受信機能を複数の受信ホストに分散させることが可能です。 たとえば、アダプターごとにメッセージ受信用のホストを設けたり、メッセージの受信ホストを取引先ごとに用意することもできます。 複数の受信ホストを設ける際、セキュリティの処理境界を作成することで環境の管理性とスケーラビリティは向上しますが、それによって環境の高可用性が実現するというわけではありません。  
  
 環境の高可用性を実現するためには、受信ホストごとに複数のホスト インスタンスを作成する必要があります。 たとえば、3 つの受信ホスト (A、B、C) を用意し、それぞれが異なる会社からのメッセージを受信するように構成したとします。 すべての受信ホストに高可用性を確保するためには、受信ホストごとに複数のホスト インスタンスを作成し、それらを複数のコンピューターに展開する必要があります。 セキュリティの処理境界、管理性、スケーラビリティを損なうことなく、複数のホスト インスタンスを 1 台のコンピューターに割り当てることができるという点に注目してください。  
  
 次の図は、会社ごとに専用の受信ホストが用意された BizTalk Server 環境に対し、3 台のコンピューターを使って高可用性を実現した例です。  
  
 ![受信インスタンス](../core/media/tdi-ha-receiveinstances2.gif "TDI_HA_ReceiveInstances2")  
  
 この構成で高可用性を実現するには、各コンピューターが 3 つのホスト インスタンスを実行します。 3 つの会社の列ごとに 1 つのインスタンス。 各会社に対応するホスト インスタンスには、その会社と通信するための受信場所およびパイプラインが保持されます。 通常動作中は、受信アダプターのスケールアウトに必要な作業 (たとえば、HTTP 用にネットワーク負荷分散を構成するなど) を終えていれば、メッセージの負荷が各ホストの 3 つのホスト インスタンスに分散されます。 1 つのコンピューターの特定のホスト インスタンスで障害が発生した場合、その他の 2 つのコンピューターで実行されているホスト インスタンスが処理を引き継ぐため、サービスの可用性は維持されます。  
  
## <a name="scaling-the-biztalk-server-receive-adapters"></a>BizTalk Server 受信アダプターの拡張  
 受信ホストをスケールアウトして高可用性を確保するという目的において考慮するべき要素はホスト インスタンスだけではありません。環境に実装されているアダプターにも注目する必要があります。 各アダプターには、プロトコルごとの特性があるため、計画と導入もそれぞれのケースによって異なります。 ただし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、すべてのアダプターに対して同じ高可用性ソリューションを適用できます。これは、主にコンピューターとホスト インスタンスの増設を通じて行うことになります。  
  
 受信メッセージを複数のホスト コンピューターに分散して高可用性を確保する際、使用するプロトコルによっては、受信アダプターに追加のメカニズムが必要になる場合もあります。 たとえば、HTTP アダプターまたは SOAP アダプター (Web サービス アダプター) を使用する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ソリューションでは、ネットワーク負荷分散 (NLB) などのロード バランサーを使用して、受信のワークロードを分散する必要があります。 次の表は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で一般的に使用されるアダプターについて、高可用性を実現する上でのガイドラインをまとめたものです。  
  
|**アダプター**|**高可用性のガイドライン**|  
|-----------------|---------------------------------------|  
|HTTP|受信ホストに複数のコンピューターを追加して NLB を構成し、受信メッセージを複数のホスト コンピューターに分散させます。|  
|SOAP|受信ホストに複数のコンピューターを追加して NLB を構成し、受信メッセージを複数のホスト コンピューターに分散させます。|  
|ファイル|受信ホストに複数のコンピューターを追加し、各ホスト コンピューター上で、受信場所として同じファイル フォルダーまたは UNC (汎用名前付け規則) パスが参照されるように構成します。 さらに強固な可用性ソリューションを導入する場合は、UNC パスで指定された場所の可用性を確保します (あるいは信頼性を高める)。|  
|FTP|クラスター化された BizTalk ホストで FTP 受信アダプターを実行するように構成します。 詳細については、次を参照してください。[化されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)です。|  
|POP3|クラスター化された BizTalk ホストで POP3 受信アダプターを実行するように構成します。 詳細については、次を参照してください。[化されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)です。|  
|MSMQ (MSMQ)|MSMQ を構成する受信アダプタは、Windows クラスター化された BizTalk ホストで実行します。 詳細については、次を参照してください。[化されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)です。 場合は、MSMQ 受信場所は、キューを使用してリモート MSMQ サーバーでは、BizTalk ホストをクラスター化する必要はありません。  このシナリオでは、実行、MSMQ は、グループ内の複数の BizTalk コンピューター上のホストを受信します。|  
|MQSeries|このアダプターの受信ホストに複数のコンピューターを追加して、MQSeries for Windows のキュー マネージャーをクラスター化し、MQSeries Server for Windows をクラスター化します。|  
|Windows Sharepoint Services|受信ホストに複数のコンピューターを追加して NLB を構成し、受信メッセージを複数のホスト コンピューターに分散させます。|  
|WCF-NetTcp<br />-Wcf-custom|受信ホストに複数のコンピューターを追加して NLB を構成し、受信メッセージをこれらのホスト コンピューターに分散させます。<br /><br /> - または -<br /><br /> アダプター受信ハンドラーによって使用されるホストをクラスター化します。|  
|-Wcf-netnamedpipe<br />-Wcf-basichttp<br />-Wcf-wshttp<br />-Wcf-customisolated|受信ホストに複数のコンピューターを追加して NLB を構成し、受信メッセージをこれらのホスト コンピューターに分散させます。|  
|WCF-NetMsmq|アダプター受信ハンドラーによって使用されるホストをクラスター化します。|  
  
### <a name="http-adapter"></a>HTTP アダプター  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の HTTP 受信アダプターは、各受信ホスト コンピューター上でホスト インスタンスとして動作する ISAPI (Internet Server API) 拡張 (BTSHTTPReceive.dll) です。 パートナーが HTTP プロトコルを通じて BizTalk Server にメッセージを送信すると、そのメッセージは通常、インターネット インフォメーション サービス (IIS) のインストールされた BizTalk Server コンピューターの特定の URL で受信されます。 BizTalk Server には、受信場所でこの URL をサブスクライブするホスト インスタンスを作成することになります。 この URL に到着したメッセージは、BizTalk Server によって取り出され、メッセージ ボックス データベースに格納されます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、同じ受信ホストのホスト インスタンスを複数作成することにより、HTTP 受信アダプターに高い可用性を確保できます。 これらのホスト インスタンスは、共有可能な特定の URL (NLB を使って受信メッセージを複数の受信ホストに分散させている場合はクラスターの IP アドレス) をサブスクライブします。 これらのホストはすべて、クラスターの仮想 IP アドレスに対してサービスを提供するため、いずれかのクラスター メンバーで障害が発生しても、他のホストがこの IP アドレスに対してサービスを提供できます。  
  
### <a name="soap-adapter-web-services-adapter"></a>SOAP アダプター (Web サービス アダプター)  
 HTTP 受信アダプターとは異なり、Web サービスの受信アダプターには ISAPI 拡張は使用されません。 受信メッセージは、BizTalk Web サービス公開ウィザードで指定された URL を通じて取得されます。 このウィザードでは、Web サービスがエクスポートされ、受信場所として機能する仮想ディレクトリが作成されます。  
  
 Web サービス アダプターに高い可用性を確保するには、受信ホストに複数のコンピューターを追加して NLB を構成し、受信メッセージを複数のホスト コンピューターに分散させます。 クライアントが Web サービス アダプターを通じて BizTalk Server にメッセージを送信すると、NLB は、そのメッセージを負荷の状況に応じて、いずれかの受信ホストに送信します。さらに、そのホスト上で実行されている適切なホスト インスタンスが、メッセージをメッセージ ボックス データベースに保存します。  
  
### <a name="file-adapter"></a>ファイル アダプタ  
 ファイル受信アダプターは、メッセージをファイル フォルダーまたは UNC パスから取得します。 ファイル アダプターが B2B のシナリオで使用されることはあまり多くありません。ファイル アダプターを使用するには、特定のパスに対するアクセス許可を双方が必要としますが、企業がファイル システムを外部と共有することは通常考えられないからです。むしろ、社内で使用されることの多いアダプターです。 受信場所に到着したメッセージを BizTalk Server が取得できるようにファイル受信ハンドラーを構成する (パスをサブスクライブする) 必要があります。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、同じ UNC パスをサブスクライブするホスト インスタンスを複数のホスト コンピューターに作成することで、ファイル受信アダプターに高い可用性を確保できます。 あるホスト コンピューターで実行されているホスト インスタンスにエラーや障害が発生した場合、別のホスト コンピューターで実行されている同じホスト インスタンスが、メッセージを取得し、メッセージ ボックス データベースに保存します。  
  
### <a name="ftp-adapter"></a>FTP アダプタ  
 FTP 受信アダプターを複数のホストで実行するように構成することはできません。FTP 受信アダプターは、FTP プロトコルを使ってファイルを対象システムから取得します。仮に FTP 受信アダプターの複数のインスタンスを実行しようとした場合、同じファイルの複数のコピーが同時に取得されることのないようにファイルをロックする必要があります。しかし、FTP プロトコルにはファイルをロックするという概念がありません。 FTP 受信アダプターは、クラスター化された BizTalk ホストで実行するように構成する必要があります。 詳細については、次を参照してください。[化されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)です。  
  
### <a name="pop3-adapter"></a>POP3 アダプタ  
 POP3 受信アダプターは、データの読み取り先 POP3 サーバーが、同一のメールボックスに対する複数同時接続を許可している場合を除き、複数のホストで実行させることができます。 POP3 アダプターが接続されている POP3 サーバーでメールボックスに対する複数の同時接続が可能な場合、POP3 アダプターの受信ハンドラーを構成してクラスター化された BizTalk ホスト インスタンスで実行することで、POP3 アダプターの高可用性を実現する必要があります。 詳細については、次を参照してください。[化されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)です。  
  
### <a name="msmq-adapter"></a>MSMQ アダプター  
 高可用性を実現するために実行、MSMQ 受信アダプターをクラスター化された MSMQ リソースと同じクラスター グループ内にある Windows クラスター化された BizTalk ホストで。 詳細については、次を参照してください。[化されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)です。  
  
 MSMQ 受信場所の場合は**のみ**BizTalk グループに複数の BizTalk コンピューター上のホストが表示される、MSMQ を実行して、高可用性を実現することができますし、リモートの MSMQ サーバー上の MSMQ キューから受信します。  MSMQ の高可用性を実現するには、Windows のフェールオーバー クラスタ リングを使用して、リモートの MSMQ サーバーを確認する必要があります。  トランザクション キューを使用する場合、リモートの MSMQ サーバーが MSMQ 4.0 (Windows Server 2008) を実行する必要がありますかそれ以降。  
  
### <a name="mqseries-adapter"></a>MQSeries アダプタ  
 Microsoft BizTalk Adapter for MQSeries は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サーバーと IBM MQSeries サーバー間の仲介役として機能します。 このアダプターに高可用性ソリューションを適用するには、MQSeries アダプターを実行するホスト インスタンスを複数用意し、MQSeries for Windows のキュー マネージャーをクラスター化し、さらに、MQSeries Server for Windows をクラスター化する必要があります。 キュー マネージャーのクラスタリングおよび MQSeries Server のクラスタリングの詳細については、IBM WebSphere MQ のドキュメントを参照してください。 MQSeries アダプターの高可用性を実現する方法の詳細については、Microsoft BizTalk Adapter for MQSeries のヘルプで「High Availability (高可用性)」を参照してください。  
  
### <a name="windows-sharepoint-services-adapter"></a>Windows SharePoint Services アダプタ  
 Windows SharePoint Services アダプターは、SharePoint コンピューターにインストールされた Windows SharePoint Services Web サービスを呼び出すことによって、SharePoint からメッセージを取得します。 このアダプターでは、同じメッセージが異なるホスト インスタンスによって処理されてしまうのを防ぐため、チェックアウト メカニズムが使用されています。 そのため、ホスト インスタンスの追加による受信アダプターのスケールアウトが可能となっています。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、同じ HTTP URL (SharePoint の NLB 環境の URL) をサブスクライブする同じ受信場所を、複数のホスト インスタンス上で実行することによって、SharePoint 受信アダプタの高可用性を確保できます。  
  
### <a name="wcf-nettcp-adapter"></a>Wcf-nettcp アダプター  
 NetTcpBinding では IP レイヤー負荷分散手法を使用して負荷分散できます。 しかし、既定では、NetTcpBinding は接続待ち時間を減らすため、TCP 接続をプールします。 このような最適化は負荷分散の基本メカニズムの支障となります。 NetTcpBinding を最適化する主要な構成値は、接続プールの設定の一部であるリース タイムアウトです。 接続プールを使用すると、クライアント接続はファーム内の特定のサーバーに関連付けられます。 接続の有効期間が増えると (リース タイムアウト設定で制御される要素)、ファームのさまざまなサーバー間の負荷分散が不適切になります。 その結果、平均呼び出し時間が増加します。 したがって、負荷分散シナリオで NetTcpBinding を使用する場合、バインディングで使用されるリース タイムアウトの既定値を小さくすることを検討してください。 負荷分散シナリオの最初の値として 30 秒のリース タイムアウトは妥当ですが、最適な値はアプリケーションによって異なります。 チャネル リース タイムアウトおよびその他のトランスポート クォータの詳細については、「トランスポート クォータ」を参照してください。  
  
## <a name="see-also"></a>参照  
 [BizTalk ホストの高可用性](../core/providing-high-availability-for-biztalk-hosts.md)