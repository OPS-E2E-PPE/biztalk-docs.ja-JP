---
title: "どのような操作は、Oracle データベース アダプターによってサポートされて |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP
- operations, performing
ms.assetid: d78dbeb8-9dab-4a71-982e-f7ada51472e8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 014b0fc6158c151d510152550c0093f6ffa9031b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-operations-are-supported-by-the-oracle-database-adapter"></a><span data-ttu-id="6f442-102">どのような操作、Oracle データベース アダプターによってサポートされます。</span><span class="sxs-lookup"><span data-stu-id="6f442-102">What operations are supported by the Oracle Database adapter</span></span>
<span data-ttu-id="6f442-103">アダプターのクライアントは、BizTalk プロジェクトを作成することで、WCF チャネル モデルを使用して、または WCF サービス モデルを使用して Oracle データベースで操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="6f442-103">Adapter clients can perform operations on the Oracle database by creating BizTalk projects, by using the WCF channel model, or by using the WCF service model.</span></span> <span data-ttu-id="6f442-104">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アプリケーションがそれで呼び出すことができ、アプリケーションで呼び出すことができます、さらに、操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="6f442-104">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="6f442-105">これらの操作がチャネル経由で SOAP メッセージを送信することによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6f442-105">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="6f442-106">応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。</span><span class="sxs-lookup"><span data-stu-id="6f442-106">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="6f442-107">メッセージの構造および各操作に関連付けられている SOAP アクションについては、次を参照してください。[メッセージと BizTalk Adapter 用 Oracle Database のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="6f442-107">For information about the message structure and the SOAP action associated with each operation, see [Messages and Message Schemas for BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span></span>  
  
 <span data-ttu-id="6f442-108">このセクションでは、Oracle データベースを使用して、サポートされる操作に関する情報を提供、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6f442-108">This section provides information about the operations supported on the Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f442-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6f442-109">In This Section</span></span>  
  
-   [<span data-ttu-id="6f442-110">基本的な Insert、Update、Delete、および Oracle のテーブルおよびビューに対する Select 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6f442-110">Performing Basic Insert, Update, Delete, and Select Operations on Oracle Tables and Views</span></span>](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-and-select-operations-on-oracle-tables-and-views.md)  
  
-   [<span data-ttu-id="6f442-111">テーブルと LOB データを含むビューでの操作</span><span class="sxs-lookup"><span data-stu-id="6f442-111">Operations on Tables and Views That Contain LOB Data</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md)  
  
-   [<span data-ttu-id="6f442-112">関数と Oracle データベースでストアド プロシージャでの操作</span><span class="sxs-lookup"><span data-stu-id="6f442-112">Operations on Functions and Stored Procedures in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-stored-procedures-in-oracle-database.md)  
  
-   [<span data-ttu-id="6f442-113">関数と Oracle データベースの REF CURSOR パラメーターを持つプロシージャに対する操作</span><span class="sxs-lookup"><span data-stu-id="6f442-113">Operations on Functions and Procedures with REF CURSOR Parameters in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/ref-cursor-parameters-in-oracle-database-adapter.md)  
  
-   [<span data-ttu-id="6f442-114">関数と Oracle データベースのレコードの種類を持つプロシージャに対する操作</span><span class="sxs-lookup"><span data-stu-id="6f442-114">Operations on Functions and Procedures with RECORD Types in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-procedures-with-record-types-in-oracle-database.md)  
  
-   [<span data-ttu-id="6f442-115">BFILE データ型を持つテーブルに対する操作</span><span class="sxs-lookup"><span data-stu-id="6f442-115">Operations on Tables With BFILE Data Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)  
  
-   [<span data-ttu-id="6f442-116">Oracle データベースでシノニムに対する操作</span><span class="sxs-lookup"><span data-stu-id="6f442-116">Operations on Synonyms in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-synonyms-in-oracle-database.md)  
  
-   [<span data-ttu-id="6f442-117">Oracle データベースで SQLEXECUTE 操作</span><span class="sxs-lookup"><span data-stu-id="6f442-117">SQLEXECUTE Operation in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md)  
  
-   [<span data-ttu-id="6f442-118">Oracle データベースで複合操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6f442-118">Performing Composite Operations in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md)  
  
-   [<span data-ttu-id="6f442-119">Oracle データベースでデータ変更のポーリングに基づいたメッセージを受信するためのサポート</span><span class="sxs-lookup"><span data-stu-id="6f442-119">Support for Receiving Polling-based Data-changed Messages in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md)  
  
-   [<span data-ttu-id="6f442-120">受信データベースの変更通知を使用して、Oracle Database アダプターに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="6f442-120">Considerations for Receiving Database Change Notifications Using the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [<span data-ttu-id="6f442-121">Oracle データベースの Oracle ユーザー定義型のサポート</span><span class="sxs-lookup"><span data-stu-id="6f442-121">Support for Oracle User-Defined Types in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/support-for-oracle-user-defined-types-in-oracle-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="6f442-122">参照</span><span class="sxs-lookup"><span data-stu-id="6f442-122">See Also</span></span>  
 [<span data-ttu-id="6f442-123">BizTalk Adapter 用 Oracle Database の概要</span><span class="sxs-lookup"><span data-stu-id="6f442-123">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)