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
ms.openlocfilehash: 6c6a97bd38a68eef866549f980624a92ee2b3143
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391638"
---
# <a name="components-of-the-mqseries-adapter"></a><span data-ttu-id="da2f8-102">MQSeries アダプターのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="da2f8-102">Components of the MQSeries Adapter</span></span>
<span data-ttu-id="da2f8-103">MQSeries アダプターの間のドキュメント転送を容易に 2 つのコンポーネントを使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と MQSeries Server for Windows。</span><span class="sxs-lookup"><span data-stu-id="da2f8-103">The MQSeries adapter uses two components to facilitate document transfer between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and MQSeries Server for Windows.</span></span>  
  
- <span data-ttu-id="da2f8-104">**BizTalk コンポーネントです。**</span><span class="sxs-lookup"><span data-stu-id="da2f8-104">**BizTalk component.**</span></span> <span data-ttu-id="da2f8-105">Microsoft と同じコンピューターにこのコンポーネントをインストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="da2f8-105">Install this component on the same computer as Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="da2f8-106">このコンポーネントは、BizTalk Server と通信します。</span><span class="sxs-lookup"><span data-stu-id="da2f8-106">This component communicates with BizTalk Server.</span></span>  
  
- <span data-ttu-id="da2f8-107">**MQSeries コンポーネントです。**</span><span class="sxs-lookup"><span data-stu-id="da2f8-107">**MQSeries component.**</span></span> <span data-ttu-id="da2f8-108">Windows の MQSeries サーバーでこのコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="da2f8-108">Install this component on the MQSeries Server for Windows.</span></span> <span data-ttu-id="da2f8-109">MQSeries Server for Windows 上で実行[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="da2f8-109">MQSeries Server for Windows runs on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].</span></span> <span data-ttu-id="da2f8-110">このコンポーネント (MQSAgent と呼ばれます) は、IBM MQSeries Server と通信します。</span><span class="sxs-lookup"><span data-stu-id="da2f8-110">This component (referred to as MQSAgent) communicates with IBM MQSeries Server.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="da2f8-111">MQSeries アダプターの MQSAgent コンポーネントは、サポートされている実行に対して MQSeries Server 5.3、CSD10 以降および Windows 上の WebSphere MQSeries Server 6.0 です。</span><span class="sxs-lookup"><span data-stu-id="da2f8-111">The MQSAgent component of the MQSeries Adapter is supported running against MQSeries Server 5.3, CSD10 or above, and WebSphere MQSeries Server 6.0 on Windows.</span></span>  
  
  <span data-ttu-id="da2f8-112">次の図では、アダプターの一般的な使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="da2f8-112">The following figure outlines a typical use of the adapter.</span></span>  
  
  <span data-ttu-id="da2f8-113">![MQSeries Server と BizTalk 間のフローを文書化](../core/media/bts-dev-mqadapterflow.gif "BTS_Dev_MQAdapterFlow")</span><span class="sxs-lookup"><span data-stu-id="da2f8-113">![Document flow between MQSeries Server and BizTalk](../core/media/bts-dev-mqadapterflow.gif "BTS_Dev_MQAdapterFlow")</span></span>  
  
  <span data-ttu-id="da2f8-114">MQSeries アダプターが使用できるようにする接続ソリューション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]エンタープライズで選択したメッセージング標準として MQSeries します。</span><span class="sxs-lookup"><span data-stu-id="da2f8-114">The MQSeries adapter is a connectivity solution that lets you use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in an enterprise with MQSeries as the chosen messaging standard.</span></span> <span data-ttu-id="da2f8-115">このソリューションが開発されたように促されて、一部を次の問題。</span><span class="sxs-lookup"><span data-stu-id="da2f8-115">Developing this solution was motivated, in part, by the following issues:</span></span>  
  
- <span data-ttu-id="da2f8-116">簡単なインストールと構成、および MQSeries 接続ソリューションに対する顧客の要望に対応</span><span class="sxs-lookup"><span data-stu-id="da2f8-116">Accommodating customer requests for simple installation and configuration, and an MQSeries connectivity solution</span></span>  
  
- <span data-ttu-id="da2f8-117">最大 100 MB のサイズをメッセージのサポート</span><span class="sxs-lookup"><span data-stu-id="da2f8-117">Supporting message sizes up to 100 MB</span></span>  
  
- <span data-ttu-id="da2f8-118">MQSeries のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="da2f8-118">Providing MQSeries support</span></span>  
  
- <span data-ttu-id="da2f8-119">送信される MQSeries メッセージのプラグ アンド プレイの接続ソリューションを提供します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da2f8-119">Providing a Plug and Play connectivity solution for MQSeries messages to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
  <span data-ttu-id="da2f8-120">MQSeries アダプターは、重要な追加、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]さまざまな通信プロトコル標準用のリスナーのセットを提供する受信サービスのスイートです。</span><span class="sxs-lookup"><span data-stu-id="da2f8-120">The MQSeries adapter is a key addition to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suite of receive services that provide a set of listeners for various communication protocol standards.</span></span> <span data-ttu-id="da2f8-121">リスナーは、エンタープライズ アプリケーション統合 (EAI)、企業間取引、またはアプリケーションの統合の取引関係にプロトコル、HTTP、FTP、または MQSeries、たとえばをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="da2f8-121">The listeners attach a protocol, for example HTTP, FTP, or MQSeries, to an enterprise application integration (EAI), business-to-business, or application-to-application integration trading relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da2f8-122">参照</span><span class="sxs-lookup"><span data-stu-id="da2f8-122">See Also</span></span>  
 <span data-ttu-id="da2f8-123">[MQSeries アダプターのアーキテクチャ](../core/mqseries-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="da2f8-123">[MQSeries Adapter Architecture](../core/mqseries-adapter-architecture.md) </span></span>  
 [<span data-ttu-id="da2f8-124">MQSeries アダプターとは</span><span class="sxs-lookup"><span data-stu-id="da2f8-124">What Is the MQSeries Adapter?</span></span>](../core/what-is-the-mqseries-adapter.md)