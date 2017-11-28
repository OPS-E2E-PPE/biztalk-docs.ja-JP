---
title: "SAP アダプターのパフォーマンス カウンターを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance counters, using
- troubleshooting, using performance counters
ms.assetid: 2749add3-31f1-47ff-b3b4-ef46c76fa533
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5da387377f6201b518d3c5fdf37dabb872bcf600
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="use-performance-counters-with-the-sap-adapter"></a><span data-ttu-id="ec3f9-102">SAP アダプターのパフォーマンス カウンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-102">Use Performance Counters with the SAP adapter</span></span>
<span data-ttu-id="ec3f9-103">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]クライアントは、アダプターのパフォーマンスを測定するパフォーマンス カウンターを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-103">Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] clients can use performance counters to gauge the performance of the adapters.</span></span> <span data-ttu-id="ec3f9-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムは、パフォーマンス カウンターのカテゴリを作成します。"[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]"をインストールするに沿って、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program creates the performance counter category "[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]" along installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
  
## <a name="lob-time-cumulative-performance-counter"></a><span data-ttu-id="ec3f9-105">LOB (累積) 時間のパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="ec3f9-105">LOB Time (Cumulative) Performance Counter</span></span>  
 <span data-ttu-id="ec3f9-106">**SAP 向け BizTalk .NET Adapter**カテゴリには 1 つのパフォーマンス カウンター"LOB Time (累積)"と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-106">The **BizTalk .NET Adapter for SAP** category has one performance counter called the "LOB Time (Cumulative)".</span></span> <span data-ttu-id="ec3f9-107">このパフォーマンス カウンターは、LOB クライアント ライブラリは、アダプターを開始する操作が完了する時間をミリ秒単位で、時間を表します。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-107">This performance counter denotes the time, in milliseconds, that the LOB client library takes to complete an action that the adapter initiates.</span></span> <span data-ttu-id="ec3f9-108">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次のパターンでは、パフォーマンス カウンターのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-108">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] creates an instance of the performance counter in the following pattern:</span></span>  
  
```  
<process id>:<app domain id>:<endpoint id>:<action id>  
```  
  
 <span data-ttu-id="ec3f9-109">エンドポイント ID が考えられます。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-109">The endpoint ID could be:</span></span>  
  
-   <span data-ttu-id="ec3f9-110">アダプターから (送信)、SAP システムへの呼び出しの</span><span class="sxs-lookup"><span data-stu-id="ec3f9-110">For calls from the adapter to the SAP system (outbound)</span></span>  
  
    -   <span data-ttu-id="ec3f9-111">A、\<アプリケーション サーバーのホスト >、\<システム番号 ></span><span class="sxs-lookup"><span data-stu-id="ec3f9-111">A,\<application server host>,\<system number></span></span>  
  
    -   <span data-ttu-id="ec3f9-112">B、\<メッセージ サーバー ホスト >、\<R3NAME ></span><span class="sxs-lookup"><span data-stu-id="ec3f9-112">B,\<message server host>,\<R3NAME></span></span>  
  
    -   <span data-ttu-id="ec3f9-113">D、\<先 ></span><span class="sxs-lookup"><span data-stu-id="ec3f9-113">D,\<destination></span></span>  
  
-   <span data-ttu-id="ec3f9-114">SAP システムからアダプターへの呼び出しの (受信)</span><span class="sxs-lookup"><span data-stu-id="ec3f9-114">For calls from the SAP system to the adapter (inbound)</span></span>  
  
    -   <span data-ttu-id="ec3f9-115">I,\<ゲートウェイ ホスト >、\<ゲートウェイ サーバー ></span><span class="sxs-lookup"><span data-stu-id="ec3f9-115">I,\<gateway host>,\<gateway server></span></span>  
  
    -   <span data-ttu-id="ec3f9-116">ID、\<先 ></span><span class="sxs-lookup"><span data-stu-id="ec3f9-116">ID,\<destination></span></span>  
  
 <span data-ttu-id="ec3f9-117">アクション ID が考えられます。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-117">The action ID could be:</span></span>  
  
-   <span data-ttu-id="ec3f9-118">\<RFC 名 > の RFC 呼び出し)</span><span class="sxs-lookup"><span data-stu-id="ec3f9-118">\<RFC name> (for an RFC call)</span></span>  
  
-   <span data-ttu-id="ec3f9-119">T、\<RFC 名 > (用 tRFC の呼び出し)</span><span class="sxs-lookup"><span data-stu-id="ec3f9-119">T,\<RFC name> (for a tRFC call)</span></span>  
  
 <span data-ttu-id="ec3f9-120">パフォーマンス カウンターは、アダプターが SAP システムへの最初の呼び出し後にのみ初期化されます。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-120">The performance counter is initialized only after the adapter makes the first call to the SAP system.</span></span> <span data-ttu-id="ec3f9-121">また、 [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx)パフォーマンス カウンターのプロパティが 'Process' は、パフォーマンス カウンターは、カウンターを作成するプログラムが終了するとすぐに存在しなくなることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-121">Also, the [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx) property of the performance counter is set to 'Process', which means that the performance counter ceases to exist as soon as the program that creates the counter terminates.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="ec3f9-122">LOB Time (累積) パフォーマンス カウンターの有効桁数は、16 ミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-122">The precision of the LOB Time (Cumulative) performance counter is 16 milliseconds.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="ec3f9-123">パフォーマンス カウンターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-123">Enabling Performance Counters</span></span>  
 <span data-ttu-id="ec3f9-124">パフォーマンス カウンターを有効になっているやバインド プロパティを設定して無効になっている*EnablePerformanceCounters*です。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-124">The performance counters can be enabled or disabled by setting the binding property *EnablePerformanceCounters*.</span></span> <span data-ttu-id="ec3f9-125">パフォーマンス カウンターを有効にするには設定、 *EnablePerformanceCounters*にプロパティのバインド**True**です。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-125">To enable performance counters, set the *EnablePerformanceCounters* binding property to **True**.</span></span> <span data-ttu-id="ec3f9-126">パフォーマンス カウンターを無効にする設定*EnablePerformanceCounters*に**False**です。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-126">To disable performance counters, set *EnablePerformanceCounters* to **False**.</span></span> <span data-ttu-id="ec3f9-127">既定では、 *EnablePerformanceCounters*に設定されている**False**です。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-127">By default, *EnablePerformanceCounters* is set to **False**.</span></span>  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="ec3f9-128">パフォーマンス カウンターと WCF LOB Adapter SDK</span><span class="sxs-lookup"><span data-stu-id="ec3f9-128">Performance Counters and the WCF LOB Adapter SDK</span></span>  
 <span data-ttu-id="ec3f9-129">値を変更する、 *EnablePerformanceCounters*に対応するパフォーマンス カウンターの値が変更もプロパティのバインド、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-129">Changing the value of the *EnablePerformanceCounters* binding property also changes the value of the corresponding performance counter for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="ec3f9-130">バインディング プロパティも、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]静的では、一方の[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]は動的です。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-130">Also, the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, whereas that for the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is dynamic.</span></span> <span data-ttu-id="ec3f9-131">そのため、2 つのインスタンスがある場合、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 、AppDomain にバインドされ、 *EnablePerformanceCounters*に設定されているプロパティのバインド**True**いずれかでと**False**アダプター固有のパフォーマンス カウンターのいずれかで有効にし、他の無効になっているは、それ以外のです。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-131">Hence, if there are two instances of the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding in the AppDomain, and the *EnablePerformanceCounters* binding property is set to **True** in one and **False** in the other, the adapter-specific performance counter will be enabled in one and disabled in the other.</span></span> <span data-ttu-id="ec3f9-132">ただし、ためのバインディング プロパティ[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で、いずれかに設定されます**True**または**False**によってどのような値を最後に指定されました。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-132">However, because the binding property for [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, it will either be set to **True** or **False** depending on what value was specified last.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec3f9-133">参照</span><span class="sxs-lookup"><span data-stu-id="ec3f9-133">See Also</span></span>  

[<span data-ttu-id="ec3f9-134">SAP アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="ec3f9-134">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)