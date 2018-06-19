---
title: Wcf-custom 送信ポートを構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a195c047-5d5c-478b-accd-252e9dc5cfe8
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c615e2f54e1d7db9115a2607162f6eae1dffc01a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
ms.locfileid: "25975984"
---
# <a name="how-to-configure-a-wcf-custom-send-port"></a>WCF-Custom 送信ポートを構成する方法
WCF-Custom 送信ポートは、プログラムから、または BizTalk 管理コンソールを使用して構成できます。  
  
## <a name="configuration-properties"></a>構成プロパティ
  
 BizTalk エクスプ ローラー オブジェクト モデルがという名前の送信ポートのアダプターに固有のインターフェイスを公開する **ITransportInfo** を持つ、 **TransportTypeData** 読み取り/書き込みプロパティです。 このプロパティでは、XML 文字列の名前と値のペアという形式で、WCF-Custom 送信ポートの構成プロパティ バッグを指定できます。  
  
 **TransportTypeData** のプロパティ、 **ITransportInfo** インターフェイスは必要ありません。 このプロパティを設定しない場合は、アダプタで、次の表に記載されている WCF-Custom 送信ポートの構成の既定値が使用されます。  
  
 次の表に、BizTalk エクスプローラ オブジェクト モデルで WCF-Custom 送信ポート用に設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|  
|-------------------|----------|-----------------|  
|**Id**|XML Blob<br /><br /> 例:<br /><br /> &lt;id&gt;<br /><br /> &lt;userPrincipalName value="username@contoso.com" /&gt;<br /><br /> &lt;/identity&gt;|この送信ポートが必要とするサービスの ID を指定します。 これらの設定により、この送信ポートでサービスを認証できます。 クライアントとサービス間のハンドシェイク プロセスでは、WCF インフラストラクチャによって、予期されるサービスの ID がこの要素の値に一致します。 指定できる値、 **Identity** プロパティが、セキュリティ構成によって異なります。<br /><br /> 既定値は空の文字列です。|  
|**StaticAction**|文字列|指定の **SOAPAction** 送信メッセージのヘッダー フィールドです。 このプロパティは、メッセージ コンテキスト プロパティからは設定も **WCF です。アクション** パイプラインまたはオーケストレーションします。 2 つの方法でこの値を指定することができます。 シングル アクション形式とアクション マッピング形式です。 たとえば、シングル アクション形式にこのプロパティを設定する場合 http://contoso.com/Svc/Op1- 、 **SOAPAction**ヘッダーは常に送信メッセージの値に設定、このプロパティで指定します。<br /><br /> 送信アクション マッピング形式でこのプロパティを設定した場合 **SOAPAction** によってヘッダーが決定、 **BTS します。操作** コンテキスト プロパティです。 たとえば、このプロパティは、次の XML 形式に設定されている場合、 **BTS です。操作**を Op1 に設定されているプロパティ、WCF 送信アダプタを使用して http://contoso.com/Svc/Op1 アウトゴーイング**SOAPAction**ヘッダー。<br /><br /> \<BtsActionMapping\><br /><br /> \<Operation Name="Op1" Action="http://contoso.com/Svc/Op1" /\><br /><br /> \<Operation Name="Op2" Action="http://contoso.com/Svc/Op2" /\><br /><br /> \</BtsActionMapping\><br /><br /> 送信メッセージは、オーケストレーション ポートから送られてきた場合、オーケストレーション インスタンスは動的に設定、 **BTS します。操作** ポートの操作の名前を持つプロパティです。 コンテンツ ベースのルーティングと送信メッセージがルーティングされる場合は、設定、 **BTS します。操作** パイプライン コンポーネントのプロパティです。<br /><br /> 既定値は空の文字列です。|  
|**BindingType**|Enum<br /><br /> メンバー名の詳細については、 **BindingType**プロパティを参照してください、**バインディングの種類**プロパティに、 **Wcf-custom トランスポートのプロパティ ダイアログ ボックス、送信、バインディング**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。|この送信ポートが使用するエンドポイントに対して使用するバインドの種類を指定します。 **注:**  カスタム バインディングを使用する場合、 **BindingType** プロパティは、カスタム バインドで構成することができます。 カスタム バインドを使用する方法の詳細については、次を参照してください。 [WCF アダプターで WCF 機能拡張ポイントを有効にする方法](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)です。|  
|**BindingConfiguration**|XML Blob<br /><br /> 例:<br /><br /> &lt;バインディング名 ="netNamedPipeBinding"&gt;&lt;readerQuotas maxDepth「32」maxStringContentLength = =「8192」maxArrayLength「16384」maxBytesPerRead = =「4096」maxNameTableCharCount「16384」/&gt;&lt;セキュリティ モード ="None"/&gt;&lt;/binding&gt;|XML 文字列を指定し、 **\<バインディング\>** のさまざまな種類を構成するのには定義済みの Windows Communication Foundation (WCF) によって提供されるバインディング。 システムで提供されているバインドとカスタム バインドの詳細については、「関連項目」の該当するトピックを参照してください。 **注:**  BizTalk Server がで構成できるバインド拡張要素のすべての種類をサポートしていない、 **BindingConfiguration** プロパティです。 <br /><br /> 既定値は空の文字列です。|  
|**EndpointBehaviorConfiguration**|XML Blob<br /><br /> 例:<br /><br /> &lt;動作名 ="sampleBehavior"&gt;&lt;callbackTimeouts/&gt;&lt;/behavior&gt;|XML 文字列を指定し、 **\<動作\>** の要素、 **\<endpointBehaviors\>** の動作設定を構成するのには、WCF エンドポイントです。 詳細については、 **\<endpointBehaviors\>** 要素では、「参照」の該当するトピックを参照してください。 **注:**  BizTalk Server がで構成できる動作拡張機能の要素のすべての種類をサポートしていない、 **EndpointBehaviorConfiguration** プロパティです。 <br /><br /> 既定値は空の文字列です。|  
|**AffiliateApplicationName**|文字列|エンタープライズ シングル サインオン (SSO) に使用する関連アプリケーションを指定します。<br /><br /> 既定値は空の文字列です。|  
|**UseSSO**|ブール値|接続先のサーバーでの認証でクライアントの資格情報を取得する際に、シングル サインオンを使用するかどうかを指定します。<br /><br /> 既定値: **False**|  
|**ユーザー名**|文字列|接続先サーバーで認証を使用するユーザー名を指定時に、 **UseSSO** にプロパティが設定されている **False**します。 このプロパティでは domain\user 形式は使用できません。<br /><br /> 既定値は空の文字列です。|  
|**パスワード**|文字列|接続先サーバーで認証を使用するパスワードを指定するときに、 **UseSSO** にプロパティが設定されている **False**します。<br /><br /> 既定値は空の文字列です。|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -BizTalk メッセージのボディ部を使用して、SOAP のコンテンツを作成する**本文**送信メッセージの要素。<br />-   **UseTemplate** -で提供されているテンプレートを使用して、 **OutboundXMLTemplate** SOAP の内容を作成するプロパティ **本文** 、送信メッセージの要素。<br /><br /> 使用する方法についての詳細、 **OutboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のデータ選択を指定 **本文** 送信 WCF メッセージの要素。<br /><br /> 既定値: **UseBodyElement**|  
|**OutboundXMLTemplate**|文字列<br /><br /> 使用する方法についての詳細、 **OutboundXMLTemplate**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のコンテンツを XML 形式のテンプレートを指定 **本文** 、送信メッセージの要素。 このプロパティは必要な場合、 **OutboundBodyLocation** プロパティに設定されて **UseTemplate**します。<br /><br /> 既定値は空の文字列です。|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -SOAP のコンテンツを使用して**本文**を BizTalk メッセージのボディ部を作成する受信メッセージの要素。 **Body** 要素に複数の子要素がある場合は、最初の要素のみが BizTalk メッセージのボディ部になります。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br />-   **UseEnvelope** -全体の SOAP から BizTalk メッセージのボディ部を作成 **エンベロープ** 受信メッセージのです。<br />-   **UseBodyPath** -ボディ パス式を使用して、 **InboundBodyPathExpression** プロパティを BizTalk メッセージのボディ部を作成します。 ボディ パス式は、受信メッセージの SOAP **Body** 要素のすぐ下の子要素に対して評価されます。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 使用する方法についての詳細、 **InboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のデータ選択を指定 **本文** 受信 WCF メッセージの要素。<br /><br /> 既定値: **UseBodyElement**|  
|**InboundBodyPathExpression**|文字列<br /><br /> 使用する方法についての詳細、 **InboundBodyPathExpression**プロパティを参照してください[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)です。|BizTalk メッセージのボディ部を作成するために使用する受信メッセージの特定の部分を示すボディ パス式を指定します。 このボディ パス式が、SOAP の直下の子要素に対して評価されます **本文** 受信メッセージのノードです。 このボディ パス式で複数のノードが返される場合は、最初のノードのみが BizTalk メッセージのボディ部に対して選択されます。 このプロパティは必要な場合、 **InboundBodyLocation** プロパティに設定されて **UseBodyPath**します。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 既定値は空の文字列です。|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **XML**<br />-   **Base64** の Base64 エンコードします。<br />-   **16 進** : 16 進エンコードします。<br />-   **文字列** : テキスト エンコード - utf-8。<br />-   **XML** の WCF アダプターは、ボディ パス式で選択されたノードの外部の XML で BizTalk メッセージ本文を作成する **InboundBodyPathExpression**します。|指定されたボディ パスで識別されるノードに対して、Wcf-custom 送信アダプタがデコードに使用するエンコードの種類を指定 **InboundBodyPathExpression**します。 このプロパティは必要な場合、 **InboundBodyLocation** プロパティに設定されて **UseBodyPath**します。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 既定値: **XML**|  
|**PropagateFaultMessage**|ブール値<br /><br /> -   **True**にサブスクライブしているアプリケーションへの送信処理に失敗したメッセージのルーティング (別の受信ポートやオーケストレーション スケジュールなど)。<br />-   **False** -中断失敗したメッセージおよび否定受信確認応答 (NACK) を生成します。|送信処理に失敗したメッセージをルーティングまたは中断するかどうかを指定します。<br /><br /> このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 既定値: **は True。**|  
|**ReferencedBindings**|XML Blob<br /><br /> 例:<br /><br /> \<**BindingConfiguration** vt="8"\><br /><br /> &lt;wsFederationHttpBinding&gt;<br /><br /> &lt;バインディング名 ="sampleBinding"&gt;<br /><br /> &lt;セキュリティ モード"Message"を =&gt;<br /><br /> &lt;メッセージ issuedKeyType ="AsymmetricKey"&gt;<br /><br /> &lt;issuer address="http://www.contoso.com/samplests" binding="wsFederationHttpBinding" bindingConfiguration="**contosoSTSBinding**"/&gt;<br /><br /> &lt;/message&gt;<br /><br /> &lt;/security&gt;<br /><br /> &lt;バインド/&gt;<br /><br /> &lt;/wsFederationHttpBinding&gt;<br /><br /> \</**BindingConfiguration**\><br /><br /> \<**ReferencedBindings** vt="8"\><br /><br /> &lt;バインド&gt;<br /><br /> &lt;wsFederationHttpBinding&gt;<br /><br /> &lt;バインディング名 ="**contosoSTSBinding**"&gt;<br /><br /> &lt;セキュリティ モード"Message"を =&gt;<br /><br /> &lt;メッセージ negotiateServiceCredential ="false"&gt;<br /><br /> &lt;issuer address="http://northwind.com/samplests" bindingConfiguration="**northwindBinding**" binding="wsHttpBinding"&gt;<br /><br /> &lt;/issuer&gt;<br /><br /> &lt;/message&gt;<br /><br /> &lt;/security&gt;<br /><br /> &lt;バインド/&gt;<br /><br /> &lt;/wsFederationHttpBinding&gt;<br /><br /> &lt;wsHttpBinding&gt;<br /><br /> &lt;バインディング名 ="**northwindBinding**"&gt;<br /><br /> &lt;セキュリティ モード"Message"を =&gt;<br /><br /> &lt;メッセージ clientCredentialType"Certificate"=/&gt;<br /><br /> &lt;/security&gt;<br /><br /> &lt;バインド/&gt;<br /><br /> &lt;/wsHttpBinding&gt;<br /><br /> &lt;/bindings&gt;<br /><br /> \</**ReferencedBindings** \> **注:** 、 **ReferencedBinding**プロパティで使用されるバインド構成を格納する必要があります、 **BindingConfiguration**プロパティです。|によって参照されるバインド構成を指定、 **bindingConfiguration**の属性、 **\<発行者\>** 要素を**wsFederationHttpBinding**と**customBinding**、セキュリティ トークン サービス (STS) セキュリティ トークンを発行することを示します。 詳細については、 **\<発行者\>** 要素のトピック「」を参照してください"\<発行者\>"で[ http://go.microsoft.com/fwlink/?LinkId=83476](http://go.microsoft.com/fwlink/?LinkId=83476)です。<br /><br /> バインド情報を含む、 **\<発行者\>** 要素を**wsFederationHttpBinding**と**customBinding**できます使用して構成、 **BindingConfiguration** Wcf-custom および Wcf-customisolated アダプターのプロパティです。 形式でこのプロパティの参照先のバインディング構成のすべてに配置する必要があります、 [\<バインド\>](http://go.microsoft.com/fwlink/?LinkID=80878)要素。 **注:**  でこのプロパティを構成することはできません、 **バインド** トランスポートのプロパティ ダイアログ ボックスのタブをクリックします。 インポートおよびによってこのプロパティをエクスポートすることができます、 **インポート/エクスポート** Wcf-custom および Wcf-customisolated アダプターのトランスポートのプロパティ ダイアログ ボックスのタブをクリックします。 **注:** 、 **bindingConfiguration**の属性、 **\<発行者\>** 要素は、このプロパティに有効なバインド名を参照する必要があります。 **注:** 、 **\<発行者\>** で参照されるバインド構成要素を指すことも t の異なるバインド構成プロパティこの参照チェーンが循環を行わなかった場合依存関係です。 <br /><br /> 既定値は空の文字列です。|  
  
## <a name="configure-a-wcf-custom-send-port-with-the-biztalk-administration-console"></a>BizTalk 管理コンソールを使用する Wcf-custom 送信ポートを構成します。
  
 BizTalk 管理コンソールで、WCF-Custom 送信ポート アダプタの変数を設定できます。 プロパティが送信ポートに設定されていない場合は、上の表に記載されている WCF-Custom 送信ポートの構成の既定値が使用されます。  
  
## <a name="configure-variables-for-a-wcf-custom-send-port"></a>Wcf-custom 送信ポートの変数を構成します。  
  
1.  WCF-Custom アダプタを構成するときにカスタム バインド要素、カスタム動作要素、カスタム チャネル コンポーネントなどの WCF の機能拡張ポイントを使用する場合は、機能拡張ポイントを実装するアセンブリおよびすべての依存アセンブリを、BizTalk 処理コンピュータ (ランタイム コンピュータ) と管理コンピュータの両方のグローバル アセンブリ キャッシュに追加する必要があります。 さらに、拡張コンポーネントを machine.config ファイルに登録する必要があります。 WCF カスタム アダプターで WCF 機能拡張ポイントを使用する方法の詳細については、次を参照してください。 [WCF アダプターで WCF 機能拡張ポイントを有効にする方法](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)です。  
  
2.  BizTalk 管理コンソールで、新しい送信ポートを作成するか、既存の送信ポートをダブルクリックして変更します。 詳細については、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。 すべての送信ポートのオプションを構成し、指定**Wcf-custom**の**型**オプション、**トランスポート**のセクションで、**全般** タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
3.  **全般**  タブの 、 **トランスポート**  をクリックして、 **構成** ボックスの横に **型**します。  
  
4.  **Wcf-custom トランスポートのプロパティ**  ダイアログ ボックスの 、 **全般**  タブで、エンドポイント アドレス、サービス id を構成して、 **SOAPAction** WCF カスタム ヘッダーの送信ポート。 詳細については、**全般** タブで、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-custom トランスポートのプロパティ ダイアログ ボックス、送信、一般的な**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
5.  **WCF カスタム トランスポート プロパティ**  ダイアログ ボックスの 、 **バインド**  タブで、さまざまな種類の定義済みまたはカスタム WCF バインドを構成します。 詳細については、**バインド** タブで、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-custom トランスポートのプロパティ ダイアログ ボックス、送信、バインディング**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
6.  **WCF カスタム トランスポート プロパティ**  ダイアログ ボックスの 、 **動作**  タブで、この送信ポートのエンドポイントの動作を構成します。 エンドポイントの動作は、変更したり、サービスまたはクライアントの機能を拡張する動作拡張要素のセットです。 詳細については、**動作** タブで、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-custom トランスポートのプロパティ ダイアログ ボックス、送信、動作**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
7.  **Wcf-custom トランスポートのプロパティ**  ダイアログ ボックスで、 **資格情報**  タブで、メッセージを送信するときに使用される資格情報を指定します。 詳細については、**資格情報** タブで、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスを参照してください、 **Wcf-custom トランスポートのプロパティ ダイアログ ボックス、送信、資格情報**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
8.  **Wcf-custom トランスポートのプロパティ**  ダイアログ ボックスで、 **メッセージ**  タブで、SOAP のデータ選択を指定 **本文** 要素。 詳細については、**メッセージ** タブで、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-custom トランスポートのプロパティ ダイアログ ボックス、送信、メッセージ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
9. **Wcf-custom トランスポートのプロパティ**  ダイアログ ボックスの 、 **インポート/エクスポート**  タブで、インポートおよびエクスポート、 **アドレス (URI)** と **エンドポイント Id** プロパティを **全般**  タブで、上のバインド情報、 **バインディング**  タブ、およびエンドポイント動作、 **動作** この送信ポートのタブをクリックします。 詳細については、**インポート/エクスポート** タブで、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-custom トランスポートのプロパティ ダイアログ ボックス、送信、インポートとエクスポート**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
## <a name="configure-a-wcf-custom-send-port-programmatically"></a>プログラムから Wcf-custom 送信ポートを構成します。  
  
 次の形式を使用してプロパティを設定できます。  
  
```  
<CustomProps>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <InboundBodyPathExpression vt="8" />  
  <EndpointBehaviorConfiguration vt="8"><behavior name="sampleBehavior"><callbackTimeouts /></behavior></EndpointBehaviorConfiguration>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
  <StaticAction vt="8">http://www.northwindtraders.com/Service/Operation</StaticAction>  
  <BindingConfiguration vt="8"><binding name="NetNamedPipeOrderProcessService.OrderProcessServieEndpoint"><readerQuotas maxDepth="32" maxStringContentLength="8192" maxArrayLength="16384" maxBytesPerRead="4096" maxNameTableCharCount="16384" /><security mode="None" /></binding></BindingConfiguration>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <UseSSO vt="11">0</UseSSO>  
  <AffiliateApplicationName vt="8" />  
  <BindingType vt="8">netNamedPipeBinding</BindingType>  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <UserName vt="8" />  
  <PropagateFaultMessage vt="11">-1</PropagateFaultMessage>  
</CustomProps>  
  
```  
  
 次のコードは、WCF-Custom 送信ポートの作成方法を示しています。  
  
```  
// Use BizTalk Explorer object model to create new WCF-Custom send port.  
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
string transportConfigData = @"<CustomProps>  
                                 <StaticAction vt=""8"">http://www.northwindtraders.com/Service/Operation</StaticAction>  
                                 <EndpointBehaviorConfiguration vt=""8""><behavior name=""sampleBehavior""><callbackTimeouts /></behavior></EndpointBehaviorConfiguration>  
                                 <BindingType vt=""8"">netNamedPipeBinding</BindingType>  
                               </CustomProps>";  
//requires project reference to \Program Files\Microsoft BizTalk Server 2009\Developer Tools\Microsoft.BizTalk.ExplorerOM.dll  
BtsCatalogExplorer explorer = new Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer();  
explorer.ConnectionString = connectionString;  
// Add a new BizTalk application  
Application application = explorer.AddNewApplication();  
application.Name = "SampleBizTalkApplication";  
// Save  
explorer.SaveChanges();  
  
// Add a new static one-way send port  
SendPort sendPort = application.AddNewSendPort(false, false);   
sendPort.Name = "SampleSendPort";  
sendPort.PrimaryTransport.TransportType = explorer.ProtocolTypes["WCF-Custom"];  
sendPort.PrimaryTransport.Address = "net.pipe://mycomputer/private/samplequeue";  
sendPort.PrimaryTransport.TransportTypeData = transportConfigData; // propertyData; // need to change  
sendPort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  
// Save  
explorer.SaveChanges();  
```  
  
## <a name="see-also"></a>参照  
 [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)   
 [WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [WCF アダプターの証明書のインストール](../core/installing-certificates-for-the-wcf-adapters.md)   
 [WCF カスタム アダプターを構成します。](../core/configuring-the-wcf-custom-adapter.md)   
 [WCF アダプター コンテキスト プロパティを使用して動的送信ポートの構成](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)   
 [\<bindings\>](http://go.microsoft.com/fwlink/?LinkId=80878)   
 [\<動作\>の\<endpointBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=80879)