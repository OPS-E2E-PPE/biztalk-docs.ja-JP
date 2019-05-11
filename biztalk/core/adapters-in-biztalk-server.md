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
ms.openlocfilehash: 8c21203f0bcadee50142b7f3021fdfb5f1b6949f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361057"
---
# <a name="adapters-in-biztalk-server"></a>BizTalk Server のアダプター
主な設計目標の 1 つ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]取引先間でのビジネス ドキュメントの交換を容易にします。 この目標を達成するために[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ドキュメント形式よくを使用して取引先 BizTalk Server との間の接続データ プロトコルの認識を提供するいくつかのアダプターが含まれています。 このトピックではどのようなアダプターがいるし、アダプターを使用する理由。  
  
## <a name="what-is-an-adapter"></a>アダプターとは何ですか。  
 アダプターを簡単にメッセージを送信または SMTP、POP3、FTP、または Microsoft メッセージ キュー (MSMQ) などの共通に認識される標準に準拠した配信メカニズムで BizTalk Server にメッセージを受信できるようにするソフトウェア コンポーネントです。 マイクロソフトとして[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]進化してきた、必要があるすばやく一般的との接続を有効にするアダプター アプリケーションで使用され、テクノロジが増加します。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 次のアダプターには、「ネイティブ」または「統合」アダプタと呼びますが含まれます。ファイル、FTP、HTTP、MQSeries、MSMQ、POP3、SMTP、SOAP、Windows Sharepoint Services、および 7 つの WCF アダプター (Wcf-wshttp、Wcf-basichttp、Wcf-nettcp、Wcf-netmsmq、Wcf-netnamedpipe、Wcf-custom、および Wcf-customisolated)。 ネイティブ アダプターがインストールされて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 BizTalk アダプター フレームワークを使用して、特定のソリューションのカスタム アダプターを作成することもできます。  
  
 ネイティブ アダプターのそれぞれに関連付けられている受信場所が特定のアドレスで特定のトランスポートからのメッセージをリッスンするように設計されています。 受信場所でメッセージを受信すると後、は、アダプターに渡されます。 アダプターは、メッセージ (通常、メッセージのボディ部) にデータ ストリームをアタッチします。 から受信したデータがあり、BizTalk メッセージング エンジンにそのメッセージを送信エンドポイントに関するメタデータを追加します。  
  
 既定では、BizTalk 構成ウィザードを実行すると、ウィザードが、ネイティブ アダプターがインストールされ、それぞれの既定の構成でアダプター ハンドラーを作成します。  
  
 BizTalk Server 管理コンソールを使用して、することができます、アダプター ハンドラーの既定の構成を変更だけでなく追加、削除、および送信ポートを変更およびアダプターの受信場所。 これらのプロセスの詳細については、「参照」の該当するトピックを参照してください。  
  
## <a name="why-use-an-adapter"></a>アダプターを使用する理由  
 BizTalk Server の内外に、大幅にアダプターを使用して、メッセージの転送が簡略化します。 を、既存のインフラストラクチャが存在では、対応する BizTalk アダプターのトランスポートのいずれかを使用する場合は、送信または受信する適切なアダプターを構成するだけで、プロセスにメッセージを送信または BizTalk Server からメッセージを受信対応するトランスポート メカニズムでのメッセージ。  
  
## <a name="functionality-support-in-built-in-adapters"></a>組み込みのアダプターでの機能のサポート  
 次の表では、各ネイティブ アダプタと、アダプターは、次の機能を提供するかどうかの主な利点を示します。  
  
-   **トランザクションのサポート**:分散トランザクション コーディネーター (DTC) トランザクションのコンテキストでドキュメントを送受信する機能。 この機能は、メッセージの順次配送を維持し、ドキュメントが重複または消失しないようにするために必要です。  
  
-   **双方向通信のサポート (要求/応答または送信請求-応答)** :ドキュメントを送信し、宛先からの応答メッセージを処理するか、ドキュメントを受信し、ソースに応答メッセージを送信する権限です。  
  
-   **順序のサポートを受ける**:ドキュメントを受信した正確な順序で BizTalk メッセージ ボックス データベースに受信したドキュメントを発行する機能。  
  
-   **SSO が有効な**:アダプタを使用してドキュメントの送受信を行う際に SSO 認証を使用する機能です。  
  
-   **ホスティング プロセス**:アダプターが実行されるプロセスです。 *BizTalk IP* 、BTSNTSvc.exe プロセス内で実行中に*IIS OOP*インターネット インフォメーション サーバー (IIS) プロセスで BizTalk Server プロセスの外部で実行します。  
  
|[アダプター]|主な利点|トランザクションのサポート|双方向通信のサポート|順次受信のサポート|SSO を有効になっています。|ホスト プロセス|  
|---|---|---|---|---|---|---|  
|カスタム|システムをサポートしています。|あり (カスタム コードが必要)|あり (カスタム コードが必要)|あり (カスタム コードが必要)|あり (カスタム コードが必要)|BizTalk IP|  
|ファイル|使いやすさ。|いいえ|いいえ|いいえ|いいえ|BizTalk IP|  
|FTP|企業間の通信に広く使用されています。|いいえ|いいえ|いいえ|はい|BizTalk IP|  
|HTTP(S)|企業間の通信に広く使用されています。|いいえ|要求 - 応答および送信請求 - 応答|いいえ|はい|IIS OOP|  
|MSMQ (MSMQ)|確実な BizTalk Server と Microsoft メッセージ キュー間のメッセージの 1 回限りの配信をサポートします。|はい|いいえ|はい|いいえ|BizTalk IP|  
|ロジック アプリ| 受信し、Azure ロジック アプリに送信します。 オンプレミスとクラウド環境では、このアダプターを使用してさまざまな Azure サービスにアクセスするには | はい | ワークフローのデザインに依存します。 | いいえ | いいえ |表示されます。BizTalk IP<br/>送信：IIS OOP| 
|MQ Series|サポートは、Windows プラットフォーム用の BizTalk Server と IBM WebSphere MQ 間のメッセージの 1 回限りの配信を保証します。|はい|いいえ|はい|はい|BizTalk IP|  
|Office 365 のメール | 受信して、Office 365 の電子メールを送信 | | いいえ | いいえの順序で次のように表示します。 | いいえ | BizTalk IP| 
|Office 365 カレンダー | 受信し、Office 365 でのイベントの作成 | | いいえ | いいえの順序で次のように表示します。 | いいえ | BizTalk IP| 
|Office 365 にお問い合わせください。 | Office 365 での連絡先を作成します。 | | いいえ | いいえの順序で次のように表示します。 | いいえ | BizTalk IP| 
|POP3|電子メールでドキュメントの受信をサポートします。|いいえ|いいえ|いいえ|いいえ|BizTalk IP|  
|SMTP (SMTP)|ドキュメントを電子メールの送信をサポートします。|いいえ|いいえ|いいえ|いいえ|BizTalk IP|  
|SOAP|Web サービスの使用をサポートしています。|いいえ|要求 - 応答および送信請求 - 応答|いいえ|はい|IIS OOP|  
|Windows SharePoint Services|XML メッセージと BizTalk Server と SharePoint ドキュメント ライブラリの間のバイナリ メッセージの交換を有効にします。|いいえ|いいえ|いいえ|いいえ|BizTalk IP| 
|WCF-WSHttp|サポート ws-* 標準 HTTP トランスポートを経由します。|あり (WsHTTP でトランザクションをサポート) (WS トランザクションのみ)|要求 - 応答および送信請求 - 応答|いいえ|はい|IIS OOP|  
|WCF-BasicHttp|ASMX ベースの Web サービスとクライアント、および、WS に準拠するその他のサービスと通信の基本プロファイル 1.1 HTTP または HTTPS を使用します。|いいえ|要求 - 応答および送信請求 - 応答|いいえ|はい|IIS OOP|  
|WCF-NetTcp|サポート ws-* 標準 TCP トランスポートを経由します。|はい|要求 - 応答および送信請求 - 応答|いいえ|はい|BizTalk IP|  
|WCF-NetMsmq|Microsoft メッセージ キュー (MSMQ) をトランスポートとして使用したキューをサポートします。|はい|いいえ|はい|はい|BizTalk IP|  
|WCF-NetNamedPipe|(WCF アプリケーション) の場合のみ、同じコンピューター上のプロセス間通信の高速トランスポートを提供します。|はい|要求 - 応答および送信請求 - 応答|いいえ|はい|BizTalk IP|  
|WCF-Custom|WCF の拡張機能を使用できるようにします。|はい|はい|あり (バインドでサポートされている場合)|はい|BizTalk IP|  
|WCF-CustomIsolated|HTTP トランスポート経由で WCF 拡張機能を使用できるようにします。|はい|[はい]|いいえ|はい|IIS OOP|  
  
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
 同梱されているアダプターを使用することもできます。[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]さまざまな基幹業務システムに接続します。 詳細については[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を参照してください[BizTalk Adapter Pack](../adapters-and-accelerators/biztalk-adapter-pack.md)します。
  
## <a name="see-also"></a>参照  
 [アダプターをセキュリティで保護するためのベスト プラクティス](../core/best-practices-for-securing-adapters.md)   
 [作成して、アダプター ハンドラーを削除します。](../core/creating-and-deleting-adapter-handlers.md)   
 [Enterprise Single Sign-On の実装](../core/implementing-enterprise-single-sign-on.md)