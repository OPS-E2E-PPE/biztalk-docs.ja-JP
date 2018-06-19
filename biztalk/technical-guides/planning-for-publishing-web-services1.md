---
title: Web サービスの計画を発行 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b571c3aa-874b-43f7-af2e-5a71113a93dd
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c34539704a0725a96464fae03226fb88cdd6660c
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015425"
---
# <a name="planning-for-publishing-web-services"></a>Web サービスを公開するための計画
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web サービスを組み込みサポートを提供します。 再利用し、オーケストレーション内の既存の Web サービスを集計することができます。  

## <a name="overview"></a>概要
 (公開) を公開することも、オーケストレーションを Web を区切るための Web サービスとしてサービス ロジックとビジネス プロセス ロジックを更新または Web サービス ロジックを使用するコードを変更することがなく、必要に応じて、ビジネス ロジックを置き換えることができます。 この機能は「モジュールのコード」を実装するいると呼ばれます 一般に可能なモジュール型のコードを実装するベスト プラクティスと見なされます。 Web サービスを公開するには、Web サービスを有効にすることと、BizTalk Web サービス公開ウィザードを使用して Web サービスとして、オーケストレーションまたはスキーマを発行することが必要です。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SOAP アダプターを使用して Web サービスでのネイティブ アダプターのサポートを実装します。 ネイティブ アダプタのサポートにより、コードを記述しなくても、Web サービスのスケーラビリティ、フォールト トレランス、および追跡の機能を利用できます。 SOAP アダプターに関する詳細については、次を参照してください。 [SOAP アダプター](../core/soap-adapter.md)です。  
  
Web サービスの計画は、Web サービスを公開し、Web サービスの使用を計画の計画、2 つのカテゴリに分けることができます。 このトピックでは、Web サービスを公開するために必要な手順について説明します。  
  
## <a name="enabling-web-services"></a>Web サービスの有効化  
 Web サービスを公開するには、インターネット インフォメーション サービス (IIS)、BizTalk 分離ホスト、および Windows のユーザー アカウントとグループ アカウントを構成する必要があります。 このセクションでは、web サービスを有効にする方法の概要を説明します。 Web サービスの有効化の詳細については、IIS のドキュメントを参照してください。  
  
### <a name="internet-information-services"></a>[インターネット インフォメーション サービス]
 IIS と ASP.NET が構成されている Windows システムには、Web サービスを公開することができます。 IIS では、すべての Web サービスを ASP.NET ワーカー プロセス内で実行します。  
  
 IIS では、Web サービス要求を処理するアプリケーション プールを使用します。 IIS で複数のアプリケーション プールをサポートし、各アプリケーション プール プロセスが別のユーザー コンテキストで実行できます。  
  
### <a name="biztalk-isolated-hosts"></a>BizTalk 分離ホスト  
 Web サービスを有効にするには、少なくとも 1 つの分離ホストを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 分離ホストは、ISAPI 拡張機能と BizTalk Server が作成または管理する ASP.NET プロセスなどの外部プロセスを表します。 このような種類の外部プロセスは、HTTP/S や SOAP などの特定のアダプタをホストする必要があります。  
  
 BizTalk Server 構成マネージャーの作成、BizTalkServerIsolatedHost[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は既定の分離ホストとして使用します。 BizTalk 分離ホスト ユーザー グループは、このホストに関連付けられている既定の Windows グループ名です。 ホストとホスト インスタンスの詳細については、次を参照してください。[を管理する BizTalk ホストとホスト インスタンス](../core/managing-biztalk-hosts-and-host-instances.md)です。  
  
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
  
-   アプリケーション プールのユーザー アカウントを、適切な分離ホストのローカル グループまたはドメイン グループに追加する必要があります。 参照してください[Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)です。  
  
-   分離ホスト インスタンスと前の表に従って、対応するアプリケーション プールのユーザー アカウントと一致する必要があります。 分離ホスト インスタンスとアプリケーション プールのユーザー アカウントの間のリレーションシップの詳細については、次を参照してください。[サービス アカウントの変更をパスワード](../core/how-to-change-service-accounts-and-passwords.md)です。  
  
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
参照してください[の ASP.NET 4.0 を有効にする方法の公開済み Web サービス](../core/how-to-enable-asp-net-4-0-for-published-web-services.md)です。  
  
## <a name="using-the-biztalk-web-services-publishing-wizard"></a>BizTalk Web サービス公開ウィザードを使用します。  
 オーケストレーションを Web サービスとして公開の詳細については、次を参照してください。[オーケストレーション Web サービスとして公開](../core/publishing-an-orchestration-as-a-web-service.md)です。  
  
 Web サービスとして公開スキーマの詳細については、次を参照してください。 [Web サービスとして公開スキーマ](../core/publishing-schemas-as-a-web-service.md)です。  
  
## <a name="planning-for-publishing-wcf-services"></a>WCF サービスを公開するための計画  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Windows Communication Foundation (WCF) の組み込みサポートが導入されています。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用すると、再利用し、すべての既存の WCF サービス、オーケストレーション内に集約できます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]WCF サービスでのネイティブ アダプタのサポートも実装します。 ネイティブ アダプタのサポートにより、コードを記述しなくても、WCF サービスのスケーラビリティ、フォールト トレランス、および追跡の機能を利用できます。 WCF アダプターについては、次を参照してください。 [WCF アダプタ](../core/wcf-adapters.md)です。  
  
 WCF サービスの計画の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[WCF サービスの公開](../core/publishing-wcf-services.md)です。  
  
## <a name="see-also"></a>参照  
 [Web サービスの使用の計画](../technical-guides/planning-for-consuming-web-services.md)
