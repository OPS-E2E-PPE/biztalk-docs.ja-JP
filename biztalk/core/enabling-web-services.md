---
title: Web サービスの有効化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- hosts, isolated
- Web services, planning
- Web services, enabling
ms.assetid: 2a4681f6-9ded-423d-baa5-5831e6a85c61
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59a811fe61a6a5b17e8c5cbf803b35d630836d05
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349697"
---
# <a name="enabling-web-services"></a>Web サービスを有効にします。
Web サービスを発行するには、インターネット インフォメーション サービス (IIS)、BizTalk 分離ホスト、および Windows ユーザーおよびグループ アカウントを構成する必要があります。 このセクションでは、IIS の Web サービスを有効にする方法について説明します。 Web サービスを有効にする方法の詳細については、IIS のマニュアルを参照してください。  
  
 **[インターネット インフォメーション サービス]**  
  
 ASP.NET で構成された IIS を搭載する Windows システムに Web サービスを発行することができます。 各サーバーでは、すべての Web サービスは、ASP.NET ワーカー プロセス内で実行します。  
  
 ASP.NET ワーカー プロセスは、既定では、ローカルの ASPNET アカウントを使用します。 IIS は、Web サービス要求を処理するためのアプリケーション プールを使用します。  
  
 **BizTalk 分離ホスト**  
  
 Web サービスを有効には、BizTalk Server で少なくとも 1 つの分離ホストを作成する必要があります。 分離ホストは、ISAPI 拡張機能と BizTalk Server は作成または制御する ASP.NET プロセスなどの外部プロセスを表します。 これらの種類の外部プロセスでは、HTTP/S や SOAP などの特定のアダプターをホストする必要があります。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration Manager は、BizTalk が既定値として使用する BizTalkServerIsolatedHost を作成します。 分離ホスト。 BizTalk 分離ホスト ユーザー グループは、既定では、このホストに関連付けられている Windows グループの名前です。 ホストとホスト インスタンスの詳細については、次を参照してください。 [BizTalk ホストの管理およびホスト インスタンス](../core/managing-biztalk-hosts-and-host-instances.md)します。  
  
 分離ホスト インスタンスは、1 つのアダプターでのみ実行できます。 1 つの分離ホストで HTTP および SOAP アダプターの受信ハンドラーを構成する場合は、2 つのアプリケーション プール、アダプターごとに 1 つのアプリケーション プールを作成する必要があります。  
  
 たとえば、次の 2 つの分離ホストを構成する予定の場合。  
  
|分離ホスト名|受信場所|  
|------------------------|-----------------------|  
|分離ホスト 1|HTTP_ReceiveLocation1A<br /><br /> HTTP_ReceiveLocation1B<br /><br /> SOAP_ReceiveLocation1**に注意してください。****Isolated Host 1**の使用は、SOAP および HTTP アダプターの受信ハンドラー。|  
|分離ホスト 2|HTTP_ReceiveLocation2|  
  
 ごとに 1 つの受信場所を次のように、4 つの仮想ディレクトリを作成することがあります。  
  
|受信場所|仮想ディレクトリ|  
|----------------------|-----------------------|  
|HTTP_ReceiveLocation1A|IIS_Virtual_Directory1A|  
|HTTP_ReceiveLocation1B|IIS_Virtual_Directory1B|  
|SOAP_ReceiveLocation1|IIS_Virtual_Directory1C|  
|HTTP_ReceiveLocation2|IIS_Virtual_Directory2|  
  
 次に、よう、仮想ディレクトリの少なくとも 3 つのアプリケーション プールを作成する必要があります。  
  
> [!NOTE]
>  分離ホストごとに少なくとも 1 つのアプリケーション プールを作成する必要があります。  
  
|仮想ディレクトリ|アプリケーション プール|説明|  
|-------------------------|----------------------|-----------------|  
|IIS_Virtual_Directory1A<br /><br /> IIS_Virtual_Directory1B|AppPool_Host1_HTTP|同じ分離ホスト (Isolated Host 1) と同じプロトコルのすべての受信場所があるために、個別のアプリケーション プールは必要ありません。|  
|IIS_Virtual_Directory1C|AppPool_Host1_SOAP|受信場所は、同じホスト (Isolated Host 1) で他の受信場所から別のプロトコル (SOAP) を使用するため、個別のアプリケーション プールが必要です。|  
|IIS_Virtual_Directory2|AppPool_Host2_HTTP|受信場所は、分離ホスト 1 から別のホストで実行されるので、個別のアプリケーション プールが必要です。|  
  
> [!NOTE]
>  分離ホストの適切なローカルまたはドメイン グループには、アプリケーション プールのユーザー アカウントを追加する必要があります。 詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)します。  
  
> [!NOTE]
>  分離ホスト インスタンスと前の表に従って、対応するアプリケーション プールのユーザー アカウントと一致する必要があります。 分離ホスト インスタンスとアプリケーション プールのユーザー アカウントの間のリレーションシップの詳細については、次を参照してください。[変更サービス アカウントおよびパスワード方法](../core/how-to-change-service-accounts-and-passwords.md)します。  
  
 **単一サーバー インストールのデータベースへのアクセス**  
  
 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と BizTalk 管理データベースが同じサーバー上に、ローカルの ASPNET ユーザー アカウント、または最小限の特権を持つローカルまたはドメイン ユーザー アカウントに、ASP.NET ワーカー プロセスまたは IIS アプリケーション プールのユーザー コンテキストを設定する必要があります。  
  
 **複数のサーバー インストールでのデータベースへのアクセス**  
  
 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と BizTalk 管理データベースが別のサーバーに存在する、ドメイン ユーザー アカウントに、ASP.NET ワーカー プロセスまたは IIS アプリケーション プールのユーザー コンテキストを変更する必要があります。  
  
 マルチ サーバー展開を実装する場合は、分離ホスト Windows グループが BizTalk データベース サーバーが属するドメインに存在する必要があります。  
  
 **アカウントの特権およびユーザー権限を最小限に抑える**  
  
 分離ホストを使用して、BizTalk Server との対話に必要なリソース量が最小限に外部プロセスへのアクセスで実行されるアダプターを与えます。 セキュリティで保護された展開は、するようにユーザー コンテキスト、外部プロセスの最小限の特権します。  
  
 **BizTalk Web サービス公開ウィザードのセキュリティに関する推奨事項**  
  
 BizTalk Web サービス公開ウィザードによって作成された仮想ディレクトリでは、アクセス制御リスト (ACL) と認証の要件を親仮想ディレクトリまたは Web サイトから継承されます。 親仮想ディレクトリまたは Web サイトへの匿名アクセスを許可している場合、BizTalk Web サービス公開ウィザードは、仮想ディレクトリを作成するときにその機能を削除します。  
  
 次には、セキュリティに関する注意事項と推奨事項が含まれます。[!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)]します。  
  
## <a name="next"></a>Next
  
[公開済み Web サービスの ASP.NET を有効にする方法](../core/how-to-enable-asp-net-4-0-for-published-web-services.md)