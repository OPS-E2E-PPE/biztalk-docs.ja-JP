---
title: 送信アダプターを WCF を使用した WCF サービスの使用時の考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- consuming, WCF services
- best practices, WCF services
- WCF services, best practices
- consuming, best practices
- WCF services, consuming
ms.assetid: 8bbcfd99-3495-458d-bd7a-6d170a29dde2
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ab74cc71cf083ac8f6dd33a75cd7fe3be3fb00d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390381"
---
# <a name="considerations-when-consuming-wcf-services-with-the-wcf-send-adapters"></a>送信アダプターを WCF を使用した WCF サービスの使用時の考慮事項
このトピックでは、WCF アダプターで WCF サービスを使用する際に考慮に入れる必要のある情報を提供します。  
  
## <a name="use-the-template----content-specified-by-template-option-when-sending-non-xml-content-as-solicit-messages"></a>XML 以外のコンテンツと、送信請求メッセージを送信するときに、テンプレート--コンテンツ テンプレートで指定された"オプションを使用します。  
 WCF アダプターで**ボディ--BizTalk 応答メッセージ本文**(既定値) オプションは文字データやビットマップ イメージなどの XML 以外のメッセージの送信を許可していません。 使用することができます、**テンプレート--テンプレートで指定されたコンテンツ**XML 以外のメッセージを送信する WCF アダプターのオプション。 テンプレートを使用する方法の詳細については、次を参照してください。[に関する考慮事項と WCF サービスを公開、WCF 受信アダプタ](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)します。  
  
## <a name="the-wcf-basichttp-and-wcf-wshttp-send-ports-always-ignore-the-proxy-if-the-service-address-begins-with-httplocalhost"></a>Wcf-basichttp と Wcf-wshttp の送信ポートは、サービス アドレスが始まる場合に、プロキシを無視 http://localhost  
 Wcf-basichttp と Wcf-wshttp の送信ポートが常に、サービスのアドレスが始まる場合に、プロキシが無視 http://localhostでプロキシが構成されているかどうか、**プロキシ**の送信ポート タブまたは**プロキシ**のタブ送信ハンドラー。 クライアントが同じコンピューター上のサービスとの通信時にプロキシを経由する場合は、ホスト名 (なく localhost) を使用する必要があります。  
  
## <a name="the-wcf-basichttp-and-wcf-wshttp-send-adapters-suspend-the-messages-if-the-proxy-setting-is-not-correctly-configured"></a>Wcf-basichttp と Wcf-wshttp 送信アダプターは、プロキシの設定が正しく構成されていない場合に、メッセージを中断  
 プロキシ、Wcf-basichttp と Wcf-wshttp 送信アダプターの設定を指定することができます、**プロキシ**の送信ポート タブまたは**プロキシ**の送信ハンドラー タブ。 このプロキシ設定が正しく構成されていない場合、WCF アダプタは、メッセージを中断し、イベント ログに「をリッスンしているエンドポイントにメッセージを受信しない可能性がありますがあります」エラー メッセージを受信します。  
  
## <a name="setting-up-the-permissions-for-a-wcf-send-port-with-the-wcf-netmsmq-adapter"></a>Wcf-netmsmq アダプターを使用した送信ポートの WCF のアクセス許可の設定  
 Wcf-netmsmq アダプタの WCF 送信ポートは、NetMsmqBinding によって公開された WCF サービスにメッセージを送信するときに、サービスのキュー マネージャーによって管理されている対象のキューにメッセージを説明します。 クライアント上のキュー マネージャーは、メッセージを転送 (または送信) キューに送ります。 転送キューは、ターゲット キューに転送するためのメッセージを格納する、クライアント側キュー マネージャー上のキューです。  
  
 サービスのキュー マネージャーは、それが所有するターゲット キューに宛先指定されたメッセージを受け入れて、格納します。 次に、サービスがターゲット キューからの読み取り要求を行い、キュー マネージャーがメッセージをサービスに配布します。 このため、送信ポートをホストする BizTalk ホスト インスタンスのサービス アカウントは、転送キューに書き込むアクセス許可が必要です。  
  
## <a name="use-an-empty-xpath-expression-to-receive-a-soap-message-with-character-data-in-the-content-of-the-soap-body-element"></a>SOAP Body 要素のコンテンツに文字データの SOAP メッセージを受信するのに空の XPath 式を使用します。  
 送信請求-応答 WCF 送信ポートは、応答メッセージとして、WCF メッセージを受信できます。 SOAP のコンテンツに文字データの受信応答メッセージから BizTalk メッセージを作成する**本文**ままにする必要があります要素の次の例に示すよう、 **XPath 式**テキスト ボックス空で、**メッセージ**WCF アダプター トランスポートのプロパティ ダイアログ ボックスのタブ。  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
    <s:Header>  
      ...  
    </s:Header>  
    <s:Body>Contoso</s:Body>  
</s:Envelope>  
```  
  
 選択した場合、**エンベロープ**または**本文**オプション、受信メッセージから、アダプターは BizTalk メッセージを作成はできません。 受信 SOAP マーシャリング プロセスでエラーとなったメッセージは保留されないので、このメッセージは保留されません。 XPath 式を使用する方法について、**メッセージ** タブを参照してください[WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)します。  
  
> [!NOTE]
>  BTSNTSvc.exe.config ファイルを構成すると、Windows SDK の TraceViewer ツール (SvcTraceViewer.exe) を使用できます。 Windows SDK の詳細についてを参照してください"What is Windows SDK の新" [ http://go.microsoft.com/fwlink/?LinkId=75219](http://go.microsoft.com/fwlink/?LinkId=75219)します。 TraceViewer ツールの詳細についてを参照してください「TraceViewer ツール (SvcTraceViewer.exe)」 [ http://go.microsoft.com/fwlink/?LinkId=75218](http://go.microsoft.com/fwlink/?LinkId=75218)します。  
  
## <a name="biztalk-server-does-not-use-multi-part-message-types-and-root-elements-describing-custom-soap-headers"></a>BizTalk Server では、カスタム SOAP ヘッダーを表すルート要素とマルチパート メッセージの種類は使用しません  
 BizTalk WCF サービスを実行する場合、メタデータ、カスタム SOAP ヘッダーが定義されているウィザードの使用のウィザードをカスタム SOAP ヘッダーを表す、生成されたスキーマにルート要素を生成します。 ウィザードには、カスタム SOAP ヘッダーのオーケストレーションでマルチパート メッセージの種類も作成します。 BizTalk Server です。 ただし、BizTalk Server は、カスタム SOAP ヘッダーを処理するためにルート要素とマルチパート メッセージの種類を使用しません。  
  
 カスタム SOAP ヘッダーにアクセスするに使用する必要があります、 **InboundHeaders**プロパティ。 カスタム SOAP ヘッダーの受信についての詳細については、次を参照してください。[公開された WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-published-wcf-services.md)します。 カスタム SOAP ヘッダーを使用する必要がありますを使用する、 **OutboundCustomHeaders**プロパティ。 カスタム SOAP ヘッダーを送信する方法の詳細については、次を参照してください。[で WCF サービスの使用の SOAP ヘッダー](../core/soap-headers-with-consumed-wcf-services.md)します。  
  
## <a name="create-separate-host-instances-for-send-ports-that-use-different-proxy-addresses-andor-proxy-credentials"></a>別のプロキシ アドレス/プロキシ資格情報を使用する送信ポートの別のホスト インスタンスを作成します。  
 できるだけを実現するためにパフォーマンスを WCF 送信アダプタ、別のプロキシ アドレス/プロキシ資格情報を使用する送信ポートの別のホスト インスタンスを作成することをお勧めします。 プロキシ設定の競合を回避できます。  
  
## <a name="see-also"></a>参照  
 [BTSNTSvc.exe.config ファイル](../core/btsntsvc-exe-config-file.md)