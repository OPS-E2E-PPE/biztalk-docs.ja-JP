---
title: "受信アダプターの wcf サービス メタデータの公開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publishing, WCF services
- WCF services, publishing
ms.assetid: 4df09e8f-e0c9-41c5-bd71-13bb0e96cd97
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d922c0acecf81a96b0e40cebf739e7b56c5ffd3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-service-metadata-for-the-wcf-receive-adapters"></a>WCF 受信アダプタへのサービス メタデータの公開
BizTalk WCF サービス公開ウィザードでは、既存の WCF 受信場所のサービス メタデータを公開するための WCF サービスを作成できます。 公開されたメタデータ ドキュメントからクライアント サービス モデル コードを生成するに含まれている Service Model メタデータ ユーティリティ ツール (SvcUtil.exe) を使用することができます、 [!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]ソフトウェア開発キット (SDK) の[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]と[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]ランタイム コンポーネントです。  
  
> [!NOTE]
>  WCF アダプターのサービス メタデータを公開する前に、WCF を作成する必要があります、BizTalk 管理コンソールまたはに付属する BTSTask コマンド ライン ツールを使用して受信場所[!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 WCF を作成する方法の詳細については、受信場所の各 WCF アダプタの該当するトピックを参照してください[WCF アダプタ](../core/wcf-adapters.md)です。  
  
 **IIS のバージョン**  
  
 サービス メタデータを公開する WCF サービスは、次のオペレーティング システムでは、次のバージョンのインターネット インフォメーション サービス (IIS) で実行されていることができます。  
  
-   **Windows Vista、Windows Server 2008 SP2、および Windows Server 2008 R2 上の IIS 7.0/7.5。** IIS 7.0/7.5 は IIS 6.0 と同様の高度なプロセス モデルを提供します。 公開する BizTalk WCF サービスは IIS 7.0/7.5 の ASP.NET 互換モードで実行する必要があります。 IIS 7.0/7.5 の Web アプリケーションによって WCF 受信アダプターに公開されるサービス メタデータには、HTTP トランスポート経由でアクセスできます。  
  
 **WCF 受信場所のサービス メタデータの公開**  
  
 WCF 受信場所にサービス メタデータを公開するには、BizTalk WCF サービス公開ウィザードを使用して、サービス メタデータを提供する WCF サービスをホストする Web アプリケーションを作成する必要があります。 これにより、受信場所を WCF サービスのように呼び出すことができます。  BizTalk WCF サービス公開ウィザードは、作成した Web アプリケーションのルート フォルダに次のファイルを生成します。  
  
|ファイル|フォルダー|Description|  
|----------|------------|-----------------|  
|WCF サービス (.svc ファイル)|\|WCF 受信場所にサービス メタデータを公開する WCF サービス。 WCF サービスは、HTTP GET 要求で取得できるようにサービス メタデータを公開します。|  
|Web.config|\|ASP.NET 構成ファイル。このファイルには、ASP.NET Web アプリケーションの動作、公開済み WCF サービスの動作、メタデータ エンドポイント、および BizTalk 固有の設定についての情報が含まれます。 ウィザードには、Web.config が生成されるときに、 **httpGetEnabled**の属性、  **\<serviceMetadata >**要素に設定されている**true**です。 メタデータ インポート ツール (SvcUtil.exe など) を使用すると、開発環境でこのサービスを呼び出すために必要なクライアント コードを生成できます。 メタデータが公開されるアドレスは、WCF サービスのエンドポイント アドレスと**? wsdl**クエリ文字列。 **注:** BizTalk WCF 公開ウィザードによって生成される既定のメタデータ バインディングが安全でないと、メタデータへの匿名アクセスを許可します。 サービス メタデータには、サービスの詳細な説明が含まれており、意図的に、または意図せずに機密情報が含まれる可能性があります。 サービス メタデータを不正アクセスから保護するには、メタデータ エンドポイントでセキュリティ保護されたバインドを使用するように Web.config を変更します。|  
|ServiceDescription.xml|\|メッセージの種類を含む、公開済み WCF サービスのコントラクトが記述されている XML ファイル。|  
|BizTalk スキーマ (.xsd ファイル)|\App_Data|WCF 受信場所で使用される XML インスタンス メッセージの構造を定義する XML スキーマ。|  
|SchemaIndex.xml|\App_Data|WCF 受信場所で使用される XML スキーマ ファイルを示す XML ファイル。|  
|Serialization.xsd|\App_Data|によってエクスポートされた XML スキーマ[DataContractSerializer](http://go.microsoft.com/fwlink/?LinkId=81722)型、要素、および、名前空間からの属性に対する http://schemas.microsoft.com/2003/10/Serialization/ です。|  
|BindingInfo.xml|\App_Data\Temp|受信場所を構成するために開発用コマンド ライン ツールまたはウィザードによってインポートされる BizTalk バインド ファイル。 公開済み WCF サービスは、実行時にこのファイルと Temp フォルダを使用しません。|  
|WcfServiceDescription.xml|\App_Data\Temp|BizTalk WCF サービス公開ウィザードで、この Web アプリケーションを作成する際に使用した設定を要約した XML ファイル。 公開済み WCF サービスは、実行時にこのファイルと Temp フォルダを使用しません。|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk WCF サービス公開ウィザードを使用して、コンテンツ ベース ルーティングの WCF 受信場所用にサービス メタデータを公開する方法](../core/publish-service-metadata-for-a-wcf-receive-location-for-content-based-routing.md)  
  
-   [オーケストレーション ポートにバインドされている BizTalk WCF サービス公開ウィザードを使用して、WCF 受信場所用にサービス メタデータを公開する方法](../core/publish-receive-location-service-metadata-biztalk-wcf-service-publishing-wizard.md)  
  
## <a name="see-also"></a>参照  
 [チュートリアル: Wcf-netmsmq アダプタを使用して WCF サービスの発行](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)