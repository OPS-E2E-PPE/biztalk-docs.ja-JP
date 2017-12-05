---
title: "送受信の計画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d67e5f7-5127-4c1d-be20-8d8dbb538286
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca2b87964266b77629f7fa1d1156ace3cd048e7f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="planning-for-sending-and-receiving"></a>送受信の計画
処理されるドキュメントのほぼすべて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が受信した、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信アダプター、およびから送信された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信アダプター。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプターのいずれかで目立つように図[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、することが重要が済んだ後どのアダプターやアクセラレータを使用してこれらのアダプターやアクセラレータを正しく構成する方法を決定します。  
  
## <a name="determining-which-adapters-and-accelerators-you-will-use"></a>どのアダプターおよび使用するアクセラレータを決定します。  
 アダプターとアクセラレータ間および BizTalk アプリケーションと、内部組織と取引先間のドキュメントの送受信を容易にする必要がありますを決定するには、事前に取引先に相談します。ビジネス アプリケーション。 デザイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]とその他の取引関係を確立することは、追加のアダプターやアクセラレータを追加することに対応する十分な柔軟性に優れたアーキテクチャが、将来パートナーです。  
  
## <a name="functionality-supported-by-biztalk-adapters"></a>BizTalk アダプターでサポートされる機能  
 このセクションの表では、各ネイティブ アダプタと、アダプターは、次の機能を提供するかどうかの主な利点を示します。  
  
-   **トランザクションのサポート**分散トランザクション コーディネーター (DTC) トランザクションのコンテキストでドキュメントを送受信する機能。 この機能は、メッセージの順次配送を維持し、ドキュメントが重複または消失しないようにするために必要です。  
  
    > [!NOTE]  
    >  MSDTC の問題を発生した場合は、トピックを参照[MSDTC の問題のトラブルシューティング](http://go.microsoft.com/fwlink/?LinkID=154693)(http://go.microsoft.com/fwlink/?LinkID=154693)。  
  
-   **双方向通信のサポート (要求/応答または送信請求-応答)**機能ドキュメントを送信して送信先からの応答メッセージを処理できる、またはドキュメントを受信し、ソースに応答メッセージを送信します。  
  
-   **順次受信のサポート。** ドキュメントを受信したとおりの順序でメッセージ ボックス データベースに受信したドキュメントをパブリッシュする権限です。  
  
    > [!NOTE]  
    >  他のアダプターは、特定のアダプターは受信場所のレベルでドキュメントの順序付き配信を適用できます。 順次配送は、受信場所のレベルでドキュメントの配信を順序付けがサポートされていないアダプターの送信ポート レベルで引き続き適用できますが、パフォーマンスの低下が発生する可能性があります。 メッセージの順次配送の詳細については、トピックを参照してください。[のメッセージ配信の順序付け](http://go.microsoft.com/fwlink/?LinkId=155751)(http://go.microsoft.com/fwlink/?LinkId=155751)。  
  
-   **SSO が有効にします。** アダプタを使用してドキュメントの送受信を行う際に SSO 認証を使用する機能です。  
  
|[アダプター]|主な利点|トランザクションのサポート|双方向通信のサポート|順次受信のサポート|SSO は有効|  
|-------------|---------------------|-------------------------|------------------------------------|-------------------------------|-----------------|  
|ファイル|使いやすい|不可|いいえ|いいえ|不可|  
|FTP|企業間の通信は、広く使用します。|不可|いいえ|いいえ|可|  
|HTTP(S)|企業間の通信は、広く使用します。|不可|要求 - 応答および送信請求 - 応答|不可|可|  
|SOAP|Web サービスの使用をサポートしています|不可|要求 - 応答および送信請求 - 応答|不可|可|  
|MSMQ (MSMQ)|BizTalk Server と Microsoft メッセージ キュー間でメッセージの 1 回限りの配信の保証をサポートしています|可|いいえ|可|不可|  
|MQ Series|Windows プラットフォームの BizTalk Server と IBM WebSphere MQ 間でメッセージの 1 回限りの配信の保証をサポートしています|可|いいえ|はい|可|  
|SQL|直接 BizTalk Server と SQL Server データベース間の通信をサポート|可|送信請求 - 応答のみ|不可|不可|  
|Windows SharePoint Services|XML メッセージと BizTalk Server と SharePoint ドキュメント ライブラリの間でのバイナリのメッセージを交換できるように|不可|いいえ|いいえ|不可|  
|POP3|電子メールでドキュメントの受信をサポートしています|不可|いいえ|いいえ|不可|  
|SMTP (SMTP)|電子メールを使用したドキュメントの送信をサポート|不可|いいえ|いいえ|不可|  
|EDI |EDI 標準に準拠するビジネス ドキュメントの処理をサポート|不可|いいえ|いいえ|不可|  
|Custom|レガシ システムをサポートしています|あり (カスタム コードが必要)|あり (カスタム コードが必要)|あり (カスタム コードが必要)|あり (カスタム コードが必要)|  
|WCF-WSHttp|サポート ws-* 標準 HTTP トランスポート経由で|あり (WsHTTP でトランザクションをサポート) (WS トランザクションのみ)|要求 - 応答および送信請求 - 応答|不可|可|  
|WCF-BasicHttp|ASMX ベースの Web サービスとクライアント、および、WS に準拠するその他のサービスと通信する-基本プロファイル 1.1 HTTP または HTTPS を使用します。|不可|要求 - 応答および送信請求 - 応答|不可|可|  
|WCF-NetTcp|サポート ws-* 標準 TCP トランスポート経由で|可|要求 - 応答および送信請求 - 応答|不可|可|  
|WCF-NetMsmq|Microsoft メッセージ キュー (MSMQ) をトランスポートとしてを活用することにより、キューをサポート|可|いいえ|はい|可|  
|WCF-NetNamedPipe|(WCF アプリケーション) の場合のみ、同じコンピューター上のプロセス間通信の高速トランスポートを提供します。|可|要求 - 応答および送信請求 - 応答|不可|可|  
|WCF-Custom|WCF の拡張機能を使用をできます。|可能。|可能。|あり (バインドでサポートされている場合)|可能。|  
|WCF-CustomIsolated|HTTP トランスポート経由で WCF 拡張機能の使用を有効に|可能。|可能。|不可。|可能。|  
  
## <a name="line-of-business-adapters"></a>基幹業務アダプタ  
 次に、Microsoft から提供されている基幹業務 (LOB) アダプタのリストを示します。  
  
> [!NOTE]  
>  を除き、Microsoft BizTalk Adapter v2.0 for mySAP™ Business Suite (アダプター)、基幹業務アダプターのいずれも Windows Vista ではサポートされています。  
  
|[アダプター]|Description|Supported Versions|  
|-------------|-----------------|------------------------|  
|SAP (「アダプター」とも呼ばれる)|中間ドキュメント (IDOC)、BAPI、および BizTalk Server と SAP R/3® システム間でのリモート関数呼び出し (RFC) メッセージの交換を有効にします。|SAP R/3 4.x および R/3 6.20 (Enterprise)|  
|PeopleSoft Enterprise|BizTalk Server と PeopleSoft システム間での Component Interface (CI) メッセージの交換を有効にします。|PeopleTools Version 8.17.02、8.43、8.45、8.46、および 8.48|  
|JD Edwards OneWorld XE|BizTalk Server と JD Edwards OneWorld システム間での Business Function メッセージの交換を有効にします。|B7.3.3.3 および SP23 と JDE 8.0 (B7.3.3.4)|  
|JD Edwards EnterpriseOne|BizTalk Server と JD Edwards EnterpriseOne システム間での Business Function メッセージの交換を有効にします。|8.10 & 8.11 およびツール リリース 8.93、8.94、8.95、8.96|  
|ODBC Adapter for Oracle Database|Oracle Server データベースからの情報の読み取り、およびこのデータベースへの情報の書き込みを有効にします。|Oracle 8i (8.1.6.0)、9 i (9.2.0.1)、または 10 g|  
|Siebel eBusiness Applications|BizTalk Server と Siebel eBusiness Application 間での Business Components メッセージと Business Service メッセージの交換を有効にします。|7.0、7.5。 * 7.7、します。\*、7.8 とします。\*|  
|TIBCO Rendezvous|BizTalk Server と TIBCO Rendezvous 間での XML メッセージとバイナリ データ形式メッセージの交換を有効にします。|7.3|  
|TIBCO Enterprise Message Service|BizTalk Server と TIBCO EMS サーバー間での XML メッセージとバイナリ データ形式メッセージの交換を有効にします。TIBCO EMS サーバーは、緊密に統合され信頼性の高いアプリケーション インフラストラクチャを提供します。|4.2|  
|WebSphere MQ|BizTalk Server と IBM WebSphere MQ 間でのメッセージの交換を有効にします。|5.3 フィックス パック 10 以降またはおよび 6.0 修正パック 1.1 以降|  
  
 BizTalk Server で使用可能な LOB アダプタについての詳細については、次を参照してください。 [BizTalk Server 2010 に含まれるアダプター](http://go.microsoft.com/fwlink/?LinkId=152664) (http://go.microsoft.com/fwlink/?LinkId=152664)。  
  
## <a name="biztalk-adapter-pack"></a>BizTalk アダプター パック  
 Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] Oracle データベース、Oracle E-business Suite、SAP、Siebel、および SQL Server などの LOB アプリケーションへの接続を提供する WCF ベース アダプターが含まれます。 使用可能なアダプターの一覧については[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を参照してください[BizTalk Adapter Pack](http://go.microsoft.com/fwlink/?LinkId=152665) (http://go.microsoft.com/fwlink/?LinkId=152665)。  
  
> [!IMPORTANT]  
>  使用することができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]で利用可能な WCF ベースの LOB アダプターの BizTalk プロジェクトに LOB アダプターの BizTalk プロジェクトを移行する移行ツール、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。 ダウンロードすることができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]移行ツールから[BizTalk アダプター パック移行ツール](http://go.microsoft.com/fwlink/?LinkID=153328)(http://go.microsoft.com/fwlink/?LinkID=153328)。 含まれている LOB の WCF ベース アダプターに移行中の LOB アダプタについての詳細、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を参照してください、 [Microsoft BizTalk Adapter 2.0 の移行に関するホワイト ペーパー](http://go.microsoft.com/fwlink/?LinkId=158848) (http://go.microsoft.com/fwlink/?LinkId=158848)。  
  
## <a name="biztalk-accelerators"></a>BizTalk アクセラレータ  
 BizTalk アダプターは、特定のプロトコルで送信側と受信側のドキュメントを合わせて、中に BizTalk アクセラレータが特定の業界標準に従ってドキュメントの交換に合わせて設計されています。 使用可能な BizTalk アクセラレータの一覧は、次を参照してください。 [Microsoft BizTalk Server アクセラレータ](http://go.microsoft.com/fwlink/?LinkId=103609)(http://go.microsoft.com/fwlink/?LinkId=103609)。  
  
##  <a name="BKMK_InternetTrans"></a>インターネットにトランスポートを公開するときに、ドメインの構成  
 送信と受信の組織と外部の取引先間でドキュメントを容易にするためには、インターネットからアクセスできるパブリックに公開されたサイトでのトランスポートを公開する必要があります。 これらの状況では、次のドメインの構成の使用をお勧めします。  
  
-   **インターネットを提供するハウス サーバー (非武装地帯 (DMZ) と呼ばれるまたはスクリーン サブネットも)、境界ネットワーク ドメインを使用し、関連するサービスを組織で**  
  
     境界ネットワークのドメインは、インターネットに接続されたトランスポートが実行しているコンピューター間でドキュメントをルーティングする物理的な場所を格納しているサーバーを含める必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]取引先とします。 境界ネットワークのファイアウォールは、インターネットに面してトランスポートとの間の通信を許可するために必要なポートのみを開いてください。 コンピューターを実行していることはありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]境界ネットワークのドメイン内の場所、またはサーバー コンピュータでエンタープライズ シングル サインオンを受信します。 Internet Security and Acceleration Server (ISA) Server Web の発行を使用して、処理ドメインを保護するファイアウォール インターネットに接続されたファイアウォールからを/、境界ネットワークのドメイン内のトランスポートからの送信/受信ドキュメントをルーティングする必要があります、サーバー公開します。 詳細については、ISA Server の Web およびサーバーの公開を使用して、次を参照してください。 [ISA Server 2006 では公開概念](http://go.microsoft.com/fwlink/?LinkID=86359)(http://go.microsoft.com/fwlink/?LinkID=86359)。  
  
    > [!NOTE]  
    >  ドキュメントの暗号化および復号化のために公開キー基盤 (PKI) デジタル証明書を使用して、セキュリティの追加のメジャーを検討、ドキュメントの署名と送信または受信取引からドキュメントの検証 (否認不可)このドメイン内のトランスポートが直面しているインターネット経由でパートナーです。  
  
     次のトランスポートは通常、インターネットからアクセスできる境界ネットワークのドメインで使用されます。  
  
    -   FTP プロトコルを使用してドキュメントを受信する FTP-  
  
    -   SMTP プロトコルを使用してドキュメントを送信する SMTP-  
  
    -   HTTP プロトコルを使用してドキュメントを受信する HTTP-  
  
    -   SOAP を使用してドキュメントを受信する SOAP-  
  
    -   POP3 の POP3 プロトコルを使用してドキュメントを受信するには  
  
-   **ハウス、BizTalk Server が含まれているサーバーが受信し、送信ハンドラーおよび BAM ポータル サーバーに、処理ドメインを使用します。**  
  
     境界ドメインの外部に公開されたトランスポートと、処理ドメイン内の BizTalk アダプター間のドキュメント フローは、これらのドメインの間にファイアウォールを介してルーティングする必要があります。 処理ドメインを格納する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポート、受信場所、パイプライン、マップ、スキーマ、および、受信するためのアセンブリは、ルーティングし、メッセージを送信します。 処理ドメインでは、BAM ポータルのサーバーを含める必要があります。 実行しているコンピューターの台数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で、処理ドメインは、ホストの数に依存し、組織のパフォーマンスのニーズを満たすために必要なインスタンスをホスト、します。  
  
    > [!IMPORTANT]  
    >  HTTP および SOAP トランスポートには、境界のドメインでと、HTTP アダプタと SOAP アダプタ、処理ドメイン内の間を流れるトラフィックに合わせて、処理ドメインで十分な分離ホスト インスタンスを作成することを確認します。 組織と取引先間でドキュメント トラフィックの大部分は、HTTP および SOAP トランスポートを介してフロー、する場合がある処理のための十分な帯域幅ドキュメント フローを処理する、処理ドメイン内。  
  
-   **環境内の分離とセキュリティの層を提供する追加のドメインを使用します。**  
  
     これらのドメインを含める必要があります。  
  
    -   処理ドメインによって信頼されていると、メッセージを正常に処理するに必要なサービスのドメイン。 サービス ドメイン内のサーバーは通常 BizTalk オーケストレーション、パイプライン、エンタープライズ シングル サインオン (SSO) サービス、ビジネス ルール エンジンを実行し、他のビジネス プロセスを含めることができます。  
  
    -   によって使用される SQL Server を実行しているコンピューター用のデータ ドメイン[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
    -   サーバーと、組織内のインフォメーション ワーカー サービスを提供するデスクトップ コンピューターの会社のドメイン。  
  
     さまざまなことをお勧めドメイン トポロジの詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アーキテクチャを参照してください[サンプル BizTalk Server アーキテクチャ](http://go.microsoft.com/fwlink/?LinkId=155750)(http://go.microsoft.com/fwlink/?LinkId=155750)。  
  
## <a name="high-availability-considerations"></a>高可用性に関する考慮事項  
 BizTalk グループ内の複数の BizTalk server でアダプター ハンドラーのホスト インスタンスを実行して、ほとんどのアダプターの高可用性を提供できます。 こうすれば、1 つのアダプター ハンドラーのホスト インスタンスが失敗した場合、別のアダプター ハンドラーのホスト インスタンスがある処理を続行します。 ただし、これを行う例外があります。 場合によっては複数のアダプター ハンドラーのホスト インスタンスを実行すると、競合の問題が発生することができます。 たとえば、POP3 アダプターと FTP アダプターの複数のインスタンスを実行している場合、競合の問題が発生します。 このような場合は、クラスター化された BizTalk ホストでアダプター ハンドラーのホスト インスタンスを実行して高可用性をアダプターに指定できます。  
  
 詳細については、ホスト クラスタ リングを介して、アダプター ハンドラーのホスト インスタンスの高可用性を実現する、次を参照してください。[化されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](http://go.microsoft.com/fwlink/?LinkID=151284)(http://go.microsoft.com/fwlink/?LinkID=151284)。 詳細については、BizTalk ホストの高可用性を実現する、次を参照してください。 [BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)です。  
  
## <a name="performance-considerations"></a>パフォーマンスに関する考慮事項  
 **SOAP アダプターのパフォーマンスに関する考慮事項**  
  
 SOAP アダプターのパフォーマンスを最適化する方法の詳細については、次を参照してください。[構成パラメーターに影響を与えるアダプター パフォーマンス](http://go.microsoft.com/fwlink/?LinkID=154200)(http://go.microsoft.com/fwlink/?LinkID=154200)。  
  
 **MQSeries アダプターのパフォーマンスに関する考慮事項**  
  
 **トランザクションのサポートを無効にして、順次配送が不要な場合に MQSeries アダプターの受信場所**MQSeries アダプターの受信場所が設定されています、**トランザクションがサポートされている**にセットのオプション**[はい]**、または**Ordered**オプションに設定**が停止すると注文**、Microsoft 分散のコンテキストで処理される各メッセージの受信場所で取得し、トランザクション コーディネーター (MSDTC) トランザクションです。 追加があるため、MSDTC トランザクションのコンテキスト内でメッセージを処理するには、これらのオプションが有効にできません順次配送場合またはトランザクションのサポートが、MQSeries に必要でない場合に発生するオーバーヘッド アダプターの受信場所。  
  
## <a name="planning-for-ordered-message-delivery"></a>メッセージの順次配送の計画  
 メッセージの順次配送は、特定の順序でメッセージ ボックス データベースに公開されたメッセージが同じ順序で一致する各サブスクライバーに配信されたことにより、します。 メッセージの順次配送を実装する場合は、次の考慮事項が適用されます。  
  
 **メッセージの順次配送を構成します。**  
  
 メッセージの順次配送は、次の場所で構成できます。  
  
-   オーケストレーションの受信図形  
  
-   特定のアダプターの受信場所  
  
-   送信ポート  
  
 **既存のトランスポートでの配信を順序付け**  
  
 トランスポートに使用されるプロトコルによっては、特に順次配送が必要ないものもあります (FILE や HTTP など)。 ただし、このようなトランスポートを使用しても、ポートにバインドされている場合、トランスポートが順次配送は、対象としてマークし、BizTalk Server では、順次配送を適用するトランスポートを取得しません、[次へ] の送信メッセージ現在 1 つが正常に送信されるまでにより. ためには、アダプターが正常に削除メッセージ ボックス データベースから別のバッチでアダプターに次のメッセージを配信する前になるまで、BizTalk Server は 1 つのバッチおよび待機のトランスポートのアダプターに各メッセージを渡します。  
  
 **カスタム アダプターの順次配送**  
  
 カスタム受信アダプターを BizTalk Server に送信するメッセージの順序を保持する場合は、アダプターが、次の機能を使用して開発する必要があります。  
  
-   カスタムの受信メッセージのバッチを送信した後、次のバッチを送信する前に BizTalk Server から返さ BatchComplete 呼び出しのアダプターを待機する必要があります。 詳細については、次を参照してください。 [Batch-Supported 受信アダプター用のインターフェイス](http://go.microsoft.com/fwlink/?LinkId=155752)(http://go.microsoft.com/fwlink/?LinkId=155752)。  
  
-   メッセージは、パイプラインで失敗した場合、これは保留されます、できれば再開不可として。 BTS を使用します。SuspendAsNonResumable メッセージ コンテキスト プロパティに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]に適切なメッセージのフラグを設定します。  
  
    > [!NOTE]  
    >  保留したメッセージが後で再開されると、メッセージの順序が破綻してしまいます。 この動作したくない場合は、再開不可として失敗したメッセージを中断します。  
  
 **条件をエンド ツー エンドの順次メッセージ処理**  
  
 エンド ツー エンドの順次配送を実現するには、次の条件を満たす必要があります。  
  
-   メッセージは、BizTalk Server に送信するメッセージの順序を保持できるアダプターで受信されなければなりません。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、この条件を満たすアダプターとして、MSMQ および MQSeries があります。 HTTP アダプターまたは SOAP アダプターを使用して、メッセージを順次配送することもできますが、その場合は、HTTP クライアントまたは SOAP クライアント側で、正しい順序が維持されるよう配慮する必要があります (メッセージを 1 つずつ送信する)。  
  
-   持つ送信ポートでこれらのメッセージをサブスクライブする必要があります、**順次配送**オプションに設定**True**です。  
  
-   シーケンシャルなコンボイを使用するオーケストレーションを構成する必要があります、オーケストレーションがメッセージをオーケストレーションのインスタンスが 1 つだけを使用する必要がありますプロセスに使用されている場合、**順次配送**のプロパティ、オーケストレーションの受信ポートに設定する必要があります**True**です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の環境の計画](../technical-guides/planning-the-environment-for-biztalk-server.md)