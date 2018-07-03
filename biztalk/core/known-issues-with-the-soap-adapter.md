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
ms.openlocfilehash: 273ebf62251050f6cb4aa8de9582aec9f475cbee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018697"
---
# <a name="known-issues-with-the-soap-adapter"></a><span data-ttu-id="441cb-102">SOAP アダプターに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="441cb-102">Known Issues with the SOAP Adapter</span></span>
<span data-ttu-id="441cb-103">ここでは、エラー回避に役立つ情報を記載します。</span><span class="sxs-lookup"><span data-stu-id="441cb-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="441cb-104">既知の問題</span><span class="sxs-lookup"><span data-stu-id="441cb-104">Known Issues</span></span>  
  
#### <a name="the-soap-adapter-experiences-poor-performance-or-generates-errors-under-load"></a><span data-ttu-id="441cb-105">負荷状況下で SOAP アダプターのパフォーマンスが低下したりエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="441cb-105">The SOAP Adapter experiences poor performance or generates errors under load</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="441cb-106">問題</span><span class="sxs-lookup"><span data-stu-id="441cb-106">Problem</span></span>  
 <span data-ttu-id="441cb-107">負荷状況下で SOAP アダプターのパフォーマンスが低下したりエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="441cb-107">The SOAP Adapter experiences poor performance or generates errors under load</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="441cb-108">原因</span><span class="sxs-lookup"><span data-stu-id="441cb-108">Cause</span></span>  
 <span data-ttu-id="441cb-109">この問題は、SOAP アダプターまたは SOAP アダプターに影響する依存関係コンポーネントの既定の構成オプションが、負荷状況下のパフォーマンス用にチューニングされていないために発生します。</span><span class="sxs-lookup"><span data-stu-id="441cb-109">This problem occurs because the default configuration options for the SOAP adapter or for dependency components that affect the SOAP adapter are not tuned for performance under load.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="441cb-110">解決策</span><span class="sxs-lookup"><span data-stu-id="441cb-110">Resolution</span></span>  
 <span data-ttu-id="441cb-111">この問題を解決するには、変更の SOAP アダプターまたはトピックで説明されている依存関係コンポーネントの構成オプション[構成パラメーターを アダプターのパフォーマンスの影響を与える](../core/configuration-parameters-that-affect-adapter-performance.md)します。</span><span class="sxs-lookup"><span data-stu-id="441cb-111">To resolve this problem modify the configuration options for the SOAP adapter or for the dependency components described in the topic [Configuration Parameters that Affect Adapter Performance](../core/configuration-parameters-that-affect-adapter-performance.md).</span></span>  
  
#### <a name="the-mimesmime-encoder-and-decoder-pipeline-components-cannot-encode-and-decode-data-processed-by-the-soap-adapter"></a><span data-ttu-id="441cb-112">MIME/SMIME エンコーダーおよびデコーダー パイプライン コンポーネントが、SOAP アダプターで処理されたデータをエンコードまたはデコードできない</span><span class="sxs-lookup"><span data-stu-id="441cb-112">The MIME/SMIME encoder and decoder pipeline components cannot encode and decode data processed by the SOAP adapter</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="441cb-113">問題</span><span class="sxs-lookup"><span data-stu-id="441cb-113">Problem</span></span>  
 <span data-ttu-id="441cb-114">MIME/SMIME エンコーダーおよびデコーダー パイプライン コンポーネントが、SOAP アダプターで処理されたデータをエンコードまたはデコードできない</span><span class="sxs-lookup"><span data-stu-id="441cb-114">The MIME/SMIME encoder and decoder pipeline components cannot encode and decode data processed by the SOAP adapter</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="441cb-115">原因</span><span class="sxs-lookup"><span data-stu-id="441cb-115">Cause</span></span>  
 <span data-ttu-id="441cb-116">この問題は、SOAP アダプターが、処理のアダプター ステージにある SOAP メッセージをアセンブルおよび逆アセンブルするために発生します。</span><span class="sxs-lookup"><span data-stu-id="441cb-116">This problem occurs because the SOAP adapter assembles and disassembles the SOAP messages in the adapter stage of the process.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="441cb-117">解決策</span><span class="sxs-lookup"><span data-stu-id="441cb-117">Resolution</span></span>  
 <span data-ttu-id="441cb-118">この問題を解決するには、SSL (Secure Sockets Layer) による保護された通信を使って、SOAP アダプターが処理するメッセージをエンコードします。</span><span class="sxs-lookup"><span data-stu-id="441cb-118">To resolve this problem, Use Secure Sockets Layer (SSL) to secure communications to encode messages processed by the SOAP adapter.</span></span> <span data-ttu-id="441cb-119">送信側を使用して、**クライアント証明書の拇印**でこれを実現するには、SOAP アダプター プロパティ ページのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="441cb-119">On the send side, use the **Client Certificate Thumbprint** property in the SOAP adapter properties page to achieve this.</span></span> <span data-ttu-id="441cb-120">受信側では、SSL による保護された通信で BizTalk Web サービスをホストする仮想ディレクトリを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="441cb-120">On the receive side, you must configure the virtual directory that hosts the BizTalk Web Service for SSL secure communications.</span></span>  
  
#### <a name="the-default-appdomain-hosting-the-soap-adapter-gets-unloaded-causing-the-host-process-to-hang"></a><span data-ttu-id="441cb-121">SOAP アダプターをホストする既定の AppDomain がアンロードされてホスト プロセスがハングアップする</span><span class="sxs-lookup"><span data-stu-id="441cb-121">The default AppDomain hosting the SOAP adapter gets unloaded causing the host process to hang</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="441cb-122">問題</span><span class="sxs-lookup"><span data-stu-id="441cb-122">Problem</span></span>  
 <span data-ttu-id="441cb-123">SOAP アダプターをホストするプロセスがハングアップし、それによってプロセス内のその他すべての Web サービスがハングアップします。</span><span class="sxs-lookup"><span data-stu-id="441cb-123">The process hosting the SOAP adapter hangs, causing all other Web services in the process to hang.</span></span> <span data-ttu-id="441cb-124">これによって次のエラーが発生するおそれがあります。</span><span class="sxs-lookup"><span data-stu-id="441cb-124">This may result in the following error:</span></span>  
  
 <span data-ttu-id="441cb-125">パイプライン"不明"を実行中にエラーが発生しました:"Unknown"のソース:"不明"受信ポート::"TwoWayLatencyLoopBack_RxPort"、URI:"/TwoWayLatencyRxSOAP/TwoWayLatencyWS.asmx"理由: アンロードされた AppDomain にアクセスしようとしています。</span><span class="sxs-lookup"><span data-stu-id="441cb-125">There was a failure executing the response(send) pipeline: "Unknown " Source: "Unknown " Receive Port: TwoWayLatencyLoopBack_RxPort" URI: "/TwoWayLatencyRxSOAP/TwoWayLatencyWS.asmx" Reason: Attempted to access an unloaded AppDomain.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="441cb-126">原因</span><span class="sxs-lookup"><span data-stu-id="441cb-126">Cause</span></span>  
 <span data-ttu-id="441cb-127">SOAP アダプターは IIS プロセス領域で実行されます。</span><span class="sxs-lookup"><span data-stu-id="441cb-127">The SOAP adapter runs in the IIS process space.</span></span> <span data-ttu-id="441cb-128">IIS AppPool に複数の Web サービスが存在する場合は、すべての Web サービスが独自の AppDomain を持つことになります。</span><span class="sxs-lookup"><span data-stu-id="441cb-128">If more than one Web service exists in the IIS AppPool, then every Web service ends up having its own AppDomain.</span></span>  
  
 <span data-ttu-id="441cb-129">既定ですべてのメッセージング エンジン オブジェクトが最初の AppDomain で作成されます (つまり、します。</span><span class="sxs-lookup"><span data-stu-id="441cb-129">By default all messaging engine objects are created in the first AppDomain (that is,.</span></span> <span data-ttu-id="441cb-130">AppDomain 最初の Web サービスに対応する)。</span><span class="sxs-lookup"><span data-stu-id="441cb-130">the AppDomain corresponding to the first Web service).</span></span> <span data-ttu-id="441cb-131">最初の Web サービスが何らかの理由で一定期間以上非アクティブになると、IIS は最初の AppDomain をアンロードします。</span><span class="sxs-lookup"><span data-stu-id="441cb-131">If the first Web service is inactive for an extended period of time for any reason, IIS unloads the first AppDomain.</span></span> <span data-ttu-id="441cb-132">この場合、ホスティング プロセスのすべてのサービスが使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="441cb-132">When this happens, all services in the hosting process become unusable.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="441cb-133">解決策</span><span class="sxs-lookup"><span data-stu-id="441cb-133">Resolution</span></span>  
 <span data-ttu-id="441cb-134">AppDomain がアンロードされないようにするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="441cb-134">To prevent the AppDomain from being unloaded, follow the procedure below:</span></span>  
  
1. <span data-ttu-id="441cb-135">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Server**順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="441cb-135">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server** and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="441cb-136">**BizTalk Server 管理コンソール**、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、 をクリックし、**ホスト**します。</span><span class="sxs-lookup"><span data-stu-id="441cb-136">In **BizTalk Server Administration Console**, Expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Hosts**.</span></span>  
  
3. <span data-ttu-id="441cb-137">ホストの一覧から、必要なホストを右クリックし、**設定**します。</span><span class="sxs-lookup"><span data-stu-id="441cb-137">From the list of Hosts, right-click the required host, and then click **Settings**.</span></span>  
  
4. <span data-ttu-id="441cb-138">**BizTalk 設定ダッシュ ボード**、確認**分離アダプターの既定のアプリケーション ドメイン****全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="441cb-138">In the **BizTalk Settings Dashboard**, check **Default application domain for isolated adapter** under **General** tab.</span></span>  
  
   <span data-ttu-id="441cb-139">この設定を行うと、BizTalk メッセージング エンジン オブジェクトが、独自の AppDomain ではなく既定の AppDomain に作成されます。</span><span class="sxs-lookup"><span data-stu-id="441cb-139">When you do this, the BizTalk Messaging Engine objects are created in the default AppDomain instead of in their own AppDomains.</span></span> <span data-ttu-id="441cb-140">既定の AppDomain はアンロードされないため、問題は発生しなくなります。</span><span class="sxs-lookup"><span data-stu-id="441cb-140">Because the default AppDomain is never unloaded, the problem no longer occurs.</span></span>  
  
#### <a name="the-soap-adapter-fails-to-register"></a><span data-ttu-id="441cb-141">SOAP アダプターを登録できない</span><span class="sxs-lookup"><span data-stu-id="441cb-141">The SOAP Adapter fails to register</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="441cb-142">問題</span><span class="sxs-lookup"><span data-stu-id="441cb-142">Problem</span></span>  
 <span data-ttu-id="441cb-143">BizTalk Server が SOAP (または HTTP) アダプターを登録する際に次のエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="441cb-143">The following error may occur when BizTalk Server attempts to register the SOAP (or HTTP) adapter.</span></span>  
  
 <span data-ttu-id="441cb-144">"メッセージング エンジンがアダプター "SOAP" を登録できませんでした。</span><span class="sxs-lookup"><span data-stu-id="441cb-144">"The Messaging Engine failed to register an adapter "SOAP".</span></span> <span data-ttu-id="441cb-145">詳細:"同じプロセス内で複数のアダプターの種類を登録、シナリオ サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="441cb-145">Details: "Registering multiple adapter types within the same process is not a supported scenario.</span></span> <span data-ttu-id="441cb-146">たとえば、HTTP および SOAP の受信アダプターは同じプロセス内に共存できません。"</span><span class="sxs-lookup"><span data-stu-id="441cb-146">For e.g. HTTP and SOAP receive adapters cannot co-exist in the same process".</span></span>  
  
 <span data-ttu-id="441cb-147">スイッチまたは</span><span class="sxs-lookup"><span data-stu-id="441cb-147">Or</span></span>  
  
 <span data-ttu-id="441cb-148">"メッセージング エンジンがアダプター "HTTP" を登録できませんでした。</span><span class="sxs-lookup"><span data-stu-id="441cb-148">"The Messaging Engine failed to register an adapter "HTTP".</span></span> <span data-ttu-id="441cb-149">詳細:"同じプロセス内で複数のアダプターの種類を登録、シナリオ サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="441cb-149">Details: "Registering multiple adapter types within the same process is not a supported scenario.</span></span>  <span data-ttu-id="441cb-150">たとえば、HTTP および SOAP の受信アダプターは同じプロセス内に共存できません。"</span><span class="sxs-lookup"><span data-stu-id="441cb-150">For e.g. HTTP and SOAP receive adapters cannot co-exist in the same process".</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="441cb-151">原因</span><span class="sxs-lookup"><span data-stu-id="441cb-151">Cause</span></span>  
 <span data-ttu-id="441cb-152">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 上の IIS 6.x で実行する場合は、SOAP アダプターと HTTP アダプターを同じプロセス領域またはアプリケーション プールで実行できません。</span><span class="sxs-lookup"><span data-stu-id="441cb-152">When running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] / IIS 6.x, the SOAP and HTTP adapters cannot execute in the same process space or application pool.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="441cb-153">解決策</span><span class="sxs-lookup"><span data-stu-id="441cb-153">Resolution</span></span>  
 <span data-ttu-id="441cb-154">SOAP アダプターと HTTP アダプターの両方を同じ Web サーバーで使用する必要があるインストール環境では、各アダプターに別個のアプリケーション プールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="441cb-154">If an installation requires using both the SOAP and HTTP adapters on the same Web server then separate application pools must be created for each adapter.</span></span>  <span data-ttu-id="441cb-155">作成された各アプリケーション プールには、各アダプターの仮想ディレクトリがそれぞれ割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="441cb-155">Once created, the virtual directories for each adapter are each assigned to a different application pool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="441cb-156">Windows XP では、IIS 5.x の下で SOAP アダプターと HTTP アダプターが別々のプロセス領域で実行されるため、この問題は発生しません。</span><span class="sxs-lookup"><span data-stu-id="441cb-156">This problem does not occur under Windows XP since under these operating systems, the SOAP and HTTP adapter run in different process spaces under IIS 5.x.</span></span>  <span data-ttu-id="441cb-157">SOAP アダプターは aspnet_wp.exe プロセスで ASP.Net アプリケーションとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="441cb-157">The SOAP adapter runs as an ASP.Net application in the aspnet_wp.exe process.</span></span>  <span data-ttu-id="441cb-158">HTTP アダプターは、dllhost.exe の専用のプロセス領域で実行されます。</span><span class="sxs-lookup"><span data-stu-id="441cb-158">The HTTP adapter runs in the dedicated process space of dllhost.exe.</span></span>  <span data-ttu-id="441cb-159">このため両方のアダプターが分離されて、同じ Web サーバーで同時に実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="441cb-159">Therefore both adapters are isolated from each other allowing them to run on the same Web server concurrently.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="441cb-160">参照</span><span class="sxs-lookup"><span data-stu-id="441cb-160">See Also</span></span>  
 [<span data-ttu-id="441cb-161">SOAP アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="441cb-161">Troubleshooting the SOAP Adapter</span></span>](../core/troubleshooting-the-soap-adapter.md)