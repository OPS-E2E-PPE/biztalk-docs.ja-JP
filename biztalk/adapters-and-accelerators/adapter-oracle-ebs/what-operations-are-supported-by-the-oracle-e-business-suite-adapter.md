---
title: Oracle E-business Suite アダプターによってサポートされる操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64cd124a-5e7f-4ee8-85d3-f9540b25d766
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07ad676d737fffc45898c31f68d0895fc6919b63
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984051"
---
# <a name="what-operations-are-supported-by-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="c2d41-102">Oracle E-business Suite アダプターによってサポートされる操作</span><span class="sxs-lookup"><span data-stu-id="c2d41-102">What operations are supported by the Oracle E-Business Suite adapter</span></span>
## <a name="overview"></a><span data-ttu-id="c2d41-103">概要</span><span class="sxs-lookup"><span data-stu-id="c2d41-103">Overview</span></span>
<span data-ttu-id="c2d41-104">アダプター クライアントでの Oracle E-business Suite での操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c2d41-104">Adapter clients can perform operations in Oracle E-Business Suite by:</span></span>  
  
- <span data-ttu-id="c2d41-105">BizTalk プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="c2d41-105">Creating BizTalk projects</span></span>  
  
- <span data-ttu-id="c2d41-106">WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2d41-106">Using the WCF channel model</span></span>  
  
- <span data-ttu-id="c2d41-107">WCF サービス モデルの使用</span><span class="sxs-lookup"><span data-stu-id="c2d41-107">Using the WCF service model</span></span>  
  
  <span data-ttu-id="c2d41-108">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]アプリケーションは、それを呼び出すことができ、アプリケーションで呼び出すことができます、さらに、操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="c2d41-108">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="c2d41-109">これらの操作は、チャネル経由で SOAP メッセージを送信することによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c2d41-109">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="c2d41-110">応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。</span><span class="sxs-lookup"><span data-stu-id="c2d41-110">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="c2d41-111">メッセージの構造とそれぞれの操作に関連付けられている SOAP アクションについては、次を参照してください。[メッセージとメッセージ スキーマの BizTalk Adapter for Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2d41-111">For information about the message structure and the SOAP action associated with each operation, see [messages and message schemas for BizTalk Adapter for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span></span>  
  
  <span data-ttu-id="c2d41-112">このセクションで、Oracle E-business Suite を使用してサポートされる操作について説明します、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c2d41-112">This section provides information about the operations supported in Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c2d41-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c2d41-113">In this section</span></span>  
  
-   [<span data-ttu-id="c2d41-114">アプリケーションのコンテキストの設定</span><span class="sxs-lookup"><span data-stu-id="c2d41-114">Set Application Context</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)  
  
-   [<span data-ttu-id="c2d41-115">インターフェイス テーブルとインターフェイス ビューに対する操作</span><span class="sxs-lookup"><span data-stu-id="c2d41-115">Operations on Interface Tables and Interface Views</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)  
  
-   [<span data-ttu-id="c2d41-116">PL/SQL API に対する操作</span><span class="sxs-lookup"><span data-stu-id="c2d41-116">Operations on PL/SQL APIs</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-pl-sql-apis.md)  
  
-   [<span data-ttu-id="c2d41-117">同時実行プログラムに対する操作</span><span class="sxs-lookup"><span data-stu-id="c2d41-117">Operations on Concurrent Programs</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)  
  
-   [<span data-ttu-id="c2d41-118">要求セットに対する操作</span><span class="sxs-lookup"><span data-stu-id="c2d41-118">Operations on Request Sets</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)  
  
-   [<span data-ttu-id="c2d41-119">LOB データを含むインターフェイス テーブル、インターフェイス ビュー、テーブル、ビューに対する操作</span><span class="sxs-lookup"><span data-stu-id="c2d41-119">Operations on Interface Tables, Interface Views, Tables, and Views That Contain LOB Data</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)  
  
-   [<span data-ttu-id="c2d41-120">BFILE データ型を含むテーブルに対する操作</span><span class="sxs-lookup"><span data-stu-id="c2d41-120">Operations on Tables That Contain BFILE Data Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)  
  
-   [<span data-ttu-id="c2d41-121">関数とストアド プロシージャに対する操作</span><span class="sxs-lookup"><span data-stu-id="c2d41-121">Operations on Functions and Stored Procedures</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-stored-procedures1.md)  
  
-   [<span data-ttu-id="c2d41-122">REF CURSOR パラメーターを使用した関数およびプロシージャに対する操作</span><span class="sxs-lookup"><span data-stu-id="c2d41-122">Operations on Functions and Procedures with REF CURSOR Parameters</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md)  
  
-   [<span data-ttu-id="c2d41-123">RECORD 型を使用した関数およびプロシージャに対する操作</span><span class="sxs-lookup"><span data-stu-id="c2d41-123">Operations on Functions and Procedures with RECORD Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
-   [<span data-ttu-id="c2d41-124">シノニムに対する操作</span><span class="sxs-lookup"><span data-stu-id="c2d41-124">Operations on Synonyms</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-synonyms2.md)  
  
-   [<span data-ttu-id="c2d41-125">データベース変更通知を受信するための考慮事項</span><span class="sxs-lookup"><span data-stu-id="c2d41-125">Consideration for Receiving Database Change Notifications</span></span>](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [<span data-ttu-id="c2d41-126">ポーリングを使用する受信呼び出しのサポート</span><span class="sxs-lookup"><span data-stu-id="c2d41-126">Support for Inbound Calls Using Polling</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)  
  
-   [<span data-ttu-id="c2d41-127">ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のサポート</span><span class="sxs-lookup"><span data-stu-id="c2d41-127">Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)  
  
-   [<span data-ttu-id="c2d41-128">複合操作のサポート</span><span class="sxs-lookup"><span data-stu-id="c2d41-128">Support for Composite Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)  
  
-   [<span data-ttu-id="c2d41-129">Oracle ユーザー定義型のサポート</span><span class="sxs-lookup"><span data-stu-id="c2d41-129">Support for Oracle User-Defined Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-oracle-user-defined-types2.md)  
  
## <a name="see-also"></a><span data-ttu-id="c2d41-130">参照</span><span class="sxs-lookup"><span data-stu-id="c2d41-130">See Also</span></span>  
[<span data-ttu-id="c2d41-131">BizTalk Adapter for Oracle E-Business Suite について</span><span class="sxs-lookup"><span data-stu-id="c2d41-131">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)