---
title: 受信アダプター、WCF を使用した WCF サービス公開する場合の考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- publishing, WCF services
- WCF adapters, best practices
- WCF adapters, receive adapters
- WCF services, publishing
- best practices, WCF adapters
ms.assetid: 797b7ffd-534c-4f09-9738-fb17b208bc96
caps.latest.revision: 34
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa7a36d9e38463ea9be43b6be1520d7b6732ef5e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354702"
---
# <a name="considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters"></a>WCF 受信アダプターで WCF サービスを公開する場合の考慮事項
このトピックでは、WCF 受信アダプターで WCF サービスを公開する際に考慮する必要がある情報を示します。  WCF アダプターを使用してサービスを公開すると、サービスを標準の WCF サービスのように WCF クライアントから呼び出すことができます。  
  
## <a name="in-process-hosting"></a>インプロセス ホスト  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロセス空間 btsntsvc.exe 内で受信場所をホストすると、開発および展開が簡素化されるという利点があります。 また、IIS でホストするよりも多くのホスト インスタンスが作成されて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の高可用性機能と負荷分散機能を利用できます。  外部でホストでは、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] IIS のプロセスを参照してください[IIS 分離 WCF 受信アダプタを構成する](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)します。  
  
## <a name="set-the-isoneway-property-of-wcf-services-published-with-the-wcf-adapters-except-for-the-wcf-netmsmq-receive-adapter-to-false"></a>WCF アダプター (WCF-NetMsmq 受信アダプター以外) によって公開された WCF サービスの IsOneWay プロパティを false に設定する  
 **System.ServiceModel.OperationContractAttribute.IsOneWay** WCF アダプターで公開した WCF サービスのプロパティ-Wcf-netmsmq によって公開されたサービスを除く受信アダプターに設定されている**は true。** — に設定されている**false**一方向の受信場所に対してもします。 場合、 **IsOneWay**プロパティに設定されて**false**を返すメソッドであっても、 **void**応答メッセージで発生します。 この場合、インフラストラクチャにより、メソッドが返した呼び出し元に示す空のメッセージが作成および送信されます。 この方法により、インフラストラクチャはサービス操作によってスローされた例外をクライアントに返すことができます。  
  
 これで WCF アダプター (Wcf-netmsmq 受信アダプター) 以外で公開された WCF サービスを使用する**IsOneWay**は**false**、 **IsOneWay**プロパティをクライアント側に設定する必要があります**false**次のようにします。  
  
```  
[ServiceContract(Namespace="Microsoft.WCF.Documentation")]  
  public interface ISampleService{  
    [OperationContract(IsOneWay=false, ReplyAction="*",Action="…"]  
    string SampleMethod(string msg);  
}  
```  
  
> [!NOTE]
>  の既定値、 **IsOneWay**プロパティは**false**コードでプロパティを指定する必要はありません。  
  
## <a name="the-replyaction-property-of-the-operationcontractattribute-on-the-client-side-should-be-set-to--an-asterisk-when-consuming-wcf-services-published-with-one-way-receive-locations"></a>一方向の受信場所で公開される WCF サービスを使用する場合、クライアント側の OperationContractAttribute の ReplyAction プロパティを "*" (アスタリスク) に設定する必要がある  
 **System.ServiceModel.OperationContractAttribute.ReplyAction**のプロパティ、 **System.ServiceModel.OperationContractAttribute**の値を指定するクライアント側で使用できます、WCF サービスから応答メッセージの SOAP アクション。  
  
 応答メッセージのアクション ヘッダーに特定の値を指定する (クライアントにこれが応答であることと、実行するアクションを伝えるため) 以外に、文字列 "*" (アスタリスク) を指定することもできます。 クライアント アプリケーションでアスタリスクを指定することで、サービスが送信する応答メッセージの応答アクションを検証しないようにクライアントに指示します。  
  
 WCF を使用する一方向によって発行されるサービスの受信場所は、プロキシのメソッド、WCF サービスが返す必要があります**void**、その場合、プロキシのメソッドでは、WCF サービスが、呼び出し元に示すために空のメッセージを送信することが必要ですがメソッドが返されます。 この空のメッセージを受信するプロキシ メソッドの**ReplyAction**のプロパティ、 **OperationContractAttribute**に設定する必要があります"*"(アスタリスク) 次のようにします。  
  
```  
[ServiceContract(Namespace="Microsoft.WCF.Documentation")]  
  public interface ISampleService{  
    [OperationContract(IsOneWay=false, ReplyAction="*",Action="…"]  
    string SampleMethod(string msg);  
}  
```  
  
> [!NOTE]
>  設定する必要はありません、 **ReplyAction**プロパティを"\*"(アスタリスク)、Wcf-netmsmq アダプターの場合、Wcf-netmsmq アダプターが WCF クライアントを設定する必要があるため、 **IsOneWay**プロパティを**true**します。  
  
## <a name="an-isolated-host-instance-can-run-only-one-adapter"></a>分離ホスト インスタンスは 1 つのアダプターでのみ実行できる  
 分離ホスト インスタンスは、1 つのアダプターでのみ実行できます。 1 つの分離ホストで HTTP、SOAP、WCF などの複数の分離アダプターの受信ハンドラーを構成する場合、複数のアプリケーション プール (各アダプターに 1 つのアプリケーション プール) を作成する必要があります。 BizTalk 分離ホストの詳細については、次を参照してください。 [Web サービスを有効にする](../core/enabling-web-services.md)します。  
  
## <a name="use-the-template----content-specified-by-template-option-when-sending-non-xml-content-as-response-messages"></a>XML 以外のコンテンツを応答メッセージとして送信する場合は、[テンプレート -- テンプレートで指定されたコンテンツ] オプションを使用する  
 WCF アダプターで**ボディ--BizTalk 応答メッセージ本文**(既定値) オプションは文字データやビットマップ イメージなどの XML 以外のメッセージの送信を許可していません。 使用することができます、**テンプレート--テンプレートで指定されたコンテンツ**XML 以外のメッセージを送信する WCF アダプターのオプション。 テンプレートを使用する方法の詳細については、次を参照してください。 [WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)します。  
  
## <a name="setting-up-the-permissions-for-a-wcf-service-published-with-the-wcf-service-publishing-wizard"></a>WCF サービス公開ウィザードで公開した WCF サービスに対してアクセス許可を設定する  
 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] または [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] プラットフォームの WCF サービス公開ウィザードを使用して作成された ASP.NET アプリケーションを使用する場合、WCF サービスの呼び出し時に DLL へのアクセスに関連するエラーが発生する可能性があります。 通常、これらのエラーは、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] および [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] の既定のセキュリティの問題に関連しています。 これらのエラーの詳細については、Microsoft ヘルプとサポート資料という、"System.IO.FileNotFoundException"エラー時に、クライアント アプリケーションの呼び出しを Web サービス"のヘルプとサポート Web サイトで参照してください[ http://go.microsoft.com/fwlink/?LinkId=43659](http://go.microsoft.com/fwlink/?LinkId=43659).  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、インプロセス ホストと分離ホストのどちらがサービスを実行するかに関係なく、WCF サービスを実行するプロセスに適切なアクセス許可が付与されることが必要です。 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] および [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] では、分離ホストの既定の Windows グループは分離ホスト ユーザー グループであるため、分離ホスト ユーザー グループにアクセス許可を追加することで、この問題を解決します。  
  
#### <a name="to-add-the-permissions-to-the-isolated-host-users-group"></a>分離ホスト ユーザー グループにアクセス許可を追加するには  
  
1.  Microsoft Windows エクスプローラーで、%windir%\temp ディレクトリを探します。  
  
2.  Windir%\temp を右クリックし、をクリックし、**プロパティ**します。  
  
3.  **プロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。  
  
4.  をクリックして**追加**を選択します**分離ホスト ユーザー グループ**、順にクリックします**OK**します。  
  
## <a name="setting-up-the-permissions-for-a-wcf-receive-location-with-the-wcf-netmsmq-adapter"></a>Wcf-netmsmq アダプターを使用した場所を受信する WCF のアクセス許可を設定  
 NetMsmqBinding を使用する WCF クライアントは、WCF-NetMsmq アダプターによって公開された WCF サービスにメッセージを送信する場合、サービスのキュー マネージャーによって管理されているターゲット キューにこのメッセージの宛先を指定します。 クライアント上のキュー マネージャーは、メッセージを転送 (または送信) キューに送ります。 転送キューは、ターゲット キューに転送するためのメッセージを格納する、クライアント側キュー マネージャー上のキューです。  
  
 サービスのキュー マネージャーは、それが所有するターゲット キューに宛先指定されたメッセージを受け入れて、格納します。 次に、サービスがターゲット キューからの読み取り要求を行い、キュー マネージャーがメッセージをサービスに配布します。 そのため、受信場所をホストする BizTalk ホスト インスタンスのサービス アカウントには、ターゲット キューから読み取るためのアクセス許可を与える必要があります。  
  
## <a name="use-an-empty-body-path-expression-to-receive-a-soap-message-with-character-data-in-the-content-of-the-soap-body-element"></a>SOAP Body 要素のコンテンツに文字データが含まれた SOAP メッセージを受信するには、空のボディ パス式を使用する  
 WCF 受信アダプター、SOAP のコンテンツに文字データの受信応答メッセージから BizTalk メッセージを作成する**本文**要素、次の例で示すようにしておき、**本文のパス式**で空のテキスト ボックス、**メッセージ**WCF アダプター トランスポートのプロパティ ダイアログ ボックスのタブ。  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
    <s:Header>  
      ...  
    </s:Header>  
    <s:Body>Contoso</s:Body>  
</s:Envelope>  
```  
  
 選択した場合、**エンベロープ**または**本文**オプション、アダプター、BizTalk メッセージを作成できません前の受信メッセージから。 受信 SOAP マーシャリング プロセスでエラーとなったメッセージは保留されないので、このメッセージは保留されません。 ボディ パス式を使用する方法について、**メッセージ** タブを参照してください[WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)します。  
  
> [!NOTE]
>  BTSNTSvc.exe.config ファイルを構成すると、Windows SDK の TraceViewer ツール (SvcTraceViewer.exe) を使用できます。 Windows SDK の詳細についてを参照してください"What is Windows SDK の新" [ http://go.microsoft.com/fwlink/?LinkId=75219](http://go.microsoft.com/fwlink/?LinkId=75219)します。 TraceViewer ツールの詳細についてを参照してください「TraceViewer ツール (SvcTraceViewer.exe)」 [ http://go.microsoft.com/fwlink/?LinkId=75218](http://go.microsoft.com/fwlink/?LinkId=75218)します。  
  
## <a name="using-schemas-that-reference-other-schemas"></a>他のスキーマを参照するスキーマの使用  
 使用することができます、**再定義**、**含める**と**インポート**大規模で複雑な場合は、スキーマになったときに要素またはときに、スキーマを表す、さまざまな種類のインスタンス メッセージでは、共通のいくつかの部分があります。 小さいスキーマを、取引先と交換するインスタンス メッセージの構造を最終的に定義するスキーマに結合すると便利な場合があります。 BizTalk WCF サービス公開ウィザードを使用して、これらのスキーマを WCF サービスとして公開できます。  
  
 BizTalk プロジェクトから WCF サービスを使用するために必要な BizTalk アイテムを作成するには、BizTalk WCF サービス使用ウィザードを使用する必要があります。 .NET アプリケーションから WCF サービスを使用するには、ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe) を使用して、WCF サービスのプロキシ クラスを作成する必要があります。 その他のスキーマを参照するスキーマを使用する方法の詳細については、次を参照してください。[を使用して、他のスキーマ](../core/schemas-that-use-other-schemas.md)と[作成を使用して、他のスキーマ方法](../core/how-to-create-schemas-that-use-other-schemas.md)します。 Svcutil.exe の詳細についてを参照してください「サービス モデル メタデータ ユーティリティ ツール (Svcutil.exe)」 [ http://go.microsoft.com/fwlink/?LinkID=74696](http://go.microsoft.com/fwlink/?LinkID=74696)します。  
  
 次の表は、他のスキーマを使用するスキーマを使って公開された WCF サービスを使用するときに理解しておく必要がある制限と注意点を示しています。  
  
|XML スキーマ要素|BizTalk WCF サービス公開ウィザードで公開した WCF サービスの使用|.NET アプリケーションでホストされる WCF サービスの使用|  
|------------------------|-------------------------------------------------------------------------------------|--------------------------------------------------------|  
|\<import\>|BizTalk WCF サービス使用ウィザードと Svcutil.exe の両方でサポート|BizTalk WCF サービス使用ウィザードと Svcutil.exe の両方でサポート|  
|\<include\>|両方の BizTalk WCF サービス使用ウィザードと Svcutil.exe ではサポートされて**に注意してください。** Svcutil.exe は、プロキシ クラスを作成するときに、警告メッセージを発生させる可能性があります。|両方の BizTalk WCF サービス使用ウィザードと Svcutil.exe ではサポートされて**に注意してください。** Svcutil.exe は、プロキシ クラスを作成するときに、警告メッセージを発生させる可能性があります。|  
|\<redefine\>|BizTalk WCF サービス使用ウィザードでサポートされています。<br />Svcutil.exe によってサポートが制限される**に注意してください。** Svcutil.exe は、同じ制限の**redefine** XSD.exe と要素が。|両方の BizTalk WCF サービス使用ウィザードと Svcutil.exe ではサポートされて**に注意してください。** Svcutil.exe は、プロキシ クラスを作成するときに、警告メッセージを発生させる可能性があります。|  
  
> [!NOTE]
>  使用してスキーマを公開した BizTalk WCF サービスに対してプロキシ クラスを作成するときに、Svcutil.exe が警告メッセージを発生させる可能性があります、**含める**と**redefine**要素。 たとえば、"グローバル要素は既に宣言されています。" などです。  
  
## <a name="ensure-that-an-in-process-wcf-receive-location-is-not-disabled-after-you-change-the-computer-name-part-in-its-service-endpoint-address"></a>サービス エンドポイント アドレスのコンピューター名の部分を変更した場合、インプロセス WCF 受信場所が無効になっていないことを確認する  
 コンピューター名の部分を変更する場合、**アドレス (URI)** プロセスで実行されている WCF のテキスト ボックスの受信場所、受信場所がまだ実行されているかどうかを確認するのには、BizTalk 管理コンソールを使用することをお勧めします。 たとえば、変更した場合、WCF NetTcp を使用してサービスのエンドポイント アドレスは受信アダプター、 **net.tcp://\<**<em>コンピューター名を</em>**\>/samplepath**を**net.tcp://localhost/samplepath**で、受信場所を無効にすることがあります、 **Service.InvalidOperationException**します。 パスの部分を変更せずに、サービス エンドポイント アドレスのコンピューター名の部分のみを変更した場合は、受信場所が無効になっていないことを確認し、必要に応じて有効にします。  
  
## <a name="set-the-appropriate-msdtc-security-configuration-options-on-client-computers-communicating-with-remote-wcf-receive-locations-through-a-transaction-protocol"></a>トランザクション プロトコルを使用してリモートの WCF 受信場所と通信するクライアント コンピューターで、適切な MSDTC セキュリティ構成オプションを設定する  
 Wcf-nettcp、Wcf-wshttp、および Wcf-netnamedpipe 受信アダプターで WCF クライアントを管理するトランザクション調整プロセスに参加できる、 **WS-AtomicTransaction**と**OleTransaction**トランザクション プロトコルです。 メッセージは、送信先の受信場所に送信したり、トランザクション プロトコルを使用してトランザクション コンテキストでメッセージ ボックス データベースから削除できます。  
  
 WCF 受信場所をリモートで通信するためにトランザクション プロトコルを使用して、MSDTC を構成する必要が適切に**セキュリティ構成**WCF クライアント コンピューター上でオプションです。 次の表に、必要な値は、MSDTC で使用できるオプションを**セキュリティ構成** ダイアログ ボックス。  
  
|構成オプション|既定値|推奨値|  
|--------------------------|-------------------|-----------------------|  
|ネットワーク DTC アクセス|Disabled|有効|  
|送信を許可する|Disabled|有効|  
|相互認証を必要とする|有効|場所が Windows Server 2003 SP1 または SP2 を実行しているしで構成された場合は、対応するリモートの受信が有効な**相互認証を必要**します。|  
|着信呼び出し側には認証を必要とする|Disabled|クラスター上で MSDTC を実行している場合は有効|  
  
 これらの変更を適用した後で、MSDTC サービスを再開する必要があります。  
  
 MSDTC へのアクセスに**セキュリティの構成** ダイアログ ボックスで、これらの手順に従います。  
  
1.  をクリックして**開始**、 をクリックして**実行**、および種類**dcomcnfg**を起動する、**コンポーネント サービス**管理コンソール。  
  
2.  展開**コンポーネント サービス**、展開**コンピューター**、右クリックして**マイ コンピューター**、順にクリックします**プロパティ**します。  
  
3.  **マイ コンピューター プロパティ**ダイアログ ボックスで、をクリックして、 **MSDTC**  タブをクリックして**セキュリティ構成**を表示する、**セキュリティの構成**  ダイアログ ボックス。  
  
## <a name="explanation-of-the-soap-wrapper-when-using-the-biztalk-wcf-service-publishing-wizard"></a>BizTalk WCF サービス公開ウィザードを使用する場合の SOAP ラッパーについての説明  
 オーケストレーションが [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] サービス公開ウィザードを使用して [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスとして公開されると、ラッパーが生成されます。 このラッパーは、XML メッセージでメッセージの送信先のポートのメソッド名を使用します。 このラッパーは Microsoft SOAP エンベロープの既定の設定です。 ラッパーを使用すると、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] でマルチパート SOAP メッセージを 1 つの WCF メッセージにラップして、アダプターによってエンドポイントに送信できます。  
  
 ベスト プラクティスとして、送信者はラッパーを使用して受信者はそのラッパーを要求するか、送信者はラッパーを使用しないで受信者は生の [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] メッセージを要求します。 ラッパーを使用するかどうかについてあらかじめ合意できていないと、送信内容と受信内容が一致しないという問題が発生する可能性があります。