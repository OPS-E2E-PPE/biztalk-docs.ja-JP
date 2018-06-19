---
title: WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発 |Microsoft ドキュメント
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
ms.openlocfilehash: 77fb9b6ca1fc70a55b59c6708450b8d94a01eff8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214986"
---
# <a name="develop-oracle-database-applications-using-the-wcf-channel-model"></a><span data-ttu-id="d6119-102">WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="d6119-102">Develop Oracle Database applications using the WCF Channel Model</span></span>
<span data-ttu-id="d6119-103">使用することができます、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]チャネル モデルを使用する、 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle DB バインドで作成されたチャネル インスタンス経由で直接 XML メッセージを送信することによってです。</span><span class="sxs-lookup"><span data-stu-id="d6119-103">You can use the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] channel model to consume the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] by sending XML messages directly over a channel instance created with the Oracle DB Binding.</span></span>  
  
 <span data-ttu-id="d6119-104">厳密に型指定されたクラスと、WCF サービス モデルを公開するメソッドを使用する場合より、WCF チャネル モデルを使用する利点の 1 つは、チャネル モデルが Oracle データベースで実行する操作をより詳細に制御を提供することです。</span><span class="sxs-lookup"><span data-stu-id="d6119-104">One advantage of using the WCF channel model over using the strongly-typed classes and methods that the WCF service model exposes is that the channel model provides more fine-grained control over the operations that you perform on the Oracle database.</span></span> <span data-ttu-id="d6119-105">なぜでしょうか。</span><span class="sxs-lookup"><span data-stu-id="d6119-105">Why?</span></span> <span data-ttu-id="d6119-106">WCF チャネル モデルでは、チャネル経由で送信するメッセージの内容を直接制御します。</span><span class="sxs-lookup"><span data-stu-id="d6119-106">In the WCF channel model you directly control the contents of the messages that you send over the channel.</span></span>  
  
 <span data-ttu-id="d6119-107">特定のシナリオでは、この余分なレベルの制御と役に立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="d6119-107">In certain scenarios, this extra level of control can be beneficial.</span></span> <span data-ttu-id="d6119-108">たとえば、WCF チャネル モデルを使用して、テーブルの更新操作を実行するときに、ターゲット行の列をメッセージを渡すテンプレートの更新からの列を省略することでに更新できます選択的にします。</span><span class="sxs-lookup"><span data-stu-id="d6119-108">For example, when you use the WCF channel model to perform an Update operation on a table, you can selectively update columns in the target rows by omitting columns from the update template that you pass in the message.</span></span> <span data-ttu-id="d6119-109">によって公開されている、update メソッドを[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントは、テーブルのスキーマ内のすべての列を含むテンプレートに対してレコードの厳密に型指定されたパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d6119-109">The update method exposed by a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] client uses a strongly-typed record parameter for the template that includes every column in the table schema.</span></span> <span data-ttu-id="d6119-110">列にある場合"nillable = false"、WSDL 内で、更新する必要がある WCF サービス モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="d6119-110">If a column has “nillable=false” in the WSDL, it must be updated using the WCF service model.</span></span>  
  
 <span data-ttu-id="d6119-111">WCF チャネル モデルを WCF サービス モデルを提供する主なメリットは、Oracle ラージ オブジェクト (LOB) データ型のエンド ツー エンドのストリーミングをサポートする包括的なです。</span><span class="sxs-lookup"><span data-stu-id="d6119-111">Another key advantage that the WCF channel model provides over the WCF service model is more comprehensive support for end-to-end streaming of Oracle large object (LOB) data types.</span></span> <span data-ttu-id="d6119-112">WCF チャネル モデルを使用して、エンド ツー エンドのストリーミングを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d6119-112">By using the WCF channel model you can perform end-to-end streaming:</span></span>  
  
-   <span data-ttu-id="d6119-113">テーブル内の LOB 列を更新または UpdateLOB 操作を使用して表示します。</span><span class="sxs-lookup"><span data-stu-id="d6119-113">To update an LOB column in a table or view using the UpdateLOB operation.</span></span>  
  
-   <span data-ttu-id="d6119-114">アウトでと OUT パラメーターを含む IN は LOB プロシージャと関数によって返されるデータです。</span><span class="sxs-lookup"><span data-stu-id="d6119-114">On OUT and IN OUT parameters containing LOB data that are returned by procedures and functions.</span></span>  
  
-   <span data-ttu-id="d6119-115">LOB データに SQLEXECUTE 操作の結果に含まれます。</span><span class="sxs-lookup"><span data-stu-id="d6119-115">On LOB data that is contained in the result of a SQLEXECUTE operation.</span></span>  
  
-   <span data-ttu-id="d6119-116">LOB データの列を POLLINGSTMT 操作で返されます。</span><span class="sxs-lookup"><span data-stu-id="d6119-116">On LOB data columns that are returned in the POLLINGSTMT operation.</span></span>  
  
-   <span data-ttu-id="d6119-117">LOB データの列をテーブルまたはビューに対する Select 操作によって返されます。</span><span class="sxs-lookup"><span data-stu-id="d6119-117">On LOB data columns that are returned by a Select operation on a table or view.</span></span>  
  
 <span data-ttu-id="d6119-118">これは、ため、WCF チャネル モデルで直接制御する送信メッセージにメッセージ本文を指定する方法と、受信メッセージでメッセージ本文を処理する方法です。</span><span class="sxs-lookup"><span data-stu-id="d6119-118">This is because in the WCF channel model you directly control how you provide the message body on outgoing messages and how you process the message body on incoming messages.</span></span>  
  
 <span data-ttu-id="d6119-119">これに対し、WCF サービスのモデルのみを提供します。</span><span class="sxs-lookup"><span data-stu-id="d6119-119">In contrast, the WCF service model only provides:</span></span>  
  
-   <span data-ttu-id="d6119-120">エンドツー エンド ReadLOB 操作の 1 つの操作の LOB データをストリーミングします。</span><span class="sxs-lookup"><span data-stu-id="d6119-120">End-to-end streaming for LOB data on one operation, the ReadLOB operation.</span></span>  
  
-   <span data-ttu-id="d6119-121">LOB データをストリーミング方式で Oracle データベースを更新する機能がありません。</span><span class="sxs-lookup"><span data-stu-id="d6119-121">No capability to update LOB data on the Oracle database in a streamed fashion.</span></span>  
  
 <span data-ttu-id="d6119-122">このトピックのセクションでは、操作を実行する方法を説明する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="d6119-122">The sections in this topic explain how to perform operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] by using the WCF channel model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d6119-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d6119-123">In This Section</span></span>  
  
-   [<span data-ttu-id="d6119-124">Oracle データベース アダプターで WCF チャネル モデルの概要</span><span class="sxs-lookup"><span data-stu-id="d6119-124">Overview of the WCF channel model with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-channel-model-with-the-oracle-database-adapter.md) 
  
-   [<span data-ttu-id="d6119-125">Oracle データベースを使用して、チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d6119-125">Create a channel using Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md) 
  
-   [<span data-ttu-id="d6119-126">WCF チャネル モデルを使用して Oracle データベースに対する操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="d6119-126">Invoke Operations on the Oracle Database Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/invoke-operations-on-the-oracle-database-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="d6119-127">WCF チャネル モデルを使用して Oracle データベースで SQLEXECUTE 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d6119-127">Run a SQLEXECUTE Operation in Oracle Database using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="d6119-128">WCF チャネル モデルを使用して Oracle データベースで挿入操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d6119-128">Run an Insert Operation in Oracle Database using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="d6119-129">WCF チャネル モデルを使用して Oracle データベース内の関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="d6119-129">Invoke a Function in Oracle Database using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="d6119-130">WCF チャネル モデルを使用して Oracle データベースでデータ変更のポーリングに基づいたメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="d6119-130">Receive Polling-based Data-changed Messages in Oracle Database using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-channel.md)  
  
-   [<span data-ttu-id="d6119-131">ストリーミングの Oracle データベース LOB データ型 WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="d6119-131">Streaming Oracle Database LOB Data Types Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)