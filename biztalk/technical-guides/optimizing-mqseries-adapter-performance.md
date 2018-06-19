---
title: MQSeries アダプターのパフォーマンスの最適化 |Microsoft ドキュメント
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
ms.openlocfilehash: 0d4a2bd1f2cfa338d31fd574879d73249d74d08b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299130"
---
# <a name="optimizing-mqseries-adapter-performance"></a><span data-ttu-id="ca958-102">MQSeries アダプターのパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="ca958-102">Optimizing MQSeries Adapter Performance</span></span>
<span data-ttu-id="ca958-103">パフォーマンスを向上させる、可能な場合は、次の設定を使用して、MQSeries アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="ca958-103">Configure the MQSeries adapter by using the following settings when possible to increase performance.</span></span>  
  
## <a name="adjust-the-value-for-the-mqseries-receive-adapter-polling-threads"></a><span data-ttu-id="ca958-104">MQSeries 受信アダプタのポーリング スレッドの値を調整します。</span><span class="sxs-lookup"><span data-stu-id="ca958-104">Adjust the value for the MQSeries receive adapter polling threads</span></span>  
 <span data-ttu-id="ca958-105">指定された値を増やす**スレッド**で、 **MQSeries トランスポートのプロパティ**受信場所の MQSeries アダプタを構成するときにします。</span><span class="sxs-lookup"><span data-stu-id="ca958-105">Increase the value specified for **Threads** in the **MQSeries Transport Properties** when configuring MQSeries adapter receive locations.</span></span> <span data-ttu-id="ca958-106">このプロパティを既定値は 2 から 5 の値を大きくにメッセージを受信 MQSeries アダプタの使用率が大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="ca958-106">Increasing this property from the default value of 2 to a value of 5 will significantly improve the rate at which messages can be received using the MQSeries adapter.</span></span>  
  
## <a name="disable-transaction-support-on-mqseries-receive-locations-where-not-required"></a><span data-ttu-id="ca958-107">MQSeries のトランザクション サポートを無効にする受信場所必要ない場合</span><span class="sxs-lookup"><span data-stu-id="ca958-107">Disable transaction support on MQSeries receive locations where not required</span></span>  
 <span data-ttu-id="ca958-108">MQSeries アダプターのトランザクションのサポートには、大幅なオーバーヘッドが発生します。</span><span class="sxs-lookup"><span data-stu-id="ca958-108">MQSeries adapter transaction support incurs significant overhead.</span></span> <span data-ttu-id="ca958-109">トランザクションのサポートがない場合、ビジネス要件、設定、**トランザクションがサポートされている**値で、 **MQSeries トランスポートのプロパティ** ダイアログ ボックスの既定値から**をはい**に**いいえ**です。</span><span class="sxs-lookup"><span data-stu-id="ca958-109">If transaction support is not a business requirement, set the **Transaction Supported** value in the **MQSeries Transport Properties** dialog box from the default value of **Yes** to **No**.</span></span>  
  
## <a name="disable-ordered-delivery-of-messages-on-the-mqseries-adapter-when-not-required"></a><span data-ttu-id="ca958-110">不要な場合、MQSeries アダプターでメッセージの順次配送を無効にします。</span><span class="sxs-lookup"><span data-stu-id="ca958-110">Disable Ordered delivery of messages on the MQSeries Adapter when not required</span></span>  
 <span data-ttu-id="ca958-111">このプロパティを有効にするはそのままから受信した MQSeries キューに送信されるメッセージの順次配送が適用されますが、パフォーマンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="ca958-111">Enabling this property will enforce ordered delivery of messages as they are received from or sent to the MQSeries queue but will affect performance.</span></span> <span data-ttu-id="ca958-112">順次配送を有効にすると、メッセージング ランタイムは指定された MQSeries キューからメッセージを受信するのに 1 つのスレッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca958-112">When ordered delivery is enabled, the messaging runtime will use a single thread to receive messages from a given MQSeries queue.</span></span> <span data-ttu-id="ca958-113">順序付けられたメッセージの配信がビジネス要件ではないの場合、値を変更しない、既定の**Ordered**プロパティに、 **MQSeries トランスポートのプロパティ**として設定 ダイアログ ボックス**なし順序付け**です。</span><span class="sxs-lookup"><span data-stu-id="ca958-113">If ordered delivery of messages is not a business requirement, then do not change the default value of **Ordered** property in the **MQSeries Transport Properties** dialog box which is set as **No Ordering**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca958-114">参照</span><span class="sxs-lookup"><span data-stu-id="ca958-114">See Also</span></span>  
 [<span data-ttu-id="ca958-115">BizTalk Server のパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="ca958-115">Optimizing BizTalk Server Performance</span></span>](../technical-guides/optimizing-biztalk-server-performance.md)