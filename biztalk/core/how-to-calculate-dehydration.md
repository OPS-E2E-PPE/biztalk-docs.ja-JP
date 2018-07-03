---
title: 退避を計算する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88f2d09c-60db-4daf-b850-23f2c8915502
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db413cfef1e49f1f3177d8a9f578c94f5a2a1a28
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998147"
---
# <a name="how-to-calculate-dehydration"></a><span data-ttu-id="60578-102">退避を計算する方法</span><span class="sxs-lookup"><span data-stu-id="60578-102">How to Calculate Dehydration</span></span>
<span data-ttu-id="60578-103">退避を計算するには、構成されたプロパティおよび特定の実行時の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="60578-103">To calculate dehydration, you use the configured properties and certain run-time values.</span></span> <span data-ttu-id="60578-104">仮定の退避シナリオを計算する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="60578-104">The following example demonstrates how to calculate a hypothetical dehydration scenario.</span></span>  
  
### <a name="to-calculate-dehydration"></a><span data-ttu-id="60578-105">退避を計算するには</span><span class="sxs-lookup"><span data-stu-id="60578-105">To calculate dehydration</span></span>  
  
1. <span data-ttu-id="60578-106">メモリの負荷を測定する 0 と 1 の間の要素を alpha によって表します。</span><span class="sxs-lookup"><span data-stu-id="60578-106">Let alpha represent a factor between 0 and 1 that measures memory stress.</span></span>  <span data-ttu-id="60578-107">実際には、アルファは、3 つのコンポーネントを持つメモリ制限の条件 (退避プロパティ)。この例ではそれらと示す alpha(virtual)、alpha(private) および alpha(physical)。</span><span class="sxs-lookup"><span data-stu-id="60578-107">In practice, alpha has a component for each of the three memory throttling criteria (dehydration properties); in this example we denote them as alpha(virtual), alpha(private) and alpha(physical).</span></span> <span data-ttu-id="60578-108">次のように定義します。</span><span class="sxs-lookup"><span data-stu-id="60578-108">Define the following:</span></span>  
  
   ```  
   IF ActualPrivateBytes < OptimalUsage  
      alpha(private) = 1  
   ELSE IF ActualPrivateBytes > MaximalUsage  
      alpha(private) = 0  
   ELSE  
      alpha(private) = (MaximalUsage - ActualPrivateBytes) / (MaximalUsage - OptimalUsage)  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="60578-109">OptimalUsage と MaximalUsage には各退避プロパティの既定値があります。</span><span class="sxs-lookup"><span data-stu-id="60578-109">OptimalUsage and MaximalUsage have default values for each dehydration property.</span></span> <span data-ttu-id="60578-110">これらの値は BTSNTSvc.exe.config ファイルで変更できます。</span><span class="sxs-lookup"><span data-stu-id="60578-110">These values can be changed in the BTSNTSvc.exe.config file.</span></span> <span data-ttu-id="60578-111">詳細については、次を参照してください。[既定の退避プロパティ](../core/dehydration-default-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="60578-111">For more information, see [Dehydration Default Properties](../core/dehydration-default-properties.md).</span></span>  
  
2. <span data-ttu-id="60578-112">その他の alpha コンポーネントも同様に定義します。</span><span class="sxs-lookup"><span data-stu-id="60578-112">Define the other alpha components analogously.</span></span> <span data-ttu-id="60578-113">次のように定義します。</span><span class="sxs-lookup"><span data-stu-id="60578-113">Define the following:</span></span>  
  
   ```  
   alpha = Minimum { alpha(virtual), alpha(private), alpha(physical) }  
   where alpha(…) = 1 whenever IsActive=false for that given memory unit  
   ```  
  
3. <span data-ttu-id="60578-114">次に TestThreshold を定義します (TestThreshold、MinThreshold、および MaxThreshold は秒単位で定義します)。</span><span class="sxs-lookup"><span data-stu-id="60578-114">Then define TestThreshold (TestThreshold, MinThreshold, and MaxThreshold are defined in seconds):</span></span>  
  
   ```  
   TestThreshold = MinThreshold + (alpha * (MaxThreshold – MinThreshold))  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="60578-115">MinThreshold の既定値 = 1。</span><span class="sxs-lookup"><span data-stu-id="60578-115">MinThreshold default value = 1.</span></span> <span data-ttu-id="60578-116">MaxThreshold の既定値 = 1800。</span><span class="sxs-lookup"><span data-stu-id="60578-116">MaxThreshold default value = 1800.</span></span> <span data-ttu-id="60578-117">これらの値は BTSNTSvc.exe.config ファイルで変更できます。</span><span class="sxs-lookup"><span data-stu-id="60578-117">These values can be changed in the BTSNTSvc.exe.config file.</span></span> <span data-ttu-id="60578-118">詳細については、次を参照してください。[既定の退避プロパティ](../core/dehydration-default-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="60578-118">For more information, see [Dehydration Default Properties](../core/dehydration-default-properties.md).</span></span>  
  
4. <span data-ttu-id="60578-119">次に TimeBlocked と EstimatedTime を定義します。</span><span class="sxs-lookup"><span data-stu-id="60578-119">Then define TimeBlocked and EstimatedTime:</span></span>  
  
   -   <span data-ttu-id="60578-120">TimeBlocked = サブスクリプションが満たされるまでに待機する実際の時間</span><span class="sxs-lookup"><span data-stu-id="60578-120">TimeBlocked = actual time we have been waiting for this subscription to be satisfied</span></span>  
  
   -   <span data-ttu-id="60578-121">EstimatedTime = このオーケストレーションがアイドルである推定時間 (たとえば、待ち受け中の残りのタイムアウト)</span><span class="sxs-lookup"><span data-stu-id="60578-121">EstimatedTime = estimated time that this orchestration will remain idle (e.g. remaining timeout on the listen)</span></span>  
  
   <span data-ttu-id="60578-122">退避するかどうかの決定は、次のブール値条件の結果によって決まります (true = 退避)。</span><span class="sxs-lookup"><span data-stu-id="60578-122">The decision whether to dehydrate is the result of the following Boolean condition (true = dehydrate):</span></span>  
  
-   <span data-ttu-id="60578-123">待避 = (EstimatedTime > TestThreshold または TimeBlocked > (2\* TestThreshold))</span><span class="sxs-lookup"><span data-stu-id="60578-123">Dehydrate = (EstimatedTime > TestThreshold OR TimeBlocked > (2\* TestThreshold))</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60578-124">推定時間は遅延が終了するまでの残り時間です (5 分間と 2 分間の遅延が経過した場合、TimeBlocked=120 秒、EstimatedTime=180 秒です)。</span><span class="sxs-lookup"><span data-stu-id="60578-124">Estimated time is the time remaining until the delay is ended (if delayed for 5 minutes and 2 minutes has passed, TimeBlocked=120 seconds, EstimatedTime=180 seconds).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60578-125">参照</span><span class="sxs-lookup"><span data-stu-id="60578-125">See Also</span></span>  
 <span data-ttu-id="60578-126">[既定の退避プロパティ](../core/dehydration-default-properties.md) </span><span class="sxs-lookup"><span data-stu-id="60578-126">[Dehydration Default Properties](../core/dehydration-default-properties.md) </span></span>  
 [<span data-ttu-id="60578-127">BTSNTSvc.exe.config ファイル</span><span class="sxs-lookup"><span data-stu-id="60578-127">BTSNTSvc.exe.config File</span></span>](../core/btsntsvc-exe-config-file.md)