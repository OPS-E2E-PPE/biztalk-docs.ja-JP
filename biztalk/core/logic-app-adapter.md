---
title: BizTalk Server で使用してロジック アプリ アダプター |Microsoft Docs
description: 受信ポートを作成、受信場所、および BizTalk server 送信ポートを Logic Apps アダプター インストールし、構成
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
ms.openlocfilehash: e13756fb6310b73f8e7fb88c336bdf2a7bbc1372
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972827"
---
# <a name="logic-app-adapter"></a>ロジック アプリのアダプター

## <a name="overview"></a>概要
BizTalk Server では、Azure ロジック アプリからメッセージを受信または Azure ロジック アプリにメッセージを送信する Logic Apps アダプターを使用します。 

Azure では、ロジック アプリを作成します。 このロジック アプリでは、BizTalk コネクタを使用して、BizTalk Server で作成した受信場所に接続します。 このトピックでは、Azure Logic Apps の知識があると仮定します。 かどうかは、ロジック アプリを初めてしたら、お勧め[詳細については、学習](https://azure.microsoft.com/documentation/articles/app-service-logic-what-are-logic-apps/)、さらに[ロジック アプリの作成](https://azure.microsoft.com/documentation/articles/app-service-logic-create-a-logic-app/)です。

このトピックでは、ロジック アプリから BizTalk Server でメッセージを受信する手順を示します。 別の言い方を行うには、ロジック アプリは、BizTalk Server にメッセージを送信します。 受信側では、Azure サービスとの通信を処理するために、IIS でアプリケーションを使用します。 BizTalk Server が、オンプレミスの場合は、また、BizTalk Server にデータ ゲートウェイをインストールして Azure でゲートウェイを作成します。 

BizTalk Server が Azure の仮想マシン (VM) にインストールされているかどうかは、HTTP エンドポイント (URL を取得) として、VM を公開することができますか、HTTP エンドポイントとして公開しません。 公開する場合は、ゲートウェイを使用する必要はありません。 BizTalk コネクタでロジック アプリで、URL を入力できます。 VM (URL) を公開しない場合は、ゲートウェイを使用する必要があります。 次の手順は、このトピックに表示されます。

紹介する Azure ロジック アプリに、BizTalk Server からメッセージを送信する方法。 別の言い方を行うには、ロジック アプリは、BizTalk Server からメッセージを受信します。 送信側は、非常に単純ですが、ここに表示されます。

受信場所と Logic Apps アダプターを使用して送信ポートを作成するのにには、このトピックを使用します。 LogicApp アダプターは、オンプレミス (ドメインに参加) BizTalk Server では、または BizTalk Server を実行する Azure 仮想マシンを使用することができます。 

## <a name="requirements"></a>要件

- Azure portal にサインインし、ロジック アプリを作成する Azure サブスクリプション。
- 任意。 インストール、HTTP テスト ツールなどに、ロジック アプリをテスト メッセージを送信する[Fiddler](http://www.telerik.com/fiddler)または[Postman](https://www.getpostman.com/)します。 ロジック アプリにメッセージを送信する別のメソッドを使用する場合は、これらのツールを使用する必要はありません。 

## <a name="receive-messages-from-a-logic-app"></a>ロジック アプリからメッセージを受信します。

ロジック アプリからのメッセージを受信する BizTalk Server には、いくつかの手順があります。 このセクションでは、次の手順を示します。 Azure の変更、手順の一部のユーザー インターフェイスが表示されているとおりにならないことができます。 

#### <a name="prerequisites"></a>前提条件

- BizTalk Server が、オンプレミスの場合は、インストールし、構成、 [、オンプレミス データ ゲートウェイ](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-install/)Logic Apps の。 その後、Azure では、[データ ゲートウェイ リソースを作成](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-connection/)BizTalk Server に接続します。
- BizTalk Server が、Azure VM にインストールされている VM は、HTTP エンドポイントとして公開されない場合は、インストールし、構成、 [、オンプレミス データ ゲートウェイ](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-install/)Logic Apps の。 その後、Azure では、[データ ゲートウェイ リソースを作成](https://azure.microsoft.com/documentation/articles/app-service-logic-gateway-connection/)BizTalk Server に接続します。
- BizTalk Server が、Azure VM にインストールされている VM が HTTP エンドポイントとして公開されている場合は、ゲートウェイがないために必要なまたは使用。 

### <a name="step-1-install-the-logic-app-adapter"></a>手順 1: ロジック アプリのアダプターをインストールします。

ロジック アプリのアダプターは個別のダウンロードし、は BizTalk Server のインストールに含まれません。 

> [!IMPORTANT] 
> LogicAppAdapter.iso をダウンロードするには。
> 
> 1. 移動して[Logic Apps の Microsoft BizTalk Server アダプター](https://www.microsoft.com/download/details.aspx?id=54287)、保存します。 
> 2. LogicAppAdapter.iso を開き、実行、 **LogicApp Adapter.msi**ファイルをインストールします。

1. BizTalk Server をダウンロードして、ロジック アプリのアダプターをインストールします。 

2. 二重選択**LogicApp Adapter.msi**をインストールします。 ライセンス条項に同意し、**インストール**します。
3. **[完了]** 、インストール、d の再起動、 **BizTalkServerApplication**と**BizTalkServerIsolatedHost**インスタンスをホストします。

インストールされると、次があります。

- ロジック アプリのアダプターは、BizTalk 管理コンソールに追加されます。
- 送信ハンドラーが作成され、BizTalkServerApplication ホストを使用します。
- 受信ハンドラーは、WCF サービスとして作成され、[biztalkserverisolatedhost] ホストを使用します。
- `C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter`フォルダーが作成され、2 つのサービスが含まれています: 管理および ReceiveService します。 

    **管理**data gateway を使用して BizTalk Server に接続するロジック アプリで BizTalk コネクタによって使用されます。 この管理サービスでは、データ ゲートウェイを使用して Azure ロジック アプリからのメッセージを受信する BizTalk Server を使用します。 このサービスは、BizTalk の受信側でのみ使用されます。 送信側では使用されません。

    **ReceiveService**受信場所を入力すると、ロジック アプリで BizTalk コネクタによって使用されます。 **ReceiveService**はロジック アプリからメッセージを送信する責任を負います。 このサービスは、BizTalk の受信側でのみ使用されます。 送信側では使用されません。


### <a name="step-2-create-the-iis-applications"></a>手順 2: IIS のアプリケーションを作成します。

IIS アプリケーションは、管理と ReceiveService サービスを使用します。

新しいアプリケーション プール、または既存のアプリケーション プールを使用して IIS アプリケーションを実行することができます。 AppPool の id には、BizTalk Application Users および BizTalk 分離ホスト ユーザー グループなど、BizTalk services を実行するアカウントと同じグループのメンバーシップが必要です。  

> [!TIP] 
> 新しいアプリケーション プールを作成する場合は、既定の .NET CLR バージョンおよびマネージ パイプラインを保持します。 忘れないでください。 BizTalk サービス アカウントと同じ BizTalk グループのメンバーシップを持っているユーザー (詳細設定) を選択します。 

#### <a name="create-the-management-iis-application"></a>IIS の管理アプリケーションを作成します。
この IIS アプリケーションの URL は、BizTalk Server のデータ ゲートウェイを使用するロジック アプリ) の「BizTalk コネクタによって使用されます。

1. インターネット インフォメーション サービス (IIS) マネージャーを開きます。
2. 右クリック**Default Web Site**、および**アプリケーションを追加**します。 この新しいアプリケーション。 

    1. 入力、**エイリアス**(名前)、アプリケーションのなど**IISLogicApp**します。 
    2. **選択**アプリケーション プール。
    3. 設定、**物理パス**に`C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter\Management`します。 
    3. **テストの設定**の id が認証を通過するアプリケーション プールを確認して、承認をテストします。

3. **[OK]** を選択して変更を保存します。
4. Web ブラウザーを開きに移動`http://localhost/YourApplicationAlias/schemas?api-version=2016-10-26`など`http://localhost/IISLogicApp/Schemas?api-version=2016-10-26`します。 いずれかのスキーマの表示の一覧またはするは、開く/保存するように求められます`schemas.json`します。 実際の結果は、web ブラウザーに依存します。 どちらのような場合は、アプリケーション プール id は、BizTalk グループのメンバーシップをない可能性があります。

#### <a name="create-the-biztalk-receiveservice-iis-application"></a>BizTalk ReceiveService IIS アプリケーションを作成します。
この IIS アプリケーションの URL は、ロジック アプリ) の「BizTalk コネクタで使用、受信場所を選択するとします。 

1. インターネット インフォメーション サービス (IIS) マネージャーを開きます。
2. 右クリック**Default Web Site**、および**アプリケーションを追加**します。 この新しいアプリケーション。 

    1. 入力、**エイリアス**(名前)、アプリケーションのなど**ReceiveWCFService**します。 
    2. **選択**以前の IIS アプリケーションとして同じアプリケーション プール。
    3. 設定、**物理パス**に`C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter\ReceiveService`します。 
    3. **テストの設定**の id が認証を通過するアプリケーション プールを確認して、承認をテストします。

3. **[OK]** を選択して変更を保存します。


### <a name="step-3-create-a-logic-app"></a>手順 3: ロジック アプリを作成します。

1. [Azure portal](https://portal.azure.com)、新しいロジック アプリを作成します。
2. 追加、**ときに HTTP 要求を受信した**トリガーします。
3. 追加、 **BizTalk Server に JSON からメッセージを準備**アクション。 
4. **省略可能な**: 選択**のオンプレミス データ ゲートウェイ経由で接続**、」と入力します。 

    | プロパティ | 説明 |
   | --- | --- |
    | BizTalk Server の URL | IIS アプリケーションの URL での BizTalk 管理の完全修飾ドメイン名 (FQDN) を入力します。 たとえば、入力`http://BizTalkServerName.corp.contoso.com/IISLogicApp/`します。 |
    | [認証の種類] | 選択**Windows**します。 |
   | Username | IIS アプリケーション プールの id を入力します。 |
   | パスワード | IIS アプリケーション プールのパスワードを入力します。 |
   | ゲートウェイ | 作成したゲートウェイを選択します。 |

    > [!TIP] 
    > ただし、データ ゲートウェイはのみ場合は必須です。
    > - オンプレミスの BizTalk Server を使用しています。
    > - BizTalk Server の Azure 仮想マシンを使用して*と*VM は、HTTP エンドポイント (URL) として公開されません。

5. **[作成]** を選択します。 
6. アクションを構成します。 **本文**、HTTP 本文出力を選択します。 **スキーマ**、使用するスキーマを選択します。 

    > [!NOTE] 
    > この手順では、BizTalk のスキーマに精通してするどのスキーマを把握前提としています。 確認していない場合は、HelloWorld SDK サンプルのデプロイ、ロジック アプリのアダプターを使用するには、そのアイテムを更新し、スキーマとサンプルのメッセージを使用します。 

7. 新しいステップを追加し、選択、 **BizTalk Server のメッセージの送信**アクション。 **受信場所**、ドロップダウン リストから URL を選択するか、ReceiveService IIS アプリケーション URL の完全修飾ドメイン名 (FQDN) を入力します。 たとえば、入力`http://BizTalkServerName.corp.contoso.com/ReceiveWCFService/Service1.svc`します。

    > [!TIP] 
    > この正確な URL は受信場所のトランスポート プロパティとして入力することも、受信場所を作成するときに、**パブリック アドレス**([全般] タブ)。

    **本文**、BizTalk Server の前のアクションから本文出力を選択します。 

8. **保存**変更します。 

保存すると、HTTP 要求トリガー URL を自動的に作成します。 この URL をコピーします。必要な**手順 5: メッセージを送信する**します。

### <a name="step-4-create-a-receive-port-and-a-receive-location"></a>手順 4: 受信ポートと受信場所を作成します。

> [!NOTE] 
> 作成する代わりに、独自の受信ポートし、受信場所は、HelloWorld SDK サンプルを展開できます。 Logic Apps アダプターを使用するアイテムを更新します。 
 
このセクションでは、独自のアーティファクトを作成する手順を示します。 

1. BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開アプリケーション受信場所を実行します。 たとえば、 **BizTalk アプリケーション 1**します。
2. 右クリック**受信ポート**を選択します**新規**、選び**一方向の受信ポート**します。
3. 受信ポートのプロパティで、次のように入力します。  

    | プロパティ | 目的 |
    | --- | --- |
    | **名前** | 受信ポートの名前を入力します。 たとえば、入力**LAReceivePort**します。 |
    | **[認証]** | オプション： <br/><ul><li>認証なし: 既定値です。 認証を無効にします。</li><li>認証が失敗した場合は、メッセージを削除します。 認証されていないメッセージを削除するが、認証を有効します。</li><li>認証が失敗した場合は、メッセージを保持します。 認証を有効にすると、認証されていないメッセージを保持するには、このオプションをクリックします。 </li></ul>|
    | **失敗したメッセージのルーティングを有効にします。** | サブスクライブするアプリケーションの処理に失敗したすべてのメッセージのルーティング (別の受信ポートやオーケストレーション スケジュールなど)。 失敗したメッセージを中断し、否定受信確認応答 (NACK) を生成するには、このオプションをオフにします。 既定値はオフです。 詳細については、次を参照してください。[受信ポートの失敗したメッセージのルーティングを有効にする方法](../core/how-to-enable-routing-for-failed-messages-for-a-receive-port.md)します。|

4. 選択**受信場所**、選び**新規**します。 
5. 入力、**名前**受信場所の。 たとえば、入力**LAReceiveLoc**します。
6. **型**を選択します**LogicApp**を選択し、一覧から、**構成ボタン**します。 
7. **全般** タブで、ロジック アプリのエンドポイント アドレスを構成します。

    | プロパティ | 目的 |
    | --- | --- |
    | **アドレス (URI)** | 必須。 BizTalk ReceiveService IIS アプリケーションの URL を入力します (`/YourIISApp2Name/Service1.svc`)。 たとえば、入力`/ReceiveWCFService/Service1.svc`します。 |
    | **パブリック アドレス** | 必須。 入力`http://<your fully qualified machine name>/YourIISApp2Name/Service1.svc`します。 たとえば、入力`http://btsProd.northamerica.corp.contoso.com/ReceiveWCFService/Service1.svc`します。 <br/><br/>この正確な URL は、受信場所でロジック アプリにも表示されます。|

8. **省略可能な**します。 **バインド** タブで、タイムアウトとエンコーディング関係のプロパティを基になる Wcf-webhttp バインディングの構成します。 これらのプロパティは、サイズの大きいメッセージを処理するときに役立ちます。

    | プロパティ | 目的 |
    | --- | --- |
    | オープン タイムアウト | チャネルを開く操作を完了する必要がありますかかる時間間隔を入力します。 この値は、System.TimeSpan.Zero 以上になります。 <br/><br/>既定値:00:01:00<br/>最大値: 23時 59分: 59 |
    | 送信タイムアウト |送信操作を完了する必要がありますかかる時間間隔を入力します。 この値は、System.TimeSpan.Zero 以上になります。 要求-応答を使用する場合は、受信ポート、クライアントは、サイズの大きいメッセージを返した場合であっても、この値が全体の操作を完了するまでの時間を指定します。 <br/><br/>既定値:00:01:00<br/>最大値: 23時 59分: 59|
    | クローズ タイムアウト | チャネルを閉じる操作を完了する必要がありますかかる時間間隔を入力します。 この値は、System.TimeSpan.Zero 以上になります。 <br/><br/>既定値:00:01:00<br/>最大値: 23時 59分: 59 |
    | [最大受信メッセージ サイズ (バイト単位)] | ヘッダーを含む、ネットワーク上で受信するメッセージをバイト単位で最大のサイズを入力します。 メッセージのサイズは、各メッセージに割り当てられたメモリの量によってバインドされています。 このプロパティを使用して、サービス拒否 (DoS) 攻撃にさらされる危険性を制限できます。 <br/><br/>既定値:65536<br/>最大値: 2147483647|
    | [最大同時呼び出し数] | 1 つのサービス インスタンスに対する同時呼び出しの数を入力します。 制限を超える呼び出しはキューに格納されます。 この値を 0 に設定することは、Int32.MaxValue に設定するのと同じです。 <br/><br/>既定値は 200 です。|

9. **省略可能な**します。 **セキュリティ** タブで、任意のセキュリティ プロパティを構成します。 開発目的で、[なし] を選択できます。

    | プロパティ | 目的 |
    | --- | --- |
    | [セキュリティ モード] | オプション：  <br/><br/><ul><li>None: メッセージ セキュリティの管轄外の転送中にします。</li><li>トランスポート: セキュリティは、HTTPS トランスポートを使用して提供します。 SOAP メッセージは、HTTPS を使用してセキュリティ保護されます。 このモードを使用するをセキュリティで保護されたソケット レイヤー (SSL) では、インターネット インフォメーション サービス (IIS) を設定する必要があります。 </li><li>TransportCredentialOnly: 既定値します。 </li></ul> |
    | トランスポート クライアントの資格情報の種類 | クライアント認証を使用する場合は、資格情報の種類を選択します。 オプション：  <br/><br/><ul><li>None: 認証は行われません、トランスポート レベルでします。</li><li>Basic の場合: 使用して基本認証ユーザー名とパスワードをプレーン テキストでネットワーク経由で送信するには 資格情報に対応するドメイン ユーザー アカウントまたはローカル ユーザー アカウントを作成する必要があります。</li><li>ハッシュ値として、ネットワーク経由でパスワードを送信するダイジェスト: はダイジェスト認証です。 Windows Server オペレーティング システムの認証を実行するドメイン コント ローラーのドメインに対してのみ使用できます。 クライアントの資格情報に対応するドメイン ユーザー アカウントまたはローカル ユーザー アカウントを作成する必要があります。</li><li>Ntlm: 既定値します。 クライアントは、受信場所にこのパスワードを送信せずに資格情報を送信します。 クライアントの資格情報に対応するドメイン ユーザー アカウントまたはローカル ユーザー アカウントを作成する必要があります。</li><li>Windows: Windows 統合認証はネゴシエート Kerberos または NTLM、Kerberos をドメインが存在する場合よりも優先されます。 Kerberos を使用するには、クライアントがサービス プリンシパル名 (SPN) でサービスを識別する必要があります。 クライアントの資格情報に対応するドメイン ユーザー アカウントまたはローカル ユーザー アカウントを作成する必要があります。</li><li>証明書: クライアント証明書を使用します。 CA の証明書チェーンがこのクライアントを認証できるように、このコンピューターの信頼されたルート証明機関の証明書ストアにクライアントの X.509 証明書をインストールする必要がありますの受信場所。</li><li>InheritedFromHost</li></ul> |
    | [シングル サインオンを使用する] | |


10. **省略可能な**します。 **メッセージ** タブで、使用、**送信 HTTP ヘッダー**プロパティをカスタム ヘッダーを追加しに障害が発生する追加のプロパティを使用します。 

    | プロパティ | 目的 |
    | --- | --- |
    |送信 HTTP ヘッダー | 応答メッセージにスタンプする任意の HTTP ヘッダーを入力します。 | 
    | [エラー発生時に場所を無効にする] | 受信パイプラインまたはルーティングの障害によって受信処理が失敗した場合は、受信場所を無効にします。 既定値はチェックされません。|
    | [エラー発生時に要求メッセージを保留する] | 受信パイプラインまたはルーティングの障害によって受信処理が失敗した場合は、要求メッセージを中断します。 既定値はチェックされません。|
    | [エラーに例外の詳細を含める] | エラーが発生する場合は、デバッグを支援する SOAP エラーを返します。 既定値はチェックされません。|

[受信場所を管理する](../core/managing-receive-locations.md)追加のプロパティについて説明します。 

### <a name="step-5-send-a-message"></a>手順 5: メッセージを送信します。

1. Fiddler または Postman (またはに応じて) を開きます。
2. ロジック アプリからの要求トリガーの URL を貼り付けます。 手順 3 では、この URL をコピーします。 
3. 選択**POST** HTTP 動詞、およびセットとして、 **content-type**ヘッダーを`application/json`します。 本文には、次の JSON を貼り付けます。  

    ```json
    {“hello”:”world”}
    ```

4. BizTalk に一方向の呼び出しであるため、結果は、HTTP 202 になります。 HelloWorld SDK サンプルを使用している場合は、BizTalk server に移動します。 送信フォルダーにファイルが可能性があります。 


## <a name="send-messages-to-a-logic-app"></a>ロジック アプリにメッセージを送信します。

### <a name="step-1-install-the-logic-apps-adapter"></a>手順 1: Logic Apps アダプターをインストールします。

Logic Apps アダプターでは、個別のダウンロードしは、BizTalk Server のインストールに含まれていません。

1. 移動して[Logic Apps の Microsoft BizTalk Server アダプター](https://www.microsoft.com/download/details.aspx?id=54287)、保存します。 
2. LogicAppAdapter.iso を開き、実行、 **LogicApp Adapter.msi**ファイルをインストールします。
3. **[完了]** インストール、および再起動、 **BizTalkServerApplication**と**BizTalkServerIsolatedHost**インスタンスをホストします。

インストールされると、次があります。

- ロジック アプリのアダプターは BizTalk 管理コンソールに追加されます。
- 送信ハンドラーが作成され、BizTalkServerApplication ホストを使用します。
- 受信ハンドラーは、WCF サービスとして作成され、[biztalkserverisolatedhost] ホストを使用します。
- `C:\Program Files (x86)\Microsoft BizTalk Server 2016\LogicApp Adapter`フォルダーが作成され、2 つのサービスが含まれています: 管理および ReceiveService します。 これらのサービスは、メッセージを送信するロジック アプリには使用されません。 


### <a name="step-2-create-a-logic-app"></a>手順 2: ロジック アプリを作成します。

1. [Azure portal](https://portal.azure.com)、新しいロジック アプリを作成します。
2. 追加、**ときに HTTP 要求を受信した**トリガー
3. 追加、 **Office 365 Outlook - 電子メールの送信**アクション。 **に**アドレス、Office 365 のアドレスを入力します。 **サブジェクト**、入力`Sending from BizTalk`します。 **本文**、選択、*本文*からの出力、**ときに HTTP 要求を受信した**トリガーします。 
4. ロジック アプリは次のようになります。 

    ![LogicAppExample](../core/media/logicappexample.gif)

5. ロジック アプリを保存するときに自動的に作成される HTTP POST の URL をコピーします。次の手順では、この URL をする必要があります。 URL を表示するロジック アプリを閉じて再度開くことがあります。  


### <a name="step-3-create-a-send-port"></a>手順 3: 送信ポートを作成します。

ロジック アプリへのメッセージを送信する BizTalk Server、ロジック アプリがいる必要があります、**手動**トリガーなど、**手動 - ときに HTTP 要求を受信した**します。 

1. BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開アプリケーション送信ポートを実行します。 たとえば、 **BizTalk アプリケーション 1**します。
2. 右クリック**送信ポート**を選択します**新規**、選び**静的な一方向送信ポート**します。
3. 入力、**名前**送信ポート。 たとえば、入力**LASendPort**します。
4. **型**を選択します**LogicApp**を選択し、一覧から、**構成**ボタンをクリックします。 
5. **全般** タブで、構成、**のコールバック URI**のロジック アプリ トリガー。 これには 2 つの方法があります。 

    **オプション 1** : 前の手順でコピーした、HTTP POST の URL を貼り付け、**トリガー (コールバック URI)** プロパティ。 次の手順を使用して URI をコピーすることもできます。  
  
   1. [Azure portal](https://portal.azure.com)、Logic Apps デザイナー (編集モード) でロジック アプリを開きます。 
   2. 選択、**ときに HTTP 要求を受信した**カード、およびコピー、 **URL**します。 
   3. この URL を貼り付け、送信ポートで、**トリガー (コールバック URI)** プロパティ。

      > [!TIP] 
      > この URI を取得するのに、管理 Api を使用することもできます。

      **オプション 2** : トリガーのコールバック URI がわからない場合は、選択**構成**、し、Azure にサインインします。 次に、ドロップダウン リストを使用して、選択、**サブスクリプション**、**リソース グループ**、**ロジック アプリ**、および**トリガー**します。
 
6. **省略可能な**します。 **バインド** タブで、タイムアウトとエンコーディング関係のプロパティを基になる Wcf-webhttp バインディングの構成します。 これらのプロパティは、サイズの大きいメッセージを処理するときに役立ちます。

    | プロパティ | 目的 |
    | --- | --- |
    | オープン タイムアウト | チャネルを開く操作を完了する必要がありますかかる時間間隔を入力します。 この値は、System.TimeSpan.Zero 以上になります。 <br/><br/>既定値:00:01:00<br/>最大値: 23時 59分: 59 |
    | 送信タイムアウト |送信操作を完了する必要がありますかかる時間間隔を入力します。 この値は、System.TimeSpan.Zero 以上になります。 要求-応答を使用する場合は、受信ポート、クライアントは、サイズの大きいメッセージを返した場合であっても、この値が全体の操作を完了するまでの時間を指定します。 <br/><br/>既定値:00:01:00<br/>最大値: 23時 59分: 59|
    | クローズ タイムアウト | チャネルを閉じる操作を完了する必要がありますかかる時間間隔を入力します。 この値は、System.TimeSpan.Zero 以上になります。 <br/><br/>既定値:00:01:00<br/>最大値: 23時 59分: 59 |
    | [最大受信メッセージ サイズ (バイト単位)] | ヘッダーを含む、ネットワーク上で受信するメッセージをバイト単位で最大のサイズを入力します。 メッセージのサイズは、各メッセージに割り当てられたメモリの量によってバインドされています。 このプロパティを使用して、サービス拒否 (DoS) 攻撃にさらされる危険性を制限できます。 <br/><br/>ロジック appa アダプター活用して、 [WebHttpBinding クラス](https://msdn.microsoft.com/library/system.servicemodel.webhttpbinding.aspx)エンドポイントとの通信に、バッファリングされた送信モードでします。 バッファリングされたトランスポート モードの場合、 [WebHttpBinding.MaxBufferSize](https://msdn.microsoft.com/library/system.servicemodel.webhttpbinding.maxbuffersize.aspx)プロパティは常にこのプロパティの値を等しくします。  <br/><br/>既定値:65536<br/>最大値: 2147483647 |


7. **省略可能な**します。 **メッセージ** タブで、使用、**送信 HTTP ヘッダー**プロパティを送信メッセージにカスタム ヘッダーを追加します。 
8. 選択**OK**構成を保存します。 

[送信ポートと送信ポート グループを管理する](../core/managing-send-ports-and-send-port-groups.md)追加の送信ポートのプロパティについて説明します。 

### <a name="step-4-send-some-messages"></a>手順 4: 一部のメッセージを送信します。

受信ポートと受信場所がファイル アダプターを使用して作成できます。 ロジック アプリが有効になっていることを確認します。

1. 受信ポートを作成します*FileSendPort*、。
2. 受信場所を作成しのようなプロパティを設定します。  

    | プロパティ | 入力のサンプル |
    | --- | --- |
   | 受信フォルダ | C:\temp\In\ |
   | ファイル マスク | *.txt |
   | パイプライン | PassThruReceive |

3. 作成した送信ポートの設定、**フィルター**に。

    | プロパティ | 演算子 | 値 |
    | --- | --- | --- |
    | BTS.ReceivePortName |  == | *FileSendPort* |

4. 次のテキストをテキスト ファイル (ファイル名.txt) を作成します。 サンプル メッセージとしてこのテキスト ファイルを使用します。 

    ```
    <Data>
      <DataID>DataID_0</DataID>
      <DataDetails>DataDetails_0</DataDetails>
    </Data>
    ```

5. 受信フォルダーにサンプル メッセージ (ファイル名.txt) をコピーします。 送信ポートは、.txt ファイルを入力した URI を使用してロジック アプリに送信します。 ロジック アプリでは、ファイルを取得します。 Office 365 Outlook コネクタを使用している場合、*に*電子メール アドレスは、サンプル メッセージで、電子メールを受信する必要があります。

## <a name="next"></a>Next
[Logic Apps とは](https://azure.microsoft.com/documentation/articles/app-service-logic-what-are-logic-apps/)  

[ロジック アプリを作成します。](https://azure.microsoft.com/documentation/articles/app-service-logic-create-a-logic-app/)

[BizTalk Server でのアダプターの使用](../core/using-adapters.md)