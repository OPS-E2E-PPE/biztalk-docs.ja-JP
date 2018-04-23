---
title: BizTalk Server で使用する Logic App アダプター |Microsoft ドキュメント
description: インストールし、Logic Apps アダプターは受信ポートを作成、受信場所、および BizTalk Server での送信ポートの構成
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72f2a5ac-a1f6-4bdb-8c29-8267ede75b17
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faa43c187df7a8eb9fccd2f02f23f16e86b97ce0
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="logic-app-adapter"></a>ロジック アプリのアダプター

## <a name="overview"></a>概要
BizTalk Server では、Azure のロジック アプリでは、メッセージを受信するか、Azure のロジック アプリにメッセージを送信、Logic Apps アダプターを使用します。 

Azure では、ロジック アプリを作成します。 このロジック アプリでは、BizTalk コネクタを使用して、BizTalk Server で作成した受信場所に接続します。 このトピックでは、Azure Logic Apps をある程度必要があると想定しています。 かどうかは、ロジック アプリに新しいできたら、ことをお勧め [ことに関する詳細な学習](https://azure.microsoft.com/documentation/articles/app-service-logic-what-are-logic-apps/), 、そして [ロジック アプリを作成する](https://azure.microsoft.com/documentation/articles/app-service-logic-create-a-logic-app/)です。

このトピックでは、ロジック アプリから BizTalk Server でメッセージを受信する手順をリストします。 別の言い方を行うには、ロジック アプリは、BizTalk Server にメッセージを送信します。 受信側では、IIS でアプリケーションを使用して、Azure のサービスとの通信を処理します。 BizTalk Server が内部設置型の場合は、また BizTalk Server にデータ ゲートウェイをインストールして Azure でゲートウェイを作成します。 

Azure の仮想マシン (VM) に BizTalk Server がインストールされているかどうかは、VM を (URL で取得)、HTTP エンドポイントとして公開することができますか、HTTP エンドポイントとして公開しません。 公開する場合は、ゲートウェイを使用する必要ありません。 ロジック アプリで BizTalk コネクタに、URL を入力できます。 VM (URL) を公開しない場合は、ゲートウェイを使用する必要があります。 次の手順は、このトピックに記載されています。

また方法を説明メッセージを BizTalk Server から Azure のロジック アプリに送信します。 別の言い方を行うには、ロジック アプリは、BizTalk Server からのメッセージを受信します。 このトピックで確認するため、送信側は、かなり簡単です。

このトピックを使用すると、受信場所と Logic Apps アダプターを使用して送信ポートを作成できます。 ロジック アダプターは、内部設置型 (ドメインに参加している) BizTalk Server、または BizTalk Server を実行する Azure の仮想マシンを使用することができます。 

## <a name="requirements"></a>必要条件

- Azure ポータルにサインインし、ロジック アプリを作成する Azure サブスクリプション。
- 省略可。 ロジック アプリをテスト メッセージを送信するなどのインストール、HTTP のテスト ツール [Fiddler](http://www.telerik.com/fiddler) または [Postman](https://www.getpostman.com/)します。 ロジック アプリにメッセージを送信する別のメソッドを使用する場合は、これらのツールを使用する必要はありません。 

## <a name="receive-messages-from-a-logic-app"></a>ロジック アプリからメッセージを受信します。

ロジック アプリからのメッセージを受信する BizTalk Server には、いくつかの手順があります。 このセクションでは、次の手順を示します。 Azure の変更手順の一部のユーザー インターフェイスが表示されているとおりに正確にできないことができます。 

#### <a name="prerequisites"></a>前提条件

- BizTalk Server が内部設置型の場合は、インストールし、構成、 [内部設置型のデータ ゲートウェイ](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-install/) Logic Apps 向けです。 その後、Azure では、 [データ ゲートウェイのリソースを作成する](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-connection/) 、BizTalk Server に接続します。
- BizTalk Server が、Azure VM にインストールされている VM は HTTP エンドポイントとして公開されない場合は、インストールし、構成、 [内部設置型のデータ ゲートウェイ](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-install/) Logic Apps 向けです。 その後、Azure では、 [データ ゲートウェイのリソースを作成する](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-connection/) 、BizTalk Server に接続します。
- BizTalk Server が、Azure VM にインストールされている VM が HTTP エンドポイントとして公開されている場合は、次ゲートウェイはないために必要なかために使用します。 

### <a name="step-1-install-the-logic-app-adapter"></a>手順 1: ロジック アプリのアダプターをインストールします。

ロジック アプリ アダプターでは、個別のダウンロードし、BizTalk Server のインストールに含まれていません。 

> [!IMPORTANT] 
> LogicAppAdapter.iso をダウンロードします。
> 
> 1. 移動して [Logic Apps 向けの Microsoft BizTalk Server アダプター](https://www.microsoft.com/download/details.aspx?id=54287), 、保存します。 
> 2. LogicAppAdapter.iso を開き、実行、 **ロジック Adapter.msi** ファイルをインストールします。

1. BizTalk Server をダウンロードして、ロジック アプリのアダプターをインストールします。 

2. ダブルクリックして **ロジック Adapter.msi** をインストールします。 ライセンス条項に同意し、 **インストール**します。
3. **[完了]** インストール、d の再起動、 **BizTalkServerApplication** と **BizTalkServerIsolatedHost** インスタンスをホストします。

インストールされると、次があります。

- ロジックのアダプターは、BizTalk 管理コンソールに追加されます。
- 送信ハンドラーが作成され、BizTalkServerApplication ホストを使用します。
- 受信ハンドラーは、WCF サービスとして作成され、BizTalkServerIsolatedHost ホストを使用します。
- `C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter`フォルダーが作成され、2 つのサービスが含まれています: 管理と ReceiveService です。 

    **管理**data gateway を使用して BizTalk Server に接続するアプリケーションでロジック BizTalk Connector が使用されます。 この管理サービスでは、データ ゲートウェイを使用して Azure のロジック アプリからのメッセージを受信する BizTalk Server を使用します。 このサービスは、BizTalk の受信側でのみ使用します。 送信側では使用されません。

    **ReceiveService**受信場所を入力するときは、アプリケーションでロジック BizTalk コネクタによって使用されます。 **ReceiveService**は、logic app からメッセージを送信します。 このサービスは、BizTalk の受信側でのみ使用します。 送信側では使用されません。


### <a name="step-2-create-the-iis-applications"></a>手順 2: IIS のアプリケーションを作成します。

IIS アプリケーションは、管理と ReceiveService サービスを使用します。

新しいアプリケーション プール、または既存のアプリケーション プールを使用して IIS アプリケーションを実行することができます。 AppPool の id には、BizTalk Application Users グループと BizTalk 分離ホスト ユーザー グループなどの BizTalk サービスを実行するアカウントと同じグループのメンバーシップが必要です。  

> [!TIP] 
> 新しいアプリケーション プールを作成する、既定の .NET CLR のバージョン、およびマネージ パイプラインを保持します。 忘れないでください。 BizTalk サービス アカウントと同じ BizTalk グループのメンバーシップを持っているユーザー (詳細設定) を選択します。 

#### <a name="create-the-management-iis-application"></a>管理の IIS アプリケーションを作成します。
この IIS アプリケーションの URL は、BizTalk Server で、データ ゲートウェイを使用してロジック アプリ) の「BizTalk コネクタによって使用します。

1. インターネット インフォメーション サービス (IIS) マネージャーを開きます。
2. 右クリック **既定の Web サイト**, 、および **アプリケーション追加**します。 この新しいアプリケーション。 

    1. 入力、 **エイリアス** (名前)、アプリケーションのなど **IISLogicApp**します。 
    2. **選択** アプリケーション プール。
    3. 設定、**物理パス**に`C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter\Management`です。 
    3. **テストの設定** の id が認証を通過するアプリケーション プールを確認して、承認をテストします。

3. 選択 **OK** して変更を保存します。
4. Web ブラウザーを開きに移動`http://localhost/YourApplicationAlias/schemas?api-version=2016-10-26`など`http://localhost/IISLogicApp/Schemas?api-version=2016-10-26`です。 開く/保存するように求められます、表示するスキーマのリスト、またはする `schemas.json`です。 実際の結果は、web ブラウザーに依存します。 これらはいずれもが発生した場合、BizTalk グループのメンバーシップをアプリケーション プール id にない可能性があります。

#### <a name="create-the-biztalk-receiveservice-iis-application"></a>BizTalk ReceiveService IIS アプリケーションを作成します。
この IIS アプリケーションの URL がロジック アプリ) の「BizTalk コネクタで使用受信場所を選択するとします。 

1. インターネット インフォメーション サービス (IIS) マネージャーを開きます。
2. 右クリック **既定の Web サイト**, 、および **アプリケーション追加**します。 この新しいアプリケーション。 

    1. 入力、 **エイリアス** (名前)、アプリケーションのなど **ReceiveWCFService**します。 
    2. **選択** 以前の IIS アプリケーションとして同じアプリケーション プール。
    3. 設定、**物理パス**に`C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter\ReceiveService`です。 
    3. **テストの設定** の id が認証を通過するアプリケーション プールを確認して、承認をテストします。

3. 選択 **OK** して変更を保存します。


### <a name="step-3-create-a-logic-app"></a>手順 3: ロジック アプリを作成します。

1. [Azure ポータル](https://portal.azure.com), 、新しいロジック アプリを作成します。
2. 追加、 **ときに HTTP 要求を受信した** トリガーします。
3. 追加、 **BizTalk Server では、JSON からメッセージを準備する** アクション。 
4. **省略可能な**: 選択 **内部設置型のデータ ゲートウェイ経由で接続**, を次を入力します。 

    | プロパティ | Description |
   | --- | --- |
    | BizTalk サーバーの URL | IIS アプリケーション URL での BizTalk 管理の完全修飾ドメイン名 (FQDN) を入力します。 たとえば、入力`http://BizTalkServerName.corp.contoso.com/IISLogicApp/`です。 |
    | [認証の種類] | 選択 **Windows**します。 |
   | [ユーザー名] | IIS アプリケーション プールの id を入力します。 |
   | Password | IIS アプリケーション プールのパスワードを入力します。 |
   | ゲートウェイ | 作成したゲートウェイを選択します。 |

    > [!TIP] 
    > データ ゲートウェイは、必要な場合。
    > - 内部設置型 BizTalk Server を使用しています。
    > - BizTalk Server の Azure 仮想マシンを使用している *と* VM は HTTP エンドポイント (URL) として公開されません。

5. **[作成]**を選択します。 
6. アクションを構成します。 **本文**, 、HTTP 本文の出力を選択します。 **スキーマ**, 、使用するスキーマを選択します。 

    > [!NOTE] 
    > この手順では、biztalk のスキーマに関する知識があり、必要なスキーマを知ると仮定します。 確認していない場合は、展開、HelloWorld の SDK サンプル、ロジック アプリのアダプターを使用するには、そのアイテムを更新し、スキーマとサンプルのメッセージを使用します。 

7. 新しい手順を追加し、選択、 **BizTalk Server のメッセージの送信** アクション。 **受信場所の**をドロップダウン リストから URL を選択するか、ReceiveService IIS アプリケーション URL の完全修飾ドメイン名 (FQDN) を入力します。 たとえば、入力 `http://BizTalkServerName.corp.contoso.com/ReceiveWCFService/Service1.svc`します。

    > [!TIP] 
    > この正確な URL として受信場所のトランスポート プロパティにも入力する受信場所を作成するときに、 **パブリック アドレス** ([全般] タブ)。

    **本文**, 、以前のアクションを BizTalk Server から本文出力を選択します。 

8. **保存** 変更します。 

保存すると、HTTP 要求のトリガーは、URL を自動的に作成されます。 この URL をコピーします。必要な **手順 5: メッセージを送信する**です。

### <a name="step-4-create-a-receive-port-and-a-receive-location"></a>手順 4: 受信ポートと受信場所を作成します。

> [!NOTE] 
> 作成する代わりに、独自の受信ポートし、受信場所、HelloWorld SDK サンプルを展開することができます。 Logic Apps アダプターを使用するアイテムを更新します。 
 
このセクションでは、独自の成果物を作成する手順を示します。 

1. BizTalk Server 管理コンソールで  **BizTalk Server 管理コンソール**, 、展開 **BizTalk グループ**, 、展開 **アプリケーション**, 、し、受信場所を実行するアプリケーションを展開します。 たとえば、 **BizTalk アプリケーション 1**します。
2. 右側の選択 **受信ポート**,  **新規**, を選択し、 **一方向の受信ポート**します。
3. 受信ポートのプロパティで、次のように入力します。  

    | プロパティ | 目的 |
    | --- | --- |
    | **名** | 受信ポートの名前を入力します。 たとえば、入力 **LAReceivePort**します。 |
    | **認証** | オプション： <br/><ul><li>認証なし: 既定値です。 認証を無効にします。</li><li>認証が失敗した場合は、メッセージを削除します。 認証されていないメッセージを削除するが、認証を有効にします。</li><li>認証が失敗した場合は、メッセージを保持する: 認証を有効にして、認証されていないメッセージを保持するのには、このオプションをクリックします。 </li></ul>|
    | **失敗したメッセージのルーティングを有効にします。** | サブスクライブしているアプリケーションの処理に失敗したすべてのメッセージのルーティング (別の受信ポートやオーケストレーション スケジュールなど)。 失敗したメッセージを中断し、否定受信確認応答 (NACK) を生成するには、このオプションをオフにします。 既定値はオフです。 詳細については、次を参照してください。[受信ポートの失敗のメッセージのルーティングを有効にする方法](../core/how-to-enable-routing-for-failed-messages-for-a-receive-port.md)です。|

4. 選択 **受信場所**, を選択して **新規**します。 
5. 入力、 **名前** 受信場所のです。 たとえば、入力 **LAReceiveLoc**します。
6. **型**,  **ロジック**  を選択し、一覧から、 **構成 ボタン**します。 
7. **全般**  タブで、ロジック アプリのエンドポイント アドレスを構成します。

    | プロパティ | 目的 |
    | --- | --- |
    | **アドレス (URI)** | 必須。 BizTalk ReceiveService IIS アプリケーション URL の入力 (`/YourIISApp2Name/Service1.svc`)。 たとえば、入力 `/ReceiveWCFService/Service1.svc`します。 |
    | **パブリック アドレス** | 必須。 入力 `http://<your fully qualified machine name>/YourIISApp2Name/Service1.svc`します。 たとえば、入力 `http://btsProd.northamerica.corp.contoso.com/ReceiveWCFService/Service1.svc`します。 <br/><br/>この正確な URL は、受信場所でロジック アプリでも表示されます。|

8. **省略可能な**です。 **バインディング**  タブで、任意のタイムアウトと基になる Wcf-webhttp バインドのエンコーディングに関連するプロパティを構成します。 これらのプロパティは、サイズの大きいメッセージを処理する場合に役立ちます。

    | プロパティ | 目的 |
    | --- | --- |
    | オープン タイムアウト | チャネルのオープン操作を完了する必要がありますがかかる時間間隔を入力します。 この値は、System.TimeSpan.Zero 以上にする必要があります。 <br/><br/>既定値:00:01:00<br/>最大値: 23時 59分: 59 |
    | 送信タイムアウト |送信操作が完了するにかかるはずの時間間隔を入力します。 この値は、System.TimeSpan.Zero 以上にする必要があります。 要求-応答を使用する場合は、受信ポート、クライアントは、サイズの大きいメッセージを返した場合でも、この値が完了するには全体の相互作用の期間を指定します。 <br/><br/>既定値:00:01:00<br/>最大値: 23時 59分: 59|
    | クローズ タイムアウト | チャネルのクローズ操作を完了する必要がありますがかかる時間間隔を入力します。 この値は、System.TimeSpan.Zero 以上にする必要があります。 <br/><br/>既定値:00:01:00<br/>最大値: 23時 59分: 59 |
    | [最大受信メッセージ サイズ (バイト単位)] | ヘッダーを含む、ネットワークで受信されるメッセージのバイト単位の最大サイズを入力します。 メッセージのサイズは、各メッセージに割り当てられたメモリの量がバインドされます。 このプロパティを使用して、サービス拒否 (DoS) 攻撃にさらされる危険性を制限できます。 <br/><br/>既定値:65536<br/>最大値: 2147483647|
    | [最大同時呼び出し数] | 1 つのサービス インスタンスに対する同時呼び出しの数を入力します。 制限を超える呼び出しはキューに格納されます。 この値を 0 に設定することは、Int32.MaxValue に設定すると同じです。 <br/><br/>既定値は 200 です。|

9. **省略可能な**です。 **セキュリティ**  タブで、そのセキュリティ プロパティを設定します。 開発目的で、[なし] を選択できます。

    | プロパティ | 目的 |
    | --- | --- |
    | [セキュリティ モード] | オプション：  <br/><br/><ul><li>None: メッセージ セキュリティの管轄外の転送中にします。</li><li>トランスポート: セキュリティは、HTTPS トランスポートを使用して提供されます。 SOAP メッセージは、HTTPS を使用してセキュリティ保護されます。 このモードを使用するをセキュリティで保護されたソケット レイヤー (SSL) インターネット インフォメーション サービス (IIS) を設定する必要があります。 </li><li>TransportCredentialOnly: 既定値です。 </li></ul> |
    | トランスポート クライアント資格情報の種類 | クライアント認証を使用するには、資格情報の種類を選択します。 オプション：  <br/><br/><ul><li>None: 認証は行われませんトランスポート レベルでします。</li><li>Basic: 基本認証を使用ユーザー名とパスワードをプレーン テキストでネットワーク経由で送信します。 資格情報に対応するドメイン ユーザー アカウントまたはローカル ユーザー アカウントを作成する必要があります。</li><li>パスワードをハッシュ値として、ネットワーク経由で送信 Digest: 使用のダイジェスト認証です。 Windows Server オペレーティング システムの認証を実行するドメイン コント ローラーのドメインでのみ使用できます。 クライアントの資格情報に対応するドメイン ユーザー アカウントまたはローカル ユーザー アカウントを作成する必要があります。</li><li>Ntlm: 既定値です。 クライアントは、受信場所にこのパスワードを送信せずに資格情報を送信します。 クライアントの資格情報に対応するドメイン ユーザー アカウントまたはローカル ユーザー アカウントを作成する必要があります。</li><li>Windows: Windows 統合認証をネゴシエート Kerberos または NTLM、ドメインが存在する場合は、Kerberos を選択します。 Kerberos を使用するのには、クライアントがサービス プリンシパル名 (SPN) で、サービスを識別する必要があります。 クライアントの資格情報に対応するドメイン ユーザー アカウントまたはローカル ユーザー アカウントを作成する必要があります。</li><li>証明書: は、クライアント証明書を使用します。 CA 証明書チェーンの次のように、クライアントが認証できるように、このコンピューターの信頼されたルート証明機関の証明書ストアにクライアントの X.509 証明書をインストールする必要があります場所が表示されます。</li><li>InheritedFromHost</li></ul> |
    | [シングル サインオンを使用する] | |


10. **省略可能な**です。 **メッセージ**  タブで、使用して、 **送信 HTTP ヘッダー** プロパティをカスタム ヘッダーを追加し、エラーを支援する追加のプロパティを使用します。 

    | プロパティ | 目的 |
    | --- | --- |
    |送信 HTTP ヘッダー | 応答メッセージに付加する任意の HTTP ヘッダーを入力します。 | 
    | [エラー発生時に場所を無効にする] | 受信パイプラインまたはルーティングの障害によって受信処理が失敗した場合は、受信場所を無効にします。 既定でオフにできません。|
    | [エラー発生時に要求メッセージを保留する] | 受信パイプラインまたはルーティングの障害によって受信処理が失敗した場合は、要求メッセージを中断します。 既定でオフにできません。|
    | [エラーに例外の詳細を含める] | エラーが発生する場合は、ヘルプのデバッグに何らかの SOAP エラーを返します。 既定でオフにできません。|

[受信場所を管理する](../core/managing-receive-locations.md)追加のプロパティについて説明します。 

### <a name="step-5-send-a-message"></a>手順 5: メッセージを送信します。

1. Fiddler や Postman (または必要に応じて) を開きます。
2. ロジック アプリからの要求のトリガーの URL を貼り付けます。 手順 3 では、この URL をコピーします。 
3. 選択 **POST** HTTP 動詞のセットとして、 **content-type** ヘッダーを `application/json`します。 本文では、次の JSON を貼り付けます。  

    ```json
    {“hello”:”world”}
    ```

4. これは BizTalk に一方向の呼び出しであるため、結果は HTTP 202 をする必要があります。 HelloWorld SDK サンプルを使用している場合は、BizTalk server に移動します。 送信フォルダーにファイルがあります。 


## <a name="send-messages-to-a-logic-app"></a>ロジック アプリにメッセージを送信します。

### <a name="step-1-install-the-logic-apps-adapter"></a>手順 1: Logic Apps アダプターをインストールします。

Logic Apps アダプターでは、個別のダウンロードし、BizTalk Server のインストールに含まれていません。

1. 移動して [Logic Apps 向けの Microsoft BizTalk Server アダプター](https://www.microsoft.com/download/details.aspx?id=54287), 、保存します。 
2. LogicAppAdapter.iso を開き、実行、 **ロジック Adapter.msi** ファイルをインストールします。
3. **[完了]** のインストールと再起動、 **BizTalkServerApplication** と **BizTalkServerIsolatedHost** インスタンスをホストします。

インストールされると、次があります。

- BizTalk 管理コンソールには、ロジックのアダプターを追加してください。
- 送信ハンドラーが作成され、BizTalkServerApplication ホストを使用します。
- 受信ハンドラーは、WCF サービスとして作成され、BizTalkServerIsolatedHost ホストを使用します。
- `C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter`フォルダーが作成され、2 つのサービスが含まれています: 管理と ReceiveService です。 これらのサービスは、メッセージを送信するロジック アプリには使用されません。 


### <a name="step-2-create-a-logic-app"></a>手順 2: ロジック アプリを作成します。

1. [Azure ポータル](https://portal.azure.com), 、新しいロジック アプリを作成します。
2. 追加、 **ときに HTTP 要求を受信した** トリガー
3. 追加、 **Office 365 の Outlook の電子メールを送信** アクション。 **に** アドレス、Office 365 アドレスを入力します。 **サブジェクト**, 、入力 `Sending from BizTalk`します。 **本文**, 、選択、 *本文* からの出力、 **ときに HTTP 要求を受信した** トリガーします。 
4. ロジック アプリのようになります。 

    ![LogicAppExample](../core/media/logicappexample.gif)

5. ロジック アプリで; を保存するときに自動的に作成される HTTP POST URL のコピーします。次の手順では、この URL を必要とします。 URL をロジック アプリを閉じて再度開くことがあります。  


### <a name="step-3-create-a-send-port"></a>手順 3: 送信ポートを作成します。

ロジック アプリにメッセージを送信する BizTalk Server、ロジック アプリがいる必要があります、 **手動** トリガーなど **(Manual) ときに HTTP 要求を受信した**します。 

1. BizTalk Server 管理コンソールで  **BizTalk Server 管理コンソール**, 、展開 **BizTalk グループ**, 、展開 **アプリケーション**, 、し、送信ポートを実行するアプリケーションを展開します。 たとえば、 **BizTalk アプリケーション 1**します。
2. 右側の選択 **送信ポート**,  **新規**, を選択し、 **静的な一方向送信ポート**します。
3. 入力、 **名前** 送信ポートにします。 たとえば、入力 **LASendPort**します。
4. **型**,  **ロジック**  を選択し、一覧から、 **構成**  ボタンをクリックします。 
5. **全般**  タブで、構成、 **コールバック URI** 、ロジック アプリのトリガーのです。 これには 2 つの方法があります。 

    **オプション 1** : の前の手順でコピーした、HTTP POST URL を貼り付け、 **トリガー (コールバック URI)** プロパティです。 次の手順を使用して URI をコピーすることもできます。  
  
      1. [Azure ポータル](https://portal.azure.com), 、Logic Apps デザイナー (編集モード) で、ロジック アプリを開きます。 
      2. 選択、 **ときに HTTP 要求を受信した** カード、およびコピー、 **URL**します。 
      3. 送信ポートをでこの URL を貼り付け、 **トリガー (コールバック URI)** プロパティです。

    > [!TIP] 
    > この URI を取得するのに、管理 Api を使用することもできます。

    **オプション 2** : トリガーのコールバック URI がわからない場合は、選択 **構成**, 、および Azure にサインインします。 次に、ドロップダウン リストを使用して、選択、 **サブスクリプション**, 、**リソース グループ**, 、**ロジック アプリ**, 、および **トリガー**します。
 
6. **省略可能な**です。 **バインディング**  タブで、任意のタイムアウトと基になる Wcf-webhttp バインドのエンコーディングに関連するプロパティを構成します。 これらのプロパティは、サイズの大きいメッセージを処理する場合に役立ちます。

    | プロパティ | 目的 |
    | --- | --- |
    | オープン タイムアウト | チャネルのオープン操作を完了する必要がありますがかかる時間間隔を入力します。 この値は、System.TimeSpan.Zero 以上にする必要があります。 <br/><br/>既定値:00:01:00<br/>最大値: 23時 59分: 59 |
    | 送信タイムアウト |送信操作が完了するにかかるはずの時間間隔を入力します。 この値は、System.TimeSpan.Zero 以上にする必要があります。 要求-応答を使用する場合は、受信ポート、クライアントは、サイズの大きいメッセージを返した場合でも、この値が完了するには全体の相互作用の期間を指定します。 <br/><br/>既定値:00:01:00<br/>最大値: 23時 59分: 59|
    | クローズ タイムアウト | チャネルのクローズ操作を完了する必要がありますがかかる時間間隔を入力します。 この値は、System.TimeSpan.Zero 以上にする必要があります。 <br/><br/>既定値:00:01:00<br/>最大値: 23時 59分: 59 |
    | [最大受信メッセージ サイズ (バイト単位)] | ヘッダーを含む、ネットワークで受信されるメッセージのバイト単位の最大サイズを入力します。 メッセージのサイズは、各メッセージに割り当てられたメモリの量がバインドされます。 このプロパティを使用して、サービス拒否 (DoS) 攻撃にさらされる危険性を制限できます。 <br/><br/>Appa アダプターのロジックを活用、 [WebHttpBinding クラス](https://msdn.microsoft.com/library/system.servicemodel.webhttpbinding.aspx) のバッファリングされた送信モードで、エンドポイントと通信します。 バッファリングされたトランスポート モード用、 [WebHttpBinding.MaxBufferSize](https://msdn.microsoft.com/library/system.servicemodel.webhttpbinding.maxbuffersize.aspx) プロパティは常にこのプロパティの値とします。  <br/><br/>既定値:65536<br/>最大値: 2147483647 |


7. **省略可能な**です。 **メッセージ**  タブで、使用して、 **送信 HTTP ヘッダー** プロパティを送信メッセージにカスタム ヘッダーを追加します。 
8. 選択 **OK** して構成を保存します。 

[送信ポートと送信ポート グループを管理する](../core/managing-send-ports-and-send-port-groups.md)追加の送信ポートのプロパティについて説明します。 

### <a name="step-4-send-some-messages"></a>手順 4: いくつかのメッセージを送信します。

ファイル アダプターを使用して受信場所と受信ポートを作成できます。 ロジック アプリが有効になっていることを確認します。

1. 受信ポートを作成し *FileSendPort*,、
2. 受信場所を作成しのようなプロパティを設定します。  

    | プロパティ | 入力のサンプル |
    | --- | --- |
   | 受信フォルダ | C:\temp\In\ |
   | ファイル マスク | *.txt |
   | パイプライン | PassThruReceive |

3. 作成した送信ポートの設定、 **フィルター** にします。

    | プロパティ | 演算子 | 値 |
    | --- | --- | --- |
    | BTS.ReceivePortName |  == | *FileSendPort* |

4. 次のテキストをテキスト ファイル (ファイル名.txt) を作成します。 サンプル メッセージとして、このテキスト ファイルを使用します。 

    ```
    <Data>
      <DataID>DataID_0</DataID>
      <DataDetails>DataDetails_0</DataDetails>
    </Data>
    ```

5. 受信フォルダーにサンプル メッセージ (ファイル名.txt) をコピーします。 送信ポートは、.txt ファイルを入力した URI を使用してロジック アプリに送信します。 ロジック アプリでは、ファイルを取得します。 Office 365 の Outlook connector を使用した場合、 *に* 電子メール アドレスは、サンプル メッセージで、電子メールを受信する必要があります。

## <a name="next"></a>Next
[Logic Apps とは](https://azure.microsoft.com/documentation/articles/app-service-logic-what-are-logic-apps/)  

[ロジック アプリを作成します。](https://azure.microsoft.com/documentation/articles/app-service-logic-create-a-logic-app/)

[BizTalk Server でアダプターの使用](../core/using-adapters.md)