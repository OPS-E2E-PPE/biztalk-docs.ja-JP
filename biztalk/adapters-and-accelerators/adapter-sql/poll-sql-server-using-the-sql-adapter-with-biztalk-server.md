---
title: BizTalk Server と SQL アダプタを使用して SQL Server をポーリング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eef9a4b4-552d-4552-b318-1deab506bad9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 971de39bff2149b1b6bdb5d20d6e8b721821a8ea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996443"
---
# <a name="poll-sql-server-using-the-sql-adapter-with-biztalk-server"></a><span data-ttu-id="ac07d-102">BizTalk Server と SQL アダプタを使用して SQL Server をポーリング</span><span class="sxs-lookup"><span data-stu-id="ac07d-102">Poll SQL Server using the SQL Adapter with BizTalk Server</span></span>
<span data-ttu-id="ac07d-103">構成することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を SQL Server からのポーリングに基づいたデータ変更メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="ac07d-103">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive polling-based data-changed messages from SQL Server.</span></span> <span data-ttu-id="ac07d-104">データベースをポーリングするアダプターを実行するポーリング ステートメントを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="ac07d-104">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="ac07d-105">ポーリング ステートメントには、SELECT ステートメントまたはストアド プロシージャを返す結果セットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ac07d-105">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span> <span data-ttu-id="ac07d-106">受信したメッセージのポーリングの種類に基づいて、アダプターは、ポーリングの 3 つの方法を公開します。</span><span class="sxs-lookup"><span data-stu-id="ac07d-106">Based on the type of polling message received, the adapter exposes three different ways of polling:</span></span>  
  
- <span data-ttu-id="ac07d-107">**ポーリング**します。</span><span class="sxs-lookup"><span data-stu-id="ac07d-107">**Polling**.</span></span> <span data-ttu-id="ac07d-108">この操作は、ポーリング メッセージの一部としてデータ セットを返します。</span><span class="sxs-lookup"><span data-stu-id="ac07d-108">This operation returns a data set as part of the polling message.</span></span> <span data-ttu-id="ac07d-109">デザイン時に、ポーリングされているデータベース オブジェクトのスキーマは使用できません。</span><span class="sxs-lookup"><span data-stu-id="ac07d-109">At design time, the schema of the database object being polled is not available.</span></span> <span data-ttu-id="ac07d-110">代わりに、スキーマが使用可能な実行時のポーリング メッセージの一部として。</span><span class="sxs-lookup"><span data-stu-id="ac07d-110">Instead, the schema is available as part of the polling message during run time.</span></span>  
  
- <span data-ttu-id="ac07d-111">**TypedPolling**します。</span><span class="sxs-lookup"><span data-stu-id="ac07d-111">**TypedPolling**.</span></span> <span data-ttu-id="ac07d-112">この操作は、厳密に型指定されたポーリング メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="ac07d-112">This operation returns a strongly-typed polling message.</span></span> <span data-ttu-id="ac07d-113">デザイン時に、データベース オブジェクトのスキーマも使用できます。</span><span class="sxs-lookup"><span data-stu-id="ac07d-113">At design time, the schema of the database object is also available.</span></span> <span data-ttu-id="ac07d-114">別の操作である可能性がある別のスキーマにポーリング メッセージから特定の要素をマップする場合をポーリングするためには、この操作を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac07d-114">You must use this operation for polling if you want to map certain elements from the polling message to another schema, which could be for another operation.</span></span>  
  
- <span data-ttu-id="ac07d-115">**XmlPolling**します。</span><span class="sxs-lookup"><span data-stu-id="ac07d-115">**XmlPolling**.</span></span> <span data-ttu-id="ac07d-116">この操作は、XML メッセージとしてポーリング メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="ac07d-116">This operation returns the polling message as an XML message.</span></span> <span data-ttu-id="ac07d-117">SELECT ステートメントまたは XML メッセージとしてデータを返す FOR XML 句を使用するストアド プロシージャを使用する場合、この操作を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac07d-117">You must use this operation if you want to use SELECT statements or stored procedures that use the FOR XML clause to return data as XML messages.</span></span> <span data-ttu-id="ac07d-118">FOR XML 句の詳細については、[FOR XML (SQL Server)](https://msdn.microsoft.com/library/ms178107.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac07d-118">For more information about the FOR XML clause, see [FOR XML (SQL Server)](https://msdn.microsoft.com/library/ms178107.aspx).</span></span> 
  
  <span data-ttu-id="ac07d-119">これらのポーリング操作の詳細については、[のポーリング サポート](https://msdn.microsoft.com/library/dd788416.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac07d-119">For more information about these polling operations, see [Support for Polling](https://msdn.microsoft.com/library/dd788416.aspx).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac07d-120">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]によりアダプターでクライアントに、同じデータベースまたはテーブルの 1 つ以上のポーリングや TypedPolling 操作を 1 つの BizTalk アプリケーションがあります。</span><span class="sxs-lookup"><span data-stu-id="ac07d-120">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enables adapter clients to have a single BizTalk application with more than one Polling or TypedPolling operations for the same database or table.</span></span> <span data-ttu-id="ac07d-121">アダプターには、このようなシナリオをサポートするには、一意の ID が含まれています — **InboundID**— 接続 URI。</span><span class="sxs-lookup"><span data-stu-id="ac07d-121">To support such a scenario, the adapter includes a unique ID— **InboundID**—in the connection URI.</span></span> <span data-ttu-id="ac07d-122">接続 URI に追加されたときに、この ID になります一意、単一の BizTalk アプリケーションで複数のポーリング操作できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ac07d-122">This ID, when added to the connection URI, makes it unique, thereby enabling multiple polling operations in a single BizTalk application.</span></span>  
  
 <span data-ttu-id="ac07d-123">このセクションのトピックでは、ポーリングや TypedPolling、XmlPolling を BizTalk アプリケーションで使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac07d-123">The topics in this section provide instructions on how to use Polling, TypedPolling, and XmlPolling in a BizTalk application.</span></span> <span data-ttu-id="ac07d-124">このセクションでは、使用する方法についても説明します、 **InboundID**接続プロパティです。</span><span class="sxs-lookup"><span data-stu-id="ac07d-124">This section also provides information about how to use the **InboundID** connection property.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ac07d-125">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ac07d-125">In This Section</span></span>  
  
-   [<span data-ttu-id="ac07d-126">BizTalk Server を使用して SQL Server からのポーリングに基づいたデータ変更メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="ac07d-126">Receive Polling-based Data-changed Messages from SQL Server by using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)  
  
-   [<span data-ttu-id="ac07d-127">BizTalk Server を使用して SQL Server からのポーリングに基づいたデータ変更メッセージを厳密に型指定の受信します。</span><span class="sxs-lookup"><span data-stu-id="ac07d-127">Receive Strongly-typed Polling-based Data-changed Messages from SQL Server using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-messages-from-sql-in-biztalk.md)  
  
-   [<span data-ttu-id="ac07d-128">BizTalk Server を使用して SQL からのポーリング メッセージを使用して SELECT ステートメントと FOR XML 句の受信します。</span><span class="sxs-lookup"><span data-stu-id="ac07d-128">Receive Polling Messages Using SELECT Statements with FOR XML Clause from SQL using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-using-select-with-for-xml-clause-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="ac07d-129">BizTalk Server を使用して SQL からの複数の受信ポートにメッセージ間でのポーリングの受信します。</span><span class="sxs-lookup"><span data-stu-id="ac07d-129">Receive Polling Messages Across Multiple Receive Ports from SQL using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)  
  
## <a name="see-also"></a><span data-ttu-id="ac07d-130">参照</span><span class="sxs-lookup"><span data-stu-id="ac07d-130">See Also</span></span>  
[<span data-ttu-id="ac07d-131">SQL アダプターを使用して BizTalk アプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="ac07d-131">Develop BizTalk applications using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)