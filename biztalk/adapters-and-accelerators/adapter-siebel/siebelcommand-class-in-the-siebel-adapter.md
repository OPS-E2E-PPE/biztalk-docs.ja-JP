---
title: Siebel アダプターの SiebelCommand クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SiebelCommand
- Data Provider for Siebel, SiebelCommand
- SiebelCommand, supported methods and properties
ms.assetid: 7cba0e47-634b-4878-b480-80fbcbbf5c90
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e35ecc56dd95fdd413827bc7744c1a02745eaa87
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370579"
---
# <a name="siebelcommand-class-in-the-siebel-adapter"></a><span data-ttu-id="03569-102">Siebel アダプターの SiebelCommand クラス</span><span class="sxs-lookup"><span data-stu-id="03569-102">SiebelCommand class in the Siebel adapter</span></span>
<span data-ttu-id="03569-103">Siebel システムへの接続を確立した後、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]コマンド文字列が Siebel と ADO.NET クライアントによって提供されるコマンドのパラメーターを解析し、コマンドを WCF 要求メッセージにマップします。</span><span class="sxs-lookup"><span data-stu-id="03569-103">After establishing a connection with the Siebel system, the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] parses the Siebel command strings and command parameters provided by the ADO.NET client and maps the command into a WCF request message.</span></span> <span data-ttu-id="03569-104">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]する要求を送信し、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]から XML 応答を取得し、アダプターから本文の内容。</span><span class="sxs-lookup"><span data-stu-id="03569-104">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] then sends the request to the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] and obtains the response XML and the body contents from the adapter.</span></span> <span data-ttu-id="03569-105">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を使用して、 `XMLDataReader` XML 本文からリレーショナル データを取得します。</span><span class="sxs-lookup"><span data-stu-id="03569-105">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] then uses the `XMLDataReader` to retrieve the relational data from the XML body.</span></span>  
  
 <span data-ttu-id="03569-106">インスタンスを使用して`Microsoft.Data.SiebelClient.SiebelClientFactory`、クライアント プログラムがのインスタンスを取得、 `System.Data.Common.DbCommand` Siebel コマンドを作成するクラス。</span><span class="sxs-lookup"><span data-stu-id="03569-106">Using an instance of `Microsoft.Data.SiebelClient.SiebelClientFactory`, a client program can obtain an instance of the `System.Data.Common.DbCommand` class to construct a Siebel command.</span></span>  
  
```  
//In this example, factory is an instance of SiebelClientFactory  
DbCommand command = factory.CreateCommand();  
```  
  
 <span data-ttu-id="03569-107">または、次のアプローチを使用して、コマンドを作成します。</span><span class="sxs-lookup"><span data-stu-id="03569-107">Alternatively, the following approach can be used to create a command:</span></span>  
  
```  
//Here connection is an instance of SiebelConnection  
SiebelCommand cmd = (SiebelCommand) connection.CreateCommand();  
cmd.CommandText = "SELECT [Name] as MyName, [City], [Country]  from Account.Account WHERE Name LIKE '3Com*' OPTION 'ViewMode 1'";  
```  
  
 <span data-ttu-id="03569-108">`SiebelCommand`クラスから継承`DbCommand`します。</span><span class="sxs-lookup"><span data-stu-id="03569-108">The `SiebelCommand` class inherits from `DbCommand`.</span></span>  <span data-ttu-id="03569-109">名前空間内に存在する`Microsoft.Data.SiebelClient`します。</span><span class="sxs-lookup"><span data-stu-id="03569-109">It exists in the namespace `Microsoft.Data.SiebelClient`.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="03569-110">サポートされているプロパティ</span><span class="sxs-lookup"><span data-stu-id="03569-110">Supported Properties</span></span>  
 <span data-ttu-id="03569-111">**SiebelCommand**クラスは、次をサポート`DbCommand`*保護*プロパティ。</span><span class="sxs-lookup"><span data-stu-id="03569-111">The **SiebelCommand** class supports the following `DbCommand`*protected* properties:</span></span>  
  
|<span data-ttu-id="03569-112">名前</span><span class="sxs-lookup"><span data-stu-id="03569-112">Name</span></span>|<span data-ttu-id="03569-113">Get/Set</span><span class="sxs-lookup"><span data-stu-id="03569-113">Get/Set</span></span>|<span data-ttu-id="03569-114">説明</span><span class="sxs-lookup"><span data-stu-id="03569-114">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="03569-115">**DbConnection**</span><span class="sxs-lookup"><span data-stu-id="03569-115">**DbConnection**</span></span>|<span data-ttu-id="03569-116">Get と Set</span><span class="sxs-lookup"><span data-stu-id="03569-116">Get and Set</span></span>|<span data-ttu-id="03569-117">これは、基になるを含める必要があります`DbConnection`元であるインスタンス`DbCommand`インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="03569-117">This should contain the underlying `DbConnection` instance from which this `DbCommand` instance is obtained.</span></span>|  
|<span data-ttu-id="03569-118">**DbParameterCollection**</span><span class="sxs-lookup"><span data-stu-id="03569-118">**DbParameterCollection**</span></span>|<span data-ttu-id="03569-119">取得</span><span class="sxs-lookup"><span data-stu-id="03569-119">Get</span></span>|<span data-ttu-id="03569-120">コレクションを取得`DbParameter`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="03569-120">Gets the collection of `DbParameter` objects.</span></span>|  
  
 <span data-ttu-id="03569-121">`SiebelCommand` 次のサポートも`DbCommand`*パブリック*プロパティ。</span><span class="sxs-lookup"><span data-stu-id="03569-121">`SiebelCommand` also supports the following `DbCommand`*public* properties:</span></span>  
  
|<span data-ttu-id="03569-122">名前</span><span class="sxs-lookup"><span data-stu-id="03569-122">Name</span></span>|<span data-ttu-id="03569-123">Get/Set</span><span class="sxs-lookup"><span data-stu-id="03569-123">Get/Set</span></span>|<span data-ttu-id="03569-124">説明</span><span class="sxs-lookup"><span data-stu-id="03569-124">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="03569-125">**CommandText**</span><span class="sxs-lookup"><span data-stu-id="03569-125">**CommandText**</span></span>|<span data-ttu-id="03569-126">Get と Set</span><span class="sxs-lookup"><span data-stu-id="03569-126">Get and Set</span></span>|<span data-ttu-id="03569-127">これには、ADO.NET クライアントを実行することを希望する SQL ステートメントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="03569-127">This contain the SQL statement that the ADO.NET client wishes to execute.</span></span>|  
|<span data-ttu-id="03569-128">**CommandType**</span><span class="sxs-lookup"><span data-stu-id="03569-128">**CommandType**</span></span>|<span data-ttu-id="03569-129">Get と Set</span><span class="sxs-lookup"><span data-stu-id="03569-129">Get and Set</span></span>|<span data-ttu-id="03569-130">サポートされるのは `CommandType.Text` のみです。</span><span class="sxs-lookup"><span data-stu-id="03569-130">Only `CommandType.Text` is supported.</span></span>|  
|<span data-ttu-id="03569-131">**Connection**</span><span class="sxs-lookup"><span data-stu-id="03569-131">**Connection**</span></span>|<span data-ttu-id="03569-132">Get と Set</span><span class="sxs-lookup"><span data-stu-id="03569-132">Get and Set</span></span>|<span data-ttu-id="03569-133">これを使用して、`DbConnection`メンバー。</span><span class="sxs-lookup"><span data-stu-id="03569-133">This uses the `DbConnection` member.</span></span>|  
|<span data-ttu-id="03569-134">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="03569-134">**Parameters**</span></span>|<span data-ttu-id="03569-135">取得</span><span class="sxs-lookup"><span data-stu-id="03569-135">Get</span></span>|<span data-ttu-id="03569-136">これを使用して、`DbParameterCollection`メンバー。</span><span class="sxs-lookup"><span data-stu-id="03569-136">This uses the `DbParameterCollection` member.</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="03569-137">`SiebelCommand`クラスは無視されます、 `CommandTimeout`、 `DesignTimeVisible`、および`DbTransaction`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="03569-137">The `SiebelCommand` class ignores the `CommandTimeout`, `DesignTimeVisible`, and `DbTransaction` properties.</span></span>  
  
## <a name="supported-methods"></a><span data-ttu-id="03569-138">サポートされているメソッド</span><span class="sxs-lookup"><span data-stu-id="03569-138">Supported Methods</span></span>  
 <span data-ttu-id="03569-139">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]は、次をサポート`DbCommand`*保護*メソッド。</span><span class="sxs-lookup"><span data-stu-id="03569-139">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports the following `DbCommand`*protected* methods:</span></span>  
  
|<span data-ttu-id="03569-140">名前</span><span class="sxs-lookup"><span data-stu-id="03569-140">Name</span></span>|<span data-ttu-id="03569-141">説明</span><span class="sxs-lookup"><span data-stu-id="03569-141">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="03569-142">**CreateDbParameter**</span><span class="sxs-lookup"><span data-stu-id="03569-142">**CreateDbParameter**</span></span>|<span data-ttu-id="03569-143">新たに作成`DbParameter`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="03569-143">Creates a new `DbParameter` instance.</span></span>|  
|<span data-ttu-id="03569-144">**ExecuteDbDataReader**</span><span class="sxs-lookup"><span data-stu-id="03569-144">**ExecuteDbDataReader**</span></span>|<span data-ttu-id="03569-145">を選択し、EXEC コマンドを実行し、返しますこれを`DbDataReader`します。</span><span class="sxs-lookup"><span data-stu-id="03569-145">This executes the SELECT and EXEC commands and returns a `DbDataReader`.</span></span>|  
  
 <span data-ttu-id="03569-146">`SiebelCommand` 次のサポートも`DbCommand`*パブリック*メソッド。</span><span class="sxs-lookup"><span data-stu-id="03569-146">`SiebelCommand` also supports the following `DbCommand`*public* methods:</span></span>  
  
|<span data-ttu-id="03569-147">名前</span><span class="sxs-lookup"><span data-stu-id="03569-147">Name</span></span>|<span data-ttu-id="03569-148">説明</span><span class="sxs-lookup"><span data-stu-id="03569-148">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="03569-149">**CreateParameter**</span><span class="sxs-lookup"><span data-stu-id="03569-149">**CreateParameter**</span></span>|<span data-ttu-id="03569-150">新たに作成`DbParameter`を通じてインスタンス `CreateDbParameter().`</span><span class="sxs-lookup"><span data-stu-id="03569-150">Creates a new `DbParameter` instance through `CreateDbParameter().`</span></span>|  
|<span data-ttu-id="03569-151">**ExecuteReader**</span><span class="sxs-lookup"><span data-stu-id="03569-151">**ExecuteReader**</span></span>|<span data-ttu-id="03569-152">実行`CommandText`に対して、`Connection`返します`DbDataReader`を通じて`ExecuteDbDataReader()`。</span><span class="sxs-lookup"><span data-stu-id="03569-152">Executes `CommandText` against the `Connection` and returns `DbDataReader` through `ExecuteDbDataReader()`.</span></span>|  
|<span data-ttu-id="03569-153">**準備します。**</span><span class="sxs-lookup"><span data-stu-id="03569-153">**Prepare**</span></span>|<span data-ttu-id="03569-154">これを解析し、`CommandText`し SQL コマンドの解析ツリーをビルドします。</span><span class="sxs-lookup"><span data-stu-id="03569-154">This parses the `CommandText` and builds the SQL command parse tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="03569-155">参照</span><span class="sxs-lookup"><span data-stu-id="03569-155">See Also</span></span>  
 [<span data-ttu-id="03569-156">Siebel アダプターを使用した ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="03569-156">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)