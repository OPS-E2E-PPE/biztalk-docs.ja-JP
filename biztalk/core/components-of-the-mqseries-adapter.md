---
title: MQSeries アダプターのコンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, BizTalk component
- MQSeries adapters, components
- MQSeries components, MQSeries adapters
- BizTalk components
- MQSeries adapters, MQSeries component
ms.assetid: 923974cb-371d-47dc-99a7-2f7b93f60ada
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afeac0dda1d42c244eeeac124632ed68aa2e90d4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990331"
---
# <a name="components-of-the-mqseries-adapter"></a><span data-ttu-id="e8d02-102">MQSeries アダプターのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="e8d02-102">Components of the MQSeries Adapter</span></span>
<span data-ttu-id="e8d02-103">MQSeries アダプターでは、2 つのコンポーネントを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と MQSeries Server for Windows の間のドキュメント転送を容易にしています。</span><span class="sxs-lookup"><span data-stu-id="e8d02-103">The MQSeries adapter uses two components to facilitate document transfer between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and MQSeries Server for Windows.</span></span>  
  
- <span data-ttu-id="e8d02-104">**BizTalk コンポーネントです。**</span><span class="sxs-lookup"><span data-stu-id="e8d02-104">**BizTalk component.**</span></span> <span data-ttu-id="e8d02-105">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と同じコンピューターにこのコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e8d02-105">Install this component on the same computer as Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="e8d02-106">このコンポーネントによって BizTalk Server との通信が行われます。</span><span class="sxs-lookup"><span data-stu-id="e8d02-106">This component communicates with BizTalk Server.</span></span>  
  
- <span data-ttu-id="e8d02-107">**MQSeries コンポーネントです。**</span><span class="sxs-lookup"><span data-stu-id="e8d02-107">**MQSeries component.**</span></span> <span data-ttu-id="e8d02-108">MQSeries Server for Windows にこのコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e8d02-108">Install this component on the MQSeries Server for Windows.</span></span> <span data-ttu-id="e8d02-109">MQSeries Server for Windows は、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] または [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 上で動作します。</span><span class="sxs-lookup"><span data-stu-id="e8d02-109">MQSeries Server for Windows runs on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].</span></span> <span data-ttu-id="e8d02-110">このコンポーネント (MQSAgent と呼ばれます) によって IBM MQSeries Server との通信が行われます。</span><span class="sxs-lookup"><span data-stu-id="e8d02-110">This component (referred to as MQSAgent) communicates with IBM MQSeries Server.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="e8d02-111">MQSeries アダプターの MQSAgent コンポーネントは、Windows 上の MQSeries Server 5.3、CSD10 以降、および WebSphere MQSeries Server 6.0 に対して実行できます。</span><span class="sxs-lookup"><span data-stu-id="e8d02-111">The MQSAgent component of the MQSeries Adapter is supported running against MQSeries Server 5.3, CSD10 or above, and WebSphere MQSeries Server 6.0 on Windows.</span></span>  
  
  <span data-ttu-id="e8d02-112">次の図に、MQSeries アダプターの一般的な使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e8d02-112">The following figure outlines a typical use of the adapter.</span></span>  
  
  <span data-ttu-id="e8d02-113">![MQSeries Server と BizTalk 間のフローを文書化](../core/media/bts-dev-mqadapterflow.gif "BTS_Dev_MQAdapterFlow")</span><span class="sxs-lookup"><span data-stu-id="e8d02-113">![Document flow between MQSeries Server and BizTalk](../core/media/bts-dev-mqadapterflow.gif "BTS_Dev_MQAdapterFlow")</span></span>  
  
  <span data-ttu-id="e8d02-114">MQSeries アダプターは、メッセージング標準として MQSeries を選択している企業で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用できるようにする接続ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="e8d02-114">The MQSeries adapter is a connectivity solution that lets you use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in an enterprise with MQSeries as the chosen messaging standard.</span></span> <span data-ttu-id="e8d02-115">このソリューションを開発した背景として、以下のような課題がありました。</span><span class="sxs-lookup"><span data-stu-id="e8d02-115">Developing this solution was motivated, in part, by the following issues:</span></span>  
  
- <span data-ttu-id="e8d02-116">簡単なインストールと構成、および MQSeries 接続ソリューションに対する顧客の要望に応えること</span><span class="sxs-lookup"><span data-stu-id="e8d02-116">Accommodating customer requests for simple installation and configuration, and an MQSeries connectivity solution</span></span>  
  
- <span data-ttu-id="e8d02-117">最大 100 MB のメッセージ サイズをサポートすること</span><span class="sxs-lookup"><span data-stu-id="e8d02-117">Supporting message sizes up to 100 MB</span></span>  
  
- <span data-ttu-id="e8d02-118">MQSeries のサポートを提供すること</span><span class="sxs-lookup"><span data-stu-id="e8d02-118">Providing MQSeries support</span></span>  
  
- <span data-ttu-id="e8d02-119">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信される MQSeries メッセージに対するプラグ アンド プレイの接続ソリューションを提供すること</span><span class="sxs-lookup"><span data-stu-id="e8d02-119">Providing a Plug and Play connectivity solution for MQSeries messages to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
  <span data-ttu-id="e8d02-120">MQSeries アダプターは、さまざまな通信プロトコル標準用のリスナー セットを提供する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 受信サービスの重要な追加機能です。</span><span class="sxs-lookup"><span data-stu-id="e8d02-120">The MQSeries adapter is a key addition to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suite of receive services that provide a set of listeners for various communication protocol standards.</span></span> <span data-ttu-id="e8d02-121">これらのリスナーによって、HTTP、FTP、MQSeries などのプロトコルがエンタープライズ アプリケーション統合 (EAI)、企業間統合、またはアプリケーション統合の取引関係に追加されます。</span><span class="sxs-lookup"><span data-stu-id="e8d02-121">The listeners attach a protocol, for example HTTP, FTP, or MQSeries, to an enterprise application integration (EAI), business-to-business, or application-to-application integration trading relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8d02-122">参照</span><span class="sxs-lookup"><span data-stu-id="e8d02-122">See Also</span></span>  
 <span data-ttu-id="e8d02-123">[MQSeries アダプターのアーキテクチャ](../core/mqseries-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="e8d02-123">[MQSeries Adapter Architecture](../core/mqseries-adapter-architecture.md) </span></span>  
 [<span data-ttu-id="e8d02-124">MQSeries アダプターとは</span><span class="sxs-lookup"><span data-stu-id="e8d02-124">What Is the MQSeries Adapter?</span></span>](../core/what-is-the-mqseries-adapter.md)