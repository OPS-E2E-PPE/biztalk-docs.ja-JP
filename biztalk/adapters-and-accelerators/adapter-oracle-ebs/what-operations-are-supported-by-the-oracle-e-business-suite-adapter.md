---
title: "Oracle E-business Suite アダプターによってどのような操作がサポートされている |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64cd124a-5e7f-4ee8-85d3-f9540b25d766
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7236c21f1e298f2ccd4cbb97db481cbd3626d186
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-operations-are-supported-by-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="7a0d2-102">どのような操作、Oracle E-business Suite アダプターによってサポートされます。</span><span class="sxs-lookup"><span data-stu-id="7a0d2-102">What operations are supported by the Oracle E-Business Suite adapter</span></span>
## <a name="overview"></a><span data-ttu-id="7a0d2-103">概要</span><span class="sxs-lookup"><span data-stu-id="7a0d2-103">Overview</span></span>
<span data-ttu-id="7a0d2-104">アダプターのクライアントは、Oracle E-business Suite での操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7a0d2-104">Adapter clients can perform operations in Oracle E-Business Suite by:</span></span>  
  
-   <span data-ttu-id="7a0d2-105">BizTalk プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="7a0d2-105">Creating BizTalk projects</span></span>  
  
-   <span data-ttu-id="7a0d2-106">WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="7a0d2-106">Using the WCF channel model</span></span>  
  
-   <span data-ttu-id="7a0d2-107">WCF サービス モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="7a0d2-107">Using the WCF service model</span></span>  
  
 <span data-ttu-id="7a0d2-108">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]アプリケーションがそれで呼び出すことができ、アプリケーションで呼び出すことができます、さらに、操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="7a0d2-108">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="7a0d2-109">これらの操作がチャネル経由で SOAP メッセージを送信することによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="7a0d2-109">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="7a0d2-110">応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。</span><span class="sxs-lookup"><span data-stu-id="7a0d2-110">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="7a0d2-111">メッセージの構造および各操作に関連付けられている SOAP アクションについては、次を参照してください。[メッセージと BizTalk Adapter for Oracle E-business Suite のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="7a0d2-111">For information about the message structure and the SOAP action associated with each operation, see [messages and message schemas for BizTalk Adapter for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span></span>  
  
 <span data-ttu-id="7a0d2-112">このセクションでは、Oracle E-business Suite を使用してサポートされる操作に関する情報を提供、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="7a0d2-112">This section provides information about the operations supported in Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7a0d2-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7a0d2-113">In this section</span></span>  
  
-   [<span data-ttu-id="7a0d2-114">アプリケーション コンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="7a0d2-114">Set Application Context</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)  
  
-   [<span data-ttu-id="7a0d2-115">インターフェイスのテーブルとのインターフェイス ビューでの操作</span><span class="sxs-lookup"><span data-stu-id="7a0d2-115">Operations on Interface Tables and Interface Views</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)  
  
-   [<span data-ttu-id="7a0d2-116">PL/SQL Api に対する操作</span><span class="sxs-lookup"><span data-stu-id="7a0d2-116">Operations on PL/SQL APIs</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-pl-sql-apis.md)  
  
-   [<span data-ttu-id="7a0d2-117">同時実行プログラムでの操作</span><span class="sxs-lookup"><span data-stu-id="7a0d2-117">Operations on Concurrent Programs</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)  
  
-   [<span data-ttu-id="7a0d2-118">要求のセットに対する操作</span><span class="sxs-lookup"><span data-stu-id="7a0d2-118">Operations on Request Sets</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)  
  
-   [<span data-ttu-id="7a0d2-119">インターフェイス テーブル、インターフェイス ビュー、テーブル、および LOB データを含むビューでの操作</span><span class="sxs-lookup"><span data-stu-id="7a0d2-119">Operations on Interface Tables, Interface Views, Tables, and Views That Contain LOB Data</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)  
  
-   [<span data-ttu-id="7a0d2-120">BFILE データ型を含むテーブルでの操作</span><span class="sxs-lookup"><span data-stu-id="7a0d2-120">Operations on Tables That Contain BFILE Data Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)  
  
-   [<span data-ttu-id="7a0d2-121">関数およびストアド プロシージャでの操作</span><span class="sxs-lookup"><span data-stu-id="7a0d2-121">Operations on Functions and Stored Procedures</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-stored-procedures1.md)  
  
-   [<span data-ttu-id="7a0d2-122">関数と REF CURSOR パラメーターを持つプロシージャに対する操作</span><span class="sxs-lookup"><span data-stu-id="7a0d2-122">Operations on Functions and Procedures with REF CURSOR Parameters</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md)  
  
-   [<span data-ttu-id="7a0d2-123">関数およびレコードの種類のプロシージャでの操作</span><span class="sxs-lookup"><span data-stu-id="7a0d2-123">Operations on Functions and Procedures with RECORD Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
-   [<span data-ttu-id="7a0d2-124">シノニムに対する操作</span><span class="sxs-lookup"><span data-stu-id="7a0d2-124">Operations on Synonyms</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-synonyms2.md)  
  
-   [<span data-ttu-id="7a0d2-125">データベースの変更通知を受信するための考慮事項</span><span class="sxs-lookup"><span data-stu-id="7a0d2-125">Consideration for Receiving Database Change Notifications</span></span>](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [<span data-ttu-id="7a0d2-126">ポーリングの受信呼び出しのサポート</span><span class="sxs-lookup"><span data-stu-id="7a0d2-126">Support for Inbound Calls Using Polling</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)  
  
-   [<span data-ttu-id="7a0d2-127">ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のサポート</span><span class="sxs-lookup"><span data-stu-id="7a0d2-127">Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)  
  
-   [<span data-ttu-id="7a0d2-128">複合操作のサポート</span><span class="sxs-lookup"><span data-stu-id="7a0d2-128">Support for Composite Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)  
  
-   [<span data-ttu-id="7a0d2-129">Oracle ユーザー定義型のサポート</span><span class="sxs-lookup"><span data-stu-id="7a0d2-129">Support for Oracle User-Defined Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-oracle-user-defined-types2.md)  
  
## <a name="see-also"></a><span data-ttu-id="7a0d2-130">参照</span><span class="sxs-lookup"><span data-stu-id="7a0d2-130">See Also</span></span>  
[<span data-ttu-id="7a0d2-131">Oracle E-business Suite の BizTalk アダプターを理解します。</span><span class="sxs-lookup"><span data-stu-id="7a0d2-131">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)