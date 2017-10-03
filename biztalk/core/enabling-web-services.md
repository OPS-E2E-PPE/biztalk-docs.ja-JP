---
title: "Web サービスの有効化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- hosts, isolated
- Web services, planning
- Web services, enabling
ms.assetid: 2a4681f6-9ded-423d-baa5-5831e6a85c61
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b7cd0b1694422caf04285206f0bd7411ff5de20
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="enabling-web-services"></a>Web サービスの有効化
Web サービスを公開するには、インターネット インフォメーション サービス (IIS)、BizTalk 分離ホスト、および Windows のユーザー アカウントとグループ アカウントを構成する必要があります。 このセクションでは、IIS の Web サービスを有効にする方法について説明します。 Web サービスの有効化の詳細については、IIS のドキュメントを参照してください。  
  
 **[インターネット インフォメーション サービス]**  
  
 IIS と ASP.NET が構成されている Windows システムには、Web サービスを公開することができます。 サーバーごとに、すべての Web サービスが ASP.NET ワーカー プロセス内で実行されます。  
  
 既定では、ASP.NET ワーカー プロセスは、ローカルの ASPNET アカウントを使用します。 IIS では、Web サービス要求を処理するアプリケーション プールを使用します。  
  
 **BizTalk 分離ホスト**  
  
 Web サービスを有効にするには、BizTalk Server で少なくとも 1 つの分離ホストを作成する必要があります。 分離ホストは、ISAPI 拡張プロセスや ASP.NET プロセスなどの、BizTalk Server で作成、コントロールしない外部プロセスといえます。 このような種類の外部プロセスは、HTTP/S や SOAP などの特定のアダプタをホストする必要があります。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成マネージャにより、BizTalk が既定の分離ホストとして使用する BizTalkServerIsolatedHost が作成されます。 BizTalk 分離ホスト ユーザー グループは、このホストに関連付けられている既定の Windows グループ名です。 ホストとホスト インスタンスの詳細については、次を参照してください。[を管理する BizTalk ホストとホスト インスタンス](../core/managing-biztalk-hosts-and-host-instances.md)です。  
  
 分離ホスト インスタンスは、1 つのアダプターでのみ実行できます。 1 つの分離ホストで HTTP アダプタと SOAP アダプタの受信ハンドラを構成する場合、2 つのアプリケーション プール (各アダプタに 1 つのアプリケーション プール) を作成する必要があります。  
  
 たとえば、次の 2 つの分離ホストを構成するとします。  
  
|分離ホスト名|受信場所|  
|------------------------|-----------------------|  
|分離ホスト 1|HTTP_ReceiveLocation1A<br /><br /> HTTP_ReceiveLocation1B<br /><br /> SOAP_ReceiveLocation1**注:** 、 **Isolated Host 1**の使用は、SOAP および HTTP アダプターの受信ハンドラー。|  
|分離ホスト 2|HTTP_ReceiveLocation2|  
  
 仮想ディレクトリを 4 つ (次の受信場所ごとに 1 つ) 作成するとします。  
  
|受信場所|仮想ディレクトリ|  
|----------------------|-----------------------|  
|HTTP_ReceiveLocation1A|IIS_Virtual_Directory1A|  
|HTTP_ReceiveLocation1B|IIS_Virtual_Directory1B|  
|SOAP_ReceiveLocation1|IIS_Virtual_Directory1C|  
|HTTP_ReceiveLocation2|IIS_Virtual_Directory2|  
  
 次のように、仮想ディレクトリに、少なくとも 3 つのアプリケーション プールを作成する必要があります。  
  
> [!NOTE]
>  分離ホストごとに、少なくとも 1 つのアプリケーション プールを作成する必要があります。  
  
|仮想ディレクトリ|アプリケーション プール|Description|  
|-------------------------|----------------------|-----------------|  
|IIS_Virtual_Directory1A<br /><br /> IIS_Virtual_Directory1B|AppPool_Host1_HTTP|すべての受信場所で同じ分離ホスト (分離ホスト 1) と同じプロトコルを使用するため、個別のアプリケーション プールは不要です。|  
|IIS_Virtual_Directory1C|AppPool_Host1_SOAP|この受信場所で使用するプロトコル (SOAP) は、同じホスト (Isolated Host 1) の他の受信場所で使用するプロトコルと異なるため、個別のアプリケーション プールが必要です。|  
|IIS_Virtual_Directory2|AppPool_Host2_HTTP|この受信場所は、Isolated Host 1 と異なるホストで実行されるため、個別のアプリケーション プールが必要です。|  
  
> [!NOTE]
>  アプリケーション プールのユーザー アカウントを、適切な分離ホストのローカル グループまたはドメイン グループに追加する必要があります。 詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)です。  
  
> [!NOTE]
>  分離ホスト インスタンスと前の表に従って、対応するアプリケーション プールのユーザー アカウントと一致する必要があります。 分離ホスト インスタンスとアプリケーション プールのユーザー アカウントの間のリレーションシップの詳細については、次を参照してください。[サービス アカウントの変更をパスワード](../core/how-to-change-service-accounts-and-passwords.md)です。  
  
 **単一サーバー インストールのデータベースへのアクセス**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] および BizTalk 管理データベースが同じサーバーに存在する場合、ASP.NET ワーカー プロセスまたは IIS アプリケーション プールのユーザー コンテキストを、ローカルの ASPNET ユーザー アカウント、または最小限の権限を持つローカルのユーザー アカウントかドメイン ユーザー アカウントに設定します。  
  
 **複数のサーバー インストールでのデータベースへのアクセス**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] および BizTalk 管理データベースが異なるサーバーに存在する場合、ASP.NET ワーカー プロセスまたは IIS アプリケーション プールのユーザー コンテキストをドメイン ユーザー アカウントに変更します。  
  
 マルチ サーバー展開を実装するときに、分離ホスト Windows グループが BizTalk データベース サーバーが属するドメインに存在する必要があります。  
  
 **アカウントの特権およびユーザー権限を最小限に抑える**  
  
 分離ホストを使用すると、外部プロセスで実行するアダプタに、BizTalk Server との連携に必要な最小限のリソースへのアクセス権が付与されます。 セキュリティで保護された展開を行うために、外部プロセスのユーザー コンテキストに最小限の権限を付与します。  
  
 **BizTalk Web サービス公開ウィザードのセキュリティに関する推奨事項**  
  
 BizTalk Web サービス公開ウィザードで作成する仮想ディレクトリは、親仮想ディレクトリまたは Web サイトからアクセス制御リスト (ACL) および認証要件を継承します。 親仮想ディレクトリまたは Web サイトへの匿名アクセスが許可されている場合、仮想ディレクトリを作成するときに、BizTalk Web サービス公開ウィザードによってその機能は削除されます。  
  
 次のトピックには、[!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)] のセキュリティに関する注意事項と推奨事項が記載されています。  
  
## <a name="next"></a>Next
  
[公開済み Web サービスの ASP.NET を有効にする方法](../core/how-to-enable-asp-net-4-0-for-published-web-services.md)