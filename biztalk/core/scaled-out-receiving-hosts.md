---
title: 受信ホスト スケール アウト |Microsoft Docs
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
ms.openlocfilehash: 5f66b1966814be2784b2372135ac0c042a0746a7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309330"
---
# <a name="scaled-out-receiving-hosts"></a>受信ホスト スケール アウト
受信機能 (受信場所やパイプラインなど) をつかさどるホストはセキュリティの処理境界として機能し、メッセージのデコードや復号化は、そのホスト内のパイプラインで行われます。 受信ホストの可用性を高めるには、2 つ以上をいる必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]各受信ホストのインスタンスを実行しているコンピューター。 スケール アウトは、受信ホストでの可用性を保証できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]はメッセージングの集中的に使用するデプロイ。 これらの展開可能性があります最小オーケストレーション処理を実行しますが、高速かつ高い信頼性でさまざまな種類の多数のメッセージをルーティングすることができます。  
  
 受信側のオーケストレーションを処理し、セキュリティで保護およびその他のホストとは無関係に、各ホストをスケールできるため、メッセージを送信するホストからホストを分離することで、環境内のセキュリティとスケーラビリティを強化できます。 たとえば、せず、処理にすべてのコンピューターを追加するか、送信ホスト、受信ホストに 2 台のコンピューター (ホスト インスタンス) を追加できます。  
  
## <a name="multiple-hosts-for-receiving-messages"></a>メッセージを受信するための複数のホスト  
 次に示します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信ホストのインスタンスを実行する 2 つのコンピューターを使用して、受信ホストの高可用性を提供するデプロイ。 この図では、処理ホストおよび送信ホストできないが高可用性に注意してください。  
  
 ![メッセージを受信するための複数のホスト](../core/media/tdi-ha-scalereceive.gif "TDI_HA_ScaleReceive")  
  
 大規模な展開での複数の取引を処理するシナリオとさまざまなプロトコルを使用する場合のシナリオでは、受信側の機能を複数の受信ホストの間で分散できます。 たとえば、アダプターごとに、メッセージまたは別のパートナーからメッセージを受信するための別のホストを受信するためホストを作成することができます。 複数の受信ホストを作成する場合は、セキュリティ境界を作成および管理性と、環境内のスケーラビリティが容易になりますただし、これは行いません環境高可用性。  
  
 環境を高可用性にするには、必要があります、作成した受信ホストごとに 2 つ以上のホスト インスタンスを作成します。 たとえば、ことができますを作成する 3 つの異なる受信ホスト (A、B、および C) を次の 3 つの異なる会社からメッセージを受信します。 これらのホストの高可用性には 2 つまたは複数のコンピューターでのこれらのホストの各ホスト インスタンスを作成します。 各ホストのインスタンス セキュリティの境界や管理容易性、スケーラビリティを失うことがなく 1 台のコンピューターに配置できますに注意してください。  
  
 次の図は、さまざまな企業からメッセージを受信する専用のホストで 3 台のコンピューターの高可用性 BizTalk Server 環境を示します。  
  
 ![受信インスタンス](../core/media/tdi-ha-receiveinstances2.gif "TDI_HA_ReceiveInstances2")  
  
 この構成で高可用性を実現するには、各コンピューターには 3 つのホスト インスタンスが実行されます。 次の 3 つの会社の 1 つのインスタンス。 各サイトのホスト インスタンスには、受信場所およびその会社と通信するためにパイプラインが含まれます。 通常の操作中にスケール アウト (たとえば、ネットワーク負荷分散を HTTP を構成する場合)、受信アダプターの前に必要な作業を行う場合に限りメッセージング負荷が分散されて、3 つのホスト インスタンス間でホストごとにします。 1 台のコンピューター上のホスト インスタンスが失敗した場合、他の 2 台のコンピューターで実行されているホスト インスタンスは冗長性を提供し、サービスの可用性を維持します。  
  
## <a name="scaling-the-biztalk-server-receive-adapters"></a>受信アダプターの BizTalk Server の拡張  
 ホストのインスタンス以外の拡張機能と、受信ホストの高可用性を実現するプロセスは、展開で実装されている特定のアダプターによっても異なります。 各アダプターでは、各ケースで異なる計画と展開を作成するプロトコル固有の特性を持ちます。 ただし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主に、追加のコンピューターとホスト インスタンスでのすべてのアダプターと同じ高可用性ソリューションを適用することができます。  
  
 使用されている特定のプロトコルによっては、いくつかの受信アダプターの高可用性を提供する複数のホスト コンピューター間で受信メッセージを配布するために追加のメカニズムが必要です。 たとえば、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (それ以外の場合は、Web サービス アダプターと呼ばれます)、HTTP または SOAP アダプターを使用するソリューションがロード バランサーなどネットワーク負荷分散 (NLB) の受信側の負荷を分散する必要があります。 次の表は、の最も一般的なアダプターの高可用性のガイドラインをまとめたものです。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
|**アダプター**|**高可用性のガイドライン**|  
|-----------------|---------------------------------------|  
|HTTP|受信ホストに複数のコンピューターを追加し、受信メッセージを複数のホスト コンピューターに分散する NLB を構成します。|  
|SOAP|受信ホストに複数のコンピューターを追加し、受信メッセージを複数のホスト コンピューターに分散する NLB を構成します。|  
|ファイル|同じファイル フォルダーまたは汎用名前付け規則 (UNC) パスを参照する各ホスト コンピューター上の受信場所で受信ホストに複数のコンピューターを追加します。 高可用性の完全なソリューションには、UNC パスをポイントするファイルの場所が高可用性 (または少なくとも信頼性の高い) であることを確認の操作を行う必要があります。|  
|FTP|構成、FTP 受信アダプタは、クラスター化された BizTalk ホストで実行します。 詳細については、次を参照してください。[されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)します。|  
|POP3|構成、POP3 受信アダプタは、クラスター化された BizTalk ホストで実行します。 詳細については、次を参照してください。[されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)します。|  
|MSMQ (MSMQ)|MSMQ を構成する受信アダプタは、Windows クラスター化された BizTalk ホストで実行します。 詳細については、次を参照してください。[されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)します。 場合は、MSMQ 受信場所がリモート MSMQ サーバー上のキューを使用して、BizTalk ホストをクラスター化する必要はありません。  このシナリオでは、実行、MSMQ は、グループ内の複数の BizTalk コンピューター上のホストを受け取ります。|  
|MQSeries|このアダプターの受信ホストに複数のコンピューター MQSeries for Windows でクラスター化されたキュー マネージャーを使用し、MQSeries Server を Windows のクラスターを追加します。|  
|Windows Sharepoint Services|受信ホストに複数のコンピューターを追加し、受信メッセージを複数のホスト コンピューターに分散する NLB を構成します。|  
|-   WCF-NetTcp<br />WCF-カスタム|受信ホストに複数のコンピューターを追加し、これらのホスト コンピューターで受信メッセージを配布するために NLB を構成します。<br /><br /> - または -<br /><br /> アダプターによって使用されるホスト クラスターには、ハンドラーが表示されます。|  
|-Wcf-netnamedpipe<br />-Wcf-basichttp<br />-Wcf-wshttp<br />-Wcf-customisolated|受信ホストに複数のコンピューターを追加し、これらのホスト コンピューターで受信メッセージを配布するために NLB を構成します。|  
|WCF-NetMsmq|アダプターによって使用されるホスト クラスターには、ハンドラーが表示されます。|  
  
### <a name="http-adapter"></a>HTTP アダプター  
 HTTP 受信アダプターで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]各受信ホスト コンピューター上のホスト インスタンスとして実行される Internet Server API (ISAPI) 拡張 (BTSHTTPReceive.dll) です。 パートナーは、HTTP プロトコルを通じて BizTalk Server にメッセージを送信するときに、メッセージ通常に到着する特定の URL を BizTalk Server コンピューターにインターネット インフォメーション サービス (IIS) がインストールされています。 この URL をサブスクライブする受信場所には、BizTalk Server でホスト インスタンスを作成します。 URL にメッセージを受信する BizTalk Server はそれらを取得し、取り出され、メッセージ ボックス データベース。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 高可用性は、HTTP 受信アダプターを同じ受信ホストの複数のホスト インスタンスを作成することができます。 受信ホストの複数の受信メッセージを分散する NLB を使用している場合、クラスター IP アドレス、これらのホスト インスタンスの共有できる特定の URL にサブスクライブします。 この IP アドレスを使用他のユーザーが失敗すると、1 つのクラスター メンバーもできるように、それらすべてのホストは、クラスターの仮想 IP アドレスを提供する機能します。  
  
### <a name="soap-adapter-web-services-adapter"></a>SOAP アダプター (Web サービス アダプター)  
 HTTP 受信アダプターとは異なり Web サービスの受信アダプターでは、ISAPI 拡張機能は関与しません。 BizTalk Web サービス公開ウィザードを使用して、指定した URL からの受信メッセージを受信します。 このウィザードでは、Web サービスをエクスポートして、受信場所として機能する仮想ディレクトリを作成します。  
  
 Web サービス アダプターの高可用性を実現するには、受信ホストに複数のコンピューターを追加し、NLB を使用して受信メッセージを配布します。 クライアントは、Web サービス アダプターを通じて BizTalk Server にメッセージを送信するときにメッセージを受信側のホストの 1 つの NLB 負荷を分散し、ホストで実行されている適切なホスト インスタンスには、メッセージ ボックス データベースにメッセージが引き続き発生すます。  
  
### <a name="file-adapter"></a>ファイル アダプター  
 ファイルでは、ファイル フォルダーまたは UNC パスからアダプターを取得しますメッセージを受信します。 このアダプターは、両当事者が、パスへのアクセス許可を必要と、企業を通常のファイル システム共有しないために頻繁に企業間取引シナリオでの代わりに企業内で使用されます。 受信場所に到着したときに、BizTalk Server がメッセージを取得するために、パスをサブスクライブするファイル受信ハンドラーを構成します。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 同じ UNC パスをサブスクライブする複数のホスト コンピューターでホスト インスタンスを作成することで、ファイル受信アダプターの高可用性を提供します。 1 つのホスト コンピューターで実行されているホスト インスタンスには、エラーまたは失敗が発生すると、別のホスト コンピューターで実行されている同じホスト インスタンスがメッセージを取得し、メッセージ ボックス データベースに保存できます。  
  
### <a name="ftp-adapter"></a>FTP アダプター  
 FTP 受信アダプターが FTP 受信アダプターの使用は、ターゲット システムからファイルを取得する FTP プロトコルは、FTP プロトコルにロックして、複数ファイルの概念がないため、複数のホストで実行する構成されていませんが、同一のコピーファイルが同時に取得されない受信アダプター、FTP の複数のインスタンスを実行している場合。 FTP 受信アダプターは、クラスター化された BizTalk ホストで実行するように構成する必要があります。 詳細については、次を参照してください。[されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)します。  
  
### <a name="pop3-adapter"></a>POP3 アダプター  
 POP3 受信アダプターは、アダプターが読み込みを行う POP3 サーバーが同一のメールボックスに対する複数の同時接続が許可されない限り、複数のホストで実行するように構成できます。 POP3 アダプターに接続されている POP3 サーバーでメールボックスに対する複数の同時接続を許可される場合、POP3 アダプターの高可用性達成しなければならない POP3 アダプターの受信されている BizTalk ホスト インスタンスで実行するハンドラーを構成することでクラスター化します。 詳細については、次を参照してください。[されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)します。  
  
### <a name="msmq-adapter"></a>MSMQ アダプター  
 高可用性を実現するために実行、MSMQ 受信アダプターをクラスター化された MSMQ リソースと同じクラスター グループ内にある Windows クラスター化された BizTalk ホストで。 詳細については、次を参照してください。[されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)します。  
  
 MSMQ 受信場所が**のみ**BizTalk グループに複数の BizTalk コンピューター上のホストが表示される、MSMQ を実行して高可用性を実現することができますし、リモートの MSMQ サーバー上の MSMQ キューから受信します。  MSMQ の高可用性を実現するには、リモート MSMQ サーバーが Windows でフェールオーバー クラスタ リングを使用することを確認する必要があります。  トランザクション キューを使用して場合リモート MSMQ サーバーが MSMQ 4.0 (Windows Server 2008) を実行する必要がありますまたはそれ以降。  
  
### <a name="mqseries-adapter"></a>MQSeries アダプター  
 Microsoft BizTalk Adapter for MQSeries の間のブリッジとして機能します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と IBM MQSeries サーバー。 このアダプターを使用する場合は、高可用性ソリューションを提供するにする必要があります、MQSeries アダプターを実行しているホストの複数のインスタンス、MQSeries for Windows でクラスター化されたキュー マネージャーを使用して Windows 用の MQSeries Server のクラスターします。 キュー マネージャーのクラスタ リングと MQSeries Server をクラスタ リングする方法の詳細については、IBM WebSphere MQ のドキュメントを参照してください。 MQSeries アダプターの高可用性を作成する方法についての詳細については、MQSeries のヘルプの Microsoft BizTalk Adapter の「高可用性」を参照してください。  
  
### <a name="windows-sharepoint-services-adapter"></a>Windows SharePoint Services アダプター  
 Windows SharePoint Services アダプターは、SharePoint コンピューターに BizTalk によってインストールされた Windows SharePoint Services web サービスを呼び出すことによって、SharePoint からメッセージを取得します。 アダプターは、別のホスト インスタンスが同じメッセージを処理していないことを確認するには、チェック アウト メカニズムを使用します。 これにより、受信アダプターのホスト インスタンスを追加してスケール アウトできます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 高可用性は、SharePoint 受信アダプターを使用することができます、同じ受信、SharePoint の NLB のインストールを指す同じ HTTP URL にサブスクライブする複数のホスト インスタンス上の場所を実行します。  
  
### <a name="wcf-nettcp-adapter"></a>Wcf-nettcp アダプター  
 NetTcpBinding では、IP レイヤー負荷分散手法を使用して負荷分散を指定できます。 ただし、NetTcpBinding は接続待ち時間を減らすための既定で TCP 接続をプールします。 これは、負荷分散の基本的なメカニズムと競合する最適化です。 NetTcpBinding を最適化するための主要な構成値は、接続プールの設定の一部であるリース タイムアウトです。 接続プールすると、クライアント接続、ファーム内の特定のサーバーに関連付けられます。 これらの接続の有効期間と (リース タイムアウトの設定で制御される要素) を増やす、ファーム内のさまざまなサーバー間の負荷分散が不適切になります。 その結果、平均呼び出し時間が増加します。 バインディングによって使用される既定のリース タイムアウトを減らすことを検討、負荷分散のシナリオで NetTcpBinding を使用するとき。 30 秒のリース タイムアウトは負荷分散のシナリオでは、適切な開始点、最適な値は、アプリケーションによって異なります。 チャネル リース タイムアウトおよびその他のトランスポート クォータの詳細については、トランスポート クォータを参照してください。  
  
## <a name="see-also"></a>参照  
 [BizTalk ホストの高可用性を実現します。](../core/providing-high-availability-for-biztalk-hosts.md)