---
title: 複数の MSMQ アダプターを使用して場所の受信を管理する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, receive locations
- MSMQ adapters, threads
- receive locations, multiple
- threads
- receive locations, MSMQ adapters
- receive locations, threads
- configuring [MSMQ adapters], receive locations
ms.assetid: 5b2ee043-bcc9-443b-84b0-df7f487159eb
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b46ab60e3e5073c7c487ffb530dbc0407b0444f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384707"
---
# <a name="how-to-manage-multiple-receive-locations-using-the-msmq-adapter"></a><span data-ttu-id="cb3e4-102">複数の MSMQ アダプターを使用して場所の受信を管理する方法</span><span class="sxs-lookup"><span data-stu-id="cb3e4-102">How to Manage Multiple Receive Locations Using the MSMQ Adapter</span></span>
<span data-ttu-id="cb3e4-103">パフォーマンスを向上させるのには、MSMQ アダプターがマルチ スレッドです。</span><span class="sxs-lookup"><span data-stu-id="cb3e4-103">To increase performance, the MSMQ adapter is multithreaded.</span></span> <span data-ttu-id="cb3e4-104">多くの受信場所があれば、ある可能性がありますいないのに十分なスレッドすべての受信場所の使用可能です。</span><span class="sxs-lookup"><span data-stu-id="cb3e4-104">If you have many receive locations, there may not be enough threads available for all the receive locations.</span></span> <span data-ttu-id="cb3e4-105">これは、いくつかの受信場所でメッセージを取得できないようにします。</span><span class="sxs-lookup"><span data-stu-id="cb3e4-105">This prevents some of the receive locations from picking up messages.</span></span> <span data-ttu-id="cb3e4-106">この問題を解決するために 3 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="cb3e4-106">There are three ways to solve this problem:</span></span>  
  
-   <span data-ttu-id="cb3e4-107">お使いのコンピューターに BizTalk ホストを追加し、ホスト間で受信場所を分割します。</span><span class="sxs-lookup"><span data-stu-id="cb3e4-107">Add BizTalk Hosts to your computer and divide the receive locations among the hosts.</span></span> <span data-ttu-id="cb3e4-108">受信場所の使用可能な多くのスレッドは、ホストを追加します。</span><span class="sxs-lookup"><span data-stu-id="cb3e4-108">Adding hosts makes more threads available for the receive locations.</span></span>  
  
-   <span data-ttu-id="cb3e4-109">設定、**シリアル処理**プロパティを`True`各受信場所。</span><span class="sxs-lookup"><span data-stu-id="cb3e4-109">Set the **Serial Processing** property to `True` on each receive location.</span></span> <span data-ttu-id="cb3e4-110">プロパティを設定する`True`受信場所の 1 つのスレッドのそれぞれに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="cb3e4-110">Setting the property to `True` assigns a single thread to each receive location.</span></span> <span data-ttu-id="cb3e4-111">これにより、プールで使用可能な多くのスレッドが残ります。</span><span class="sxs-lookup"><span data-stu-id="cb3e4-111">This leaves more threads available in the pool.</span></span> <span data-ttu-id="cb3e4-112">ただし、パフォーマンスの低下がありますも。</span><span class="sxs-lookup"><span data-stu-id="cb3e4-112">However, this may also cause a decrease in performance.</span></span>  
  
-   <span data-ttu-id="cb3e4-113">MSMQ アダプターの受信ハンドラーのホストに利用できるスレッドの数を増やすにレジストリを変更します。</span><span class="sxs-lookup"><span data-stu-id="cb3e4-113">Modify the registry to increase the number of threads that are available to the host for the MSMQ adapter receive handler.</span></span> <span data-ttu-id="cb3e4-114">詳細については、次を参照してください。、**ホスト用 CLR Hosting スレッド値を変更**の[構成パラメーターを アダプターのパフォーマンスの影響を与える](../core/configuration-parameters-that-affect-adapter-performance.md)します。</span><span class="sxs-lookup"><span data-stu-id="cb3e4-114">For more information see the **Modify the CLR Hosting thread values for the host** section of [Configuration Parameters that Affect Adapter Performance](../core/configuration-parameters-that-affect-adapter-performance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb3e4-115">参照</span><span class="sxs-lookup"><span data-stu-id="cb3e4-115">See Also</span></span>  
 [<span data-ttu-id="cb3e4-116">MSMQ アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="cb3e4-116">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)