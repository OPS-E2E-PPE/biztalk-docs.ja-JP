---
title: EPM スレッド プール サイズを設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e170e76-5151-4306-9473-5b68e815219a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54afa88b51876d0ee56f548f263be1b00c37967a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271138"
---
# <a name="setting-the-epm-threadpool-size"></a><span data-ttu-id="3af18-102">EPM スレッドプール サイズの設定</span><span class="sxs-lookup"><span data-stu-id="3af18-102">Setting the EPM Threadpool Size</span></span>
<span data-ttu-id="3af18-103">このトピックでは、エンド ポイント マネージャー (EPM) のスレッドプール サイズの設定方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3af18-103">This topic explains how to set the threadpool size for the End Point Manager (EPM).</span></span>  
  
 <span data-ttu-id="3af18-104">**詳細** タブで、**ホストのプロパティ**ダイアログ ボックスで、というプロパティがある**CPU あたりのスレッドをメッセージング エンジンの最大数**です。</span><span class="sxs-lookup"><span data-stu-id="3af18-104">On the **Advanced** tab in the **Host Properties** dialog box, there is a property called **Maximum number of messaging engine threads per CPU**.</span></span> <span data-ttu-id="3af18-105">このダイアログ ボックスにアクセスする方法については、次を参照してください。[を新しいホストを作成する方法](../core/how-to-create-a-new-host.md)です。</span><span class="sxs-lookup"><span data-stu-id="3af18-105">For instructions about accessing this dialog box, see [How to Create a New Host](../core/how-to-create-a-new-host.md).</span></span> <span data-ttu-id="3af18-106">このプロパティを使用すると、メッセージを処理するためにメッセージング エンジンが使用するプロセス スレッドのプールのサイズを制御できます。</span><span class="sxs-lookup"><span data-stu-id="3af18-106">Use this property to control the size of the pool of process threads that the messaging engine uses to process messages.</span></span> <span data-ttu-id="3af18-107">このプロパティの既定値は 20 です。つまり、サーバー上の CPU ごとに最大 20 個のスレッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3af18-107">The default value for this property is 20, meaning that the messaging engine will use no more than 20 threads for each CPU on the server.</span></span>  
  
 <span data-ttu-id="3af18-108">各スレッド プールでは、メッセージのバッチが処理される、ための値を調整する**CPU あたりのスレッドをメッセージング エンジンの最大数**サーバー上のリソース使用のダイナミクスを変更することでパフォーマンスに影響することができます。</span><span class="sxs-lookup"><span data-stu-id="3af18-108">Since batches of messages are processed by each thread in the pool, adjusting the value of **Maximum number of messaging engine threads per CPU** can affect performance by changing the dynamics of resource utilization on the server.</span></span> <span data-ttu-id="3af18-109">Threadpool のしくみの詳細については、次を参照してください。 [BizTalk メッセージング エンジンを使用して](../core/using-the-biztalk-messaging-engine.md)です。</span><span class="sxs-lookup"><span data-stu-id="3af18-109">For more information about how the threadpool works, see [Using the BizTalk Messaging Engine](../core/using-the-biztalk-messaging-engine.md).</span></span>  
  
 <span data-ttu-id="3af18-110">テストによれば、または SQL サーバーの CPU が過負荷の場合の値を小さく**CPU あたりのスレッドをメッセージング エンジンの最大数**スループットが向上になります。</span><span class="sxs-lookup"><span data-stu-id="3af18-110">Testing has shown that in cases where the CPU or the SQL Server is over utilized, decreasing the value of **Maximum number of messaging engine threads per CPU** can result in a net gain in throughput.</span></span> <span data-ttu-id="3af18-111">たとえば、メッセージ ボックス データベース サーバーで CPU の使用率が 90% 以上と示されている場合、または SQL のロック待機時間が 500 ～ 1000 ミリ秒以上に上がった場合、プールのスレッド数が減り、SQL Server に接続している全体の接続数が少なくなります。このため、効率的なメッセージ処理が実現します。</span><span class="sxs-lookup"><span data-stu-id="3af18-111">For example, in cases where the MessageBox database server exhibits CPU utilization above 90% or the SQL lock wait times are elevated above 500-1000 milliseconds, reducing the number of threads in the pool will reduce the overall number connections being made to SQL Server, which results in more efficient message processing.</span></span> <span data-ttu-id="3af18-112">最大スレッド プール サイズを 2 に設定すると、明確なスループットの向上が実現する場合があります。</span><span class="sxs-lookup"><span data-stu-id="3af18-112">In some cases, setting the maximum thread pool size to a value as low as 2 can result in measurable throughput gain.</span></span>  
  
## <a name="recommendation"></a><span data-ttu-id="3af18-113">推奨</span><span class="sxs-lookup"><span data-stu-id="3af18-113">Recommendation</span></span>  
 <span data-ttu-id="3af18-114">BizTalk Server のインストールを最適化するときは、設定した値を調整微調整することをお勧め**CPU あたりのスレッドをメッセージング エンジンの最大数**です。</span><span class="sxs-lookup"><span data-stu-id="3af18-114">When optimizing a BizTalk Server installation, it is recommended that you fine tune the value you set for **Maximum number of messaging engine threads per CPU**.</span></span>  <span data-ttu-id="3af18-115">メッセージ ボックス データベース サーバーを使用する割合を減らす場合は、このプロパティの値を小さくすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="3af18-115">When you try to reduce the utilization of the MessageBox database server, consider reducing the value of this property.</span></span>  
  
 <span data-ttu-id="3af18-116">BizTalk server またはメッセージ ボックス データベース サーバーがない使用率の高い、追加の負荷を適用することは行われませんスループットがさらに、再試行の値を大きく**CPU あたりのスレッドをメッセージング エンジンの最大数**過小使用されたリソースの利用します。</span><span class="sxs-lookup"><span data-stu-id="3af18-116">When the BizTalk server or the MessageBox database server is not highly utilized, and applying additional load does not result in additional throughput, try increasing the value of **Maximum number of messaging engine threads per CPU** to take advantage of underutilized resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3af18-117">参照</span><span class="sxs-lookup"><span data-stu-id="3af18-117">See Also</span></span>  
 <span data-ttu-id="3af18-118">[新しいホストを作成する方法](../core/how-to-create-a-new-host.md) </span><span class="sxs-lookup"><span data-stu-id="3af18-118">[How to Create a New Host](../core/how-to-create-a-new-host.md) </span></span>  
 [<span data-ttu-id="3af18-119">BizTalk メッセージング エンジンを使用します。</span><span class="sxs-lookup"><span data-stu-id="3af18-119">Using the BizTalk Messaging Engine</span></span>](../core/using-the-biztalk-messaging-engine.md)