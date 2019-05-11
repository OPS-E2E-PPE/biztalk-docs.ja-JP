---
title: EPM スレッド プールのサイズの設定 |Microsoft Docs
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
ms.openlocfilehash: 0eeb755b7fbee5939510e9e3fae0bb8868f91611
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393242"
---
# <a name="setting-the-epm-threadpool-size"></a><span data-ttu-id="4b4fc-102">EPM スレッドプール サイズの設定</span><span class="sxs-lookup"><span data-stu-id="4b4fc-102">Setting the EPM Threadpool Size</span></span>
<span data-ttu-id="4b4fc-103">このトピックでは、エンド ポイント マネージャー (EPM) のスレッド プール サイズを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b4fc-103">This topic explains how to set the threadpool size for the End Point Manager (EPM).</span></span>  
  
 <span data-ttu-id="4b4fc-104">**詳細設定**  タブで、**ホストのプロパティ**ダイアログ ボックスで、という名前のプロパティがある**CPU ごとのメッセージング エンジンの最大数のスレッド**します。</span><span class="sxs-lookup"><span data-stu-id="4b4fc-104">On the **Advanced** tab in the **Host Properties** dialog box, there is a property called **Maximum number of messaging engine threads per CPU**.</span></span> <span data-ttu-id="4b4fc-105">このダイアログ ボックスにアクセスする方法については、次を参照してください。[新しいホストを作成する方法](../core/how-to-create-a-new-host.md)します。</span><span class="sxs-lookup"><span data-stu-id="4b4fc-105">For instructions about accessing this dialog box, see [How to Create a New Host](../core/how-to-create-a-new-host.md).</span></span> <span data-ttu-id="4b4fc-106">このプロパティを使用して、メッセージング エンジンを使用してメッセージを処理するプロセスのスレッドのプールのサイズを制御します。</span><span class="sxs-lookup"><span data-stu-id="4b4fc-106">Use this property to control the size of the pool of process threads that the messaging engine uses to process messages.</span></span> <span data-ttu-id="4b4fc-107">既定値 20 をこのプロパティには、つまり、メッセージング エンジンが、サーバー上の各 CPU の最大 20 個のスレッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b4fc-107">The default value for this property is 20, meaning that the messaging engine will use no more than 20 threads for each CPU on the server.</span></span>  
  
 <span data-ttu-id="4b4fc-108">各スレッド プールでは、メッセージのバッチが処理される、ための値を調整する**CPU ごとのメッセージング エンジンの最大数のスレッド**サーバー上のリソース使用率のダイナミクスを変更することで、パフォーマンスに影響を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="4b4fc-108">Since batches of messages are processed by each thread in the pool, adjusting the value of **Maximum number of messaging engine threads per CPU** can affect performance by changing the dynamics of resource utilization on the server.</span></span> <span data-ttu-id="4b4fc-109">スレッド プールの機能の詳細については、次を参照してください。 [BizTalk メッセージング エンジンを使用して](../core/using-the-biztalk-messaging-engine.md)します。</span><span class="sxs-lookup"><span data-stu-id="4b4fc-109">For more information about how the threadpool works, see [Using the BizTalk Messaging Engine](../core/using-the-biztalk-messaging-engine.md).</span></span>  
  
 <span data-ttu-id="4b4fc-110">テストによれば、または SQL サーバーの CPU が過負荷の場合の値を小さく**CPU ごとのメッセージング エンジンの最大数のスレッド**により、スループットが向上します。</span><span class="sxs-lookup"><span data-stu-id="4b4fc-110">Testing has shown that in cases where the CPU or the SQL Server is over utilized, decreasing the value of **Maximum number of messaging engine threads per CPU** can result in a net gain in throughput.</span></span> <span data-ttu-id="4b4fc-111">たとえば、メッセージ ボックス データベース サーバーが CPU を示す場合 90% または SQL のロック待機時間は、プール内のスレッドの数を減らして、500-1000 ミリ秒を超える昇格上記の使用率が減少 SQL に対して行われる全体的な数の接続サーバーより効率的なメッセージ処理の結果します。</span><span class="sxs-lookup"><span data-stu-id="4b4fc-111">For example, in cases where the MessageBox database server exhibits CPU utilization above 90% or the SQL lock wait times are elevated above 500-1000 milliseconds, reducing the number of threads in the pool will reduce the overall number connections being made to SQL Server, which results in more efficient message processing.</span></span> <span data-ttu-id="4b4fc-112">場合によっては、最大スレッド プールのサイズに値を設定 2 は測定可能なスループットの向上につながる低くします。</span><span class="sxs-lookup"><span data-stu-id="4b4fc-112">In some cases, setting the maximum thread pool size to a value as low as 2 can result in measurable throughput gain.</span></span>  
  
## <a name="recommendation"></a><span data-ttu-id="4b4fc-113">推奨</span><span class="sxs-lookup"><span data-stu-id="4b4fc-113">Recommendation</span></span>  
 <span data-ttu-id="4b4fc-114">BizTalk Server のインストールを最適化するときは、設定した値を調整して微調整することをお勧め**CPU ごとのメッセージング エンジンの最大数のスレッド**します。</span><span class="sxs-lookup"><span data-stu-id="4b4fc-114">When optimizing a BizTalk Server installation, it is recommended that you fine tune the value you set for **Maximum number of messaging engine threads per CPU**.</span></span>  <span data-ttu-id="4b4fc-115">メッセージ ボックス データベース サーバーの使用率を低減しようとすると、このプロパティの値を減らすことを検討します。</span><span class="sxs-lookup"><span data-stu-id="4b4fc-115">When you try to reduce the utilization of the MessageBox database server, consider reducing the value of this property.</span></span>  
  
 <span data-ttu-id="4b4fc-116">BizTalk server またはメッセージ ボックス データベース サーバーに高くならなければ、および追加の負荷を適用することは、追加のスループットはされることはありません、ときにの値を増やすことをお試しください**CPU ごとのメッセージング エンジンの最大数のスレッド**過小使用されたリソースの利用します。</span><span class="sxs-lookup"><span data-stu-id="4b4fc-116">When the BizTalk server or the MessageBox database server is not highly utilized, and applying additional load does not result in additional throughput, try increasing the value of **Maximum number of messaging engine threads per CPU** to take advantage of underutilized resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b4fc-117">参照</span><span class="sxs-lookup"><span data-stu-id="4b4fc-117">See Also</span></span>  
 <span data-ttu-id="4b4fc-118">[新しいホストを作成する方法](../core/how-to-create-a-new-host.md) </span><span class="sxs-lookup"><span data-stu-id="4b4fc-118">[How to Create a New Host](../core/how-to-create-a-new-host.md) </span></span>  
 [<span data-ttu-id="4b4fc-119">BizTalk メッセージング エンジンを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b4fc-119">Using the BizTalk Messaging Engine</span></span>](../core/using-the-biztalk-messaging-engine.md)