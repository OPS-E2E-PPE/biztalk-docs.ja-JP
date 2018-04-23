---
title: ネットワーク パフォーマンスを向上させる変更可能な設定 |Microsoft ドキュメント
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
ms.openlocfilehash: 8557c8bbe8c0b1c785d6da8d87e8950d3779b8d0
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="settings-that-can-be-modified-to-improve-network-performance"></a><span data-ttu-id="9ef8b-102">ネットワーク パフォーマンスを向上するように変更する設定</span><span class="sxs-lookup"><span data-stu-id="9ef8b-102">Settings that can be Modified to Improve Network Performance</span></span>
<span data-ttu-id="9ef8b-103">このトピックでは、ネットワーク パフォーマンスに影響する推奨値の説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-103">This topic provides a description of recommended values   that impact network performance.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9ef8b-104">このガイドを完了したパフォーマンスのテスト中に Windows Server 2008 が既定ではチューニングするが表示されることが確認されました。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-104">During performance testing completed for this guide it was observed that Windows Server 2008 appears to be tuned by default.</span></span> <span data-ttu-id="9ef8b-105">レジストリ設定の変更は、システムへの影響を慎重に分析した後にのみ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-105">Modification of  registry settings should only be done after a careful analysis of the effects on the system.</span></span>  
  
## <a name="adjust-the-maxuserport-and-tcptimedwaitdelay-settings"></a><span data-ttu-id="9ef8b-106">MaxUserPort と TcpTimedWaitDelay 設定を調整します。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-106">Adjust the MaxUserPort and TcpTimedWaitDelay settings</span></span>  
 <span data-ttu-id="9ef8b-107">**MaxUserPort**値アプリケーションは、システムから利用可能なユーザーの任意のポートを要求するときに使用される最大ポート数を制御します。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-107">The **MaxUserPort** value controls the maximum port number used when an application requests any available user port from the system.</span></span> <span data-ttu-id="9ef8b-108">通常、短時間のポートは、1025 65535 までからの範囲で割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-108">Normally, short-lived ports are allocated in the range from 1025 through 65535.</span></span> <span data-ttu-id="9ef8b-109">ポートの範囲は、実際に開始点とは、エンドポイントとの範囲ではようになりました。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-109">The port range is now truly a range with a starting point and with an endpoint.</span></span> <span data-ttu-id="9ef8b-110">新しい既定の開始ポートは 49152、および既定の終了ポートは 65535 です。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-110">The new default start port is 49152, and the default end port is 65535.</span></span> <span data-ttu-id="9ef8b-111">この範囲は、アプリケーションとサービスによって使用される既知のポートだけでなく、します。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-111">This range is in addition to well-known ports that are used by services and by applications.</span></span> <span data-ttu-id="9ef8b-112">各サーバーでは、サーバーで使用するポートの範囲を変更できます。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-112">The port range that is used by the servers can be modified on each server.</span></span> <span data-ttu-id="9ef8b-113">この範囲を調整するには、netsh コマンドを使用して次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-113">You adjust this range by using the netsh command, as follows:</span></span>  
  
 <span data-ttu-id="9ef8b-114">**netsh int \<ipv4&#124;ipv6\>動的設定\<tcp&#124;udp\>開始番号 num = 範囲を =**</span><span class="sxs-lookup"><span data-stu-id="9ef8b-114">**netsh int \<ipv4&#124;ipv6\> set dynamicport \<tcp&#124;udp\> start=number num=range**</span></span>  
  
 <span data-ttu-id="9ef8b-115">このコマンドは、tcp 動的ポートの範囲を設定します。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-115">This command sets the dynamic port range for TCP.</span></span> <span data-ttu-id="9ef8b-116">開始ポート アドレスが**数**、ポートの総数と**範囲**です。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-116">The start port is **number**, and the total number of ports is **range**.</span></span> <span data-ttu-id="9ef8b-117">サンプル コマンドは、次のとおり: 次の netsh コマンドを使用して動的ポートの範囲を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-117">The following are sample commands: You can view the dynamic port range by using the following netsh commands:</span></span>  
  
-   <span data-ttu-id="9ef8b-118">netsh int ipv4 では、動的 tcp を表示します。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-118">netsh int ipv4 show dynamicport tcp.</span></span> <span data-ttu-id="9ef8b-119">Tcp v4 の最大許容値の範囲を向上させるのには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-119">To increase the range to the maximum allowed value for tcp v4, use the following command:</span></span>  
  
     <span data-ttu-id="9ef8b-120">**netsh int ipv4 設定動的 tcp 開始 1025 num = 64511 を =**</span><span class="sxs-lookup"><span data-stu-id="9ef8b-120">**netsh int ipv4 set dynamicport tcp start=1025 num=64511**</span></span>  
  
-   <span data-ttu-id="9ef8b-121">netsh int ipv4 動的 udp を表示します。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-121">netsh int ipv4 show dynamicport udp</span></span>  
  
-   <span data-ttu-id="9ef8b-122">netsh int ipv6 動的 tcp を表示します。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-122">netsh int ipv6 show dynamicport tcp</span></span>  
  
-   <span data-ttu-id="9ef8b-123">netsh int ipv6 動的 udp を表示します。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-123">netsh int ipv6 show dynamicport udp</span></span>  
  
 <span data-ttu-id="9ef8b-124">**TcpTimedWaitDelay**値が閉じられるときに、接続が TIME_WAIT 状態で保持される時間の長さを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-124">The **TcpTimedWaitDelay** value determines the length of time that a connection stays in the TIME_WAIT state when being closed.</span></span> <span data-ttu-id="9ef8b-125">接続が TIME_WAIT 状態のときに、ソケット ペアを再利用できません。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-125">While a connection is in the TIME_WAIT state, the socket pair cannot be reused.</span></span> <span data-ttu-id="9ef8b-126">これは、値が 2 回セグメントの最大有効期間中、ネットワーク上にする必要があります 2 msl 状態とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-126">This is also known as the 2MSL state because the value should be twice the maximum segment lifetime on the network.</span></span> <span data-ttu-id="9ef8b-127">詳細については、次を参照してください。[インターネット RFC 793](http://go.microsoft.com/fwlink/?LinkId=113719) (ハイパーリンク"http://go.microsoft.com/fwlink/?LinkId=113719"http://go.microsoft.com/fwlink/?LinkId=113719)です。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-127">For more information, see [Internet RFC 793](http://go.microsoft.com/fwlink/?LinkId=113719) ( HYPERLINK "http://go.microsoft.com/fwlink/?LinkId=113719" http://go.microsoft.com/fwlink/?LinkId=113719).</span></span> <span data-ttu-id="9ef8b-128">TcpTimedWaitDelay 設定を調整するには、次に示すようにレジストリ設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-128">To adjust the TcpTimedWaitDelay settings, you have to modify the registry settings as listed below:</span></span>  
  
###  
  
|||  
|-|-|  
|<span data-ttu-id="9ef8b-129">キー:</span><span class="sxs-lookup"><span data-stu-id="9ef8b-129">Key:</span></span>|<span data-ttu-id="9ef8b-130">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters</span><span class="sxs-lookup"><span data-stu-id="9ef8b-130">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters</span></span>|  
|<span data-ttu-id="9ef8b-131">値: </span><span class="sxs-lookup"><span data-stu-id="9ef8b-131">Value:</span></span>|<span data-ttu-id="9ef8b-132">TcpTimedWaitDelay</span><span class="sxs-lookup"><span data-stu-id="9ef8b-132">TcpTimedWaitDelay</span></span>|  
|<span data-ttu-id="9ef8b-133">データ型:</span><span class="sxs-lookup"><span data-stu-id="9ef8b-133">Data Type:</span></span>|<span data-ttu-id="9ef8b-134">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="9ef8b-134">REG_DWORD</span></span>|  
|<span data-ttu-id="9ef8b-135">範囲:</span><span class="sxs-lookup"><span data-stu-id="9ef8b-135">Range:</span></span>|<span data-ttu-id="9ef8b-136">30 ~ 300 (10 進数)</span><span class="sxs-lookup"><span data-stu-id="9ef8b-136">30-300 (decimal)</span></span>|  
|<span data-ttu-id="9ef8b-137">既定値:</span><span class="sxs-lookup"><span data-stu-id="9ef8b-137">Default value:</span></span>|<span data-ttu-id="9ef8b-138">0x78 (120 10 進数)</span><span class="sxs-lookup"><span data-stu-id="9ef8b-138">0x78 (120 decimal)</span></span>|  
|<span data-ttu-id="9ef8b-139">推奨値:</span><span class="sxs-lookup"><span data-stu-id="9ef8b-139">Recommended value:</span></span>|<span data-ttu-id="9ef8b-140">30</span><span class="sxs-lookup"><span data-stu-id="9ef8b-140">30</span></span>|  
|<span data-ttu-id="9ef8b-141">既定値が存在するか。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-141">Value exists by default?</span></span>|<span data-ttu-id="9ef8b-142">**いいえ**、追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ef8b-142">**No**, needs to be added.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ef8b-143">参照</span><span class="sxs-lookup"><span data-stu-id="9ef8b-143">See Also</span></span>  
 [<span data-ttu-id="9ef8b-144">ネットワークのパフォーマンスを向上するための一般的なガイドライン</span><span class="sxs-lookup"><span data-stu-id="9ef8b-144">General Guidelines for Improving Network Performance</span></span>](../technical-guides/general-guidelines-for-improving-network-performance.md)