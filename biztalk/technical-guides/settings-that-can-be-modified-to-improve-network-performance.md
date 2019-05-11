---
title: ネットワーク パフォーマンスを向上させる変更可能な設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb6aacc3-e697-4cc9-b937-73a2f54e733b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 363597ca798abcaa4a75a7c1c1df8568b439001d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65278987"
---
# <a name="settings-that-can-be-modified-to-improve-network-performance"></a><span data-ttu-id="f04bc-102">ネットワーク パフォーマンスを向上させる変更可能な設定</span><span class="sxs-lookup"><span data-stu-id="f04bc-102">Settings that can be Modified to Improve Network Performance</span></span>
<span data-ttu-id="f04bc-103">このトピックでは、ネットワーク パフォーマンスに影響する推奨値の説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="f04bc-103">This topic provides a description of recommended values   that impact network performance.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f04bc-104">このガイドを完了したパフォーマンスのテスト中には、既定でチューニングする Windows Server 2008 が表示されることがわかりました。</span><span class="sxs-lookup"><span data-stu-id="f04bc-104">During performance testing completed for this guide it was observed that Windows Server 2008 appears to be tuned by default.</span></span> <span data-ttu-id="f04bc-105">レジストリ設定の変更は、システムへの影響を慎重に分析した後にのみ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f04bc-105">Modification of  registry settings should only be done after a careful analysis of the effects on the system.</span></span>  
  
## <a name="adjust-the-maxuserport-and-tcptimedwaitdelay-settings"></a><span data-ttu-id="f04bc-106">MaxUserPort と TcpTimedWaitDelay 設定を調整します。</span><span class="sxs-lookup"><span data-stu-id="f04bc-106">Adjust the MaxUserPort and TcpTimedWaitDelay settings</span></span>  
 <span data-ttu-id="f04bc-107">**MaxUserPort**値アプリケーションは、システムから利用可能なユーザーの任意のポートを要求するときに使用される最大ポート数を制御します。</span><span class="sxs-lookup"><span data-stu-id="f04bc-107">The **MaxUserPort** value controls the maximum port number used when an application requests any available user port from the system.</span></span> <span data-ttu-id="f04bc-108">通常、有効期間が短いポートは、1025 65535 までからの範囲で割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f04bc-108">Normally, short-lived ports are allocated in the range from 1025 through 65535.</span></span> <span data-ttu-id="f04bc-109">ポートの範囲は、本当に範囲の開始点と、エンドポイントではようになりました。</span><span class="sxs-lookup"><span data-stu-id="f04bc-109">The port range is now truly a range with a starting point and with an endpoint.</span></span> <span data-ttu-id="f04bc-110">新しい既定の開始ポートは 49152、および既定の終了ポートは 65535 です。</span><span class="sxs-lookup"><span data-stu-id="f04bc-110">The new default start port is 49152, and the default end port is 65535.</span></span> <span data-ttu-id="f04bc-111">この範囲は、アプリケーションとサービスによって使用される既知のポートだけでなく、します。</span><span class="sxs-lookup"><span data-stu-id="f04bc-111">This range is in addition to well-known ports that are used by services and by applications.</span></span> <span data-ttu-id="f04bc-112">各サーバーでは、サーバーで使用するポートの範囲を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f04bc-112">The port range that is used by the servers can be modified on each server.</span></span> <span data-ttu-id="f04bc-113">次のように、netsh コマンドを使用して、この範囲を調整します。</span><span class="sxs-lookup"><span data-stu-id="f04bc-113">You adjust this range by using the netsh command, as follows:</span></span>  
  
 <span data-ttu-id="f04bc-114">**netsh int \<ipv4&#124;ipv6\> set dynamicport \<tcp&#124;udp\> start=number num=range**</span><span class="sxs-lookup"><span data-stu-id="f04bc-114">**netsh int \<ipv4&#124;ipv6\> set dynamicport \<tcp&#124;udp\> start=number num=range**</span></span>  
  
 <span data-ttu-id="f04bc-115">このコマンドは、tcp 動的ポートの範囲を設定します。</span><span class="sxs-lookup"><span data-stu-id="f04bc-115">This command sets the dynamic port range for TCP.</span></span> <span data-ttu-id="f04bc-116">開始ポート アドレスが**数**、ポートの合計数は**範囲**します。</span><span class="sxs-lookup"><span data-stu-id="f04bc-116">The start port is **number**, and the total number of ports is **range**.</span></span> <span data-ttu-id="f04bc-117">サンプル コマンドは、次のように。動的ポートの範囲を表示するには、次の netsh コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f04bc-117">The following are sample commands: You can view the dynamic port range by using the following netsh commands:</span></span>  
  
- <span data-ttu-id="f04bc-118">netsh int ipv4 では、動的 tcp を表示します。</span><span class="sxs-lookup"><span data-stu-id="f04bc-118">netsh int ipv4 show dynamicport tcp.</span></span> <span data-ttu-id="f04bc-119">Tcp v4 の最大許容値の範囲を向上させるのには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f04bc-119">To increase the range to the maximum allowed value for tcp v4, use the following command:</span></span>  
  
   <span data-ttu-id="f04bc-120">**netsh int ipv4 set dynamicport tcp start=1025 num=64511**</span><span class="sxs-lookup"><span data-stu-id="f04bc-120">**netsh int ipv4 set dynamicport tcp start=1025 num=64511**</span></span>  
  
- <span data-ttu-id="f04bc-121">netsh int ipv4 動的 udp を表示します。</span><span class="sxs-lookup"><span data-stu-id="f04bc-121">netsh int ipv4 show dynamicport udp</span></span>  
  
- <span data-ttu-id="f04bc-122">netsh int ipv6 が動的 tcp を表示します。</span><span class="sxs-lookup"><span data-stu-id="f04bc-122">netsh int ipv6 show dynamicport tcp</span></span>  
  
- <span data-ttu-id="f04bc-123">netsh int ipv6 動的 udp を表示します。</span><span class="sxs-lookup"><span data-stu-id="f04bc-123">netsh int ipv6 show dynamicport udp</span></span>  
  
  <span data-ttu-id="f04bc-124">**TcpTimedWaitDelay**値が閉じられるときに、接続が TIME_WAIT 状態で保持される時間の長さを決定します。</span><span class="sxs-lookup"><span data-stu-id="f04bc-124">The **TcpTimedWaitDelay** value determines the length of time that a connection stays in the TIME_WAIT state when being closed.</span></span> <span data-ttu-id="f04bc-125">接続が TIME_WAIT 状態にある間は、ソケット ペアを再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f04bc-125">While a connection is in the TIME_WAIT state, the socket pair cannot be reused.</span></span> <span data-ttu-id="f04bc-126">これは、値が、ネットワークのセグメントの最大有効期間 2 倍にする必要があります 2 msl 状態とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f04bc-126">This is also known as the 2MSL state because the value should be twice the maximum segment lifetime on the network.</span></span> <span data-ttu-id="f04bc-127">詳細については、次を参照してください。[インターネット RFC 793](http://go.microsoft.com/fwlink/?LinkId=113719) (HYPERLINK"<http://go.microsoft.com/fwlink/?LinkId=113719>" <http://go.microsoft.com/fwlink/?LinkId=113719>)。</span><span class="sxs-lookup"><span data-stu-id="f04bc-127">For more information, see [Internet RFC 793](http://go.microsoft.com/fwlink/?LinkId=113719) ( HYPERLINK "<http://go.microsoft.com/fwlink/?LinkId=113719>" <http://go.microsoft.com/fwlink/?LinkId=113719>).</span></span> <span data-ttu-id="f04bc-128">TcpTimedWaitDelay 設定を調整するには、次に示すように、レジストリ設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f04bc-128">To adjust the TcpTimedWaitDelay settings, you have to modify the registry settings as listed below:</span></span>  
  
###  
  
|||  
|-|-|  
|<span data-ttu-id="f04bc-129">キー:</span><span class="sxs-lookup"><span data-stu-id="f04bc-129">Key:</span></span>|<span data-ttu-id="f04bc-130">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters</span><span class="sxs-lookup"><span data-stu-id="f04bc-130">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters</span></span>|  
|<span data-ttu-id="f04bc-131">値: </span><span class="sxs-lookup"><span data-stu-id="f04bc-131">Value:</span></span>|<span data-ttu-id="f04bc-132">TcpTimedWaitDelay</span><span class="sxs-lookup"><span data-stu-id="f04bc-132">TcpTimedWaitDelay</span></span>|  
|<span data-ttu-id="f04bc-133">データの種類:</span><span class="sxs-lookup"><span data-stu-id="f04bc-133">Data Type:</span></span>|<span data-ttu-id="f04bc-134">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="f04bc-134">REG_DWORD</span></span>|  
|<span data-ttu-id="f04bc-135">範囲:</span><span class="sxs-lookup"><span data-stu-id="f04bc-135">Range:</span></span>|<span data-ttu-id="f04bc-136">30 ~ 300 (10 進数)</span><span class="sxs-lookup"><span data-stu-id="f04bc-136">30-300 (decimal)</span></span>|  
|<span data-ttu-id="f04bc-137">既定値:</span><span class="sxs-lookup"><span data-stu-id="f04bc-137">Default value:</span></span>|<span data-ttu-id="f04bc-138">0x78 (120 10 進数)</span><span class="sxs-lookup"><span data-stu-id="f04bc-138">0x78 (120 decimal)</span></span>|  
|<span data-ttu-id="f04bc-139">推奨値:</span><span class="sxs-lookup"><span data-stu-id="f04bc-139">Recommended value:</span></span>|<span data-ttu-id="f04bc-140">30</span><span class="sxs-lookup"><span data-stu-id="f04bc-140">30</span></span>|  
|<span data-ttu-id="f04bc-141">既定では、値が存在するでしょうか。</span><span class="sxs-lookup"><span data-stu-id="f04bc-141">Value exists by default?</span></span>|<span data-ttu-id="f04bc-142">**いいえ**、追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f04bc-142">**No**, needs to be added.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f04bc-143">参照</span><span class="sxs-lookup"><span data-stu-id="f04bc-143">See Also</span></span>  
 [<span data-ttu-id="f04bc-144">ネットワークのパフォーマンスを向上するための一般的なガイドライン</span><span class="sxs-lookup"><span data-stu-id="f04bc-144">General Guidelines for Improving Network Performance</span></span>](../technical-guides/general-guidelines-for-improving-network-performance.md)