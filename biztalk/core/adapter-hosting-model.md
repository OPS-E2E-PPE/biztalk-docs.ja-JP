---
title: アダプターのホスト モデル |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf9a8e6b-8c8d-47ec-b2a3-aed58206121d
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 645a1fcd41650c98c442549a898f7083be770842
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
ms.locfileid: "22225170"
---
# <a name="adapter-hosting-model"></a><span data-ttu-id="a1673-102">アダプターのホスト モデル</span><span class="sxs-lookup"><span data-stu-id="a1673-102">Adapter Hosting Model</span></span>
<span data-ttu-id="a1673-103">一般に BizTalk アダプターは、BizTalk サービス Btsntsvc.exe でホストされます。</span><span class="sxs-lookup"><span data-stu-id="a1673-103">In general BizTalk adapters are hosted in the BizTalk service, Btsntsvc.exe.</span></span> <span data-ttu-id="a1673-104">つまり、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプターの有効期間を管理します。</span><span class="sxs-lookup"><span data-stu-id="a1673-104">This means that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] manages the lifetime of the adapter.</span></span> <span data-ttu-id="a1673-105">状況によっては、次に説明するように、他のプロセスがこのアダプターを管理する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a1673-105">There are also situations, described below, where other processes manage the adapter.</span></span>  
  
## <a name="in-process-adapters"></a><span data-ttu-id="a1673-106">インプロセス アダプター</span><span class="sxs-lookup"><span data-stu-id="a1673-106">In-Process Adapters</span></span>  
 <span data-ttu-id="a1673-107">管理されているアダプター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インプロセス アダプターと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a1673-107">Adapters that are managed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are called in-process adapters.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a1673-108"> これらのアダプターは、次が行われます。</span><span class="sxs-lookup"><span data-stu-id="a1673-108"> does the following for these adapters:</span></span>  
  
-   <span data-ttu-id="a1673-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の起動時にアダプターをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="a1673-109">Instantiate the adapter when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is started</span></span>  
  
-   <span data-ttu-id="a1673-110">初期化時にアダプターのトランスポート プロキシをアダプターに渡します。</span><span class="sxs-lookup"><span data-stu-id="a1673-110">Passes the adapter's transport proxy to the adapter during initialization</span></span>  
  
-   <span data-ttu-id="a1673-111">アダプターの要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="a1673-111">Services the adapter's requests</span></span>  
  
-   <span data-ttu-id="a1673-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスのシャットダウン時にアダプターを終了します。</span><span class="sxs-lookup"><span data-stu-id="a1673-112">Terminates the adapter on shutdown of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] service</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a1673-113"> は、実行時にハンドラー構成およびエンドポイント構成の情報をアダプターに送信します。</span><span class="sxs-lookup"><span data-stu-id="a1673-113"> delivers handler configuration and endpoint configuration information to the adapter at run time.</span></span> <span data-ttu-id="a1673-114">アダプターが要求をアクティブに処理できる特定の期間を定義するサービス時間帯などの、構成のその他の要素が指定されます。</span><span class="sxs-lookup"><span data-stu-id="a1673-114">Other aspects of configuration are specified, such as service windows that define specific time periods during which the adapter is enabled to actively handle requests.</span></span>  
  
 <span data-ttu-id="a1673-115">BizTalk サービスが手動でシャット ダウンを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールまたはサービス コントロール マネージャーを使用しています。</span><span class="sxs-lookup"><span data-stu-id="a1673-115">The BizTalk service may be manually shut down by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or by using the service control manager.</span></span> <span data-ttu-id="a1673-116">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースとの接続が失われた場合は、サービスが自動的に自身を再利用します。</span><span class="sxs-lookup"><span data-stu-id="a1673-116">If connectivity to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases is lost the service automatically recycles itself.</span></span>  
  
 <span data-ttu-id="a1673-117">一般的なホスト モデルでは、受信側アダプターと送信側アダプターが、メッセージング エンジンおよびオーケストレーション エンジンと共に、BizTalk サービスと同じプロセスでホストされます。</span><span class="sxs-lookup"><span data-stu-id="a1673-117">In the typical hosting model, receive-side adapters and send-side adapters are hosted in the same process as the BizTalk service, along with the Messaging Engine and the Orchestration Engine.</span></span> <span data-ttu-id="a1673-118">このホスト モデルでは、受信、送信、オーケストレーションの各ホストを柔軟に分離したり組み合わせたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a1673-118">The hosting model is flexible enough to allow for separation of receive, send, and orchestration hosts and combinations of these.</span></span> <span data-ttu-id="a1673-119">次の図では、ホストが 3 つすべてを同じプロセスで実行しています。</span><span class="sxs-lookup"><span data-stu-id="a1673-119">In the following figure, the host is executing all three in the same process.</span></span>  
  
 <span data-ttu-id="a1673-120">多様なホスト モデルのため、アダプターを開発する際には、送信アダプターと受信アダプターを同じホストで構成できないことに留意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1673-120">Because of the rich hosting model, it is important when developing adapters to remember that the send and receive adapters may never be configured in the same host.</span></span> <span data-ttu-id="a1673-121">これらのアダプターは、別々のコンピューターで稼働するように構成される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a1673-121">They may even be configured to run on different computers.</span></span>  
  
 <span data-ttu-id="a1673-122">![](../core/media/regularadapterhostingmodel.gif "RegularAdapterHostingModel")</span><span class="sxs-lookup"><span data-stu-id="a1673-122">![](../core/media/regularadapterhostingmodel.gif "RegularAdapterHostingModel")</span></span>  
<span data-ttu-id="a1673-123">インプロセス アダプターのホスト モデル</span><span class="sxs-lookup"><span data-stu-id="a1673-123">The in-process adapter hosting model</span></span>  
  
## <a name="isolated-adapters"></a><span data-ttu-id="a1673-124">分離アダプター</span><span class="sxs-lookup"><span data-stu-id="a1673-124">Isolated Adapters</span></span>  
 <span data-ttu-id="a1673-125">シナリオによっては、BizTalk サービスで受信アダプターをホストできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a1673-125">There are scenarios when hosting receive adapters in the BizTalk service is not possible.</span></span> <span data-ttu-id="a1673-126">たとえば、インターネット インフォメーション サービス (IIS) のプロセス モデルでは、ASP.NET アプリケーションと ISAPI 拡張の有効期間が IIS で管理されるようになっています。</span><span class="sxs-lookup"><span data-stu-id="a1673-126">For example, the Internet Information Services (IIS) process model is such that IIS manages the lifetime of ASP.NET applications and ISAPI extensions.</span></span> <span data-ttu-id="a1673-127">BizTalk SOAP アダプターは IIS と同じプロセス領域で実行する必要があるため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では SOAP アダプターのインスタンスの有効期間を制御できません。</span><span class="sxs-lookup"><span data-stu-id="a1673-127">The BizTalk SOAP adapter must run within the same process space as IIS, thus making it impossible for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to control the lifetime of any instances of the SOAP adapter.</span></span>  
  
 <span data-ttu-id="a1673-128">これらのアダプターには、分離受信アダプター、または単に分離アダプターと呼ばれる別のホスト モデルが用意されています。</span><span class="sxs-lookup"><span data-stu-id="a1673-128">For these types of adapters there is another hosting model referred to as isolated receive adapters, or simply isolated adapters.</span></span> <span data-ttu-id="a1673-129">分離送信アダプターという概念は存在しません。</span><span class="sxs-lookup"><span data-stu-id="a1673-129">There is no concept of an isolated send adapter.</span></span>  
  
 <span data-ttu-id="a1673-130">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では分離アダプターを作成できないため、アダプターで独自のトランスポート プロキシを取得し、そのトランスポート プロキシでアダプターを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1673-130">Because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot create an isolated adapter, the adapter must acquire its own transport proxy and register itself with that transport proxy.</span></span>  
  
 <span data-ttu-id="a1673-131">次の図は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のホスト アーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="a1673-131">The following figure illustrates the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hosting architecture.</span></span> <span data-ttu-id="a1673-132">パフォーマンスを確保するために、分離ホスト アーキテクチャでは不要なプロセス間通信が削除されます。</span><span class="sxs-lookup"><span data-stu-id="a1673-132">For the sake of performance, the isolated host architecture tries to eliminate any unnecessary interprocess communication.</span></span> <span data-ttu-id="a1673-133">分離アダプターと BizTalk メッセージング エンジン スタックは同じプロセスにあるため、アダプターでメッセージング エンジンが呼び出されているときはプロセス間通信は発生しません。</span><span class="sxs-lookup"><span data-stu-id="a1673-133">Because the isolated adapter and the BizTalk Messaging Engine stack are in the same process, there is no interprocess communication when the adapter is calling the Messaging Engine.</span></span> <span data-ttu-id="a1673-134">このシナリオでは、唯一のプロセス間通信は、メッセージング エンジンとデータベースの間で行われます。これは回避できません。</span><span class="sxs-lookup"><span data-stu-id="a1673-134">In that scenario the only interprocess communication is between the Messaging Engine and the database, which is unavoidable.</span></span>  
  
 <span data-ttu-id="a1673-135">![](../core/media/isolatedadapters.gif "IsolatedAdapters")</span><span class="sxs-lookup"><span data-stu-id="a1673-135">![](../core/media/isolatedadapters.gif "IsolatedAdapters")</span></span>  
<span data-ttu-id="a1673-136">分離アダプターのホスト モデル</span><span class="sxs-lookup"><span data-stu-id="a1673-136">The isolated adapter hosting model</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1673-137">参照</span><span class="sxs-lookup"><span data-stu-id="a1673-137">See Also</span></span>  
 [<span data-ttu-id="a1673-138">アダプター フレームワークについて</span><span class="sxs-lookup"><span data-stu-id="a1673-138">What Is the Adapter Framework?</span></span>](../core/what-is-the-adapter-framework.md)