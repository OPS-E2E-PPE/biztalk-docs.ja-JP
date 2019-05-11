---
title: SQL アダプタのサンプル |Microsoft Docs
description: BizTalk Server、WCF サービス モデル、および WCF チャネル モデルで使用できる SQL WCF アダプタのサンプル
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2438696-bc51-46df-81ca-00c17a52736e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90a937d53b9a8f09ad8ed20633cca1bedfefc6a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368115"
---
# <a name="samples-for-the-sql-adapter"></a><span data-ttu-id="709f7-103">SQL アダプタのサンプル</span><span class="sxs-lookup"><span data-stu-id="709f7-103">Samples for the SQL adapter</span></span>

<span data-ttu-id="709f7-104">サンプルは[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]に分類されます。</span><span class="sxs-lookup"><span data-stu-id="709f7-104">Samples for [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] are categorized into:</span></span>  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="709f7-105">サンプル</span><span class="sxs-lookup"><span data-stu-id="709f7-105">samples</span></span>  
  
- <span data-ttu-id="709f7-106">WCF サービス モデルのサンプル</span><span class="sxs-lookup"><span data-stu-id="709f7-106">WCF service model samples</span></span>  
  
- <span data-ttu-id="709f7-107">WCF チャネル モデルのサンプル</span><span class="sxs-lookup"><span data-stu-id="709f7-107">WCF channel model samples</span></span>  
  
<span data-ttu-id="709f7-108">サンプルについては、「 [BizTalk Adapter Pack 2010。SQL アダプタ サンプル](https://www.microsoft.com/download/details.aspx?id=22455)します。</span><span class="sxs-lookup"><span data-stu-id="709f7-108">The samples are available at [BizTalk Adapter Pack 2010: SQL adapter samples](https://www.microsoft.com/download/details.aspx?id=22455).</span></span> <span data-ttu-id="709f7-109">テーブル、データベースなどのサンプルで使用されるオブジェクトを作成するための SQL スクリプトと手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="709f7-109">The SQL scripts for creating the objects used in the samples, such as database, tables, and procedures are included.</span></span> 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
<span data-ttu-id="709f7-110">サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-110">The following list describes the samples.</span></span>
  
## <a name="biztalk-server-samples"></a><span data-ttu-id="709f7-111">BizTalk Server のサンプル</span><span class="sxs-lookup"><span data-stu-id="709f7-111">BizTalk Server samples</span></span>  
  
|  <span data-ttu-id="709f7-112">サンプルのディレクトリ名</span><span class="sxs-lookup"><span data-stu-id="709f7-112">Sample Directory Name</span></span>  |                                                                                          <span data-ttu-id="709f7-113">説明</span><span class="sxs-lookup"><span data-stu-id="709f7-113">Description</span></span>                                                                                          |
|-------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="709f7-114">ExecuteStoredProcedure</span><span class="sxs-lookup"><span data-stu-id="709f7-114">ExecuteStoredProcedure</span></span>  |      <span data-ttu-id="709f7-115">アダプターを使用して SQL Server データベース内のストアド プロシージャを呼び出す方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="709f7-115">Demonstrates how to invoke a stored procedure in SQL Server database using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] .</span></span>      |
|       <span data-ttu-id="709f7-116">SelectTable</span><span class="sxs-lookup"><span data-stu-id="709f7-116">SelectTable</span></span>       |  <span data-ttu-id="709f7-117">アダプターを使用して SQL Server データベース テーブルでの選択操作を実行する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="709f7-117">Demonstrates how to perform a Select operation on a SQL Server database table using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  |
|   <span data-ttu-id="709f7-118">CompositeOperations</span><span class="sxs-lookup"><span data-stu-id="709f7-118">CompositeOperations</span></span>   |    <span data-ttu-id="709f7-119">アダプターを使用して SQL Server データベースでの複合操作を実行する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="709f7-119">Demonstrates how to perform composite operations on a SQL Server database using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>    |
|      <span data-ttu-id="709f7-120">TypedPolling</span><span class="sxs-lookup"><span data-stu-id="709f7-120">TypedPolling</span></span>       |   <span data-ttu-id="709f7-121">アダプターを使用して SQL Server データベースで厳密に型指定されたポーリングを実行する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="709f7-121">Demonstrates how to perform strongly-typed polling on a SQL Server database using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>   |
|   <span data-ttu-id="709f7-122">FILESTREAMOperation</span><span class="sxs-lookup"><span data-stu-id="709f7-122">FILESTREAMOperation</span></span>   | <span data-ttu-id="709f7-123">アダプターを使用してデータベースを SQL Server 2008 の FILESTREAM 操作を実行する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="709f7-123">Demonstrates how to perform FILESTREAM operations on a SQL Server 2008 database using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> |
| <span data-ttu-id="709f7-124">IncrementalNotification</span><span class="sxs-lookup"><span data-stu-id="709f7-124">IncrementalNotification</span></span> | <span data-ttu-id="709f7-125">アダプターを使用して SQL Server データベースからインクリメンタル通知を受信する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="709f7-125">Demonstrates how to receive incremental notification from a SQL Server database using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> |
| <span data-ttu-id="709f7-126">Employee_PurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="709f7-126">Employee_PurchaseOrder</span></span>  |                  <span data-ttu-id="709f7-127">サンプルに基づいて[チュートリアル 2。従業員 - 発注プロセス SQL アダプターを使用して](tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="709f7-127">Sample based on [Tutorial 2: Employee - Purchase Order Process using the SQL adapter](tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md).</span></span>                  |
  
## <a name="wcf-service-model-samples"></a><span data-ttu-id="709f7-128">WCF サービス モデルのサンプル</span><span class="sxs-lookup"><span data-stu-id="709f7-128">WCF service model samples</span></span>   
  
|<span data-ttu-id="709f7-129">サンプルのディレクトリ名</span><span class="sxs-lookup"><span data-stu-id="709f7-129">Sample Directory Name</span></span>|<span data-ttu-id="709f7-130">説明</span><span class="sxs-lookup"><span data-stu-id="709f7-130">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="709f7-131">EmployeeBasicOps</span><span class="sxs-lookup"><span data-stu-id="709f7-131">EmployeeBasicOps</span></span>|<span data-ttu-id="709f7-132">Insert、Select、Update を実行して、アダプターを使用して SQL Server データベースでの操作を削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-132">Demonstrates how to perform Insert, Select, Update, and Delete operation on a SQL Server database using the adapter.</span></span>|  
|<span data-ttu-id="709f7-133">ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="709f7-133">ExecuteReader</span></span>|<span data-ttu-id="709f7-134">アダプターを使用して SQL Server データベースで ExecuteReader 操作を呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-134">Demonstrates how to invoke an ExecuteReader operation on a SQL Server database using the adapter.</span></span>|  
|<span data-ttu-id="709f7-135">Execute_StoredProc</span><span class="sxs-lookup"><span data-stu-id="709f7-135">Execute_StoredProc</span></span>|<span data-ttu-id="709f7-136">アダプターを使用して SQL Server データベースでストアド プロシージャを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-136">Demonstrates how to invoke a stored procedure in SQL Server database using the adapter.</span></span>|  
|<span data-ttu-id="709f7-137">Execute_TypedStoredProcedure</span><span class="sxs-lookup"><span data-stu-id="709f7-137">Execute_TypedStoredProcedure</span></span>|<span data-ttu-id="709f7-138">厳密に型指定されたアダプターを使用して SQL Server データベースでストアド プロシージャを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-138">Demonstrates how to invoke a strongly-typed stored procedure in SQL Server database using the adapter.</span></span>|  
|<span data-ttu-id="709f7-139">Records_FILESTREAM_Op</span><span class="sxs-lookup"><span data-stu-id="709f7-139">Records_FILESTREAM_Op</span></span>|<span data-ttu-id="709f7-140">アダプターを使用して SQL Server データベース テーブル内の FILESTREAM データを更新する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-140">Demonstrates how to update FILESTREAM data in a SQL Server database table using the adapter.</span></span>|  
|<span data-ttu-id="709f7-141">ScalarFunction_ServiceModel</span><span class="sxs-lookup"><span data-stu-id="709f7-141">ScalarFunction_ServiceModel</span></span>|<span data-ttu-id="709f7-142">アダプターを使用して SQL Server データベースのスカラー関数を呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-142">Demonstrates how to invoke scalar functions in a SQL Server database using the adapter.</span></span>|  
|<span data-ttu-id="709f7-143">TableFunction_ServiceModel</span><span class="sxs-lookup"><span data-stu-id="709f7-143">TableFunction_ServiceModel</span></span>|<span data-ttu-id="709f7-144">アダプターを使用して SQL Server データベースのテーブル値関数を呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-144">Demonstrates how to invoke table-valued functions in a SQL Server database using the adapter.</span></span>|  
|<span data-ttu-id="709f7-145">Polling_ServiceModel</span><span class="sxs-lookup"><span data-stu-id="709f7-145">Polling_ServiceModel</span></span>|<span data-ttu-id="709f7-146">アダプターを使用して SQL Server データベースからのポーリングに基づいたデータ変更メッセージを受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-146">Demonstrates how to receive polling-based data-changed messages from a SQL Server database using the adapter.</span></span>|  
|<span data-ttu-id="709f7-147">TypedPolling_ServiceModel</span><span class="sxs-lookup"><span data-stu-id="709f7-147">TypedPolling_ServiceModel</span></span>|<span data-ttu-id="709f7-148">アダプターを使用して SQL Server データベースからのポーリングに基づいたデータ変更メッセージを厳密に型指定されたを受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-148">Demonstrates how to receive strongly-typed polling-based data-changed messages from a SQL Server database using the adapter.</span></span>|  
|<span data-ttu-id="709f7-149">Notification_ServiceModel</span><span class="sxs-lookup"><span data-stu-id="709f7-149">Notification_ServiceModel</span></span>|<span data-ttu-id="709f7-150">アダプターを使用して SQL Server データベースからクエリ通知を受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-150">Demonstrates how to receive query notifications from a SQL Server database using the adapter.</span></span>|  
  
## <a name="wcf-channel-model-samples"></a><span data-ttu-id="709f7-151">WCF チャネル モデルのサンプル</span><span class="sxs-lookup"><span data-stu-id="709f7-151">WCF channel model samples</span></span> 
  
|<span data-ttu-id="709f7-152">サンプルのディレクトリ名</span><span class="sxs-lookup"><span data-stu-id="709f7-152">Sample Directory Name</span></span>|<span data-ttu-id="709f7-153">説明</span><span class="sxs-lookup"><span data-stu-id="709f7-153">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="709f7-154">EmployeeInsertOp</span><span class="sxs-lookup"><span data-stu-id="709f7-154">EmployeeInsertOp</span></span>|<span data-ttu-id="709f7-155">アダプターを使用して SQL Server データベースに対して、挿入操作を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-155">Demonstrates how to perform an Insert operation on a SQL Server database using the adapter.</span></span>|  
|<span data-ttu-id="709f7-156">Polling_ChannelModel</span><span class="sxs-lookup"><span data-stu-id="709f7-156">Polling_ChannelModel</span></span>|<span data-ttu-id="709f7-157">アダプターを使用して SQL Server データベースからのポーリングに基づいたデータ変更メッセージを受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="709f7-157">Demonstrates how to receive polling-based data-changed messages from a SQL Server database using the adapter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="709f7-158">参照</span><span class="sxs-lookup"><span data-stu-id="709f7-158">See Also</span></span>  
[<span data-ttu-id="709f7-159">SQL アプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="709f7-159">Develop your SQL applications</span></span>](develop-your-sql-applications.md)