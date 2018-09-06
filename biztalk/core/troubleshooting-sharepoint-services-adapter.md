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
ms.openlocfilehash: a3bc6cb2d7569e7d1ee0c8816bafa91151294df7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979315"
---
# <a name="troubleshooting-sharepoint-services-adapter"></a><span data-ttu-id="535e4-102">SharePoint Services アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="535e4-102">Troubleshooting SharePoint Services Adapter</span></span>
<span data-ttu-id="535e4-103">このトピックでは、[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS) アダプターのトラブルシューティングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="535e4-103">This topic focuses on troubleshooting the [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS) adapter.</span></span>  

## <a name="installation"></a><span data-ttu-id="535e4-104">インストール</span><span class="sxs-lookup"><span data-stu-id="535e4-104">Installation</span></span>  
 <span data-ttu-id="535e4-105">[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS) アダプターを使用するときは、2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="535e4-105">When using the [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS) adapter, there are two options:</span></span>  


|                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|-----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="535e4-106">**クライアント OM を使用して、** 設定**はい**します。</span><span class="sxs-lookup"><span data-stu-id="535e4-106">**Use Client OM** set to **Yes**.</span></span> |                                                                                                                                     <span data-ttu-id="535e4-107">**推奨**。</span><span class="sxs-lookup"><span data-stu-id="535e4-107">**Recommended**.</span></span> <span data-ttu-id="535e4-108">[はい] に設定すると、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] のクライアント側オブジェクト モデル (CSOM) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="535e4-108">When set to Yes, the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Client Side Object Model (CSOM) is used.</span></span> <span data-ttu-id="535e4-109">このアダプターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストール時にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="535e4-109">The adapter is installed when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed.</span></span> <span data-ttu-id="535e4-110">追加のインストール手順はありません。</span><span class="sxs-lookup"><span data-stu-id="535e4-110">There are no additional installation steps.</span></span> <span data-ttu-id="535e4-111">**注:** 、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールも自動的にインストール、SharePoint クライアント オブジェクト モデル再頒布可能パッケージで使用可能な[ http://go.microsoft.com/fwlink/p/?LinkId=263482](http://go.microsoft.com/fwlink/p/?LinkId=263482)します。</span><span class="sxs-lookup"><span data-stu-id="535e4-111">**Note:**  The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation also automatically installs the SharePoint Client Object Model Redistributable available at [http://go.microsoft.com/fwlink/p/?LinkId=263482](http://go.microsoft.com/fwlink/p/?LinkId=263482).</span></span>                                                                                                                                     |
| <span data-ttu-id="535e4-112">**クライアント OM を使用して、** 設定**いいえ**します。</span><span class="sxs-lookup"><span data-stu-id="535e4-112">**Use Client OM** set to **No**.</span></span>  | <span data-ttu-id="535e4-113">**非推奨**。</span><span class="sxs-lookup"><span data-stu-id="535e4-113">**Deprecated**.</span></span> <span data-ttu-id="535e4-114">[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] サービス側オブジェクト モデル (SSOM) を使用します。</span><span class="sxs-lookup"><span data-stu-id="535e4-114">Uses the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Service Side Object Model (SSOM).</span></span><br /><br /> <span data-ttu-id="535e4-115">Web サービスが [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] コンピューターにインストールされます。このコンピューターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のコンピューターと同じでも別でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="535e4-115">A web service is installed on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] computer, which can be on the same computer as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or a separate computer.</span></span><br /><br /> <span data-ttu-id="535e4-116">Web サービスをインストールするには、実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]へのインストール、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]コンピューターとチェック**Windows SharePoint Services アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="535e4-116">To install the web service, run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] computer and check **Windows SharePoint Services Adapter**.</span></span> <span data-ttu-id="535e4-117">参照してください[付録 b: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)固有のインストール手順についてはします。</span><span class="sxs-lookup"><span data-stu-id="535e4-117">See [Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) for specific installation steps.</span></span> |

 <span data-ttu-id="535e4-118">**クライアント OM を使用して、** に設定**はい**をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="535e4-118">**Use Client OM** set to **Yes** is recommended.</span></span> <span data-ttu-id="535e4-119">設定すると**はい**、web サービスが SharePoint コンピューターにインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="535e4-119">When set to **Yes**, the web service is NOT installed on the SharePoint computer.</span></span> <span data-ttu-id="535e4-120">設定する必要があります web サービスのオプションを使用する場合は、**クライアント OM を使用して**に**いいえ**上、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="535e4-120">If you prefer to use the web service option, you must set **Use Client OM** to **No** on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

## <a name="iis"></a><span data-ttu-id="535e4-121">IIS</span><span class="sxs-lookup"><span data-stu-id="535e4-121">IIS</span></span>  
 <span data-ttu-id="535e4-122">**BTSharePointAdapterWS.asmx web サービス**</span><span class="sxs-lookup"><span data-stu-id="535e4-122">**BTSharePointAdapterWS.asmx web service**</span></span>  

 <span data-ttu-id="535e4-123">[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] アダプターが SharePoint コンピューターにインストールされると、BTSharePointAdapterWS.asmx Web サービスが SharePoint コンピューターの IIS に作成されます。</span><span class="sxs-lookup"><span data-stu-id="535e4-123">When the [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] adapter is installed on the SharePoint computer, the BTSharePointAdapterWS.asmx web service is created in IIS on the SharePoint computer.</span></span> <span data-ttu-id="535e4-124">通常、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と SharePoint は異なるコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="535e4-124">Typically, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SharePoint are installed on different computers.</span></span> <span data-ttu-id="535e4-125">SharePoint がインストールされるとき、コンテンツ SQL データベースは SharePoint コンピューターのローカルにあっても、リモート [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] に存在していてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="535e4-125">When SharePoint is installed, the content SQL database can be local to the SharePoint computer or on a remote [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  

 <span data-ttu-id="535e4-126">**アプリケーション プール ドメイン アカウントを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="535e4-126">**Application Pool uses Domain account**</span></span>  

 <span data-ttu-id="535e4-127">BizTalk と SharePoint が異なるコンピューター上にある場合は、BTSharePointAdapterWS.asmx Web サービスを実行する IIS アプリケーション プールは、ドメイン アカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="535e4-127">When BizTalk and SharePoint are on different computers, the IIS application pool running the BTSharePointAdapterWS.asmx web service must use a domain account.</span></span> <span data-ttu-id="535e4-128">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、BizTalk データベース、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]、および [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] SharePoint データベースがすべて同じコンピューターにインストールされている場合は、ローカル アカウントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="535e4-128">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the BizTalk databases, [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] and the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] SharePoint databases are all installed on the same computer, then a local account can be used.</span></span>  

 <span data-ttu-id="535e4-129">**ダブル ホップ シナリオ**</span><span class="sxs-lookup"><span data-stu-id="535e4-129">**Double-Hop Scenario**</span></span>  

 <span data-ttu-id="535e4-130">3 台のコンピューターが使用される場合は ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)])、Kerberos 認証を必要とするダブル ホップ シナリオになります。</span><span class="sxs-lookup"><span data-stu-id="535e4-130">When there are three computers involved ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]), there is a double-hop scenario that requires Kerberos authentication.</span></span> <span data-ttu-id="535e4-131">BizTalk コンピューター上の SharePoint アダプターは、SharePoint コンピューター上の BTSharePointAdapterWS.asmx Web サービスに対して POST 要求を行います。</span><span class="sxs-lookup"><span data-stu-id="535e4-131">The SharePoint adapter on the BizTalk computer does a POST request to the BTSharePointAdapterWS.asmx web service on the SharePoint computer.</span></span> <span data-ttu-id="535e4-132">その後、SharePoint コンピューターは [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] コンピューター上のデータベースにクエリを行います。</span><span class="sxs-lookup"><span data-stu-id="535e4-132">The SharePoint computer then queries its databases on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  

 <span data-ttu-id="535e4-133">BizTalk アダプターからのこの POST 要求は正常に完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="535e4-133">This POST request from the BizTalk adapter must complete successfully.</span></span> <span data-ttu-id="535e4-134">認証の失敗の疑いがある場合は、IIS ログを確認してください。</span><span class="sxs-lookup"><span data-stu-id="535e4-134">If you suspect an authentication failure, review the IIS logs.</span></span> <span data-ttu-id="535e4-135">既定では、IIS ログは c:\inetpub\logs\logfiles\w3svc*x*します。</span><span class="sxs-lookup"><span data-stu-id="535e4-135">By default, the IIS logs are in c:\inetpub\logs\LogFiles\W3SVC*x*.</span></span> <span data-ttu-id="535e4-136">POST 要求では、ステータス コード 200 (成功) が表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="535e4-136">The POST request should display a 200 (success) status code.</span></span> <span data-ttu-id="535e4-137">かどうか失敗のステータス コードが返された後に 401.1、別の 4、401.2*xx*エラー、し、認証が失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="535e4-137">If a failed status code is returned, like a 401.2, followed by a 401.1, following by another 4*xx* error, then authentication may be failing.</span></span>  

 <span data-ttu-id="535e4-138">Kerberos 認証を使用する場合は、サービス プリンシパル名 (SPN) が必要で、委任を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="535e4-138">When Kerberos authentication is used, service principal names (SPN) are required and delegation must be enabled.</span></span>  

## <a name="enable-kerberos-authentication"></a><span data-ttu-id="535e4-139">Kerberos 認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="535e4-139">Enable Kerberos Authentication</span></span>  
 <span data-ttu-id="535e4-140">ダブル ホップのシナリオでは、Kerberos 認証と委任を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="535e4-140">In a double-hop scenario, Kerberos authentication and enabling delegation are required.</span></span> <span data-ttu-id="535e4-141">次の手順で行います。</span><span class="sxs-lookup"><span data-stu-id="535e4-141">Steps include:</span></span>  

1. <span data-ttu-id="535e4-142">有効にする**ネゴシエート**Iis/sharepoint サーバーでします。</span><span class="sxs-lookup"><span data-stu-id="535e4-142">Enable **Negotiate** on the IIS/SharePoint server.</span></span> <span data-ttu-id="535e4-143">[215383: ネットワーク認証のため、Kerberos プロトコルと NTLM プロトコルの両方をサポートするために IIS を構成する方法](http://support.microsoft.com/kb/215383)の手順を示します。</span><span class="sxs-lookup"><span data-stu-id="535e4-143">[215383: How to configure IIS to support both the Kerberos protocol and the NTLM protocol for network authentication](http://support.microsoft.com/kb/215383) lists the steps.</span></span>  

2. <span data-ttu-id="535e4-144">ドメイン アカウントが IIS/SharePoint コンピューターで [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] サービスとアプリケーション プールを実行するには、サービス プリンシパル名 (SPN) が必要です。</span><span class="sxs-lookup"><span data-stu-id="535e4-144">Service Principal Names (SPNs) are required for the domain accounts executing the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Service and the Application Pool on the IIS/SharePoint computer.</span></span> <span data-ttu-id="535e4-145">SPN を作成するには、SetSPN.exe コマンド ライン ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="535e4-145">To create an SPN, use the SetSPN.exe command-line tool:</span></span>  

    [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]<span data-ttu-id="535e4-146">: [Windows Server 2003 での Setspn.exe の更新プログラムがあります。](http://support.microsoft.com/kb/970536)</span><span class="sxs-lookup"><span data-stu-id="535e4-146">: [An update for Setspn.exe in Windows Server 2003 is available](http://support.microsoft.com/kb/970536)</span></span>  

    [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]<span data-ttu-id="535e4-147"> 8 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]と[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]: [SetSPN](http://technet.microsoft.com/library/cc731241.aspx)</span><span class="sxs-lookup"><span data-stu-id="535e4-147"> 8, [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] and [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]: [SetSPN](http://technet.microsoft.com/library/cc731241.aspx)</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="535e4-148">SetSPN にはドメイン管理者権限が必要です。SetSPN はドメイン内の任意のコンピューターで実行できます。</span><span class="sxs-lookup"><span data-stu-id="535e4-148">SetSPN requires Domain Administrator rights and can be executed from any computer in the domain.</span></span>  

    <span data-ttu-id="535e4-149">ドメイン アカウントに登録されているすべての SPN の一覧を取得するには:</span><span class="sxs-lookup"><span data-stu-id="535e4-149">To return a list of all SPNs registered to a domain account:</span></span>  

   ```  
   setspn.exe -l Domain\UserAccount  
   ```  

    <span data-ttu-id="535e4-150">SPN を作成します。</span><span class="sxs-lookup"><span data-stu-id="535e4-150">Create the SPNs:</span></span>  

   1.  <span data-ttu-id="535e4-151">IIS/SharePoint コンピューターの FQDN の SPN を作成します。</span><span class="sxs-lookup"><span data-stu-id="535e4-151">Create an SPN for the FQDN of the IIS/SharePoint computer:</span></span>  

       ```  
       setspn.exe -s http/IISSharePointComputerName.domain.com domain\IISApplicationPoolDomainAccount  
       ```  

   2.  <span data-ttu-id="535e4-152">IIS/SharePoint コンピューターの NETBIOS 名の SPN を作成します。</span><span class="sxs-lookup"><span data-stu-id="535e4-152">Create an SPN for the NETBIOS name of the IIS/SharePoint computer:</span></span>  

       ```  
       setspn.exe -s http/IISSharePointComputerNamedomain\IISApplicationPoolDomainAccount  
       ```  

   3.  <span data-ttu-id="535e4-153">IIS/SharePoint コンピューターによって使用される SQL Server コンピューターの FQDN の SPN を作成します。</span><span class="sxs-lookup"><span data-stu-id="535e4-153">Create an SPN for the FQDN of the SQL Server computer used by the IIS/SharePoint computer:</span></span>  

       ```  
       setspn.exe -s mssqlsvc/SQLComputerName.domain.com domain\SQLServerServiceDomainAccount  
       ```  

   4.  <span data-ttu-id="535e4-154">IIS/SharePoint コンピューターによって使用される SQL Server コンピューターの FQDN および TCP ポートの SPN を作成します。</span><span class="sxs-lookup"><span data-stu-id="535e4-154">Create an SPN for the FQDN and TCP Port of the SQL Server computer used by the IIS/SharePoint computer:</span></span>  

       ```  
       setspn.exe -s mssqlsvc/SQLComputerName.domain.com:1433 domain\SQLServerServiceDomainAccount  
       ```  

   5.  <span data-ttu-id="535e4-155">IIS/SharePoint コンピューターによって使用される SQL Server コンピューターの NETBIOS 名の SPN を作成します。</span><span class="sxs-lookup"><span data-stu-id="535e4-155">Create an SPN for the NETBIOS name of the SQL Server computer used by the IIS/SharePoint computer:</span></span>  

       ```  
       setspn.exe -s mssqlsvc/SQLComputerNamedomain\SQLServerServiceDomainAccount  
       ```  

   6.  <span data-ttu-id="535e4-156">IIS/SharePoint コンピューターによって使用される SQL Server コンピューターの NETBIOS 名:TCP ポートの SPN を作成します。</span><span class="sxs-lookup"><span data-stu-id="535e4-156">Create an SPN for the NETBIOS name:TCP Port of the SQL Server computer used by the IIS/SharePoint computer:</span></span>  

       ```  
       setspn.exe -s mssqlsvc/SQLComputerName:1433 domain\SQLServerServiceDomainAccount  
       ```  

3. <span data-ttu-id="535e4-157">ドメイン コント ローラー上に移動**Active Directory ユーザーとコンピューター**次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="535e4-157">On the Domain controller, go to **Active Directory Users & Computers** and do the following:</span></span>  

   1.  <span data-ttu-id="535e4-158">確認**任意のサービスへの委任でこのコンピューターを信頼**次のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="535e4-158">Check **Trust this computer for delegation to any service** for the following computers:</span></span>  

       -   <span data-ttu-id="535e4-159">SharePoint/IIS サーバー</span><span class="sxs-lookup"><span data-stu-id="535e4-159">SharePoint/IIS server</span></span>  

       -   <span data-ttu-id="535e4-160">SharePoint によって使用される SQL Server</span><span class="sxs-lookup"><span data-stu-id="535e4-160">SQL Server used by SharePoint</span></span>  

   2.  <span data-ttu-id="535e4-161">確認**のアカウントが信頼された委任**をオフにし、**アカウントは重要なので委任できない**次のドメイン アカウント。</span><span class="sxs-lookup"><span data-stu-id="535e4-161">Check **Account is Trusted for Delegation** and uncheck **Account is sensitive and cannot be delegated** for the following domain accounts:</span></span>  

       -   <span data-ttu-id="535e4-162">SQL Server サービス ドメイン アカウント</span><span class="sxs-lookup"><span data-stu-id="535e4-162">SQL Server service domain account</span></span>  

       -   <span data-ttu-id="535e4-163">IIS アプリケーション プール ドメイン アカウント</span><span class="sxs-lookup"><span data-stu-id="535e4-163">IIS Application Pool domain account</span></span>  

   <span data-ttu-id="535e4-164">その他のトラブルシューティングを参照してください[Windows SharePoint Services アダプターのトラブルシューティング](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)</span><span class="sxs-lookup"><span data-stu-id="535e4-164">For additional troubleshooting, go to [Troubleshooting the Windows SharePoint Services Adapter](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)</span></span>  

## <a name="see-also"></a><span data-ttu-id="535e4-165">参照</span><span class="sxs-lookup"><span data-stu-id="535e4-165">See Also</span></span>  
 <span data-ttu-id="535e4-166">[SharePoint を構成する受信場所のサービス](../core/configure-sharepoint-services-receive-location.md) </span><span class="sxs-lookup"><span data-stu-id="535e4-166">[Configure SharePoint Services Receive Location](../core/configure-sharepoint-services-receive-location.md) </span></span>  
 <span data-ttu-id="535e4-167">[SharePoint Services 送信ポートを構成します。](../core/configure-sharepoint-services-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="535e4-167">[Configure SharePoint Services Send Port](../core/configure-sharepoint-services-send-port.md) </span></span>  
 [<span data-ttu-id="535e4-168">CSOM: SharePoint Services アダプター</span><span class="sxs-lookup"><span data-stu-id="535e4-168">CSOM: SharePoint Services Adapter</span></span>](../core/csom-sharepoint-services-adapter.md)