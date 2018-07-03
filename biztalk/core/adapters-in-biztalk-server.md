---
title: BizTalk Server のアダプター |Microsoft Docs
description: BizTalk server の組み込みのアダプター、enterprise アダプター、および BizTalk Adapter Pack を含むすべての使用可能なアダプターの完全な一覧
ms.custom: ''
ms.date: 06/22/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8fd279fb-2c68-4de4-a586-5a8e42a685ff
caps.latest.revision: 48
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f19ecce5c7068f7218d9189a6dffd19e76d6211
ms.sourcegitcommit: e7609c319b64ec20bf215d17aa5ac4f9dcae52ec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36945541"
---
# <a name="adapters-in-biztalk-server"></a>BizTalk Server のアダプター
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の主な設計目標の 1 つとして、取引先間でのビジネス ドキュメントの交換を容易にする点が挙げられます。 この目標を達成するために、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、一般的に知られているデータ プロトコルやドキュメント形式を使用して BizTalk Server と取引先との間に接続を提供するアダプタがいくつか用意されています。 このトピックでは、アダプタとアダプタを使用する理由について説明します。  
  
## <a name="what-is-an-adapter"></a>アダプタについて  
 アダプタとは、SMTP、POP3、FTP、または Microsoft メッセージ キュー (MSMQ) など一般的に知られている標準に準拠した配信メカニズムを使用して、BizTalk Server で簡単にメッセージを送受信できるようにするソフトウェア コンポーネントです。 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の進化に伴い、一般的に使用されるアプリケーションやテクノロジとすばやく接続できるアダプタのニーズが高まってきました。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 次のアダプターには、「ネイティブ」または「統合」アダプタと呼びますが含まれています: ファイル、FTP、HTTP、MQSeries、MSMQ、POP3、SMTP、SOAP、Windows Sharepoint Services、および 7 つの WCF アダプター (Wcf-wshttp、Wcf-basichttp、Wcf-nettcp、Wcf-netmsmq、WCF-NetNamedPipe、Wcf-custom、および Wcf-customisolated)。 ネイティブ アダプタは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と共にインストールされます。 また、BizTalk アダプタ フレームワークを使用して、特定のソリューション用にカスタム アダプタを作成することもできます。  
  
 各ネイティブ アダプタは、特定のアドレスの特定のトランスポートからのメッセージを待機するように設計された受信場所に関連付けられています。 メッセージは、受信場所で受信された後、アダプタに渡されます。 アダプタは、データ ストリームをメッセージ (通常はメッセージのボディ部) にアタッチし、データの受信元エンドポイントに関するメタデータを追加して、そのメッセージを BizTalk メッセージング エンジンに送信します。  
  
 既定では、BizTalk 構成ウィザードを実行するときに、ネイティブ アダプタがインストールされ、各アダプタのアダプタ ハンドラが既定の構成で作成されます。  
  
 BizTalk Server 管理コンソールを使用すると、アダプター ハンドラーの既定の構成を変更するだけでなく、アダプターの送信ポートおよび受信場所を追加、削除、および変更できます。 これらのプロセスの詳細については、「関連項目」の該当するトピックを参照してください。  
  
## <a name="why-use-an-adapter"></a>アダプタを使用する理由  
 アダプタを使用すると、BizTalk Server とのメッセージの送受信が大幅に簡略化されます。 既存のインフラストラクチャで、対応する BizTalk アダプタが存在するトランスポートを使用する場合、BizTalk Server でメッセージを送受信するプロセスは、対応するトランスポート メカニズムを使用してメッセージを送信または受信するように適切なアダプタを構成するのと同様に簡単です。  
  
## <a name="functionality-support-in-built-in-adapters"></a>組み込みのアダプターでの機能のサポート  
 次の表は、各ネイティブ アダプタの主な利点、およびアダプタが次の機能を提供するかどうかを示しています。  
  
-   **トランザクションのサポート**: 分散トランザクション コーディネーター (DTC) トランザクションのコンテキストでドキュメントを送受信する機能。 この機能は、メッセージの順次配送を維持し、ドキュメントが重複または消失しないようにするために必要です。  
  
-   **双方向通信のサポート (要求/応答または送信請求-応答)** : ドキュメントを送信し、宛先からの応答メッセージを処理するか、ドキュメントを受信し、ソースに応答メッセージを送信する機能。  
  
-   **順序のサポートを受ける**: ドキュメントを受信した正確な順序で BizTalk メッセージ ボックス データベースに受信したドキュメントを発行する機能。  
  
-   **SSO が有効な**: アダプターを使用したドキュメントを送受信するときに、SSO 認証を使用する機能。  
  
-   **ホスティング プロセス**: アダプターを実行するプロセス。 *BizTalk IP* 、BTSNTSvc.exe プロセス内で実行中に*IIS OOP*インターネット インフォメーション サーバー (IIS) プロセスで BizTalk Server プロセスの外部で実行します。  
  
|[アダプター]|主な利点|トランザクションのサポート|双方向通信のサポート|順次受信のサポート|SSO は有効|ホスト プロセス|  
|---|---|---|---|---|---|---|  
|Custom|システムをサポートします。|あり (カスタム コードが必要)|あり (カスタム コードが必要)|あり (カスタム コードが必要)|あり (カスタム コードが必要)|BizTalk IP|  
|ファイル|簡単に使用できます。|いいえ|いいえ|いいえ|いいえ|BizTalk IP|  
|FTP|企業間通信によく使用されています。|いいえ|いいえ|いいえ|はい|BizTalk IP|  
|HTTP(S)|企業間通信によく使用されています。|いいえ|要求 - 応答および送信請求 - 応答|いいえ|はい|IIS OOP|  
|MSMQ (MSMQ)|BizTalk Server と Microsoft メッセージ キュー間での、メッセージの 1 回限りの確実な配信をサポートします。|はい|いいえ|はい|いいえ|BizTalk IP|  
|ロジック アプリ| 受信し、Azure ロジック アプリに送信します。 オンプレミスとクラウド環境では、このアダプターを使用してさまざまな Azure サービスにアクセスするには | はい | ワークフローのデザインに依存します。 | いいえ | いいえ |BizTalk IP を受信します。<br/>IIS OOP を送信します。| 
|MQ Series|BizTalk Server と IBM WebSphere MQ for Windows プラットフォームとの間でのメッセージの 1 回限りの確実な配信をサポートします。|はい|いいえ|はい|はい|BizTalk IP|  
|Office 365 のメール | 受信して、Office 365 の電子メールを送信 | | いいえ | いいえの順序で次のように表示します。 | いいえ | BizTalk IP| 
|Office 365 カレンダー | 受信し、Office 365 でのイベントの作成 | | いいえ | いいえの順序で次のように表示します。 | いいえ | BizTalk IP| 
|Office 365 にお問い合わせください。 | Office 365 での連絡先を作成します。 | | いいえ | いいえの順序で次のように表示します。 | いいえ | BizTalk IP| 
|POP3|電子メールを使用したドキュメントの受信をサポートします。|いいえ|いいえ|いいえ|いいえ|BizTalk IP|  
|SMTP (SMTP)|電子メールを使用したドキュメントの送信をサポートします。|いいえ|いいえ|いいえ|いいえ|BizTalk IP|  
|SOAP|Web サービスの使用をサポートします。|いいえ|要求 - 応答および送信請求 - 応答|いいえ|はい|IIS OOP|  
|Windows SharePoint Services|BizTalk Server と SharePoint ドキュメント ライブラリ間の XML とバイナリのメッセージ交換を有効にします。|いいえ|いいえ|いいえ|いいえ|BizTalk IP| 
|WCF-WSHttp|HTTP トランスポート経由で WS-* 標準をサポートします。|あり (WsHTTP でトランザクションをサポート) (WS トランザクションのみ)|要求 - 応答および送信請求 - 応答|いいえ|はい|IIS OOP|  
|WCF-BasicHttp|HTTP または HTTPS を使用して、ASMX ベースの Web サービスとクライアント、および WS-I 基本プロファイル 1.1 に準拠した他のサービスと通信します。|いいえ|要求 - 応答および送信請求 - 応答|いいえ|はい|IIS OOP|  
|WCF-NetTcp|TCP トランスポート経由で WS-* 標準をサポートします。|はい|要求 - 応答および送信請求 - 応答|いいえ|はい|BizTalk IP|  
|WCF-NetMsmq|Microsoft メッセージ キュー (MSMQ) をトランスポートとして利用することにより、キューをサポートします。|はい|いいえ|はい|はい|BizTalk IP|  
|WCF-NetNamedPipe|同じコンピュータにプロセス間通信用の高速トランスポートを提供します (WCF アプリケーションのみ)。|はい|要求 - 応答および送信請求 - 応答|いいえ|はい|BizTalk IP|  
|WCF-Custom|WCF 拡張機能を使用できるようにします。|はい|はい|あり (バインドでサポートされている場合)|はい|BizTalk IP|  
|WCF-CustomIsolated|HTTP トランスポート経由で WCF 拡張機能を使用できるようにします。|はい|はい|いいえ|はい|IIS OOP|  
  
## <a name="enterprise-adapters"></a>Enterprise アダプター  
 次に、Microsoft から提供されている基幹業務 (LOB) アダプタのリストを示します。  
  
|[アダプター]|説明|Supported Versions|  
|---|---|---|  
|PeopleSoft Enterprise|BizTalk Server と PeopleSoft システム間での Component Interface (CI) メッセージの交換を有効にします。|[サポートされている基幹業務 (LOB) とエンタープライズ システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|JD Edwards OneWorld XE|BizTalk Server と JD Edwards OneWorld システム間での Business Function メッセージの交換を有効にします。|[サポートされている基幹業務 (LOB) とエンタープライズ システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|JD Edwards EnterpriseOne|BizTalk Server と JD Edwards EnterpriseOne システム間での Business Function メッセージの交換を有効にします。|[サポートされている基幹業務 (LOB) とエンタープライズ システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|TIBCO Rendezvous|BizTalk Server と TIBCO Rendezvous 間での XML メッセージとバイナリ データ形式メッセージの交換を有効にします。|[サポートされている基幹業務 (LOB) とエンタープライズ システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|TIBCO Enterprise Message Service|BizTalk Server と TIBCO EMS サーバー間での XML メッセージとバイナリ データ形式メッセージの交換を有効にします。TIBCO EMS サーバーは、緊密に統合され信頼性の高いアプリケーション インフラストラクチャを提供します。|[サポートされている基幹業務 (LOB) とエンタープライズ システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  

## <a name="biztalk-adapter-pack"></a>BizTalk アダプター パック  
 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] に付属するアダプターを使用してさまざまな基幹業務システムに接続することもできます。 詳細については[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を参照してください[BizTalk Adapter Pack](../adapters-and-accelerators/biztalk-adapter-pack.md)します。
  
## <a name="see-also"></a>参照  
 [アダプターをセキュリティで保護するためのベスト プラクティス](../core/best-practices-for-securing-adapters.md)   
 [作成して、アダプター ハンドラーを削除します。](../core/creating-and-deleting-adapter-handlers.md)   
 [Enterprise Single Sign-On の実装](../core/implementing-enterprise-single-sign-on.md)