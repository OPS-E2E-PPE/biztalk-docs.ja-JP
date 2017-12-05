---
title: "SQL アダプターのパフォーマンス カウンターを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae381b78-d89e-4cf2-810b-821e49422463
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f81189e34346d377686dac79b44e5a9b34889dc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="use-performance-counters-with-the-sql-adapter"></a><span data-ttu-id="745bd-102">SQL アダプターのパフォーマンス カウンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="745bd-102">Use Performance Counters with the SQL adapter</span></span>
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]<span data-ttu-id="745bd-103">クライアントは、アダプターのパフォーマンスを測定するのにパフォーマンス カウンターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="745bd-103"> clients can use the performance counters to gauge the performance of the adapters.</span></span> <span data-ttu-id="745bd-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムによって作成のパフォーマンス カウンター カテゴリ"[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]"アダプター パックのインストールと共にします。</span><span class="sxs-lookup"><span data-stu-id="745bd-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program creates the performance counter category "[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]" along with the Adapter Pack installation.</span></span>  
  
## <a name="the-lob-time-cumulative-performance-counter"></a><span data-ttu-id="745bd-105">LOB (累積) 時間のパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="745bd-105">The LOB Time (Cumulative) Performance Counter</span></span>  
 <span data-ttu-id="745bd-106">**SQL 用の BizTalk .NET アダプター**カテゴリには 1 つのパフォーマンス カウンター「LOB 時間 (累積)」と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="745bd-106">The **BizTalk .NET Adapter for SQL** category has one performance counter called "LOB Time (Cumulative)".</span></span> <span data-ttu-id="745bd-107">このパフォーマンス カウンターは、SQL Server のクライアント ライブラリがアダプターを開始する操作が完了する時間をミリ秒単位で、時間を表します。</span><span class="sxs-lookup"><span data-stu-id="745bd-107">This performance counter denotes the time, in milliseconds, that the SQL Server client library takes to complete an action that the adapter initiates.</span></span> <span data-ttu-id="745bd-108">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]特定の SQL Server インスタンスおよびデータベースの名前については、各操作のパフォーマンス カウンターのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="745bd-108">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] creates an instance of the performance counter for each action, for a specific SQL Server instance and database name.</span></span> <span data-ttu-id="745bd-109">次のパターンでは、インスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="745bd-109">The instances are created in the following pattern:</span></span>  
  
```  
<processId>:<appDomainId>:<endpointId>:<actionId>  
```  
  
 <span data-ttu-id="745bd-110">`<endpointId>`として派生`<sql_server_name>, <instance_name>, <database_name>`です。</span><span class="sxs-lookup"><span data-stu-id="745bd-110">The `<endpointId>` is derived as `<sql_server_name>, <instance_name>, <database_name>`.</span></span>  
  
 <span data-ttu-id="745bd-111">\<ActionId\>は次のように派生します。</span><span class="sxs-lookup"><span data-stu-id="745bd-111">The \<actionId\> is derived in the following manner:</span></span>  
  
-   <span data-ttu-id="745bd-112">接続を開くには、アクション ID「開く」です。</span><span class="sxs-lookup"><span data-stu-id="745bd-112">For opening a connection, the action ID is “Open”.</span></span>  
  
-   <span data-ttu-id="745bd-113">受信操作は、操作 ID は"Inbound"です。</span><span class="sxs-lookup"><span data-stu-id="745bd-113">For inbound operations, the action ID is “Inbound”.</span></span>  
  
-   <span data-ttu-id="745bd-114">送信操作は、操作 ID は、呼び出される操作のアクションと「/」は、アンダー スコア「_」に置換します。</span><span class="sxs-lookup"><span data-stu-id="745bd-114">For outbound operations, the action ID is the action of the operation being invoked, with “/” replaced by an underscore “_”.</span></span> <span data-ttu-id="745bd-115">また、アクション ID が付いて"ExecuteScalar"、"ExecuteReader"または"ExecuteNonQuery"方法によっては、アダプターは、SQL Server データベースで操作を実行する内部で使用します。</span><span class="sxs-lookup"><span data-stu-id="745bd-115">Also, the action ID is prefixed with the “ExecuteScalar”, “ExecuteReader”, or “ExecuteNonQuery” depending on the method that the adapter internally uses to perform the operation on the SQL Server database.</span></span> <span data-ttu-id="745bd-116">アダプターが内部的に使用するなど、 **ExecuteReader** SQL Server でストアド プロシージャを実行するメソッド。</span><span class="sxs-lookup"><span data-stu-id="745bd-116">For example, the adapter internally uses the **ExecuteReader** method to execute a stored procedure in SQL Server.</span></span> <span data-ttu-id="745bd-117">そのため、ストアド プロシージャで MyProcedure、操作 ID になります。</span><span class="sxs-lookup"><span data-stu-id="745bd-117">So, the action ID for the stored procedure, MyProcedure, will be:</span></span>  
  
    ```  
    ExecuteReader_Procedure_dbo_MyProcedure  
    ```  

 <span data-ttu-id="745bd-118">パフォーマンス カウンターは、アダプターが SQL Server データベースへの最初の呼び出し後にのみ初期化されます。</span><span class="sxs-lookup"><span data-stu-id="745bd-118">The performance counter is initialized only after the adapter makes the first call to the SQL Server database.</span></span> <span data-ttu-id="745bd-119">また、 [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx)パフォーマンス カウンターのプロパティが 'Process' は、パフォーマンス カウンターは、カウンターを作成するプログラムが終了するとすぐに存在しなくなることを意味します。</span><span class="sxs-lookup"><span data-stu-id="745bd-119">Also, the [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx) property of the performance counter is set to 'Process', which means that the performance counter ceases to exist as soon as the program that creates the counter terminates.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="745bd-120">LOB Time (累積) パフォーマンス カウンターの有効桁数は、16 ミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="745bd-120">The precision of the LOB Time (Cumulative) performance counter is 16 milliseconds.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="745bd-121">パフォーマンス カウンターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="745bd-121">Enabling Performance Counters</span></span>  
 <span data-ttu-id="745bd-122">パフォーマンス カウンターを有効になっているやバインド プロパティを設定して無効になっている**EnablePerformanceCounters**です。</span><span class="sxs-lookup"><span data-stu-id="745bd-122">The performance counters can be enabled or disabled by setting the binding property **EnablePerformanceCounters**.</span></span> <span data-ttu-id="745bd-123">パフォーマンス カウンターを有効にするには設定、 **EnablePerformanceCounters**にプロパティのバインド**True**です。</span><span class="sxs-lookup"><span data-stu-id="745bd-123">To enable performance counters, set the **EnablePerformanceCounters** binding property to **True**.</span></span> <span data-ttu-id="745bd-124">パフォーマンス カウンターを無効にする設定**EnablePerformanceCounters**に**False**です。</span><span class="sxs-lookup"><span data-stu-id="745bd-124">To disable performance counters, set **EnablePerformanceCounters** to **False**.</span></span> <span data-ttu-id="745bd-125">既定では、プロパティに設定が**False**です。</span><span class="sxs-lookup"><span data-stu-id="745bd-125">By default, the property is set to **False**.</span></span> <span data-ttu-id="745bd-126">このバインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="745bd-126">For more information about this binding property, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="745bd-127">パフォーマンス カウンターと WCF LOB Adapter SDK</span><span class="sxs-lookup"><span data-stu-id="745bd-127">Performance Counters and the WCF LOB Adapter SDK</span></span>  
 <span data-ttu-id="745bd-128">値を変更する、 **EnablePerformanceCounters**に対応するパフォーマンス カウンターの値が変更もプロパティのバインド、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="745bd-128">Changing the value of the **EnablePerformanceCounters** binding property also changes the value of the corresponding performance counter for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="745bd-129">バインディング プロパティも、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]静的では、一方の[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]は動的です。</span><span class="sxs-lookup"><span data-stu-id="745bd-129">Also, the binding property for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, whereas that for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is dynamic.</span></span> <span data-ttu-id="745bd-130">そのため、2 つのインスタンスがある場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アプリケーション ドメインでのバインディング、および**EnablePerformanceCounters**に設定されているプロパティのバインド**True**いずれかでと**False**アダプター固有のパフォーマンス カウンターのいずれかで有効にし、他の無効になっているは、それ以外のです。</span><span class="sxs-lookup"><span data-stu-id="745bd-130">Hence, if there are two instances of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding in the application domain, and the **EnablePerformanceCounters** binding property is set to **True** in one and **False** in the other, the adapter-specific performance counter will be enabled in one and disabled in the other.</span></span> <span data-ttu-id="745bd-131">ただし、ためのバインディング プロパティ[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で、いずれかに設定されます**True**または**False**によってどのような値を最後に指定されました。</span><span class="sxs-lookup"><span data-stu-id="745bd-131">However, because the binding property for [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is static, it will either be set to **True** or **False** depending on what value was specified last.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="745bd-132">参照</span><span class="sxs-lookup"><span data-stu-id="745bd-132">See Also</span></span>  
[<span data-ttu-id="745bd-133">SQL アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="745bd-133">Troubleshoot the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)