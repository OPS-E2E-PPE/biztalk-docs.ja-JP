---
title: 発行の WCF サービスを分離 WCF 受信アダプター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive adapters, WCF services
- publishing, WCF services
- WCF services, receive adapters
- WCF services, publishing
ms.assetid: 62ebf373-075c-4c98-8130-ac2cf06e4a70
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c5305560713771e7279eb013d26ff267aa21a74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271634"
---
# <a name="publishing-wcf-services-with-the-isolated-wcf-receive-adapters"></a>分離 WCF 受信アダプタでの WCF サービスの公開
BizTalk Windows Communication Foundation (WCF) アダプターを許可する[!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の WCF ベースのアプリケーションと通信します。 BizTalk WCF アダプターには 7 つの物理アダプターが含まれています。 各アダプター (WCF-CustomIsolated アダプターを除く) は、送信アダプターと受信アダプターで構成されています。  
  
 WCF 受信アダプタの 2 種類のアダプターで提供される: WCF アダプタとインプロセス WCF アダプターを分離します。 インプロセス アダプタは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって管理されますが、分離アダプタは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ではインスタンス化されません。 代わりに、別のプロセスでインスタンス化され、ホストされます。 分離 WCF アダプタは、インターネット インフォメーション サービス (IIS) で実行されている Web アプリケーションでホストされます。  
  
> [!NOTE]
>  分離 WCF アダプターを使用して WCF サービスを公開する前に、インターネット インフォメーション サービス (IIS) で WCF サービスをホストする方法について理解しておく必要があります。 IIS でホストされる WCF サービスの詳細についてを参照してください「IIS でホストしている」 [http://go.microsoft.com/fwlink/?LinkID=75700](http://go.microsoft.com/fwlink/?LinkID=75700)です。  
  
 **IIS のバージョン**  
  
 3 つの分離 WCF アダプター (WCF-CustomIsolated、WCF-BasicHttp、WCF-WSHttp) をホストできるオペレーティング システムの IIS バージョンを次に示します。  
  
-   **Windows Vista および Windows Server 2008 上の IIS 7.0/7.5。** IIS 7.0/7.5 は IIS 6.0 と同様の高度なプロセス モデルを提供します。 公開する BizTalk WCF サービスは IIS 7.0/7.5 の ASP.NET 互換モードで実行する必要があります。  
  
> [!NOTE]
>  IIS 7.0/7.5 の Windows プロセス アクティブ化サービス (WAS) で、HTTP 以外のプロトコル経由でのアクティベーションとネットワーク通信を許可している場合でも、分離 WCF アダプターでは HTTP トランスポートのみをサポートします。  
  
 **分離 WCF アダプタ**  
  
 分離 WCF アダプタの一覧を次に示します。  
  
-   **Wcf-wshttp アダプタ**です。 HTTP トランスポート経由の WS-* 標準をサポートします。 WCF-WSHttp アダプターは、外部アプリケーションと MessageBox データベース間のトランザクション上の対話に WS-Transaction、メッセージ セキュリティと認証に WS-Security という仕様を実装します。 トランスポートは HTTP または HTTPS で、メッセージのエンコードは、テキスト エンコードまたは Message Transmission Optimization Mechanism (MTOM) エンコードです。  
  
-   **Wcf-basichttp アダプター**です。 ASMX ベースの Web サービスとクライアント、および、WS に準拠するその他のサービスの通信の Basic Profile 1.1 です。 トランスポートは HTTP または HTTPS で、メッセージのエンコードは、テキスト エンコードまたは MTOM エンコードです。  
  
-   **Wcf-customisolated アダプター**です。 HTTP トランスポート経由で WCF 拡張機能を使用できるようにします。 このアダプタでは、分離ホストで実行している受信場所に対して、WCF バインドと WCF 動作情報を選択および構成できます。  
  
 **分離 WCF アダプターで WCF サービスの公開**  
  
 分離 WCF 受信アダプタを使用して WCF サービスを公開するには、BizTalk WCF サービス公開ウィザードで、分離 WCF アダプタをホストする Web アプリケーションを作成する必要があります。 また、BizTalk WCF サービス公開ウィザードを使用すると、作成した Web アプリケーションのルート フォルダに次のファイルが生成されます。  
  
|ファイル|フォルダー|Description|  
|----------|------------|-----------------|  
|WCF サービス (.svc ファイル)|\|分離 WCF アダプタを使用して公開される WCF 受信場所の WCF サービス。|  
|Web.config|\|ASP.NET 構成ファイル。このファイルには、ASP.NET Web アプリケーションの動作、公開済み WCF サービスの動作、メタデータ エンドポイント、および BizTalk 固有の設定についての情報が含まれます。 BizTalk WCF 公開ウィザードによって生成される既定のメタデータ バインドはセキュリティで保護されていないため、メタデータへの匿名アクセスが可能です。 サービス メタデータには、サービスの詳細な説明が含まれており、意図的に、または意図せずに機密情報が含まれる可能性があります。 サービス メタデータを不正アクセスから保護するには、メタデータ エンドポイントでセキュリティ保護されたバインドを使用するように Web.config を変更します。 **注:** メタデータ エンドポイントのバインドとサービス エンドポイントのバインドのすべての組み合わせが無効です。 メタデータ エンドポイントのバインド構成がサービス エンドポイントのバインド構成と一致する必要がある場合もあります。 たとえば、サービス エンドポイントのセキュリティ モードで HTTPS を使用している場合は、HTTP トランスポートを必要とするセキュリティ モードでメタデータ エンドポイントを構成することはできません。|  
|ServiceDescription.xml|\|メッセージの種類を含む、公開済み WCF サービスのコントラクトが記述されている XML ファイル。|  
|BizTalk スキーマ (.xsd ファイル)|\App_Data|分離 WCF アダプタを使用して公開される XML インスタンス メッセージの構造を定義する XML スキーマ。|  
|SchemaIndex.xml|\App_Data|公開済み WCF サービスで使用する XML スキーマ ファイルを示す XML ファイル。|  
|Serialization.xsd|\App_Data|によってエクスポートされた XML スキーマ[DataContractSerializer](http://go.microsoft.com/fwlink/?LinkId=81722)型、要素、および、名前空間からの属性に対する http://schemas.microsoft.com/2003/10/Serialization/ です。|  
|BindingInfo.xml|\App_Data\Temp|公開済み WCF サービスに対応する WCF 受信場所を作成するための BizTalk バインド ファイル。 開発用コマンド ライン ツールまたはウィザードで BindingInfo.xml ファイルをインポートして、必要な受信場所を作成できます。 公開済み WCF サービスは、実行時にこのファイルと Temp フォルダを使用しません。|  
|WcfServiceDescription.xml|\App_Data\Temp|BizTalk WCF サービス公開ウィザードで、この Web アプリケーションを作成する際に使用した設定を要約した XML ファイル。 公開済み WCF サービスは、実行時にこのファイルと Temp フォルダを使用しません。|  
  
 また、BizTalk WCF サービス公開ウィザードでは、WCF 受信場所を作成することも、分離 WCF アダプタを実行している受信場所のサービス メタデータを作成することもできます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk WCF サービス公開ウィザードを使用してオーケストレーションを WCF サービスとして公開する方法](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)  
  
-   [BizTalk WCF サービス公開ウィザードを使用してスキーマを WCF サービスとして公開する方法](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)  
  
-   [構成の IIS 分離 wcf 受信アダプター](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)  
  
-   [BizTalk WCF サービス公開ウィザードで公開された WCF サービスを構成する方法](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)  
  
-   [BizTalk WCF サービス公開ウィザードによって公開された WCF サービスをテストするための .NET アプリケーションを作成する方法](../core/use-net-application-to-test-wcf-service-published-with-wcf-service-publishing.md)  
  
## <a name="see-also"></a>参照  
 [チュートリアル: Wcf-basichttp アダプタを使用して WCF サービスの発行](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)