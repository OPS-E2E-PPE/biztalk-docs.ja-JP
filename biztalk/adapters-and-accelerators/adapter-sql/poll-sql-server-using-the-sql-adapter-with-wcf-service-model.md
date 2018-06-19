---
title: WCF サービス モデルで、SQL アダプターを使用してポーリング SQL Server |Microsoft ドキュメント
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
ms.openlocfilehash: 20d0ab576e5feddb0b5f3e867ca549a45bb2af97
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222914"
---
# <a name="poll-sql-server-using-the-sql-adapter-with-wcf-service-model"></a><span data-ttu-id="2840c-102">WCF サービス モデルで、SQL アダプターを使用して SQL サーバーにポーリング</span><span class="sxs-lookup"><span data-stu-id="2840c-102">Poll SQL Server using the SQL Adapter with WCF Service Model</span></span>
<span data-ttu-id="2840c-103">構成することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を SQL Server からデータ変更のポーリングに基づいたメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="2840c-103">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive polling-based data-changed messages from SQL Server.</span></span> <span data-ttu-id="2840c-104">データベースをポーリングするアダプターを実行するポーリング ステートメントを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="2840c-104">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="2840c-105">ポーリング ステートメントには、SELECT ステートメントまたは結果セットを返すストアド プロシージャを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2840c-105">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span> <span data-ttu-id="2840c-106">ポーリングのメッセージの種類に基づいて、アダプターは、さまざまなポーリング操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="2840c-106">Based on the type of polling message received, the adapter exposes different polling operations:</span></span>  
  
-   <span data-ttu-id="2840c-107">**ポーリング**です。</span><span class="sxs-lookup"><span data-stu-id="2840c-107">**Polling**.</span></span> <span data-ttu-id="2840c-108">この操作は、ポーリング メッセージの一部としてデータ セットを返します。</span><span class="sxs-lookup"><span data-stu-id="2840c-108">This operation returns a data set as part of the polling message.</span></span>  
  
-   <span data-ttu-id="2840c-109">**TypedPolling**です。</span><span class="sxs-lookup"><span data-stu-id="2840c-109">**TypedPolling**.</span></span> <span data-ttu-id="2840c-110">この操作は、厳密に型指定されたポーリング メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="2840c-110">This operation returns a strongly-typed polling message.</span></span>  
  
-   <span data-ttu-id="2840c-111">**XmlPolling**です。</span><span class="sxs-lookup"><span data-stu-id="2840c-111">**XmlPolling**.</span></span> <span data-ttu-id="2840c-112">この操作は、XML メッセージとしてポーリング メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="2840c-112">This operation returns the polling message as an XML message.</span></span> <span data-ttu-id="2840c-113">SELECT ステートメントや XML メッセージとしてデータを返す FOR XML 句を使用するストアド プロシージャを使用する場合は、この操作を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2840c-113">You must use this operation if you want to use SELECT statements or stored procedures that use the FOR XML clause to return data as XML messages.</span></span> <span data-ttu-id="2840c-114">[FOR XML 句](https://docs.microsoft.com/sql/relational-databases/xml/for-xml-sql-server)詳細な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2840c-114">[FOR XML clause](https://docs.microsoft.com/sql/relational-databases/xml/for-xml-sql-server) provides more info.</span></span> 
  
 <span data-ttu-id="2840c-115">これらのポーリング処理の詳細については、次を参照してください。 [SQL アダプタを使用して SQL Server でのポーリング](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="2840c-115">For more information about these polling operations, see [Polling in SQL Server using the SQL adapter](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2840c-116">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントには同じデータベースまたはテーブルの 1 つ以上のポーリングや TypedPolling 操作を 1 つのアプリケーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2840c-116">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enables adapter clients to have a single application with more than one Polling or TypedPolling operations for the same database or table.</span></span> <span data-ttu-id="2840c-117">このようなシナリオをサポートするために、アダプターに一意の ID が含まれています — **InboundID**— 接続 URI にします。</span><span class="sxs-lookup"><span data-stu-id="2840c-117">To support such a scenario, the adapter includes a unique ID— **InboundID**—in the connection URI.</span></span> <span data-ttu-id="2840c-118">接続 URI に追加すると、この ID には一意になります、1 つのアプリケーションで複数のポーリング操作できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2840c-118">This ID, when added to the connection URI, makes it unique, thereby enabling multiple polling operations in a single application.</span></span>  
  
 <span data-ttu-id="2840c-119">このセクションのトピックでは、.NET アプリケーションでのポーリングと TypedPolling 操作の両方を使用する方法の手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="2840c-119">The topics in this section provide instructions on how to use both Polling and TypedPolling operations in a .NET application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2840c-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2840c-120">In This Section</span></span>  
  
-   [<span data-ttu-id="2840c-121">WCF サービス モデルを使用して SQL Server からのデータ変更のポーリングに基づいたメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="2840c-121">Receive Polling-based Data-changed Messages from SQL Server Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-service.md)  
  
-   [<span data-ttu-id="2840c-122">厳密に型指定されたポーリング ベース データが変更されてから受信 WCF サービスのモデルを使用して SQL Server</span><span class="sxs-lookup"><span data-stu-id="2840c-122">Receive Strongly-typed Polling-based Data-changed Messages from SQL Server Using WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md)  
  
## <a name="see-also"></a><span data-ttu-id="2840c-123">参照</span><span class="sxs-lookup"><span data-stu-id="2840c-123">See Also</span></span>  
[<span data-ttu-id="2840c-124">WCF サービス モデルを使用して SQL アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="2840c-124">Develop SQL applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)