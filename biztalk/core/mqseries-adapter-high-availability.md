---
title: MQSeries アダプターの高可用性 |Microsoft ドキュメント
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
ms.openlocfilehash: 21c0b6486e49cb2ccddfab37271a94a4ba7a6948
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263234"
---
# <a name="mqseries-adapter-high-availability"></a><span data-ttu-id="b7774-102">MQSeries アダプターの高可用性</span><span class="sxs-lookup"><span data-stu-id="b7774-102">MQSeries Adapter High Availability</span></span>
<span data-ttu-id="b7774-103">MQSeries アダプターを使用する場合、次に示すいくつかの方法で可用性を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="b7774-103">You can improve availability in the following ways when you use the adapter:</span></span>  
  
-   <span data-ttu-id="b7774-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用にフォールト トレランスのホスティング環境を設定します。</span><span class="sxs-lookup"><span data-stu-id="b7774-104">Set up a fault-tolerant hosting environment for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="b7774-105">IBM WebSphere MQ で Windows クラスタリングを使用します。</span><span class="sxs-lookup"><span data-stu-id="b7774-105">Use Windows Clustering with IBM WebSphere MQ.</span></span>  
  
 <span data-ttu-id="b7774-106">フォールト トレランスについておよび[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)と[フォールト トレランスのため、プラットフォームの計画](../core/planning-your-platform-for-fault-tolerance.md)で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="b7774-106">For information about fault tolerance and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md) and [Planning Your Platform for Fault Tolerance](../core/planning-your-platform-for-fault-tolerance.md) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="b7774-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries アダプターが MQSAgent コンポーネントのリモート インストールと通信できるようにするには、IBM WebSphere MQ がインストールされている [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] およびサーバー上でネットワーク COM+ アクセスを有効にしておいてください。</span><span class="sxs-lookup"><span data-stu-id="b7774-107">To ensure that the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries Adapter is able to communicate with a remote installation of the MQSAgent component, ensure that you have enabled network COM+ access on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]and server where IBM WebSphere MQ is installed.</span></span> <span data-ttu-id="b7774-108">ネットワーク COM + アクセスを有効にする方法の詳細については、Microsoft サポート技術情報の資料 817065 を参照してください。"Windows Server 2003 でネットワーク COM + アクセスを有効にする方法」で利用可能な[http://go.microsoft.com/fwlink/?LinkId=196580](http://go.microsoft.com/fwlink/?LinkId=196580)です。</span><span class="sxs-lookup"><span data-stu-id="b7774-108">For more information about enabling network COM+ access, see Microsoft Knowledge Base article number 817065, " How to enable network COM+ access in Windows Server 2003," available at [http://go.microsoft.com/fwlink/?LinkId=196580](http://go.microsoft.com/fwlink/?LinkId=196580).</span></span>  
  
 <span data-ttu-id="b7774-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries アダプターと共に使用される MQSAgent (MQSAgent2) COM+ アプリケーションをクラスター化するための要件はありません。</span><span class="sxs-lookup"><span data-stu-id="b7774-109">There is no requirement to cluster the MQSAgent (MQSAgent2) COM+ application that is used with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries adapter.</span></span> <span data-ttu-id="b7774-110">このコンポーネントの高可用性を確保するためには、各クラスター ノードにコンポーネントをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="b7774-110">To provide high availability for this component, install the component on each cluster node.</span></span> <span data-ttu-id="b7774-111">COM+ アプリケーションが停止した場合、クライアントから次に呼び出されたときに開始されます。</span><span class="sxs-lookup"><span data-stu-id="b7774-111">If the COM+ application stops, the next call from the client will start it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7774-112">参照</span><span class="sxs-lookup"><span data-stu-id="b7774-112">See Also</span></span>  
 [<span data-ttu-id="b7774-113">MQSeries アダプタの使用</span><span class="sxs-lookup"><span data-stu-id="b7774-113">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)