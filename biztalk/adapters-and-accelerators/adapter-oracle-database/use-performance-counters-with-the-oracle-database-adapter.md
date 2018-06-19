---
title: Oracle データベース アダプターのパフォーマンス カウンターを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance counters, using
- performance counter, LOB Time Cumulative
- performance counters, enabling
- performance counters, and the WCF LOB Adapter SDK
ms.assetid: beb80896-7594-411e-a83c-169d5278e2ce
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce36fe948daeb89d8fc248dbe33191aa69cdd9ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215186"
---
# <a name="use-performance-counters-with-the-oracle-database-adapter"></a><span data-ttu-id="bb498-102">Oracle データベース アダプターのパフォーマンス カウンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="bb498-102">Use performance counters with the Oracle Database adapter</span></span>
<span data-ttu-id="bb498-103">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]クライアントは、アダプターのパフォーマンスを測定するパフォーマンス カウンターを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="bb498-103">Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] clients can use performance counters to gauge the performance of the adapters.</span></span> <span data-ttu-id="bb498-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムは、パフォーマンス カウンターのカテゴリを作成**BizTalk .NET Adapter for Oracle DB**をインストールすると共に、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="bb498-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program creates the performance counter category **BizTalk .NET Adapter for Oracle DB** along with installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
  
## <a name="lob-time-cumulative-performance-counter"></a><span data-ttu-id="bb498-105">LOB (累積) 時間のパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="bb498-105">LOB Time (Cumulative) Performance Counter</span></span>  
 <span data-ttu-id="bb498-106">**BizTalk .NET Adapter for Oracle DB**カテゴリには 1 つというパフォーマンス カウンター"LOB Time (累積)."</span><span class="sxs-lookup"><span data-stu-id="bb498-106">The **BizTalk .NET Adapter for Oracle DB** category has one performance counter called the “LOB Time (Cumulative).”</span></span> <span data-ttu-id="bb498-107">このパフォーマンス カウンターは、LOB クライアント ライブラリは、アダプターを開始する操作が完了する時間をミリ秒単位で、時間を表します。</span><span class="sxs-lookup"><span data-stu-id="bb498-107">This performance counter denotes the time, in milliseconds, that the LOB client library takes to complete an action that the adapter initiates.</span></span> <span data-ttu-id="bb498-108">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]パターンを次のいずれかで、パフォーマンス カウンターのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="bb498-108">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] creates an instance of the performance counter in any of the following patterns:</span></span>  
  
```  
<process id>:<app domain id>:<oracle data source>:<string>  
```  
  
 <span data-ttu-id="bb498-109">ここで"string"可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bb498-109">Where "string" could be:</span></span>  
  
-   <span data-ttu-id="bb498-110">Connection.Open</span><span class="sxs-lookup"><span data-stu-id="bb498-110">Connection.Open</span></span>  
  
-   <span data-ttu-id="bb498-111">Connection.Close</span><span class="sxs-lookup"><span data-stu-id="bb498-111">Connection.Close</span></span>  
  
-   <span data-ttu-id="bb498-112">メタデータ</span><span class="sxs-lookup"><span data-stu-id="bb498-112">Metadata</span></span>  
  
-   <span data-ttu-id="bb498-113">メッセージ アクション。</span><span class="sxs-lookup"><span data-stu-id="bb498-113">Message action.</span></span> <span data-ttu-id="bb498-114">たとえば、次のアクションは`http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert`SCOTT は文字列になります。Table.EMP.Insert です。</span><span class="sxs-lookup"><span data-stu-id="bb498-114">For example, if the action is `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert` then the string will be SCOTT.Table.EMP.Insert.</span></span>  
  
 <span data-ttu-id="bb498-115">Oracle データ ソースは、接続 URI の指定と同じです。</span><span class="sxs-lookup"><span data-stu-id="bb498-115">The Oracle data source is the same as specified in the connection URI.</span></span>  
  
 <span data-ttu-id="bb498-116">パフォーマンス カウンターは、アダプターが、Oracle データベースへの最初の呼び出し後にのみ初期化されます。</span><span class="sxs-lookup"><span data-stu-id="bb498-116">The performance counter is initialized only after the adapter makes the first call to the Oracle database.</span></span> <span data-ttu-id="bb498-117">また、パフォーマンス カウンターの InstanceLifetime プロパティは、'Process' は、パフォーマンス カウンターは、カウンターを作成するプログラムが終了するとすぐに存在しなくなることを意味する設定です。</span><span class="sxs-lookup"><span data-stu-id="bb498-117">Also, the InstanceLifetime property of the performance counter is set to 'Process', which means that the performance counter ceases to exist as soon as the program that creates the counter terminates.</span></span> <span data-ttu-id="bb498-118">詳細については、`InstanceLifetime property`を参照してください[http://go.microsoft.com/fwlink/p/?LinkId=104181](http://go.microsoft.com/fwlink/p/?LinkId=104181)です。</span><span class="sxs-lookup"><span data-stu-id="bb498-118">For more information about the `InstanceLifetime property`, see [http://go.microsoft.com/fwlink/p/?LinkId=104181](http://go.microsoft.com/fwlink/p/?LinkId=104181).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb498-119">LOB Time (累積) パフォーマンス カウンターの有効桁数は、16 ミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="bb498-119">The precision of the LOB Time (Cumulative) performance counter is 16 milliseconds.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="bb498-120">パフォーマンス カウンターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bb498-120">Enabling Performance Counters</span></span>  
 <span data-ttu-id="bb498-121">パフォーマンス カウンターを有効になっているやバインド プロパティを設定して無効になっている**EnablePerformanceCounters**です。</span><span class="sxs-lookup"><span data-stu-id="bb498-121">The performance counters can be enabled or disabled by setting the binding property **EnablePerformanceCounters**.</span></span> <span data-ttu-id="bb498-122">パフォーマンス カウンターを有効にするには設定、 **EnablePerformanceCounters**にプロパティのバインド**True**です。</span><span class="sxs-lookup"><span data-stu-id="bb498-122">To enable performance counters, set the **EnablePerformanceCounters** binding property to **True**.</span></span> <span data-ttu-id="bb498-123">パフォーマンス カウンターを無効にする設定**EnablePerformanceCounters**に**False**です。</span><span class="sxs-lookup"><span data-stu-id="bb498-123">To disable performance counters, set **EnablePerformanceCounters** to **False**.</span></span> <span data-ttu-id="bb498-124">既定では、 **EnablePerformanceCounters**に設定されている**False**です。</span><span class="sxs-lookup"><span data-stu-id="bb498-124">By default, **EnablePerformanceCounters** is set to **False**.</span></span>  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="bb498-125">パフォーマンス カウンターと WCF LOB Adapter SDK</span><span class="sxs-lookup"><span data-stu-id="bb498-125">Performance Counters and the WCF LOB Adapter SDK</span></span>  
 <span data-ttu-id="bb498-126">値を変更する、 **EnablePerformanceCounters**に対応するパフォーマンス カウンターの値が変更もプロパティのバインド、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="bb498-126">Changing the value of the **EnablePerformanceCounters** binding property also changes the value of the corresponding performance counter for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="bb498-127">バインディング プロパティも、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]静的では、一方の[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]は動的です。</span><span class="sxs-lookup"><span data-stu-id="bb498-127">Also, the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, whereas that for the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is dynamic.</span></span> <span data-ttu-id="bb498-128">そのため、2 つのインスタンスがある場合、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] 、AppDomain にバインドされ、 **EnablePerformanceCounters**に設定されているプロパティのバインド**True**いずれかでと**False**アダプター固有のパフォーマンス カウンターのいずれかで有効にし、他の無効になっているは、それ以外のです。</span><span class="sxs-lookup"><span data-stu-id="bb498-128">Therefore, if there are two instances of the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding in the AppDomain, and the **EnablePerformanceCounters** binding property is set to **True** in one and **False** in the other, the adapter-specific performance counter will be enabled in one and disabled in the other.</span></span> <span data-ttu-id="bb498-129">ただし、ためのバインディング プロパティ[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で、いずれかに設定されます**True**または**False**によってどのような値を最後に指定されました。</span><span class="sxs-lookup"><span data-stu-id="bb498-129">However, because the binding property for [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, it will either be set to **True** or **False** depending on what value was specified last.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb498-130">参照</span><span class="sxs-lookup"><span data-stu-id="bb498-130">See Also</span></span>  
[<span data-ttu-id="bb498-131">Oracle データベース アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="bb498-131">Troubleshoot the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)