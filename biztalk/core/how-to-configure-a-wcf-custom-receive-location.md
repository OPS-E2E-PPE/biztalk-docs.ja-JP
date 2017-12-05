---
title: "Wcf-custom 受信場所を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2092cd4-6612-4ac3-81f3-dd25438837ae
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9c46434f22fe94ce046b7e7caf855d7f7a3eed4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-a-wcf-custom-receive-location"></a>WCF-Custom 受信場所を構成する方法
WCF-Custom 受信場所は、プログラムから、または BizTalk 管理コンソールを使用して構成できます。  
  
## <a name="configuration-properties"></a>構成プロパティ
  
 BizTalk エクスプローラー オブジェクト モデルにより、プログラムから受信場所を作成および構成することができます。 BizTalk エクスプ ローラー オブジェクト モデルは、公開、**という**受信場所の構成インターフェイスを持つ、 **TransportTypeData**読み取り/書き込みプロパティです。 このプロパティでは、名前と値を組み合わせた XML 文字列の形式で WCF-Custom 受信場所の構成プロパティ バッグを指定できます。 BizTalk エクスプローラ オブジェクト モデルでこのプロパティを設定に設定する必要があります、 **InboundTransportLocation**のプロパティ、**という**インターフェイスです。  
  
 **TransportTypeData**のプロパティ、**という**インターフェイスを設定する必要はありません。 このプロパティを設定しない場合、WCF-Custom アダプタでは、次の表に記載されている WCF-Custom 受信場所の構成の既定値が使用されます。  
  
 次の表に、BizTalk エクスプローラのオブジェクト モデルで WCF-Custom 受信場所用に設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|  
|-------------------|----------|-----------------|  
|**Identity**|XML Blob<br /><br /> 例:<br /><br /> &lt;id&gt;<br /><br /> &lt;userPrincipalName 値 ="username@contoso.com"/&gt;<br /><br /> &lt;/identity&gt;|この受信場所が提供するサービスの ID を指定します。 指定できる値、 **Identity**プロパティが、セキュリティ構成によって異なります。 これらの設定により、クライアントはこの受信場所を認証できます。 クライアントとサービスの間のハンドシェイク プロセスでは、Windows Communication Foundation (WCF) インフラストラクチャによって、この要素の値と予期されるサービスの ID が照合されます。<br /><br /> 既定値は空の文字列です。|  
|**BindingType**|Enum<br /><br /> -   **basicHttpBinding**<br />-   **customBinding**<br />-   **mexHttpBinding**<br />-   **mexHttpsBinding**<br />-   **mexNamedPipeBinding**<br />-   **mexTcpBinding**<br />-   **netMsmqBinding**<br />-   **netNamedPipeBinding**<br />-   **netPeerTcpBinding**<br />-   **netTcpBinding**<br />-   **wsDualHttpBinding**<br />-   **wsFederationHttpBinding**<br />-   **wsHttpBinding**|この受信場所が使用するエンドポイントに対して使用するバインドの種類を指定します。 **注:**カスタム バインドを使用する場合、 **BindingType**プロパティは、カスタム バインドで構成することができます。 カスタム バインドを使用する方法の詳細については、次を参照してください。 [WCF アダプターで WCF 機能拡張ポイントを有効にする方法](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)です。 <br /><br /> 既定値は空の文字列です。|  
|**BindingConfiguration**|XML Blob<br /><br /> 例:<br /><br /> &lt;バインディング名 ="netNamedPipeBinding"&gt;&lt;セキュリティ モード"None"=/&gt;&lt;バインド/&gt;|XML 文字列を指定し、 **\<バインディング\>**のさまざまな種類を構成するのには定義済みの Windows Communication Foundation (WCF) によって提供されるバインディング。 システム指定のバインディングおよびカスタム バインドの詳細については、適切なトピックを参照を参照してください。 **注:** BizTalk Server が構成するときのバインディング拡張要素のすべての種類をサポートしていません、 **BindingConfiguration**プロパティです。 <br /><br /> 既定値は空の文字列です。|  
|**ServiceBehaviorConfiguration**|XML Blob<br /><br /> 例:<br /><br /> &lt;動作名 ="SampleServiceBehavior"&gt;&lt;serviceMetadata httpGetEnabled"true"httpGetUrl を = ="http://mycomputer:9995/SampleMex"/&gt;&lt;serviceCredentials/&gt; &lt;/behavior&gt;|XML 文字列を指定し、 **\<動作\>**の要素、  **\<serviceBehaviors\>**  WCF の動作設定を構成するのにはサービス。 詳細については、  **\<serviceBehaviors\>** 要素では、「参照」の該当するトピックを参照してください。<br /><br /> 既定値は空の文字列です。|  
|**EndpointBehaviorConfiguration**|XML Blob<br /><br /> 例:<br /><br /> &lt;動作名 ="sampleBehavior"&gt;&lt;callbackTimeouts/&gt;&lt;/behavior&gt;|XML 文字列を指定し、 **\<動作\>**の要素、  **\<endpointBehaviors\>** の動作設定を構成するのには、WCF エンドポイントです。 詳細については、  **\<endpointBehaviors\>** 要素では、「参照」の該当するトピックを参照してください。 **注:** BizTalk Server が構成するときの動作拡張機能の要素のすべての種類をサポートしていません、 **EndpointBehaviorConfiguration**プロパティです。 <br /><br /> 既定値は空の文字列です。|  
|**CredentialType**|Enum<br /><br /> -   **None**: 送信請求、外部サービスをポーリングするメッセージをこの受信場所と任意の資格情報の送信を使用しないか、この受信場所で任意の外部サービスをポーリングする必要はありません。<br />-   **IssueTicket**: 使用するエンタープライズ シングル サインオン (SSO) SSO チケットを発行するクライアントの資格情報を取得します。 このオプションを使用する場合は、セキュリティ モードを使用して、この受信場所が SSO チケットを発行するためのユーザー アカウントを借用できるようにする必要があります。<br />-   **UserAccount**: で指定された資格情報を使用して、 **Username**と**パスワード**この受信場所の送信時のプロパティが外部サービスをポーリングするメッセージを送信請求します。<br />-   **GetCredentials**: に指定された SSO 関連アプリケーションを使用して、 **AffiliateApplicationName**送信請求メッセージを外部サービスをポーリングするときに、この受信場所のプロパティを送信します。|外部サービスをポーリングする場合に、この受信場所で使用する資格情報を指定します。<br /><br /> 既定値:**なし**|  
|**UserName**|文字列|外部サービスをポーリングして応答メッセージを取得する場合に、この受信場所で使用するユーザー名を指定します。 このプロパティは、必要なときに、 **CredentialType**プロパティに設定されている**UserAccount**です。<br /><br /> 既定値は空の文字列です。|  
|**Password**|文字列|外部サービスをポーリングして応答メッセージを取得する場合に、この受信場所で使用するパスワードを指定します。 このプロパティは、必要なときに、 **CredentialType**プロパティに設定されている**UserAccount**です。<br /><br /> 既定値は空の文字列です。|  
|**AffiliateApplicationName**|文字列|この受信場所が外部サービスをポーリングするために送信請求メッセージを送信する際に、使用する外部資格情報を返す SSO 関連アプリケーションを指定します。 指定された SSO 関連アプリケーションでは、この受信場所が実行される Windows アカウントと外部サービスのアカウントとの間のマッピングが作成されている必要があります。 このプロパティは、必要なときに、 **CredentialType**プロパティに設定されている**GetCredentials**です。<br /><br /> 既定値は空の文字列です。|  
|**OrderedProcessing**|ブール値|メッセージの処理時にメッセージの順序を保持するかどうかを指定します (NetMsmq バインドで使用)。<br /><br /> 既定値: **False**|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -SOAP のコンテンツを使用して**本文**を BizTalk メッセージのボディ部を作成する受信メッセージの要素。 **Body** 要素に複数の子要素がある場合は、最初の要素のみが BizTalk メッセージのボディ部になります。<br />-   **UseEnvelope** -全体の SOAP から BizTalk メッセージのボディ部を作成する**エンベロープ**受信メッセージのです。<br />-   **UseBodyPath** -ボディ パス式を使用して、 **InboundBodyPathExpression**プロパティを BizTalk メッセージのボディ部を作成します。 ボディ パス式は、受信メッセージの SOAP **Body** 要素のすぐ下の子要素に対して評価されます。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 使用する方法についての詳細、 **InboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のデータ選択を指定**本文**受信 WCF メッセージの要素。<br /><br /> 既定値: **UseBodyElement**|  
|**InboundBodyPathExpression**|文字列<br /><br /> 使用する方法についての詳細、 **InboundBodyPathExpression**プロパティを参照してください[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)です。|BizTalk メッセージのボディ部を作成するために使用する受信メッセージの特定の部分を示すボディ パス式を指定します。 このボディ パス式が、SOAP の直接の子要素に対して評価されます**本文**受信メッセージのノードです。 このボディ パス式で複数のノードが返される場合は、最初のノードのみが BizTalk メッセージのボディ部に対して選択されます。 このプロパティは必要な場合、 **InboundBodyLocation**プロパティに設定されている**UseBodyPath**です。<br /><br /> 既定値は空の文字列です。|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **Base64** -Base64 エンコードします。<br />-   **16 進**: 16 進エンコードします。<br />-   **文字列**: テキスト エンコード - utf-8。<br />-   **XML** -WCF アダプターは、ボディ パス式で選択されたノードの外部の XML で、BizTalk メッセージ本文を作成する**InboundBodyPathExpression**です。|Wcf-custom 受信アダプターで指定されたボディ パス式で識別されるノードのデコードに使用するエンコードの種類の指定**InboundBodyPathExpression**です。 このプロパティは必要な場合、 **InboundBodyLocation**プロパティに設定されている**UseBodyPath**です。<br /><br /> 既定値: **XML**|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -BizTalk メッセージのボディ部を使用して、SOAP のコンテンツを作成する**本文**送信応答メッセージの要素。<br />-   **UseTemplate** -で提供されているテンプレートを使用して、 **OutboundXMLTemplate** SOAP の内容を作成するプロパティ**本文**送信応答メッセージの要素。<br /><br /> 使用する方法についての詳細、 **OutboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のデータ選択を指定**本文**送信 WCF メッセージの要素。 このプロパティは、要求 - 応答の受信場所に対してのみ有効です。<br /><br /> 既定値: **UseBodyElement**|  
|**OutboundXMLTemplate**|文字列<br /><br /> 使用する方法についての詳細、 **OutboundXMLTemplate**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。|SOAP のコンテンツを XML 形式のテンプレートを指定**本文**送信応答メッセージの要素。 このプロパティは必要な場合、 **OutboundBodyLocation**プロパティに設定されている**UseTemplate**です。 このプロパティは、要求 - 応答の受信場所に対してのみ有効です。<br /><br /> 既定値は空の文字列です。|  
|**DisableLocationOnFailure**|ブール値|受信パイプラインまたはルーティングの障害によって受信処理に失敗した受信場所を無効にするかどうかを指定します。<br /><br /> 既定値: **False**|  
|**SuspendMessageOnFailure**|ブール値|受信パイプラインまたはルーティングの障害によって受信処理に失敗した要求メッセージを保留するかどうかを指定します。<br /><br /> 既定値:**は True。**|  
|**IncludeExceptionDetailInFaults**|ブール値|デバッグの目的でクライアントに返される SOAP エラーの詳細にマネージ例外情報を含めるかどうかを指定します。<br /><br /> 既定値: **False**|  
|**ReferencedBindings**|XML Blob<br /><br /> 例:<br /><br /> \<**BindingConfiguration** vt =「8」\><br /><br /> &lt;wsFederationHttpBinding&gt;<br /><br /> &lt;バインディング名"sampleBinding"を =&gt;<br /><br /> &lt;セキュリティ モード「メッセージ」を =&gt;<br /><br /> &lt;メッセージ issuedKeyType"AsymmetricKey"を =&gt;<br /><br /> &lt;発行者のアドレス ="http://www.contoso.com/samplests"バインド"wsFederationHttpBinding"bindingConfiguration を = ="**contosoSTSBinding**"/&gt;<br /><br /> &lt;/message&gt;<br /><br /> &lt;/security&gt;<br /><br /> &lt;バインド/&gt;<br /><br /> &lt;/wsFederationHttpBinding&gt;<br /><br /> \</**BindingConfiguration**\><br /><br /> \<**ReferencedBindings** vt =「8」\><br /><br /> &lt;バインド&gt;<br /><br /> &lt;wsFederationHttpBinding&gt;<br /><br /> &lt;バインディング名 ="**contosoSTSBinding**"&gt;<br /><br /> &lt;セキュリティ モード「メッセージ」を =&gt;<br /><br /> &lt;メッセージ negotiateServiceCredential ="false"&gt;<br /><br /> &lt;発行者のアドレス"http://northwind.com/samplests"bindingConfiguration を = ="**northwindBinding**"バインド"wsHttpBinding"を =&gt;<br /><br /> &lt;/issuer&gt;<br /><br /> &lt;/message&gt;<br /><br /> &lt;/security&gt;<br /><br /> &lt;バインド/&gt;<br /><br /> &lt;/wsFederationHttpBinding&gt;<br /><br /> &lt;wsHttpBinding&gt;<br /><br /> &lt;バインディング名 ="**northwindBinding**"&gt;<br /><br /> &lt;セキュリティ モード「メッセージ」を =&gt;<br /><br /> &lt;メッセージの clientCredentialType ="Certificate"/&gt;<br /><br /> &lt;/security&gt;<br /><br /> &lt;バインド/&gt;<br /><br /> &lt;/wsHttpBinding&gt;<br /><br /> &lt;/bindings&gt;<br /><br /> \</**ReferencedBindings** \> **注:** 、 **ReferencedBinding**プロパティで使用されるバインド構成を格納する必要があります、 **BindingConfiguration**プロパティです。|によって参照されるバインド構成を指定、 **bindingConfiguration**の属性、 **\<発行者\>**要素を**wsFederationHttpBinding**と**customBinding**、セキュリティ トークン サービス (STS) セキュリティ トークンを発行することを示します。 詳細については、 **\<発行者\>**要素のトピック「」を参照してください"\<発行者\>"で[http://go.microsoft.com/fwlink/?LinkId=83476](http://go.microsoft.com/fwlink/?LinkId=83476)です。<br /><br /> バインド情報を含む、 **\<発行者\>**要素を**wsFederationHttpBinding**と**customBinding**できます使用して構成、 **BindingConfiguration** Wcf-custom および Wcf-customisolated アダプターのプロパティです。 形式でこのプロパティの参照先のバインディング構成のすべてに配置する必要があります、 [\<バインド\>](http://go.microsoft.com/fwlink/?LinkID=80878)要素。 **注:**でこのプロパティを構成することはできません、**バインド**トランスポートのプロパティ ダイアログ ボックスのタブです。 インポートおよびによってこのプロパティをエクスポートすることができます、**インポート/エクスポート** タブで、Wcf-custom および Wcf-customisolated アダプターのトランスポートのプロパティ ダイアログ ボックス。 **注:** 、 **bindingConfiguration**の属性、 **\<発行者\>**要素は、このプロパティに有効なバインド名を参照する必要があります。 **注:** 、 **\<発行者\>**で参照されるバインド構成要素を指すことも t の異なるバインド構成、このプロパティがこの参照チェーンを行わない場合、循環する依存関係。 <br /><br /> 既定値は空の文字列です。|  
  
## <a name="configure-a-wcf-custom-receive-location-with-the-biztalk-administration-console"></a>WCF カスタムを構成する BizTalk 管理コンソールでの受信場所
  
 WCF-Custom 受信場所のアダプタ変数は、BizTalk 管理コンソールで設定できます。 プロパティが受信場所に設定されていない場合は、BizTalk 管理コンソールで設定された既定の受信ハンドラーの値が使用されます。  
  
> [!NOTE]
>  次の手順を実行する前に、受信ポートを追加する必要があります。 詳細については、次を参照してください。[受信ポートを作成する方法](../core/how-to-create-a-receive-port.md)です。  
  
## <a name="configure-variables-for-a-wcf-custom-receive-location"></a>Wcf-custom 受信場所の変数を構成します。  
  
1.  WCF-Custom アダプタを構成するときにカスタム バインド要素、カスタム動作要素、カスタム チャネル コンポーネントなどの WCF の機能拡張ポイントを使用する場合は、機能拡張ポイントを実装するアセンブリおよびすべての依存アセンブリを、BizTalk 処理コンピュータ (ランタイム コンピュータ) と管理コンピュータの両方のグローバル アセンブリ キャッシュに追加する必要があります。 さらに、拡張コンポーネントを machine.config ファイルに登録する必要があります。 WCF カスタム アダプターで WCF 機能拡張ポイントを使用する方法の詳細については、次を参照してください。 [WCF アダプターで WCF 機能拡張ポイントを有効にする方法](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)です。  
  
2.  BizTalk 管理コンソールで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**、し、受信場所を作成するアプリケーションを展開します。  
  
3.  BizTalk 管理コンソールの左側のウィンドウで、**[受信ポート]** ノードをクリックします。 次に右ウィンドウで、既存の受信場所に関連付けられているか、新しい受信場所に関連付ける受信ポートを右クリックし、**[プロパティ]** をクリックします。  
  
4.  **受信ポートのプロパティ**ダイアログ ボックスで、左ペインで、select、**受信場所**、右側のペインをダブルクリックして、既存の受信場所またはをクリックし **新規**新しい受信場所を作成します。  
  
5.  **受信場所のプロパティ**] ダイアログ ボックスで、**トランスポート**横**型**[ **Wcf-custom**ドロップダウン リストから一覧で、クリックして**構成**です。  
  
6.  **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、**全般** タブで、エンドポイント アドレスを構成し、サービス id を Wcf-custom 受信場所。 詳細については、**全般** タブで、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **WCF カスタム トランスポート プロパティ ダイアログ ボックス、受信、一般的な**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
7.  **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、**バインド** タブで、WCF 定義済みまたはカスタム バインディングの種類を構成します。 詳細については、**バインド** タブで、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-custom トランスポートのプロパティ ダイアログ ボックス、受信、バインディング**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
8.  **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、**動作** タブで、エンドポイントを構成し、受信場所がこのサービスの動作です。 エンドポイント動作とは、サービスまたはクライアント機能を変更または拡張する動作拡張機能の要素のセットです。 詳細については、**動作** タブで、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-custom トランスポートのプロパティ ダイアログ ボックス、受信、動作**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
9. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスの**他** タブで、この資格情報の受信場所で、外部サービスをポーリングするときに使用して、かどうか、この受信場所の構成メッセージを処理するときに、メッセージの順序が保存されます。 詳細については、**他** タブで、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **WCF カスタム トランスポート プロパティ ダイアログ ボックスで、受信、その他の**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
10. **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、**メッセージ** タブで、SOAP のデータ選択を指定**本文**要素。 詳細については、**メッセージ** タブで、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-custom トランスポートのプロパティ ダイアログ ボックス、受信、メッセージ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  
  
11. **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、**インポート/エクスポート** タブ、インポートおよびエクスポート、**アドレス (URI)**と**エンドポイント Id**プロパティを**全般** タブで、上のバインド情報、**バインディング**タブ、およびエンドポイント動作、**動作**この受信を タブ場所です。 詳細については、**インポート/エクスポート** タブで、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-custom トランスポートのプロパティ ダイアログ ボックス、受信、インポートとエクスポート**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。  

## <a name="configure-a-wcf-custom-receive-location-programmatically"></a>プログラムから Wcf-custom 受信場所を構成します。
  
 次の形式を使用してプロパティを設定できます。  
  
```  
<CustomProps>  
  <InboundBodyPathExpression vt="8" />  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <BindingConfiguration vt="8"><binding name="netNamedPipeBinding"><security mode="None" /></binding></BindingConfiguration>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <CredentialType vt="8">GetCredentials</CredentialType>  
  <Identity vt="8" />  
  <ServiceBehaviorConfiguration vt="8"><behavior name="SampleServiceBehavior"><serviceMetadata httpGetEnabled="true" httpGetUrl="http://mycomputer:9995/SampleService/Mex" /><serviceCredentials /></behavior></ServiceBehaviorConfiguration>  
  <Password vt="1" />  
  <OrderedProcessing vt="11">-1</OrderedProcessing>  
  <IncludeExceptionDetailInFaults vt="11">0</IncludeExceptionDetailInFaults>  
  <AffiliateApplicationName vt="8">SampleAffiliateApplication</AffiliateApplicationName>  
  <DisableLocationOnFailure vt="11">0</DisableLocationOnFailure>  
  <SuspendMessageOnFailure vt="11">0</SuspendMessageOnFailure>  
  <BindingType vt="8">netNamedPipeBinding</BindingType>  
  <UserName vt="8">Hello</UserName>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <EndpointBehaviorConfiguration vt="8"><behavior name="EndpointBehavior" /></EndpointBehaviorConfiguration>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
</CustomProps>  
  
```  
  
 次のコードは、WCF-Custom 受信場所の作成方法を示しています。  
  
```  
// Use BizTalk Explorer object model to create new WCF-Custom receive location   
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
string transportConfigData = @"<CustomProps>  
  <BindingConfiguration vt=""8""><binding name=""netNamedPipeBinding""><security mode=""None"" /></binding></BindingConfiguration>  
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
  
// Add a new one-way receive port  
IReceivePort receivePort = application.AddNewReceivePort(false);  
receivePort.Name = "SampleReceivePort";  
// Add a new one-way receive location  
IReceiveLocation recieveLocation = receivePort.AddNewReceiveLocation();  
recieveLocation.Name = "SampleReceiveLocation";  
// Find a receive handler for WCF-Custom   
int i = 0;  
for(i=0; i < explorer.ReceiveHandlers.Count; ++i)   
{  
    if("WCF-Custom" == explorer.ReceiveHandlers[i].TransportType.Name)  
        break;  
}  
recieveLocation.ReceiveHandler = explorer.ReceiveHandlers[i];  
recieveLocation.Address = "net.pipe://mycomputer/samplePipeName";  
recieveLocation.ReceivePipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruReceive"];  
recieveLocation.TransportType = explorer.ProtocolTypes["WCF-Custom"];  
recieveLocation.TransportTypeData = transportConfigData;  
// Save  
explorer.SaveChanges();   
```  
  
## <a name="see-also"></a>参照  
 [受信アダプターの wcf サービス メタデータの公開](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)   
 [BizTalk ホストとホスト インスタンスを管理します。](../core/managing-biztalk-hosts-and-host-instances.md)   
 [サービス アカウントとパスワードを変更する方法](../core/how-to-change-service-accounts-and-passwords.md)   
 [WCF アダプターの証明書のインストール](../core/installing-certificates-for-the-wcf-adapters.md)   
 [WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [WCF カスタム アダプターを構成します。](../core/configuring-the-wcf-custom-adapter.md)   
 [関連アプリケーションを作成する方法](../core/how-to-create-an-affiliate-application.md)   
 [\<動作\>の\<endpointBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=80879)   
 [\<バインド\>](http://go.microsoft.com/fwlink/?LinkId=80878)   
 [\<動作\>の\<serviceBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=81095)