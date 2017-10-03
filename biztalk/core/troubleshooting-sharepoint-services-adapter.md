---
title: "トラブルシューティング SharePoint Services アダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77f88174-118d-4ed6-8449-c89ca195ce5c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f9885696df24cd5c5f8321ad3c6dd79d444559a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-sharepoint-services-adapter"></a>SharePoint Services アダプターのトラブルシューティング
このトピックでは、[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS) アダプターのトラブルシューティングについて説明します。  
  
## <a name="installation"></a>インストール  
 [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS) アダプターを使用するときは、2 つのオプションがあります。  
  
|||  
|-|-|  
|**クライアント OM を使用して**'éý'**はい**です。|**推奨**。 [はい] に設定すると、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] のクライアント側オブジェクト モデル (CSOM) が使用されます。 このアダプターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストール時にインストールされます。 追加のインストール手順はありません。 **注:** 、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]も自動的にインストール、SharePoint クライアント オブジェクト モデル再頒布可能パッケージで使用可能な[http://go.microsoft.com/fwlink/p/?LinkId=263482](http://go.microsoft.com/fwlink/p/?LinkId=263482)です。|  
|**クライアント OM を使用して**'éý'**いいえ**です。|**使用しません**。 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] サービス側オブジェクト モデル (SSOM) を使用します。<br /><br /> Web サービスが [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] コンピューターにインストールされます。このコンピューターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のコンピューターと同じでも別でもかまいません。<br /><br /> Web サービスをインストールするには、実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]へのインストール、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]コンピューターとチェック**Windows SharePoint Services アダプター**です。 参照してください[付録 b: Microsoft SharePoint アダプターをインストールして](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)固有のインストール手順についてはします。|  
  
 **クライアント OM を使用して**'éý'**はい**をお勧めします。 設定すると**はい**、web サービスが SharePoint コンピューターにインストールされていません。 Web サービス オプションを使用する場合は、設定する必要があります**クライアント OM を使用して**に**いいえ**上、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
## <a name="iis"></a>IIS  
 **BTSharePointAdapterWS.asmx web サービス**  
  
 [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] アダプターが SharePoint コンピューターにインストールされると、BTSharePointAdapterWS.asmx Web サービスが SharePoint コンピューターの IIS に作成されます。 通常、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と SharePoint は異なるコンピューターにインストールされます。 SharePoint がインストールされるとき、コンテンツ SQL データベースは SharePoint コンピューターのローカルにあっても、リモート [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] に存在していてもかまいません。  
  
 **アプリケーション プール ドメイン アカウントを使用してください。**  
  
 BizTalk と SharePoint が異なるコンピューター上にある場合は、BTSharePointAdapterWS.asmx Web サービスを実行する IIS アプリケーション プールは、ドメイン アカウントを使用する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、BizTalk データベース、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]、および [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] SharePoint データベースがすべて同じコンピューターにインストールされている場合は、ローカル アカウントを使用できます。  
  
 **ダブル ホップ シナリオ**  
  
 3 台のコンピューターが使用される場合は ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)])、Kerberos 認証を必要とするダブル ホップ シナリオになります。 BizTalk コンピューター上の SharePoint アダプターは、SharePoint コンピューター上の BTSharePointAdapterWS.asmx Web サービスに対して POST 要求を行います。 その後、SharePoint コンピューターは [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] コンピューター上のデータベースにクエリを行います。  
  
 BizTalk アダプターからのこの POST 要求は正常に完了する必要があります。 認証の失敗の疑いがある場合は、IIS ログを確認してください。 既定では、IIS ログは c:\inetpub\logs\LogFiles\W3SVC*x*です。 POST 要求では、ステータス コード 200 (成功) が表示される必要があります。 かどうか、失敗のステータス コードが返されます、401.1、別の 4 で続けて、401.2 と同様に*xx*エラー、し、認証が失敗する可能性があります。  
  
 Kerberos 認証を使用する場合は、サービス プリンシパル名 (SPN) が必要で、委任を有効にする必要があります。  
  
## <a name="enable-kerberos-authentication"></a>Kerberos 認証を有効にする  
 ダブル ホップのシナリオでは、Kerberos 認証と委任を有効にする必要があります。 次の手順で行います。  
  
1.  有効にする**Negotiate** Iis/sharepoint サーバーでします。 [215383: ネットワークの認証に Kerberos プロトコルと NTLM プロトコルの両方をサポートするために IIS を構成する方法](http://support.microsoft.com/kb/215383)手順について説明します。  
  
2.  ドメイン アカウントが IIS/SharePoint コンピューターで [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] サービスとアプリケーション プールを実行するには、サービス プリンシパル名 (SPN) が必要です。 SPN を作成するには、SetSPN.exe コマンド ライン ツールを使用します。  
  
     [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]: [Windows Server 2003 での Setspn.exe の更新プログラムがあります。](http://support.microsoft.com/kb/970536)  
  
     [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]8、 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]と[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]: [SetSPN](http://technet.microsoft.com/library/cc731241.aspx)  
  
    > [!IMPORTANT]
    >  SetSPN にはドメイン管理者権限が必要です。SetSPN はドメイン内の任意のコンピューターで実行できます。  
  
     ドメイン アカウントに登録されているすべての SPN の一覧を取得するには:  
  
    ```  
    setspn.exe -l Domain\UserAccount  
    ```  
  
     SPN を作成します。  
  
    1.  IIS/SharePoint コンピューターの FQDN の SPN を作成します。  
  
        ```  
        setspn.exe -s http/IISSharePointComputerName.domain.com domain\IISApplicationPoolDomainAccount  
        ```  
  
    2.  IIS/SharePoint コンピューターの NETBIOS 名の SPN を作成します。  
  
        ```  
        setspn.exe -s http/IISSharePointComputerNamedomain\IISApplicationPoolDomainAccount  
        ```  
  
    3.  IIS/SharePoint コンピューターによって使用される SQL Server コンピューターの FQDN の SPN を作成します。  
  
        ```  
        setspn.exe -s mssqlsvc/SQLComputerName.domain.com domain\SQLServerServiceDomainAccount  
        ```  
  
    4.  IIS/SharePoint コンピューターによって使用される SQL Server コンピューターの FQDN および TCP ポートの SPN を作成します。  
  
        ```  
        setspn.exe -s mssqlsvc/SQLComputerName.domain.com:1433 domain\SQLServerServiceDomainAccount  
        ```  
  
    5.  IIS/SharePoint コンピューターによって使用される SQL Server コンピューターの NETBIOS 名の SPN を作成します。  
  
        ```  
        setspn.exe -s mssqlsvc/SQLComputerNamedomain\SQLServerServiceDomainAccount  
        ```  
  
    6.  IIS/SharePoint コンピューターによって使用される SQL Server コンピューターの NETBIOS 名:TCP ポートの SPN を作成します。  
  
        ```  
        setspn.exe -s mssqlsvc/SQLComputerName:1433 domain\SQLServerServiceDomainAccount  
        ```  
  
3.  ドメイン コント ローラー上に移動**Active Directory ユーザーとコンピューター**し、次の操作を行います。  
  
    1.  確認**任意のサービスへの委任に対して信頼**の次のコンピューター。  
  
        -   SharePoint/IIS サーバー  
  
        -   SharePoint によって使用される SQL Server  
  
    2.  確認**のアカウントが信頼された委任**をオフにし、**アカウントは重要なので委任できない**次のドメイン アカウント。  
  
        -   SQL Server サービス ドメイン アカウント  
  
        -   IIS アプリケーション プール ドメイン アカウント  
  
 追加のトラブルシューティングについてを参照してください[Windows SharePoint Services アダプターのトラブルシューティング](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)  
  
## <a name="see-also"></a>参照  
 [SharePoint を構成する受信場所のサービス](../core/configure-sharepoint-services-receive-location.md)   
 [SharePoint Services 送信ポートを構成します。](../core/configure-sharepoint-services-send-port.md)   
 [SharePoint Services アダプターの CSOM:](../core/csom-sharepoint-services-adapter.md)