---
title: クエリを実行して、一覧の取得時の制限事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, querying limitations
- querying, limitations [JD Edwards OneWorld adapters]
ms.assetid: 1b6f5d2a-d1e2-4c78-8f4a-f00d10f008b9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f2e0f813a793aa05756ef52925081375203f2f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262338"
---
# <a name="limitations-when-querying-and-retrieving-lists"></a><span data-ttu-id="191ec-102">リストのクエリと取得時の制限事項</span><span class="sxs-lookup"><span data-stu-id="191ec-102">Limitations When Querying and Retrieving Lists</span></span>
<span data-ttu-id="191ec-103">JD Edwards OneWorld の通信アーキテクチャは、単一メッセージ、単一応答のアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="191ec-103">The JD Edwards OneWorld communication architecture is a single-message, single-reply architecture.</span></span> <span data-ttu-id="191ec-104">メッセージのリストまたは配列を返すことはできません。</span><span class="sxs-lookup"><span data-stu-id="191ec-104">You cannot return a list of messages or an array.</span></span> <span data-ttu-id="191ec-105">基になるコードは C++ であり、C++ では、1 つの構造体へのポインタを指定して呼び出し、その構造体で変更を行って、関数が終了します。</span><span class="sxs-lookup"><span data-stu-id="191ec-105">The underlying code is C++, which calls with a pointer to a single structure, makes changes in the structure, and then exits.</span></span>  
  
## <a name="querying-and-retrieving-lists"></a><span data-ttu-id="191ec-106">リストのクエリと取得</span><span class="sxs-lookup"><span data-stu-id="191ec-106">Querying and Retrieving Lists</span></span>  
 <span data-ttu-id="191ec-107">JD Edwards OneWorld のビジネス関数アーキテクチャの制限により、Microsoft BizTalk Adapter for JD Edwards OneWorld を使用して検索条件に基づきレコードのリストをクエリおよび取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="191ec-107">You cannot query and retrieve lists of records based on search criteria using Microsoft BizTalk Adapter for JD Edwards OneWorld due to a limitation with the JD Edwards OneWorld business function architecture.</span></span>  
  
 <span data-ttu-id="191ec-108">JD Edwards OneWorld では、専用の (複雑な) 内部関数呼び出しを使用して、データベース接続が実現されます。</span><span class="sxs-lookup"><span data-stu-id="191ec-108">In JD Edwards OneWorld, database connectivity is provided by using a set of proprietary (and complex) internal function calls.</span></span> <span data-ttu-id="191ec-109">取得または更新する列のリストを作成し、並べ替えまたは選択用の特別な構造体を作成するために明示的な低レベルの呼び出しが必要とされるため、専用の内部関数呼び出しによって基になるデータベースの関数呼び出しはマスクされます。</span><span class="sxs-lookup"><span data-stu-id="191ec-109">These calls mask the underlying database version by requiring very explicit and low-level calls to create lists of columns to retrieve or update, and create specialized structures for sorting or selection.</span></span> <span data-ttu-id="191ec-110">API セットは Java (または他の) 接続メソッドでは公開されないため、ビジネス関数を使用してレコードセットを処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="191ec-110">The sets of APIs are not exposed through the Java (or any other) connectivity method; therefore, record sets cannot be handled through business functions.</span></span>  
  
 <span data-ttu-id="191ec-111">JD Edwards OneWorld ツールセット内で、1 つのレコードまたはレコードセットを処理するビジネス関数を作成することはできますが、JD Edwards OneWorld ツールの外部にある項目のリストにアクセスするのはより困難です。</span><span class="sxs-lookup"><span data-stu-id="191ec-111">Within the JD Edwards OneWorld toolset, you can create business functions that handle a single record or operate on a group of records; however, accessing lists of items outside the JD Edwards OneWorld tools is more difficult.</span></span>  
  
 <span data-ttu-id="191ec-112">この問題を回避するために、クエリに基づいてレコード キーのリストを返すカスタム ビジネス関数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="191ec-112">To work around this issue, you can create a custom business function that returns a list of record keys based on a query.</span></span> <span data-ttu-id="191ec-113">JDENET (JD Edwards OneWorld 内部の専用メッセージング API) では、大規模または無制限の結果セットを管理するためのメッセージ バッファ サイズに制限があるため、リストをセグメント化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="191ec-113">You must segment the lists, because JDENET (the JD Edwards OneWorld internal proprietary messaging API) has a limitation on the message buffer size for managing large or unbounded result sets.</span></span> <span data-ttu-id="191ec-114">リストが完了したことを示すインジケータが返されるまで、クライアント コードはそのビジネス関数の連続呼び出しで反復 (ループ) しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="191ec-114">The client code must iterate (loop) through successive calls to the business function, until an indicator is returned stating that the list is complete.</span></span>  
  
## <a name="controlling-iteration"></a><span data-ttu-id="191ec-115">繰り返しの制御</span><span class="sxs-lookup"><span data-stu-id="191ec-115">Controlling Iteration</span></span>  
 <span data-ttu-id="191ec-116">JD Edwards OneWorld ビジネス関数の呼び出しはすべてステートレスであるため、オープン カーソルを保持し、要求に応じて追加の行を返すことができません。</span><span class="sxs-lookup"><span data-stu-id="191ec-116">All calls to JD Edwards OneWorld business functions are stateless; therefore, the business function cannot maintain an open cursor and return more rows on request.</span></span> <span data-ttu-id="191ec-117">呼び出しごとに、JD Edwards OneWorld XE ビジネス関数に位置情報を渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="191ec-117">Positioning information must be passed to the JD Edwards OneWorld XE business function on each call.</span></span>  
  
 <span data-ttu-id="191ec-118">繰り返しを制御するための方法の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="191ec-118">The following is a list of techniques for controlling iteration:</span></span>  
  
-   <span data-ttu-id="191ec-119">JD Edwards OneWorld 側で、結果セットを一時ストレージ ファイルに書き込みます。この一時ストレージ ファイルは、連続呼び出しに渡される (ファイル名やジョブ番号などの) ID を、カーソル位置を指定するレコード番号と共に返します。</span><span class="sxs-lookup"><span data-stu-id="191ec-119">On the JD Edwards OneWorld side, write the result set to a temporary storage file, which returns an ID (such as a file name or job number) that can be given on successive calls, along with the record number to position the cursor.</span></span> <span data-ttu-id="191ec-120">それぞれの連続呼び出しは、渡されたレコード番号に基づいてリスト内で位置指定されます。</span><span class="sxs-lookup"><span data-stu-id="191ec-120">Any successive call is positioned within the list based on the passed-in record number.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="191ec-121">BizTalk Adapter for JD Edwards OneWorld を経由した呼び出しは負荷分散できますが、最終的には、呼び出し先の資格情報とビジネス関数に基づいて単一のアプリケーション サーバーによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="191ec-121">Calls through BizTalk Adapter for JD Edwards OneWorld can be load-balanced; however, they are eventually served by a single application server based on the credentials and business function being called.</span></span> <span data-ttu-id="191ec-122">したがって、ある呼び出しによってサーバー上に一時ファイルが作成されると、2 回目以降の呼び出しは同じサーバーで処理されます。</span><span class="sxs-lookup"><span data-stu-id="191ec-122">Therefore, if a call creates a temporary file on a server, additional calls are served by the same server.</span></span> <span data-ttu-id="191ec-123">詳細については、『JD Edwards OneWorld CNC Guides』の「Object Configuration Mapping」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="191ec-123">For more information, see Object Configuration Mapping in the JD Edwards OneWorld CNC Guides.</span></span>  
  
-   <span data-ttu-id="191ec-124">2 回目以降の呼び出しで (主キーの値などの) 位置情報を返し、そのキーを追加のパラメータとして渡してクエリを再実行できます。</span><span class="sxs-lookup"><span data-stu-id="191ec-124">Position information (such as a primary key value) can be returned on the second and subsequent calls, and the query can be reissued based on the key as an additional parameter.</span></span> <span data-ttu-id="191ec-125">この方法は、BizTalk Adapter for JD Edwards OneWorld のリポジトリ参照コードで使用されます。</span><span class="sxs-lookup"><span data-stu-id="191ec-125">This method is used in the repository browsing code for BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="191ec-126">最初の 2 つの方法のうち、主キーの値を使用してクエリを再実行する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="191ec-126">Of the first two techniques, the recommended method is to use primary key values and reissue the query.</span></span> <span data-ttu-id="191ec-127">この方法の場合、必要になるコードの量が最も少なく、最適化やキャッシュの負荷はデータベースに課せられます。</span><span class="sxs-lookup"><span data-stu-id="191ec-127">This method requires the smallest amount of code and places the optimization and caching burden on the database.</span></span>  
  
-   <span data-ttu-id="191ec-128">呼び出し元のアプリケーションは、主キーのリスト (相互参照など) を格納できます。</span><span class="sxs-lookup"><span data-stu-id="191ec-128">The calling application can store a list of primary keys (such as a cross reference).</span></span> <span data-ttu-id="191ec-129">たとえば、カスタマ リレーションシップ マネジメント (CRM) システムによって顧客レコードが作成され、ビジネス関数呼び出しを使用して JD Edwards OneWorld に追加された場合、この顧客レコードを追加するビジネス関数は AN8 フィールド (short アドレス番号) の値を設定し、リターン バッファで可視になります。</span><span class="sxs-lookup"><span data-stu-id="191ec-129">For example, if a customer relationship management (CRM) system creates a customer record and then adds it to JD Edwards OneWorld using a business function call, the business function that adds a customer record sets the value for the AN8 field (short address number) and is visible in the return buffer.</span></span> <span data-ttu-id="191ec-130">この番号は、元の顧客レコードの参照フィールドに書き込まれるか、カスタマイズされた相互参照テーブルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="191ec-130">This number can then be written to a reference field on the original customer record, or stored into a customized cross-reference table.</span></span>  
  
-   <span data-ttu-id="191ec-131">JD Edwards OneWorld の大部分のマスタ レコードには、ルックアップ キーまたは代替キーという概念があります。</span><span class="sxs-lookup"><span data-stu-id="191ec-131">The majority of all master records in JD Edwards OneWorld have a concept of a lookup, or alternate key.</span></span> <span data-ttu-id="191ec-132">このキーを使用して、呼び出し元のシステムからのキー情報を格納できます。</span><span class="sxs-lookup"><span data-stu-id="191ec-132">This key can be used to store the key information from the calling system.</span></span> <span data-ttu-id="191ec-133">ビジネス関数は、JD Edwards OneWorld 側でルックアップを実行できます。</span><span class="sxs-lookup"><span data-stu-id="191ec-133">Business functions can perform the lookup on the JD Edwards OneWorld side.</span></span> <span data-ttu-id="191ec-134">顧客レコードを作成するためにビジネス関数にパラメータが渡されるとき、long キー値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="191ec-134">When parameters are passed to the business function to create a customer record, the long key value is set.</span></span>  
  
 <span data-ttu-id="191ec-135">これらの概念の詳細については、JD Edwards OneWorld ヘルプ システムの「Interoperability」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="191ec-135">For more information on these concepts, see the Interoperability topic in the JD Edwards OneWorld Help system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="191ec-136">参照</span><span class="sxs-lookup"><span data-stu-id="191ec-136">See Also</span></span>  
 [<span data-ttu-id="191ec-137">計画とアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="191ec-137">Planning and Architecture</span></span>](../core/planning-and-architecture17.md)