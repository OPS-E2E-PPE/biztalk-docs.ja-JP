---
title: "テーブルと Oracle データベースでの LOB データを含むビューでの操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data type
- binary file
- UpdateLOB
- ReadLOB
- LOB data types
- NCLOB
- large object
- binary large object
- CLOB
- national character large object
- BFILE
- BLOB
- character large object
ms.assetid: 25afd8c7-8ca3-4855-a231-2bec28c9a5cb
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba5e110af598ac75ca9a8b6e7ebf2e5e8acc7aee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-tables-and-views-that-contain-lob-data-in-oracle-database"></a><span data-ttu-id="bc293-102">テーブルと Oracle データベースでの LOB データを含むビューでの操作</span><span class="sxs-lookup"><span data-stu-id="bc293-102">Operations on tables and views that contain LOB data in Oracle Database</span></span>
<span data-ttu-id="bc293-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle ラージ オブジェクト (LOB) データ型のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="bc293-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] provides support for the Oracle large object (LOB) data types:</span></span>  
  
-   <span data-ttu-id="bc293-104">バイナリ ラージ オブジェクト (BLOB)</span><span class="sxs-lookup"><span data-stu-id="bc293-104">Binary large object (BLOB)</span></span>  
  
-   <span data-ttu-id="bc293-105">文字ラージ オブジェクト (CLOB)</span><span class="sxs-lookup"><span data-stu-id="bc293-105">Character large object (CLOB)</span></span>  
  
-   <span data-ttu-id="bc293-106">各国語文字ラージ オブジェクト (NCLOB)</span><span class="sxs-lookup"><span data-stu-id="bc293-106">National character large object (NCLOB)</span></span>  
  
-   <span data-ttu-id="bc293-107">バイナリ ファイル (BFILE)。</span><span class="sxs-lookup"><span data-stu-id="bc293-107">Binary file (BFILE).</span></span> <span data-ttu-id="bc293-108">詳細については、次を参照してください。 [BFILE データ型を含むテーブルでの操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)です。</span><span class="sxs-lookup"><span data-stu-id="bc293-108">For more information, see [Operations on Tables that contains BFILE Data Types](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span></span>  
  
 <span data-ttu-id="bc293-109">大量のデータを格納する Oracle データベースに LOB データ型の使用 (4 GB まで)。</span><span class="sxs-lookup"><span data-stu-id="bc293-109">On the Oracle database, LOB data types are used to store large amounts of data (up to 4 GB).</span></span> <span data-ttu-id="bc293-110">LOB 型では、入力と出力ストリームの両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="bc293-110">LOB types support both input and output streaming.</span></span>  
  
 <span data-ttu-id="bc293-111">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェスのテーブルと LOB 列を含むビューの次の操作。</span><span class="sxs-lookup"><span data-stu-id="bc293-111">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces the following operations for tables and views that contain LOB columns:</span></span>  
  
-   <span data-ttu-id="bc293-112">**ReadLOB**です。</span><span class="sxs-lookup"><span data-stu-id="bc293-112">**ReadLOB**.</span></span> <span data-ttu-id="bc293-113">ReadLOB 操作は、テーブルおよび BLOB、CLOB、NCLOB、BFILE、列を含むビューを確認できます。</span><span class="sxs-lookup"><span data-stu-id="bc293-113">The ReadLOB operation is surfaced for tables and views that contain BLOB, CLOB, NCLOB, and BFILE columns.</span></span> <span data-ttu-id="bc293-114">ReadLOB 操作を使用すると、アダプターのクライアントは、データ ストリームとしての LOB 列の値を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="bc293-114">By using the ReadLOB operation, adapter clients can read values in a LOB column as a data stream.</span></span> <span data-ttu-id="bc293-115">この操作は、LOB データ型の列名と、フィルター文字列をパラメーターとして受け取ります。</span><span class="sxs-lookup"><span data-stu-id="bc293-115">This operation takes the LOB data type column name and a filter string as parameters.</span></span> <span data-ttu-id="bc293-116">アダプターのクライアントでは、フィルター文字列が正確に 1 つの一致する行をフェッチすることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bc293-116">Adapter clients must ensure that the filter string fetches exactly one matching row.</span></span> <span data-ttu-id="bc293-117">1 つ以上の一致する行がある場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]のみ (照合) の最初の行の LOB 列が返されます。</span><span class="sxs-lookup"><span data-stu-id="bc293-117">If there is more than one matching row, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] only returns the LOB column for the first (matching) row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc293-118">ReadLOB 操作は、WCF サービス モデルでの LOB データの入力ストリーミングをサポートするために設計されています。</span><span class="sxs-lookup"><span data-stu-id="bc293-118">The ReadLOB operation is designed to support input streaming of LOB data in the WCF service model.</span></span> <span data-ttu-id="bc293-119">WCF チャネル モデルから LOB データを読み取るテーブルの選択操作を使用する必要がありますまたは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="bc293-119">You should use a table Select operation to read LOB data from a WCF Channel Model or [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span> <span data-ttu-id="bc293-120">ストリーミングの詳細については、次を参照してください。 [Oracle データベースでの LOB データ型のストリーミング サポート](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="bc293-120">For more information about streaming, see [Streaming Support for LOB Data Types in Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md).</span></span>  
  
-   <span data-ttu-id="bc293-121">**UpdateLOB**です。</span><span class="sxs-lookup"><span data-stu-id="bc293-121">**UpdateLOB**.</span></span> <span data-ttu-id="bc293-122">UpdateLOB 操作は、テーブルおよび BLOB、CLOB、NCLOB 列を格納するビューを確認できます。</span><span class="sxs-lookup"><span data-stu-id="bc293-122">The UpdateLOB operation is surfaced for tables and views that contain BLOB, CLOB, and NCLOB columns.</span></span> <span data-ttu-id="bc293-123">UpdateLOB 操作を使用すると、アダプターのクライアントは、LOB 列の値を更新できます。</span><span class="sxs-lookup"><span data-stu-id="bc293-123">By using the UpdateLOB operation, adapter clients can update values in a LOB column.</span></span> <span data-ttu-id="bc293-124">この操作が LOB データ型の列名、フィルター文字列を受け取り、base64binary がパラメーターとしてデータをエンコードします。</span><span class="sxs-lookup"><span data-stu-id="bc293-124">This operation takes the LOB data type column name, a filter string, and base64binary encoded data as parameters.</span></span> <span data-ttu-id="bc293-125">アダプターのクライアントのフィルター文字列が; 1 つだけの一致する行をフェッチすることが保証されている必要があります。それ以外の場合、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] XmlReaderParsingException をスローします。</span><span class="sxs-lookup"><span data-stu-id="bc293-125">Adapter clients must ensure that the filter string fetches exactly one matching row; otherwise the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] throws an XmlReaderParsingException.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc293-126">UpdateLOB 操作:</span><span class="sxs-lookup"><span data-stu-id="bc293-126">The UpdateLOB operation:</span></span>  
    >   
    >  -   <span data-ttu-id="bc293-127">BFILE データ型のサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bc293-127">Is not supported for the BFILE data type.</span></span> <span data-ttu-id="bc293-128">アダプターのクライアントは、更新操作を使用またはできます。</span><span class="sxs-lookup"><span data-stu-id="bc293-128">Adapter clients can alternatively use the Update operation.</span></span> <span data-ttu-id="bc293-129">詳細については、次を参照してください。 [BFILE データ型を含むテーブルでの操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)です。</span><span class="sxs-lookup"><span data-stu-id="bc293-129">For more information, see [Operations on Tables that contains BFILE Data Types](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span></span>  
    > -   <span data-ttu-id="bc293-130">トランザクションの一部として実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc293-130">Must be performed as part of a transaction.</span></span> <span data-ttu-id="bc293-131">これには、ことを確認する、 **UseAmbientTransaction** binding プロパティを設定する必要があります**True**です。</span><span class="sxs-lookup"><span data-stu-id="bc293-131">To ensure this, the **UseAmbientTransaction** binding property must be set to **True**.</span></span> <span data-ttu-id="bc293-132">については、 **UseAmbientTransaction**バインディング プロパティを参照してください[Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="bc293-132">For information about the **UseAmbientTransaction** binding property, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc293-133">ReadLOB と UpdateLOB は、1 つのテーブルの行に 1 つの LOB 列で機能します。</span><span class="sxs-lookup"><span data-stu-id="bc293-133">ReadLOB and UpdateLOB operate on a single LOB column in a single table row.</span></span> <span data-ttu-id="bc293-134">または、単一行内の複数の LOB 列上で複数の行の LOB 列を操作するをターゲットの各行に含まれる各ターゲット列に対して ReadLOB または UpdateLOB を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc293-134">To operate on LOB columns in multiple rows or on multiple LOB columns within a single row, you must invoke ReadLOB or UpdateLOB for each target column within each target row.</span></span>  
  
 <span data-ttu-id="bc293-135">詳細については。</span><span class="sxs-lookup"><span data-stu-id="bc293-135">For more information about:</span></span>  
  
-   <span data-ttu-id="bc293-136">Oracle データベース テーブルを使用して、UpdateLOB 操作を呼び出す[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[を使用して BizTalk Server で大規模なオブジェクト型のデータを持つテーブルでの操作の実行](https://msdn.microsoft.com/library/cc185405(v=bts.10).aspx)です。</span><span class="sxs-lookup"><span data-stu-id="bc293-136">Invoking the UpdateLOB operation on an Oracle database table using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Performing Operations on Tables with Large Object Types Data by Using BizTalk Server](https://msdn.microsoft.com/library/cc185405(v=bts.10).aspx).</span></span> <span data-ttu-id="bc293-137">(テーブルの選択操作の LOB データ型の読み取りに使用する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="bc293-137">(You should use a table Select operation to read LOB data types in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].)</span></span>  
  
-   <span data-ttu-id="bc293-138">WCF サービスのモデルを使用して Oracle データベース テーブルで ReadLOB と UpdateLOB の操作を呼び出すことを参照してください[WCF サービス モデルを使用して大規模なオブジェクトの種類を持つテーブルでの操作を実行](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md)です。</span><span class="sxs-lookup"><span data-stu-id="bc293-138">Invoking ReadLOB and UpdateLOB operations on an Oracle database table using WCF service model, see [Run Operations on Tables with Large Object Types by Using the WCF Service Model](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md).</span></span>  
  
-   <span data-ttu-id="bc293-139">メッセージの構造と ReadLOB および UpdateLOB 操作を実行するための SOAP アクションを参照してください[特別な LOB 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md)です。</span><span class="sxs-lookup"><span data-stu-id="bc293-139">Message structure and SOAP actions for performing ReadLOB and UpdateLOB operations, see [Message Schemas for Special LOB Operations](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc293-140">参照</span><span class="sxs-lookup"><span data-stu-id="bc293-140">See Also</span></span>  
 <span data-ttu-id="bc293-141">[どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="bc293-141">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)</span></span>