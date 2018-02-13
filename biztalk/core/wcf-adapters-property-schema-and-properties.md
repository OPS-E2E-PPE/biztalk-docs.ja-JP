---
title: "WCF アダプター プロパティ スキーマおよびプロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/09/2018
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2093745e-86c0-4276-a7cc-a0187391ca4a
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04bb48f54347eabeb886d91fa245bae18c34de55
ms.sourcegitcommit: 50798e04fdcaf5dce5288aa18608e2a981b162fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2018
---
# <a name="wcf-adapters-property-schema-and-properties"></a>WCF アダプタ プロパティ スキーマおよびプロパティ
WCF アダプタ プロパティ スキーマで昇格させたプロパティについて確認します。 WCF アダプタは、アプリケーションで使用できるプロパティに値を割り当てます。 また、WCF アダプタは、カスタム プロパティを BizTalk メッセージ コンテキストに書き込むが昇格させないメカニズムと、カスタム プロパティを BizTalk メッセージ コンテキストに昇格させるメカニズムを提供します。 詳細については、次を参照してください。[公開された WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-published-wcf-services.md)です。  

## <a name="promoted-properties"></a>昇格させたプロパティ  
**名前空間:** http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties  

#### <a name="action"></a>操作
指定の **SOAPAction** 送信メッセージのヘッダー フィールドです。 2 つの方法でこの値を指定することができます。 シングル アクション形式とアクション マッピング形式です。 シングル アクション形式では、このプロパティを設定するかどうかは、http://contoso.com/Svc/Op1 など —、 **SOAPAction**ヘッダーは常に送信メッセージの設定をこのプロパティで指定された値にします。

送信アクション マッピング形式でこのプロパティを設定した場合 **SOAPAction** によってヘッダーが決定、 **BTS します。操作** コンテキスト プロパティです。 たとえば、次の XML 形式にこのプロパティが設定されている場合、 **BTS します。操作** を Op1 に設定されているプロパティ、WCF 送信アダプタを使用して `http://contoso.com/Svc/Op1` を送信 **SOAPAction** ヘッダー。

```
<BtsActionMapping>
<Operation Name="Op1" Action="http://contoso.com/Svc/Op1">
<Operation Name="Op2" Action="http://contoso.com/Svc/Op2">
</BtsActionMapping>
```

送信メッセージは、オーケストレーション ポートから送られてきた場合、オーケストレーション インスタンスは動的に設定、 **BTS します。操作** ポートの操作の名前を持つプロパティです。 コンテンツ ベースのルーティングと送信メッセージがルーティングされる場合は、設定、 **BTS します。操作** パイプライン コンポーネントのプロパティです。
このプロパティは、シングル アクション形式で受信したメッセージから自動的に昇格します。

型:文字列  
既定値: 空の文字列  
適用されますすべての WCF 送信アダプタ。

#### <a name="affiliateapplicationname"></a>AffiliateApplicationName
エンタープライズ シングル サインオン (SSO) に使用する関連アプリケーションを指定します。 場合に、このプロパティは必須、 **UseSSO** にプロパティが設定されている **True**します。 

型:文字列  
既定値: 空の文字列  
適用されますすべての WCF 送信アダプタ*を除く*Wcf-netnamedpipe アダプター。

#### <a name="algorithmsuite"></a>AlgorithmSuite
メッセージの暗号化とキー ラップのアルゴリズムを指定します。 これらのアルゴリズムは、セキュリティ ポリシー言語 (WS-SecurityPolicy) 仕様で指定されたアルゴリズムにマップされます。

該当する値の詳細については、 **AlgorithmSuite**プロパティを参照してください、**アルゴリズム スイート**プロパティに、 **Wcf-nettcp トランスポートのプロパティ ダイアログ ボックス、送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。

型:文字列  
既定値: **Basic256**  
適用対象 

- Wcf-basichttp アダプタ
- Wcf-netmsmq アダプタ
- WCF-NetTcp アダプタ
- WCF-WSHttp アダプタ

#### <a name="bindingconfiguration"></a>BindingConfiguration
XML 文字列を指定し、 **\<バインディング\>**のさまざまな種類を構成するのには定義済みの Windows Communication Foundation (WCF) によって提供されるバインディング。 システム指定のバインディングとカスタム バインドの詳細については、該当するトピックを参照してくださいを参照してください。

例:

```
<binding name="wsHttpBinding" transactionFlow="true">
<security><message clientCredentialType="UserName"></security>
</binding>
```

型:文字列  
既定値: 空の文字列  
適用されます WCF カスタム アダプター、Wcf-customisolated アダプター。

#### <a name="bindingtype"></a>BindingType
エンドポイントに使用するバインドの種類を指定します。 該当する値の詳細については、 **BindingType**プロパティを参照してください、**バインディングの種類**プロパティに、 **Wcf-custom トランスポートのプロパティ ダイアログ ボックス、送信、バインディング**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。

型:文字列  
既定値: 空の文字列  
適用されます WCF カスタム アダプター、Wcf-customisolated アダプター。

#### <a name="clientcertificate"></a>ClientCertificate
この送信ポートをサービスに対して認証する際に使用する X.509 証明書の拇印を指定します。 このプロパティは必要な場合、 **ClientCredentialsType** プロパティに設定されて **証明書**します。 このプロパティを使用する証明書をインストールする必要があります、 **マイ** に格納、 **現在のユーザー** 場所です。

型:文字列  
既定値: 空の文字列  
適用対象 

- WCF-BasicHttp 送信アダプタ
- WCF-WSHttp 送信アダプタ
- Wcf-nettcp 送信アダプター
- Wcf-netmsmq 送信アダプター

#### <a name="closetimeout"></a>CloseTimeout
チャネルを閉じる操作が完了するまでの間隔を示す期間値を指定します。

型:文字列  
既定値:00:01:00  
適用されますすべての WCF アダプタ*を除く*Wcf-custom および Wcf-customisolated。

#### <a name="customdeadletterqueue"></a>CustomDeadLetterQueue
完全修飾 URI を指定、 **net.msmq** 期限切れになったか、転送または配信に失敗したメッセージが配置されているアプリケーションごとの配信不能キューの場所を設定します。 たとえば、net.msmq://localhost/deadLetterQueueName と指定します。 配信不能キューは、配信に失敗した期限切れのメッセージの送信アプリケーションのキュー マネージャのキューです。 このプロパティは必要な場合、 **DeadLetterQueue** プロパティに設定されて **カスタム**します。

型:文字列  
既定値: 空の文字列  
適用されます: Wcf-netmsmq 送信アダプター

#### <a name="deadletterqueue"></a>DeadLetterQueue
アプリケーションへの配信に失敗したメッセージの転送先となる配信不能キューを指定します。 配信不能キューに配信されたメッセージの詳細については、次を参照してください。、 **Wcf-netmsmq トランスポートのプロパティ ダイアログ ボックス、送信、バインディング**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。

型:文字列  
既定値: **システム**  
適用されます: Wcf-netmsmq 送信アダプター

#### <a name="disablelocationonfailure"></a>DisableLocationOnFailure
受信パイプラインまたはルーティングの障害によって受信処理に失敗した受信場所を無効にするかどうかを指定します。 このプロパティを設定する **True** が表示されたらの場所を無効にして、サービス拒否 (DoS) は問題になりません。

例:  
- Wcf-custom アダプター: ときに、 **BindingType**プロパティに設定されている**netMsmqBinding**です。
- Wcf-custom アダプター: ときに、 **BindingType**プロパティに設定されている**customBinding**、および**BindingConfiguration**プロパティが依存するカスタム チャネルを使用するよう構成MSMQ などのトランスポートをキューに登録します。
- Wcf-customisolated アダプター: ときに、 **BindingType**プロパティに設定されている**customBinding**、および**BindingConfiguration**プロパティは、カスタム チャネルを使用するように構成MSMQ などのキューに置かれたトランスポートに依存します。
- Wcf-netmsmq アダプタ

型: ブール  
既定値: **False**  
適用対象  
- Wcf-netmsmq 受信アダプター
- Wcf-custom 受信アダプター
- WCF-CustomIsolated 受信アダプタ

#### <a name="enabletransaction"></a>EnableTransaction
このプロパティの効果は、WCF アダプタによって異なります。 このプロパティの詳細については、の各 WCF アダプタの操作方法に関するトピックを参照してください。 [WCF アダプタ](../core/wcf-adapters.md)です。

型: ブール  
適用対象 

- WCF-WSHttp アダプタ
- WCF-NetTcp アダプタ
- Wcf-netnamedpipe アダプタ
- Wcf-netmsmq アダプタ

#### <a name="endpointbehaviorconfiguration"></a>EndpointBehaviorConfiguration
XML 文字列を指定し、 **\<動作\>**の要素、  **\<endpointBehaviors\>** の動作設定を構成するのには、WCF エンドポイントです。 詳細については、  **\<endpointBehaviors\>** 要素では、「参照」の該当するトピックを参照してください。

例: 
```
<behavior name="sampleBehavior"><callbackTimeouts/></behavior>
```

型:文字列  
既定値: 空の文字列  
適用されます: Wcf-custom 送信アダプター

#### <a name="establishsecuritycontext"></a>EstablishSecurityContext
セキュリティ チャネルで、セキュリティで保護されたセッションを確立するかどうかを指定します。 セキュリティで保護されたセッションでは、アプリケーションのメッセージを交換する前に、セキュリティ コンテキスト トークン (SCT) が確立されます。

型: ブール  
既定値: True  
適用: Wcf-wshttp アダプター

#### <a name="fromaddress"></a>FromAddress
受信 WCF メッセージの送信元のエンドポイント アドレスを示します。 このプロパティは、受信メッセージから自動的に昇格されます。

型:文字列  
適用されますすべての WCF アダプタ*を除く*Wcf-netmsmq 送信アダプター。
  
#### <a name="headers"></a>ヘッダー
URI 以外の追加アドレス指定情報を提供するエンドポイント参照を指定します。 このプロパティを使用すると、このプロパティが必要、 \<**ヘッダー** \>ルート要素としての要素。 内のすべてのアドレス ヘッダーに配置する必要があります、 \<**ヘッダー** \>要素。 このプロパティは、受信メッセージに自動的に昇格されます。

例:
```
<headers>
<Region xmlns="Uri">"String"</Region>
<Member xmlns="Uri">"String"</Member> 
</headers>
```

型:文字列  
適用されますすべての WCF アダプタ。
  
#### <a name="identity"></a>Identity
受信場所が提供するか、送信ポートが必要とするサービスの ID を指定します。 指定できる値、 **Identity** プロパティが、セキュリティ構成によって異なります。 これらの設定により、クライアントがサービスを認証できます。 クライアントとサービスの間のハンドシェイク プロセスでは、Windows Communication Foundation (WCF) インフラストラクチャによって、クライアントの値とサービスの ID が照合されます。

例:
```
<identity>
<userPrincipalName value="username@contoso.com"/>
</identity>
```

型:文字列  
既定値: 空の文字列  
適用されますすべての WCF アダプタ。

#### <a name="inboundbodylocation"></a>InboundBodyLocation
SOAP のデータ選択を指定 **本文** 受信 WCF メッセージの要素。 使用する方法についての詳細、 **InboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。

型:文字列  
既定値: UseBodyElement  

    Applicable values are:  
        - UseBodyElement: Use the content of the SOAP **Body** element of an incoming message to create the BizTalk message body part. If the **Body** element has more than one child element, only the first element becomes the BizTalk message body part.
        - UseEnvelope: Create the BizTalk message body part from the entire SOAP **Envelope** of an incoming message.
        - UseBodyPath: Use the body path expression in the **InboundBodyPathExpression** property to create the BizTalk message body part. The body path expression is evaluated against the immediate child element of the SOAP **Body** element of an incoming message. This property is valid only for solicit-response ports.  

適用されますすべての WCF アダプタ*を除く*Wcf-netmsmq 送信。  

#### <a name="inboundbodypathexpression"></a>InboundBodyPathExpression
BizTalk メッセージのボディ部を作成するために使用する受信メッセージの特定の部分を示すボディ パス式を指定します。 このボディ パス式が、SOAP の直下の子要素に対して評価されます **本文** 受信メッセージのノードです。 このボディ パス式で複数のノードが返される場合は、最初のノードのみが BizTalk メッセージのボディ部に対して選択されます。 このプロパティは必要な場合、 **InboundBodyLocation** プロパティに設定されて **UseBodyPath**します。 使用する方法についての詳細、 **InboundBodyPathExpression**プロパティを参照してください[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)です。

型:文字列  
既定値: 空の文字列  
適用されますすべての WCF アダプタ*を除く*Wcf-netmsmq 送信アダプター。

#### <a name="inboundheaders"></a>InboundHeaders
使用して、 **InboundHeaders** 受信 WCF メッセージの SOAP ヘッダーにアクセスするプロパティです。 WCF アダプタは、このプロパティに受信メッセージのすべての SOAP ヘッダー値をコピーします。このヘッダー値には、WCF インフラストラクチャが WS-Addressing、WS-Security、WS-AtomicTransaction などに使用するカスタム SOAP ヘッダーおよび標準 SOAP ヘッダーが含まれています。 コンテキスト プロパティに含まれる値は、使用した XML データを含む文字列、 \<**ヘッダー** \>の子要素としてのルート要素と、受信 SOAP ヘッダーのコピー、 \< **ヘッダー** \>要素。 WCF アダプタで SOAP ヘッダーにアクセスする方法の詳細については、「WCF アダプターでのカスタム SOAP ヘッダーの使用の SDK サンプルから [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)します。

型:文字列  
適用されますすべての WCF アダプタ*を除く*Wcf-netmsmq 送信アダプター。

#### <a name="inboundnodeencoding"></a>InboundNodeEncoding
WCF 受信アダプターで指定されたボディ パス式で識別されるノードのデコードに使用であるエンコードの種類を指定 **InboundBodyPathExpression**します。 このプロパティは必要な場合、 **InboundBodyLocation** プロパティに設定されて **UseBodyPath**します。

型:文字列  
既定値: XML  

    Applicable values are:  
        - Base64: Base64 encoding
        - Hex: Hexadecimal encoding
        - String: Text encoding - UTF-8
        - XML: The WCF adapters create the BizTalk message body with the outer XML of the node selected by the body path expression in **InboundBodyPathExpression**.  

適用されますすべての WCF アダプタ*を除く*Wcf-netmsmq 送信アダプター。

#### <a name="isfault"></a>IsFault
SOAP エラー メッセージが受信されるかどうかを示します。 このプロパティは、受信メッセージから自動的に昇格されます。 

**注**  
**IsFault**プロパティは、HTTP 404 (ファイルまたはディレクトリが見つかりません) エラーなどのトランスポート エラーを受信したメッセージの確認に使用できません。

型: ブール  
適用されますすべての WCF アダプタ*を除く*Wcf-netmsmq 送信アダプター。

#### <a name="leasetimeout"></a>LeaseTimeout
アクティブなプールされた接続の最大有効期間を指定します。 指定した時間が経過すると、現在の要求の処理後に、接続が閉じられます。

Wcf-nettcp アダプターの活用、 [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) 、エンドポイントと通信するクラス。 使用する場合、 [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) 負荷分散のシナリオでは、既定のリース タイムアウトを減らすことを検討してください。負荷分散を使用する場合の詳細については、 [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)、「参照」の該当するトピックを参照してください。

型:文字列  
既定値: 00時 05分: 00  
適用されます WCF-NetTcp 受信アダプター。  

#### <a name="maxconcurrentcalls"></a>MaxConcurrentCalls
単一のサービス インスタンスに対する同時呼び出しの数を指定します。 制限を超える呼び出しはキューに格納されます。 この値を 0 に設定することは、 **Int32.MaxValue**に設定するのと同じです。 

**注**  
このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。 

型: 整数  
既定値:200  
適用されますすべての WCF 受信アダプタ*を除く*Wcf-custom および Wcf-customisolated アダプター。

#### <a name="maxconnections"></a>MaxConnections
リスナーが保持することができる、アプリケーションによる受け入れを待機する接続の最大数を指定します。 この数を超えた場合、新しい受信接続は受け入れを待機する代わりに削除されます。 

**注**  
これはアダプタ ハンドラ プロパティであるため、このプロパティはパイプライン コンポーネントおよびオーケストレーションでは構成できません。 

**注**  
このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。 

型: 整数  
既定値: 10  
適用されます: Wcf-netnamedpipe アダプター, Wcf-nettcp アダプター  

#### <a name="maxreceivedmessagesize"></a>MaxReceivedMessageSize
有線ネットワーク上で受信できる、ヘッダーを含むメッセージの最大サイズをバイト単位で指定します。 メッセージのサイズは、各メッセージに割り当てられているメモリの量に制限されます。 このプロパティを使用して、サービス拒否 (DoS) 攻撃にさらされる危険性を制限できます。

型: 整数  
既定値:65536  
適用対象 
- Wcf-basichttp アダプタ
- WCF-WSHttp アダプタ
- WCF-NetTcp アダプタ
- Wcf-netnamedpipe アダプタ
- Wcf-netmsmq 受信アダプター

#### <a name="messageclientcredentialtype"></a>MessageClientCredentialType
メッセージ ベースのセキュリティを使用してクライアント認証を実行するときに使用する、資格情報の種類を指定します。

適用可能な値は、WCF アダプタごとに異なります。 詳細については、 **MessageClientCredentialType**プロパティの各 WCF アダプタの操作方法に関するトピックを参照してください[WCF アダプタ](../core/wcf-adapters.md)です。

型:文字列  
適用対象 
- Wcf-basichttp アダプタ
- WCF-WSHttp アダプタ
- WCF-NetTcp アダプタ
- Wcf-netnamedpipe アダプタ

#### <a name="messageencoding"></a>MessageEncoding
SOAP メッセージをエンコードするために使用されるエンコーダーを指定します。

型:文字列  
既定値: テキスト  

    Applicable values: 
        - Text: Use a text message encoder
        - Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder  

適用されます: Wcf-basichttp アダプタ、Wcf-wshttp アダプター


#### <a name="msmqauthenticationmode"></a>MsmqAuthenticationMode
MSMQ トランスポートによるメッセージの認証方法を指定します。

型:文字列  
既定値: **WindowsDomain**  
    該当する値の詳細については、 **MsmqAuthenticationMode**プロパティを参照してください、 **MSMQ 認証モード**プロパティに、 **Wcf-netmsmq トランスポートのプロパティダイアログ ボックスの 送信セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
適用されます: Wcf-netmsmq アダプター  

#### <a name="msmqencryptionalgorithm"></a>MsmqEncryptionAlgorithm
メッセージ キュー マネージャー間でメッセージを転送するときに、有線ネットワーク上でメッセージを暗号化するために使用するアルゴリズムを指定します。 このプロパティは使用可能な場合にのみ、 **MsmqProtectionLevel** にプロパティが設定されている **EncryptAndSign**します。

型:文字列  
既定値: **RC4Stream**  

    Applicable values are: RC4Stream, AES

適用されます: Wcf-netmsmq アダプター  

#### <a name="msmqprotectionlevel"></a>MsmqProtectionLevel
MSMQ トランスポートのレベルでメッセージをセキュリティ保護する方法を指定します。

型:文字列  
既定値: **記号**  

    Applicable values are:
        - None: No protection
        - Sign: Messages are signed
        - EncryptAndSign: Messages are encrypted and signed. To use this protection level, you must enable **Active Directory Integration** for **MSMQ**  

適用されます: Wcf-netmsmq アダプター  

#### <a name="msmqsecurehashalgorithm"></a>MsmqSecureHashAlgorithm
メッセージ ダイジェストの計算に使用するハッシュ アルゴリズムを指定します。 このプロパティは使用できない場合、 **MsmqProtectionLevel** にプロパティが設定されている **None**します。

型:文字列  
既定値: **SHA1**  

    Applicable values are: MD5, SHA1, SHA25, SHA512  

適用されます: Wcf-netmsmq アダプター  

#### <a name="negotiateservicecredential"></a>NegotiateServiceCredential
サービスの資格情報が帯域外のクライアントで提供されるか、またはネゴシエーションのプロセスによってクライアントへのサービスから取得されるかを指定します。 このようなネゴシエーションは、通常のメッセージ交換に先行して実行されます。

場合、 **MessageClientCredentialType** プロパティ = **なし**, 、**Username**, 、または **証明書**, 、このプロパティを設定 **False** サービス証明書がクライアントの帯域外で使用可能であり、クライアントがサービス証明書を指定する必要があることを意味します。 このモードは、Ws-trust および Ws-secureconversation が実装された SOAP スタックと相互運用可能です。

場合、 **MessageClientCredentialType** にプロパティが設定されている **Windows**, 、このプロパティを設定 **False** Kerberos ベースの認証を指定します。 つまり、クライアントとサービスは同じ Kerberos ドメイン内に含める必要があります。 このモードは、WS-Trust や WS-SecureConversation に加えて (OASIS WSS TC で定義されている) Kerberos トークン プロファイルを実装する SOAP スタックと相互運用できます。

このプロパティが **True**, 、SOAP メッセージを介して SPNego 交換をトンネル化する .NET SOAP ネゴシエーションが発生します。

型: ブール  
既定値: True  
適用されます: Wcf-wshttp アダプター  

#### <a name="opentimeout"></a>OpenTimeout
チャネルを開く操作が完了するまでの間隔を示す期間値を指定します。 

**注**  
このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。 

型:文字列  
既定値:00:01:00  
適用されますすべての WCF アダプタ*を除く*Wcf-custom および Wcf-customisolated アダプター。

#### <a name="orderedprocessing"></a>OrderedProcessing
メッセージを順番に処理するかどうかを指定します。 この受信場所でこのプロパティを選択すると、BizTalk メッセージングまたはオーケストレーション送信ポートを持つと組み合わせて使用すると、メッセージの順次配送の対応、 **順次配送** オプションに設定 `True`します。 詳細については、 **順次配送** オプションを参照してください、該当するトピックを参照してください。

このプロパティの値は次の場合に適用されます。
- Wcf-custom アダプター: ときに、 **BindingType**プロパティに設定されている**netMsmqBinding**
- Wcf-custom アダプター: ときに、 **BindingType**プロパティに設定されている**customBinding**、および**BindingConfiguration**プロパティが依存するカスタム チャネルを使用するよう構成トランスポートが MSMQ などの順次配送をサポートします。
- Wcf-customisolated アダプター: ときに、 **BindingType**プロパティに設定されている**customBinding**、および**BindingConfiguration**プロパティは、カスタム チャネルを使用するように構成順次配送をサポートするトランスポートに依存します。
- Wcf-netmsmq アダプタ

型:文字列  
既定値: **False**  
適用対象 
- Wcf-netmsmq 受信アダプター
- Wcf-custom 受信アダプター
- WCF-CustomIsolated 受信アダプタ

#### <a name="outboundbodylocation"></a>OutboundBodyLocation
SOAP のデータ選択を指定 **本文** 送信 WCF メッセージの要素。 使用する方法についての詳細、 **OutboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。

型:文字列  
既定値: UseBodyElement  

    Applicable values are:
        - UseBodyElement: Use the BizTalk message body part to create the content of the SOAP **Body** element for an outgoing message
        - **UseTem****plate**: Use the template supplied in the OutboundXMLTemplate property to create the content of the SOAP **Body** element for an outgoing message

適用されますすべての WCF アダプタ*を除く*Wcf-netmsmq 受信アダプター。

#### <a name="outboundcustomheaders"></a>OutboundCustomHeaders
送信メッセージのカスタム SOAP ヘッダーを指定します。 このプロパティを使用すると、プロパティが必要、 \<**ヘッダー** \>ルート要素としての要素。 内のすべてのカスタム SOAP ヘッダーに配置する必要があります、 \<**ヘッダー** \>要素。 カスタム SOAP ヘッダーの値が空の文字列の場合は、割り当てる必要があります\<**ヘッダー**\>\</**ヘッダー** \>または\<**ヘッダー** \>このプロパティにします。 WCF アダプタで SOAP ヘッダーを使用する方法の詳細については、「WCF アダプターでのカスタム SOAP ヘッダーの使用の SDK サンプルから [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)します。

型:文字列  
適用されますすべての WCF アダプタ*を除く*Wcf-netmsmq 受信アダプター。

#### <a name="outboundxmltemplate"></a>OutboundXmlTemplate
SOAP のコンテンツを XML 形式のテンプレートを指定 **本文** 、送信メッセージの要素。 このプロパティは必要な場合、 **OutboundBodyLocation** プロパティに設定されて **UseTemplate**します。 使用する方法についての詳細、 **OutboundXMLTemplate**プロパティを参照してください[WCF アダプタのメッセージの本文を指定する](../core/specifying-the-message-body-for-the-wcf-adapters.md)です。

型:文字列  
既定値: 空の文字列  
適用されますすべての WCF アダプタ*を除く*Wcf-netmsmq 受信アダプター。

#### <a name="password"></a>Password
接続先サーバーで認証を使用するパスワードを指定するときに、 **UseSSO** にプロパティが設定されている **False**します。

型:文字列  
既定値: 空の文字列  
適用されますすべての WCF 送信アダプタ*を除く*Wcf-netnamedpipe アダプター。  

#### <a name="propagatefaultmessage"></a>PropagateFaultMessage
送信処理に失敗したメッセージを回送または保留するかどうかを指定します。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。 

**注**  
このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。

型: ブール  
既定値: **は True。**  

    Applicable values are:  
        - True: Route the message that fails outbound processing to a subscribing application (such as another receive port or orchestration schedule)
        - False: Suspend failed messages and generate a negative acknowledgment (NACK)

適用されますすべての WCF 送信アダプタ*を除く*Wcf-netmsmq アダプター。
  
#### <a name="proxyaddress"></a>ProxyAddress
プロキシ サーバーのアドレスを指定します。 使用して、 **https** または **http** セキュリティ構成に応じて設定します。 このアドレスの後に、コロンとポート番号を指定します。 場合、プロパティは必須、 **ProxyToUse**プロパティに設定されている**UserSpecified** (たとえば、http://127.0.0.1:8080 と指定)

型:文字列  
既定値: 空の文字列  
適用されます: Wcf-basichttp 送信アダプター、Wcf-wshttp 送信アダプター  

#### <a name="proxypassword"></a>ProxyPassword
指定されているプロキシ サーバーを使用するパスワードを指定して、 **ProxyAddress** プロパティです。

型:文字列  
既定値: 空の文字列  
適用されます: Wcf-basichttp 送信アダプター、Wcf-wshttp 送信アダプター

#### <a name="proxytouse"></a>ProxyToUse
送信 HTTP トラフィックに使用するプロキシ サーバーを指定します。

型:文字列  
既定値: **なし**  

    Applicable values are:  
        - None: Do not use a proxy server for this send port
        - Default: Use the proxy settings in the send handler hosting this send port
        - UserSpecified: Use the proxy server specified in the **ProxyAddress** property

適用されます: Wcf-basichttp 送信アダプター、Wcf-wshttp 送信アダプター  

#### <a name="proxyusername"></a>ProxyUserName
指定されているプロキシ サーバーを使用するユーザー名を指定して、 **ProxyAddress** プロパティです。 場合、プロパティは必須、 **ProxyToUse** にプロパティが設定されている **UserSpecified**します。

このプロパティの詳細については、次を参照してください。 [Wcf-wshttp 送信ポートを構成する方法](../core/how-to-configure-a-wcf-wshttp-send-port.md)と[Wcf-basichttp 送信ポートを構成する方法](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f)です。

型:文字列  
適用されます: Wcf-basichttp 送信アダプター、Wcf-wshttp 送信アダプター

#### <a name="replytoaddress"></a>ReplyToAddress
要求 - 応答受信場所を介して受信された受信メッセージに対応する送信 WCF メッセージの応答エンドポイント アドレスを指定します。 このプロパティは、受信メッセージから自動的に昇格されます。

型:文字列  
既定値: 空の文字列  
適用されますすべての WCF アダプタ*を除く*Wcf-netmsmq アダプター。

#### <a name="securitymode"></a>SecurityMode
使用するセキュリティの種類を指定します。 適用可能な値は、WCF アダプタごとに異なります。 詳細については、 **SecurityMode**プロパティの各 WCF アダプタの操作方法に関するトピックを参照してください[WCF アダプタ](../core/wcf-adapters.md)です。 

**注**  
このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。

型:文字列  
適用されますすべての WCF アダプタ*を除く*Wcf-custom および Wcf-customisolated アダプター。

#### <a name="sendtimeout"></a>SendTimeout
送信操作が完了するまでの間隔を示す期間値を指定します。 この値は、送信者が大きなメッセージを送信した場合、対話処理がすべて完了するまでの時間を指定します。

型:文字列  
既定値:00:01:00  
適用されますすべての WCF アダプタ*を除く*Wcf-custom および Wcf-customisolated アダプター。

#### <a name="servicebehaviorconfiguration"></a>ServiceBehaviorConfiguration
XML 文字列を指定し、 **\<動作\>**の要素、  **\<serviceBehaviors\>**  WCF の動作設定を構成するのにはサービス。 詳細については、  **\<serviceBehaviors\>** 要素では、「参照」の該当するトピックを参照してください。

例:

```
<behavior name="SampleServiceBehavior">
<serviceAuthorization principalPermissionMode="UseAspNetRoles"/>
<serviceCredentials>
<serviceCertificate findValue="539d9ab3089bb6dc187fa7dbb382cf01f8d78f5f" storeLocation="CurrentUser" x509FindType="FindByThumbprint"/>
</serviceCredentials>
<serviceMetadata httpGetEnabled="true"/>
</behavior>
```

型:文字列  
既定値: 空の文字列  
適用されます: Wcf-custom 受信アダプター、Wcf-customisolated アダプター

#### <a name="servicecertificate"></a>ServiceCertificate
このプロパティを受信場所で使用する場合、クライアントがサービスの認証に使用する、この受信場所に対する X.509 証明書の拇印を指定します。 このプロパティを使用する証明書をインストールする必要があります、 **マイ** に格納、 **現在のユーザー** 場所です。

このプロパティを送信ポートで使用する場合、この送信ポートのメッセージ送信先のサービスの認証に使用する X.509 証明書の拇印を指定します。 このプロパティを使用する証明書をインストールする必要があります、 **その他のユーザー** に格納、 **ローカル マシン** 場所です。

型:文字列  
既定値: 空の文字列  
適用対象 
- Wcf-basichttp アダプタ
- Wcf-netmsmq アダプタ
- WCF-WSHttp アダプタ
- WCF-NetTcp 受信アダプタ

#### <a name="suspendmessageonfailure"></a>SuspendMessageOnFailure
受信パイプラインまたはルーティングの障害によって受信処理に失敗した要求メッセージを保留するかどうかを指定します。

型: ブール  
既定値: True  
適用されますすべての WCF 受信アダプタ。  

#### <a name="textencoding"></a>TextEncoding
文字セットのバインディングでメッセージを出力するために使用するエンコーディングを指定時に、 **MessageEncoding** にプロパティが設定されている **テキスト**します。 

**注**  
このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。 

型:文字列  
既定値: utf-8  

    Applicable values are:  
        - unicodeFFF: Unicode BigEndian encoding
        - utf-16: 16-bit encoding
        - utf-8: 8-bit encoding

適用されます: Wcf-basichttp アダプタ、Wcf-wshttp アダプター
  
#### <a name="timetolive"></a>TimeToLive
メッセージが期限切れになり、配信不能キューに格納されるまでのメッセージが有効な期間を指定します。 このプロパティは、時間が重要な要素になるメッセージが送信ポートによって処理されるまで古くならないようにするために設定されます。 指定された時間間隔内にこの送信ポートによって処理されないキュー内のメッセージは、期限切れのメッセージといいます。 期限切れのメッセージは、配信不能キューと呼ばれる特別なキューに送信されます。 配信不能キューの場所を設定、 **DeadLetterQueue** プロパティです。

型:文字列  
既定値: 1.00:00:00  
適用されます: Wcf-netmsmq 送信アダプター

#### <a name="to"></a>変換先
WCF 送信ポートが送信する送信 WCF メッセージの送信先エンドポイント アドレスを指定します。

型:文字列  
既定値: 空の文字列  
適用されますすべての WCF 送信アダプタ。  

#### <a name="transactionprotocol"></a>TransactionProtocol
このバインドで使用するトランザクション プロトコルを指定します。 場合に、このプロパティは必須、 **EnableTransaction** にプロパティが設定されている **True**します。

型:文字列  
既定値: [oletransaction]  

    Applicable values are: OleTransaction, WS-AtomicTransaction

適用されます: Wcf-netnamedpipe アダプター, Wcf-nettcp アダプター  

#### <a name="transportclientcredentialtype"></a>TransportClientCredentialType
送信ポート認証の実行時に使用する資格情報の種類を指定します。 適用可能な値は、WCF アダプタごとに異なります。 詳細については、 **TransportClientCredentialType**プロパティの各 WCF アダプタの操作方法に関するトピックを参照してください[WCF アダプタ](../core/wcf-adapters.md)です。

型:文字列  
適用されます: Wcf-basic アダプタ、Wcf-nettcp アダプター、Wcf-wshttp アダプター  

#### <a name="transportprotectionlevel"></a>TransportProtectionLevel
TCP トランスポートのレベルでのセキュリティを指定します。 メッセージに署名を付けることで、メッセージの転送中に第三者によって改ざんされるリスクが軽減されます。 暗号化によって、トランスポート中にデータ レベルのプライバシーが提供されます。

型:文字列  
既定値: **EncryptAndSign**  

    Applicable values are:  
        - None: No protection
        - Sign: Messages are signed
        - EncryptAndSign: Messages are encrypted and signed

適用されます: Wcf-nettcp アダプター, Wcf-netnamedpipe アダプター  

#### <a name="username"></a>UserName
接続先サーバーで認証を使用するユーザー名を指定時に、 **UseSSO** にプロパティが設定されている **False**します。 このプロパティでは domain\user 形式は使用できません。

型:文字列  
既定値: 空の文字列  
適用されますすべての WCF 送信アダプタ*を除く*Wcf-netnamedpipe アダプター。

#### <a name="usesourcejournal"></a>UseSourceJournal
この送信ポートによって処理されるメッセージのコピーをソース ジャーナル キューに保存するかどうかを指定します。

型: ブール  
既定値: False  
適用されます: Wcf-netmsmq 送信アダプター  

#### <a name="usesso"></a>UseSSO
接続先のサーバーでの認証でクライアントの資格情報を取得する際に、シングル サインオンを使用するかどうかを指定します。 

**注**  
このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。 

型: ブール  
既定値: False  
適用されますすべての WCF 送信アダプタ*を除く*Wcf-netnamedpipe アダプター。

#### <a name="referencedbindings"></a>ReferencedBindings
によって参照されるバインド構成を指定、 **bindingConfiguration**の属性、 **\<発行者\>**要素を**wsFederationHttpBinding**と**customBinding**、セキュリティ トークン サービス (STS) セキュリティ トークンを発行することを示します。 詳細については、 **\<発行者\>**要素のトピック「」を参照してください"\<発行者\>"で[http://go.microsoft.com/fwlink/?LinkId=83476](http://go.microsoft.com/fwlink/?LinkId=83476)です。

バインド情報を含む、 **\<発行者\>**要素を**wsFederationHttpBinding**と**customBinding**できます使用して構成、 **BindingConfiguration** Wcf-custom および Wcf-customisolated アダプターのプロパティです。 形式でこのプロパティの参照先のバインディング構成のすべてに配置する必要があります、 [\<バインド\>](http://go.microsoft.com/fwlink/?LinkID=80878)要素。 

**注**  
**BindingConfiguration**の属性、 **\<発行者\>**要素は、このプロパティに有効なバインド名を指す必要があります。 

**注**  
**\<発行者\>**で参照されるバインド構成要素を指すこともこのプロパティの異なるバインド構成この参照チェーンが循環する依存関係を行わない場合は。 

例: 

```
WCF.BindingConfiguration = @"<wsFederationHttpBinding>
<binding name=""sampleBinding"">
<security mode=""Message"">
<message issuedKeyType=""AsymmetricKey"">
<issuer address=""http://www.contoso.com/samplests"" binding=""wsFederationHttpBinding"" bindingConfiguration=""**contosoSTSBinding**""/>
</message>
</security>
</binding>
</wsFederationHttpBinding>";
WCF.ReferencedBinding =@"<bindings>
<wsFederationHttpBinding>
<binding name=""**contosoSTSBinding**"">
<security mode=""Message"">
<message negotiateServiceCredential=""false"">
<issuer address=""http://northwind.com/samplests"" bindingConfiguration=""**northwindBinding**"" binding=""wsHttpBinding"">
</issuer>
</message>
</security>
</binding>
</wsFederationHttpBinding>
<wsHttpBinding>
<binding name=""**northwindBinding**"">
<security mode=""Message"">
<message clientCredentialType=""Certificate""/>
</security>
</binding>
</wsHttpBinding>
</bindings>" 
``` 

**注**  
**ReferencedBinding**プロパティで使用されるバインド構成を格納する必要があります、 **BindingConfiguration**プロパティです。

型:文字列  
既定値: 空の文字列  
適用されます WCF カスタム アダプター、Wcf-customisolated アダプター。
  
## <a name="see-also"></a>参照  
 [WCF アダプタ](../core/wcf-adapters.md)   
 [\<動作\>の\<endpointBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=80879)   
 [\<bindings\>](http://go.microsoft.com/fwlink/?LinkId=80878)   
 [\<動作\>の\<serviceBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=81095)   
 [メッセージの配信を順序付け](../core/ordered-delivery-of-messages.md)   
 [負荷分散](http://go.microsoft.com/fwlink/?LinkId=81089)
