---
title: Web Services の計画の発行 |Microsoft Docs
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
ms.openlocfilehash: 25ac0868660c5cff39f4879fe44738036dccca1f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400705"
---
# <a name="planning-for-publishing-web-services"></a>Web サービス公開の計画
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web サービスの組み込みサポートを提供します。 再利用し、オーケストレーション内で、既存の Web サービスを集計できます。  

## <a name="overview"></a>概要
 (公開) を公開することも、オーケストレーションを Web を分離する Web サービスとしてのサービス ロジックとビジネス プロセス ロジックを更新または Web サービスのロジックに使用されるコードの手を加えることがなく、必要に応じて、ビジネス ロジックを置き換えることができます。 この機能は実装「モジュールのコード」と呼ばれます 一般に可能な場合は、モジュール コードを実装するベスト プラクティスと見なされます。 Web サービスを公開するには、Web サービスを有効にして、オーケストレーションまたはスキーマを BizTalk Web サービス公開ウィザードを使用して Web サービスとして発行する必要があります。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SOAP アダプターを使用して Web サービスでのネイティブ アダプターのサポートを実装します。 ネイティブ アダプタのサポートは、スケーラビリティ、フォールト トレランス、および Web サービスの機能を 1 行のコードを記述することがなく追跡を提供します。 SOAP アダプターに関する詳細については、次を参照してください。 [SOAP アダプター](../core/soap-adapter.md)します。  
  
Web サービスの計画は、Web サービスを公開し、Web サービスを使用するための計画の計画、2 つのカテゴリに分けることができます。 このトピックでは、Web サービスを公開するために従う必要のある手順について説明します。  
  
## <a name="enabling-web-services"></a>Web サービスを有効にします。  
 Web サービスを発行するには、インターネット インフォメーション サービス (IIS)、BizTalk 分離ホスト、および Windows ユーザーおよびグループ アカウントを構成する必要があります。 このセクションでは、web サービスを有効にする方法の概要を示します。 Web サービスを有効にする方法の詳細については、IIS のマニュアルを参照してください。  
  
### <a name="internet-information-services"></a>[インターネット インフォメーション サービス]
 ASP.NET で構成された IIS を搭載する Windows システムに Web サービスを発行することができます。 IIS では、すべての Web サービスは、ASP.NET ワーカー プロセス内で実行します。  
  
 IIS は、Web サービス要求を処理するためのアプリケーション プールを使用します。 IIS が複数のアプリケーション プールをサポートし、各アプリケーション プール プロセスが別のユーザー コンテキストで実行できます。  
  
### <a name="biztalk-isolated-hosts"></a>BizTalk 分離ホスト  
 Web サービスを有効にするには少なくとも 1 つの分離ホストを作成する必要がある[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 分離ホストは、ISAPI 拡張機能と BizTalk Server は作成または制御する ASP.NET プロセスなどの外部プロセスを表します。 これらの種類の外部プロセスでは、HTTP/S や SOAP などの特定のアダプターをホストする必要があります。  
  
 BizTalk Server 構成マネージャーの作成、BizTalkServerIsolatedHost[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は既定の分離ホストとして使用します。 BizTalk 分離ホスト ユーザー グループは、既定では、このホストに関連付けられている Windows グループの名前です。 ホストとホスト インスタンスの詳細については、次を参照してください。 [BizTalk ホストの管理およびホスト インスタンス](../core/managing-biztalk-hosts-and-host-instances.md)します。  
  
 分離ホスト インスタンスは、1 つのアダプターでのみ実行できます。 1 つの分離ホストで HTTP および SOAP アダプターの受信ハンドラーを構成する場合は、2 つのアプリケーション プール、アダプターごとに 1 つのアプリケーション プールを作成する必要があります。  
  
 たとえば、次のように 2 つの分離ホストを構成する予定の場合。  
  
|分離ホスト名|受信場所|  
|------------------------|-----------------------|  
|分離ホスト 1|HTTP_ReceiveLocation1A<br /><br /> HTTP_ReceiveLocation1B<br /><br /> SOAP_ReceiveLocation1**に注意してください。****Isolated Host 1**の使用は、SOAP および HTTP アダプターの受信ハンドラー。|  
|分離ホスト 2|HTTP_ReceiveLocation2|  
  
 ごとに 1 つの受信場所を次のように、4 つの仮想ディレクトリを作成することがあります。  
  
|受信場所|[仮想ディレクトリ]|  
|----------------------|-----------------------|  
|HTTP_ReceiveLocation1A|IIS_Virtual_Directory1A|  
|HTTP_ReceiveLocation1B|IIS_Virtual_Directory1B|  
|SOAP_ReceiveLocation1|IIS_Virtual_Directory1C|  
|HTTP_ReceiveLocation2|IIS_Virtual_Directory2|  
  
 よう、仮想ディレクトリの少なくとも 3 つのアプリケーション プールを作成する必要があります。  
  
> [!NOTE]  
>  分離ホストごとに少なくとも 1 つのアプリケーション プールを作成する必要があります。  
  
|仮想ディレクトリ|アプリケーション プール|説明|  
|-------------------------|----------------------|-----------------|  
|IIS_Virtual_Directory1A<br /><br /> IIS_Virtual_Directory1B|AppPool_Host1_HTTP|同じ分離ホスト (Isolated Host 1) と同じプロトコルのすべての受信場所があるために、個別のアプリケーション プールは必要ありません。|  
|IIS_Virtual_Directory1C|AppPool_Host1_SOAP|受信場所は、同じホスト (Isolated Host 1) で他の受信場所から別のプロトコル (SOAP) を使用するため、個別のアプリケーション プールが必要です。|  
|IIS_Virtual_Directory2|AppPool_Host2_HTTP|受信場所は、分離ホスト 1 から別のホストで実行されるので、個別のアプリケーション プールが必要です。|  
  
 アプリケーション プールを作成する際に、次の重要な点を考慮してください。  
  
-   分離ホストの適切なローカルまたはドメイン グループには、アプリケーション プールのユーザー アカウントを追加する必要があります。 参照してください[Windows グループと BizTalk Server のユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)します。  
  
-   分離ホスト インスタンスと前の表に従って、対応するアプリケーション プールのユーザー アカウントと一致する必要があります。 分離ホスト インスタンスとアプリケーション プールのユーザー アカウントの間のリレーションシップの詳細については、次を参照してください。[変更サービス アカウントおよびパスワード方法](../core/how-to-change-service-accounts-and-passwords.md)します。  
  
### <a name="database-access-for-single-server-installations"></a>単一サーバー インストールのデータベースへのアクセス  
 BizTalk Server と BizTalk 管理データベースと同じサーバーに存在する場合、ローカルの ASPNET ユーザー アカウントまたは最小限の特権を持つローカルまたはドメイン ユーザー アカウントに、ASP.NET ワーカー プロセスまたは IIS アプリケーション プールのユーザー コンテキストを設定する必要があります。  
  
### <a name="database-access-for-multiple-server-installations"></a>複数のサーバー インストールでのデータベースへのアクセス  
 BizTalk Server と BizTalk 管理データベースの異なるサーバーに存在する場合は、ドメイン ユーザー アカウントに、ASP.NET ワーカー プロセスまたは IIS アプリケーション プールのユーザー コンテキストを変更する必要があります。  
  
 マルチ サーバー展開を実装する場合は、分離ホスト Windows グループが BizTalk データベース サーバーが属するドメインに存在する必要があります。  
  
### <a name="minimizing-account-privileges-and-user-rights"></a>アカウントの特権およびユーザー権限を最小限に抑える  
 分離ホストを使用して、BizTalk Server との対話に必要なリソース量が最小限に外部プロセスへのアクセスで実行されるアダプターを与えます。 安全な展開では、するようにユーザー コンテキスト、外部プロセスの最小限の特権します。  
  
### <a name="security-recommendations-for-biztalk-web-services-publishing-wizard"></a>BizTalk Web サービス公開ウィザードのセキュリティに関する推奨事項  
 BizTalk Web サービス公開ウィザードによって作成された仮想ディレクトリでは、アクセス制御リスト (ACL) と認証の要件を親仮想ディレクトリまたは Web サイトから継承されます。 親仮想ディレクトリまたは Web サイトへの匿名アクセスを許可している場合、BizTalk Web サービス公開ウィザードは、仮想ディレクトリを作成するときにその機能を削除します。  
  
### <a name="enabling-aspnet-40-for-published-web-services"></a>公開済み Web サービスの ASP.NET 4.0 の有効化  
参照してください[の ASP.NET 4.0 を有効にする方法が公開済み Web サービス](../core/how-to-enable-asp-net-4-0-for-published-web-services.md)します。  
  
## <a name="using-the-biztalk-web-services-publishing-wizard"></a>BizTalk Web サービス公開ウィザードを使用します。  
 Web サービスとしてのオーケストレーションの公開の詳細については、次を参照してください。 [Web サービスとしてのオーケストレーションの公開](../core/publishing-an-orchestration-as-a-web-service.md)します。  
  
 Web サービスとして公開スキーマの詳細については、次を参照してください。 [Web サービスとして公開スキーマ](../core/publishing-schemas-as-a-web-service.md)します。  
  
## <a name="planning-for-publishing-wcf-services"></a>WCF サービスを公開するための計画  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Windows Communication Foundation (WCF) 用の組み込みサポートが導入されています。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 再利用し、すべての既存の WCF サービス、オーケストレーション内の集計ができます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] WCF サービスにもネイティブ アダプターのサポートを実装します。 ネイティブ アダプタのサポートは、スケーラビリティ、フォールト トレランス、およびコードを記述することがなく追跡の WCF サービスの機能を提供します。 WCF アダプターについては、次を参照してください。 [WCF アダプタ](../core/wcf-adapters.md)します。  
  
 WCF サービスの計画の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[WCF サービスの公開](../core/publishing-wcf-services.md)します。  
  
## <a name="see-also"></a>参照  
 [Web サービスの使用の計画](../technical-guides/planning-for-consuming-web-services.md)
