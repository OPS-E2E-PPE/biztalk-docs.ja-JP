---
title: 受信ホストをスケール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9f78710-93fa-4877-8273-a1634d768d88
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 650042a5de59410f932af260ee6ca2cfc0a56d77
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985707"
---
# <a name="scaling-out-receiving-hosts"></a>スケール アウト、受信ホスト
受信ホストの可用性を高めるには、2 つ以上をいる必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]各受信ホストのインスタンスを実行しているコンピューター。 スケール アウトは、受信ホストがメッセージを大量に消費する BizTalk Server の展開の可用性を向上できます。 こうすることで、受信ホストが実行するオーケストレーション処理を最小限に抑えながら、さまざまなタイプのメッセージを高速かつ高い信頼性でルーティングさせることができます。  
  
 オーケストレーション処理やメッセージ送信を行うホストから受信ホストを分離することは、環境のセキュリティとスケーラビリティ強化にもつながります。各ホストのセキュリティやスケーラビリティを他のホストと切り離して捉えることができるためです。 たとえば、処理ホストや送信ホストには一切コンピューターを追加することなく、受信ホストにのみ 2 台のコンピューター (ホスト インスタンス) を追加することもできます。  
  
## <a name="understanding-in-process-and-isolated-receiving-hosts"></a>インプロセスと分離受信ホストを理解します。  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ビジネス サービスを提供するアプリケーションを統合します。 通常、統合、として表されます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)](アプリケーション) からのドキュメントを受け取り、ドキュメントを処理し、アプリケーションまたは別のアプリケーションには、処理済みのドキュメントを送信します。 プロセスには、ドキュメントのトランザクションは呼び出されます。  
  
 トランザクションは、通常、特定のプロトコル チャネルを監視し、ドキュメントを受信 BizTalk アダプターで起動します。 *アダプター*他のアプリケーションを接続するためのいわゆる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 その関数に基づき、送信アダプターまたは受信アダプターを指定ができます。 既定のアダプターのほとんどは、受信機能と 1 つの .NET アセンブリに組み込まれている送信関数の両方で 1 つの .NET コンポーネントです。 アダプターが存在するプロセスのメモリ領域に基づき、これは、いずれかでのプロセス (受信) アダプターまたは分離 (受信) アダプター。 インプロセス アダプターのみでホストされる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセス (BTSNTSvc.exe) と、分離アダプターは別のプロセスによってホストされるように設計されています。 たとえば、HTTP アダプタと SOAP アダプタは、インターネット インフォメーション サービス (IIS) プロセスによってホストされます。 これらは基本的に ISAPI 拡張機能です。 その一方で、すべての送信アダプターには、インプロセス アダプターです。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成が 2 つの既定のホストを作成します: インプロセス ホストは、BizTalkServerApplication と呼ばれ、分離ホストには、BizTalkServerIsolatedHost が呼び出されます。 ホストには 2 つの関数が機能します: 1 つは論理的にグループ化、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]項目をこれらの項目が別に割り当てることができるように[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセス、およびその他のセキュリティを制御します。 ホスト Windows グループを指定する必要があります。 このグループ内のユーザーによってホストされるアダプターにドキュメントを送信できるのみ、*インスタンスをホスト*このホストに割り当てられています。  
  
 各 2 つの既定のホストは、ホスト インスタンスがあります。 ホスト インスタンスでは、名前はありませんが、ホストと関連付けられています。 BizTalkServerApplication ホスト インスタンスが実際には、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でサービス プロセス (BTSNTSvc.exe)、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BizTalk グループ内のコンピューター。 BizTalkServerIsolatedHost ホスト インスタンスが、このプロセスには直接バインドされていません。 受信アダプターをホストするプロセスに関連付けられます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成を作成も、*受信ハンドラー* SMTP を除き、既定のアダプターの各 (送信アダプタは SMTP)。 受信ハンドラのプロパティの 1 つは、ホスト名です。 ホストとそのホストのホスト インスタンスにバインドされている方法です。  
  
 アダプター、ホスト、ホスト インスタンス、および受信ハンドラー、に加えてする前に受信ポートを構成する必要があります。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ドキュメントの受信を開始することができます。 受信ポートには、受信場所が含まれています。 受信場所では、受信ハンドラー プロパティがあります。 次のロジックをトレースできます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]これを処理するプロセスの受信ポート。  
  
 受信ポートの構成では、必要に応じてマップを指定します。 受信場所の構成では、ドキュメントの前処理に使用されるパイプラインを指定する必要があります。 指定された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセスで処理されるすべてのドキュメントのドキュメントのマッピングを前処理する、ドキュメントを受信します。 これは、インプロセス ホスト インスタンスと分離ホスト インスタンスの両方で同じです。  
  
## <a name="scaling-out-in-process-receiving-hosts"></a>ホストのスケール アウト プロセスでの受信  
 次の図は、別のコンピューターで 2 つのホスト インスタンスそれぞれを使用して、受信ホストを高可用性を実現する BizTalk Server の展開を示します。 この図では処理と送信ホストのない高可用性、ホストに割り当てられている BizTalk アイテムを処理する 1 つだけのホスト インスタンスがあるため、注意してください。  
  
 ![メッセージを受信するための複数のホスト](../core/media/tdi-ha-scalereceive.gif "TDI_HA_ScaleReceive")  
  
 複数の取引先とやりとりする場合や、異なるプロトコルを使用する場合など、環境の規模が大きい場合は、受信機能を複数の受信ホストに分散させることが可能です。 たとえば、アダプターごとにメッセージ受信用のホストを設けたり、メッセージの受信ホストを取引先ごとに用意することもできます。 複数の受信ホストを設ける際、セキュリティの処理境界を作成することで環境の管理性とスケーラビリティは向上しますが、それによって環境の高可用性が実現するというわけではありません。 環境の高可用性を実現するためには、受信ホストごとに複数のホスト インスタンスを作成する必要があります。 たとえば、次の 3 つ異なる受信ホスト (A、B、および C) 3 つの異なる会社から送信されるメッセージを作成できます。 すべての受信ホストに高可用性を確保するためには、受信ホストごとに複数のホスト インスタンスを作成し、それらを複数のコンピューターに展開する必要があります。 セキュリティの処理境界、管理性、スケーラビリティを損なうことなく、複数のホスト インスタンスを 1 台のコンピューターに割り当てることができるという点に注目してください。  
  
 次の図は、高可用性の 3 台のコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]専用のホスト環境のさまざまな企業からメッセージを受信します。  
  
 ![受信ホストのスケール アウト](../technical-guides/media/04bd4234-dc71-49d8-b630-0643390b29f0.gif "04bd4234-dc71-49d8-b630-0643390b29f0")  
  
 この構成で高可用性を実現するには、各コンピューターには 3 つのホスト インスタンスが実行されます。 次の 3 つの会社の 1 つのインスタンス。 各会社に対応するホスト インスタンスには、その会社と通信するための受信場所およびパイプラインが保持されます。 通常の操作中、受信アダプターの前にスケール アウトに必要な作業を行う場合に限りメッセージング負荷が分散されて次の 3 つのホスト インスタンス間でホストごとにします。 1 つのコンピューターの特定のホスト インスタンスで障害が発生した場合、その他の 2 つのコンピューターで実行されているホスト インスタンスが処理を引き継ぐため、サービスの可用性は維持されます。  
  
## <a name="scaling-out-isolated-receiving-hosts"></a>受信ホストに分離されたスケール アウト  
 ホストのインスタンス以外の拡張機能と受信ホストの高可用性を実現するプロセスは、展開で実装されている特定のアダプターによっても異なります。 各アダプターには、プロトコルごとの特性があるため、計画と導入もそれぞれのケースによって異なります。 ただし、BizTalk Server には、主に、追加のコンピューターとホスト インスタンスで、すべてのアダプターに対して同じ高可用性ソリューションを適用することができます。  
  
 受信メッセージを複数のホスト コンピューターに分散して高可用性を確保する際、使用するプロトコルによっては、受信アダプターに追加のメカニズムが必要になる場合もあります。 (それ以外の場合は、Web サービス アダプターと呼ばれます)、HTTP または SOAP アダプターを使用する BizTalk Server ソリューションでは、次の図に示すように、ロード バランサーなどネットワーク負荷分散 (NLB) の受信側の負荷を分散するを必要があります。  
  
 ![受信ホストのスケール アウト分離](../technical-guides/media/cb38ec25-bfb0-4a55-8464-b7918b6fc746.gif "cb38ec25-bfb0-4a55-8464-b7918b6fc746")  
  
 最も一般的なアダプターの高可用性のガイドラインの詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、「BizTalk Server 受信アダプターの拡張」セクションを参照してください[Scaled-Out 受信ホスト](http://go.microsoft.com/fwlink/?LinkId=151283)(<http://go.microsoft.com/fwlink/?LinkId=151283>) biztalk。サーバーのヘルプ。  
  
## <a name="see-also"></a>参照  
 [受信ホストをクラスタ リング](../technical-guides/clustering-receiving-hosts.md)   
 [スケール アウト処理ホスト](../technical-guides/scaling-out-processing-hosts.md)   
 [送信ホストのスケールアウト](../technical-guides/scaling-out-sending-hosts.md)