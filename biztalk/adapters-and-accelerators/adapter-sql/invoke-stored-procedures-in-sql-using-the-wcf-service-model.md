---
title: WCF サービス モデルを使用して SQL ストアド プロシージャを呼び出す |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4edd2fac-0b54-4406-932e-e3044a66b2e6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e2d707c37ba92fb6f1d1608ae43d02d1e964cd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222290"
---
# <a name="invoke-stored-procedures-in-sql-using-the-wcf-service-model"></a><span data-ttu-id="b1878-102">WCF サービス モデルを使用して SQL ストアド プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="b1878-102">Invoke Stored Procedures in SQL using the WCF Service Model</span></span>
<span data-ttu-id="b1878-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントは、ストアド プロシージャを呼び出す、WCF クライアントで呼び出すことができますの操作として、ストアド プロシージャを検出します。</span><span class="sxs-lookup"><span data-stu-id="b1878-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] discovers the stored procedures as operations that the adapter clients can invoke on the WCF client to invoke the stored procedure.</span></span> <span data-ttu-id="b1878-104">ストアド プロシージャが結果セットを返す方法に基づき、アダプターは、すべてのストアド プロシージャとしてを分類します。</span><span class="sxs-lookup"><span data-stu-id="b1878-104">Based on how the stored procedure returns the result set, the adapter categorizes all the stored procedures as:</span></span>  
  
-   <span data-ttu-id="b1878-105">**プロシージャ**です。</span><span class="sxs-lookup"><span data-stu-id="b1878-105">**Procedures**.</span></span> <span data-ttu-id="b1878-106">ストアド プロシージャを呼び出して、**プロシージャ**ノードは、データセットの配列を返します。</span><span class="sxs-lookup"><span data-stu-id="b1878-106">Invoking stored procedures from the **Procedures** node returns an array of DataSet.</span></span>  
  
-   <span data-ttu-id="b1878-107">**厳密に型指定されたプロシージャ**です。</span><span class="sxs-lookup"><span data-stu-id="b1878-107">**Strongly-Typed Procedures**.</span></span> <span data-ttu-id="b1878-108">ストアド プロシージャを呼び出して、 **Strongly-Typed プロシージャ**ノードは、厳密に型指定された結果セットを返します。</span><span class="sxs-lookup"><span data-stu-id="b1878-108">Invoking stored procedures from the **Strongly-Typed Procedures** node returns a strongly-typed result set.</span></span>  
  
 <span data-ttu-id="b1878-109">接続されているデータベースのストアド プロシージャの同じセットは、両方の下の一覧を表示、**プロシージャ**と**Strongly-Typed プロシージャ**ノード。</span><span class="sxs-lookup"><span data-stu-id="b1878-109">Note that the same set of stored procedures in the database you connected to will be listed both under the **Procedures** and **Strongly-Typed Procedures** node.</span></span> <span data-ttu-id="b1878-110">目的の結果セットの種類に基づいて、関連するノードからストアド プロシージャを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1878-110">Based on the kind of result set you want, you must invoke the stored procedure from the relevant node.</span></span> <span data-ttu-id="b1878-111">方法の詳細については[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ストアド プロシージャをサポートするを参照してください[BizTalk Server を使用して SQL Server でストアド プロシージャの実行](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="b1878-111">For more information about how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports stored procedures, see [Execute Stored Procedures in SQL Server using BizTalk Server](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="b1878-112">このセクションでは 2 つのストアド プロシージャを呼び出す方法について説明、**プロシージャ**と**Strongly-Typed プロシージャ**ノードでは、WCF クライアントを使用します。</span><span class="sxs-lookup"><span data-stu-id="b1878-112">This section provides instructions on how to invoke stored procedures from both the **Procedures** and **Strongly-Typed Procedures** node by using a WCF client.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b1878-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b1878-113">In This Section</span></span>  
  
-   [<span data-ttu-id="b1878-114">WCF サービス モデルを使用して sql Involk 弱い型指定のストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="b1878-114">Involk Weakly-typed Stored Procedures in SQL Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/invoke-weakly-typed-stored-procedures-in-sql-using-the-wcf-service-model.md)  
  
-   [<span data-ttu-id="b1878-115">WCF サービスのモデルを使用して SQL での厳密に型指定のストアド プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="b1878-115">Invoke Strongly-typed Stored Procedure in SQL Using WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/invoke-strongly-typed-stored-procedures-in-sql-using-wcf-service-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="b1878-116">参照</span><span class="sxs-lookup"><span data-stu-id="b1878-116">See Also</span></span>  
[<span data-ttu-id="b1878-117">WCF サービス モデルを使用してアプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="b1878-117">Develop applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)