---
title: Oracle データベース アダプターによってサポートされる操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP
- operations, performing
ms.assetid: d78dbeb8-9dab-4a71-982e-f7ada51472e8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed048357b98f8b831f53d00495fb9f9961f6afb7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375847"
---
# <a name="what-operations-are-supported-by-the-oracle-database-adapter"></a><span data-ttu-id="e7d6f-102">Oracle データベース アダプターによってサポートされる操作</span><span class="sxs-lookup"><span data-stu-id="e7d6f-102">What operations are supported by the Oracle Database adapter</span></span>
<span data-ttu-id="e7d6f-103">アダプター クライアントは、BizTalk プロジェクトを作成して、WCF チャネル モデルを使用して、または WCF サービス モデルを使用して、Oracle データベースで操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e7d6f-103">Adapter clients can perform operations on the Oracle database by creating BizTalk projects, by using the WCF channel model, or by using the WCF service model.</span></span> <span data-ttu-id="e7d6f-104">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アプリケーションは、それを呼び出すことができ、アプリケーションで呼び出すことができます、さらに、操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="e7d6f-104">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="e7d6f-105">これらの操作は、チャネル経由で SOAP メッセージを送信することによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e7d6f-105">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="e7d6f-106">応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。</span><span class="sxs-lookup"><span data-stu-id="e7d6f-106">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="e7d6f-107">メッセージの構造とそれぞれの操作に関連付けられている SOAP アクションについては、次を参照してください。[メッセージとメッセージ スキーマの BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="e7d6f-107">For information about the message structure and the SOAP action associated with each operation, see [Messages and Message Schemas for BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span></span>  
  
 <span data-ttu-id="e7d6f-108">このセクションで使用して Oracle データベースでサポートされる操作に関する情報を提供する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e7d6f-108">This section provides information about the operations supported on the Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e7d6f-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e7d6f-109">In This Section</span></span>  
  
-   [<span data-ttu-id="e7d6f-110">基本的な Insert、Update、Delete、および Oracle のテーブルおよびビューに対する Select 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e7d6f-110">Performing Basic Insert, Update, Delete, and Select Operations on Oracle Tables and Views</span></span>](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-and-select-operations-on-oracle-tables-and-views.md)  
  
-   [<span data-ttu-id="e7d6f-111">テーブルと LOB データを格納するビューに対する操作</span><span class="sxs-lookup"><span data-stu-id="e7d6f-111">Operations on Tables and Views That Contain LOB Data</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md)  
  
-   [<span data-ttu-id="e7d6f-112">関数と Oracle データベースでストアド プロシージャに対する操作</span><span class="sxs-lookup"><span data-stu-id="e7d6f-112">Operations on Functions and Stored Procedures in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-stored-procedures-in-oracle-database.md)  
  
-   [<span data-ttu-id="e7d6f-113">関数と Oracle データベースの REF CURSOR パラメーターを使用したプロシージャに対する操作</span><span class="sxs-lookup"><span data-stu-id="e7d6f-113">Operations on Functions and Procedures with REF CURSOR Parameters in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/ref-cursor-parameters-in-oracle-database-adapter.md)  
  
-   [<span data-ttu-id="e7d6f-114">Oracle データベースのレコードの種類で関数とプロシージャに対する操作</span><span class="sxs-lookup"><span data-stu-id="e7d6f-114">Operations on Functions and Procedures with RECORD Types in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-procedures-with-record-types-in-oracle-database.md)  
  
-   [<span data-ttu-id="e7d6f-115">BFILE データ型を持つテーブルに対する操作</span><span class="sxs-lookup"><span data-stu-id="e7d6f-115">Operations on Tables With BFILE Data Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)  
  
-   [<span data-ttu-id="e7d6f-116">Oracle データベースでシノニムに対する操作</span><span class="sxs-lookup"><span data-stu-id="e7d6f-116">Operations on Synonyms in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-synonyms-in-oracle-database.md)  
  
-   [<span data-ttu-id="e7d6f-117">Oracle データベースで SQLEXECUTE 操作</span><span class="sxs-lookup"><span data-stu-id="e7d6f-117">SQLEXECUTE Operation in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md)  
  
-   [<span data-ttu-id="e7d6f-118">Oracle データベースで複合操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e7d6f-118">Performing Composite Operations in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md)  
  
-   [<span data-ttu-id="e7d6f-119">Oracle データベースでのポーリングに基づいたデータ変更メッセージを受信するためのサポート</span><span class="sxs-lookup"><span data-stu-id="e7d6f-119">Support for Receiving Polling-based Data-changed Messages in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md)  
  
-   [<span data-ttu-id="e7d6f-120">受信データベース変更通知を使用して、Oracle Database アダプターに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="e7d6f-120">Considerations for Receiving Database Change Notifications Using the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [<span data-ttu-id="e7d6f-121">Oracle データベースでの Oracle ユーザー定義型のサポート</span><span class="sxs-lookup"><span data-stu-id="e7d6f-121">Support for Oracle User-Defined Types in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/support-for-oracle-user-defined-types-in-oracle-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="e7d6f-122">参照</span><span class="sxs-lookup"><span data-stu-id="e7d6f-122">See Also</span></span>  
 [<span data-ttu-id="e7d6f-123">BizTalk Adapter for Oracle Database の概要</span><span class="sxs-lookup"><span data-stu-id="e7d6f-123">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)