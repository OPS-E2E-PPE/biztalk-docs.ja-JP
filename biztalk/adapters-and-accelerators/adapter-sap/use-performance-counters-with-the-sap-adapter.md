---
title: SAP アダプターを使用したパフォーマンス カウンターの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance counters, using
- troubleshooting, using performance counters
ms.assetid: 2749add3-31f1-47ff-b3b4-ef46c76fa533
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16f83041339275b1b372f57a86754e8df28a24a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372210"
---
# <a name="use-performance-counters-with-the-sap-adapter"></a><span data-ttu-id="e977d-102">SAP アダプターを使用したパフォーマンス カウンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e977d-102">Use Performance Counters with the SAP adapter</span></span>
<span data-ttu-id="e977d-103">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]クライアントは、パフォーマンス カウンターを使用して、アダプターのパフォーマンスを測定します。</span><span class="sxs-lookup"><span data-stu-id="e977d-103">Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] clients can use performance counters to gauge the performance of the adapters.</span></span> <span data-ttu-id="e977d-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムは、パフォーマンス カウンター カテゴリを作成します。"[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]"インストールに沿って、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e977d-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program creates the performance counter category "[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]" along installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
  
## <a name="lob-time-cumulative-performance-counter"></a><span data-ttu-id="e977d-105">LOB の時間 (累積) パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="e977d-105">LOB Time (Cumulative) Performance Counter</span></span>  
 <span data-ttu-id="e977d-106">**SAP 向け BizTalk .NET アダプター**カテゴリには 1 つのパフォーマンス カウンター"LOB Time (累積)"と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="e977d-106">The **BizTalk .NET Adapter for SAP** category has one performance counter called the "LOB Time (Cumulative)".</span></span> <span data-ttu-id="e977d-107">このパフォーマンス カウンターは、LOB クライアント ライブラリは、アダプターを起動する操作を完了するまでをミリ秒単位の時間を示します。</span><span class="sxs-lookup"><span data-stu-id="e977d-107">This performance counter denotes the time, in milliseconds, that the LOB client library takes to complete an action that the adapter initiates.</span></span> <span data-ttu-id="e977d-108">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次のパターンでは、パフォーマンス カウンターのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e977d-108">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] creates an instance of the performance counter in the following pattern:</span></span>  
  
```  
<process id>:<app domain id>:<endpoint id>:<action id>  
```  
  
 <span data-ttu-id="e977d-109">エンドポイントの ID になります。</span><span class="sxs-lookup"><span data-stu-id="e977d-109">The endpoint ID could be:</span></span>  
  
- <span data-ttu-id="e977d-110">(送信) の SAP システムにアダプターからの呼び出し</span><span class="sxs-lookup"><span data-stu-id="e977d-110">For calls from the adapter to the SAP system (outbound)</span></span>  
  
  -   <span data-ttu-id="e977d-111">A、\<アプリケーション サーバーのホスト\>、\<システム番号\></span><span class="sxs-lookup"><span data-stu-id="e977d-111">A,\<application server host\>,\<system number\></span></span>  
  
  -   <span data-ttu-id="e977d-112">B、\<メッセージ サーバー ホスト\>、\<R3NAME\></span><span class="sxs-lookup"><span data-stu-id="e977d-112">B,\<message server host\>,\<R3NAME\></span></span>  
  
  -   <span data-ttu-id="e977d-113">D、\<変換先\></span><span class="sxs-lookup"><span data-stu-id="e977d-113">D,\<destination\></span></span>  
  
- <span data-ttu-id="e977d-114">SAP システムからアダプターへの呼び出しの (受信)</span><span class="sxs-lookup"><span data-stu-id="e977d-114">For calls from the SAP system to the adapter (inbound)</span></span>  
  
  -   <span data-ttu-id="e977d-115">I,\<ゲートウェイ ホスト\>、\<ゲートウェイ サーバー\></span><span class="sxs-lookup"><span data-stu-id="e977d-115">I,\<gateway host\>,\<gateway server\></span></span>  
  
  -   <span data-ttu-id="e977d-116">ID、\<変換先\></span><span class="sxs-lookup"><span data-stu-id="e977d-116">ID,\<destination\></span></span>  
  
  <span data-ttu-id="e977d-117">操作 ID になります。</span><span class="sxs-lookup"><span data-stu-id="e977d-117">The action ID could be:</span></span>  
  
- <span data-ttu-id="e977d-118">\<RFC 名前\>(の RFC 呼び出しを)</span><span class="sxs-lookup"><span data-stu-id="e977d-118">\<RFC name\> (for an RFC call)</span></span>  
  
- <span data-ttu-id="e977d-119">T、\<RFC 名前\>(の tRFC の呼び出し)</span><span class="sxs-lookup"><span data-stu-id="e977d-119">T,\<RFC name\> (for a tRFC call)</span></span>  
  
  <span data-ttu-id="e977d-120">パフォーマンス カウンターは、アダプターが SAP システムへの最初の呼び出し後にのみ初期化されます。</span><span class="sxs-lookup"><span data-stu-id="e977d-120">The performance counter is initialized only after the adapter makes the first call to the SAP system.</span></span> <span data-ttu-id="e977d-121">また、 [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx) 'Process' は、パフォーマンス カウンターは、カウンターを作成するプログラムが終了すると、すぐに存在しなくなることを意味するパフォーマンス カウンターのプロパティが設定されています。</span><span class="sxs-lookup"><span data-stu-id="e977d-121">Also, the [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx) property of the performance counter is set to 'Process', which means that the performance counter ceases to exist as soon as the program that creates the counter terminates.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="e977d-122">LOB の時間 (累積) パフォーマンス カウンターの有効桁数は、16 ミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="e977d-122">The precision of the LOB Time (Cumulative) performance counter is 16 milliseconds.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="e977d-123">パフォーマンス カウンターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e977d-123">Enabling Performance Counters</span></span>  
 <span data-ttu-id="e977d-124">パフォーマンス カウンターを有効またはバインドのプロパティを設定して無効にできる*EnablePerformanceCounters*します。</span><span class="sxs-lookup"><span data-stu-id="e977d-124">The performance counters can be enabled or disabled by setting the binding property *EnablePerformanceCounters*.</span></span> <span data-ttu-id="e977d-125">パフォーマンス カウンターを有効にするには設定、 *EnablePerformanceCounters*プロパティをバインド**True**します。</span><span class="sxs-lookup"><span data-stu-id="e977d-125">To enable performance counters, set the *EnablePerformanceCounters* binding property to **True**.</span></span> <span data-ttu-id="e977d-126">パフォーマンス カウンターを無効にするには設定*EnablePerformanceCounters*に**False**します。</span><span class="sxs-lookup"><span data-stu-id="e977d-126">To disable performance counters, set *EnablePerformanceCounters* to **False**.</span></span> <span data-ttu-id="e977d-127">既定では、 *EnablePerformanceCounters*に設定されている**False**します。</span><span class="sxs-lookup"><span data-stu-id="e977d-127">By default, *EnablePerformanceCounters* is set to **False**.</span></span>  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="e977d-128">パフォーマンス カウンターと WCF LOB Adapter SDK</span><span class="sxs-lookup"><span data-stu-id="e977d-128">Performance Counters and the WCF LOB Adapter SDK</span></span>  
 <span data-ttu-id="e977d-129">値を変更する、 *EnablePerformanceCounters*に対応するパフォーマンス カウンターの値を変更してもプロパティをバインド、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e977d-129">Changing the value of the *EnablePerformanceCounters* binding property also changes the value of the corresponding performance counter for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="e977d-130">バインド プロパティも、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で一方の場合、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]は動的です。</span><span class="sxs-lookup"><span data-stu-id="e977d-130">Also, the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, whereas that for the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is dynamic.</span></span> <span data-ttu-id="e977d-131">そのため、2 つのインスタンスがある場合、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 、appdomain のバインドと*EnablePerformanceCounters*に設定されているプロパティのバインド**True**で 1 つと**False**アダプター固有のパフォーマンス カウンターのいずれかで有効にし、他の無効になっているで、他のです。</span><span class="sxs-lookup"><span data-stu-id="e977d-131">Hence, if there are two instances of the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding in the AppDomain, and the *EnablePerformanceCounters* binding property is set to **True** in one and **False** in the other, the adapter-specific performance counter will be enabled in one and disabled in the other.</span></span> <span data-ttu-id="e977d-132">ただし、ためのバインディング プロパティ[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で、いずれかに設定されます**True**または**False**によってどのような値を最後に指定されました。</span><span class="sxs-lookup"><span data-stu-id="e977d-132">However, because the binding property for [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, it will either be set to **True** or **False** depending on what value was specified last.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e977d-133">参照</span><span class="sxs-lookup"><span data-stu-id="e977d-133">See Also</span></span>  

[<span data-ttu-id="e977d-134">SAP アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="e977d-134">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)