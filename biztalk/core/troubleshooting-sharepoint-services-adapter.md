---
title: トラブルシューティングの SharePoint Services アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77f88174-118d-4ed6-8449-c89ca195ce5c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1f3c4e3740d2fb73cde2cc71426e109f7534fa7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306487"
---
# <a name="troubleshooting-sharepoint-services-adapter"></a>SharePoint Services アダプターのトラブルシューティング
このトピックの「トラブルシューティングについて説明、 [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS) アダプター。  

## <a name="installation"></a>インストール  
 使用する場合、 [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS) アダプターの場合は、2 つのオプションがあります。  


|                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|-----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **クライアント OM を使用して、** 設定**はい**します。 |                                                                                                                                     **推奨**します。 [はい] に設定すると、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]クライアント側オブジェクト モデル (CSOM) を使用します。 このアダプターは、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストール時にインストールされます。 追加のインストール手順はありません。 **注:**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールも自動的にインストール、SharePoint クライアント オブジェクト モデル再頒布可能パッケージで使用可能な[ http://go.microsoft.com/fwlink/p/?LinkId=263482](http://go.microsoft.com/fwlink/p/?LinkId=263482)します。                                                                                                                                     |
| **クライアント OM を使用して、** 設定**いいえ**します。  | **非推奨**。 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] サービス側オブジェクト モデル (SSOM) を使用します。<br /><br /> Web サービスがインストールされている、 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 、コンピューターと同じコンピューター上にあることができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]または別のコンピューター。<br /><br /> Web サービスをインストールするには、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストールを [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] コンピューターで実行し、**[Windows SharePoint Services アダプター]** をオンにします。 参照してください[付録 b:Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)固有のインストール手順についてはします。 |

 **クライアント OM を使用して、** に設定**はい**をお勧めします。 設定すると**はい**、web サービスが SharePoint コンピューターにインストールされていません。 設定する必要があります web サービスのオプションを使用する場合は、**クライアント OM を使用して**に**いいえ**上、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  

## <a name="iis"></a>IIS  
 **BTSharePointAdapterWS.asmx web サービス**  

 ときに、[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]アダプターが SharePoint コンピューターにインストールされている、SharePoint コンピューターで、BTSharePointAdapterWS.asmx web サービスが IIS で作成されます。 通常、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SharePoint は別のコンピューターにインストールされているとします。 コンテンツの SQL database は、SharePoint コンピューターまたはリモート コンピューターのローカル SharePoint がインストールされているときに[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。  

 **アプリケーション プール ドメイン アカウントを使用してください。**  

 BizTalk と SharePoint が異なるコンピューター上にある場合は、BTSharePointAdapterWS.asmx web サービスを実行する IIS アプリケーション プールは、ドメイン アカウントを使用する必要があります。 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、BizTalk データベース、 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] SharePoint データベースはすべて、同じコンピューターにインストールし、ローカル アカウントを使用できます。  

 **ダブル ホップ シナリオ**  

 関連する 3 台のコンピューターがある場合 ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)])、Kerberos 認証を必要とするダブル ホップ シナリオがあります。 BizTalk コンピューター上の SharePoint アダプターは、SharePoint コンピューター上の BTSharePointAdapterWS.asmx web サービスへの POST 要求です。 SharePoint コンピューターでそのデータベースを照会し、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  

 BizTalk アダプターからこの POST 要求が正常に完了する必要があります。 認証の失敗を疑いがある場合は、IIS ログを確認します。 既定では、IIS ログは c:\inetpub\logs\logfiles\w3svc*x*します。 POST 要求は、200 (成功) を表示する状態コード。 かどうか失敗のステータス コードが返された後に 401.1、別の 4、401.2*xx*エラー、し、認証が失敗する可能性があります。  

 Kerberos 認証を使用するとサービス プリンシパル名 (SPN) が必要な委任を有効にする必要があります。  

## <a name="enable-kerberos-authentication"></a>Kerberos 認証を有効にします。  
 ダブル ホップ シナリオで Kerberos 認証と有効にする委任が必要です。 手順は次のとおりです。  

1. 有効にする**ネゴシエート**Iis/sharepoint サーバーでします。 [215383:ネットワーク認証のため、Kerberos プロトコルと NTLM プロトコルの両方をサポートするために IIS を構成する方法](http://support.microsoft.com/kb/215383)の手順を示します。  

2. サービス プリンシパル名 (Spn) を実行するドメイン アカウントに必要な[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]サービスと Iis/sharepoint コンピューターのアプリケーション プール。 SPN を作成するには、SetSPN.exe コマンドライン ツールを使用します。  

    [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]:[Windows Server 2003 での Setspn.exe の更新プログラムがあります。](http://support.microsoft.com/kb/970536)  

    [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] 8 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]と[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]:[SetSPN](http://technet.microsoft.com/library/cc731241.aspx)  

   > [!IMPORTANT]
   >  SetSPN はドメイン管理者権限が必要し、ドメイン内のコンピューターから実行できます。  

    ドメイン アカウントに登録されているすべての Spn の一覧が返されます。  

   ```  
   setspn.exe -l Domain\UserAccount  
   ```  

    Spn を作成します。  

   1.  Iis/sharepoint コンピューターの FQDN の SPN を作成します。  

       ```  
       setspn.exe -s http/IISSharePointComputerName.domain.com domain\IISApplicationPoolDomainAccount  
       ```  

   2.  Iis/sharepoint コンピューターの NETBIOS 名の SPN を作成します。  

       ```  
       setspn.exe -s http/IISSharePointComputerNamedomain\IISApplicationPoolDomainAccount  
       ```  

   3.  Iis/sharepoint コンピューターによって使用される SQL Server コンピューターの FQDN の SPN を作成します。  

       ```  
       setspn.exe -s mssqlsvc/SQLComputerName.domain.com domain\SQLServerServiceDomainAccount  
       ```  

   4.  FQDN と Iis/sharepoint コンピューターによって使用される SQL Server コンピューターの TCP ポートの SPN を作成します。  

       ```  
       setspn.exe -s mssqlsvc/SQLComputerName.domain.com:1433 domain\SQLServerServiceDomainAccount  
       ```  

   5.  Iis/sharepoint コンピューターによって使用される SQL Server コンピューターの NETBIOS 名の SPN を作成します。  

       ```  
       setspn.exe -s mssqlsvc/SQLComputerNamedomain\SQLServerServiceDomainAccount  
       ```  

   6.  Iis/sharepoint コンピューターによって使用される SQL Server コンピューターの NETBIOS 名:TCP ポートの SPN を作成します。  

       ```  
       setspn.exe -s mssqlsvc/SQLComputerName:1433 domain\SQLServerServiceDomainAccount  
       ```  

3. ドメイン コント ローラー上に移動**Active Directory ユーザーとコンピューター**次の操作を行います。  

   1.  確認**任意のサービスへの委任でこのコンピューターを信頼**次のコンピューター。  

       -   SHAREPOINT/IIS サーバー  

       -   SharePoint で使用される SQL Server  

   2.  確認**のアカウントが信頼された委任**をオフにし、**アカウントは重要なので委任できない**次のドメイン アカウント。  

       -   SQL Server サービスのドメイン アカウント  

       -   IIS アプリケーション プール ドメイン アカウント  

   その他のトラブルシューティングを参照してください[Windows SharePoint Services アダプターのトラブルシューティング](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)  

## <a name="see-also"></a>参照  
 [SharePoint を構成する受信場所のサービス](../core/configure-sharepoint-services-receive-location.md)   
 [SharePoint Services 送信ポートを構成します。](../core/configure-sharepoint-services-send-port.md)   
 [CSOM:SharePoint Services アダプター](../core/csom-sharepoint-services-adapter.md)