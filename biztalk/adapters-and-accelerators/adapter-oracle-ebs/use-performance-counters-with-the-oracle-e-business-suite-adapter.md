---
title: Oracle E-business Suite アダプターを使用したパフォーマンス カウンターの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7d722b7-8343-4956-81ed-acd5a463a9b1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4b2c187dbc33a441de8d11d489c5377c0c4e742
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985011"
---
# <a name="use-performance-counters-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="f33c6-102">Oracle E-business Suite アダプターを使用したパフォーマンス カウンターの使用します。</span><span class="sxs-lookup"><span data-stu-id="f33c6-102">Use Performance Counters with the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="f33c6-103">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]クライアントは、パフォーマンス カウンターを使用して、アダプターのパフォーマンスを測定します。</span><span class="sxs-lookup"><span data-stu-id="f33c6-103">Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] clients can use performance counters to gauge the performance of the adapters.</span></span> <span data-ttu-id="f33c6-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムは、パフォーマンス カウンター カテゴリを作成します。 **BizTalk .NET の Adapter for Oracle E-business Suite**をインストールすると共に、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f33c6-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program creates the performance counter category **BizTalk .NET Adapter for Oracle E-Business Suite** along with installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
  
## <a name="lob-time-cumulative-performance-counter"></a><span data-ttu-id="f33c6-105">LOB Time (累積) パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="f33c6-105">LOB Time (Cumulative) performance counter</span></span>  
 <span data-ttu-id="f33c6-106">**BizTalk .NET の Adapter for Oracle E-business Suite**カテゴリ カウンター"LOB Time (累積)."と呼ばれる 1 つのパフォーマンスには</span><span class="sxs-lookup"><span data-stu-id="f33c6-106">The **BizTalk .NET Adapter for Oracle E-Business Suite** category has one performance counter called the “LOB Time (Cumulative).”</span></span> <span data-ttu-id="f33c6-107">このパフォーマンス カウンターは、LOB クライアント ライブラリは、アダプターを起動する操作を完了するまでをミリ秒単位の時間を示します。</span><span class="sxs-lookup"><span data-stu-id="f33c6-107">This performance counter denotes the time, in milliseconds, that the LOB client library takes to complete an action that the adapter initiates.</span></span> <span data-ttu-id="f33c6-108">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の次のパターンで、パフォーマンス カウンターのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f33c6-108">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] creates an instance of the performance counter in any of the following patterns:</span></span>  
  
```  
<process id>:<app domain id>:<oracle data source>:<string>  
```  
  
 <span data-ttu-id="f33c6-109">場所"string"になります。</span><span class="sxs-lookup"><span data-stu-id="f33c6-109">Where "string" could be:</span></span>  
  
- <span data-ttu-id="f33c6-110">Connection.Open</span><span class="sxs-lookup"><span data-stu-id="f33c6-110">Connection.Open</span></span>  
  
- <span data-ttu-id="f33c6-111">Connection.Close</span><span class="sxs-lookup"><span data-stu-id="f33c6-111">Connection.Close</span></span>  
  
- <span data-ttu-id="f33c6-112">メタデータ</span><span class="sxs-lookup"><span data-stu-id="f33c6-112">Metadata</span></span>  
  
- <span data-ttu-id="f33c6-113">メッセージ アクション。</span><span class="sxs-lookup"><span data-stu-id="f33c6-113">Message action.</span></span> <span data-ttu-id="f33c6-114">たとえば、次のアクションが`InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`文字列は InterfaceTables.Insert.FND.APPS.MS_SAMPLE_EMPLOYEE になります。</span><span class="sxs-lookup"><span data-stu-id="f33c6-114">For example, if the action is `InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE` then the string will be InterfaceTables.Insert.FND.APPS.MS_SAMPLE_EMPLOYEE.</span></span>  
  
  <span data-ttu-id="f33c6-115">Oracle データ ソースは、接続 URI で指定されている同じです。</span><span class="sxs-lookup"><span data-stu-id="f33c6-115">The Oracle data source is the same as specified in the connection URI.</span></span>  
  
  <span data-ttu-id="f33c6-116">パフォーマンス カウンターは、アダプターが Oracle データベースへの最初の呼び出し後にのみ初期化されます。</span><span class="sxs-lookup"><span data-stu-id="f33c6-116">The performance counter is initialized only after the adapter makes the first call to the Oracle database.</span></span> <span data-ttu-id="f33c6-117">また、パフォーマンス カウンターの InstanceLifetime プロパティは、'Process' は、パフォーマンス カウンターがカウンターを作成するプログラムが終了するとすぐには存在しなくなりますに設定されます。</span><span class="sxs-lookup"><span data-stu-id="f33c6-117">Also, the InstanceLifetime property of the performance counter is set to 'Process', which means that the performance counter ceases to exist as soon as the program that creates the counter terminates.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="f33c6-118">LOB の時間 (累積) パフォーマンス カウンターの有効桁数は、16 ミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="f33c6-118">The precision of the LOB Time (Cumulative) performance counter is 16 milliseconds.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="f33c6-119">パフォーマンス カウンターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f33c6-119">Enabling Performance Counters</span></span>  
 <span data-ttu-id="f33c6-120">パフォーマンス カウンターを有効またはバインドのプロパティを設定して無効にできる**EnablePerformanceCounters**します。</span><span class="sxs-lookup"><span data-stu-id="f33c6-120">The performance counters can be enabled or disabled by setting the binding property **EnablePerformanceCounters**.</span></span> <span data-ttu-id="f33c6-121">パフォーマンス カウンターを有効にするには設定、 **EnablePerformanceCounters**プロパティをバインド**True**します。</span><span class="sxs-lookup"><span data-stu-id="f33c6-121">To enable performance counters, set the **EnablePerformanceCounters** binding property to **True**.</span></span> <span data-ttu-id="f33c6-122">パフォーマンス カウンターを無効にするには設定**EnablePerformanceCounters**に**False**します。</span><span class="sxs-lookup"><span data-stu-id="f33c6-122">To disable performance counters, set **EnablePerformanceCounters** to **False**.</span></span> <span data-ttu-id="f33c6-123">既定では、 **EnablePerformanceCounters**に設定されている**False**します。</span><span class="sxs-lookup"><span data-stu-id="f33c6-123">By default, **EnablePerformanceCounters** is set to **False**.</span></span>  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="f33c6-124">パフォーマンス カウンターと WCF LOB Adapter SDK</span><span class="sxs-lookup"><span data-stu-id="f33c6-124">Performance Counters and the WCF LOB Adapter SDK</span></span>  
 <span data-ttu-id="f33c6-125">値を変更する、 **EnablePerformanceCounters**に対応するパフォーマンス カウンターの値を変更してもプロパティをバインド、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f33c6-125">Changing the value of the **EnablePerformanceCounters** binding property also changes the value of the corresponding performance counter for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="f33c6-126">バインド プロパティも、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で一方の場合、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]は動的です。</span><span class="sxs-lookup"><span data-stu-id="f33c6-126">Also, the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, whereas that for the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is dynamic.</span></span> <span data-ttu-id="f33c6-127">そのため、2 つのインスタンスがある場合、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] 、appdomain のバインドと**EnablePerformanceCounters**に設定されているプロパティのバインド**True**いずれかでと**False**アダプター固有のパフォーマンス カウンターのいずれかで有効にし、他の無効になっているで、他のです。</span><span class="sxs-lookup"><span data-stu-id="f33c6-127">Therefore, if there are two instances of the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding in the AppDomain, and the **EnablePerformanceCounters** binding property is set to **True** in one and **False** in the other, the adapter-specific performance counter will be enabled in one and disabled in the other.</span></span> <span data-ttu-id="f33c6-128">ただし、ためのバインディング プロパティ[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で、いずれかに設定されます**True**または**False**によってどのような値を最後に指定されました。</span><span class="sxs-lookup"><span data-stu-id="f33c6-128">However, because the binding property for [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, it will either be set to **True** or **False** depending on what value was specified last.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f33c6-129">参照</span><span class="sxs-lookup"><span data-stu-id="f33c6-129">See Also</span></span>  
[<span data-ttu-id="f33c6-130">アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f33c6-130">Troubleshooting the adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)