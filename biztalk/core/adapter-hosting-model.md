---
title: アダプターのホスト モデル |Microsoft Docs
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
ms.openlocfilehash: 3f6603c07bc74cb904ad3eb88f50a3c7d2c60d09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361427"
---
# <a name="adapter-hosting-model"></a><span data-ttu-id="677cd-102">アダプターのホスト モデル</span><span class="sxs-lookup"><span data-stu-id="677cd-102">Adapter Hosting Model</span></span>
<span data-ttu-id="677cd-103">一般に BizTalk アダプターは、BizTalk サービス Btsntsvc.exe でホストされます。</span><span class="sxs-lookup"><span data-stu-id="677cd-103">In general BizTalk adapters are hosted in the BizTalk service, Btsntsvc.exe.</span></span> <span data-ttu-id="677cd-104">つまり、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプターの有効期間を管理します。</span><span class="sxs-lookup"><span data-stu-id="677cd-104">This means that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] manages the lifetime of the adapter.</span></span> <span data-ttu-id="677cd-105">場合、次のように、他のプロセスの管理対象アダプター。</span><span class="sxs-lookup"><span data-stu-id="677cd-105">There are also situations, described below, where other processes manage the adapter.</span></span>  
  
## <a name="in-process-adapters"></a><span data-ttu-id="677cd-106">インプロセス アダプター</span><span class="sxs-lookup"><span data-stu-id="677cd-106">In-Process Adapters</span></span>  
 <span data-ttu-id="677cd-107">管理されているアダプター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インプロセス アダプターと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="677cd-107">Adapters that are managed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are called in-process adapters.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="677cd-108">これらのアダプターは、次を行います。</span><span class="sxs-lookup"><span data-stu-id="677cd-108">does the following for these adapters:</span></span>  
  
- <span data-ttu-id="677cd-109">アダプターをインスタンス化時に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が開始</span><span class="sxs-lookup"><span data-stu-id="677cd-109">Instantiate the adapter when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is started</span></span>  
  
- <span data-ttu-id="677cd-110">初期化中に、アダプターのトランスポート プロキシをアダプターに渡します</span><span class="sxs-lookup"><span data-stu-id="677cd-110">Passes the adapter's transport proxy to the adapter during initialization</span></span>  
  
- <span data-ttu-id="677cd-111">サービスのアダプターの要求</span><span class="sxs-lookup"><span data-stu-id="677cd-111">Services the adapter's requests</span></span>  
  
- <span data-ttu-id="677cd-112">アダプターのシャット ダウンを終了します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービス</span><span class="sxs-lookup"><span data-stu-id="677cd-112">Terminates the adapter on shutdown of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] service</span></span>  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="677cd-113">実行時に、アダプター ハンドラーの構成およびエンドポイントの構成情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="677cd-113">delivers handler configuration and endpoint configuration information to the adapter at run time.</span></span> <span data-ttu-id="677cd-114">アクティブに要求を処理するために、アダプターが有効なを特定の期間を定義する windows サービスなど、他の構成が指定されます。</span><span class="sxs-lookup"><span data-stu-id="677cd-114">Other aspects of configuration are specified, such as service windows that define specific time periods during which the adapter is enabled to actively handle requests.</span></span>  
  
  <span data-ttu-id="677cd-115">BizTalk サービスが手動でシャット ダウンを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールまたはサービス コントロール マネージャーを使用しています。</span><span class="sxs-lookup"><span data-stu-id="677cd-115">The BizTalk service may be manually shut down by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or by using the service control manager.</span></span> <span data-ttu-id="677cd-116">場合への接続、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースには、サービスが失われることに自動的に自体をリサイクルします。</span><span class="sxs-lookup"><span data-stu-id="677cd-116">If connectivity to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases is lost the service automatically recycles itself.</span></span>  
  
  <span data-ttu-id="677cd-117">一般的なホスティング モデルでは、受信側アダプターと送信側アダプターがメッセージング エンジンとオーケストレーション エンジンと共に、BizTalk サービスと同じプロセスでホストされます。</span><span class="sxs-lookup"><span data-stu-id="677cd-117">In the typical hosting model, receive-side adapters and send-side adapters are hosted in the same process as the BizTalk service, along with the Messaging Engine and the Orchestration Engine.</span></span> <span data-ttu-id="677cd-118">ホスティング モデルは、受信、送信、およびオーケストレーションのホストとこれらの組み合わせの分離を許可するのに十分な柔軟性があります。</span><span class="sxs-lookup"><span data-stu-id="677cd-118">The hosting model is flexible enough to allow for separation of receive, send, and orchestration hosts and combinations of these.</span></span> <span data-ttu-id="677cd-119">次の図では、ホストは同じプロセス内で 3 つすべてを実行しています。</span><span class="sxs-lookup"><span data-stu-id="677cd-119">In the following figure, the host is executing all three in the same process.</span></span>  
  
  <span data-ttu-id="677cd-120">リッチのホスティング モデルであるため重要な点に注意するアダプターの送信を開発するときに、受信アダプターと同じホストで構成できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="677cd-120">Because of the rich hosting model, it is important when developing adapters to remember that the send and receive adapters may never be configured in the same host.</span></span> <span data-ttu-id="677cd-121">また、別のコンピューターで実行するでも構成できます。</span><span class="sxs-lookup"><span data-stu-id="677cd-121">They may even be configured to run on different computers.</span></span>  
  
  <span data-ttu-id="677cd-122">![](../core/media/regularadapterhostingmodel.gif "RegularAdapterHostingModel")</span><span class="sxs-lookup"><span data-stu-id="677cd-122">![](../core/media/regularadapterhostingmodel.gif "RegularAdapterHostingModel")</span></span>  
  <span data-ttu-id="677cd-123">インプロセス アダプターのホスト モデル</span><span class="sxs-lookup"><span data-stu-id="677cd-123">The in-process adapter hosting model</span></span>  
  
## <a name="isolated-adapters"></a><span data-ttu-id="677cd-124">分離アダプター</span><span class="sxs-lookup"><span data-stu-id="677cd-124">Isolated Adapters</span></span>  
 <span data-ttu-id="677cd-125">BizTalk サービスで受信アダプターをホストしているときにシナリオのことはできません。</span><span class="sxs-lookup"><span data-stu-id="677cd-125">There are scenarios when hosting receive adapters in the BizTalk service is not possible.</span></span> <span data-ttu-id="677cd-126">たとえば、インターネット インフォメーション サービス (IIS) プロセス モデルは、IIS で ASP.NET アプリケーションと ISAPI 拡張機能の有効期間管理されるようは。</span><span class="sxs-lookup"><span data-stu-id="677cd-126">For example, the Internet Information Services (IIS) process model is such that IIS manages the lifetime of ASP.NET applications and ISAPI extensions.</span></span> <span data-ttu-id="677cd-127">BizTalk SOAP アダプターは、IIS と同じプロセス領域内で実行する必要がありますできなくなり[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SOAP アダプターのすべてのインスタンスの有効期間を制御します。</span><span class="sxs-lookup"><span data-stu-id="677cd-127">The BizTalk SOAP adapter must run within the same process space as IIS, thus making it impossible for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to control the lifetime of any instances of the SOAP adapter.</span></span>  
  
 <span data-ttu-id="677cd-128">これらの種類のアダプターの分離受信アダプター、または単に分離アダプターと呼ばれるもう 1 つのホスティング モデルがあります。</span><span class="sxs-lookup"><span data-stu-id="677cd-128">For these types of adapters there is another hosting model referred to as isolated receive adapters, or simply isolated adapters.</span></span> <span data-ttu-id="677cd-129">分離送信アダプターの概念はありません。</span><span class="sxs-lookup"><span data-stu-id="677cd-129">There is no concept of an isolated send adapter.</span></span>  
  
 <span data-ttu-id="677cd-130">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]分離アダプターを作成することはできません、アダプターのトランスポート プロキシを取得し、そのトランスポート プロキシで自身を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="677cd-130">Because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot create an isolated adapter, the adapter must acquire its own transport proxy and register itself with that transport proxy.</span></span>  
  
 <span data-ttu-id="677cd-131">次の図を示しています、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アーキテクチャをホストします。</span><span class="sxs-lookup"><span data-stu-id="677cd-131">The following figure illustrates the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hosting architecture.</span></span> <span data-ttu-id="677cd-132">パフォーマンスを低下させない分離ホスト アーキテクチャは、不要なプロセス間通信を除去しようとします。</span><span class="sxs-lookup"><span data-stu-id="677cd-132">For the sake of performance, the isolated host architecture tries to eliminate any unnecessary interprocess communication.</span></span> <span data-ttu-id="677cd-133">分離アダプターと BizTalk メッセージング エンジン スタックは、同じプロセスでは、ためはプロセス間通信、アダプターがメッセージング エンジンを呼び出すときに、</span><span class="sxs-lookup"><span data-stu-id="677cd-133">Because the isolated adapter and the BizTalk Messaging Engine stack are in the same process, there is no interprocess communication when the adapter is calling the Messaging Engine.</span></span> <span data-ttu-id="677cd-134">シナリオでは、メッセージング エンジンとデータベース間の唯一のプロセス間通信は、これは回避できません。</span><span class="sxs-lookup"><span data-stu-id="677cd-134">In that scenario the only interprocess communication is between the Messaging Engine and the database, which is unavoidable.</span></span>  
  
 <span data-ttu-id="677cd-135">![](../core/media/isolatedadapters.gif "IsolatedAdapters")</span><span class="sxs-lookup"><span data-stu-id="677cd-135">![](../core/media/isolatedadapters.gif "IsolatedAdapters")</span></span>  
<span data-ttu-id="677cd-136">分離アダプターのホスティング モデル</span><span class="sxs-lookup"><span data-stu-id="677cd-136">The isolated adapter hosting model</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="677cd-137">参照</span><span class="sxs-lookup"><span data-stu-id="677cd-137">See Also</span></span>  
 [<span data-ttu-id="677cd-138">アダプター フレームワークについて</span><span class="sxs-lookup"><span data-stu-id="677cd-138">What Is the Adapter Framework?</span></span>](../core/what-is-the-adapter-framework.md)