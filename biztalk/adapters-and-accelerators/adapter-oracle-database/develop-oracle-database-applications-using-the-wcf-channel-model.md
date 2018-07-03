---
title: WCF チャネル モデルを使用して Oracle データベース アプリケーションの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, streaming
- channel programming, streaming
- WCF channel model, performing operations
- developing applications, by using the WCF channel model
- streaming, using the WCF channel model
- WCF channel model, developingn applications
- channel programming, performing operations
ms.assetid: cb6bf5fd-ff90-44bd-a9dd-03b00f12a78d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4990ebb9e9aad612a82af42b3d186643da1e91ab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002731"
---
# <a name="develop-oracle-database-applications-using-the-wcf-channel-model"></a><span data-ttu-id="5edcc-102">WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="5edcc-102">Develop Oracle Database applications using the WCF Channel Model</span></span>
<span data-ttu-id="5edcc-103">使用することができます、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]チャネル モデルを使用する、 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle DB のバインドで作成されたチャネル インスタンス経由で直接 XML メッセージを送信することです。</span><span class="sxs-lookup"><span data-stu-id="5edcc-103">You can use the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] channel model to consume the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] by sending XML messages directly over a channel instance created with the Oracle DB Binding.</span></span>  
  
 <span data-ttu-id="5edcc-104">WCF チャネル モデルを使用して、厳密に型指定されたクラスと、WCF サービス モデルを公開するメソッドを使用する利点の 1 つは、チャネル モデルが Oracle データベースで実行する操作のきめの細かい制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="5edcc-104">One advantage of using the WCF channel model over using the strongly-typed classes and methods that the WCF service model exposes is that the channel model provides more fine-grained control over the operations that you perform on the Oracle database.</span></span> <span data-ttu-id="5edcc-105">なぜでしょうか。</span><span class="sxs-lookup"><span data-stu-id="5edcc-105">Why?</span></span> <span data-ttu-id="5edcc-106">WCF チャネル モデルでは、直接チャネル経由で送信するメッセージの内容を制御します。</span><span class="sxs-lookup"><span data-stu-id="5edcc-106">In the WCF channel model you directly control the contents of the messages that you send over the channel.</span></span>  
  
 <span data-ttu-id="5edcc-107">特定のシナリオでこの追加レベルの制御はパフォーマンスを向上することはできます。</span><span class="sxs-lookup"><span data-stu-id="5edcc-107">In certain scenarios, this extra level of control can be beneficial.</span></span> <span data-ttu-id="5edcc-108">たとえば、WCF チャネル モデルを使用して、テーブルに対する Update 操作を実行するときに選択的に更新できますターゲット行内の列、メッセージを渡すテンプレートの更新からの列を省略することで。</span><span class="sxs-lookup"><span data-stu-id="5edcc-108">For example, when you use the WCF channel model to perform an Update operation on a table, you can selectively update columns in the target rows by omitting columns from the update template that you pass in the message.</span></span> <span data-ttu-id="5edcc-109">によって公開されている、update メソッドを[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントで、テーブルのスキーマ内のすべての列を含むテンプレートのレコードの厳密に型指定されたパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="5edcc-109">The update method exposed by a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] client uses a strongly-typed record parameter for the template that includes every column in the table schema.</span></span> <span data-ttu-id="5edcc-110">列にある場合は、"nillable = false"、WSDL の更新が必要、WCF サービス モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="5edcc-110">If a column has “nillable=false” in the WSDL, it must be updated using the WCF service model.</span></span>  
  
 <span data-ttu-id="5edcc-111">WCF チャネル モデルを使用する WCF サービスのモデルに対するもう 1 つの主な利点は、Oracle のラージ オブジェクト (LOB) データ型のエンド ツー エンドのストリーミングをサポートするより包括的なです。</span><span class="sxs-lookup"><span data-stu-id="5edcc-111">Another key advantage that the WCF channel model provides over the WCF service model is more comprehensive support for end-to-end streaming of Oracle large object (LOB) data types.</span></span> <span data-ttu-id="5edcc-112">WCF チャネル モデルを使用して、エンド ツー エンドのストリーミングを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5edcc-112">By using the WCF channel model you can perform end-to-end streaming:</span></span>  
  
- <span data-ttu-id="5edcc-113">テーブル内の LOB 列を更新または UpdateLOB 操作を使用して表示します。</span><span class="sxs-lookup"><span data-stu-id="5edcc-113">To update an LOB column in a table or view using the UpdateLOB operation.</span></span>  
  
- <span data-ttu-id="5edcc-114">アウトでと OUT パラメーターを含む IN は LOB プロシージャおよび関数によって返されるデータです。</span><span class="sxs-lookup"><span data-stu-id="5edcc-114">On OUT and IN OUT parameters containing LOB data that are returned by procedures and functions.</span></span>  
  
- <span data-ttu-id="5edcc-115">LOB データを SQLEXECUTE 操作の結果に含まれます。</span><span class="sxs-lookup"><span data-stu-id="5edcc-115">On LOB data that is contained in the result of a SQLEXECUTE operation.</span></span>  
  
- <span data-ttu-id="5edcc-116">LOB データ POLLINGSTMT 操作で返される列。</span><span class="sxs-lookup"><span data-stu-id="5edcc-116">On LOB data columns that are returned in the POLLINGSTMT operation.</span></span>  
  
- <span data-ttu-id="5edcc-117">LOB データ列でテーブルまたはビューの選択操作によって返されます。</span><span class="sxs-lookup"><span data-stu-id="5edcc-117">On LOB data columns that are returned by a Select operation on a table or view.</span></span>  
  
  <span data-ttu-id="5edcc-118">これは、ため、WCF チャネル モデルで直接制御する送信メッセージにメッセージ本文を提供する方法と、受信メッセージでメッセージ本文を処理する方法です。</span><span class="sxs-lookup"><span data-stu-id="5edcc-118">This is because in the WCF channel model you directly control how you provide the message body on outgoing messages and how you process the message body on incoming messages.</span></span>  
  
  <span data-ttu-id="5edcc-119">これに対し、WCF サービス モデルのみを提供します。</span><span class="sxs-lookup"><span data-stu-id="5edcc-119">In contrast, the WCF service model only provides:</span></span>  
  
- <span data-ttu-id="5edcc-120">エンド ツー エンド ReadLOB 操作の 1 つの操作では LOB データにストリーミングします。</span><span class="sxs-lookup"><span data-stu-id="5edcc-120">End-to-end streaming for LOB data on one operation, the ReadLOB operation.</span></span>  
  
- <span data-ttu-id="5edcc-121">LOB データをストリーミング方式で Oracle データベースを更新する機能がありません。</span><span class="sxs-lookup"><span data-stu-id="5edcc-121">No capability to update LOB data on the Oracle database in a streamed fashion.</span></span>  
  
  <span data-ttu-id="5edcc-122">このトピックのセクションでは、操作を実行する方法を説明します、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF チャネル モデルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="5edcc-122">The sections in this topic explain how to perform operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] by using the WCF channel model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5edcc-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5edcc-123">In This Section</span></span>  
  
-   [<span data-ttu-id="5edcc-124">Oracle データベース アダプターを使用した WCF チャネル モデルの概要</span><span class="sxs-lookup"><span data-stu-id="5edcc-124">Overview of the WCF channel model with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-channel-model-with-the-oracle-database-adapter.md) 
  
-   [<span data-ttu-id="5edcc-125">Oracle データベースを使用してチャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5edcc-125">Create a channel using Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md) 
  
-   [<span data-ttu-id="5edcc-126">WCF チャネル モデルを使用して Oracle データベースに対する操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="5edcc-126">Invoke Operations on the Oracle Database Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/invoke-operations-on-the-oracle-database-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="5edcc-127">WCF チャネル モデルを使用して Oracle データベースで SQLEXECUTE 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="5edcc-127">Run a SQLEXECUTE Operation in Oracle Database using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="5edcc-128">WCF チャネル モデルを使用して Oracle データベースで挿入操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="5edcc-128">Run an Insert Operation in Oracle Database using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="5edcc-129">WCF チャネル モデルを使用して Oracle データベースで関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="5edcc-129">Invoke a Function in Oracle Database using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="5edcc-130">WCF チャネル モデルを使用して Oracle データベースでのポーリングに基づいたデータ変更メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="5edcc-130">Receive Polling-based Data-changed Messages in Oracle Database using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-channel.md)  
  
-   [<span data-ttu-id="5edcc-131">ストリーミングの Oracle データベース LOB データ型 WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="5edcc-131">Streaming Oracle Database LOB Data Types Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)