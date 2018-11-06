---
title: Wcf-wshttp 送信ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 035d9a62-b8a3-4705-a7bc-b62676437206
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4b27136c01db4414d43d30790474a0deb339aee
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752352"
---
# <a name="how-to-configure-a-wcf-wshttp-send-port"></a>WCF-WSHttp 送信ポートを構成する方法
WCF-WSHttp 送信ポートは、プログラムから、または BizTalk 管理コンソールを使用して構成できます。  

## <a name="configuration-properties"></a>構成プロパティ

 BizTalk エクスプ ローラー オブジェクト モデルは、という名前の送信ポートのアダプター固有のインターフェイスを公開します。 **ITransportInfo**を持つ、 **TransportTypeData**読み取り/書き込みプロパティ。 このプロパティでは、名前と値のペアの XML 文字列の形式で WCF-WSHttp 送信ポートの構成プロパティ バッグを指定できます。  

 **TransportTypeData**のプロパティ、 **ITransportInfo**インターフェイスは必要ありません。 このプロパティを設定しない場合、アダプタでは、次の表に記載されている WCF-WSHttp 送信ポートの構成の既定値が使用されます。  

 次の表に、BizTalk エクスプローラ オブジェクト モデルで WCF-WSHttp 送信ポート用に設定できる構成プロパティを示します。  


| プロパティ名 | 型 |  説明 |
|---|---|---|
| **[ID]**            |  XML Blob<br /><br /> 例:<br /><br /> &lt;identity&gt;<br /><br /> &lt;userPrincipalName value="username@contoso.com" /&gt;<br /><br /> &lt;/identity&gt; |  この送信ポートが必要とするサービスの ID を指定します。 これらの設定により、この送信ポートでサービスを認証できます。 クライアントとサービスの間のハンドシェイク プロセスでは、Windows Communication Foundation (WCF) インフラストラクチャによって、この要素の値と予期されるサービスの ID が照合されます。<br /><br /> 既定値は空の文字列です。  |
|  **StaticAction**          |  -文字列  | 指定、 **SOAPAction**送信メッセージの HTTP ヘッダー フィールド。 このプロパティは、メッセージ コンテキスト プロパティも設定できます**WCF です。アクション**パイプラインまたはオーケストレーションします。 2 つの方法でこの値を指定することができます。 シングル アクション形式とアクション マッピング形式。 たとえば、1 つのアクションの形式でこのプロパティを設定した場合 <`http://contoso.com/Svc/Op1-`>、 **SOAPAction**このプロパティで指定された値を設定は常に送信メッセージのヘッダー。<br /><br /> 送信アクション マッピング形式でこのプロパティを設定する場合**SOAPAction**ヘッダーはによって決定されます、 **BTS します。操作**コンテキスト プロパティ。 たとえば、このプロパティは、次の XML 形式に設定されている場合、 **BTS です。操作**を Op1 に設定されているプロパティ、WCF 送信アダプタを使用して <http://contoso.com/Svc/Op1> アウトゴーイング**SOAPAction**ヘッダー。<br /><br /> \<BtsActionMapping\><br /><br /> \<Operation Name="Op1" Action="<http://contoso.com/Svc/Op1>" /\><br /><br /> \<操作名"Op2"アクションを = ="<http://contoso.com/Svc/Op2>"/\><br /><br /> \</BtsActionMapping\><br /><br /> 送信メッセージがオーケストレーション ポートに由来する場合、オーケストレーション インスタンスは動的に設定、 **BTS します。操作**ポートの操作の名前を持つプロパティです。 設定することができますコンテンツ ベースのルーティングでは、送信メッセージがルーティングされている場合、 **BTS します。操作**パイプライン コンポーネントのプロパティ。<br /><br /> 既定値は空の文字列です。 |
|          **OpenTimeout**          | **System.TimeSpan** |  チャネルを開く操作が完了するまでの間隔を示す期間値を指定します。<br /><br /> 既定値:00:01:00  |
|          **SendTimeout**          | **System.TimeSpan**  |  送信操作が完了するまでの間隔を示す期間値を指定します。 送信請求 - 応答の送信ポートを使用する場合は、サービスから大きいメッセージが返される場合でも、この値には対話処理がすべて完了するまでの時間を指定します。<br /><br /> 既定値:00:01:00  |
|         **CloseTimeout**          |  **System.TimeSpan**  |  チャネルを閉じる操作が完了するまでの間隔を示す期間値を指定します。<br /><br /> 既定値:00:01:00  |
|    **MaxReceivedMessageSize**     | Integer  | 有線ネットワーク上で受信できる、ヘッダーを含むメッセージの最大サイズをバイト単位で指定します。 メッセージのサイズは、各メッセージに割り当てられているメモリの量に制限されます。 このプロパティを使用して、サービス拒否 (DoS) 攻撃にさらされる危険性を制限できます。<br /><br /> 既定値:65536  |
|        **MessageEncoding**        |  Enum<br /><br /> -   **テキスト**-テキスト メッセージ エンコーダーを使用します。<br />-   **Mtom** -Message Transmission 組織 Mechanism 1.0 (MTOM) エンコーダーを使用します。  |  SOAP メッセージをエンコードするために使用されるエンコーダーを指定します。<br /><br /> 既定値:**テキスト**  |
|         **TextEncoding**          | Enum<br /><br /> -   **unicodeFFF** -Unicode BigEndian エンコーディングします。<br />-   **utf-16** : 16 ビット エンコードします。<br />-   **utf-8** : 8 ビット エンコードします。  | 文字セットのバインディングでメッセージを出力するために使用するエンコードを指定するときに、 **MessageEncoding**プロパティに設定されて**テキスト**します。<br /><br /> 既定値: **utf-8**  |
|       **EnableTransaction**       |  ブール値  |  メッセージが転送先サービスに転送され、トランザクション コンテキストを使用して、メッセージ ボックス データベースから削除するかどうかを指定、 **WS-AtomicTransaction**プロトコル。<br /><br /> 既定値: **False**  |
|         **SecurityMode**          |  Enum<br /><br /> -   **[なし]**<br />-   **メッセージ**<br />-   **トランスポート**<br />-   **TransportWithMessageCredential**<br /><br /> メンバー名の詳細については、 **SecurityMode**プロパティを参照してください、**セキュリティ モード**プロパティ、 **Wcf-wshttp トランスポートのプロパティ ダイアログ ボックスの送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。   | 使用するセキュリティの種類を指定します。<br /><br /> 既定値:**なし**  |
| **TransportClientCredentialType** |  Enum<br /><br /> -   **[なし]**<br />-   **基本的な**<br />-   **Windows**<br />-   **証明書**<br />-   **ダイジェスト**<br />-   **Ntlm**<br /><br /> メンバー名の詳細については、 **TransportClientCredentialType**プロパティを参照してください、**クライアント資格情報の種類のトランスポート**プロパティ、 **Wcf-wshttp トランスポートプロパティ ダイアログ ボックスで、送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。  |  送信ポート認証の実行時に使用する資格情報の種類を指定します。<br /><br /> 既定値:**なし**  |
|  **MessageClientCredentialType**  | Enum<br /><br /> -   **[なし]**<br />-   **Windows**<br />-   **ユーザー名**<br />-   **証明書**<br /><br /> メンバー名の詳細については、 **MessageClientCredentialType**プロパティを参照してください、**クライアント資格情報の種類のメッセージ**プロパティ、 **Wcf-wshttp トランスポートのプロパティダイアログ ボックスで、送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。  | メッセージ ベースのセキュリティを使用してクライアント認証を実行するときに使用する、資格情報の種類を指定します。<br /><br /> 既定値:**ユーザー名**  |
|        **AlgorithmSuite**         | Enum<br /><br /> メンバー名の詳細については、 **AlgorithmSuite**プロパティを参照してください、**アルゴリズム スイート**プロパティ、 **Wcf-wshttp トランスポートのプロパティ ダイアログ ボックスの送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。  |  メッセージの暗号化とキー ラップのアルゴリズムを指定します。 これらのアルゴリズムは、セキュリティ ポリシー言語 (WS-SecurityPolicy) 仕様で指定されたアルゴリズムにマップされます。<br /><br /> 既定値: **Basic256**  |
|  **NegotiateServiceCredential**   |  ブール値<br /><br /> メンバー名の詳細については、 **NegotiateServiceCredential**プロパティを参照してください、**サービス資格情報をネゴシエート**プロパティ、 **Wcf-wshttp トランスポートのプロパティダイアログ ボックスで、送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。 |  サービスの資格情報が帯域外のこの送信ポートで提供されるか、またはネゴシエーションのプロセスによってこの送信ポートへのサービスから取得されるかを指定します。 そのようなネゴシエーションは、通常のメッセージ交換の準備です。<br /><br /> 既定値: **False**|
|     **EnableSecurityContext**     | ブール値  |  を通じて、セキュリティ コンテキスト トークンが確立されているかどうかを指定、 **Ws-secureconversation**この送信ポートとサービス間で交換します。 このプロパティ設定されている場合**True**転送先サービスをサポートする必要がありますし、 **Ws-secureconversation**します。<br /><br /> 既定値:**は True。**  |
|       **ClientCertificate**       | String  |  この送信ポートをサービスに対して認証する際に使用する X.509 証明書の拇印を指定します。 このプロパティは必要な場合、 **ClientCredentialsType**プロパティに設定されて**証明書**します。 このプロパティに使用する証明書をインストールする必要があります、**マイ**で格納、**現在のユーザー**場所。<br /><br /> 既定値は空の文字列です。 |
|      **ServiceCertificate**       |  String  |  この送信ポートのメッセージ送信先のサービスを認証する際に使用する X.509 証明書の拇印を指定します。 このプロパティに使用する証明書をインストールする必要があります、**その他のユーザー**で格納、**ローカル マシン**場所。<br /><br /> 既定値は空の文字列です。  |
|   **AffiliateApplicationName**    |  String  | エンタープライズ シングル サインオン (SSO) に使用する関連アプリケーションを指定します。<br /><br /> 既定値は空の文字列です。 |
|            **UseSSO**             |   ブール値  |  接続先のサーバーでの認証でクライアントの資格情報を取得する際に、シングル サインオンを使用するかどうかを指定します。<br /><br /> 既定値: **False** |
|           **UserName**            |  String  |  移行先サーバーでの認証に使用するユーザー名を指定するときに、 **UseSSO**プロパティに設定されて**False**します。 このプロパティでは domain\user 形式は使用できません。<br /><br /> 既定値は空の文字列です。 |
|           **Password**            |  String  | 移行先サーバーでの認証に使用するパスワードを指定するときに、 **UseSSO**プロパティに設定されて**False**。<br /><br /> 既定値は空の文字列です。 |
|          **ProxyToUse**           | Enum<br /><br /> -   **None** -この送信ポートのプロキシ サーバーを使わないでください。<br />-   **既定の**-この送信ポートをホストする送信ハンドラーのプロキシ設定を使用します。<br />-   **UserSpecified** -で指定されたプロキシ サーバーを使用して、 **ProxyAddress**プロパティ。  | 送信 HTTP トラフィックに使用するプロキシ サーバーを指定します。<br /><br /> 既定値:**なし**  |
|         **ProxyAddress**          | String |  プロキシ サーバーのアドレスを指定します。 使用して、 **https**または**http**セキュリティ構成に応じてスキーム。 このアドレスの後に、コロンとポート番号を指定します。 たとえば、 `http://127.0.0.1:8080` のようにします。<br /><br /> 既定値は空の文字列です。 |
|         **ProxyUserName**         |  String  | プロキシに使用するユーザー名を指定します。 Wcf-wshttp アダプター活用して、 [WSHttpBinding](http://go.microsoft.com/fwlink/?LinkId=81206)エンドポイントとの通信に、バッファリングされた送信モードでします。 プロキシの資格情報の**WSHttpBinding**セキュリティ モードが場合にのみ適用されます**トランスポート**、または**None**します。 設定した場合、 **SecurityMode**プロパティを**メッセージ**または**TransportWithMessageCredential**、Wcf-wshttp アダプタは、で指定された資格情報を使用しません**ProxyUserName**と**ProxyPassword**プロキシに対する認証のプロパティ。 **注:** Wcf-wshttp 送信アダプターの使用、プロキシに対して基本認証。 <br /><br /> 既定値は空の文字列です。  |
|         **ProxyPassword**         |  String  |  プロキシに使用するパスワードを指定します。<br /><br /> 既定値は空の文字列です。|
|     **OutboundBodyLocation**      |  Enum<br /><br /> -   **UseBodyElement** -BizTalk メッセージのボディ部を使用して、SOAP のコンテンツを作成する**本文**送信メッセージの要素。<br />-   **UseTemplate** -で提供されているテンプレートを使用して、 **OutboundXMLTemplate** 、SOAP のコンテンツを作成するプロパティ**本文**送信メッセージの要素。<br /><br /> 使用する方法についての詳細、 **OutboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)します。  |  SOAP データ選択を指定**本文**送信 WCF メッセージの要素。<br /><br /> 既定値: **UseBodyElement**  |
|      **OutboundXMLTemplate**      |  String<br /><br /> 使用する方法についての詳細、 **OutboundXMLTemplate**プロパティを参照してください[WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)します。  |  SOAP のコンテンツを XML 形式のテンプレートを指定**本文**送信メッセージの要素。 このプロパティは必要な場合、 **OutboundBodyLocation**プロパティに設定されて**UseTemplate**します。<br /><br /> 既定値は空の文字列です。  |
|      **InboundBodyLocation**      | Enum<br /><br /> -   **UseBodyElement** -SOAP のコンテンツを使用して**本文**BizTalk メッセージのボディ部を作成する受信メッセージの要素。 **Body** 要素に複数の子要素がある場合は、最初の要素のみが BizTalk メッセージのボディ部になります。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br />-   **UseEnvelope** -全体の SOAP から BizTalk メッセージのボディ部を作成する**エンベロープ**受信メッセージのです。<br />-   **UseBodyPath** -ボディ パス式を使用して、 **InboundBodyPathExpression**プロパティを BizTalk メッセージのボディ部を作成します。 ボディ パス式は、受信メッセージの SOAP **Body** 要素のすぐ下の子要素に対して評価されます。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 使用する方法についての詳細、 **InboundBodyLocation**プロパティを参照してください[WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)します。 |  SOAP データ選択を指定**本文**受信 WCF メッセージの要素。<br /><br /> 既定値: **UseBodyElement**  |
|   **InboundBodyPathExpression**   |  String<br /><br /> 使用する方法についての詳細、 **InboundBodyPathExpression**プロパティを参照してください[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)します。  |  BizTalk メッセージのボディ部を作成するために使用する受信メッセージの特定の部分を示すボディ パス式を指定します。 このボディ パス式は、SOAP の直接の子要素に対して評価される**本文**受信メッセージのノード。 このボディ パス式で複数のノードが返される場合は、最初のノードのみが BizTalk メッセージのボディ部に対して選択されます。 このプロパティは必要な場合、 **InboundBodyLocation**プロパティに設定されて**UseBodyPath**します。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 既定値は空の文字列です。  |
|      **InboundNodeEncoding**      |  Enum<br /><br /> -   **Base64** -Base64 エンコードします。<br />-   **16 進**: 16 進エンコーディングします。<br />-   **文字列**: テキスト エンコード - utf-8。<br />-   **XML** -ボディ パス式で選択されたノードの外部の XML で WCF アダプターが BizTalk メッセージ本文を作成**InboundBodyPathExpression**します。  |  指定されたボディ パスで識別されるノードに対して、Wcf-wshttp 送信アダプターがデコードに使用するエンコードの種類を指定**InboundBodyPathExpression**します。 このプロパティは必要な場合、 **InboundBodyLocation**プロパティに設定されて**UseBodyPath**します。 このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 既定値: **XML**  |
|     **PropagateFaultMessage**     | ブール値<br /><br /> -   **True** -サブスクライブするアプリケーションの送信処理に失敗したメッセージのルーティング (別の受信ポートやオーケストレーション スケジュールなど)。<br />-   **False** -一時停止に失敗したメッセージおよび否定受信確認応答 (NACK) を生成します。 |  送信処理に失敗したメッセージをルーティングまたは中断するかどうかを指定します。<br /><br /> このプロパティは、送信請求 - 応答のポートに対してのみ有効です。<br /><br /> 既定値:**は True。**  |

## <a name="configure-a-wcf-wshttp-send-port-with-the-biztalk-administration-console"></a>BizTalk 管理コンソールで、Wcf-wshttp 送信ポートを構成します。

 BizTalk 管理コンソールで、WCF-WSHttp 送信ポート アダプタの変数を設定できます。 プロパティが送信ポートに設定されていない場合は、上の表に記載されている WCF-WSHttp 送信ポートの構成の既定値が使用されます。  

## <a name="configure-variables-for-a-wcf-wshttp-send-port"></a>Wcf-wshttp 送信ポートの変数を構成します。  

1. BizTalk 管理コンソールで、新しい送信ポートを作成するか、既存の送信ポートをダブルクリックして変更します。 詳細については、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)します。 すべての送信ポートのオプションを構成し、指定**Wcf-wshttp**の**型**オプション、**トランスポート**のセクション、**全般**タブ。  

2. **全般**] タブで、**トランスポート**セクションで、[、**構成**横に**型**します。  

3. **Wcf-wshttp トランスポートのプロパティ** ダイアログ ボックスの 、**全般** タブで、エンドポイント アドレス、サービスの id を構成し、 **SOAPAction**用の HTTP ヘッダーWcf-wshttp 送信ポートです。 詳細については、**全般** タブで、 **Wcf-wshttp トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-wshttp トランスポートのプロパティ ダイアログ ボックス、送信、一般的な**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。  

4. **Wcf-wshttp トランスポートのプロパティ** ダイアログ ボックスで、**バインド** タブで、タイムアウト、エンコード、およびトランザクションのプロパティを構成します。 詳細については、**バインド** タブで、 **Wcf-wshttp トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-wshttp トランスポートのプロパティ ダイアログ ボックスの送信、バインド**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。  

5. **Wcf-wshttp トランスポートのプロパティ** ダイアログ ボックスで、**セキュリティ** タブで、Wcf-wshttp 送信ポートのセキュリティ機能を定義します。 詳細については、**セキュリティ** タブで、 **Wcf-wshttp トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-wshttp トランスポートのプロパティ ダイアログ ボックスの送信、セキュリティ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。

6. **Wcf-wshttp トランスポートのプロパティ** ダイアログ ボックスで、**プロキシ** タブで、Wcf-wshttp 送信ポートのプロキシ設定を構成します。 詳細については、**プロキシ** タブで、 **Wcf-wshttp トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-wshttp トランスポートのプロパティ ダイアログ ボックスの送信、プロキシ** タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

7. **Wcf-wshttp トランスポートのプロパティ** ダイアログ ボックスで、**メッセージ** タブで、SOAP のデータ選択を指定**本文**要素。 詳細については、**メッセージ** タブで、 **Wcf-wshttp トランスポートのプロパティ**ダイアログ ボックスを参照してください、 **Wcf-wshttp トランスポートのプロパティ ダイアログ ボックスの送信、メッセージ**タブ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。

## <a name="configure-a-wcf-wshttp-send-port-programmatically"></a>プログラムから Wcf-wshttp 送信ポートを構成します。

 次の形式を使用してプロパティを設定できます。  

```  
 <CustomProps>    
  <ServiceCertificate vt="8" />  
  <UseSSO vt="11">0</UseSSO>  
  <InboundBodyPathExpression vt="8" />  
  <MessageClientCredentialType vt="8">Windows</MessageClientCredentialType>  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <Identity vt="8" />  
  <AlgorithmSuite vt="8">Basic256</AlgorithmSuite>  
  <SecurityMode vt="8">Message</SecurityMode>  
  <TransportClientCredentialType vt="8">Windows</TransportClientCredentialType>  
  <TextEncoding vt="8">utf-8</TextEncoding>  
  <NegotiateServiceCredential vt="11">-1</NegotiateServiceCredential>  
  <MaxReceivedMessageSize vt="3">2097152</MaxReceivedMessageSize>  
  <ClientCertificate vt="8" />  
  <ProxyUserName vt="8" />  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <ProxyToUse vt="8">Default</ProxyToUse>  
  <EnableTransaction vt="11">0</EnableTransaction>  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <EstablishSecurityContext vt="11">-1</EstablishSecurityContext>  
  <StaticAction vt="8">http://www.northwindtraders.com/Service/Operation</StaticAction>  
  <PropagateFaultMessage vt="11">-1</PropagateFaultMessage>  
  <ProxyAddress vt="8" />  
  <MessageEncoding vt="8">Text</MessageEncoding>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
</CustomProps>  

```  

 次のコードは、WCF-WSHttp 送信ポートの作成方法を示しています。  

```  
// Use BizTalk Explorer object model to create new WCF-WSHttp send port.  
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
string transportConfigData = @"<CustomProps>  
                                 <StaticAction vt=""8"">http://www.northwindtraders.com/Service/Operation</StaticAction>  
                                 <MessageEncoding vt=""8"">Text</MessageEncoding>  
                                 <TextEncoding vt=""8"">utf-8</TextEncoding>  
                                 <OpenTimeout vt=""8"">00:01:00</OpenTimeout>  
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
sendPort.PrimaryTransport.TransportType = explorer.ProtocolTypes["WCF-WSHttp"];  
sendPort.PrimaryTransport.Address = "http://mycomputer/samplepath";  
sendPort.PrimaryTransport.TransportTypeData = transportConfigData; // propertyData; // need to change  
sendPort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  
// Save  
explorer.SaveChanges();  
```  

## <a name="see-also"></a>参照  
 [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)   
 [Wcf-wshttp アダプタの構成](../core/configuring-the-wcf-wshttp-adapter.md)   
 [WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [WCF アダプターの証明書のインストール](../core/installing-certificates-for-the-wcf-adapters.md)   
 [WCF アダプター コンテキスト プロパティによる動的送信ポートの構成](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)
