---
title: WCF アダプターに関する FAQ:開発ライブラリ |Microsoft Docs
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
ms.openlocfilehash: ce226b4eca18007087378a04c115e95df957fe62
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393609"
---
# <a name="wcf-adapter-faq-development-libraries"></a>WCF アダプターに関する FAQ:開発ライブラリ
## <a name="when-does-it-make-more-sense-to-use-the-wcf-adapters-vs-a-wcf-custom-binding-to-communicate-with-an-external-application-or-system"></a>いって、外部アプリケーションやシステムと通信する WCF カスタム バインドと WCF アダプターを使用する際に、ですか。  
 BizTalk Server WCF アダプターは、2 つの新しい方法で WCF を使用して BizTalk Server と外部システムの統合を容易に。  
  
- WCF クライアント/サービス コードを記述し、通信を処理する標準の BizTalk Server WCF アダプターを使用できます。  
  
- または、.NET WCF フレームワークを使用して、新しいカスタム WCF バインドを開発し、通信を処理する、WCF アダプターの代わりに使用します。  
  
  WCF アダプタを BizTalk Server を使用して WCF クライアント コードを開発し、リモートの WCF サービスとしての BizTalk Server を呼び出すまたは WCF サービスを作成および WCF サービスとして公開する BizTalk Server を構成できます。 代替手段としては、通信を処理するまったく新しいカスタム WCF バインドを実際に作成することです。  
  
  書き込み標準の WCF クライアントまたはサービス コードと WCF カスタム バインド要素の記述に対して標準の BizTalk Server アダプターを使用する利点は、カスタムのバインディングを開発するはるかに困難です。 BizTalk Server の管理 (監視、構成、および展開) 領域の外部では、結果として得られる WCF クライアントまたはサービスが存在します。 新しいカスタム バインドを作成し、BizTalk WCF カスタム アダプターを使用して、ホストの利点は、ことができます緊密に統合するのには、これらの BizTalk Server 管理機能。 インフラストラクチャのサポートに関するバインドの開発に関連するコストがかなりよりも高価でサービスを開発します。  
  
  両方のアプローチが内部の BizTalk メッセージ ボックス データベースとトランザクション方式を統合することができ、同等のパフォーマンスを提供することができますを理解しておく必要があります。 複数のソリューションにする複雑な意思決定することをお勧めします。  
  
  WCF を使用する場合、カスタム サービスとクライアントを記述し、2 つの接続に標準の BizTalk WCF アダプターを使用する必要があります最初ましょう。 .NET Framework と WCF ライブラリは目的としていますので、このタスクが簡単です。 WCF サービスを作成するには、単に、カスタム インターフェイスを開発、適切な属性を設定をコントラクトのコードを実装します。 オブジェクトのシリアル化するためのメタデータからのすべての WCF が行われます。 WCF サービスを作成すること、いくつかの簡単な手順で、サービスと通信する送信ポートを通じて WCF アダプターを構成できます。 新しいサービスは、内部の BizTalk メッセージ ボックス データベースを使用したメッセージのトランザクション交換に参加できるようにトランザクションを構成することもできます。  
  
  受信側で受信場所は、ネットワーク上で WCF サービスと同じようが表示されるように、BizTalk Server を構成することができます。 通常の WCF クライアント コードを記述できるようにして、そのサービスを呼び出すときに、トランザクションを使用することもできます。 WCF サービスのコードを WCF クライアントから直接構成可能なブリッジとして標準の BizTalk WCF アダプターを使用する利点は、開発のストーリーが非常に単純なことです。 WCF アダプターは、簡単な方法で WCF サービス環境から BizTalk Server に高パフォーマンスでトランザクション ブリッジを提供します。  
  
  要約すると、外部システムとの通信に、外部システムと対話する WCF サービスを記述して、問題をより簡単なソリューションとして、WCF サービスに直接通信するコードを記述します。 複雑な方法を使用して、新しいカスタム バインドを作成しより緊密な方法で WCF サービスを使用して WCF カスタム アダプターのいずれかを使用して BizTalk Server と統合できます。 下位レベルで複雑な開発作業は、新しいカスタム バインドを作成します。 このアプローチの利点は、BizTalk Server の管理、構成、および開発のストーリーが使用中である一様にソリューション全体でを緊密に統合されたソリューションに到着した、です。 アダプターの機能は、外部の WCF クライアントとサービスとして開発された、構成は BizTalk Server 環境外である必要があり、そのため、関連するインフラストラクチャ サポートが不足しています。  
  
## <a name="what-are-the-differences-between-the-wcf-adapters-and-the-adapters-in-the-biztalk-adapter-pack"></a>BizTalk Adapter Pack の WCF アダプターとアダプターの違いとは  
 WCF アダプターとは、BizTalk Server のリリースに標準装備されている 7 つのアダプターです。  
  
- WCF-Custom  
  
- WCF-CustomIsolated  
  
- WCF-NetTcp  
  
- WCF-BasicHttp  
  
- Wcf-wshttp  
  
- WCF-NetNamedPipe  
  
- WCF-NetMsmq  
  
  [BizTalk Adapter Pack](http://www.microsoft.com/biztalk/en/us/adapter-pack.aspx)独自に開発された .NET アプリケーション、SQL Server ベースのビジネスから基幹業務 (LOB) データに簡単かつ安全に接続する 1 つのソリューションを提供する post BizTalk Server のリリースにはインテリジェンス ソリューション、または Office Business Application (OBA)。 このリリースで使用可能な 3 つのアダプターは、Siebel、SAP、および Oracle DB です。 Adapter Pack ライセンスは BizTalk Server Developer、Standard、Enterprise エディションに含まれているが、Branch エディションに含まれていません。 ソフトウェア アシュアランス付きの BizTalk Server を既に購入したお客様には、そのプログラムを通じて BizTalk Adapter Pack へのアクセスがあります。  
  
## <a name="what-is-the-recommended-order-for-deciding-to-use-the-biztalk-server-adapter-framework-the-wcf-lob-adapter-sdk-or-the-net-framework"></a>BizTalk Server アダプター フレームワーク、WCF LOB Adapter SDK または .NET Framework の使用を決めるの推奨順序とは何ですか。  
 BizTalk アダプター フレームワークは、標準の .NET WCF に基づいていないため、最小推奨オプションです。 戦略的なソリューションでは、最も可能性の高い WCF を含める必要があります、これを行う最善の方法は何でしょうか。 最も簡単なオプションは、WCF クライアントとサービスを記述し、WCF アダプターを使用して、これらを接続するには。 プログラムが BizTalk Server の外部の場合は、.NET Framework と WCF カスタム バインドを記述できます。  
  
 のみのオプションは、メタデータ中心の LOB 統合の問題を解決しようとしているかどうか、WCF LOB Adapter SDK を選択するは。 WCF LOB Adapter SDK は、WCF バインドを作成するもう 1 つの方法と、メタデータのサポートを専門としています。 このメタデータ要件の例では、通信しているシステムにドキュメントの固定の型があるない場合にです。 BizTalk Server が送信または XML ドキュメントを受信し、ターゲット システムで使用できるように、メタデータは、ドキュメント内のデータのレイアウトについて説明します。  
  
## <a name="what-are-the-differences-between-the-biztalk-adapter-framework-and-the-wcf-lob-adapter-sdk"></a>BizTalk アダプター フレームワークと WCF LOB Adapter SDK の違いとは  
 BizTalk アダプター フレームワークは、7 つの標準の WCF アダプターのいずれも通信要件を満たしている場合は、カスタム WCF アダプターをビルドに使用されます。 アダプター フレームワークは、標準化された構成と標準の WCF アダプタで使用される管理メソッドを共有して、LOB アプリケーションをサポートするメタデータの豊富なサポートを提供します。  
  
 WCF LOB Adapter SDK を使用して、メタデータ中心の要件を持つターゲット システム用のカスタム バインディングを記述できます。 WCF LOB Adapter SDK の目標は、再利用可能なメタデータを使用した WCF ベース アダプターを相互に統合するには、エンタープライズ アプリケーションとデータベースを有効にする統一された開発を容易にします。 カスタム .NET アプリケーション、BizTalk Server、Microsoft Office SharePoint® Server、および Microsoft SQL Server の統合を含む複数の .NET アプリケーションで開発された同じソリューションを再利用できるため、WCF バインドを作成する WCF LOB Adapter SDK を使用して、サービス。 さらに、WCF LOB Adapter SDK は、ターゲット システム メタデータを公開する一般的なメタデータ オブジェクト モデルを提供、アダプターからコントラクトの参照、検索、および WCF を取得するアダプターの消費者向けです。 SDK をダウンロードする[ http://go.microsoft.com/fwlink/?LinkID=96184](http://go.microsoft.com/fwlink/?LinkID=96184)します。  
  
 BizTalk アダプター フレームワークと WCF LOB Adapter SDK カスタム アダプターの開発を容易にする、類似点がありますは、注目すべきいくつかの違いがあります。  
  
- WCF LOB Adapter SDK は新しいリリースであり、.NET Framework 3.0 クラスに基づいています。 以前の BizTalk アダプター フレームワークのようなメタデータの処理および接続の管理において豊富な機能を提供しますただし、作成されたアダプターは、BizTalk Server アーキテクチャには関連付けられません。  
  
- WCF LOB Adapter SDK を使用して作成されたアダプターでは、カスタム バインドとして公開され、任意の WCF クライアント アプリケーションによって呼び出される使用します。 WCF チャネルとして拡張することもできます。 BizTalk アダプター フレームワークを使用して作成されたアダプターは、BizTalk Server によってのみ呼び出されることができます。  
  
  BizTalk アダプター フレームワークの明示的な開発ツールのサポートはありません。 WCF LOB Adapter SDK のアダプター コード生成ウィザードでは、一連の手順は、カスタム アダプターを使用する必要のあるさまざまな情報を収集し、カスタム アダプター プロジェクトで使用するためのファイルを生成します。