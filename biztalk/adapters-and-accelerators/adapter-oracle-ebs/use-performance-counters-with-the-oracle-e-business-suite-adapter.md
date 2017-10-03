---
title: "Oracle E-business Suite アダプターのパフォーマンス カウンターを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7d722b7-8343-4956-81ed-acd5a463a9b1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf2a9f345745c18ca03086833fffe3553e96cece
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="use-performance-counters-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="4adaa-102">Oracle E-business Suite アダプターのパフォーマンス カウンターの使用します。</span><span class="sxs-lookup"><span data-stu-id="4adaa-102">Use Performance Counters with the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="4adaa-103">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]クライアントは、アダプターのパフォーマンスを測定するパフォーマンス カウンターを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="4adaa-103">Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] clients can use performance counters to gauge the performance of the adapters.</span></span> <span data-ttu-id="4adaa-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムは、パフォーマンス カウンターのカテゴリを作成**BizTalk .NET Adapter for Oracle E-business Suite**をインストールすると共に、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="4adaa-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program creates the performance counter category **BizTalk .NET Adapter for Oracle E-Business Suite** along with installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
  
## <a name="lob-time-cumulative-performance-counter"></a><span data-ttu-id="4adaa-105">LOB Time (累積) パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="4adaa-105">LOB Time (Cumulative) performance counter</span></span>  
 <span data-ttu-id="4adaa-106">**BizTalk .NET Adapter for Oracle E-business Suite**カテゴリには 1 つというパフォーマンス カウンター"LOB Time (累積)."</span><span class="sxs-lookup"><span data-stu-id="4adaa-106">The **BizTalk .NET Adapter for Oracle E-Business Suite** category has one performance counter called the “LOB Time (Cumulative).”</span></span> <span data-ttu-id="4adaa-107">このパフォーマンス カウンターは、LOB クライアント ライブラリは、アダプターを開始する操作が完了する時間をミリ秒単位で、時間を表します。</span><span class="sxs-lookup"><span data-stu-id="4adaa-107">This performance counter denotes the time, in milliseconds, that the LOB client library takes to complete an action that the adapter initiates.</span></span> <span data-ttu-id="4adaa-108">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]パターンを次のいずれかで、パフォーマンス カウンターのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="4adaa-108">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] creates an instance of the performance counter in any of the following patterns:</span></span>  
  
```  
<process id>:<app domain id>:<oracle data source>:<string>  
```  
  
 <span data-ttu-id="4adaa-109">ここで"string"可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4adaa-109">Where "string" could be:</span></span>  
  
-   <span data-ttu-id="4adaa-110">Connection.Open</span><span class="sxs-lookup"><span data-stu-id="4adaa-110">Connection.Open</span></span>  
  
-   <span data-ttu-id="4adaa-111">Connection.Close</span><span class="sxs-lookup"><span data-stu-id="4adaa-111">Connection.Close</span></span>  
  
-   <span data-ttu-id="4adaa-112">メタデータ</span><span class="sxs-lookup"><span data-stu-id="4adaa-112">Metadata</span></span>  
  
-   <span data-ttu-id="4adaa-113">メッセージ アクション。</span><span class="sxs-lookup"><span data-stu-id="4adaa-113">Message action.</span></span> <span data-ttu-id="4adaa-114">たとえば、次のアクションは`InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`InterfaceTables.Insert.FND.APPS.MS_SAMPLE_EMPLOYEE は文字列になります。</span><span class="sxs-lookup"><span data-stu-id="4adaa-114">For example, if the action is `InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE` then the string will be InterfaceTables.Insert.FND.APPS.MS_SAMPLE_EMPLOYEE.</span></span>  
  
 <span data-ttu-id="4adaa-115">Oracle データ ソースは、接続 URI の指定と同じです。</span><span class="sxs-lookup"><span data-stu-id="4adaa-115">The Oracle data source is the same as specified in the connection URI.</span></span>  
  
 <span data-ttu-id="4adaa-116">パフォーマンス カウンターは、アダプターが、Oracle データベースへの最初の呼び出し後にのみ初期化されます。</span><span class="sxs-lookup"><span data-stu-id="4adaa-116">The performance counter is initialized only after the adapter makes the first call to the Oracle database.</span></span> <span data-ttu-id="4adaa-117">また、パフォーマンス カウンターの InstanceLifetime プロパティは、'Process' は、パフォーマンス カウンターは、カウンターを作成するプログラムが終了するとすぐに存在しなくなることを意味する設定です。</span><span class="sxs-lookup"><span data-stu-id="4adaa-117">Also, the InstanceLifetime property of the performance counter is set to 'Process', which means that the performance counter ceases to exist as soon as the program that creates the counter terminates.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="4adaa-118">LOB Time (累積) パフォーマンス カウンターの有効桁数は、16 ミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="4adaa-118">The precision of the LOB Time (Cumulative) performance counter is 16 milliseconds.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="4adaa-119">パフォーマンス カウンターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4adaa-119">Enabling Performance Counters</span></span>  
 <span data-ttu-id="4adaa-120">パフォーマンス カウンターを有効になっているやバインド プロパティを設定して無効になっている**EnablePerformanceCounters**です。</span><span class="sxs-lookup"><span data-stu-id="4adaa-120">The performance counters can be enabled or disabled by setting the binding property **EnablePerformanceCounters**.</span></span> <span data-ttu-id="4adaa-121">パフォーマンス カウンターを有効にするには設定、 **EnablePerformanceCounters**にプロパティのバインド**True**です。</span><span class="sxs-lookup"><span data-stu-id="4adaa-121">To enable performance counters, set the **EnablePerformanceCounters** binding property to **True**.</span></span> <span data-ttu-id="4adaa-122">パフォーマンス カウンターを無効にする設定**EnablePerformanceCounters**に**False**です。</span><span class="sxs-lookup"><span data-stu-id="4adaa-122">To disable performance counters, set **EnablePerformanceCounters** to **False**.</span></span> <span data-ttu-id="4adaa-123">既定では、 **EnablePerformanceCounters**に設定されている**False**です。</span><span class="sxs-lookup"><span data-stu-id="4adaa-123">By default, **EnablePerformanceCounters** is set to **False**.</span></span>  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="4adaa-124">パフォーマンス カウンターと WCF LOB Adapter SDK</span><span class="sxs-lookup"><span data-stu-id="4adaa-124">Performance Counters and the WCF LOB Adapter SDK</span></span>  
 <span data-ttu-id="4adaa-125">値を変更する、 **EnablePerformanceCounters**に対応するパフォーマンス カウンターの値が変更もプロパティのバインド、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="4adaa-125">Changing the value of the **EnablePerformanceCounters** binding property also changes the value of the corresponding performance counter for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="4adaa-126">バインディング プロパティも、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]静的では、一方の[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]は動的です。</span><span class="sxs-lookup"><span data-stu-id="4adaa-126">Also, the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, whereas that for the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is dynamic.</span></span> <span data-ttu-id="4adaa-127">そのため、2 つのインスタンスがある場合、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] 、AppDomain にバインドされ、 **EnablePerformanceCounters**に設定されているプロパティのバインド**True**いずれかでと**False**アダプター固有のパフォーマンス カウンターのいずれかで有効にし、他の無効になっているは、それ以外のです。</span><span class="sxs-lookup"><span data-stu-id="4adaa-127">Therefore, if there are two instances of the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding in the AppDomain, and the **EnablePerformanceCounters** binding property is set to **True** in one and **False** in the other, the adapter-specific performance counter will be enabled in one and disabled in the other.</span></span> <span data-ttu-id="4adaa-128">ただし、ためのバインディング プロパティ[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で、いずれかに設定されます**True**または**False**によってどのような値を最後に指定されました。</span><span class="sxs-lookup"><span data-stu-id="4adaa-128">However, because the binding property for [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, it will either be set to **True** or **False** depending on what value was specified last.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4adaa-129">参照</span><span class="sxs-lookup"><span data-stu-id="4adaa-129">See Also</span></span>  
[<span data-ttu-id="4adaa-130">アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4adaa-130">Troubleshooting the adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)