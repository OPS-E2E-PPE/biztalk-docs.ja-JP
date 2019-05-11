---
title: Siebel アダプターを使用したパフォーマンス カウンターの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance counters, troubleshooting
- troubleshooting, performance counters
- performance counters, using
ms.assetid: 7930e8f6-5099-4a9c-b38a-13c9902635a6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79bb582ca3f79dc20f537551d9aeb98db5cd6cc0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370349"
---
# <a name="use-performance-counters-with-the-siebel-adapter"></a><span data-ttu-id="89f96-102">Siebel アダプターを使用したパフォーマンス カウンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="89f96-102">Use Performance Counters with the Siebel adapter</span></span>
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] <span data-ttu-id="89f96-103">クライアントは、アダプターのパフォーマンスを測定するのにパフォーマンス カウンターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89f96-103">clients can use the performance counters to gauge the performance of the adapters.</span></span> <span data-ttu-id="89f96-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムは、パフォーマンス カウンター カテゴリを作成します。"[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]"アダプター パックのインストールと共にします。</span><span class="sxs-lookup"><span data-stu-id="89f96-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program creates the performance counter category "[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]" along with the Adapter Pack installation.</span></span>  
  
## <a name="the-lob-time-cumulative-performance-counter"></a><span data-ttu-id="89f96-105">LOB の時間 (累積) パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="89f96-105">The LOB Time (Cumulative) Performance Counter</span></span>  
 <span data-ttu-id="89f96-106">**BizTalk .NET Adapter for Siebel**カテゴリには 1 つのパフォーマンス カウンター"LOB Time (累積)"と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="89f96-106">The **BizTalk .NET Adapter for Siebel** category has one performance counter called "LOB Time (Cumulative)".</span></span> <span data-ttu-id="89f96-107">このパフォーマンス カウンターは、LOB クライアント ライブラリは、アダプターを起動する操作を完了するまでをミリ秒単位の時間を示します。</span><span class="sxs-lookup"><span data-stu-id="89f96-107">This performance counter denotes the time, in milliseconds, that the LOB client library takes to complete an action that the adapter initiates.</span></span> <span data-ttu-id="89f96-108">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]特定 Siebel サーバー名の各操作のパフォーマンス カウンターのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="89f96-108">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] creates an instance of the performance counter for each action, for a specific Siebel server name.</span></span> <span data-ttu-id="89f96-109">次のパターンでは、インスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="89f96-109">The instances are created in the following pattern:</span></span>  
  
```  
<process id>:<app domain id>:<endpoint id>:<action id>  
```  
  
 <span data-ttu-id="89f96-110">場合、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]エンドポイントの id は、接続 URI で指定されている、Siebel サーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="89f96-110">In case of the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], the endpoint id is the name of the Siebel server, as specified in the connection URI.</span></span> <span data-ttu-id="89f96-111">アクション id の操作によって実行される可能性があります、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]など、ログイン、ログオフ、メタデータ、\<ビジネス コンポーネント名\>.\<操作\>、\<ビジネス サービス名\>.\<ビジネス サービス メソッド\>します。</span><span class="sxs-lookup"><span data-stu-id="89f96-111">The action id could be any action performed by the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] such as Login, Logoff, Metadata, \<business component name\>.\<operation\>, \<business service name\>.\<business service method\>.</span></span> <span data-ttu-id="89f96-112">前の名前付け規則の結果を 127 文字を超える名前の場合は、次の形式でアクション ID のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="89f96-112">If the preceding naming convention results in a name that exceeds 127 characters only the action ID is displayed in the following format:</span></span>  
  
```  
:::<action id>  
```  
  
 <span data-ttu-id="89f96-113">場合`:::<action id>`もが 127 文字を超える、127 文字までには切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="89f96-113">If `:::<action id>` also exceeds 127 characters, it is trimmed down to 127 characters.</span></span>  
  
 <span data-ttu-id="89f96-114">パフォーマンス カウンターは、アダプターは、Siebel システムへの最初の呼び出しを後でのみ初期化されます。</span><span class="sxs-lookup"><span data-stu-id="89f96-114">The performance counter is initialized only after the adapter makes the first call to the Siebel system.</span></span> <span data-ttu-id="89f96-115">また、 **InstanceLifetime** 'Process' は、パフォーマンス カウンターは、カウンターを作成するプログラムが終了すると、すぐに存在しなくなることを意味するパフォーマンス カウンターのプロパティが設定されています。</span><span class="sxs-lookup"><span data-stu-id="89f96-115">Also, the **InstanceLifetime** property of the performance counter is set to 'Process', which means that the performance counter ceases to exist as soon as the program that creates the counter terminates.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="89f96-116">LOB の時間 (累積) パフォーマンス カウンターの有効桁数は、16 ミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="89f96-116">The precision of the LOB Time (Cumulative) performance counter is 16 milliseconds.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="89f96-117">パフォーマンス カウンターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="89f96-117">Enabling Performance Counters</span></span>  
 <span data-ttu-id="89f96-118">パフォーマンス カウンターを有効またはバインドのプロパティを設定して無効にできる**EnablePerformanceCounters**します。</span><span class="sxs-lookup"><span data-stu-id="89f96-118">The performance counters can be enabled or disabled by setting the binding property **EnablePerformanceCounters**.</span></span> <span data-ttu-id="89f96-119">設定**EnablePerformanceCounters**プロパティをバインド**True**パフォーマンス カウンターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="89f96-119">Set **EnablePerformanceCounters** binding property to **True** to enable performance counters.</span></span> <span data-ttu-id="89f96-120">パフォーマンス カウンターを無効にするには設定**EnablePerformanceCounters**に**False**します。</span><span class="sxs-lookup"><span data-stu-id="89f96-120">To disable performance counters, set **EnablePerformanceCounters** to **False**.</span></span> <span data-ttu-id="89f96-121">既定では、 **EnablePerformanceCounters**に設定されている**False**します。</span><span class="sxs-lookup"><span data-stu-id="89f96-121">By default, **EnablePerformanceCounters** is set to **False**.</span></span>  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="89f96-122">パフォーマンス カウンターと WCF LOB Adapter SDK</span><span class="sxs-lookup"><span data-stu-id="89f96-122">Performance Counters and the WCF LOB Adapter SDK</span></span>  
 <span data-ttu-id="89f96-123">値を変更する、 **EnablePerformanceCounters**バインディング プロパティの対応するパフォーマンス カウンターの値を変更する[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="89f96-123">Changing the value of the **EnablePerformanceCounters** binding property changes the value of the corresponding performance counter for [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="89f96-124">バインド プロパティも、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で一方の場合、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]は動的です。</span><span class="sxs-lookup"><span data-stu-id="89f96-124">Also, the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, whereas that for the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is dynamic.</span></span> <span data-ttu-id="89f96-125">そのため、2 つのインスタンスがある場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] 、appdomain のバインドと**EnablePerformanceCounters**に設定されているプロパティのバインド**True**で 1 つと**False**アダプター固有のパフォーマンス カウンターのいずれかで有効にし、他の無効になっているで、他のです。</span><span class="sxs-lookup"><span data-stu-id="89f96-125">Hence, if there are two instances of the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding in the AppDomain, and the **EnablePerformanceCounters** binding property is set to **True** in one and **False** in the other, the adapter-specific performance counter will be enabled in one and disabled in the other.</span></span> <span data-ttu-id="89f96-126">ただし、ためのバインディング プロパティ、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で、いずれかに設定されます**True**または**False**にどのような値を最後に指定された依存します。</span><span class="sxs-lookup"><span data-stu-id="89f96-126">However, because the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, it will either be set to **True** or **False**, depending on what value was specified last.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89f96-127">参照</span><span class="sxs-lookup"><span data-stu-id="89f96-127">See Also</span></span>  
[<span data-ttu-id="89f96-128">Siebel アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="89f96-128">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)