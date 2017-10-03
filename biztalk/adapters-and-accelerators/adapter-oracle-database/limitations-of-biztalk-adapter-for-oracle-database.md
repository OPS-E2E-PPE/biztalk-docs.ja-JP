---
title: "Oracle Database の BizTalk アダプターの制限事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: adapter, limitations of
ms.assetid: eab4ddea-f986-43c2-82bb-b9fe37961a5b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd6cfea523333752c0ee18fefbc6a1848057fe36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="limitations-of-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="9c642-102">Oracle Database の BizTalk アダプターの制限事項</span><span class="sxs-lookup"><span data-stu-id="9c642-102">Limitations of BizTalk Adapter for Oracle Database</span></span>
## <a name="general"></a><span data-ttu-id="9c642-103">全般</span><span class="sxs-lookup"><span data-stu-id="9c642-103">General</span></span>  
 <span data-ttu-id="9c642-104">次はの既知の制限、 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9c642-104">The following are known limitations for the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:</span></span>  
  
-   <span data-ttu-id="9c642-105">いくつかの例外がなければ、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプターの以前のリリースと互換性ができます。</span><span class="sxs-lookup"><span data-stu-id="9c642-105">Barring some exceptions, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] is compatible with the previous release of the adapters.</span></span> <span data-ttu-id="9c642-106">前回のリリースから発生した変更の一覧、次を参照してください。 [BizTalk adapter for Oracle データベースの主な特徴](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="9c642-106">For a list of changes that has happened since the last release, see [Key Features in BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md).</span></span>  
  
-   <span data-ttu-id="9c642-107">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] XML 型をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9c642-107">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support XML Types.</span></span>  
  
-   <span data-ttu-id="9c642-108">SQLEXECUTE 操作は、外の値を返しませんまたはプロシージャ、関数、またはパッケージに IN OUT パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="9c642-108">The SQLEXECUTE operation does not return values for OUT or IN OUT parameters to procedures, functions, or packages.</span></span> <span data-ttu-id="9c642-109">このため、呼び出す必要がありますプロシージャ、関数、およびパッケージ専用の操作を使用している、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]これら Oracle の成果物用に公開します。</span><span class="sxs-lookup"><span data-stu-id="9c642-109">For this reason, you must invoke procedures, functions, and packages by using the dedicated operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes for these Oracle artifacts.</span></span>  
  
-   <span data-ttu-id="9c642-110">プログラミングでは、プロキシを使用して Oracle データベースからデータを取得するときに、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] 65536 以上のノードを持つ XML メッセージを逆シリアル化ではありません。</span><span class="sxs-lookup"><span data-stu-id="9c642-110">When retrieving data from the Oracle database using proxy programming, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not deserialize XML messages that have more than 65536 nodes.</span></span> <span data-ttu-id="9c642-111">応答メッセージに 65536 のノード少ないがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9c642-111">Make sure the response message has nodes less than or equal to 65536.</span></span> <span data-ttu-id="9c642-112">この制限は、アプリケーションの app.config ファイルを変更することで回避できます。</span><span class="sxs-lookup"><span data-stu-id="9c642-112">You can work around this limitation by modifying the app.config file for your application.</span></span> <span data-ttu-id="9c642-113">手順については、次を参照してください。 [Oracle データベース アダプターの運用上の問題のトラブルシューティングを行う](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="9c642-113">For instructions, see [Troubleshoot operational issues with the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md).</span></span>  
  
-   <span data-ttu-id="9c642-114">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]は入力文字列し、アダプターによって実行される、SQL コマンドを構築します。</span><span class="sxs-lookup"><span data-stu-id="9c642-114">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] takes input strings and constructs SQL commands that are then executed by the adapter.</span></span> <span data-ttu-id="9c642-115">ただし、入力文字列も実行を取得する他の SQL コマンドが含まれ、操作コントラクトを中断する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9c642-115">However, the input string might contain other SQL commands that also get executed and might break the operation contract.</span></span>  
  
     <span data-ttu-id="9c642-116">アダプターがストアド プロシージャへの入力の REF CURSOR を提供するシナリオを検討してください。</span><span class="sxs-lookup"><span data-stu-id="9c642-116">Consider a scenario where the adapter provides an input REF CURSOR to a stored procedure.</span></span> <span data-ttu-id="9c642-117">このようなシナリオでは、アダプター クライアント必要があります提供コマンドを実行すると、REF CURSOR を取得します。</span><span class="sxs-lookup"><span data-stu-id="9c642-117">In such a scenario, the adapter client must provide a command that, when executed, obtains the REF CURSOR.</span></span> <span data-ttu-id="9c642-118">アダプターは、ストアド プロシージャに REF カーソル上で渡します。</span><span class="sxs-lookup"><span data-stu-id="9c642-118">The adapter then passes on the REF CURSOR to the stored procedure.</span></span> <span data-ttu-id="9c642-119">ただし、REF CURSOR を取得するためのコマンドは、データベースにいくつか追加の変更を実行する場合、ストアド プロシージャを実行するため、操作コントラクトは解除されます。</span><span class="sxs-lookup"><span data-stu-id="9c642-119">However, if the command for obtaining the REF CURSOR performs some additional modifications to the database, the operation contract for executing the stored procedure is broken.</span></span>  
  
-   <span data-ttu-id="9c642-120">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]のみに最大 2 つのレベルの入れ子の UDT をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9c642-120">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports UDT nesting only up to two levels.</span></span>  
  
-   <span data-ttu-id="9c642-121">アダプターを使用するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF カスタムの資格情報の送信ポートが正しくない要求メッセージは処理されません。</span><span class="sxs-lookup"><span data-stu-id="9c642-121">When using the adapters with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], if the credentials on the WCF-custom send port are incorrect, the request messages are not processed.</span></span> <span data-ttu-id="9c642-122">正しい資格情報を指定すると、Oracle データベースにメッセージを送信し、応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="9c642-122">After you specify the correct credentials, the message is sent to the Oracle database and a response is received.</span></span> <span data-ttu-id="9c642-123">ただし、応答メッセージでは、出力ポートを使用できません。</span><span class="sxs-lookup"><span data-stu-id="9c642-123">However, the response message is not available to the out port.</span></span> <span data-ttu-id="9c642-124">このようなシナリオでは、ホスト インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c642-124">In such scenarios, you may need to restart the host instance.</span></span>  
  
-   <span data-ttu-id="9c642-125">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] (レコード型、テーブルの種類、UDT、および VARRAY) などの複合型の内部 BFILE データ型をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9c642-125">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support the BFILE data type inside complex types (such as RECORD type, TABLE type, UDT, and VARRAY).</span></span>  
  
-   <span data-ttu-id="9c642-126">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]循環参照が含まれるユーザー定義型 (Udt) をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9c642-126">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support User-Defined Types (UDTs) that have circular references.</span></span>  
  
-   <span data-ttu-id="9c642-127">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]のフィールドを含むサポート レコードいないは、レコード型の PL/SQL テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="9c642-127">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support records that contain fields of type PL/SQL tables of RECORD type.</span></span>  
  
-   <span data-ttu-id="9c642-128">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を NULL に VARRAY で最初の要素の値を設定するクライアントを有効にしません。</span><span class="sxs-lookup"><span data-stu-id="9c642-128">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not enable clients to set the value of the first element in a VARRAY to NULL.</span></span>  
  
-   <span data-ttu-id="9c642-129">PL/SQL テーブルを除く、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]はパッケージ内で定義されている Udt をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9c642-129">Except for PL/SQL tables, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support UDTs that are defined inside a package.</span></span>  
  
## <a name="limitations-due-to-odpnet"></a><span data-ttu-id="9c642-130">ODP.NET のための制限事項</span><span class="sxs-lookup"><span data-stu-id="9c642-130">Limitations due to ODP.NET</span></span>  
 <span data-ttu-id="9c642-131">次はの既知の制限、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ODP.NET の制限のため。</span><span class="sxs-lookup"><span data-stu-id="9c642-131">The following are known limitations for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] due to the limitation of ODP.NET:</span></span>  
  
-   <span data-ttu-id="9c642-132">Oracle データ型の 10 進値を受け取る、ODP.NET は例外をスローしません、入力値には、アルファベット文字が含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="9c642-132">For Oracle data types that take decimal values, ODP.NET does not throw an exception if the input value contains alphabetic characters.</span></span> <span data-ttu-id="9c642-133">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用 ODP.NET、Oracle データベース アダプターのインターフェイスをすぎる例外はスローされません、アルファベット文字を渡すときにします。</span><span class="sxs-lookup"><span data-stu-id="9c642-133">Because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses ODP.NET to interface with the Oracle database, the adapter too does not throw an exception when passing alphabetic characters.</span></span> <span data-ttu-id="9c642-134">例:</span><span class="sxs-lookup"><span data-stu-id="9c642-134">For example:</span></span>  
  
    -   <span data-ttu-id="9c642-135">挿入操作の値"54r"を渡すことは、例外はスローされません。代わりに「54」の値が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="9c642-135">Passing a value “54r” for an insert operation does not throw an exception; the value “54” is inserted instead.</span></span>  
  
    -   <span data-ttu-id="9c642-136">挿入操作の値"r54"を渡すことは、例外はスローされません。値「0」は、代わりに挿入されます。</span><span class="sxs-lookup"><span data-stu-id="9c642-136">Passing a value “r54” for an insert operation does not throw an exception; the value “0” is inserted instead.</span></span>  
  
-   <span data-ttu-id="9c642-137">制限のため、ODP.NET、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]厳密に型指定され、弱い型指定の REF カーソルを使用するオーバー ロードされたプロシージャの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9c642-137">Because of an ODP.NET limitation, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support the use of overloaded procedures using strongly-typed and weakly-typed REF CURSORS.</span></span> <span data-ttu-id="9c642-138">内部的には、アダプターは、REF CURSOR だけとして厳密に型指定され、弱い型指定の両方の REF CURSOR を扱います。</span><span class="sxs-lookup"><span data-stu-id="9c642-138">Internally, the adapter treats both the strongly-typed and weakly-typed REF CURSORS as just REF CURSORS.</span></span>  
  
-   <span data-ttu-id="9c642-139">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]数値フィールドをインデックス化されていない PL/SQL テーブルをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9c642-139">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support PL/SQL tables that are not indexed by a numeric field.</span></span>  
  
-   <span data-ttu-id="9c642-140">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]は含まれていない任意の要素の連想配列をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9c642-140">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support associative arrays that do not contain any element.</span></span>  
  
-   <span data-ttu-id="9c642-141">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]はローカル タイム ゾーンの属性 (TimeStampLTZ) を持つ TimeStamp データ型が含まれている Udt をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9c642-141">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support UDTs that contain the TimeStamp data type with local time zone attributes (TimeStampLTZ).</span></span>  
  
-   <span data-ttu-id="9c642-142">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Udt を含むをサポートしていない、"です"。</span><span class="sxs-lookup"><span data-stu-id="9c642-142">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support UDTs that contain a “.”</span></span> <span data-ttu-id="9c642-143">(期間)、名前にします。</span><span class="sxs-lookup"><span data-stu-id="9c642-143">(period) in their names.</span></span>  
  
-   <span data-ttu-id="9c642-144">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] IN OUT パラメーターとして BLOB、CLOB、および NCLOB データ型が含まれている Udt をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9c642-144">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support UDTs that contain BLOB, CLOB, and NCLOB data types as an IN OUT parameter.</span></span>  
  
-   <span data-ttu-id="9c642-145">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Varray の Varray の次の単純型をサポートしていません: BFILE、IntervalDS、IntervalYM、TimeStampLTZ、および TimeStampTZ です。</span><span class="sxs-lookup"><span data-stu-id="9c642-145">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support Varray of Varray of the following simple types: BFILE, IntervalDS, IntervalYM, TimeStampLTZ, and TimeStampTZ.</span></span>  
  
-   <span data-ttu-id="9c642-146">連想配列の制限、により PL/SQL テーブルまたはデータ型を次のいずれかが含まれるレコードの PL/SQL テーブルでサポートされていない、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9c642-146">Due to the limitation of associative arrays, PL/SQL tables or PL/SQL tables of records that contain any of the following data types are not supported in the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:</span></span>  
  
    -   <span data-ttu-id="9c642-147">BFILE</span><span class="sxs-lookup"><span data-stu-id="9c642-147">BFILE</span></span>  
  
    -   <span data-ttu-id="9c642-148">BLOB</span><span class="sxs-lookup"><span data-stu-id="9c642-148">BLOB</span></span>  
  
    -   <span data-ttu-id="9c642-149">CLOB</span><span class="sxs-lookup"><span data-stu-id="9c642-149">CLOB</span></span>  
  
    -   <span data-ttu-id="9c642-150">IntervalDS</span><span class="sxs-lookup"><span data-stu-id="9c642-150">IntervalDS</span></span>  
  
    -   <span data-ttu-id="9c642-151">IntervalYM</span><span class="sxs-lookup"><span data-stu-id="9c642-151">IntervalYM</span></span>  
  
    -   <span data-ttu-id="9c642-152">Long</span><span class="sxs-lookup"><span data-stu-id="9c642-152">Long</span></span>  
  
    -   <span data-ttu-id="9c642-153">NCLOB</span><span class="sxs-lookup"><span data-stu-id="9c642-153">NCLOB</span></span>  
  
    -   <span data-ttu-id="9c642-154">RowID</span><span class="sxs-lookup"><span data-stu-id="9c642-154">RowID</span></span>  
  
    -   <span data-ttu-id="9c642-155">TimeStamp</span><span class="sxs-lookup"><span data-stu-id="9c642-155">TimeStamp</span></span>  
  
    -   <span data-ttu-id="9c642-156">TimeStampLTZ</span><span class="sxs-lookup"><span data-stu-id="9c642-156">TimeStampLTZ</span></span>  
  
    -   <span data-ttu-id="9c642-157">TimeStampTZ</span><span class="sxs-lookup"><span data-stu-id="9c642-157">TimeStampTZ</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c642-158">参照</span><span class="sxs-lookup"><span data-stu-id="9c642-158">See Also</span></span>  
 [<span data-ttu-id="9c642-159">Oracle データベースの BizTalk アダプターを理解します。</span><span class="sxs-lookup"><span data-stu-id="9c642-159">Understand the BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)