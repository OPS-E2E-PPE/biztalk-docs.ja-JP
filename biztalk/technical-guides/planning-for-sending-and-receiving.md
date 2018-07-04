---
title: 送受信の計画 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d67e5f7-5127-4c1d-be20-8d8dbb538286
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a96c75ceadfeaf06dde2c3661dd00f435529dcc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009523"
---
# <a name="planning-for-sending-and-receiving"></a>送受信の計画
ほぼすべてのドキュメントで処理される[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が受信した、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信アダプター、およびから送信された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信アダプター。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプターは、いずれかで目立つように図[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境がどのアダプターやアクセラレータを使用して、これらのアダプターやアクセラレータを正しく構成する方法を決定することを事前に計画で重要です。  
  
## <a name="determining-which-adapters-and-accelerators-you-will-use"></a>どのアダプターとアクセラレータを使用するを決定します。  
 アダプターとアクセラレータのドキュメントを取引先組織との間と、BizTalk アプリケーションと、内部の間の送受信を容易にする必要がありますを決定するには、事前に取引先パートナーと連絡をとってください。ビジネス アプリケーション。 デザイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]対応の他の取引先との関係を確立することは、追加のアダプターやアクセラレータを追加するために十分な柔軟性をアーキテクチャが、今後パートナーです。  
  
## <a name="functionality-supported-by-biztalk-adapters"></a>BizTalk アダプターでサポートされる機能  
 このセクションの表では、各ネイティブ アダプタと、アダプターは、次の機能を提供するかどうかの主な利点を示します。  
  
-   **トランザクションのサポート**分散トランザクション コーディネーター (DTC) トランザクションのコンテキストでドキュメントを送受信する機能。 この機能は、メッセージの順次配送を維持し、ドキュメントが重複または消失しないようにするために必要です。  
  
    > [!NOTE]  
    >  MSDTC の問題が発生した場合は、トピックを参照[MSDTC を使用した問題のトラブルシューティング](http://go.microsoft.com/fwlink/?LinkID=154693)(http://go.microsoft.com/fwlink/?LinkID=154693)します。  
  
-   **双方向通信のサポート (要求/応答または送信請求-応答)** ドキュメントを送信し、宛先からの応答メッセージを処理するか、ドキュメントを受信し、ソースに応答メッセージを送信する機能。  
  
-   **順次受信のサポート。** ドキュメントを受信した正確な順序でメッセージ ボックス データベースに受信したドキュメントを発行する機能。  
  
    > [!NOTE]  
    >  他のアダプターができないときに、特定のアダプターは、受信場所のレベルで順序付けされたドキュメントの配信を適用できます。 順次配送を注文の受信場所のレベルでのドキュメント配信がサポートされていないアダプターの送信ポート レベルで適用できますが、パフォーマンスの低下が発生する可能性があります。 メッセージの順次配送の詳細については、トピックを参照してください。[のメッセージ配信の順序付けられた](http://go.microsoft.com/fwlink/?LinkId=155751)(http://go.microsoft.com/fwlink/?LinkId=155751)します。  
  
-   **SSO が有効にします。** アダプタを使用してドキュメントの送受信を行う際に SSO 認証を使用する機能です。  
  
|[アダプター]|主な利点|トランザクションのサポート|双方向通信のサポート|順次受信のサポート|SSO を有効になっています。|  
|-------------|---------------------|-------------------------|------------------------------------|-------------------------------|-----------------|  
|ファイル|使いやすい|いいえ|いいえ|いいえ|いいえ|  
|FTP|企業間の通信に広く使用されて|いいえ|いいえ|いいえ|はい|  
|HTTP(S)|企業間の通信に広く使用されて|いいえ|要求 - 応答および送信請求 - 応答|いいえ|はい|  
|SOAP|Web サービスの使用をサポートしています|いいえ|要求 - 応答および送信請求 - 応答|いいえ|はい|  
|MSMQ (MSMQ)|BizTalk Server と Microsoft メッセージ キュー間のメッセージの 1 回限りの配信の保証をサポートしています|はい|いいえ|はい|いいえ|  
|MQ Series|Windows プラットフォーム用の BizTalk Server と IBM WebSphere MQ 間のメッセージの 1 回限りの配信の保証をサポートしています|はい|いいえ|はい|はい|  
|SQL|直接 BizTalk Server と SQL Server データベース間の通信をサポート|はい|送信請求 - 応答のみ|いいえ|いいえ|  
|Windows SharePoint Services|XML メッセージと BizTalk Server と SharePoint ドキュメント ライブラリの間のバイナリ メッセージを交換できるように|いいえ|いいえ|いいえ|いいえ|  
|POP3|電子メールでドキュメントの受信をサポートしています|いいえ|いいえ|いいえ|いいえ|  
|SMTP (SMTP)|ドキュメントを電子メールの送信をサポート|いいえ|いいえ|いいえ|いいえ|  
|EDI |EDI 標準に準拠するビジネス ドキュメントの処理をサポート|いいえ|いいえ|いいえ|いいえ|  
|Custom|レガシ システムをサポートしています|あり (カスタム コードが必要)|あり (カスタム コードが必要)|あり (カスタム コードが必要)|あり (カスタム コードが必要)|  
|WCF-WSHttp|サポート ws-* 標準 HTTP トランスポート経由で|あり (WsHTTP でトランザクションをサポート) (WS トランザクションのみ)|要求 - 応答および送信請求 - 応答|いいえ|はい|  
|WCF-BasicHttp|ASMX ベースの Web サービスとクライアント、および、WS に準拠するその他のサービスと通信の基本プロファイル 1.1 HTTP または HTTPS を使用して|いいえ|要求 - 応答および送信請求 - 応答|いいえ|はい|  
|WCF-NetTcp|サポート ws-* 標準 TCP トランスポート経由で|はい|要求 - 応答および送信請求 - 応答|いいえ|はい|  
|WCF-NetMsmq|Microsoft メッセージ キュー (MSMQ) をトランスポートとして活用することで、キューをサポート|はい|いいえ|はい|はい|  
|WCF-NetNamedPipe|(WCF アプリケーション) の場合のみ、同じコンピューター上のプロセス間通信の高速トランスポートを提供します。|はい|要求 - 応答および送信請求 - 応答|いいえ|はい|  
|WCF-Custom|WCF の拡張機能を使用をできます。|可能。|可能。|あり (バインドでサポートされている場合)|可能。|  
|WCF-CustomIsolated|HTTP トランスポート経由で WCF 拡張機能の使用を可能に|可能。|可能。|No.|可能。|  
  
## <a name="line-of-business-adapters"></a>基幹業務アダプタ  
 次に、Microsoft から提供されている基幹業務 (LOB) アダプタのリストを示します。  
  
> [!NOTE]  
>  例外を Microsoft BizTalk Adapter v2.0 for mySAP™ Business Suite (アダプター)、基幹業務アダプターのいずれもが Windows Vista でサポートされています。  
  
|[アダプター]|説明|Supported Versions|  
|-------------|-----------------|------------------------|  
|SAP (「アダプター」とも呼ばれる)|中間ドキュメント (IDOC)、BAPI、および BizTalk Server と SAP R/3® システムの間のリモート関数呼び出し (RFC) メッセージの交換を有効にします。|SAP R/3 4.x および R/3 6.20 (Enterprise)|  
|PeopleSoft Enterprise|BizTalk Server と PeopleSoft システム間での Component Interface (CI) メッセージの交換を有効にします。|PeopleTools Version 8.17.02、8.43、8.45、8.46、および 8.48|  
|JD Edwards OneWorld XE|BizTalk Server と JD Edwards OneWorld システム間での Business Function メッセージの交換を有効にします。|B7.3.3.3 および SP23 と JDE 8.0 (B7.3.3.4)|  
|JD Edwards EnterpriseOne|BizTalk Server と JD Edwards EnterpriseOne システム間での Business Function メッセージの交換を有効にします。|8.10 & 8.11 ツール リリース 8.93、8.94、8.95、8.96|  
|ODBC Adapter for Oracle Database|Oracle Server データベースからの情報の読み取り、およびこのデータベースへの情報の書き込みを有効にします。|Oracle 8i (8.1.6.0) 9i (9.2.0.1)、または 10 g|  
|Siebel eBusiness Applications|BizTalk Server と Siebel eBusiness Application 間での Business Components メッセージと Business Service メッセージの交換を有効にします。|7.0、7.5。 * 7.7、します。\*、および 7.8 します。\*|  
|TIBCO Rendezvous|BizTalk Server と TIBCO Rendezvous 間での XML メッセージとバイナリ データ形式メッセージの交換を有効にします。|7.3|  
|TIBCO Enterprise Message Service|BizTalk Server と TIBCO EMS サーバー間での XML メッセージとバイナリ データ形式メッセージの交換を有効にします。TIBCO EMS サーバーは、緊密に統合され信頼性の高いアプリケーション インフラストラクチャを提供します。|4.2|  
|WebSphere MQ|BizTalk Server と IBM WebSphere MQ 間でのメッセージの交換を有効にします。|5.3 フィックス パック 10 以降および 6.0 の修正パック 1.1 以降|  
  
 BizTalk Server で使用可能な LOB アダプタについての詳細については、次を参照してください。[アダプターの BizTalk Server 2010 に含まれている](http://go.microsoft.com/fwlink/?LinkId=152664)(http://go.microsoft.com/fwlink/?LinkId=152664)します。  
  
## <a name="biztalk-adapter-pack"></a>BizTalk アダプター パック  
 Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] Oracle データベース、Oracle E-business Suite、SAP、Siebel、および SQL Server などの LOB アプリケーションへの接続を提供する WCF ベース アダプターが含まれます。 使用可能なアダプターの一覧については[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を参照してください[BizTalk Adapter Pack](http://go.microsoft.com/fwlink/?LinkId=152665) (<http://go.microsoft.com/fwlink/?LinkId=152665>)。  
  
> [!IMPORTANT]
>  使用することができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]で利用可能な LOB の WCF ベース アダプターの BizTalk プロジェクトに LOB アダプターの BizTalk プロジェクトを移行する移行ツール、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。 ダウンロードすることができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]からの移行ツール[BizTalk アダプター パック移行ツール](http://go.microsoft.com/fwlink/?LinkID=153328)(<http://go.microsoft.com/fwlink/?LinkID=153328>)。 含まれている LOB の WCF ベース アダプターへの移行の LOB アダプタについての詳細は、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を参照してください、 [Microsoft BizTalk Adapter 2.0 の移行に関するホワイト ペーパー](http://go.microsoft.com/fwlink/?LinkId=158848) (<http://go.microsoft.com/fwlink/?LinkId=158848>)。  
  
## <a name="biztalk-accelerators"></a>BizTalk アクセラレータ  
 BizTalk アダプターでは、特定のプロトコルでの送信と受信ドキュメントに合わせて、中に BizTalk アクセラレータが特定の業界標準に従ってドキュメントの交換に対応するために設計されています。 使用可能な BizTalk アクセラレータの一覧は、次を参照してください。 [Microsoft BizTalk Server アクセラレータ](http://go.microsoft.com/fwlink/?LinkId=103609)(http://go.microsoft.com/fwlink/?LinkId=103609)します。  
  
##  <a name="BKMK_InternetTrans"></a> トランスポートには、インターネットに公開するときに、ドメインの構成  
 送信とを組織と外部の取引先間のドキュメントの受信を容易にするためには、インターネットからアクセスできるパブリックに公開されたサイトでのトランスポートを公開する必要があります。 このような状況は、次のドメインの構成はお勧めします。  
  
- **家のサーバーにインターネット (非武装地帯 (DMZ) と呼ばれるまたはスクリーン サブネットも)、境界ネットワーク ドメインを使用し、関連する、組織のサービス**  
  
   境界ネットワークのドメインは、インターネットに接続されたトランスポートが実行しているコンピューター間でドキュメントをルーティングする物理的な場所を格納しているサーバーを含める必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と取引先パートナーとします。 境界ネットワークのファイアウォールは、インターネット接続のトランスポートとの間の通信を許可するために必要なポートのみを開いてください。 コンピューターが実行されていることはありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]境界ネットワークのドメイン内の場所、またはサーバー コンピューターのエンタープライズ シングル サインオンを受信します。 Internet Security and Acceleration Server (ISA) Server Web の発行を使用して、処理ドメインを保護するファイアウォール インターネットに接続するファイアウォールからとの間、境界ネットワークのドメイン内のトランスポートの送信/受信ドキュメントをルーティングする必要があり、サーバー公開します。 ISA Server の Web および公開サーバーの使用に関する詳細については、次を参照してください。 [ISA Server 2006 で概念を公開](http://go.microsoft.com/fwlink/?LinkID=86359)(<http://go.microsoft.com/fwlink/?LinkID=86359>)。  
  
  > [!NOTE]  
  >  ドキュメントの暗号化および復号化のために公開キー基盤 (PKI) デジタル証明書を使用して、セキュリティの追加のメジャーを検討、ドキュメントの署名と取引先からで送受信されたドキュメントの検証 (否認)このドメイン内のトランスポートに接続する、インターネット経由でパートナーです。  
  
   次のトランスポートは通常、インターネットからアクセスできる境界ネットワークのドメインで使用されます。  
  
  -   FTP プロトコルを使用してドキュメントを受信する FTP-  
  
  -   SMTP プロトコルを使用してドキュメントを送信する SMTP-  
  
  -   HTTP - HTTP プロトコルを使用してドキュメントを受信するには  
  
  -   SOAP を使用してドキュメントを受信する、SOAP  
  
  -   POP3 の POP3 プロトコルを使用してドキュメントを受信するには  
  
- **BizTalk Server が含まれているサーバーが受信し、送信ハンドラーおよび BAM ポータル サーバーに格納する、処理ドメインを使用します。**  
  
   これらのドメインの間にファイアウォールを境界ドメインの外部に公開されたトランスポートと、処理ドメイン内の BizTalk アダプター間のドキュメント フローをルーティングする必要があります。 処理ドメインを格納する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポート、受信場所、パイプライン、マップ、スキーマ、および受信するために使用されるアセンブリは、ルーティングし、メッセージを送信します。 処理ドメインでは、BAM ポータルのサーバーを含める必要があります。 実行しているコンピューターの台数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で、処理ドメインは、ホストの数に依存し、組織のパフォーマンスのニーズを満たすために必要なインスタンスをホストします。  
  
  > [!IMPORTANT]  
  >  境界ドメインの HTTP および SOAP トランスポートと、処理ドメイン内の HTTP および SOAP アダプターの間のトラフィックに対応するために、処理ドメインで十分な分離ホスト インスタンスを作成することを確認します。 お客様の組織と取引先パートナーとの間のドキュメント トラフィックの大部分が、HTTP および SOAP トランスポートを通過する場合がある処理のための十分な帯域幅ドキュメント フローを処理するために、処理ドメイン内。  
  
- **環境の分離とセキュリティのレイヤーを提供する追加のドメインを使用します。**  
  
   これらのドメインを含める必要があります。  
  
  - サービスのドメイン、処理ドメインによって信頼されていると、必要なメッセージを正常に処理します。 通常、サービス ドメイン内のサーバーは、BizTalk オーケストレーション、パイプライン、エンタープライズ シングル サインオン (SSO) サービス、ビジネス ルール エンジンを実行し、他のビジネス プロセスを含めることができます。  
  
  - 使用される SQL Server を実行しているコンピューター用のデータ ドメイン[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
  - サーバーと、組織のインフォメーション ワーカー サービスを提供するデスクトップ コンピューターの企業ドメイン。  
  
    さまざまな推奨ドメイン トポロジの詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アーキテクチャを参照してください[BizTalk Server のサンプル アーキテクチャ](http://go.microsoft.com/fwlink/?LinkId=155750)(<http://go.microsoft.com/fwlink/?LinkId=155750>)。  
  
## <a name="high-availability-considerations"></a>高可用性に関する考慮事項  
 BizTalk グループ内の複数の BizTalk server のアダプター ハンドラーのホスト インスタンスを実行して、ほとんどのアダプターの高可用性を提供できます。 これにより、1 つのアダプター ハンドラーのホスト インスタンスが失敗した場合、別のアダプター ハンドラーのホスト インスタンスは処理を続行します。 ただし、これを行う例外があります。 場合によっては複数のアダプター ハンドラーのホスト インスタンスを実行するいると、競合の問題が発生することができます。 たとえば、POP3、FTP アダプターの複数のインスタンスを実行するときに、競合の問題が発生します。 このような場合は、クラスター化された BizTalk ホストでアダプター ハンドラーのホスト インスタンスを実行して高可用性をアダプターに指定できます。  
  
 高可用性を実現するホスト クラスタ リングをアダプター ハンドラーのホスト インスタンスの詳細については、次を参照してください。[されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](http://go.microsoft.com/fwlink/?LinkID=151284)(http://go.microsoft.com/fwlink/?LinkID=151284)します。 高可用性を実現する BizTalk ホストの詳細については、次を参照してください。 [BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)します。  
  
## <a name="performance-considerations"></a>パフォーマンスに関する考慮事項  
 **SOAP アダプターのパフォーマンスに関する考慮事項**  
  
 SOAP アダプターのパフォーマンスを最適化する方法の詳細については、次を参照してください。[構成パラメーターを アダプターのパフォーマンスの影響を与える](http://go.microsoft.com/fwlink/?LinkID=154200)(http://go.microsoft.com/fwlink/?LinkID=154200)します。  
  
 **MQSeries アダプターのパフォーマンスに関する考慮事項**  
  
 **トランザクションのサポートを無効にして、アダプターの受信場所 MQSeries に必要な場合はどう順次配送**、MQSeries アダプターの受信場所が設定されています、**トランザクションがサポートされている**に設定するオプション **[はい]**、または**Ordered**オプションに設定されて**停止順序**、受信場所で取得した各メッセージは、Microsoft 分散のコンテキストで処理されますトランザクション コーディネーター (MSDTC) トランザクション。 追加があるため、MSDTC トランザクションのコンテキスト内でメッセージを処理するには、これらのオプション必要がありますいないまたは有効にする場合、順次配送トランザクションのサポートは、MQSeries に必要なときに発生するオーバーヘッド アダプターの受信場所。  
  
## <a name="planning-for-ordered-message-delivery"></a>メッセージの順次配送の計画  
 メッセージの順次配送は、特定の順序でメッセージ ボックス データベースに公開されたメッセージが同じ順序で一致する各サブスクライバーに配信されたことにより、します。 メッセージの順次配送を実装する場合は、次の考慮事項が適用されます。  
  
 **メッセージの順次配送を構成します。**  
  
 メッセージの順次配送は、次の場所で構成できます。  
  
- オーケストレーションの受信図形  
  
- 特定のアダプターの受信場所  
  
- 送信ポート  
  
  **順次配送を既存のトランスポートで**  
  
  トランスポートに使用されるプロトコルによっては、特に順次配送が必要ないものもあります (FILE や HTTP など)。 ただし、このようなトランスポートの場合でもポートにバインドする場合、トランスポートが順次配送は、対象としてマークし、BizTalk Server では、順次配送を強制により、エントリの現在の 1 つが正常に送信されるまで、トランスポートは、[次へ] の送信メッセージが取得できません. これを実現するには、まで、アダプターは、別のバッチでアダプターに次のメッセージを配信する前に、メッセージ ボックス データベースからメッセージを正常に削除が、BizTalk Server は、トランスポートのアダプターに 1 つのバッチを待機する各メッセージを渡します。  
  
  **カスタム アダプターの順次配送**  
  
  カスタム受信アダプターが BizTalk Server に送信するメッセージの順序を保持するために、アダプターが、次の機能を使用して開発する必要があります。  
  
- カスタムの受信メッセージのバッチを送信した後、次のバッチを送信する前に BizTalk Server から BatchComplete 呼び出しのアダプターを待機する必要があります。 詳細については、次を参照してください。 [Batch-Supported の受信アダプター用のインターフェイス](http://go.microsoft.com/fwlink/?LinkId=155752)(http://go.microsoft.com/fwlink/?LinkId=155752)します。  
  
- パイプラインでメッセージが失敗した場合、中断、できれば再開不可として。 BTS を使用します。SuspendAsNonResumable メッセージ コンテキスト プロパティ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]にメッセージを適切にフラグを設定します。  
  
  > [!NOTE]  
  >  保留したメッセージが後で再開されると、メッセージの順序が破綻してしまいます。 この動作をしない場合は、再開不可として失敗したメッセージを中断します。  
  
  **条件をエンド ツー エンドの順次メッセージ処理**  
  
  エンド ツー エンドの順次配送を実現するには、次の条件を満たす必要があります。  
  
- メッセージは、BizTalk Server に送信するメッセージの順序を保持できるアダプターで受信されなければなりません。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、この条件を満たすアダプターとして、MSMQ および MQSeries があります。 HTTP アダプターまたは SOAP アダプターを使用して、メッセージを順次配送することもできますが、その場合は、HTTP クライアントまたは SOAP クライアント側で、正しい順序が維持されるよう配慮する必要があります (メッセージを 1 つずつ送信する)。  
  
- これらのメッセージを持つ送信ポートをサブスクライブする必要があります、**順次配送**オプションに設定されて**True**します。  
  
- プロセスがメッセージをオーケストレーションのインスタンスが 1 つだけを使用する必要がありますにオーケストレーションを使用する場合、オーケストレーションを構成して、シーケンシャルなコンボイを使用する必要がある、**順次配送**のプロパティ、オーケストレーションの受信ポートに設定する必要があります**True**します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の環境の計画](../technical-guides/planning-the-environment-for-biztalk-server.md)