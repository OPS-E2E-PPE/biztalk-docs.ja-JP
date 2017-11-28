---
title: "Siebel アダプターのパフォーマンス カウンターを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance counters, troubleshooting
- troubleshooting, performance counters
- performance counters, using
ms.assetid: 7930e8f6-5099-4a9c-b38a-13c9902635a6
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2540801af6c30632250602b45c21e7b57cd2bc22
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="use-performance-counters-with-the-siebel-adapter"></a><span data-ttu-id="01e25-102">Siebel アダプターのパフォーマンス カウンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="01e25-102">Use Performance Counters with the Siebel adapter</span></span>
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]<span data-ttu-id="01e25-103">クライアントは、アダプターのパフォーマンスを測定するのにパフォーマンス カウンターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="01e25-103"> clients can use the performance counters to gauge the performance of the adapters.</span></span> <span data-ttu-id="01e25-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムによって作成のパフォーマンス カウンター カテゴリ"[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]"アダプター パックのインストールと共にします。</span><span class="sxs-lookup"><span data-stu-id="01e25-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program creates the performance counter category "[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]" along with the Adapter Pack installation.</span></span>  
  
## <a name="the-lob-time-cumulative-performance-counter"></a><span data-ttu-id="01e25-105">LOB (累積) 時間のパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="01e25-105">The LOB Time (Cumulative) Performance Counter</span></span>  
 <span data-ttu-id="01e25-106">**BizTalk .NET Adapter for Siebel**カテゴリには 1 つのパフォーマンス カウンター「LOB 時間 (累積)」と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="01e25-106">The **BizTalk .NET Adapter for Siebel** category has one performance counter called "LOB Time (Cumulative)".</span></span> <span data-ttu-id="01e25-107">このパフォーマンス カウンターは、LOB クライアント ライブラリは、アダプターを開始する操作が完了する時間をミリ秒単位で、時間を表します。</span><span class="sxs-lookup"><span data-stu-id="01e25-107">This performance counter denotes the time, in milliseconds, that the LOB client library takes to complete an action that the adapter initiates.</span></span> <span data-ttu-id="01e25-108">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]特定 Siebel サーバー名については、各操作のパフォーマンス カウンターのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="01e25-108">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] creates an instance of the performance counter for each action, for a specific Siebel server name.</span></span> <span data-ttu-id="01e25-109">次のパターンでは、インスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="01e25-109">The instances are created in the following pattern:</span></span>  
  
```  
<process id>:<app domain id>:<endpoint id>:<action id>  
```  
  
 <span data-ttu-id="01e25-110">場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]、エンドポイント id は、接続 URI で指定されている、Siebel サーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="01e25-110">In case of the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], the endpoint id is the name of the Siebel server, as specified in the connection URI.</span></span> <span data-ttu-id="01e25-111">操作 id は、によって実行されたアクション、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]など、ログイン、ログオフ、メタデータ、\<ビジネス コンポーネント名 >.\<操作 >、\<ビジネス サービス名 >.\<ビジネス サービス メソッド > です。</span><span class="sxs-lookup"><span data-stu-id="01e25-111">The action id could be any action performed by the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] such as Login, Logoff, Metadata, \<business component name>.\<operation>, \<business service name>.\<business service method>.</span></span> <span data-ttu-id="01e25-112">上記の名前付け規則の結果を 127 文字を超える名に次の形式でアクション ID のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="01e25-112">If the preceding naming convention results in a name that exceeds 127 characters only the action ID is displayed in the following format:</span></span>  
  
```  
:::<action id>  
```  
  
 <span data-ttu-id="01e25-113">場合`:::<action id>`も 127 文字を超える場合、これは 127 文字まで切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="01e25-113">If `:::<action id>` also exceeds 127 characters, it is trimmed down to 127 characters.</span></span>  
  
 <span data-ttu-id="01e25-114">パフォーマンス カウンターは、アダプターは、Siebel システムへの最初の呼び出し後にのみ初期化されます。</span><span class="sxs-lookup"><span data-stu-id="01e25-114">The performance counter is initialized only after the adapter makes the first call to the Siebel system.</span></span> <span data-ttu-id="01e25-115">また、 **InstanceLifetime**パフォーマンス カウンターのプロパティが 'Process' は、パフォーマンス カウンターは、カウンターを作成するプログラムが終了するとすぐに存在しなくなることを意味します。</span><span class="sxs-lookup"><span data-stu-id="01e25-115">Also, the **InstanceLifetime** property of the performance counter is set to 'Process', which means that the performance counter ceases to exist as soon as the program that creates the counter terminates.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="01e25-116">LOB Time (累積) パフォーマンス カウンターの有効桁数は、16 ミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="01e25-116">The precision of the LOB Time (Cumulative) performance counter is 16 milliseconds.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="01e25-117">パフォーマンス カウンターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="01e25-117">Enabling Performance Counters</span></span>  
 <span data-ttu-id="01e25-118">パフォーマンス カウンターを有効になっているやバインド プロパティを設定して無効になっている**EnablePerformanceCounters**です。</span><span class="sxs-lookup"><span data-stu-id="01e25-118">The performance counters can be enabled or disabled by setting the binding property **EnablePerformanceCounters**.</span></span> <span data-ttu-id="01e25-119">設定**EnablePerformanceCounters**にプロパティのバインド**True**パフォーマンス カウンターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="01e25-119">Set **EnablePerformanceCounters** binding property to **True** to enable performance counters.</span></span> <span data-ttu-id="01e25-120">パフォーマンス カウンターを無効にする設定**EnablePerformanceCounters**に**False**です。</span><span class="sxs-lookup"><span data-stu-id="01e25-120">To disable performance counters, set **EnablePerformanceCounters** to **False**.</span></span> <span data-ttu-id="01e25-121">既定では、 **EnablePerformanceCounters**に設定されている**False**です。</span><span class="sxs-lookup"><span data-stu-id="01e25-121">By default, **EnablePerformanceCounters** is set to **False**.</span></span>  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="01e25-122">パフォーマンス カウンターと WCF LOB Adapter SDK</span><span class="sxs-lookup"><span data-stu-id="01e25-122">Performance Counters and the WCF LOB Adapter SDK</span></span>  
 <span data-ttu-id="01e25-123">値を変更する、 **EnablePerformanceCounters**バインディング プロパティの対応するパフォーマンス カウンターの値が変更[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="01e25-123">Changing the value of the **EnablePerformanceCounters** binding property changes the value of the corresponding performance counter for [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="01e25-124">バインディング プロパティも、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]静的では、一方の[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]は動的です。</span><span class="sxs-lookup"><span data-stu-id="01e25-124">Also, the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, whereas that for the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is dynamic.</span></span> <span data-ttu-id="01e25-125">そのため、2 つのインスタンスがある場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] 、AppDomain にバインドされ、 **EnablePerformanceCounters**に設定されているプロパティのバインド**True**いずれかでと**False**アダプター固有のパフォーマンス カウンターのいずれかで有効にし、他の無効になっているは、それ以外のです。</span><span class="sxs-lookup"><span data-stu-id="01e25-125">Hence, if there are two instances of the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding in the AppDomain, and the **EnablePerformanceCounters** binding property is set to **True** in one and **False** in the other, the adapter-specific performance counter will be enabled in one and disabled in the other.</span></span> <span data-ttu-id="01e25-126">ただし、ためのバインディング プロパティ、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で、いずれかに設定されます**True**または**False**にどのような値を最後に指定された依存します。</span><span class="sxs-lookup"><span data-stu-id="01e25-126">However, because the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, it will either be set to **True** or **False**, depending on what value was specified last.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01e25-127">参照</span><span class="sxs-lookup"><span data-stu-id="01e25-127">See Also</span></span>  
[<span data-ttu-id="01e25-128">Siebel アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="01e25-128">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)