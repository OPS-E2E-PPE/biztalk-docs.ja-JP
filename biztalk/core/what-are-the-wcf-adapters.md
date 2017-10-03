---
title: "WCF アダプタについて | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18ca8535-3386-4018-8b5b-d32bdb9ebf70
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41c942c7c2ef870b2a61c519e79fb8a124059f03
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-are-the-wcf-adapters"></a>WCF アダプタについて
Windows Communication Foundation (WCF) アダプタには、受信アダプタと送信アダプタの 2 つがあります。 WCF 受信アダプタは、WCF サービス要求を受信するために使用します。 WCF 受信アダプタは、要求の受信、BizTalk メッセージ オブジェクトの作成、および関連するプロパティのメッセージ コンテキストへの昇格を行います。 WCF 送信アダプタは、WCF サービスを呼び出すときに使用します。 WCF 送信アダプタは、型宣言が不要なコントラクトを使用して WCF サービスを呼び出します。  
  
> [!NOTE]
>  WCF アダプタは、リモート プロシージャ コール (RPC) スタイルの Web サービスの使用をサポートしていません。これは、WCF アダプタがメッセージ部分の要素を使用しているメッセージ要素ではなく、メッセージの種類を RPC スタイルの Web サービスが参照するためです。 BizTalk プロジェクトで Web サービスを使用する場合、Web 参照の追加ウィザードを使用して RPC スタイルの Web サービスを追加することをお勧めします。  
  
## <a name="web-services-standards-support"></a>Web サービスの標準サポート  
 WCF アダプタは、WS-Addressing、WS-Security、WS-AtomicTransaction など、WS 標準のサポートを提供しています。 WCF アダプタの現在のリリースでは、WS-ReliableMessaging はサポートされていません。 WCF がサポートする仕様の一覧は、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=88314](http://go.microsoft.com/fwlink/?LinkId=88314)です。  
  
### <a name="ws-addressing"></a>WS-Addressing  
 WCF アダプタは、WCF が提供している WS-Addressing 標準サポートに依存します。 WCF アダプタでは、次の機能を使用できます。  
  
-   メタデータ交換要求時に取得される送信ポートのエンドポイント アドレスの構成  
  
-   送信ポートのエンドポイント アドレス用のアドレス指定ヘッダーの構成  
  
-   BizTalk 受信場所で公開されるエンドポイント用のアドレス指定ヘッダーの構成  
  
### <a name="ws-security"></a>WS-Security  
 WCF アダプタは、WCF が提供しているセキュリティ標準サポートに依存します。 WCF アダプタでは、次の標準がサポートされています。  
  
-   Web サービスのセキュリティ: SOAP メッセージ セキュリティ (Ws-security) 1.0 および 1.1  
  
-   Web Services Secure Conversation Language (WS-SecureConversation)  
  
-   Web Services Trust Language (WS-Trust)  
  
-   Web Services Security X.509 Certificate Token Profile  
  
-   Web Services Security Username Token Profile 1.0  
  
-   Web Services Security Kerberos Token Profile 1.0  
  
#### <a name="service-authentication-types"></a>サービス認証の種類  
 次の WCF サービス認証の種類がサポートされています。  
  
-   なし  
  
-   Windows  
  
-   Certificate  
  
#### <a name="client-authentication-types"></a>クライアント認証の種類  
 次の WCF クライアント認証の種類がサポートされています。  
  
-   匿名  
  
-   UserName  
  
-   Windows  
  
-   Certificate  
  
#### <a name="security-modes"></a>セキュリティ モード  
 次のセキュリティ モードがサポートされています。  
  
-   [Transport]  
  
-   メッセージ  
  
-   Mixed (トランスポート レベルのセキュリティとメッセージ レベルの認証)  
  
### <a name="ws-atomictransaction"></a>WS-AtomicTransaction  
 WCF-WsHttp、WCF-NetTcp、および WCF-NetMsmq の各アダプタは WS-AtomicTransaction プロトコルをサポートしています。 このサポートにより次のシナリオが有効となります。  
  
-   メッセージ ボックス データベースへのメッセージのトランザクション送信  
  
-   メッセージ ボックス データベースからのメッセージのトランザクション送信  
  
> [!NOTE]
>  トランザクション スコープは、メッセージ ボックスにより制限されます。 たとえば、BizTalk オーケストレーションはクライアントのトランザクションに参加できません。 同様に、送信先エンドポイントは、BizTalk オーケストレーションが開始したトランザクションに参加できません。  
  
#### <a name="transactional-submission"></a>トランザクション送信  
 選択すると、Wcf-wshttp、Wcf-nettcp アダプターの BizTalk Server へのトランザクション送信が有効になって、**トランザクションを有効にする**受信場所のトランスポートのプロパティ ダイアログ ボックスのチェック ボックスをオンします。 Wcf-netmsmq アダプターの場合、**トランザクション** チェック ボックスが既定で選択します。 メッセージの抽出元のメッセージ キューがトランザクションとして指定されていない場合、このチェック ボックスをオフにする必要があります。オフにしないと、エラー メッセージを受け取ります。  
  
 トランザクション機能が有効の場合、クライアントのトランザクションを使用して、メッセージがメッセージ ボックス データベースに送信されます。 クライアントがトランザクションのスコープ外のメッセージを送信しようとすると、アダプタはそのクライアントに例外を返します。 ただし、メッセージは中断されません。 トランザクション機能が無効の場合、クライアントのトランザクションを使用せずに、メッセージがメッセージ ボックスに送信されます。 クライアントがトランザクション スコープ内のメッセージを送信しようとすると、アダプタはそのクライアントに例外を返し、メッセージは中断されません。  
  
#### <a name="transactions-and-receive-location-type"></a>トランザクションと受信場所の種類  
 トランザクション送信は、一方向の受信場所に対してのみ使用できます。 クライアントが、双方向の受信場所に対し、トランザクション スコープ内のメッセージを送信しようとすると、例外がそのクライアントに返され、メッセージは中断されません。  
  
#### <a name="transactional-transmission"></a>トランザクション送信  
 選択すると、Wcf-wshttp、Wcf-nettcp アダプターの BizTalk Server からのトランザクション送信が有効になって、**トランザクションを有効にする**送信ポート トランスポートのプロパティ ダイアログ ボックスのチェック ボックスをオンします。 Wcf-netmsmq アダプターの場合、**トランザクション** チェック ボックスが既定で選択します。 メッセージの送信先のメッセージ キューがトランザクションとして指定されていない場合、このチェック ボックスをオフにする必要があります。オフにしないと、エラー メッセージを受け取ります。  
  
 トランザクション機能が有効の場合、トランザクションでメッセージが送信され、そのメッセージがメッセージ ボックス データベースから削除されます。 メッセージ受信後、送信先サービスがなんらかの操作を実行した場合、メッセージはメッセージ ボックスから削除されず、トランザクションは中止され、サービスのすべてのトランザクション操作がロールバックされます。 トランザクション機能が無効の場合、トランザクションを使用せずにメッセージが送信され、そのメッセージがメッセージ ボックスから削除されます。  
  
## <a name="single-sign-on-support"></a>シングル サインオンのサポート  
 エンタープライズ シングル サインオン (SSO) チケットを借用および取得することで、SSO を WCF アダプタで使用できます。 WCF アダプタで SSO を使用する方法の詳細については、次を参照してください。 [WCF アダプタのシングル サインオン サポート](../core/single-sign-on-support-for-the-wcf-adapters.md)です。  
  
 次の表に、WCF 受信アダプタで SSO サポートを使用する場合にサポートされないシナリオを示します。  
  
|[セキュリティ モード]|資格情報|  
|-------------------|----------------|  
|なし|なし|  
|[Transport]|なし|  
|メッセージ|なし|  
|TransportWithMessageCredentials|なし|  
|TransportCredentialOnly|なし|  
  
## <a name="wcf-extensibility"></a>WCF 拡張機能  
 次の拡張機能を開発し、WCF-Custom アダプタおよび WCF-CustomIsolated アダプタでこれらの拡張機能を使用することで、WCF の機能を拡張できます。  
  
-   カスタム バインド  
  
-   カスタム バインド要素  
  
### <a name="custom-bindings"></a>カスタム バインド  
 カスタム バインドを開発するには、特定の使用シナリオのために構成プロパティのサブセットを公開するコンテナ内に個々のバインド要素をパッケージ化します。 アセンブリをグローバル アセンブリ キャッシュ (GAC) 内にインストールし、その後、拡張機能の要素をコンピュータの構成ファイルに追加することで、バインド拡張機能を登録する必要があります。 カスタム バインドを使用するには、BizTalk グループ内のすべてのサーバーでバインドを設定する必要があります。 バインドは、インストールすると、WCF-Custom アダプタおよび WCF-CustomIsolated アダプタによって認識されるようになります。 WCF-Custom アダプタと WCF-CustomIsolated アダプタは、バインド構成要素に対しリフレクションを使用することで、バインド構成プロパティを取得します。  
  
### <a name="custom-binding-elements"></a>カスタム バインド要素  
 カスタム バインド要素は、特定のトランスポート チャネル コンポーネントを追加または変更することで開発します。 たとえば、カスタム圧縮解除コンポーネントをバインド要素としてパッケージ化したり、UDP トランスポートをバインド要素として表したりします。 これらのバインド要素は、WCF アダプタ内で使用できます。 他の既定要素またはカスタム バインド要素と組み合わせて、カスタム バインド要素を使用するチャネル スタックを定義できます。 アセンブリを GAC 内にインストールし、その後、拡張機能の要素をコンピュータの構成ファイルに追加することで、バインド要素拡張機能を登録する必要があります。 カスタム バインドを使用するには、BizTalk グループ内のすべてのサーバーでバインドを設定する必要があります。 使用するには、カスタム バインド要素を選択できます、 **CustomBinding**バインドの種類を追加、変更、または目的の順序内のバインド要素を再配置します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [WCF 受信アダプター](../core/wcf-receive-adapter.md)  
  
-   [WCF 送信アダプタ](../core/wcf-send-adapter.md)  
  
## <a name="see-also"></a>参照  
-  [WCF アダプタ](../core/wcf-adapters.md)   
-  **WCF アダプタ サービス コントラクト リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]