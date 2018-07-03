---
title: Oracle データベース アダプターのサンプル |Microsoft Docs
description: BizTalk Server、WCF サービス モデル、および WCF チャネル モデルで使用できる oracle DB の WCF アダプタのサンプル
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 744f19ce-3126-4745-92dd-4f68443180fc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ac7a1c2cda4fd66e450d23022787f5e7d0e0324
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006451"
---
# <a name="samples-for-the-oracle-database-adapter"></a><span data-ttu-id="7d1c1-103">Oracle データベース アダプターのサンプル</span><span class="sxs-lookup"><span data-stu-id="7d1c1-103">Samples for the Oracle Database adapter</span></span>
<span data-ttu-id="7d1c1-104">サンプルは[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]に分類されます。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-104">Samples for [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] are categorized into:</span></span>  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7d1c1-105"> サンプル</span><span class="sxs-lookup"><span data-stu-id="7d1c1-105"> samples</span></span>  
  
- <span data-ttu-id="7d1c1-106">WCF サービス モデルのサンプル</span><span class="sxs-lookup"><span data-stu-id="7d1c1-106">WCF service model samples</span></span>  
  
- <span data-ttu-id="7d1c1-107">WCF チャネル モデルのサンプル</span><span class="sxs-lookup"><span data-stu-id="7d1c1-107">WCF channel model samples</span></span>  

  
<span data-ttu-id="7d1c1-108">サンプルについては、「 [BizTalk Adapter Pack 2010: Oracle データベース アダプタ サンプル](https://www.microsoft.com/download/details.aspx?id=4675)します。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-108">The samples are available at [BizTalk Adapter Pack 2010: Oracle Database adapter samples](https://www.microsoft.com/download/details.aspx?id=4675).</span></span> <span data-ttu-id="7d1c1-109">テーブルと、サンプルで使用されるパッケージを作成するための SQL スクリプトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-109">The SQL scripts for creating the tables and packages used in the samples are included.</span></span> 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
<span data-ttu-id="7d1c1-110">サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-110">The following list describes the samples.</span></span>
  
## <a name="biztalk-server-samples"></a><span data-ttu-id="7d1c1-111">BizTalk Server のサンプル</span><span class="sxs-lookup"><span data-stu-id="7d1c1-111">BizTalk Server samples</span></span>
  
| <span data-ttu-id="7d1c1-112">サンプルのディレクトリ名</span><span class="sxs-lookup"><span data-stu-id="7d1c1-112">Sample Directory Name</span></span> |                                                                                         <span data-ttu-id="7d1c1-113">説明</span><span class="sxs-lookup"><span data-stu-id="7d1c1-113">Description</span></span>                                                                                         |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   <span data-ttu-id="7d1c1-114">Func_RecordTypes</span><span class="sxs-lookup"><span data-stu-id="7d1c1-114">Func_RecordTypes</span></span>    |      <span data-ttu-id="7d1c1-115">レコード型のパラメーターを使用する関数とプロシージャを使用して値を返す方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-115">Demonstrates how to use RECORD type parameters and return values in functions and procedures using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>      |
|    <span data-ttu-id="7d1c1-116">Func_RefCursor</span><span class="sxs-lookup"><span data-stu-id="7d1c1-116">Func_RefCursor</span></span>     |               <span data-ttu-id="7d1c1-117">関数とプロシージャを使用して REF CURSOR パラメーターを使用する方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-117">Demonstrates how to use REF CURSOR parameters in functions and procedures using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>                |
|    <span data-ttu-id="7d1c1-118">InvokeFunction</span><span class="sxs-lookup"><span data-stu-id="7d1c1-118">InvokeFunction</span></span>     |                        <span data-ttu-id="7d1c1-119">使用して Oracle データベース内の関数を呼び出す方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-119">Demonstrates how to invoke a function in Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>                        |
| <span data-ttu-id="7d1c1-120">InvokeOverloadedProc</span><span class="sxs-lookup"><span data-stu-id="7d1c1-120">InvokeOverloadedProc</span></span>  |         <span data-ttu-id="7d1c1-121">オーバー ロードされた関数を使用して Oracle データベースでプロシージャを呼び出す方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-121">Demonstrates how to invoke with overloaded functions and procedures in Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>         |
|     <span data-ttu-id="7d1c1-122">Operate_BFILE</span><span class="sxs-lookup"><span data-stu-id="7d1c1-122">Operate_BFILE</span></span>     |                    <span data-ttu-id="7d1c1-123">使用して Oracle プロシージャで Oracle BFILE 型を使用する方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-123">Demonstrates how to use Oracle BFILE types in Oracle procedures using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>                     |
|      <span data-ttu-id="7d1c1-124">Operate_LOB</span><span class="sxs-lookup"><span data-stu-id="7d1c1-124">Operate_LOB</span></span>      |       <span data-ttu-id="7d1c1-125">使用して LOB データ型を持つテーブルで ReadLOB と UpdateLOB の操作を実行する方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-125">Demonstrates how to perform ReadLOB and UpdateLOB operations on tables with LOB data types using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>       |
|     <span data-ttu-id="7d1c1-126">PollingQuery</span><span class="sxs-lookup"><span data-stu-id="7d1c1-126">PollingQuery</span></span>      |                 <span data-ttu-id="7d1c1-127">ポーリング クエリを構成しを使用して結果を受信する方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-127">Demonstrates how to configure a polling query and receive the results using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>                  |
|    <span data-ttu-id="7d1c1-128">SelectAccTable</span><span class="sxs-lookup"><span data-stu-id="7d1c1-128">SelectAccTable</span></span>     |                 <span data-ttu-id="7d1c1-129">Oracle データベースを使用してテーブルに対して select クエリを実行する方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-129">Demonstrates how to perform a select query on an Oracle database table using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>                 |
|        <span data-ttu-id="7d1c1-130">SqlExec</span><span class="sxs-lookup"><span data-stu-id="7d1c1-130">SqlExec</span></span>        | <span data-ttu-id="7d1c1-131">SQLEXECUTE 操作を使用して Oracle データベースを使用してパラメーター化クエリを実行する方法を示します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-131">Demonstrates how to perform parameterized queries using the SQLEXECUTE operation on an Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> |
  
## <a name="wcf-service-model-samples"></a><span data-ttu-id="7d1c1-132">WCF サービス モデルのサンプル</span><span class="sxs-lookup"><span data-stu-id="7d1c1-132">WCF service model samples</span></span>  
  
|<span data-ttu-id="7d1c1-133">サンプルのディレクトリ名</span><span class="sxs-lookup"><span data-stu-id="7d1c1-133">Sample Directory Name</span></span>|<span data-ttu-id="7d1c1-134">説明</span><span class="sxs-lookup"><span data-stu-id="7d1c1-134">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="7d1c1-135">OracleBfileTypeSM</span><span class="sxs-lookup"><span data-stu-id="7d1c1-135">OracleBfileTypeSM</span></span>|<span data-ttu-id="7d1c1-136">Oracle のテーブルに対して、パラメーターとしてを明らかに Oracle プロシージャの基本的な SQL 操作で Oracle BFILE 型を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-136">Demonstrates how to use Oracle BFILE types in basic SQL operations surfaced for Oracle tables and as parameters to Oracle procedures.</span></span>|  
|<span data-ttu-id="7d1c1-137">OracleOverloadsSM</span><span class="sxs-lookup"><span data-stu-id="7d1c1-137">OracleOverloadsSM</span></span>|<span data-ttu-id="7d1c1-138">オーバー ロードされた関数と、パッケージ内のプロシージャを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-138">Demonstrates how to invoke overloaded functions and procedures in a package.</span></span>|  
|<span data-ttu-id="7d1c1-139">OraclePollingSM</span><span class="sxs-lookup"><span data-stu-id="7d1c1-139">OraclePollingSM</span></span>|<span data-ttu-id="7d1c1-140">ポーリング クエリを構成し、結果を受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-140">Demonstrates how to configure a polling query and receive the results.</span></span>|  
|<span data-ttu-id="7d1c1-141">OracleRecordTypesSM</span><span class="sxs-lookup"><span data-stu-id="7d1c1-141">OracleRecordTypesSM</span></span>|<span data-ttu-id="7d1c1-142">レコード型のパラメーターを使用し、関数およびプロシージャで値を返す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-142">Demonstrates how to use RECORD type parameters and return values in functions and procedures.</span></span>|  
|<span data-ttu-id="7d1c1-143">OracleRefCursorsSM</span><span class="sxs-lookup"><span data-stu-id="7d1c1-143">OracleRefCursorsSM</span></span>|<span data-ttu-id="7d1c1-144">関数およびプロシージャの REF CURSOR パラメーターを使用する方法を示します</span><span class="sxs-lookup"><span data-stu-id="7d1c1-144">Demonstrates how to use REF CURSOR parameters in functions and procedures</span></span>|  
|<span data-ttu-id="7d1c1-145">OracleTransactedDmlSM</span><span class="sxs-lookup"><span data-stu-id="7d1c1-145">OracleTransactedDmlSM</span></span>|<span data-ttu-id="7d1c1-146">WCF サービス モデルを使用して、トランザクションで Oracle データベースで操作を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-146">Demonstrates how to perform operations on the Oracle database in a transaction using the WCF service model.</span></span>|  
  
## <a name="wcf-channel-model-samples"></a><span data-ttu-id="7d1c1-147">WCF チャネル モデルのサンプル</span><span class="sxs-lookup"><span data-stu-id="7d1c1-147">WCF channel model samples</span></span>  
  
|<span data-ttu-id="7d1c1-148">サンプルのディレクトリ名</span><span class="sxs-lookup"><span data-stu-id="7d1c1-148">Sample Directory Name</span></span>|<span data-ttu-id="7d1c1-149">説明</span><span class="sxs-lookup"><span data-stu-id="7d1c1-149">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="7d1c1-150">OraclePollingCM</span><span class="sxs-lookup"><span data-stu-id="7d1c1-150">OraclePollingCM</span></span>|<span data-ttu-id="7d1c1-151">ポーリング クエリを構成し、結果を受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-151">Demonstrates how to configure a polling query and receive the results.</span></span>|  
|<span data-ttu-id="7d1c1-152">OracleStreamingDemo</span><span class="sxs-lookup"><span data-stu-id="7d1c1-152">OracleStreamingDemo</span></span>|<span data-ttu-id="7d1c1-153">エンド ツー エンド UpdateLOB とテーブルの Select 操作を使用して LOB データのストリーミングを実行する方法を示します</span><span class="sxs-lookup"><span data-stu-id="7d1c1-153">Demonstrates how to perform end-to-end streaming of LOB data using the UpdateLOB and table Select operations</span></span>|  
|<span data-ttu-id="7d1c1-154">OracleTransactedDmlCM</span><span class="sxs-lookup"><span data-stu-id="7d1c1-154">OracleTransactedDmlCM</span></span>|<span data-ttu-id="7d1c1-155">WCF チャネル モデルを使用して、トランザクションで Oracle データベースで操作を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7d1c1-155">Demonstrates how to perform operations on the Oracle database in a transaction using the WCF channel model.</span></span>|  
  

## <a name="see-also"></a><span data-ttu-id="7d1c1-156">参照</span><span class="sxs-lookup"><span data-stu-id="7d1c1-156">See Also</span></span>  
[<span data-ttu-id="7d1c1-157">Oracle データベース アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="7d1c1-157">Develop your Oracle Database applications</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)