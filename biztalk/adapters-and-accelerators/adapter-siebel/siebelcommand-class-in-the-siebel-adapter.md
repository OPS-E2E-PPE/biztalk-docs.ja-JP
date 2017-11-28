---
title: "Siebel アダプターの SiebelCommand クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SiebelCommand
- Data Provider for Siebel, SiebelCommand
- SiebelCommand, supported methods and properties
ms.assetid: 7cba0e47-634b-4878-b480-80fbcbbf5c90
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d268e9a1d5954d703d392070a53c84bd9cee0d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="siebelcommand-class-in-the-siebel-adapter"></a><span data-ttu-id="cb6d6-102">Siebel アダプターの SiebelCommand クラス</span><span class="sxs-lookup"><span data-stu-id="cb6d6-102">SiebelCommand class in the Siebel adapter</span></span>
<span data-ttu-id="cb6d6-103">Siebel システムへの接続を確立した後、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] ADO.NET クライアントによって提供されるコマンドのパラメーターと Siebel コマンド文字列を解析し、コマンドは、WCF 要求メッセージにマップします。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-103">After establishing a connection with the Siebel system, the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] parses the Siebel command strings and command parameters provided by the ADO.NET client and maps the command into a WCF request message.</span></span> <span data-ttu-id="cb6d6-104">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]への要求を送信、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]し、応答の XML を取得し、アダプターから本文の内容。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-104">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] then sends the request to the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] and obtains the response XML and the body contents from the adapter.</span></span> <span data-ttu-id="cb6d6-105">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を使用して、 `XMLDataReader` XML 本文からリレーショナル データを取得します。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-105">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] then uses the `XMLDataReader` to retrieve the relational data from the XML body.</span></span>  
  
 <span data-ttu-id="cb6d6-106">インスタンスを使用して`Microsoft.Data.SiebelClient.SiebelClientFactory`、クライアント プログラムがのインスタンスを取得できます、 `System.Data.Common.DbCommand` Siebel コマンドを構築するためにクラスです。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-106">Using an instance of `Microsoft.Data.SiebelClient.SiebelClientFactory`, a client program can obtain an instance of the `System.Data.Common.DbCommand` class to construct a Siebel command.</span></span>  
  
```  
//In this example, factory is an instance of SiebelClientFactory  
DbCommand command = factory.CreateCommand();  
```  
  
 <span data-ttu-id="cb6d6-107">または、コマンドを作成する、次の方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-107">Alternatively, the following approach can be used to create a command:</span></span>  
  
```  
//Here connection is an instance of SiebelConnection  
SiebelCommand cmd = (SiebelCommand) connection.CreateCommand();  
cmd.CommandText = "SELECT [Name] as MyName, [City], [Country]  from Account.Account WHERE Name LIKE '3Com*' OPTION 'ViewMode 1'";  
```  
  
 <span data-ttu-id="cb6d6-108">`SiebelCommand`クラスから継承`DbCommand`です。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-108">The `SiebelCommand` class inherits from `DbCommand`.</span></span>  <span data-ttu-id="cb6d6-109">名前空間内に存在する`Microsoft.Data.SiebelClient`です。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-109">It exists in the namespace `Microsoft.Data.SiebelClient`.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="cb6d6-110">サポートされているプロパティ</span><span class="sxs-lookup"><span data-stu-id="cb6d6-110">Supported Properties</span></span>  
 <span data-ttu-id="cb6d6-111">**SiebelCommand**クラスは、次をサポート`DbCommand`*保護*プロパティ。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-111">The **SiebelCommand** class supports the following `DbCommand`*protected* properties:</span></span>  
  
|<span data-ttu-id="cb6d6-112">名前</span><span class="sxs-lookup"><span data-stu-id="cb6d6-112">Name</span></span>|<span data-ttu-id="cb6d6-113">取得/設定</span><span class="sxs-lookup"><span data-stu-id="cb6d6-113">Get/Set</span></span>|<span data-ttu-id="cb6d6-114">Description</span><span class="sxs-lookup"><span data-stu-id="cb6d6-114">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="cb6d6-115">**DbConnection**</span><span class="sxs-lookup"><span data-stu-id="cb6d6-115">**DbConnection**</span></span>|<span data-ttu-id="cb6d6-116">Get および Set</span><span class="sxs-lookup"><span data-stu-id="cb6d6-116">Get and Set</span></span>|<span data-ttu-id="cb6d6-117">基になるこれを含める必要があります`DbConnection`インスタンスからこの`DbCommand`のインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-117">This should contain the underlying `DbConnection` instance from which this `DbCommand` instance is obtained.</span></span>|  
|<span data-ttu-id="cb6d6-118">**DbParameterCollection**</span><span class="sxs-lookup"><span data-stu-id="cb6d6-118">**DbParameterCollection**</span></span>|<span data-ttu-id="cb6d6-119">取得</span><span class="sxs-lookup"><span data-stu-id="cb6d6-119">Get</span></span>|<span data-ttu-id="cb6d6-120">コレクションを取得`DbParameter`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-120">Gets the collection of `DbParameter` objects.</span></span>|  
  
 <span data-ttu-id="cb6d6-121">`SiebelCommand`次のサポートも`DbCommand`*パブリック*プロパティ。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-121">`SiebelCommand` also supports the following `DbCommand`*public* properties:</span></span>  
  
|<span data-ttu-id="cb6d6-122">名前</span><span class="sxs-lookup"><span data-stu-id="cb6d6-122">Name</span></span>|<span data-ttu-id="cb6d6-123">取得/設定</span><span class="sxs-lookup"><span data-stu-id="cb6d6-123">Get/Set</span></span>|<span data-ttu-id="cb6d6-124">Description</span><span class="sxs-lookup"><span data-stu-id="cb6d6-124">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="cb6d6-125">**CommandText**</span><span class="sxs-lookup"><span data-stu-id="cb6d6-125">**CommandText**</span></span>|<span data-ttu-id="cb6d6-126">Get および Set</span><span class="sxs-lookup"><span data-stu-id="cb6d6-126">Get and Set</span></span>|<span data-ttu-id="cb6d6-127">これには、ADO.NET クライアントを実行することを希望する SQL ステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-127">This contain the SQL statement that the ADO.NET client wishes to execute.</span></span>|  
|<span data-ttu-id="cb6d6-128">**CommandType**</span><span class="sxs-lookup"><span data-stu-id="cb6d6-128">**CommandType**</span></span>|<span data-ttu-id="cb6d6-129">Get および Set</span><span class="sxs-lookup"><span data-stu-id="cb6d6-129">Get and Set</span></span>|<span data-ttu-id="cb6d6-130">サポートされるのは `CommandType.Text` のみです。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-130">Only `CommandType.Text` is supported.</span></span>|  
|<span data-ttu-id="cb6d6-131">**接続**</span><span class="sxs-lookup"><span data-stu-id="cb6d6-131">**Connection**</span></span>|<span data-ttu-id="cb6d6-132">Get および Set</span><span class="sxs-lookup"><span data-stu-id="cb6d6-132">Get and Set</span></span>|<span data-ttu-id="cb6d6-133">これは、使用、`DbConnection`メンバー。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-133">This uses the `DbConnection` member.</span></span>|  
|<span data-ttu-id="cb6d6-134">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="cb6d6-134">**Parameters**</span></span>|<span data-ttu-id="cb6d6-135">取得</span><span class="sxs-lookup"><span data-stu-id="cb6d6-135">Get</span></span>|<span data-ttu-id="cb6d6-136">これは、使用、`DbParameterCollection`メンバー。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-136">This uses the `DbParameterCollection` member.</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="cb6d6-137">`SiebelCommand`クラスは無視されます、 `CommandTimeout`、 `DesignTimeVisible`、および`DbTransaction`プロパティです。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-137">The `SiebelCommand` class ignores the `CommandTimeout`, `DesignTimeVisible`, and `DbTransaction` properties.</span></span>  
  
## <a name="supported-methods"></a><span data-ttu-id="cb6d6-138">サポートされているメソッド</span><span class="sxs-lookup"><span data-stu-id="cb6d6-138">Supported Methods</span></span>  
 <span data-ttu-id="cb6d6-139">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]次のサポート`DbCommand`*保護*メソッド。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-139">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports the following `DbCommand`*protected* methods:</span></span>  
  
|<span data-ttu-id="cb6d6-140">名前</span><span class="sxs-lookup"><span data-stu-id="cb6d6-140">Name</span></span>|<span data-ttu-id="cb6d6-141">Description</span><span class="sxs-lookup"><span data-stu-id="cb6d6-141">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="cb6d6-142">**CreateDbParameter**</span><span class="sxs-lookup"><span data-stu-id="cb6d6-142">**CreateDbParameter**</span></span>|<span data-ttu-id="cb6d6-143">新たに作成`DbParameter`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-143">Creates a new `DbParameter` instance.</span></span>|  
|<span data-ttu-id="cb6d6-144">**ExecuteDbDataReader**</span><span class="sxs-lookup"><span data-stu-id="cb6d6-144">**ExecuteDbDataReader**</span></span>|<span data-ttu-id="cb6d6-145">これを選択し、EXEC コマンドを実行しを返します、`DbDataReader`です。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-145">This executes the SELECT and EXEC commands and returns a `DbDataReader`.</span></span>|  
  
 <span data-ttu-id="cb6d6-146">`SiebelCommand`次のサポートも`DbCommand`*パブリック*メソッド。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-146">`SiebelCommand` also supports the following `DbCommand`*public* methods:</span></span>  
  
|<span data-ttu-id="cb6d6-147">名前</span><span class="sxs-lookup"><span data-stu-id="cb6d6-147">Name</span></span>|<span data-ttu-id="cb6d6-148">Description</span><span class="sxs-lookup"><span data-stu-id="cb6d6-148">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="cb6d6-149">**CreateParameter**</span><span class="sxs-lookup"><span data-stu-id="cb6d6-149">**CreateParameter**</span></span>|<span data-ttu-id="cb6d6-150">新たに作成`DbParameter`を通じてインスタンス`CreateDbParameter().`</span><span class="sxs-lookup"><span data-stu-id="cb6d6-150">Creates a new `DbParameter` instance through `CreateDbParameter().`</span></span>|  
|<span data-ttu-id="cb6d6-151">**ExecuteReader**</span><span class="sxs-lookup"><span data-stu-id="cb6d6-151">**ExecuteReader**</span></span>|<span data-ttu-id="cb6d6-152">実行`CommandText`に対して、`Connection`し、返します`DbDataReader`を通じて`ExecuteDbDataReader()`です。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-152">Executes `CommandText` against the `Connection` and returns `DbDataReader` through `ExecuteDbDataReader()`.</span></span>|  
|<span data-ttu-id="cb6d6-153">**準備します。**</span><span class="sxs-lookup"><span data-stu-id="cb6d6-153">**Prepare**</span></span>|<span data-ttu-id="cb6d6-154">これを解析し、`CommandText`し、SQL コマンドの解析ツリーを構築します。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-154">This parses the `CommandText` and builds the SQL command parse tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cb6d6-155">参照</span><span class="sxs-lookup"><span data-stu-id="cb6d6-155">See Also</span></span>  
 [<span data-ttu-id="cb6d6-156">Siebel アダプターと ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="cb6d6-156">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)