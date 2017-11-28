---
title: "SQL アダプターによってどのような操作がサポートされている |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b8f4099-df19-48c4-a135-1ec264af3513
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59d413a763823f49b0bf905b42d8513cbbb1e745
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-operations-are-supported-by-the-sql-adapter"></a><span data-ttu-id="78f33-102">どのような操作、SQL アダプターによってサポートされます。</span><span class="sxs-lookup"><span data-stu-id="78f33-102">What operations are supported by the SQL adapter</span></span>
<span data-ttu-id="78f33-103">アダプターのクライアントを使用して、によって、SQL Server データベースで操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="78f33-103">You can use the adapter clients to perform operations on the SQL Server database by:</span></span>  
  
-   <span data-ttu-id="78f33-104">BizTalk プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="78f33-104">Creating BizTalk projects</span></span>  
  
-   <span data-ttu-id="78f33-105">WCF サービス モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="78f33-105">Using the WCF service model</span></span>  
  
-   <span data-ttu-id="78f33-106">WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="78f33-106">Using the WCF channel model</span></span>  
  
 <span data-ttu-id="78f33-107">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]アプリケーションがそれで呼び出すことができ、アプリケーションで呼び出すことができます、さらに、操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="78f33-107">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="78f33-108">これらの操作がチャネル経由で SOAP メッセージを送信することによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="78f33-108">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="78f33-109">応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。</span><span class="sxs-lookup"><span data-stu-id="78f33-109">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="78f33-110">メッセージの構造および各操作に関連付けられている SOAP アクションについては、次を参照してください。[メッセージと BizTalk Adapter for SQL Server のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="78f33-110">For information about the message structure and the SOAP action associated with each operation, see [Messages and Message Schemas for BizTalk Adapter for SQL Server](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md).</span></span>  
  
 <span data-ttu-id="78f33-111">このセクションでは、SQL Server データベースを使用して、サポートされる操作に関する情報を提供、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="78f33-111">This section provides information about the operations supported on the SQL Server database using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="78f33-112">参照</span><span class="sxs-lookup"><span data-stu-id="78f33-112">See Also</span></span>  
 [<span data-ttu-id="78f33-113">BizTalk Adapter for SQL Server の概要</span><span class="sxs-lookup"><span data-stu-id="78f33-113">Overview of BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)