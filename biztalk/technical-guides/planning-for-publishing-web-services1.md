---
title: "Web Services1 を公開するための計画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b571c3aa-874b-43f7-af2e-5a71113a93dd
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f5b2b5daa3c8e91c603b2bd410acb7edc624413
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-publishing-web-services"></a>Web サービスを公開するための計画
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web サービスを組み込みサポートを提供します。 再利用し、オーケストレーション内の既存の Web サービスを集計することができます。  
  
 (公開) を公開することも、オーケストレーションを Web を区切るための Web サービスとしてサービス ロジックとビジネス プロセス ロジックを更新または Web サービス ロジックを使用するコードを変更することがなく、必要に応じて、ビジネス ロジックを置き換えることができます。 この機能は「モジュールのコード」を実装するいると呼ばれます 一般に可能なモジュール型のコードを実装するベスト プラクティスと見なされます。 Web サービスを公開するには、Web サービスを有効にすることと、BizTalk Web サービス公開ウィザードを使用して Web サービスとして、オーケストレーションまたはスキーマを発行することが必要です。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SOAP アダプターを使用して Web サービスでのネイティブ アダプターのサポートを実装します。 ネイティブ アダプタのサポートにより、コードを記述しなくても、Web サービスのスケーラビリティ、フォールト トレランス、および追跡の機能を利用できます。 SOAP アダプターに関する詳細については、次を参照してください。 [SOAP アダプター](http://go.microsoft.com/fwlink/?LinkId=155754) (http://go.microsoft.com/fwlink/?LinkId=155754)。  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]Windows Azure AppFabric Service Bus エンドポイントを持つ WCF サービスとしての BizTalk アプリケーションの発行のサポートを提供します。 詳細については、次を参照してください。[を使用してサービスの接続の AppFabric](../technical-guides/planning-for-publishing-web-services1.md#BKMK_AFCS)です。  
  
 Web サービスの計画は、Web サービスを公開し、Web サービスの使用を計画の計画、2 つのカテゴリに分けることができます。 このトピックでは、Web サービスを公開するために必要な手順について説明します。  
  
## <a name="enabling-web-services"></a>Web サービスの有効化  
 Web サービスを公開するには、インターネット インフォメーション サービス (IIS)、BizTalk 分離ホスト、および Windows のユーザー アカウントとグループ アカウントを構成する必要があります。 このセクションでは、web サービスを有効にする方法の概要を説明します。 Web サービスの有効化の詳細については、IIS のドキュメントを参照してください。  
  
### <a name="internet-information-services-70"></a>インターネット インフォメーション サービス 7.0  
 Windows システムの IIS 7.0 であったり、ASP.NET 2.0 で構成された以降に Web サービスを公開することができます。 IIS 7.0、ASP.NET ワーカー プロセス内ですべての Web サービスを実行します。  
  
 IIS 7.0 では、Web サービス要求を処理する IIS アプリケーション プールを使用します。 IIS 7.0 は、複数のアプリケーション プールをサポートしているし、各アプリケーション プール プロセスが別のユーザー コンテキストで実行できます。  
  
### <a name="biztalk-isolated-hosts"></a>BizTalk 分離ホスト  
 Web サービスを有効にするには、少なくとも 1 つの分離ホストを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 分離ホストは、ISAPI 拡張機能と BizTalk Server が作成または管理する ASP.NET プロセスなどの外部プロセスを表します。 このような種類の外部プロセスは、HTTP/S や SOAP などの特定のアダプタをホストする必要があります。  
  
 BizTalk Server 構成マネージャーの作成、BizTalkServerIsolatedHost[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は既定の分離ホストとして使用します。 BizTalk 分離ホスト ユーザー グループは、このホストに関連付けられている既定の Windows グループ名です。 ホストとホスト インスタンスの詳細については、次を参照してください。[を管理する BizTalk ホストとホスト インスタンス](http://go.microsoft.com/fwlink/?LinkID=154191)(http://go.microsoft.com/fwlink/?LinkID=154191)。  
  
 分離ホスト インスタンスは、1 つのアダプターでのみ実行できます。 1 つの分離ホストで HTTP アダプタと SOAP アダプタの受信ハンドラを構成する場合、2 つのアプリケーション プール (各アダプタに 1 つのアプリケーション プール) を作成する必要があります。  
  
 たとえば、次のように 2 つの分離ホストを構成するとします。  
  
|分離ホスト名|受信場所|  
|------------------------|-----------------------|  
|分離ホスト 1|HTTP_ReceiveLocation1A<br /><br /> HTTP_ReceiveLocation1B<br /><br /> SOAP_ReceiveLocation1**注:** 、 **Isolated Host 1**の使用は、SOAP および HTTP アダプターの受信ハンドラー。|  
|分離ホスト 2|HTTP_ReceiveLocation2|  
  
 ごとに 1 つの受信場所を次のように、次の 4 つの仮想ディレクトリを作成することがあります。  
  
|受信場所|[仮想ディレクトリ]|  
|----------------------|-----------------------|  
|HTTP_ReceiveLocation1A|IIS_Virtual_Directory1A|  
|HTTP_ReceiveLocation1B|IIS_Virtual_Directory1B|  
|SOAP_ReceiveLocation1|IIS_Virtual_Directory1C|  
|HTTP_ReceiveLocation2|IIS_Virtual_Directory2|  
  
 次のように、仮想ディレクトリの少なくとも 3 つのアプリケーション プールを作成する必要があります。  
  
> [!NOTE]  
>  分離ホストごとに、少なくとも 1 つのアプリケーション プールを作成する必要があります。  
  
|仮想ディレクトリ|アプリケーション プール|Description|  
|-------------------------|----------------------|-----------------|  
|IIS_Virtual_Directory1A<br /><br /> IIS_Virtual_Directory1B|AppPool_Host1_HTTP|すべての受信場所で同じ分離ホスト (分離ホスト 1) と同じプロトコルを使用するため、個別のアプリケーション プールは不要です。|  
|IIS_Virtual_Directory1C|AppPool_Host1_SOAP|この受信場所で使用するプロトコル (SOAP) は、同じホスト (Isolated Host 1) の他の受信場所で使用するプロトコルと異なるため、個別のアプリケーション プールが必要です。|  
|IIS_Virtual_Directory2|AppPool_Host2_HTTP|この受信場所は、Isolated Host 1 と異なるホストで実行されるため、個別のアプリケーション プールが必要です。|  
  
 次の点に注意して、アプリケーション プールを作成します。  
  
-   アプリケーション プールのユーザー アカウントを、適切な分離ホストのローカル グループまたはドメイン グループに追加する必要があります。 詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](http://go.microsoft.com/fwlink/?LinkId=155755)(http://go.microsoft.com/fwlink/?LinkId=155755)。  
  
-   分離ホスト インスタンスと前の表に従って、対応するアプリケーション プールのユーザー アカウントと一致する必要があります。 分離ホスト インスタンスとアプリケーション プールのユーザー アカウントの間のリレーションシップの詳細については、次を参照してください。[サービス アカウントの変更をパスワード](http://go.microsoft.com/fwlink/?LinkId=155756)(http://go.microsoft.com/fwlink/?LinkId=155756)。  
  
-   IIS 5.0 および Windows 2000 Server または Windows XP で IIS 5.1 には、アプリケーション プールがありません。 IIS 5.0 および 5.1 を使用している場合に、IIS 仮想ディレクトリの分離レベルを設定**高**です。 仮想ディレクトリごとに個別の COM+ アプリケーションが作成されます。 各 COM+ アプリケーションは、それぞれの dllhost.exe で実行されます。  
  
### <a name="database-access-for-single-server-installations"></a>単一サーバー インストールのデータベースへのアクセス  
 BizTalk Server と BizTalk 管理データベースは、同じサーバーに存在する場合は、ローカルの ASPNET ユーザー アカウント、または最小限の特権を持つローカルまたはドメイン ユーザー アカウントに、ASP.NET ワーカー プロセスまたは IIS アプリケーション プールのユーザー コンテキストを設定してください。  
  
### <a name="database-access-for-multiple-server-installations"></a>複数のサーバー インストールでのデータベースへのアクセス  
 BizTalk Server と BizTalk 管理データベースは、別のサーバーに存在する場合は、ドメイン ユーザー アカウントに、ASP.NET ワーカー プロセスまたは IIS アプリケーション プールのユーザー コンテキストを変更する必要があります。  
  
 マルチ サーバー展開を実装するときに分離ホスト Windows グループが BizTalk データベース サーバーに属しているドメインに存在する必要があります。  
  
### <a name="minimizing-account-privileges-and-user-rights"></a>アカウントの特権およびユーザー権限を最小限に抑える  
 分離ホストを使用すると、外部プロセスで実行するアダプターに、BizTalk Server との連携に必要な最小限のリソースへのアクセス権が付与されます。 安全な展開では、する必要がありますユーザー コンテキストを提供、外部プロセス用最小限の特権です。  
  
### <a name="security-recommendations-for-biztalk-web-services-publishing-wizard"></a>BizTalk Web サービス公開ウィザードのセキュリティに関する推奨事項  
 BizTalk Web サービス公開ウィザードで作成する仮想ディレクトリは、親仮想ディレクトリまたは Web サイトからアクセス制御リスト (ACL) および認証要件を継承します。 親仮想ディレクトリまたは Web サイトへの匿名アクセスが許可されている場合、仮想ディレクトリを作成するときに、BizTalk Web サービス公開ウィザードによってその機能は削除されます。  
  
### <a name="enabling-aspnet-40-for-published-web-services"></a>公開済み Web サービスの ASP.NET 4.0 を有効にします。  
 公開済み Web サービスで ASP.NET 4.0 を有効にするのを参照してください。[公開 Web サービスの ASP.NET 4.0 を有効にする方法](http://go.microsoft.com/fwlink/?LinkId=155758)(http://go.microsoft.com/fwlink/?LinkId=155758)。  
  
## <a name="using-the-biztalk-web-services-publishing-wizard"></a>BizTalk Web サービス公開ウィザードを使用します。  
 オーケストレーションを Web サービスとして公開の詳細については、次を参照してください。[オーケストレーション Web サービスとして公開](http://go.microsoft.com/fwlink/?LinkId=155761)(http://go.microsoft.com/fwlink/?LinkId=155761)。  
  
 Web サービスとして公開スキーマの詳細については、次を参照してください。 [Web サービスとして公開スキーマ](http://go.microsoft.com/fwlink/?LinkId=155762)(http://go.microsoft.com/fwlink/?LinkId=155762)。  
  
##  <a name="BKMK_AFCS"></a>AppFabric を使用してサービスの接続  
 詳細については、Windows Azure AppFabric Service Bus を使用して WCF サービスとして BizTalk アプリケーションを公開エンドポイントを参照してください[AppFabric Connect サービスを使用するクラウドに BizTalk アプリケーションを公開する](http://go.microsoft.com/fwlink/?LinkID=204700)(http://go.microsoft.com/fwlink/ しますか。LinkID = 204700)。  
  
## <a name="planning-for-publishing-wcf-services"></a>WCF サービスを公開するための計画  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Windows Communication Foundation (WCF) の組み込みサポートが導入されています。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用すると、再利用し、すべての既存の WCF サービス、オーケストレーション内に集約できます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]WCF サービスでのネイティブ アダプタのサポートも実装します。 ネイティブ アダプタのサポートにより、コードを記述しなくても、WCF サービスのスケーラビリティ、フォールト トレランス、および追跡の機能を利用できます。 WCF アダプターについては、次を参照してください。 [WCF アダプタ](http://go.microsoft.com/fwlink/?LinkId=155763)(http://go.microsoft.com/fwlink/?LinkId=155763)。  
  
 WCF サービスの計画の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[WCF サービスの公開](http://go.microsoft.com/fwlink/?LinkId=155764)(http://go.microsoft.com/fwlink/?LinkId=155764)。  
  
## <a name="see-also"></a>参照  
 [Web サービスを使用の計画](../technical-guides/planning-for-consuming-web-services.md)