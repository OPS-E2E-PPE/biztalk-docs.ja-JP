---
title: 'WCF アダプター FAQ: 開発ライブラリ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d05b635a-d46d-4f7d-896b-8ed7a799e80f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0676403e4fa13df5547bc518666a2e648b181fcb
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009179"
---
# <a name="wcf-adapter-faq-development-libraries"></a>WCF アダプターに関する FAQ: 開発ライブラリ
## <a name="when-does-it-make-more-sense-to-use-the-wcf-adapters-vs-a-wcf-custom-binding-to-communicate-with-an-external-application-or-system"></a>外部アプリケーションまたはシステムと通信する際に、WCF アダプターと WCF カスタム バインドのどちらを使用するのが適切ですか。  
 BizTalk Server WCF アダプターには、2 つの新しい方法で WCF を使用して BizTalk Server と外部システムの統合が容易にします。  
  
-   WCF クライアント/サービス コードを記述し、通信を処理する標準の BizTalk Server WCF アダプターを使用できます。  
  
-   .NET WCF フレームワークを使用して新しいカスタム WCF バインドを開発し、WCF アダプターの代わりに使用して通信を処理することもできます。  
  
 BizTalk Server で WCF アダプターを使用すると、WCF クライアント コードを開発して BizTalk Server をリモート WCF サービスとして呼び出したり、WCF サービスを作成して BizTalk Server を WCF サービスとして公開するように構成したりできます。 もう 1 つの方法は、新しいカスタム WCF バインド全体を実際に作成して通信を処理することです。  
  
 書き込み標準の WCF クライアントまたはサービス コードと WCF カスタム バインド要素の記述に対して標準の BizTalk Server アダプターを使用する利点は、カスタム バインドがはるかに困難を開発することです。 作成される WCF クライアントまたはサービスは、BizTalk Server の管理 (監視、構成、および展開) 領域の外部にあります。 独自の新しいカスタム バインドを作成し、BizTalk WCF カスタム アダプターを使用してホストすることの利点は、これらを BizTalk Server 管理機能と緊密に統合できる点です。 インフラストラクチャのサポートに関するバインドの開発に伴うコストは、サービスの開発に関連するコストよりも大幅に高くなります。  
  
 どちらの方法でも、トランザクションを利用して内部の BizTalk メッセージ ボックス データベースと統合し、パフォーマンスの面でも変わらないという点を理解することが重要です。 どちらを使用するかは、ソリューションの複雑さによって決まります。  
  
 WCF を使用する場合、カスタム サービスとクライアントを作成してから、標準の BizTalk WCF アダプターを使用してこの 2 つを接続する必要があります。 .NET Framework と WCF ライブラリは、このタスクを簡単にすることを目的としています。 WCF サービスを作成するには、カスタム インターフェイスを作成し、適切な属性を設定してから、コントラクトのコードを実装するだけです。 WCF では、メタデータからオブジェクトのシリアル化まで、すべてが処理されます。 WCF サービスを作成した後、送信ポートを通じて WCF アダプターを構成し、いくつかの簡単な手順によってサービスと通信できるようにします。 新しいサービスが内部の BizTalk メッセージ ボックス データベースとのメッセージのトランザクション交換に参加できるようにトランザクションを構成することもできます。  
  
 受信側では、受信場所がネットワーク上の WCF サービスと同じに見えるように BizTalk Server を構成できます。 これにより、標準の WCF クライアント コードを記述し、そのサービスを呼び出すときにトランザクションを使用することもできます。 WCF クライアントと WCF サービス コードを直接接続する構成可能なブリッジとして標準の BizTalk WCF アダプターを使用する利点は、開発のストーリーが非常に単純なことです。 WCF アダプターは、簡単な方法で、WCF サービス環境から BizTalk Server へのパフォーマンスに優れたトランザクション ブリッジを提供します。  
  
 つまり、外部システムと通信するには、外部システムと対話する WCF サービスを作成した後、問題をより簡単に解決する方法として WCF サービスと直接通信するコードを記述します。 複雑なアプローチを使用して、新しいカスタム バインドを作成しより緊密な方法で WCF サービスを使用して WCF カスタム アダプターのいずれかを使用して BizTalk Server と統合できます。 新しいカスタム バインドの作成は、詳細レベルの複雑な開発作業です。 この方法を使用する利点は、ソリューション全体で BizTalk Server の管理、構成、および開発のストーリーが均一に使用されている、緊密に統合されたソリューションを実現できることです。 アダプターの機能が外部 WCF クライアントおよびサービスとして開発される場合、構成は BizTalk Server 環境の外部に存在する必要があるため、関連するインフラストラクチャ サポートは提供されません。  
  
## <a name="what-are-the-differences-between-the-wcf-adapters-and-the-adapters-in-the-biztalk-adapter-pack"></a>WCF アダプターと BizTalk Adapter Pack に含まれる アダプターの違いは何ですか。  
 WCF アダプターは、BizTalk Server のリリースに標準で付属する 7 つのアダプターです。  
  
-   WCF-Custom  
  
-   WCF-CustomIsolated  
  
-   WCF-NetTcp  
  
-   WCF-BasicHttp  
  
-   WCF-WsHttp  
  
-   WCF-NetNamedPipe  
  
-   WCF-NetMsmq  
  
 [BizTalk Adapter Pack](http://www.microsoft.com/biztalk/en/us/adapter-pack.aspx) -BizTalk Server リリース後、独自に開発された .NET アプリケーション、SQL Server ベースのビジネスから基幹業務 (LOB) データに簡単かつ安全に接続する 1 つのソリューションを提供するにはインテリジェンス ソリューション、または Office Business Application (OBA)。 このリリースでは、Siebel、SAP、および Oracle DB の 3 つのアダプターを使用できます。 Adapter Pack ライセンスが BizTalk Server の Developer、Standard、および Enterprise のエディションに含まれるが、Branch エディションに含まれていません。 ソフトウェア アシュアランスでの BizTalk Server を既に購入した顧客は、そのプログラムを通じて BizTalk Adapter Pack へのアクセスも付与されます。  
  
## <a name="what-is-the-recommended-order-for-deciding-to-use-the-biztalk-server-adapter-framework-the-wcf-lob-adapter-sdk-or-the-net-framework"></a>BizTalk Server アダプター フレームワーク、WCF LOB アダプター SDK、または .NET Framework のいずれかに決定する場合、どの順序で推奨されますか。  
 BizTalk アダプター フレームワークは標準の .NET WCF に基づいていないため、優先順位が最も低いオプションです。 ソリューションに戦略的に WCF を含める必要がある可能性がある場合、これを行う最適な方法は何でしょうか。 最も簡単なのは、WCF クライアントおよびサービスを作成した後、WCF アダプターを使用してこれらを接続する方法です。 プログラムが BizTalk Server の外部にある場合は、.NET Framework を使用して WCF カスタム バインドを作成できます。  
  
 WCF LOB Adapter SDK をオプションとして選択できるのは、メタデータ中心の LOB 統合の問題を解決する場合のみです。 WCF LOB Adapter SDK を使用して WCF バインドを作成することもできます。WCF LOB Adapter SDK はメタデータのサポートを専門にしています。 このようなメタデータ要件の例は、ユーザーが通信しているシステムに固定されたドキュメントの種類がない場合です。 BizTalk Server は XML ドキュメントを送受信し、メタデータはドキュメント内のデータのレイアウトを記述するため、ターゲット システムはそのドキュメントを使用できます。  
  
## <a name="what-are-the-differences-between-the-biztalk-adapter-framework-and-the-wcf-lob-adapter-sdk"></a>BizTalk アダプター フレームワークと WCF LOB Adapter SDK の違いは何ですか。  
 BizTalk アダプター フレームワークは、7 つの標準の WCF アダプターがどれも通信要件を満たしていない場合にカスタム WCF アダプターを作成するために使用されます。 アダプター フレームワークはメタデータにさまざまなサポートを提供することで、LOB アプリケーションをサポートし、標準の WCF アダプターで使用される標準化された構成方法と管理方法を共有します。  
  
 WCF LOB Adapter SDK を使用すると、メタデータ中心の要件を持つターゲット システムのカスタム バインドを作成できます。 WCF LOB Adapter SDK の目標は、再利用可能なメタデータ中心の WCF ベース アダプターを一貫して開発できるようにすることです。このアダプターにより、エンタープライズ アプリケーションとデータベースを統合できます。 カスタム .NET アプリケーション、BizTalk Server、Microsoft Office SharePoint® Server、および Microsoft SQL Server の統合を含む複数の .NET アプリケーションで開発された同じソリューションを再利用できる WCF LOB Adapter SDK を使用するには、WCF バインドが生成される、ためサービスです。 また、WCF LOB Adapter SDK はターゲット システム メタデータを公開するための共通のメタデータ オブジェクト モデルを提供し、アダプターのコンシューマーがアダプターから WCF コントラクトを参照、検索、および取得できるようにします。 SDK をダウンロードする[http://go.microsoft.com/fwlink/?LinkID=96184](http://go.microsoft.com/fwlink/?LinkID=96184)です。  
  
 BizTalk アダプター フレームワークと WCF LOB Adapter SDK は、カスタム アダプターの開発を容易にするという点で似ていますが、重要な違いがいくつかあります。  
  
-   WCF LOB Adapter SDK の方が最新リリースであり、.NET Framework 3.0 クラスに基づいています。 以前の BizTalk アダプター フレームワークと同様に、WCF LOB Adapter SDK はメタデータ処理と接続の管理に関連するさまざまな機能を提供します。ただし、作成されたアダプターは BizTalk Server アーキテクチャには関連付けられません。  
  
-   WCF LOB Adapter SDK を使用して作成されたアダプターはカスタム バインドとして公開されるため、任意の WCF クライアント アプリケーションから呼び出すことができます。 また、WCF チャネルとして拡張することもできます。 BizTalk アダプター フレームワークを使用して作成されたアダプターは、BizTalk Server からのみ呼び出すことができます。  
  
 BizTalk アダプター フレームワークには、明示的な開発ツールのサポートはありません。 WCF LOB Adapter SDK の場合、アダプター コード生成ウィザードを使用することで、カスタム アダプターで必要な各種の情報を収集する手順を実行し、カスタム アダプター プロジェクトで使用するファイルを生成できます。