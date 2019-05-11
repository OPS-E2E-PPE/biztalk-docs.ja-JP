---
title: Siebel アダプターの SiebelConnection クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, SiebelConnection
- SiebelConnection, supported properties and methods
- SiebelConnection
ms.assetid: 661d9876-4c14-4748-b05f-cc4fd1c4ebcf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c61af5ce33a4d1a2fe092a0974daa522d4ef3176
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370604"
---
# <a name="siebelconnection-class-in-the-siebel-adapter"></a><span data-ttu-id="dfde5-102">Siebel アダプターの SiebelConnection クラス</span><span class="sxs-lookup"><span data-stu-id="dfde5-102">SiebelConnection class in the Siebel adapter</span></span>
<span data-ttu-id="dfde5-103">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] 、基になるにアクセスする[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] `Binding`、`ConnectionFactory`と`Channel`Siebel システムに接続します。</span><span class="sxs-lookup"><span data-stu-id="dfde5-103">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] accesses the underlying [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]`Binding`, the `ConnectionFactory`, and `Channel` to connect to the Siebel system.</span></span> <span data-ttu-id="dfde5-104">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]実装、`DbConnection`クラスには、上記をサポートするためにします。</span><span class="sxs-lookup"><span data-stu-id="dfde5-104">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] implements the `DbConnection` class to support the preceding features.</span></span>  

 <span data-ttu-id="dfde5-105">インスタンスを使用して`Microsoft.Data.SiebelClient.SiebelClientFactory`、クライアント プログラムがのインスタンスを取得、 `System.Data.Common.DbConnection` Siebel システムに接続するクラス。</span><span class="sxs-lookup"><span data-stu-id="dfde5-105">Using an instance of `Microsoft.Data.SiebelClient.SiebelClientFactory`, a client program can obtain an instance of the `System.Data.Common.DbConnection` class to connect to the Siebel system.</span></span>  

```  
//In this example, factory is an instance of SiebelClientFactory  
DbConnection connection = factory.CreateConnection();  
```  

 <span data-ttu-id="dfde5-106">または、次のアプローチを使用して、接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="dfde5-106">Alternatively, the following approach can be used to create a connection:</span></span>  

```  

SiebelConnection connection = new SiebelConnection();  
connection.ConnectionString = connectionString;  
```  

 <span data-ttu-id="dfde5-107">`SiebelConnection`クラスから継承`DbConnection`します。</span><span class="sxs-lookup"><span data-stu-id="dfde5-107">The `SiebelConnection` class inherits from `DbConnection`.</span></span> <span data-ttu-id="dfde5-108">名前空間内に存在する`Microsoft.Data.SiebelClient`します。</span><span class="sxs-lookup"><span data-stu-id="dfde5-108">It exists in the namespace `Microsoft.Data.SiebelClient`.</span></span>  

## <a name="supported-properties"></a><span data-ttu-id="dfde5-109">サポートされているプロパティ</span><span class="sxs-lookup"><span data-stu-id="dfde5-109">Supported Properties</span></span>  
 <span data-ttu-id="dfde5-110">`SiebelConnection`クラスは、次をサポート`DbConnection`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="dfde5-110">The `SiebelConnection` class supports the following `DbConnection` properties.</span></span>  


|         <span data-ttu-id="dfde5-111">名前</span><span class="sxs-lookup"><span data-stu-id="dfde5-111">Name</span></span>         |   <span data-ttu-id="dfde5-112">Get/Set</span><span class="sxs-lookup"><span data-stu-id="dfde5-112">Get/Set</span></span>   |                                                                                                      <span data-ttu-id="dfde5-113">説明</span><span class="sxs-lookup"><span data-stu-id="dfde5-113">Description</span></span>                                                                                                       |
|----------------------|-------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="dfde5-114">**ConnectionString**</span><span class="sxs-lookup"><span data-stu-id="dfde5-114">**ConnectionString**</span></span> | <span data-ttu-id="dfde5-115">Get と Set</span><span class="sxs-lookup"><span data-stu-id="dfde5-115">Get and Set</span></span> |                                                                                  <span data-ttu-id="dfde5-116">取得または設定、接続を開くために使用する文字列。</span><span class="sxs-lookup"><span data-stu-id="dfde5-116">Gets or sets the string used to open the connection.</span></span>                                                                                  |
|     <span data-ttu-id="dfde5-117">**[データベース]**</span><span class="sxs-lookup"><span data-stu-id="dfde5-117">**Database**</span></span>     |     <span data-ttu-id="dfde5-118">取得</span><span class="sxs-lookup"><span data-stu-id="dfde5-118">Get</span></span>     |        <span data-ttu-id="dfde5-119">接続が開かれる前に、接続文字列で指定されたデータベース名または接続が開かれた後に、現在のデータベースの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="dfde5-119">Gets the name of the current database after a connection is opened, or the database name specified in the connection string before the connection is opened.</span></span> <span data-ttu-id="dfde5-120">Siebel リポジトリ名があります。</span><span class="sxs-lookup"><span data-stu-id="dfde5-120">This should be the Siebel repository name.</span></span>         |
|    <span data-ttu-id="dfde5-121">**DataSource**</span><span class="sxs-lookup"><span data-stu-id="dfde5-121">**DataSource**</span></span>    |     <span data-ttu-id="dfde5-122">取得</span><span class="sxs-lookup"><span data-stu-id="dfde5-122">Get</span></span>     |                                                                                <span data-ttu-id="dfde5-123">この接続の Siebel ゲートウェイの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="dfde5-123">Gets the name of the Siebel gateway for this connection.</span></span>                                                                                |
|  <span data-ttu-id="dfde5-124">**ServerVersion**</span><span class="sxs-lookup"><span data-stu-id="dfde5-124">**ServerVersion**</span></span>   |     <span data-ttu-id="dfde5-125">取得</span><span class="sxs-lookup"><span data-stu-id="dfde5-125">Get</span></span>     | <span data-ttu-id="dfde5-126">現在のバージョンで[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]、Siebel サーバーの実際のバージョンを表していないハード コーディングされた値を返します。</span><span class="sxs-lookup"><span data-stu-id="dfde5-126">In the current version of [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], this property returns a hard-coded value, which does not represent the actual version of the Siebel server.</span></span> |
|      <span data-ttu-id="dfde5-127">**State**</span><span class="sxs-lookup"><span data-stu-id="dfde5-127">**State**</span></span>       |     <span data-ttu-id="dfde5-128">取得</span><span class="sxs-lookup"><span data-stu-id="dfde5-128">Get</span></span>     |                                               <span data-ttu-id="dfde5-129">接続の状態を説明する文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="dfde5-129">Gets a string that describes the state of the connection.</span></span> <span data-ttu-id="dfde5-130">これは、3 つの値を含めることができます。開く、BROKEN、または終了します。</span><span class="sxs-lookup"><span data-stu-id="dfde5-130">This can contain three possible values: OPEN, BROKEN, or CLOSED.</span></span>                                               |

## <a name="supported-methods"></a><span data-ttu-id="dfde5-131">サポートされているメソッド</span><span class="sxs-lookup"><span data-stu-id="dfde5-131">Supported Methods</span></span>  
 <span data-ttu-id="dfde5-132">`SiebelConnection`クラスは、次をサポート`DbConnection`メソッド。</span><span class="sxs-lookup"><span data-stu-id="dfde5-132">The `SiebelConnection` class supports the following `DbConnection` methods.</span></span>  

|<span data-ttu-id="dfde5-133">名前</span><span class="sxs-lookup"><span data-stu-id="dfde5-133">Name</span></span>|<span data-ttu-id="dfde5-134">説明</span><span class="sxs-lookup"><span data-stu-id="dfde5-134">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="dfde5-135">**CreateDbCommand**</span><span class="sxs-lookup"><span data-stu-id="dfde5-135">**CreateDbCommand**</span></span>|<span data-ttu-id="dfde5-136">この保護されているメソッドは、DbCommand の新しいインスタンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="dfde5-136">This protected method provides a new DbCommand instance.</span></span>|  
|<span data-ttu-id="dfde5-137">**ChangeDatabase**</span><span class="sxs-lookup"><span data-stu-id="dfde5-137">**ChangeDatabase**</span></span>|<span data-ttu-id="dfde5-138">このパブリック メソッドは、サポートされていませんし、呼び出された場合、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="dfde5-138">This public method is not supported, and will throw an exception if called.</span></span>|  
|<span data-ttu-id="dfde5-139">**[ファイル]**</span><span class="sxs-lookup"><span data-stu-id="dfde5-139">**Open**</span></span>|<span data-ttu-id="dfde5-140">WCF チャネルを作成して、Siebel システムとの接続を開きます。</span><span class="sxs-lookup"><span data-stu-id="dfde5-140">Opens a connection with the Siebel system by creating a WCF channel.</span></span>|  
|<span data-ttu-id="dfde5-141">**Close**</span><span class="sxs-lookup"><span data-stu-id="dfde5-141">**Close**</span></span>|<span data-ttu-id="dfde5-142">WCF チャネルを閉じることで Siebel システムへの接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="dfde5-142">Closes a connection with the Siebel system by closing a WCF channel.</span></span>|  
|<span data-ttu-id="dfde5-143">**CreateCommand**</span><span class="sxs-lookup"><span data-stu-id="dfde5-143">**CreateCommand**</span></span>|<span data-ttu-id="dfde5-144">コマンド オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfde5-144">Creates a command object.</span></span>|  

## <a name="see-also"></a><span data-ttu-id="dfde5-145">参照</span><span class="sxs-lookup"><span data-stu-id="dfde5-145">See Also</span></span>  
 [<span data-ttu-id="dfde5-146">Siebel アダプターを使用した ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="dfde5-146">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)