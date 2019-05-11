---
title: SOAP アダプターに関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3229d73-170d-42b7-bab9-12ae5f2d0fa7
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b0d27f01efee12e32d201a1a0f7ab9e686088cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329019"
---
# <a name="known-issues-with-the-soap-adapter"></a><span data-ttu-id="cf0f6-102">SOAP アダプターに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="cf0f6-102">Known Issues with the SOAP Adapter</span></span>
<span data-ttu-id="cf0f6-103">ここでは、エラー回避に役立つ情報を記載します。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="cf0f6-104">既知の問題</span><span class="sxs-lookup"><span data-stu-id="cf0f6-104">Known Issues</span></span>  
  
#### <a name="the-soap-adapter-experiences-poor-performance-or-generates-errors-under-load"></a><span data-ttu-id="cf0f6-105">SOAP アダプターのパフォーマンスの低下が発生したまたは負荷の下でエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-105">The SOAP Adapter experiences poor performance or generates errors under load</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="cf0f6-106">問題</span><span class="sxs-lookup"><span data-stu-id="cf0f6-106">Problem</span></span>  
 <span data-ttu-id="cf0f6-107">SOAP アダプターのパフォーマンスの低下が発生したまたは負荷の下でエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-107">The SOAP Adapter experiences poor performance or generates errors under load</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="cf0f6-108">原因</span><span class="sxs-lookup"><span data-stu-id="cf0f6-108">Cause</span></span>  
 <span data-ttu-id="cf0f6-109">SOAP アダプターまたは SOAP アダプターに影響する依存関係コンポーネントの既定の構成オプションが負荷の下でパフォーマンスのチューニングされないために、この問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-109">This problem occurs because the default configuration options for the SOAP adapter or for dependency components that affect the SOAP adapter are not tuned for performance under load.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="cf0f6-110">解決策</span><span class="sxs-lookup"><span data-stu-id="cf0f6-110">Resolution</span></span>  
 <span data-ttu-id="cf0f6-111">この問題を解決するには、変更の SOAP アダプターまたはトピックで説明されている依存関係コンポーネントの構成オプション[構成パラメーターを アダプターのパフォーマンスの影響を与える](../core/configuration-parameters-that-affect-adapter-performance.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-111">To resolve this problem modify the configuration options for the SOAP adapter or for the dependency components described in the topic [Configuration Parameters that Affect Adapter Performance](../core/configuration-parameters-that-affect-adapter-performance.md).</span></span>  
  
#### <a name="the-mimesmime-encoder-and-decoder-pipeline-components-cannot-encode-and-decode-data-processed-by-the-soap-adapter"></a><span data-ttu-id="cf0f6-112">MIME/SMIME エンコーダーおよびデコーダー パイプライン コンポーネントをエンコードおよび SOAP アダプターで処理されるデータをデコードできません。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-112">The MIME/SMIME encoder and decoder pipeline components cannot encode and decode data processed by the SOAP adapter</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="cf0f6-113">問題</span><span class="sxs-lookup"><span data-stu-id="cf0f6-113">Problem</span></span>  
 <span data-ttu-id="cf0f6-114">MIME/SMIME エンコーダーおよびデコーダー パイプライン コンポーネントをエンコードおよび SOAP アダプターで処理されるデータをデコードできません。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-114">The MIME/SMIME encoder and decoder pipeline components cannot encode and decode data processed by the SOAP adapter</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="cf0f6-115">原因</span><span class="sxs-lookup"><span data-stu-id="cf0f6-115">Cause</span></span>  
 <span data-ttu-id="cf0f6-116">この問題は、SOAP アダプターをアセンブルし、プロセスのアダプター ステージでは、SOAP メッセージを逆アセンブルするために発生します。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-116">This problem occurs because the SOAP adapter assembles and disassembles the SOAP messages in the adapter stage of the process.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="cf0f6-117">解決策</span><span class="sxs-lookup"><span data-stu-id="cf0f6-117">Resolution</span></span>  
 <span data-ttu-id="cf0f6-118">セキュリティで保護されたソケット レイヤー (SSL を使用)、SOAP アダプタによって処理されるメッセージをエンコードする通信をセキュリティで保護する、この問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-118">To resolve this problem, Use Secure Sockets Layer (SSL) to secure communications to encode messages processed by the SOAP adapter.</span></span> <span data-ttu-id="cf0f6-119">送信側を使用して、**クライアント証明書の拇印**でこれを実現するには、SOAP アダプター プロパティ ページのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-119">On the send side, use the **Client Certificate Thumbprint** property in the SOAP adapter properties page to achieve this.</span></span> <span data-ttu-id="cf0f6-120">受信側で安全な通信を SSL 用の BizTalk Web サービスをホストする仮想ディレクトリを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-120">On the receive side, you must configure the virtual directory that hosts the BizTalk Web Service for SSL secure communications.</span></span>  
  
#### <a name="the-default-appdomain-hosting-the-soap-adapter-gets-unloaded-causing-the-host-process-to-hang"></a><span data-ttu-id="cf0f6-121">既定の SOAP アダプターをホストする AppDomain はホスト プロセスがハングアップするアンロードされて取得します。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-121">The default AppDomain hosting the SOAP adapter gets unloaded causing the host process to hang</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="cf0f6-122">問題</span><span class="sxs-lookup"><span data-stu-id="cf0f6-122">Problem</span></span>  
 <span data-ttu-id="cf0f6-123">プロセスがハングアップするその他のすべての Web サービスを原因と、SOAP アダプターをホストするプロセスがハングします。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-123">The process hosting the SOAP adapter hangs, causing all other Web services in the process to hang.</span></span> <span data-ttu-id="cf0f6-124">次のエラーがあります。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-124">This may result in the following error:</span></span>  
  
 <span data-ttu-id="cf0f6-125">パイプライン"不明"を実行中にエラーが発生しました。「不明」のソース:「不明」の受信ポート。"TwoWayLatencyLoopBack_RxPort"、URI:"/TwoWayLatencyRxSOAP/TwoWayLatencyWS.asmx"理由。アンロードされた AppDomain にアクセスしようとしています。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-125">There was a failure executing the response(send) pipeline: "Unknown " Source: "Unknown " Receive Port: TwoWayLatencyLoopBack_RxPort" URI: "/TwoWayLatencyRxSOAP/TwoWayLatencyWS.asmx" Reason: Attempted to access an unloaded AppDomain.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="cf0f6-126">原因</span><span class="sxs-lookup"><span data-stu-id="cf0f6-126">Cause</span></span>  
 <span data-ttu-id="cf0f6-127">SOAP アダプターは、IIS プロセス領域で実行されます。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-127">The SOAP adapter runs in the IIS process space.</span></span> <span data-ttu-id="cf0f6-128">IIS AppPool に複数の Web サービスが存在する場合は、独自の AppDomain を持つのすべての Web サービスが終了します。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-128">If more than one Web service exists in the IIS AppPool, then every Web service ends up having its own AppDomain.</span></span>  
  
 <span data-ttu-id="cf0f6-129">既定ですべてのメッセージング エンジン オブジェクトが最初の AppDomain で作成されます (つまり、します。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-129">By default all messaging engine objects are created in the first AppDomain (that is,.</span></span> <span data-ttu-id="cf0f6-130">AppDomain 最初の Web サービスに対応する)。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-130">the AppDomain corresponding to the first Web service).</span></span> <span data-ttu-id="cf0f6-131">最初の Web サービスが何らかの理由の長期間非アクティブ、IIS は最初の AppDomain をアンロードします。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-131">If the first Web service is inactive for an extended period of time for any reason, IIS unloads the first AppDomain.</span></span> <span data-ttu-id="cf0f6-132">この場合、すべてのサービス ホスト プロセスでは使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-132">When this happens, all services in the hosting process become unusable.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="cf0f6-133">解決策</span><span class="sxs-lookup"><span data-stu-id="cf0f6-133">Resolution</span></span>  
 <span data-ttu-id="cf0f6-134">AppDomain がアンロードされないようにするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-134">To prevent the AppDomain from being unloaded, follow the procedure below:</span></span>  
  
1. <span data-ttu-id="cf0f6-135">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Server**順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-135">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server** and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="cf0f6-136">**BizTalk Server 管理コンソール**、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、 をクリックし、**ホスト**します。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-136">In **BizTalk Server Administration Console**, Expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Hosts**.</span></span>  
  
3. <span data-ttu-id="cf0f6-137">ホストの一覧から、必要なホストを右クリックし、**設定**します。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-137">From the list of Hosts, right-click the required host, and then click **Settings**.</span></span>  
  
4. <span data-ttu-id="cf0f6-138">**BizTalk 設定ダッシュ ボード**、確認**分離アダプターの既定のアプリケーション ドメイン\*\*\*\*全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-138">In the **BizTalk Settings Dashboard**, check **Default application domain for isolated adapter** under **General** tab.</span></span>  
  
   <span data-ttu-id="cf0f6-139">これを行うときに、BizTalk メッセージング エンジン オブジェクトは、既定値の代わりに、独自の Appdomain での AppDomain に作成されます。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-139">When you do this, the BizTalk Messaging Engine objects are created in the default AppDomain instead of in their own AppDomains.</span></span> <span data-ttu-id="cf0f6-140">既定の AppDomain はアンロードされないため、問題は発生しません。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-140">Because the default AppDomain is never unloaded, the problem no longer occurs.</span></span>  
  
#### <a name="the-soap-adapter-fails-to-register"></a><span data-ttu-id="cf0f6-141">SOAP アダプターを登録できません。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-141">The SOAP Adapter fails to register</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="cf0f6-142">問題</span><span class="sxs-lookup"><span data-stu-id="cf0f6-142">Problem</span></span>  
 <span data-ttu-id="cf0f6-143">BizTalk Server が SOAP (または HTTP) アダプターを登録しようとした場合、次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-143">The following error may occur when BizTalk Server attempts to register the SOAP (or HTTP) adapter.</span></span>  
  
 <span data-ttu-id="cf0f6-144">"メッセージング エンジンがアダプター"SOAP"を登録できませんでした。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-144">"The Messaging Engine failed to register an adapter "SOAP".</span></span> <span data-ttu-id="cf0f6-145">詳細:"同じプロセス内で複数のアダプターの種類を登録するシナリオ サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-145">Details: "Registering multiple adapter types within the same process is not a supported scenario.</span></span> <span data-ttu-id="cf0f6-146">たとえば HTTP および SOAP 受信アダプター共存できません同じプロセス内で"。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-146">For e.g. HTTP and SOAP receive adapters cannot co-exist in the same process".</span></span>  
  
 <span data-ttu-id="cf0f6-147">または</span><span class="sxs-lookup"><span data-stu-id="cf0f6-147">Or</span></span>  
  
 <span data-ttu-id="cf0f6-148">"メッセージング エンジンがアダプター"HTTP"を登録できませんでした。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-148">"The Messaging Engine failed to register an adapter "HTTP".</span></span> <span data-ttu-id="cf0f6-149">詳細:"同じプロセス内で複数のアダプターの種類を登録するシナリオ サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-149">Details: "Registering multiple adapter types within the same process is not a supported scenario.</span></span>  <span data-ttu-id="cf0f6-150">たとえば HTTP および SOAP 受信アダプター共存できません同じプロセス内で"。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-150">For e.g. HTTP and SOAP receive adapters cannot co-exist in the same process".</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="cf0f6-151">原因</span><span class="sxs-lookup"><span data-stu-id="cf0f6-151">Cause</span></span>  
 <span data-ttu-id="cf0f6-152">実行時に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]/IIS 6.x、SOAP および HTTP アダプターは同じプロセス領域またはアプリケーション プールで実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-152">When running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] / IIS 6.x, the SOAP and HTTP adapters cannot execute in the same process space or application pool.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="cf0f6-153">解決策</span><span class="sxs-lookup"><span data-stu-id="cf0f6-153">Resolution</span></span>  
 <span data-ttu-id="cf0f6-154">同じ Web サーバーでは SOAP および HTTP アダプターを使用して、インストールが必要な場合、アダプターごとに個別のアプリケーション プールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-154">If an installation requires using both the SOAP and HTTP adapters on the same Web server then separate application pools must be created for each adapter.</span></span>  <span data-ttu-id="cf0f6-155">作成されると、各アダプター用の仮想ディレクトリごとに割り当てられている別のアプリケーション プール。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-155">Once created, the virtual directories for each adapter are each assigned to a different application pool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf0f6-156">この問題は発生しません以降の Windows XP でこれらのオペレーティング システムで IIS 下で別のプロセス領域で実行する SOAP と HTTP アダプター 5.x します。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-156">This problem does not occur under Windows XP since under these operating systems, the SOAP and HTTP adapter run in different process spaces under IIS 5.x.</span></span>  <span data-ttu-id="cf0f6-157">SOAP アダプターは aspnet_wp.exe プロセスで ASP.Net アプリケーションとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-157">The SOAP adapter runs as an ASP.Net application in the aspnet_wp.exe process.</span></span>  <span data-ttu-id="cf0f6-158">HTTP アダプターは、dllhost.exe の専用のプロセス領域で実行されます。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-158">The HTTP adapter runs in the dedicated process space of dllhost.exe.</span></span>  <span data-ttu-id="cf0f6-159">そのため両方のアダプターは、同じ Web サーバーに同時に実行できるように、互いから分離されます。</span><span class="sxs-lookup"><span data-stu-id="cf0f6-159">Therefore both adapters are isolated from each other allowing them to run on the same Web server concurrently.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf0f6-160">参照</span><span class="sxs-lookup"><span data-stu-id="cf0f6-160">See Also</span></span>  
 [<span data-ttu-id="cf0f6-161">SOAP アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="cf0f6-161">Troubleshooting the SOAP Adapter</span></span>](../core/troubleshooting-the-soap-adapter.md)