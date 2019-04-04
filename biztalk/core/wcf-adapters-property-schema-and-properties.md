---
title: WCF アダプター プロパティ スキーマおよびプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 02/09/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2093745e-86c0-4276-a7cc-a0187391ca4a
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10781e8743eeea68ff0be8993b3588d5ecd204d7
ms.sourcegitcommit: 0e14c3e018b091d81d0e4a68fafc10f6e31697e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "29139298"
---
# <a name="wcf-adapters-property-schema-and-properties"></a>WCF アダプタ プロパティ スキーマおよびプロパティ
WCF アダプタ プロパティ スキーマの昇格させたプロパティをについて説明します。 WCF アダプタは、アプリケーションで使用できるプロパティに値を割り当てます。 また、WCF アダプタは、カスタム プロパティを BizTalk メッセージ コンテキストに書き込むが昇格させないメカニズムと、カスタム プロパティを BizTalk メッセージ コンテキストに昇格させるメカニズムを提供します。 詳細については、[公開された WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-published-wcf-services.md)を参照してください。  

## <a name="promoted-properties"></a>昇格させたプロパティ  
**名前空間:** http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties  

#### <a name="action"></a>操作
指定、 **SOAPAction**送信メッセージのヘッダー フィールド。 2 つの方法でこの値を指定することができます。 シングル アクション形式とアクション マッピング形式。 シングル アクション形式では、このプロパティを設定するかどうか: たとえば、 http://contoso.com/Svc/Op1 —、 **SOAPAction**このプロパティで指定された値を設定は常に送信メッセージのヘッダー。

送信アクション マッピング形式でこのプロパティを設定する場合**SOAPAction**ヘッダーはによって決定されます、 **BTS します。操作**コンテキスト プロパティ。 たとえば、このプロパティは、次の XML 形式に設定されている場合、 **BTS です。操作**を Op1 に設定されているプロパティ、WCF 送信アダプタを使用して `http://contoso.com/Svc/Op1` アウトゴーイング**SOAPAction**ヘッダー。

```
<BtsActionMapping>
<Operation Name="Op1" Action="http://contoso.com/Svc/Op1">
<Operation Name="Op2" Action="http://contoso.com/Svc/Op2">
</BtsActionMapping>
```

送信メッセージがオーケストレーション ポートに由来する場合、オーケストレーション インスタンスは動的に設定、 **BTS します。操作**ポートの操作の名前を持つプロパティです。 設定することができますコンテンツ ベースのルーティングでは、送信メッセージがルーティングされている場合、 **BTS します。操作**パイプライン コンポーネントのプロパティ。
このプロパティは、シングル アクション形式で受信したメッセージから自動的に昇格されます。

型:String  
既定値:空の文字列  
適用対象すべての WCF 送信アダプタ

#### <a name="affiliateapplicationname"></a>AffiliateApplicationName
エンタープライズ シングル サインオン (SSO) に使用する関連アプリケーションを指定します。 このプロパティは必要な場合、 **UseSSO**プロパティに設定されて**True**。 

型:String  
既定値:空の文字列  
適用対象すべての WCF 送信アダプタ*を除く*Wcf-netnamedpipe アダプター

#### <a name="algorithmsuite"></a>AlgorithmSuite
メッセージの暗号化とキー ラップのアルゴリズムを指定します。 これらのアルゴリズムは、セキュリティ ポリシー言語 (WS-SecurityPolicy) 仕様で指定されたアルゴリズムにマップされます。

適用可能な値の詳細については、 **AlgorithmSuite**プロパティを参照してください、**アルゴリズム スイート**プロパティ、 **Wcf-nettcp トランスポートのプロパティ ダイアログ ボックス、送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。

型:String  
既定値:**Basic256**  
適用対象 

- Wcf-basichttp アダプター
- Wcf-netmsmq アダプター
- WCF-NetTcp アダプタ
- WCF-WSHttp アダプタ

#### <a name="bindingconfiguration"></a>BindingConfiguration
XML 文字列を指定、 **\<バインド\>** さまざまな種類の構成要素の定義済みの Windows Communication Foundation (WCF) によって提供されるバインディング。 システム指定のバインディングとカスタム バインドの詳細については、「参照」の該当するトピックを参照してください。

例:

```
<binding name="wsHttpBinding" transactionFlow="true">
<security><message clientCredentialType="UserName"></security>
</binding>
```

型:String  
既定値:空の文字列  
適用対象WCF カスタム アダプター、Wcf-customisolated アダプター

#### <a name="bindingtype"></a>BindingType
エンドポイントに使用するバインドの種類を指定します。 適用可能な値の詳細については、 **BindingType**プロパティを参照してください、**バインドの種類**プロパティ、 **Wcf-custom トランスポートのプロパティ ダイアログ ボックスの送信、バインド**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。

型:String  
既定値:空の文字列  
適用対象WCF カスタム アダプター、Wcf-customisolated アダプター

#### <a name="clientcertificate"></a>ClientCertificate
この送信ポートをサービスに対して認証する際に使用する X.509 証明書の拇印を指定します。 このプロパティは必要な場合、 **ClientCredentialsType**プロパティに設定されて**証明書**します。 このプロパティに使用する証明書をインストールする必要があります、**マイ**で格納、**現在のユーザー**場所。

型:String  
既定値:空の文字列  
適用対象 

- WCF-BasicHttp 送信アダプタ
- WCF-WSHttp 送信アダプタ
- Wcf-nettcp 送信アダプター
- Wcf-netmsmq 送信アダプター

#### <a name="closetimeout"></a>CloseTimeout
チャネルを閉じる操作が完了するまでの間隔を示す期間値を指定します。

型:String  
既定値:00:01:00  
適用対象すべての WCF アダプター*を除く*Wcf-custom および Wcf-customisolated

#### <a name="customdeadletterqueue"></a>CustomDeadLetterQueue
完全修飾 URI を指定、 **net.msmq**期限切れになったか、転送または配信に失敗したメッセージが置かれて、アプリケーションごとの配信不能キューの場所を構成します。 たとえば、net.msmq://localhost/deadLetterQueueName と指定します。 配信不能キューは、配信に失敗した期限切れのメッセージの送信アプリケーションのキュー マネージャのキューです。 このプロパティは必要な場合、 **DeadLetterQueue**プロパティに設定されて**カスタム**します。

型:String  
既定値:空の文字列  
適用対象Wcf-netmsmq 送信アダプター

#### <a name="deadletterqueue"></a>DeadLetterQueue
アプリケーションへの配信に失敗したメッセージの転送先となる配信不能キューを指定します。 配信不能キューに配信されたメッセージの詳細については、、 **Wcf-netmsmq トランスポートのプロパティ ダイアログ ボックスの送信、バインド**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。

型:String  
既定値:**システム**  
適用対象Wcf-netmsmq 送信アダプター

#### <a name="disablelocationonfailure"></a>DisableLocationOnFailure
受信パイプラインまたはルーティングの障害によって受信処理に失敗した受信場所を無効にするかどうかを指定します。 このプロパティを設定する**True**を受信するタイミングの場所を無効にすることができ、サービス拒否 (DoS) は問題になりません。

例 :  
- WCF-Custom アダプター: ときに、 **BindingType**プロパティに設定されて**netMsmqBinding**します。
- WCF-Custom アダプター: ときに、 **BindingType**プロパティに設定されて**customBinding**、および**BindingConfiguration**プロパティを構成してキューに置かれたトランスポートに依存するカスタム チャネルを使用するにはMSMQ など。
- WCF-CustomIsolated アダプター: ときに、 **BindingType**プロパティに設定されて**customBinding**、および**BindingConfiguration**プロパティを構成してキューに置かれたトランスポートに依存するカスタム チャネルを使用するにはMSMQ など
- Wcf-netmsmq アダプター

型:ブール値  
既定値:**False**  
適用対象  
- Wcf-netmsmq 受信アダプター
- Wcf-custom 受信アダプター
- WCF-CustomIsolated 受信アダプタ

#### <a name="enabletransaction"></a>EnableTransaction
このプロパティの効果は、WCF アダプタによって異なります。 このプロパティの詳細については、の各 WCF アダプタの操作方法に関するトピックを参照してください。 [WCF アダプタ](../core/wcf-adapters.md)します。

型:ブール値  
適用対象 

- WCF-WSHttp アダプタ
- WCF-NetTcp アダプタ
- Wcf-netnamedpipe アダプター
- Wcf-netmsmq アダプター

#### <a name="endpointbehaviorconfiguration"></a>EndpointBehaviorConfiguration
XML 文字列を指定、 **\<動作\>** の要素、 **\<endpointBehaviors\>** の動作の設定を構成するのには、WCF エンドポイント。 詳細については、 **\<endpointBehaviors\>** 要素では、「も該当するトピックを参照してください。

例: 
```
<behavior name="sampleBehavior"><callbackTimeouts/></behavior>
```

型:String  
既定値:空の文字列  
適用対象Wcf-custom 送信アダプタ

#### <a name="establishsecuritycontext"></a>EstablishSecurityContext
セキュリティ チャネルで、セキュリティで保護されたセッションを確立するかどうかを指定します。 セキュリティで保護されたセッションでは、アプリケーションのメッセージを交換する前に、セキュリティ コンテキスト トークン (SCT) が確立されます。

型:ブール値  
既定値:True  
適用されます。WCF-WSHttp アダプタ

#### <a name="fromaddress"></a>FromAddress
受信 WCF メッセージの送信元のエンドポイント アドレスを示します。 このプロパティは、受信メッセージから自動的に昇格されます。

型:String  
適用対象すべての WCF アダプター*を除く*Wcf-netmsmq 送信アダプター
  
#### <a name="headers"></a>ヘッダー
URI 以外の追加アドレス指定情報を提供するエンドポイント参照を指定します。 このプロパティを使用すると、このプロパティが必要、 \<**ヘッダー** \>ルート要素としての要素。 内ですべてのアドレス ヘッダーに配置する必要があります、 \<**ヘッダー** \>要素。 このプロパティは、受信メッセージに自動的に昇格されます。

例:
```
<headers>
<Region xmlns="Uri">"String"</Region>
<Member xmlns="Uri">"String"</Member> 
</headers>
```

型:String  
適用対象すべての WCF アダプタ
  
#### <a name="identity"></a>同一。
受信場所が提供するか、送信ポートが必要とするサービスの ID を指定します。 指定できる値、 **Identity**プロパティは、セキュリティの構成によって異なります。 これらの設定により、クライアントがサービスを認証できます。 クライアントとサービスの間のハンドシェイク プロセスでは、Windows Communication Foundation (WCF) インフラストラクチャによって、クライアントの値とサービスの ID が照合されます。

例:
```
<identity>
<userPrincipalName value="username@contoso.com"/>
</identity>
```

型:String  
既定値:空の文字列  
適用対象すべての WCF アダプタ

#### <a name="inboundbodylocation"></a>InboundBodyLocation
SOAP データ選択を指定**本文**受信 WCF メッセージの要素。 使用する方法についての詳細、 **InboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)します。

型:String  
既定値:UseBodyElement  

    Applicable values are:  
        - UseBodyElement: Use the content of the SOAP **Body** element of an incoming message to create the BizTalk message body part. If the **Body** element has more than one child element, only the first element becomes the BizTalk message body part.
        - UseEnvelope: Create the BizTalk message body part from the entire SOAP **Envelope** of an incoming message.
        - UseBodyPath: Use the body path expression in the **InboundBodyPathExpression** property to create the BizTalk message body part. The body path expression is evaluated against the immediate child element of the SOAP **Body** element of an incoming message. This property is valid only for solicit-response ports.  

適用対象すべての WCF アダプター*を除く*Wcf-netmsmq 送信  

#### <a name="inboundbodypathexpression"></a>InboundBodyPathExpression
BizTalk メッセージのボディ部を作成するために使用する受信メッセージの特定の部分を示すボディ パス式を指定します。 このボディ パス式は、SOAP の直接の子要素に対して評価される**本文**受信メッセージのノード。 このボディ パス式で複数のノードが返される場合は、最初のノードのみが BizTalk メッセージのボディ部に対して選択されます。 このプロパティは必要な場合、 **InboundBodyLocation**プロパティに設定されて**UseBodyPath**します。 使用する方法についての詳細、 **InboundBodyPathExpression**プロパティを参照してください[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)します。

型:String  
既定値:空の文字列  
適用対象すべての WCF アダプター*を除く*Wcf-netmsmq 送信アダプター

#### <a name="inboundheaders"></a>InboundHeaders
使用して、 **InboundHeaders**受信 WCF メッセージの SOAP ヘッダーにアクセスするプロパティ。 WCF アダプタは、このプロパティに受信メッセージのすべての SOAP ヘッダー値をコピーします。このヘッダー値には、WCF インフラストラクチャが WS-Addressing、WS-Security、WS-AtomicTransaction などに使用するカスタム SOAP ヘッダーおよび標準 SOAP ヘッダーが含まれています。 コンテキスト プロパティに含まれる値は、XML データを格納している文字列、 \<**ヘッダー** \>の子要素としてのルート要素と、受信 SOAP ヘッダーのコピー、 \< **ヘッダー** \>要素。 WCF アダプタで SOAP ヘッダーをアクセスする方法の詳細についてから、WCF アダプタでのカスタム SOAP ヘッダーの使用の SDK サンプルを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)します。

型:String  
適用対象すべての WCF アダプター*を除く*Wcf-netmsmq 送信アダプター

#### <a name="inboundnodeencoding"></a>InboundNodeEncoding
WCF 受信アダプターで指定されたボディ パス式で識別されるノードのデコードに使用するエンコードの種類を指定**InboundBodyPathExpression**します。 このプロパティは必要な場合、 **InboundBodyLocation**プロパティに設定されて**UseBodyPath**します。

型:String  
既定値:XML  

    Applicable values are:  
        - Base64: Base64 encoding
        - Hex: Hexadecimal encoding
        - String: Text encoding - UTF-8
        - XML: The WCF adapters create the BizTalk message body with the outer XML of the node selected by the body path expression in **InboundBodyPathExpression**.  

適用対象すべての WCF アダプター*を除く*Wcf-netmsmq 送信アダプター

#### <a name="isfault"></a>IsFault
SOAP エラー メッセージが受信されるかどうかを示します。 このプロパティは、受信メッセージから自動的に昇格されます。 

**注:**  
**IsFault** HTTP 404 (ファイルまたはディレクトリが見つかりません) エラーなどのトランスポート エラーを受信したメッセージを確認するプロパティを使用することはできません。

型:ブール値  
適用対象すべての WCF アダプター*を除く*Wcf-netmsmq 送信アダプター

#### <a name="leasetimeout"></a>LeaseTimeout
アクティブなプールされた接続の最大有効期間を指定します。 指定した時間が経過すると、現在の要求が処理された後、接続を閉じます。

Wcf-nettcp アダプターの活用、 [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)エンドポイントと通信するクラス。 使用する場合、 [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)負荷分散のシナリオで、既定のリース タイムアウトを減らすことを検討します。負荷分散を使用する場合の詳細については、 [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)、関連の適切なトピックを参照してください。

型:String  
既定値:00:05:00  
適用対象WCF-NetTcp 受信アダプタ  

#### <a name="maxconcurrentcalls"></a>MaxConcurrentCalls
単一のサービス インスタンスに対する同時呼び出しの数を指定します。 制限を超える呼び出しはキューに格納されます。 この値を 0 に設定することは、 **Int32.MaxValue**に設定するのと同じです。 

**注:**  
このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。 

型:Integer  
既定値:200  
適用対象すべての WCF 受信アダプタ*を除く*Wcf-custom および Wcf-customisolated アダプター

#### <a name="maxconnections"></a>MaxConnections
リスナーが保持することができる、アプリケーションによる受け入れを待機する接続の最大数を指定します。 この数を超えた場合、新しい受信接続は受け入れを待機する代わりに削除されます。 

**注:**  
これはアダプタ ハンドラ プロパティであるため、このプロパティはパイプライン コンポーネントおよびオーケストレーションでは構成できません。 

**注:**  
このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。 

型:Integer  
既定値:10  
適用対象Wcf-netnamedpipe アダプター、Wcf-nettcp アダプター  

#### <a name="maxreceivedmessagesize"></a>MaxReceivedMessageSize
有線ネットワーク上で受信できる、ヘッダーを含むメッセージの最大サイズをバイト単位で指定します。 メッセージのサイズは、各メッセージに割り当てられているメモリの量に制限されます。 このプロパティを使用して、サービス拒否 (DoS) 攻撃にさらされる危険性を制限できます。

型:Integer  
既定値:65536  
適用対象 
- Wcf-basichttp アダプター
- WCF-WSHttp アダプタ
- WCF-NetTcp アダプタ
- Wcf-netnamedpipe アダプター
- Wcf-netmsmq 受信アダプター

#### <a name="messageclientcredentialtype"></a>MessageClientCredentialType
メッセージ ベースのセキュリティを使用してクライアント認証を実行するときに使用する、資格情報の種類を指定します。

適用可能な値は、WCF アダプタごとに異なります。 詳細については、 **MessageClientCredentialType**プロパティの各 WCF アダプタの操作方法に関するトピックを参照してください[WCF アダプタ](../core/wcf-adapters.md)します。

型:String  
適用対象 
- Wcf-basichttp アダプター
- WCF-WSHttp アダプタ
- WCF-NetTcp アダプタ
- Wcf-netnamedpipe アダプター

#### <a name="messageencoding"></a>MessageEncoding
SOAP メッセージをエンコードするために使用されるエンコーダーを指定します。

型:String  
既定値:テキスト  

    Applicable values: 
        - Text: Use a text message encoder
        - Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder  

適用対象Wcf-basichttp アダプター、Wcf-wshttp アダプター


#### <a name="msmqauthenticationmode"></a>MsmqAuthenticationMode
MSMQ トランスポートによるメッセージの認証方法を指定します。

型:String  
既定値:**WindowsDomain**  
    適用可能な値の詳細については、 **MsmqAuthenticationMode**プロパティを参照してください、 **MSMQ 認証モード**プロパティ、 **Wcf-netmsmq トランスポートのプロパティダイアログ ボックスで、送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
適用対象Wcf-netmsmq アダプター  

#### <a name="msmqencryptionalgorithm"></a>MsmqEncryptionAlgorithm
メッセージ キュー マネージャー間でメッセージを転送するときに、有線ネットワーク上でメッセージを暗号化するために使用するアルゴリズムを指定します。 このプロパティは、使用可能な場合にのみ、 **MsmqProtectionLevel**プロパティに設定されて**EncryptAndSign**します。

型:String  
既定値:**[Rc4stream]**  

    Applicable values are: RC4Stream, AES

適用対象Wcf-netmsmq アダプター  

#### <a name="msmqprotectionlevel"></a>MsmqProtectionLevel
MSMQ トランスポートのレベルでメッセージをセキュリティ保護する方法を指定します。

型:String  
既定値:**[署名]**  

    Applicable values are:
        - None: No protection
        - Sign: Messages are signed
        - EncryptAndSign: Messages are encrypted and signed. To use this protection level, you must enable **Active Directory Integration** for **MSMQ**  

適用対象Wcf-netmsmq アダプター  

#### <a name="msmqsecurehashalgorithm"></a>MsmqSecureHashAlgorithm
メッセージ ダイジェストの計算に使用するハッシュ アルゴリズムを指定します。 このプロパティは使用可能な場合、 **MsmqProtectionLevel**プロパティに設定されて**None**します。

型:String  
既定値:**SHA1**  

    Applicable values are: MD5, SHA1, SHA25, SHA512  

適用対象Wcf-netmsmq アダプター  

#### <a name="negotiateservicecredential"></a>NegotiateServiceCredential
サービスの資格情報が帯域外のクライアントで提供されるか、またはネゴシエーションのプロセスによってクライアントへのサービスから取得されるかを指定します。 そのようなネゴシエーションは、通常のメッセージ交換の準備です。

場合、 **MessageClientCredentialType**プロパティと等しい**None**、 **Username**、または**証明書**にこのプロパティの設定**False**サービス証明書がクライアントの帯域外で使用可能であり、クライアントがサービス証明書を指定する必要があることを意味します。 このモードは、WS-Trust および WS-SecureConversation が実装された SOAP スタックと同時に使用できます。

場合、 **MessageClientCredentialType**プロパティに設定されて**Windows**、このプロパティを設定**False** Kerberos ベースの認証を指定します。 つまり、クライアントとサービスは同じ Kerberos ドメイン内に含める必要があります。 このモードは、WS-Trust や WS-SecureConversation に加えて (OASIS WSS TC で定義されている) Kerberos トークン プロファイルを実装する SOAP スタックと相互運用できます。

このプロパティが**True**、SOAP メッセージで SPNego 交換をトンネリングする .NET SOAP ネゴシエーションが発生します。

型:ブール値  
既定値:True  
適用対象WCF-WSHttp アダプタ  

#### <a name="opentimeout"></a>OpenTimeout
チャネルを開く操作が完了するまでの間隔を示す期間値を指定します。 

**注:**  
このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。 

型:String  
既定値:00:01:00  
適用対象すべての WCF アダプター*を除く*Wcf-custom および Wcf-customisolated アダプター

#### <a name="orderedprocessing"></a>OrderedProcessing
メッセージを順番に処理するかどうかを指定します。 この受信場所でこのプロパティがオンの場合、BizTalk メッセージングまたはオーケストレーション送信ポートを持つと組み合わせて使用すると、メッセージの順次配送の対応、**順次配送**オプションに設定されて`True`します。 詳細については、**順次配送**オプションで、「参照」の該当するトピックを参照してください。

このプロパティの値は次の場合に適用されます。
- WCF-Custom アダプター: ときに、 **BindingType**プロパティに設定されて**netMsmqBinding**
- WCF-Custom アダプター: ときに、 **BindingType**プロパティに設定されて**customBinding**、および**BindingConfiguration**プロパティがトランスポートに依存するカスタム チャネルを使用するよう構成MSMQ などの順次配送をサポートします。
- WCF-CustomIsolated アダプター: ときに、 **BindingType**プロパティに設定されて**customBinding**、および**BindingConfiguration**プロパティがトランスポートに依存するカスタム チャネルを使用するよう構成順次配送をサポートします。
- Wcf-netmsmq アダプター

型:String  
既定値:**False**  
適用対象 
- Wcf-netmsmq 受信アダプター
- Wcf-custom 受信アダプター
- WCF-CustomIsolated 受信アダプタ

#### <a name="outboundbodylocation"></a>OutboundBodyLocation
SOAP データ選択を指定**本文**送信 WCF メッセージの要素。 使用する方法についての詳細、 **OutboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)します。

型:String  
既定値:UseBodyElement  

    Applicable values are:
        - UseBodyElement: Use the BizTalk message body part to create the content of the SOAP **Body** element for an outgoing message
        - **UseTem****plate**: Use the template supplied in the OutboundXMLTemplate property to create the content of the SOAP **Body** element for an outgoing message

適用対象すべての WCF アダプター*を除く*Wcf-netmsmq 受信アダプター

#### <a name="outboundcustomheaders"></a>OutboundCustomHeaders
送信メッセージのカスタム SOAP ヘッダーを指定します。 このプロパティを使用すると、プロパティが必要、 \<**ヘッダー** \>ルート要素としての要素。 内ですべてのカスタム SOAP ヘッダーに配置する必要があります、 \<**ヘッダー** \>要素。 カスタム SOAP ヘッダーの値が空の文字列の場合は、割り当てる必要があります\<**ヘッダー**\>\</**ヘッダー** \>または\<**ヘッダー** \>このプロパティにします。 WCF アダプタで SOAP ヘッダーを使用する方法の詳細についてを参照してください、WCF アダプタでのカスタム SOAP ヘッダーの使用の SDK サンプルから[ http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)します。

型:String  
適用対象すべての WCF アダプター*を除く*Wcf-netmsmq 受信アダプター

#### <a name="outboundxmltemplate"></a>OutboundXmlTemplate
SOAP のコンテンツを XML 形式のテンプレートを指定**本文**送信メッセージの要素。 このプロパティは必要な場合、 **OutboundBodyLocation**プロパティに設定されて**UseTemplate**します。 使用する方法についての詳細、 **OutboundXMLTemplate**プロパティを参照してください[WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)します。

型:String  
既定値:空の文字列  
適用対象すべての WCF アダプター*を除く*Wcf-netmsmq 受信アダプター

#### <a name="password"></a>パスワード
移行先サーバーでの認証に使用するパスワードを指定するときに、 **UseSSO**プロパティに設定されて**False**。

型:String  
既定値:空の文字列  
適用対象すべての WCF 送信アダプタ*を除く*Wcf-netnamedpipe アダプター  

#### <a name="propagatefaultmessage"></a>PropagateFaultMessage
送信処理に失敗したメッセージを回送または保留するかどうかを指定します。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。 

**注:**  
このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。

型:ブール値  
既定値:**True**  

    Applicable values are:  
        - True: Route the message that fails outbound processing to a subscribing application (such as another receive port or orchestration schedule)
        - False: Suspend failed messages and generate a negative acknowledgment (NACK)

適用対象すべての WCF 送信アダプタ*を除く*Wcf-netmsmq アダプター
  
#### <a name="proxyaddress"></a>ProxyAddress
プロキシ サーバーのアドレスを指定します。 使用して、 **https**または**http**セキュリティ構成に応じてスキーム。 このアドレスの後に、コロンとポート番号を指定します。 場合、プロパティは必須、 **ProxyToUse**プロパティに設定されて**UserSpecified** (例。 http://127.0.0.1:8080)

型:String  
既定値:空の文字列  
適用対象Wcf-basichttp 送信アダプター、Wcf-wshttp 送信アダプター  

#### <a name="proxypassword"></a>ProxyPassword
指定されたプロキシ サーバーを使用するパスワードを指定、 **ProxyAddress**プロパティ。

型:String  
既定値:空の文字列  
適用対象Wcf-basichttp 送信アダプター、Wcf-wshttp 送信アダプター

#### <a name="proxytouse"></a>ProxyToUse
送信 HTTP トラフィックに使用するプロキシ サーバーを指定します。

型:String  
既定値:**None**  

    Applicable values are:  
        - None: Do not use a proxy server for this send port
        - Default: Use the proxy settings in the send handler hosting this send port
        - UserSpecified: Use the proxy server specified in the **ProxyAddress** property

適用対象Wcf-basichttp 送信アダプター、Wcf-wshttp 送信アダプター  

#### <a name="proxyusername"></a>ProxyUserName
指定されているプロキシ サーバーを使用するユーザー名を指定、 **ProxyAddress**プロパティ。 場合、プロパティは必須、 **ProxyToUse**プロパティに設定されて**UserSpecified**します。

このプロパティの詳細については、[、Wcf-wshttp 送信ポートを構成する方法](../core/how-to-configure-a-wcf-wshttp-send-port.md)と[Wcf-basichttp 送信ポートを構成する方法](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f)を参照してください。

型:String  
適用対象Wcf-basichttp 送信アダプター、Wcf-wshttp 送信アダプター

#### <a name="replytoaddress"></a>ReplyToAddress
要求 - 応答受信場所を介して受信された受信メッセージに対応する送信 WCF メッセージの応答エンドポイント アドレスを指定します。 このプロパティは、受信メッセージから自動的に昇格されます。

型:String  
既定値:空の文字列  
適用対象すべての WCF アダプター*を除く*Wcf-netmsmq アダプター

#### <a name="securitymode"></a>SecurityMode
使用するセキュリティの種類を指定します。 適用可能な値は、WCF アダプタごとに異なります。 詳細については、 **SecurityMode**プロパティの各 WCF アダプタの操作方法に関するトピックを参照してください[WCF アダプタ](../core/wcf-adapters.md)します。 

**注:**  
このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。

型:String  
適用対象すべての WCF アダプター*を除く*Wcf-custom および Wcf-customisolated アダプター

#### <a name="sendtimeout"></a>SendTimeout
送信操作が完了するまでの間隔を示す期間値を指定します。 この値は、送信者が大きなメッセージを送信した場合、対話処理がすべて完了するまでの時間を指定します。

型:String  
既定値:00:01:00  
適用対象すべての WCF アダプター*を除く*Wcf-custom および Wcf-customisolated アダプター

#### <a name="servicebehaviorconfiguration"></a>ServiceBehaviorConfiguration
XML 文字列を指定、 **\<動作\>** の要素、 **\<serviceBehaviors\>** WCF の動作の設定を構成するのにはサービス。 詳細については、 **\<serviceBehaviors\>** 要素では、「も該当するトピックを参照してください。

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

型:String  
既定値:空の文字列  
適用対象Wcf-custom 受信アダプター、Wcf-customisolated アダプター

#### <a name="servicecertificate"></a>ServiceCertificate
このプロパティを受信場所で使用する場合、クライアントがサービスの認証に使用する、この受信場所に対する X.509 証明書の拇印を指定します。 このプロパティに使用する証明書をインストールする必要があります、**マイ**で格納、**現在のユーザー**場所。

このプロパティを送信ポートで使用する場合、この送信ポートのメッセージ送信先のサービスの認証に使用する X.509 証明書の拇印を指定します。 このプロパティに使用する証明書をインストールする必要があります、**その他のユーザー**で格納、**ローカル マシン**場所。

型:String  
既定値:空の文字列  
適用対象 
- Wcf-basichttp アダプター
- Wcf-netmsmq アダプター
- WCF-WSHttp アダプタ
- WCF-NetTcp 受信アダプタ

#### <a name="suspendmessageonfailure"></a>SuspendMessageOnFailure
受信パイプラインまたはルーティングの障害によって受信処理に失敗した要求メッセージを保留するかどうかを指定します。

型:ブール値  
既定値:True  
適用対象すべての WCF 受信アダプタ  

#### <a name="textencoding"></a>TextEncoding
文字セットのバインディングでメッセージを出力するために使用するエンコードを指定するときに、 **MessageEncoding**プロパティに設定されて**テキスト**します。 

**注:**  
このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。 

型:String  
既定値: utf-8  

    Applicable values are:  
        - unicodeFFF: Unicode BigEndian encoding
        - utf-16: 16-bit encoding
        - utf-8: 8-bit encoding

適用対象Wcf-basichttp アダプター、Wcf-wshttp アダプター
  
#### <a name="timetolive"></a>TimeToLive
メッセージが期限切れになり、配信不能キューに格納されるまでのメッセージが有効な期間を指定します。 このプロパティは、時間が重要な要素になるメッセージが送信ポートによって処理されるまで古くならないようにするために設定されます。 指定された時間間隔内にこの送信ポートによって処理されないキュー内のメッセージは、期限切れのメッセージといいます。 期限切れのメッセージは、配信不能キューと呼ばれる特別なキューに送信されます。 配信不能キューの場所に設定されて、 **DeadLetterQueue**プロパティ。

型:String  
既定値:1.00:00:00  
適用対象Wcf-netmsmq 送信アダプター

#### <a name="to"></a>目的
WCF 送信ポートが送信する送信 WCF メッセージの送信先エンドポイント アドレスを指定します。

型:String  
既定値:空の文字列  
適用対象すべての WCF 送信アダプタ  

#### <a name="transactionprotocol"></a>TransactionProtocol
このバインドで使用するトランザクション プロトコルを指定します。 このプロパティは必要な場合、 **EnableTransaction**プロパティに設定されて**True**。

型:String  
既定値:OleTransaction  

    Applicable values are: OleTransaction, WS-AtomicTransaction

適用対象Wcf-netnamedpipe アダプター、Wcf-nettcp アダプター  

#### <a name="transportclientcredentialtype"></a>TransportClientCredentialType
送信ポート認証の実行時に使用する資格情報の種類を指定します。 適用可能な値は、WCF アダプタごとに異なります。 詳細については、 **TransportClientCredentialType**プロパティの各 WCF アダプタの操作方法に関するトピックを参照してください[WCF アダプタ](../core/wcf-adapters.md)します。

型:String  
適用対象Wcf-basic アダプター、Wcf-nettcp アダプター、Wcf-wshttp アダプター  

#### <a name="transportprotectionlevel"></a>TransportProtectionLevel
TCP トランスポートのレベルでのセキュリティを指定します。 メッセージに署名を付けることで、メッセージの転送中に第三者によって改ざんされるリスクが軽減されます。 暗号化によって、トランスポート中にデータ レベルのプライバシーが提供されます。

型:String  
既定値:**EncryptAndSign**  

    Applicable values are:  
        - None: No protection
        - Sign: Messages are signed
        - EncryptAndSign: Messages are encrypted and signed

適用対象Wcf-nettcp アダプター、Wcf-netnamedpipe アダプター  

#### <a name="username"></a>UserName
移行先サーバーでの認証に使用するユーザー名を指定するときに、 **UseSSO**プロパティに設定されて**False**します。 このプロパティでは domain\user 形式は使用できません。

型:String  
既定値:空の文字列  
適用対象すべての WCF 送信アダプタ*を除く*Wcf-netnamedpipe アダプター

#### <a name="usesourcejournal"></a>UseSourceJournal
この送信ポートによって処理されるメッセージのコピーをソース ジャーナル キューに保存する必要があるかどうかを指定します。

型:ブール値  
既定値:False  
適用対象Wcf-netmsmq 送信アダプター  

#### <a name="usesso"></a>UseSSO
接続先のサーバーでの認証でクライアントの資格情報を取得する際に、シングル サインオンを使用するかどうかを指定します。 

**注:**  
このプロパティは、追跡プロファイルを使用して、BAM プライマリ インポート データベースで追跡することはできません。 

型:ブール値  
既定値:False  
適用対象すべての WCF 送信アダプタ*を除く*Wcf-netnamedpipe アダプター

#### <a name="referencedbindings"></a>ReferencedBindings
によって参照されるバインド構成を指定、 **bindingConfiguration**の属性、 **\<発行者\>** の要素、 **wsFederationHttpBinding**と**customBinding**、セキュリティ トークン サービス (STS) セキュリティ トークンを発行することを示します。 詳細については、 **\<発行者\>** 要素のトピック「」を参照してください"\<発行者\>"で[ http://go.microsoft.com/fwlink/?LinkId=83476](http://go.microsoft.com/fwlink/?LinkId=83476)します。

バインド情報など、 **\<発行者\>** の要素、 **wsFederationHttpBinding**と**customBinding**できます使用して構成、 **BindingConfiguration** Wcf-custom および Wcf-customisolated アダプターのプロパティ。 このプロパティの参照先のバインド構成のすべての形式で配置する必要があります、 [\<バインド\>](http://go.microsoft.com/fwlink/?LinkID=80878)要素。 

**注:**  
**BindingConfiguration**の属性、 **\<発行者\>** 要素は、このプロパティで有効なバインド名を指す必要があります。 

**注:**  
**\<発行者\>** この参照チェーンが循環する依存関係を行わない場合は、参照されるバインド構成要素はこのプロパティで異なるバインド構成を参照もできます。 

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

**注:**  
**ReferencedBinding**プロパティにはで使用されるバインド構成が含まれていない必要があります、 **BindingConfiguration**プロパティ。

型:String  
既定値:空の文字列  
適用対象WCF カスタム アダプター、Wcf-customisolated アダプター
  
## <a name="see-also"></a>参照  
 [WCF アダプタ](../core/wcf-adapters.md)   
 [\<動作\>の\<endpointBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=80879)   
 [\<バインド\>](http://go.microsoft.com/fwlink/?LinkId=80878)   
 [\<動作\>の\<serviceBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=81095)   
 [メッセージの配信を順序付け](../core/ordered-delivery-of-messages.md)   
 [負荷分散](http://go.microsoft.com/fwlink/?LinkId=81089)
