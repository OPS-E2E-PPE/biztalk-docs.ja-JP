---
title: MQSeries アダプターのパフォーマンスの最適化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a46455c-a8d2-4427-99bb-4e3c6dbd9566
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ba12a46e17c8c521afef62e7c0ad5a9f51afe35
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291424"
---
# <a name="optimizing-mqseries-adapter-performance"></a><span data-ttu-id="1bf1d-102">MQSeries アダプターのパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="1bf1d-102">Optimizing MQSeries Adapter Performance</span></span>
<span data-ttu-id="1bf1d-103">パフォーマンスを向上させる、可能な場合は、次の設定を使用して、MQSeries アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="1bf1d-103">Configure the MQSeries adapter by using the following settings when possible to increase performance.</span></span>  
  
## <a name="adjust-the-value-for-the-mqseries-receive-adapter-polling-threads"></a><span data-ttu-id="1bf1d-104">MQSeries 受信アダプタのポーリング スレッドの値を調整します。</span><span class="sxs-lookup"><span data-stu-id="1bf1d-104">Adjust the value for the MQSeries receive adapter polling threads</span></span>  
 <span data-ttu-id="1bf1d-105">指定された値を増やす**スレッド**で、 **MQSeries トランスポートのプロパティ**受信場所が MQSeries アダプターを構成する場合。</span><span class="sxs-lookup"><span data-stu-id="1bf1d-105">Increase the value specified for **Threads** in the **MQSeries Transport Properties** when configuring MQSeries adapter receive locations.</span></span> <span data-ttu-id="1bf1d-106">このプロパティを既定値の 2 から 5 の値に増やすことがメッセージを受信できる MQSeries アダプターの使用率が大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="1bf1d-106">Increasing this property from the default value of 2 to a value of 5 will significantly improve the rate at which messages can be received using the MQSeries adapter.</span></span>  
  
## <a name="disable-transaction-support-on-mqseries-receive-locations-where-not-required"></a><span data-ttu-id="1bf1d-107">受信場所の MQSeries のトランザクション サポートを無効にする必要ない場合</span><span class="sxs-lookup"><span data-stu-id="1bf1d-107">Disable transaction support on MQSeries receive locations where not required</span></span>  
 <span data-ttu-id="1bf1d-108">MQSeries アダプターのトランザクション サポートでは、かなりのオーバーヘッドが発生します。</span><span class="sxs-lookup"><span data-stu-id="1bf1d-108">MQSeries adapter transaction support incurs significant overhead.</span></span> <span data-ttu-id="1bf1d-109">トランザクションのサポートがビジネス要件ではない場合、設定、**トランザクションがサポートされている**値、 **MQSeries トランスポートのプロパティ** ダイアログ ボックスの既定値から**はい**に**いいえ**します。</span><span class="sxs-lookup"><span data-stu-id="1bf1d-109">If transaction support is not a business requirement, set the **Transaction Supported** value in the **MQSeries Transport Properties** dialog box from the default value of **Yes** to **No**.</span></span>  
  
## <a name="disable-ordered-delivery-of-messages-on-the-mqseries-adapter-when-not-required"></a><span data-ttu-id="1bf1d-110">不要な場合は、MQSeries アダプターに関するメッセージの順次配送を無効にします。</span><span class="sxs-lookup"><span data-stu-id="1bf1d-110">Disable Ordered delivery of messages on the MQSeries Adapter when not required</span></span>  
 <span data-ttu-id="1bf1d-111">このプロパティを有効にするから受信したか、または、MQSeries キューに送信とメッセージの順次配送が適用されますが、パフォーマンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="1bf1d-111">Enabling this property will enforce ordered delivery of messages as they are received from or sent to the MQSeries queue but will affect performance.</span></span> <span data-ttu-id="1bf1d-112">順次配送を有効にすると、メッセージング ランタイムは、特定の MQSeries キューからメッセージを受信するのに 1 つのスレッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="1bf1d-112">When ordered delivery is enabled, the messaging runtime will use a single thread to receive messages from a given MQSeries queue.</span></span> <span data-ttu-id="1bf1d-113">メッセージの配信は、ビジネス要件ではありませんが注文された場合、値を変更しない、既定の**Ordered**プロパティ、 **MQSeries トランスポートのプロパティ** ダイアログ ボックスとして設定された**なし順序付け**します。</span><span class="sxs-lookup"><span data-stu-id="1bf1d-113">If ordered delivery of messages is not a business requirement, then do not change the default value of **Ordered** property in the **MQSeries Transport Properties** dialog box which is set as **No Ordering**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bf1d-114">参照</span><span class="sxs-lookup"><span data-stu-id="1bf1d-114">See Also</span></span>  
 [<span data-ttu-id="1bf1d-115">BizTalk Server パフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="1bf1d-115">Optimizing BizTalk Server Performance</span></span>](../technical-guides/optimizing-biztalk-server-performance.md)