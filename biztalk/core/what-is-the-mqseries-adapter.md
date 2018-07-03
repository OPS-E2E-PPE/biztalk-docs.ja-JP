---
title: MQSeries アダプターとは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, about MQSeries adapters
- MQSeries adapters
ms.assetid: fd3dfa9a-344a-46e5-a342-bc56da7c1c50
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ecc25d09e94ab4e5238c1d4dab4e36745916a93
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991611"
---
# <a name="what-is-the-mqseries-adapter"></a><span data-ttu-id="bbe1f-103">MQSeries アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-103">What Is the MQSeries Adapter?</span></span>
<span data-ttu-id="bbe1f-104">MQSeries アダプターを使用すると、MQSeries システムに対するメッセージの送受信を Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-104">With the MQSeries adapter you can send and receive messages to MQSeries systems using Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="bbe1f-105">このアダプターは、MQSeries Server for Windows に依存しています。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-105">The adapter relies on MQSeries Server for Windows.</span></span> <span data-ttu-id="bbe1f-106">MQSeries Server for Windows が Microsoft 分散トランザクション コーディネーター (MSDTC) をサポートしているため、この依存関係によって信頼性の高いメッセージングが保証されます。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-106">This design guarantees reliable messaging because MQSeries Server for Windows supports Microsoft Distributed Transaction Coordinator (MSDTC).</span></span>  
  
 <span data-ttu-id="bbe1f-107">アダプターでは、クラスター化された MQSeries Server、クラスター化された MQSeries キュー マネージャーに加え、クラスター化された BizTalk Server もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-107">The adapter supports clustered MQSeries Servers and clustered MQSeries Queue Managers, and also clustered BizTalk servers.</span></span>  
  
 <span data-ttu-id="bbe1f-108">MQSeries アダプターでは、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-108">You can do the following with the MQSeries adapter:</span></span>  
  
- <span data-ttu-id="bbe1f-109">メッセージを、BizTalk Server から MQSeries のリモート定義のキュー、ローカル キュー、転送キュー、およびエイリアス キューに送信します。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-109">Send messages to MQSeries remote definition queues, local queues, transmission queues, and alias queues from BizTalk Server.</span></span>  
  
- <span data-ttu-id="bbe1f-110">MQSeries の転送キュー、ローカル キュー、およびエイリアス キューからメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-110">Receive messages from MQSeries transmission queues, local queues, and alias queues.</span></span>  
  
- <span data-ttu-id="bbe1f-111">MQSeries Server for Windows からのメッセージを送受信します (MQSeries Server は、BizTalk Server と同じコンピューターまたはリモート インストールで実行できます)。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-111">Send and receive messages from MQSeries Server for Windows (MQSeries Server can run on the same computer as BizTalk Server or on a remote installation).</span></span> <span data-ttu-id="bbe1f-112">MQSAgent (アダプターの COM+ コンポーネント) のコピーを 1 つ配置するだけで、BizTalk Server のすべてのインストールがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-112">You only have to deploy one copy of MQSAgent (the COM+ component of the adapter) to support all your BizTalk Server installations.</span></span>  
  
- <span data-ttu-id="bbe1f-113">待機間隔を指定して MQSeries Server をポーリングします。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-113">Poll MQSeries Server with a wait interval.</span></span>  
  
- <span data-ttu-id="bbe1f-114">動的送信ポートを使用してアダプターを制御します。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-114">Use dynamic send ports to control the adapter.</span></span>  
  
- <span data-ttu-id="bbe1f-115">実行時にキューを動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-115">Dynamically create queues at run time.</span></span>  
  
- <span data-ttu-id="bbe1f-116">MQSeries MatchOptions に基づいてキューからメッセージを動的に受信します。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-116">Dynamically receive messages from queues based upon MQSeries MatchOptions.</span></span>  
  
- <span data-ttu-id="bbe1f-117">メッセージの送信と受信のどちらも、コンテキスト プロパティをヘッダー プロパティにマップします。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-117">Map context properties to header properties for both transmitting and receiving messages.</span></span> <span data-ttu-id="bbe1f-118">MQSeries ヘッダー プロパティ (MQMD、MQXQH、MQCIH、MQIIH など) は、BizTalk Server コンテキスト プロパティを使用して取得および設定できます。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-118">You can get and set MQSeries header properties (including MQMD, MQXQH, MQCIH, and MQIIH) through BizTalk Server context properties.</span></span>  
  
- <span data-ttu-id="bbe1f-119">関連付け識別子を作成して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] または MQSeries Server との関連付けを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-119">Enable correlation with either [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or MQSeries Server creating the correlation identifier.</span></span>  
  
- <span data-ttu-id="bbe1f-120">送信メッセージのトランザクションおよび非トランザクション配信を要求して受信します。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-120">Request transactional and nontransactional delivery of messages for send and receive.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bbe1f-121">分散コンポーネント オブジェクト モデル (DCOM) によるサーバーの呼び出しを可能にする MQSeries などの機能を使用する際は、ネットワーク アドレス変換 (NAT) ベースのファイアウォールが無効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-121">When using features such as MQSeries which make Distributed Component Object Model (DCOM) calls to the server, make sure you do not have a Network Address Translation (NAT)-based firewall enabled.</span></span> <span data-ttu-id="bbe1f-122">クライアントは、実際の IP アドレスを使用してサーバーにアクセスできる必要があり、NAT ベースのファイアウォールによって、このアドレスはクライアントが認識できないように変換されます。</span><span class="sxs-lookup"><span data-stu-id="bbe1f-122">The client must be able to access the server by its actual IP address, and NAT-based firewalls translate this address to something the client will not recognize.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bbe1f-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bbe1f-123">In This Section</span></span>  
  
-   [<span data-ttu-id="bbe1f-124">MQSeries アダプターのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="bbe1f-124">Components of the MQSeries Adapter</span></span>](../core/components-of-the-mqseries-adapter.md)  
  
-   [<span data-ttu-id="bbe1f-125">MQSeries アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="bbe1f-125">MQSeries Adapter Architecture</span></span>](../core/mqseries-adapter-architecture.md)  
  
-   [<span data-ttu-id="bbe1f-126">MQSeries アダプターの使用</span><span class="sxs-lookup"><span data-stu-id="bbe1f-126">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)  
  
-   [<span data-ttu-id="bbe1f-127">MQSeries アダプターのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="bbe1f-127">MQSeries Adapter Security</span></span>](../core/mqseries-adapter-security.md)