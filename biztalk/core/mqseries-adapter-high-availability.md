---
title: MQSeries アダプターの高可用性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, MQSeries adapters
- MQSeries adapters, availability
- MQSeries adapters, performance
- high availability, MQSeries adapters
ms.assetid: 4339b10b-b35d-47c0-b78a-c60207e06c8e
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96fb7eb3ef5d126656d3cc456206ae56feba4c23
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323755"
---
# <a name="mqseries-adapter-high-availability"></a><span data-ttu-id="dc70d-102">MQSeries アダプターの高可用性</span><span class="sxs-lookup"><span data-stu-id="dc70d-102">MQSeries Adapter High Availability</span></span>
<span data-ttu-id="dc70d-103">アダプタを使用する場合は、次の方法で可用性を改善できます。</span><span class="sxs-lookup"><span data-stu-id="dc70d-103">You can improve availability in the following ways when you use the adapter:</span></span>  
  
- <span data-ttu-id="dc70d-104">フォールト トレランスのホスティング環境のセットアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="dc70d-104">Set up a fault-tolerant hosting environment for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="dc70d-105">Windows は、IBM WebSphere MQ のクラスタ リングを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc70d-105">Use Windows Clustering with IBM WebSphere MQ.</span></span>  
  
  <span data-ttu-id="dc70d-106">フォールト トレランスについては、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[BizTalk Server のサンプル アーキテクチャ](../core/sample-biztalk-server-architectures.md)と[フォールト トレランスのためのプラットフォームの計画](../core/planning-your-platform-for-fault-tolerance.md)で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="dc70d-106">For information about fault tolerance and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md) and [Planning Your Platform for Fault Tolerance](../core/planning-your-platform-for-fault-tolerance.md) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
  <span data-ttu-id="dc70d-107">いることを確認する、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries アダプターが MQSAgent コンポーネントのリモート インストールとの通信をネットワーク COM + アクセスを有効にしたことを確認するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と IBM WebSphere MQ がインストールされているサーバー。</span><span class="sxs-lookup"><span data-stu-id="dc70d-107">To ensure that the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries Adapter is able to communicate with a remote installation of the MQSAgent component, ensure that you have enabled network COM+ access on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]and server where IBM WebSphere MQ is installed.</span></span> <span data-ttu-id="dc70d-108">ネットワーク COM + アクセスを有効にする方法の詳細については、マイクロソフト サポート技術情報の資料 817065 を参照してください。"Windows Server 2003 でネットワーク COM + アクセスを有効にする方法」でご利用いただけます[ http://go.microsoft.com/fwlink/?LinkId=196580](http://go.microsoft.com/fwlink/?LinkId=196580)します。</span><span class="sxs-lookup"><span data-stu-id="dc70d-108">For more information about enabling network COM+ access, see Microsoft Knowledge Base article number 817065, " How to enable network COM+ access in Windows Server 2003," available at [http://go.microsoft.com/fwlink/?LinkId=196580](http://go.microsoft.com/fwlink/?LinkId=196580).</span></span>  
  
  <span data-ttu-id="dc70d-109">使用される MQSAgent (MQSAgent2) COM + アプリケーションをクラスター化する必要はありません、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries アダプター。</span><span class="sxs-lookup"><span data-stu-id="dc70d-109">There is no requirement to cluster the MQSAgent (MQSAgent2) COM+ application that is used with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries adapter.</span></span> <span data-ttu-id="dc70d-110">このコンポーネントの高可用性を実現するには、各クラスター ノードにコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="dc70d-110">To provide high availability for this component, install the component on each cluster node.</span></span> <span data-ttu-id="dc70d-111">COM + アプリケーションが停止した場合、クライアントから次の呼び出しによって開始されます。</span><span class="sxs-lookup"><span data-stu-id="dc70d-111">If the COM+ application stops, the next call from the client will start it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc70d-112">参照</span><span class="sxs-lookup"><span data-stu-id="dc70d-112">See Also</span></span>  
 [<span data-ttu-id="dc70d-113">MQSeries アダプターの使用</span><span class="sxs-lookup"><span data-stu-id="dc70d-113">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)