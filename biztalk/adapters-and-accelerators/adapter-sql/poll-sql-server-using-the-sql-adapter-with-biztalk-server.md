---
title: "BizTalk Server と SQL アダプタを使用してポーリング SQL Server |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eef9a4b4-552d-4552-b318-1deab506bad9
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31e631a966ffee632e6c866a962c4fe47b2f1025
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="poll-sql-server-using-the-sql-adapter-with-biztalk-server"></a><span data-ttu-id="dfec6-102">BizTalk Server と SQL アダプタを使用して SQL サーバーにポーリング</span><span class="sxs-lookup"><span data-stu-id="dfec6-102">Poll SQL Server using the SQL Adapter with BizTalk Server</span></span>
<span data-ttu-id="dfec6-103">構成することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を SQL Server からデータ変更のポーリングに基づいたメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="dfec6-103">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive polling-based data-changed messages from SQL Server.</span></span> <span data-ttu-id="dfec6-104">データベースをポーリングするアダプターを実行するポーリング ステートメントを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="dfec6-104">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="dfec6-105">ポーリング ステートメントには、SELECT ステートメントまたは結果セットを返すストアド プロシージャを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dfec6-105">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span> <span data-ttu-id="dfec6-106">ポーリングのメッセージの種類に基づいて、アダプターは、ポーリングの 3 つの方法を公開します。</span><span class="sxs-lookup"><span data-stu-id="dfec6-106">Based on the type of polling message received, the adapter exposes three different ways of polling:</span></span>  
  
-   <span data-ttu-id="dfec6-107">**ポーリング**です。</span><span class="sxs-lookup"><span data-stu-id="dfec6-107">**Polling**.</span></span> <span data-ttu-id="dfec6-108">この操作は、ポーリング メッセージの一部としてデータ セットを返します。</span><span class="sxs-lookup"><span data-stu-id="dfec6-108">This operation returns a data set as part of the polling message.</span></span> <span data-ttu-id="dfec6-109">デザイン時に、ポーリングされているデータベース オブジェクトのスキーマは使用できません。</span><span class="sxs-lookup"><span data-stu-id="dfec6-109">At design time, the schema of the database object being polled is not available.</span></span> <span data-ttu-id="dfec6-110">代わりに、スキーマは、実行時にポーリング メッセージの一部として。</span><span class="sxs-lookup"><span data-stu-id="dfec6-110">Instead, the schema is available as part of the polling message during run time.</span></span>  
  
-   <span data-ttu-id="dfec6-111">**TypedPolling**です。</span><span class="sxs-lookup"><span data-stu-id="dfec6-111">**TypedPolling**.</span></span> <span data-ttu-id="dfec6-112">この操作は、厳密に型指定されたポーリング メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="dfec6-112">This operation returns a strongly-typed polling message.</span></span> <span data-ttu-id="dfec6-113">デザイン時に、データベース オブジェクトのスキーマも使用できます。</span><span class="sxs-lookup"><span data-stu-id="dfec6-113">At design time, the schema of the database object is also available.</span></span> <span data-ttu-id="dfec6-114">ポーリング メッセージから別の操作の場合も、別のスキーマの特定の要素をマップする場合のポーリングを行うには、この操作を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfec6-114">You must use this operation for polling if you want to map certain elements from the polling message to another schema, which could be for another operation.</span></span>  
  
-   <span data-ttu-id="dfec6-115">**XmlPolling**です。</span><span class="sxs-lookup"><span data-stu-id="dfec6-115">**XmlPolling**.</span></span> <span data-ttu-id="dfec6-116">この操作は、XML メッセージとしてポーリング メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="dfec6-116">This operation returns the polling message as an XML message.</span></span> <span data-ttu-id="dfec6-117">SELECT ステートメントや XML メッセージとしてデータを返す FOR XML 句を使用するストアド プロシージャを使用する場合は、この操作を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfec6-117">You must use this operation if you want to use SELECT statements or stored procedures that use the FOR XML clause to return data as XML messages.</span></span> <span data-ttu-id="dfec6-118">FOR XML 句の詳細については、次を参照してください。 [FOR XML (SQL Server)](https://msdn.microsoft.com/library/ms178107.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="dfec6-118">For more information about the FOR XML clause, see [FOR XML (SQL Server)](https://msdn.microsoft.com/library/ms178107.aspx).</span></span> 
  
 <span data-ttu-id="dfec6-119">これらのポーリング処理の詳細については、次を参照してください。[ポーリングのサポート](https://msdn.microsoft.com/library/dd788416.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="dfec6-119">For more information about these polling operations, see [Support for Polling](https://msdn.microsoft.com/library/dd788416.aspx).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfec6-120">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントには同じデータベースまたはテーブルの 1 つ以上のポーリングや TypedPolling 操作を 1 つの BizTalk アプリケーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="dfec6-120">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enables adapter clients to have a single BizTalk application with more than one Polling or TypedPolling operations for the same database or table.</span></span> <span data-ttu-id="dfec6-121">このようなシナリオをサポートするために、アダプターに一意の ID が含まれています — **InboundID**— 接続 URI にします。</span><span class="sxs-lookup"><span data-stu-id="dfec6-121">To support such a scenario, the adapter includes a unique ID— **InboundID**—in the connection URI.</span></span> <span data-ttu-id="dfec6-122">接続 URI に追加すると、この ID には一意になります、1 つの BizTalk アプリケーションで複数のポーリング操作できるようにします。</span><span class="sxs-lookup"><span data-stu-id="dfec6-122">This ID, when added to the connection URI, makes it unique, thereby enabling multiple polling operations in a single BizTalk application.</span></span>  
  
 <span data-ttu-id="dfec6-123">このセクションのトピックでは、BizTalk アプリケーションでのポーリング、TypedPolling、および XmlPolling の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dfec6-123">The topics in this section provide instructions on how to use Polling, TypedPolling, and XmlPolling in a BizTalk application.</span></span> <span data-ttu-id="dfec6-124">使用する方法についても説明、 **InboundID**接続プロパティです。</span><span class="sxs-lookup"><span data-stu-id="dfec6-124">This section also provides information about how to use the **InboundID** connection property.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dfec6-125">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="dfec6-125">In This Section</span></span>  
  
-   [<span data-ttu-id="dfec6-126">SQL Server から BizTalk Server を使用して、データ変更のポーリングに基づいたメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="dfec6-126">Receive Polling-based Data-changed Messages from SQL Server by using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)  
  
-   [<span data-ttu-id="dfec6-127">厳密に型指定されたポーリング ベース データが変更されてから受信 BizTalk Server を使用して SQL Server</span><span class="sxs-lookup"><span data-stu-id="dfec6-127">Receive Strongly-typed Polling-based Data-changed Messages from SQL Server using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md)  
  
-   [<span data-ttu-id="dfec6-128">BizTalk Server を使用して SQL からポーリング メッセージを使用して SELECT ステートメントで FOR XML 句の受信します。</span><span class="sxs-lookup"><span data-stu-id="dfec6-128">Receive Polling Messages Using SELECT Statements with FOR XML Clause from SQL using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="dfec6-129">BizTalk Server を使用して SQL からの複数の受信ポートにメッセージ間でのポーリングの受信します。</span><span class="sxs-lookup"><span data-stu-id="dfec6-129">Receive Polling Messages Across Multiple Receive Ports from SQL using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)  
  
## <a name="see-also"></a><span data-ttu-id="dfec6-130">参照</span><span class="sxs-lookup"><span data-stu-id="dfec6-130">See Also</span></span>  
[<span data-ttu-id="dfec6-131">SQL アダプターを使用して BizTalk アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="dfec6-131">Develop BizTalk applications using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)