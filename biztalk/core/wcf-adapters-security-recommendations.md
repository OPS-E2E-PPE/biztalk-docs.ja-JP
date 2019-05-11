---
title: WCF アダプターのセキュリティに関する推奨事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF adapters, security
- security, WCF adapters
ms.assetid: bbaaca56-9ad5-4122-a8e9-6e975d308230
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 617d573dba56cfae8f95c6d847813f50e57f3b48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279093"
---
# <a name="wcf-adapters-security-recommendations"></a><span data-ttu-id="5b645-102">WCF アダプターのセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="5b645-102">WCF Adapters Security Recommendations</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="5b645-103">は、WCF アダプターを使用して WCF サービスを公開 (受信) および使用 (送信) します。</span><span class="sxs-lookup"><span data-stu-id="5b645-103">uses the WCF adapters to publish (receive) and consume (send) WCF services.</span></span> <span data-ttu-id="5b645-104">使用している環境内において WCF アダプターをセキュリティで保護して展開するには、次のガイドラインに従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5b645-104">We recommend that you follow these guidelines for securing and deploying the WCF adapters in your environment.</span></span>  
  
 <span data-ttu-id="5b645-105">WCF アダプターに関する詳細については、次を参照してください。 [WCF アダプタ](../core/wcf-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="5b645-105">For more information about the WCF adapters, see [WCF Adapters](../core/wcf-adapters.md).</span></span> <span data-ttu-id="5b645-106">WCF サービスの詳細については、次を参照してください。 [WCF サービスを使用する](../core/using-wcf-services.md)秒。</span><span class="sxs-lookup"><span data-stu-id="5b645-106">For more information about WCF services, see [Using WCF Services](../core/using-wcf-services.md)s.</span></span>  
  
## <a name="security-recommendations-for-all-wcf-adapters"></a><span data-ttu-id="5b645-107">すべての WCF アダプターのセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="5b645-107">Security Recommendations for All WCF Adapters</span></span>  
  
-   <span data-ttu-id="5b645-108">フロントエンド ユーザーのコンテンツをバックエンド システムの資格情報にマップする必要がある場合、エンタープライズ シングル サインオン (SSO) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5b645-108">You can use Enterprise Single Sign-On (SSO) in scenarios where you need to map the content of the front-end user to credentials in a back-end system.</span></span>  
  
-   <span data-ttu-id="5b645-109">すべてのサービスでメタデータが公開されている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5b645-109">Not all services must publish metadata.</span></span> <span data-ttu-id="5b645-110">メタデータの公開を無効のままにすることで、サービスの攻撃対象領域が減り、意図しない情報公開の危険性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="5b645-110">Leaving metadata publishing disabled reduces the attack surface for your service and lowers the risk of unintentional information disclosure.</span></span> <span data-ttu-id="5b645-111">メタデータに関連するセキュリティの問題に関する詳細についてにある「Security Considerations with Metadata」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=196671](http://go.microsoft.com/fwlink/?LinkId=196671)します。</span><span class="sxs-lookup"><span data-stu-id="5b645-111">For more information about security issues related to metadata, see "Security Considerations with Metadata" at [http://go.microsoft.com/fwlink/?LinkId=196671](http://go.microsoft.com/fwlink/?LinkId=196671).</span></span>  
  
-   <span data-ttu-id="5b645-112">メタデータ エンドポイントのバインドとサービス エンドポイントのバインドのすべての組み合わせが有効であるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="5b645-112">Not all combinations of metadata endpoint bindings and service endpoint bindings are valid.</span></span> <span data-ttu-id="5b645-113">メタデータ エンドポイントのバインド構成がサービス エンドポイントのバインド構成と一致する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="5b645-113">In some cases, the binding configurations for a metadata endpoint must be in agreement with the binding configurations of its service endpoint.</span></span> <span data-ttu-id="5b645-114">たとえば、メタデータが受信場所と同じ場所から提供されていて、その受信場所が HTTPS に依存するセキュリティ モードを使用している場合、メタデータ エンドポイントは、HTTP トランスポートを必要とするセキュリティ モードで構成することができません。</span><span class="sxs-lookup"><span data-stu-id="5b645-114">For example, when metadata is served from the same location as the receive location, the metadata endpoint cannot be configured with a security mode requiring the HTTP transport if the receive location uses a security mode that relies on HTTPS.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5b645-115">同じ場所が、BizTalk WCF 公開ウィザードによって生成される Web.config ファイルで、HTTPS トランスポートに依存するセキュリティ モードを必要とするサービス エンドポイント、HTTP トランスポートを通じてメタデータを発行するときに、の両方を設定する必要があります。**httpsGetEnabled**と**httpGetEnabled**属性を**true**します。</span><span class="sxs-lookup"><span data-stu-id="5b645-115">When publishing metadata through the HTTP transport for a service endpoint with the same location but requiring a security mode that relies on the HTTPS transport, in the Web.config file that the BizTalk WCF Publishing Wizard generates, you must set both of the **httpsGetEnabled** and **httpGetEnabled** attributes to **true**.</span></span>  
  
-   <span data-ttu-id="5b645-116">WCF アダプターは、Windows Communication Foundation (WCF) のセキュリティ機能を利用して通信します。</span><span class="sxs-lookup"><span data-stu-id="5b645-116">The WCF adapters leverage the security features of Windows Communication Foundation (WCF) to communicate.</span></span> <span data-ttu-id="5b645-117">セキュリティの観点から WCF の機能と制限事項を理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b645-117">It is important to understand the capabilities and limitations of WCF in terms of security.</span></span> <span data-ttu-id="5b645-118">WCF のセキュリティ機能に関する詳細についてで「Windows Communication Foundation Security」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=87806](http://go.microsoft.com/fwlink/?LinkId=87806)します。</span><span class="sxs-lookup"><span data-stu-id="5b645-118">For more information about the security features of WCF, see "Windows Communication Foundation Security" at [http://go.microsoft.com/fwlink/?LinkId=87806](http://go.microsoft.com/fwlink/?LinkId=87806).</span></span>  
  
## <a name="security-recommendations-for-the-isolated-wcf-adapters"></a><span data-ttu-id="5b645-119">分離 WCF アダプターのセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="5b645-119">Security Recommendations for the Isolated WCF Adapters</span></span>  
  
- <span data-ttu-id="5b645-120">Web サービスを公開するためのセキュリティの推奨事項については、次を参照してください。 [Web サービスを有効にする](../core/enabling-web-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="5b645-120">For security recommendations for publishing Web services, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
- <span data-ttu-id="5b645-121">WCF-CustomIsolated、WCF-BasicHttp、WCF-WSHttp などの分離 WCF アダプターは、HTTP (ハイパーテキスト転送プロトコル) を利用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] との間でメッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="5b645-121">The isolated WCF adapters such as the WCF-CustomIsolated, WCF-BasicHttp, and WCF-WSHttp adapters leverage the Hypertext Transfer Protocol (HTTP) to send and receive messages to and from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="5b645-122">そのため、インターネット インフォメーション サービス (IIS) を保護するためのセキュリティの推奨事項に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b645-122">Therefore, you must follow the security recommendations for securing Internet Information Services (IIS).</span></span>  
  
- <span data-ttu-id="5b645-123">分離 WCF 受信場所にアプリケーション プールを作成する場合は、WCF 受信アダプターを実行している分離ホストの [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] グループおよびインターネット インフォメーション サービスのワーカー プロセス グループ (IIS_WPG group) のメンバーであるアカウントで実行するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b645-123">When you create an application pool for an isolated WCF receive location, you must configure it to run under an account that is a member of the [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] group for the isolated host running the WCF receive adapter and the Internet Information Services Worker Process group (IIS_WPG group).</span></span> <span data-ttu-id="5b645-124">その後、WCF 受信アダプターのホスト インスタンスを、このアカウントを使用するように構成してください。</span><span class="sxs-lookup"><span data-stu-id="5b645-124">You must then configure the host instance for the WCF receive adapter to use this account.</span></span> <span data-ttu-id="5b645-125">IIS_WPG グループのアカウントを変更する場合は、新しいアカウントで実行するようにホスト インスタンスを更新する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="5b645-125">If you change the account for the IIS_WPG group, you must ensure that you also update the host instance to run under the new account.</span></span>  
  
## <a name="security-recommendations-for-the-wcf-custom-adapter"></a><span data-ttu-id="5b645-126">WCF-Custom アダプターのセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="5b645-126">Security Recommendations for the WCF-Custom Adapter</span></span>  
  
-   <span data-ttu-id="5b645-127">HTTP カーネル モード ドライバー (HTTP.sys) を使用する場合は、Wcf-custom 受信場所、 **httpsTransport** Secure Sockets Layer (SSL) 通信、受信場所のバインド要素は、証明書が必要ソケット (IP アドレスとポートの組み合わせ) ごとに登録します。</span><span class="sxs-lookup"><span data-stu-id="5b645-127">If a WCF-Custom receive location happens to use the HTTP kernel-mode driver (HTTP.sys) such as the **httpsTransport** binding element for Secure Sockets Layer (SSL) communications, the receive location must have a certificate registered for each socket (IP address/port combination).</span></span> <span data-ttu-id="5b645-128">SSL 証明書をコンピューター上のポートにバインドするには、HttpCfg.exe ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b645-128">Use the HttpCfg.exe tool to bind an SSL certificate to a port on the computer.</span></span> <span data-ttu-id="5b645-129">詳細については、次を参照してください。"どのようにします。構成、SSL 証明書でポート" [ http://go.microsoft.com/fwlink/?LinkId=86384](http://go.microsoft.com/fwlink/?LinkId=86384)します。</span><span class="sxs-lookup"><span data-stu-id="5b645-129">For more information, see "How To: Configure a Port with An SSL Certificate" at [http://go.microsoft.com/fwlink/?LinkId=86384](http://go.microsoft.com/fwlink/?LinkId=86384).</span></span>  
  
## <a name="security-recommendations-for-the-wcf-netmsmq-adapter"></a><span data-ttu-id="5b645-130">WCF-NetMsmq アダプターのセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="5b645-130">Security Recommendations for the WCF-NetMsmq Adapter</span></span>  
  
-   <span data-ttu-id="5b645-131">Wcf-netmsmq アダプターを使用する場合と同じ方法で、Wcf-netmsmq アダプターの MSMQ セキュリティ設定を構成する必要がある、 [netMsmqBinding](http://go.microsoft.com/fwlink/?LinkId=87813)します。</span><span class="sxs-lookup"><span data-stu-id="5b645-131">To use the WCF-NetMsmq adapter, you have to configure MSMQ security settings for the WCF-NetMsmq adapter in the same way as for the [netMsmqBinding](http://go.microsoft.com/fwlink/?LinkId=87813).</span></span> <span data-ttu-id="5b645-132">MSMQ セキュリティ設定を構成する方法について、 **netMsmqBinding**、ある Troubleshooting Queued Messaging」を参照してください[ http://go.microsoft.com/fwlink/?LinkId=87816](http://go.microsoft.com/fwlink/?LinkId=87816)します。</span><span class="sxs-lookup"><span data-stu-id="5b645-132">For more information about how to configure MSMQ security settings for the **netMsmqBinding**, see "Troubleshooting Queued Messaging" at [http://go.microsoft.com/fwlink/?LinkId=87816](http://go.microsoft.com/fwlink/?LinkId=87816).</span></span>  
  
## <a name="wcf-adapters-use-the-chaintrust-mode-to-validate-certificates"></a><span data-ttu-id="5b645-133">WCF アダプターでの ChainTrust モードを使用した証明書の検証</span><span class="sxs-lookup"><span data-stu-id="5b645-133">WCF Adapters Use the ChainTrust Mode to Validate Certificates.</span></span>  
  
-   <span data-ttu-id="5b645-134">標準の WCF 受信アダプターを使用しているため、 [ChainTrust](http://go.microsoft.com/fwlink/?LinkId=88960)モード クライアントとサービスの証明書を検証する X.509 証明書を検証する CA 証明書チェーンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b645-134">Because the standard WCF receive adapters use the [ChainTrust](http://go.microsoft.com/fwlink/?LinkId=88960) mode to validate the client and service certificates, you must install the CA certificate chain to validate the X.509 certificates.</span></span> <span data-ttu-id="5b645-135">WCF-Custom アダプターまたは WCF-CustomIsolated アダプターを使用すると、この既定の動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="5b645-135">You can use the WCF-Custom or the WCF-CustomIsolated adapter to change this default behavior.</span></span>  
  
## <a name="security-auditing-for-the-wcf-adapters"></a><span data-ttu-id="5b645-136">WCF アダプターのセキュリティ監査</span><span class="sxs-lookup"><span data-stu-id="5b645-136">Security Auditing for the WCF Adapters</span></span>  
  
- <span data-ttu-id="5b645-137">既定では、WCF アダプターは WCF セキュリティ監査機能を使用しません。</span><span class="sxs-lookup"><span data-stu-id="5b645-137">The WCF adapters do not use the WCF security auditing features by default.</span></span> <span data-ttu-id="5b645-138">WCF アダプターの WCF セキュリティ監査機能を有効にするには、複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="5b645-138">There are several ways to enable the WCF security auditing features for the WCF adapters.</span></span> <span data-ttu-id="5b645-139">WCF セキュリティ監査機能の詳細についてを参照してください「セキュリティ イベントを監査」 [ http://go.microsoft.com/fwlink/?LinkId=88975](http://go.microsoft.com/fwlink/?LinkId=88975)します。</span><span class="sxs-lookup"><span data-stu-id="5b645-139">For more information about the WCF security auditing features, see "Auditing Security Events" at [http://go.microsoft.com/fwlink/?LinkId=88975](http://go.microsoft.com/fwlink/?LinkId=88975).</span></span>  
  
- <span data-ttu-id="5b645-140">WCF セキュリティ監査の Wcf-custom 受信アダプターを使用した機能を使用することができます、 **ServiceSecurityAuditBehavior**の受信場所。</span><span class="sxs-lookup"><span data-stu-id="5b645-140">To use the WCF security auditing features with the WCF-Custom receive adapter, you can configure the **ServiceSecurityAuditBehavior** for the receive locations.</span></span>  
  
- <span data-ttu-id="5b645-141">インプロセス WCF アダプターの場合、パフォーマンス カウンターは BTSNTSvc.exe.config ファイルを使用して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5b645-141">For the in-process WCF adapters, you can enable the performance counters through the BTSNTSvc.exe.config file.</span></span> <span data-ttu-id="5b645-142">分離 WCF アダプターの場合は、BizTalk WCF サービス公開ウィザードによって Web アプリケーション フォルダーに作成される Web.config ファイルを変更して WCF 追跡を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5b645-142">For the isolated WCF adapters, you can enable WCF tracing by modifying the Web.config file that the BizTalk WCF Service Publishing Wizard creates in the Web application folder.</span></span> <span data-ttu-id="5b645-143">BTSNtSvc.exe.config または Web.config を変更するには、構成ファイルを開き、次の構成例に示すように WCF 追跡を構成します。</span><span class="sxs-lookup"><span data-stu-id="5b645-143">To modify BTSNtSvc.exe.config or Web.config, open the configuration file, and then configure WCF tracing, as indicated in the following configuration example:</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="5b645-144">BTSNTSvc.exe.config ファイルは常に BTSNTSvc.exe ファイルと同じディレクトリ (通常は [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]) に配置されます。</span><span class="sxs-lookup"><span data-stu-id="5b645-144">The BTSNTSvc.exe.config file is always located in the same directory as the BTSNTSvc.exe file, which is usually [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  > 
  > [!NOTE]
  >  <span data-ttu-id="5b645-145">BTSNTSvc.exe.config ファイルを変更した後、インプロセス WCF 受信場所を実行するホスト インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b645-145">After modifying the BTSNTSvc.exe.config file, you must restart the host instances running the in-process WCF receive locations.</span></span>  
  
  ```  
  <configuration>  
      <system.serviceModel>  
        <diagnostics performanceCounters="All" />  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="ServiceBehaviorConfiguration">  
              <serviceSecurityAudit  
                        auditLogLocation="Application"  
                        suppressAuditFailure="true"  
                        serviceAuthorizationAuditLevel="SuccessOrFailure"  
  messageAuthenticationAuditLevel="SuccessOrFailure" />  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
        <services>  
          <service name="Microsoft.BizTalk.Adapter.Wcf.Runtime.BizTalkServiceInstance" behaviorConfiguration="ServiceBehaviorConfiguration">  
          </service>  
        </services>        
      </system.serviceModel>  
  </configuration>  
  ```  
  
- <span data-ttu-id="5b645-146">さらに、"承認されていないセキュリティ呼び出し" などのセキュリティ関連のパフォーマンス カウンターを使用して WCF アダプターを監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="5b645-146">You can also use a security-related performance counter such as Security Calls Not Authorized to monitor the WCF adapters.</span></span> <span data-ttu-id="5b645-147">WCF パフォーマンス カウンタを有効にする方法の詳細については、次を参照してください。 [WCF アダプターのパフォーマンス カウンター](../core/wcf-adapters-performance-counters.md)します。</span><span class="sxs-lookup"><span data-stu-id="5b645-147">For more information about how to enable the WCF performance counters, see [WCF Adapters Performance Counters](../core/wcf-adapters-performance-counters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b645-148">参照</span><span class="sxs-lookup"><span data-stu-id="5b645-148">See Also</span></span>  
 [<span data-ttu-id="5b645-149">セキュリティの計画</span><span class="sxs-lookup"><span data-stu-id="5b645-149">Planning for Security</span></span>](../core/planning-for-security.md)