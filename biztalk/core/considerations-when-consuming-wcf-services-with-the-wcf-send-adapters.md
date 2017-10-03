---
title: "送信アダプタの WCF での WCF サービスを使用する際の考慮事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- consuming, WCF services
- best practices, WCF services
- WCF services, best practices
- consuming, best practices
- WCF services, consuming
ms.assetid: 8bbcfd99-3495-458d-bd7a-6d170a29dde2
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2bb1e512b8a13c3d91b87bbfc410c3d21f334fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-when-consuming-wcf-services-with-the-wcf-send-adapters"></a>WCF サービスを WCF 送信アダプタと共に使用する場合の考慮事項
このトピックでは、WCF サービスを WCF アダプタと共に使用する際に考慮する必要がある情報を示します。  
  
## <a name="use-the-template----content-specified-by-template-option-when-sending-non-xml-content-as-solicit-messages"></a>XML 以外のコンテンツを送信請求メッセージとして送信する場合は、[テンプレート -- テンプレートで指定されたコンテンツ] オプションを使用する  
 WCF アダプターで**ボディ--BizTalk 応答メッセージ本文**(既定値) オプション文字データやビットマップ イメージなどの XML 以外のメッセージを送信することはできます。 使用することができます、**テンプレート--テンプレートで指定されたコンテンツ**WCF アダプターでは XML 以外のメッセージを送信するためのオプションです。 テンプレートを使用する方法の詳細については、次を参照してください。[に関する考慮事項と WCF サービスを公開、WCF 受信アダプタ](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)です。  
  
## <a name="the-wcf-basichttp-and-wcf-wshttp-send-ports-always-ignore-the-proxy-if-the-service-address-begins-with-httplocalhost"></a>サービスのアドレスが http://localhost で始まる場合、WCF-BasicHttp と WCF-WSHttp の送信ポートはプロキシを常に無視する  
 Wcf-basichttp と Wcf-wshttp の送信ポートはプロキシを常に無視でプロキシが構成されているかどうかに、サービス アドレスが http://localhost で始まる場合、**プロキシ**の送信ポート タブまたは**プロキシ** タブイベントの送信ハンドラー。 クライアントが同じコンピュータ上のサービスと対話するときにプロキシを通過するようにするには、(localhost ではなく) ホスト名を使用する必要があります。  
  
## <a name="the-wcf-basichttp-and-wcf-wshttp-send-adapters-suspend-the-messages-if-the-proxy-setting-is-not-correctly-configured"></a>プロキシ設定が正しく指定されていない場合、WCF-BasicHttp と WCF-WSHttp の送信アダプタはメッセージを保留する  
 Wcf-basichttp と Wcf-wshttp 送信アダプタの設定、プロキシを指定することができます、**プロキシ**の送信ポート タブまたは**プロキシ**の送信ハンドラー タブ。 このプロキシ設定が正しく指定されていない場合は、WCF アダプタによってメッセージが保留され、「メッセージを受信できるアドレスでリッスンしているエンドポイントがありませんでした」という内容のエラー メッセージがイベント ログに返されます。  
  
## <a name="setting-up-the-permissions-for-a-wcf-send-port-with-the-wcf-netmsmq-adapter"></a>WCF-NetMsmq アダプタの WCF 送信ポートに対してアクセス許可を設定する  
 WCF-NetMsmq アダプタの WCF 送信ポートは、NetMsmqBinding によって公開された Web サービスにメッセージを送信する場合、サービスのキュー マネージャによって管理されている対象キューにこのメッセージの宛先を指定します。 クライアント上のキュー マネージャーは、メッセージを転送 (または送信) キューに送ります。 転送キューは、対象キューに転送するためのメッセージを格納する、クライアント側キュー マネージャー上のキューです。  
  
 サービスのキュー マネージャーは、それが所有する対象キューに宛先指定されたメッセージを受け入れて、格納します。 次に、サービスが対象キューからの読み取り要求を行い、キュー マネージャーがメッセージをサービスに配布します。 そのため、送信ポートをホストする BizTalk ホスト インスタンスのサービス アカウントには、転送キューに書き込むためのアクセス許可を与える必要があります。  
  
## <a name="use-an-empty-xpath-expression-to-receive-a-soap-message-with-character-data-in-the-content-of-the-soap-body-element"></a>SOAP Body 要素のコンテンツに文字データが含まれた SOAP メッセージを受信するには、空の XPath 式を使用する  
 送信請求 - 応答の WCF 送信ポートは、WCF メッセージを応答メッセージとして受信できます。 SOAP のコンテンツに文字データの受信応答メッセージから BizTalk メッセージを作成する**本文**要素の次の例に示すように、おく必要があります、 **XPath 式**テキスト ボックス空の**メッセージ**WCF アダプター トランスポートのプロパティ ダイアログ ボックスのタブです。  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
    <s:Header>  
      ...  
    </s:Header>  
    <s:Body>Contoso</s:Body>  
</s:Envelope>  
```  
  
 選択した場合、**エンベロープ**または**本文**オプション、アダプターは作成されません、BizTalk メッセージの受信メッセージからです。 受信 SOAP マーシャリング プロセスでエラーとなったメッセージは保留されないので、このメッセージは保留されません。 XPath 式を使用する方法について、**メッセージ** タブを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。  
  
> [!NOTE]
>  BTSNTSvc.exe.config ファイルを構成すると、Windows SDK の TraceViewer ツール (SvcTraceViewer.exe) を使用できます。 Windows SDK の詳細についてを参照してください「の Windows SDK は」で[http://go.microsoft.com/fwlink/?LinkId=75219](http://go.microsoft.com/fwlink/?LinkId=75219)です。 TraceViewer ツールの詳細についてで「TraceViewer ツール (SvcTraceViewer.exe)」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=75218](http://go.microsoft.com/fwlink/?LinkId=75218)です。  
  
## <a name="biztalk-server-does-not-use-multi-part-message-types-and-root-elements-describing-custom-soap-headers"></a>BizTalk Server は、カスタム SOAP ヘッダーを表すルート要素とマルチパート メッセージの種類を使用しない  
 カスタム SOAP ヘッダーが定義されたメタデータに対して BizTalk WCF サービス使用ウィザードを実行した場合、生成後のスキーマには、カスタム SOAP ヘッダーを表すルート要素が生成されます。 また、カスタム SOAP ヘッダーのオーケストレーション内に、マルチパート メッセージの種類も作成されます。 BizTalk Server。 ただし、BizTalk Server は、カスタム SOAP ヘッダーを処理するために、マルチパート メッセージの種類とルート要素を使用しません。  
  
 カスタム SOAP ヘッダーにアクセスする必要がありますを使用する、 **InboundHeaders**プロパティです。 カスタム SOAP ヘッダーの受信の詳細については、次を参照してください。[公開された WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-published-wcf-services.md)です。 カスタム SOAP ヘッダーを使用するには、使用する必要があります、 **OutboundCustomHeaders**プロパティです。 カスタム SOAP ヘッダーを送信する方法の詳細については、次を参照してください。[消費される WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-wcf-services.md)です。  
  
## <a name="create-separate-host-instances-for-send-ports-that-use-different-proxy-addresses-andor-proxy-credentials"></a>プロキシ アドレス/プロキシ資格情報が異なる送信ポートごとに別のホスト インスタンスを作成する  
 WCF 送信アダプタのパフォーマンスを最大化するには、使用するプロキシ アドレス/プロキシ資格情報が異なる送信ポートごとに別のホスト インスタンスを作成することをお勧めします。 これにより、プロキシ設定の競合を防ぐことができます。  
  
## <a name="see-also"></a>参照  
 [BTSNTSvc.exe.config ファイル](../core/btsntsvc-exe-config-file.md)