---
title: WCF サービス モデルで、SQL アダプターを使用して SQL Server をポーリング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eef2e868-bd51-4393-b091-f67299b4759d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb3bbd42c732f3377c5823831b9507bbeb0c83bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022312"
---
# <a name="poll-sql-server-using-the-sql-adapter-with-wcf-service-model"></a><span data-ttu-id="b3d36-102">SQL Server をポーリングする WCF サービス モデルでの SQL アダプタの使用</span><span class="sxs-lookup"><span data-stu-id="b3d36-102">Poll SQL Server using the SQL Adapter with WCF Service Model</span></span>
<span data-ttu-id="b3d36-103">構成することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を SQL Server からのポーリングに基づいたデータ変更メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="b3d36-103">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive polling-based data-changed messages from SQL Server.</span></span> <span data-ttu-id="b3d36-104">データベースをポーリングするアダプターを実行するポーリング ステートメントを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="b3d36-104">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="b3d36-105">ポーリング ステートメントには、SELECT ステートメントまたはストアド プロシージャを返す結果セットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3d36-105">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span> <span data-ttu-id="b3d36-106">受信したメッセージのポーリングの種類に基づいて、アダプターは、さまざまなポーリング操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="b3d36-106">Based on the type of polling message received, the adapter exposes different polling operations:</span></span>  
  
- <span data-ttu-id="b3d36-107">**ポーリング**します。</span><span class="sxs-lookup"><span data-stu-id="b3d36-107">**Polling**.</span></span> <span data-ttu-id="b3d36-108">この操作は、ポーリング メッセージの一部としてデータ セットを返します。</span><span class="sxs-lookup"><span data-stu-id="b3d36-108">This operation returns a data set as part of the polling message.</span></span>  
  
- <span data-ttu-id="b3d36-109">**TypedPolling**します。</span><span class="sxs-lookup"><span data-stu-id="b3d36-109">**TypedPolling**.</span></span> <span data-ttu-id="b3d36-110">この操作は、厳密に型指定されたポーリング メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="b3d36-110">This operation returns a strongly-typed polling message.</span></span>  
  
- <span data-ttu-id="b3d36-111">**XmlPolling**します。</span><span class="sxs-lookup"><span data-stu-id="b3d36-111">**XmlPolling**.</span></span> <span data-ttu-id="b3d36-112">この操作は、XML メッセージとしてポーリング メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="b3d36-112">This operation returns the polling message as an XML message.</span></span> <span data-ttu-id="b3d36-113">SELECT ステートメントまたは XML メッセージとしてデータを返す FOR XML 句を使用するストアド プロシージャを使用する場合、この操作を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3d36-113">You must use this operation if you want to use SELECT statements or stored procedures that use the FOR XML clause to return data as XML messages.</span></span> <span data-ttu-id="b3d36-114">[FOR XML 句](https://docs.microsoft.com/sql/relational-databases/xml/for-xml-sql-server)詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b3d36-114">[FOR XML clause](https://docs.microsoft.com/sql/relational-databases/xml/for-xml-sql-server) provides more info.</span></span> 
  
  <span data-ttu-id="b3d36-115">これらのポーリング操作の詳細については、次を参照してください。 [SQL アダプターを使用して SQL Server でのポーリング](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="b3d36-115">For more information about these polling operations, see [Polling in SQL Server using the SQL adapter](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3d36-116">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントは同じデータベースまたはテーブルの 1 つ以上のポーリングまたは TypedPolling 操作を 1 つのアプリケーションに使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3d36-116">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enables adapter clients to have a single application with more than one Polling or TypedPolling operations for the same database or table.</span></span> <span data-ttu-id="b3d36-117">アダプターには、このようなシナリオをサポートするには、一意の ID が含まれています — **InboundID**— 接続 URI。</span><span class="sxs-lookup"><span data-stu-id="b3d36-117">To support such a scenario, the adapter includes a unique ID— **InboundID**—in the connection URI.</span></span> <span data-ttu-id="b3d36-118">この ID は、接続、URI に追加されたときに、一意で単一のアプリケーションで複数のポーリング操作できるようにできます。</span><span class="sxs-lookup"><span data-stu-id="b3d36-118">This ID, when added to the connection URI, makes it unique, thereby enabling multiple polling operations in a single application.</span></span>  
  
 <span data-ttu-id="b3d36-119">このセクションのトピックでは、.NET アプリケーションでのポーリングと TypedPolling 操作を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3d36-119">The topics in this section provide instructions on how to use both Polling and TypedPolling operations in a .NET application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b3d36-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b3d36-120">In This Section</span></span>  
  
-   [<span data-ttu-id="b3d36-121">WCF サービス モデルを使用して SQL Server からのポーリングに基づいたデータ変更メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="b3d36-121">Receive Polling-based Data-changed Messages from SQL Server Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-service.md)  
  
-   [<span data-ttu-id="b3d36-122">WCF サービス モデルを使用して SQL Server からのポーリングに基づいたデータ変更メッセージを厳密に型指定の受信します。</span><span class="sxs-lookup"><span data-stu-id="b3d36-122">Receive Strongly-typed Polling-based Data-changed Messages from SQL Server Using WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md)  
  
## <a name="see-also"></a><span data-ttu-id="b3d36-123">参照</span><span class="sxs-lookup"><span data-stu-id="b3d36-123">See Also</span></span>  
[<span data-ttu-id="b3d36-124">WCF サービス モデルを使用して SQL アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="b3d36-124">Develop SQL applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)