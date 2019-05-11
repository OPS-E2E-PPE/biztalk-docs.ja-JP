---
title: SQL アダプターによってサポートされる操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b8f4099-df19-48c4-a135-1ec264af3513
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 873b74a253bd96c95ecf3d26be884fe83ac53e7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367430"
---
# <a name="what-operations-are-supported-by-the-sql-adapter"></a><span data-ttu-id="ea7e7-102">SQL アダプターによってサポートされる操作</span><span class="sxs-lookup"><span data-stu-id="ea7e7-102">What operations are supported by the SQL adapter</span></span>
<span data-ttu-id="ea7e7-103">アダプター クライアントを使用してでの SQL Server データベースで操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="ea7e7-103">You can use the adapter clients to perform operations on the SQL Server database by:</span></span>  
  
- <span data-ttu-id="ea7e7-104">BizTalk プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="ea7e7-104">Creating BizTalk projects</span></span>  
  
- <span data-ttu-id="ea7e7-105">WCF サービス モデルの使用</span><span class="sxs-lookup"><span data-stu-id="ea7e7-105">Using the WCF service model</span></span>  
  
- <span data-ttu-id="ea7e7-106">WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="ea7e7-106">Using the WCF channel model</span></span>  
  
  <span data-ttu-id="ea7e7-107">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]アプリケーションは、それを呼び出すことができ、アプリケーションで呼び出すことができます、さらに、操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="ea7e7-107">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="ea7e7-108">これらの操作は、チャネル経由で SOAP メッセージを送信することによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ea7e7-108">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="ea7e7-109">応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。</span><span class="sxs-lookup"><span data-stu-id="ea7e7-109">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="ea7e7-110">メッセージの構造とそれぞれの操作に関連付けられている SOAP アクションについては、次を参照してください。[メッセージと BizTalk adapter for SQL Server のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="ea7e7-110">For information about the message structure and the SOAP action associated with each operation, see [Messages and Message Schemas for BizTalk Adapter for SQL Server](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md).</span></span>  
  
  <span data-ttu-id="ea7e7-111">このセクションで、SQL Server データベースを使用してサポートされる操作について説明します、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ea7e7-111">This section provides information about the operations supported on the SQL Server database using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="ea7e7-112">参照</span><span class="sxs-lookup"><span data-stu-id="ea7e7-112">See Also</span></span>  
 [<span data-ttu-id="ea7e7-113">BizTalk Adapter for SQL Server の概要</span><span class="sxs-lookup"><span data-stu-id="ea7e7-113">Overview of BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)