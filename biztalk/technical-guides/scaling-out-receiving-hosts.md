---
title: 受信ホストをスケール |Microsoft ドキュメント
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
ms.openlocfilehash: 8f0a58d7dfa022c3921abb5b426dacdf387095c2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010147"
---
# <a name="scaling-out-receiving-hosts"></a>スケール アウト受信ホスト
受信ホストを高可用性にする必要がありますがある 2 つ以上の[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]各受信ホストのインスタンスを実行しているコンピューター。 スケール アウト受信ホスト メッセージングを頻繁に実行する BizTalk Server 展開の可用性が向上します。 こうすることで、受信ホストが実行するオーケストレーション処理を最小限に抑えながら、さまざまなタイプのメッセージを高速かつ高い信頼性でルーティングさせることができます。  
  
 オーケストレーション処理やメッセージ送信を行うホストから受信ホストを分離することは、環境のセキュリティとスケーラビリティ強化にもつながります。各ホストのセキュリティやスケーラビリティを他のホストと切り離して捉えることができるためです。 たとえば、処理ホストや送信ホストには一切コンピューターを追加することなく、受信ホストにのみ 2 台のコンピューター (ホスト インスタンス) を追加することもできます。  
  
## <a name="understanding-in-process-and-isolated-receiving-hosts"></a>インプロセスと分離受信ホストを理解します。  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジネス サービスを提供するアプリケーションを統合します。 通常、統合、として表されます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)](アプリケーション) からのドキュメントを受け取り、ドキュメントを処理し、アプリケーションまたは別のアプリケーションに処理されたドキュメントを送信します。 プロセスには、ドキュメントのトランザクションは呼び出されます。  
  
 トランザクションは、通常、BizTalk アダプターの特定のプロトコル チャネルを監視し、ドキュメントを受信を開始します。 *アダプター*他のアプリケーションを接続するためのいわゆる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 その関数に基づいて、送信アダプターまたは受信アダプターを指定ができます。 既定のアダプターのほとんどは、受信機能と 1 つの .NET アセンブリに組み込まれている送信関数の両方に 1 つの .NET コンポーネントです。 アダプターが存在するプロセスのメモリ領域に基づき、これは、いずれかで、プロセス (受信) アダプターまたは分離 (受信) アダプター。 インプロセス アダプターはのみでホストされる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセス (BTSNTSvc.exe) と、分離アダプターは別のプロセスによってホストされるように設計されています。 たとえば、HTTP アダプタと SOAP アダプタは、インターネット インフォメーション サービス (IIS) プロセスによってホストされます。 これらは、本質的に ISAPI 拡張機能です。 その一方で、すべての送信アダプターは、インプロセス アダプターです。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Configuration が 2 つの既定のホストを作成、インプロセス ホストは BizTalkServerApplication と呼ばれ、分離ホストは、BizTalkServerIsolatedHost と呼びます。 ホストが 2 つの機能を提供: 1 つは論理的にグループ化、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]項目をこれらの項目が別に割り当てることができるように[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセス、およびその他のセキュリティを制御します。 Windows グループ、ホストを指定する必要があります。 このグループ内のユーザーによってホストされるアダプターにドキュメントを送信できますのみ、*のホスト インスタンスの*このホストに割り当てられています。  
  
 2 つの既定のホストのそれぞれで、ホスト インスタンスがあります。 ホスト インスタンスは、名前がありませんが、ホストに関連付けられてです。 BizTalkServerApplication ホスト インスタンスが実際には、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でサービス プロセス (BTSNTSvc.exe)、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BizTalk グループ内のコンピューター。 直接、BizTalkServerIsolatedHost ホスト インスタンスは、プロセスにはバインドされません。 関連付けられている受信アダプターをホストするプロセスです。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成も作成、*受信ハンドラー* SMTP を除き、既定のアダプターの各 (は SMTP 送信アダプタ)。 受信ハンドラのプロパティの 1 つは、ホスト名です。 ホストとそのホストのホスト インスタンスにバインドされている方法です。  
  
 に加えて、アダプター、ホスト、ホスト インスタンス、および受信ハンドラー、前に受信ポートを構成する必要があります。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ドキュメントの受信を開始します。 受信ポートには、受信場所が含まれています。 受信場所では、受信ハンドラー プロパティがあります。 次のロジックでをトレースすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]これを処理するプロセスの受信ポート。  
  
 受信ポートの構成では、必要に応じてマップを指定します。 受信場所の構成のドキュメントの前処理に使用するパイプラインを指定する必要があります。 指定された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセスで、ドキュメント マップに、ドキュメントを前処理する、ドキュメントを受信からすべての情報を処理します。 これは、インプロセス ホスト インスタンスと分離ホスト インスタンスの両方で同じです。  
  
## <a name="scaling-out-in-process-receiving-hosts"></a>ホストのスケール アウト プロセスでの受信  
 次の図は、別のコンピューター上の 2 つのホスト インスタンスごとのことで、受信ホストの高可用性を実現した BizTalk Server の展開を示します。 この図では、処理と送信元ホストが使用できないこと強く、ホストに割り当てられている BizTalk アイテムを処理する 1 つだけのホスト インスタンスがあるために注意してください。  
  
 ![メッセージを受信するための複数のホスト](../core/media/tdi-ha-scalereceive.gif "TDI_HA_ScaleReceive")  
  
 複数の取引先とやりとりする場合や、異なるプロトコルを使用する場合など、環境の規模が大きい場合は、受信機能を複数の受信ホストに分散させることが可能です。 たとえば、アダプターごとにメッセージ受信用のホストを設けたり、メッセージの受信ホストを取引先ごとに用意することもできます。 複数の受信ホストを設ける際、セキュリティの処理境界を作成することで環境の管理性とスケーラビリティは向上しますが、それによって環境の高可用性が実現するというわけではありません。 環境の高可用性を実現するためには、受信ホストごとに複数のホスト インスタンスを作成する必要があります。 たとえば、次の 3 つ異なる受信ホスト (A、B、および C) 次の 3 つの異なる会社から送信されるメッセージを作成できます。 すべての受信ホストに高可用性を確保するためには、受信ホストごとに複数のホスト インスタンスを作成し、それらを複数のコンピューターに展開する必要があります。 セキュリティの処理境界、管理性、スケーラビリティを損なうことなく、複数のホスト インスタンスを 1 台のコンピューターに割り当てることができるという点に注目してください。  
  
 次の図に、高可用性の 3 台のコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]異なる会社からメッセージを受信する専用の環境をホストします。  
  
 ![受信ホストのスケール アウト](../technical-guides/media/04bd4234-dc71-49d8-b630-0643390b29f0.gif "04bd4234-dc71-49d8-b630-0643390b29f0")  
  
 この構成で高可用性を実現するには、各コンピューターが 3 つのホスト インスタンスを実行します。 3 つの会社の列ごとに 1 つのインスタンス。 各会社に対応するホスト インスタンスには、その会社と通信するための受信場所およびパイプラインが保持されます。 通常の操作中にスケール アウト受信アダプターの前に必要な作業を行っている限り、メッセージング負荷が分散、3 つのホスト インスタンス間でホストごとにします。 1 つのコンピューターの特定のホスト インスタンスで障害が発生した場合、その他の 2 つのコンピューターで実行されているホスト インスタンスが処理を引き継ぐため、サービスの可用性は維持されます。  
  
## <a name="scaling-out-isolated-receiving-hosts"></a>受信ホストを分離されたスケール アウト  
 ホスト インスタンスだけでなく、プロセスのスケーリングと受信ホストの高可用性を実現するは、展開で実装する特定のアダプターによっても異なります。 各アダプターには、プロトコルごとの特性があるため、計画と導入もそれぞれのケースによって異なります。 ただし、BizTalk Server には、すべてのアダプターの主に、追加のコンピューターとホスト インスタンスで同じ高可用性ソリューションを適用することができます。  
  
 受信メッセージを複数のホスト コンピューターに分散して高可用性を確保する際、使用するプロトコルによっては、受信アダプターに追加のメカニズムが必要になる場合もあります。 たとえば、次の図に示すように、(それ以外の場合は、Web サービス アダプターと呼ばれます)、HTTP または SOAP アダプターを使用する BizTalk Server ソリューションは、ロード バランサーなどネットワーク負荷分散 (NLB) 受信の負荷を分散が必要です。  
  
 ![受信ホストのスケール アウト分離](../technical-guides/media/cb38ec25-bfb0-4a55-8464-b7918b6fc746.gif "cb38ec25-bfb0-4a55-8464-b7918b6fc746")  
  
 最も一般的なアダプターの高可用性に関するガイドラインの詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、「BizTalk Server 受信アダプターの拡張」セクションを参照して[Scaled-Out 受信ホスト](http://go.microsoft.com/fwlink/?LinkId=151283)(http://go.microsoft.com/fwlink/しますか?LinkId = 151283) BizTalk Server ヘルプの「します。  
  
## <a name="see-also"></a>参照  
 [受信ホストをクラスタ リング](../technical-guides/clustering-receiving-hosts.md)   
 [スケール アウト処理の各ホスト](../technical-guides/scaling-out-processing-hosts.md)   
 [送信ホストのスケールアウト](../technical-guides/scaling-out-sending-hosts.md)