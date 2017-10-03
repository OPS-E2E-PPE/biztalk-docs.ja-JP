---
title: "BizTalk Server のアダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters
- adapters, about adapters
- adapters, list of BizTalk adapters
- adapters, features
ms.assetid: 8fd279fb-2c68-4de4-a586-5a8e42a685ff
caps.latest.revision: "48"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d65d7304547df50ac14128717526fa7d55880775
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adapters-in-biztalk-server"></a>BizTalk Server のアダプター
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の主な設計目標の 1 つとして、取引先間でのビジネス ドキュメントの交換を容易にする点が挙げられます。 この目標を達成するために、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、一般的に知られているデータ プロトコルやドキュメント形式を使用して BizTalk Server と取引先との間に接続を提供するアダプタがいくつか用意されています。 このトピックでは、アダプタとアダプタを使用する理由について説明します。  
  
## <a name="what-is-an-adapter"></a>アダプタについて  
 アダプタとは、SMTP、POP3、FTP、または Microsoft メッセージ キュー (MSMQ) など一般的に知られている標準に準拠した配信メカニズムを使用して、BizTalk Server で簡単にメッセージを送受信できるようにするソフトウェア コンポーネントです。 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の進化に伴い、一般的に使用されるアプリケーションやテクノロジとすばやく接続できるアダプタのニーズが高まってきました。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次のアダプターには、「ネイティブ」または「統合」アダプタと呼びますが含まれています: ファイル、FTP、HTTP、MQSeries、MSMQ、POP3、SMTP、SOAP、Windows Sharepoint Services、および 7 つの WCF アダプター (Wcf-wshttp、Wcf-basichttp、Wcf-nettcp、Wcf-netmsmq、WCF-NetNamedPipe、Wcf-custom、および Wcf-customisolated)。 ネイティブ アダプタは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と共にインストールされます。 また、BizTalk アダプタ フレームワークを使用して、特定のソリューション用にカスタム アダプタを作成することもできます。  
  
 各ネイティブ アダプタは、特定のアドレスの特定のトランスポートからのメッセージを待機するように設計された受信場所に関連付けられています。 メッセージは、受信場所で受信された後、アダプタに渡されます。 アダプタは、データ ストリームをメッセージ (通常はメッセージのボディ部) にアタッチし、データの受信元エンドポイントに関するメタデータを追加して、そのメッセージを BizTalk メッセージング エンジンに送信します。  
  
 既定では、BizTalk 構成ウィザードを実行するときに、ネイティブ アダプタがインストールされ、各アダプタのアダプタ ハンドラが既定の構成で作成されます。  
  
 BizTalk Server 管理コンソールを使用すると、アダプター ハンドラーの既定の構成を変更するだけでなく、アダプターの送信ポートおよび受信場所を追加、削除、および変更できます。 これらのプロセスの詳細については、「関連項目」の該当するトピックを参照してください。  
  
## <a name="why-use-an-adapter"></a>アダプタを使用する理由  
 アダプタを使用すると、BizTalk Server とのメッセージの送受信が大幅に簡略化されます。 既存のインフラストラクチャで、対応する BizTalk アダプタが存在するトランスポートを使用する場合、BizTalk Server でメッセージを送受信するプロセスは、対応するトランスポート メカニズムを使用してメッセージを送信または受信するように適切なアダプタを構成するのと同様に簡単です。  
  
## <a name="summary-of-functionality-supported-by-biztalk-native-adapters"></a>BizTalk ネイティブ アダプタでサポートされている機能の概要  
 次の表は、各ネイティブ アダプタの主な利点、およびアダプタが次の機能を提供するかどうかを示しています。  
  
-   **トランザクションのサポート。** 分散トランザクション コーディネータ (DTC) トランザクションのコンテキストでドキュメントを送受信する機能です。 この機能は、メッセージの順次配送を維持し、ドキュメントが重複または消失しないようにするために必要です。  
  
-   **双方向通信のサポート (要求/応答または送信請求-応答)。** ドキュメントを送信して送信先からの応答メッセージを処理したり、ドキュメントを受信して送信元に応答メッセージを送信する機能です。  
  
-   **順次受信のサポート。** 受信したドキュメントを、受信した順番どおりに BizTalk メッセージ ボックス データベースに公開する機能です。  
  
-   **SSO が有効にします。** アダプタを使用してドキュメントの送受信を行う際に SSO 認証を使用する機能です。  
  
-   **ホスティング プロセス**アダプターが実行されるプロセスです。 *BizTalk IP* BTSNTSvc.exe プロセス内で実行中に*IIS OOP*インターネット インフォメーション サーバー (IIS) プロセスで BizTalk Server プロセスの外部で実行します。  
  
|[アダプター]|主な利点|トランザクションのサポート|双方向通信のサポート|順次受信のサポート|SSO は有効|ホスト プロセス|  
|-------------|---------------------|-------------------------|------------------------------------|-------------------------------|-----------------|---------------------|  
|ファイル|簡単に使用できます。|不可|いいえ|いいえ|不可|BizTalk IP|  
|FTP|企業間通信によく使用されています。|不可|いいえ|いいえ|はい|BizTalk IP|  
|HTTP(S)|企業間通信によく使用されています。|不可|要求 - 応答および送信請求 - 応答|不可|はい|IIS OOP|  
|SOAP|Web サービスの使用をサポートします。|不可|要求 - 応答および送信請求 - 応答|不可|はい|IIS OOP|  
|MSMQ (MSMQ)|BizTalk Server と Microsoft メッセージ キュー間での、メッセージの 1 回限りの確実な配信をサポートします。|はい|いいえ|可|不可|BizTalk IP|  
|MQ Series|BizTalk Server と IBM WebSphere MQ for Windows プラットフォームとの間でのメッセージの 1 回限りの確実な配信をサポートします。|はい|いいえ|はい|はい|BizTalk IP|  
|Windows SharePoint Services|BizTalk Server と SharePoint ドキュメント ライブラリ間の XML とバイナリのメッセージ交換を有効にします。|不可|いいえ|いいえ|不可|BizTalk IP|  
|POP3|電子メールを使用したドキュメントの受信をサポートします。|不可|いいえ|いいえ|不可|BizTalk IP|  
|SMTP (SMTP)|電子メールを使用したドキュメントの送信をサポートします。|不可|いいえ|いいえ|不可|BizTalk IP|  
|Custom|システムをサポートします。|あり (カスタム コードが必要)|あり (カスタム コードが必要)|あり (カスタム コードが必要)|あり (カスタム コードが必要)|BizTalk IP|  
|WCF-WSHttp|HTTP トランスポート経由で WS-* 標準をサポートします。|あり (WsHTTP でトランザクションをサポート) (WS トランザクションのみ)|要求 - 応答および送信請求 - 応答|不可|はい|IIS OOP|  
|WCF-BasicHttp|HTTP または HTTPS を使用して、ASMX ベースの Web サービスとクライアント、および WS-I 基本プロファイル 1.1 に準拠した他のサービスと通信します。|不可|要求 - 応答および送信請求 - 応答|不可|はい|IIS OOP|  
|WCF-NetTcp|TCP トランスポート経由で WS-* 標準をサポートします。|はい|要求 - 応答および送信請求 - 応答|不可|はい|BizTalk IP|  
|WCF-NetMsmq|Microsoft メッセージ キュー (MSMQ) をトランスポートとして利用することにより、キューをサポートします。|はい|いいえ|はい|はい|BizTalk IP|  
|WCF-NetNamedPipe|同じコンピュータにプロセス間通信用の高速トランスポートを提供します (WCF アプリケーションのみ)。|はい|要求 - 応答および送信請求 - 応答|不可|はい|BizTalk IP|  
|WCF-Custom|WCF 拡張機能を使用できるようにします。|可能。|可能。|あり (バインドでサポートされている場合)|可能。|BizTalk IP|  
|WCF-CustomIsolated|HTTP トランスポート経由で WCF 拡張機能を使用できるようにします。|可能。|可能。|不可。|可能。|IIS OOP|  
  
## <a name="line-of-business-adapters"></a>基幹業務アダプタ  
 次に、Microsoft から提供されている基幹業務 (LOB) アダプタのリストを示します。  
  
|[アダプター]|Description|Supported Versions|  
|-------------|-----------------|------------------------|  
|PeopleSoft Enterprise|BizTalk Server と PeopleSoft システム間での Component Interface (CI) メッセージの交換を有効にします。|[サポートされている基幹業務 (LOB) とエンタープライズ システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|JD Edwards OneWorld XE|BizTalk Server と JD Edwards OneWorld システム間での Business Function メッセージの交換を有効にします。|[サポートされている基幹業務 (LOB) とエンタープライズ システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|JD Edwards EnterpriseOne|BizTalk Server と JD Edwards EnterpriseOne システム間での Business Function メッセージの交換を有効にします。|[サポートされている基幹業務 (LOB) とエンタープライズ システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|TIBCO Rendezvous|BizTalk Server と TIBCO Rendezvous 間での XML メッセージとバイナリ データ形式メッセージの交換を有効にします。|[サポートされている基幹業務 (LOB) とエンタープライズ システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|TIBCO Enterprise Message Service|BizTalk Server と TIBCO EMS サーバー間での XML メッセージとバイナリ データ形式メッセージの交換を有効にします。TIBCO EMS サーバーは、緊密に統合され信頼性の高いアプリケーション インフラストラクチャを提供します。|[サポートされている基幹業務 (LOB) とエンタープライズ システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
  
 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] に付属するアダプターを使用してさまざまな基幹業務システムに接続することもできます。 詳細については[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を参照してください[http://go.microsoft.com/fwlink/p/?LinkID=188849](http://go.microsoft.com/fwlink/p/?LinkID=188849)  
  
## <a name="see-also"></a>参照  
 [アダプターをセキュリティで保護するためのベスト プラクティス](../core/best-practices-for-securing-adapters.md)   
 [作成して、アダプター ハンドラーを削除します。](../core/creating-and-deleting-adapter-handlers.md)   
 [エンタープライズ シングル サインオンを実装します。](../core/implementing-enterprise-single-sign-on.md)