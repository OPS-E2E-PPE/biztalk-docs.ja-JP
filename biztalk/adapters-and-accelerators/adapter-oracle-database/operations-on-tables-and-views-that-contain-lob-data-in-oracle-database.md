---
title: テーブルと Oracle データベースで LOB データを格納するビューに対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a35be7008c47e46ca65962d113c4604c1cfad42b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984299"
---
# <a name="operations-on-tables-and-views-that-contain-lob-data-in-oracle-database"></a><span data-ttu-id="ef539-102">テーブルと Oracle データベースで LOB データを格納するビューに対する操作</span><span class="sxs-lookup"><span data-stu-id="ef539-102">Operations on tables and views that contain LOB data in Oracle Database</span></span>
<span data-ttu-id="ef539-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle のラージ オブジェクト (LOB) データ型のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="ef539-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] provides support for the Oracle large object (LOB) data types:</span></span>  
  
- <span data-ttu-id="ef539-104">バイナリ ラージ オブジェクト (BLOB)</span><span class="sxs-lookup"><span data-stu-id="ef539-104">Binary large object (BLOB)</span></span>  
  
- <span data-ttu-id="ef539-105">文字ラージ オブジェクト (CLOB)</span><span class="sxs-lookup"><span data-stu-id="ef539-105">Character large object (CLOB)</span></span>  
  
- <span data-ttu-id="ef539-106">各国語文字ラージ オブジェクト (NCLOB)</span><span class="sxs-lookup"><span data-stu-id="ef539-106">National character large object (NCLOB)</span></span>  
  
- <span data-ttu-id="ef539-107">バイナリ ファイル (BFILE)。</span><span class="sxs-lookup"><span data-stu-id="ef539-107">Binary file (BFILE).</span></span> <span data-ttu-id="ef539-108">詳細については、[BFILE データ型を含むテーブルに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef539-108">For more information, see [Operations on Tables that contains BFILE Data Types](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span></span>  
  
  <span data-ttu-id="ef539-109">大量のデータを格納する Oracle データベースで LOB データ型の使用 (最大 4 GB)。</span><span class="sxs-lookup"><span data-stu-id="ef539-109">On the Oracle database, LOB data types are used to store large amounts of data (up to 4 GB).</span></span> <span data-ttu-id="ef539-110">LOB 型では、入力と出力のストリーミングの両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="ef539-110">LOB types support both input and output streaming.</span></span>  
  
  <span data-ttu-id="ef539-111">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェスのテーブルとビューの LOB 列が含まれているは、次の操作。</span><span class="sxs-lookup"><span data-stu-id="ef539-111">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces the following operations for tables and views that contain LOB columns:</span></span>  
  
- <span data-ttu-id="ef539-112">**ReadLOB**します。</span><span class="sxs-lookup"><span data-stu-id="ef539-112">**ReadLOB**.</span></span> <span data-ttu-id="ef539-113">テーブルおよび BLOB、CLOB、NCLOB、BFILE、列を含むビューの ReadLOB 操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef539-113">The ReadLOB operation is surfaced for tables and views that contain BLOB, CLOB, NCLOB, and BFILE columns.</span></span> <span data-ttu-id="ef539-114">ReadLOB オペレーションを使用してアダプターのクライアントは、データ ストリームとして LOB 列の値を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="ef539-114">By using the ReadLOB operation, adapter clients can read values in a LOB column as a data stream.</span></span> <span data-ttu-id="ef539-115">この操作は、LOB データ型の列名とフィルター文字列をパラメーターとして受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ef539-115">This operation takes the LOB data type column name and a filter string as parameters.</span></span> <span data-ttu-id="ef539-116">アダプター クライアントは、フィルター文字列が正確に 1 つの一致する行をフェッチすることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef539-116">Adapter clients must ensure that the filter string fetches exactly one matching row.</span></span> <span data-ttu-id="ef539-117">1 つ以上の一致する行がある場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]のみ (一致する) の最初の行の LOB 列が返されます。</span><span class="sxs-lookup"><span data-stu-id="ef539-117">If there is more than one matching row, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] only returns the LOB column for the first (matching) row.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="ef539-118">ReadLOB 操作は、WCF サービス モデル内の LOB データの入力ストリームをサポートするために設計されています。</span><span class="sxs-lookup"><span data-stu-id="ef539-118">The ReadLOB operation is designed to support input streaming of LOB data in the WCF service model.</span></span> <span data-ttu-id="ef539-119">WCF チャネル モデルから LOB データを読み取るテーブルの選択操作を使用する必要がありますまたは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。</span><span class="sxs-lookup"><span data-stu-id="ef539-119">You should use a table Select operation to read LOB data from a WCF Channel Model or [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span> <span data-ttu-id="ef539-120">ストリーミングの詳細については、[Oracle データベースで LOB データ型のストリーミング サポート](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef539-120">For more information about streaming, see [Streaming Support for LOB Data Types in Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md).</span></span>  
  
- <span data-ttu-id="ef539-121">**UpdateLOB**します。</span><span class="sxs-lookup"><span data-stu-id="ef539-121">**UpdateLOB**.</span></span> <span data-ttu-id="ef539-122">テーブルおよび BLOB、CLOB、NCLOB 列を含むビューの UpdateLOB 操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef539-122">The UpdateLOB operation is surfaced for tables and views that contain BLOB, CLOB, and NCLOB columns.</span></span> <span data-ttu-id="ef539-123">UpdateLOB オペレーションを使用してアダプター クライアントは、LOB 列の値を更新できます。</span><span class="sxs-lookup"><span data-stu-id="ef539-123">By using the UpdateLOB operation, adapter clients can update values in a LOB column.</span></span> <span data-ttu-id="ef539-124">この操作は LOB データ型の列名、フィルター文字列を受け取り、base64binary パラメーターとしてデータをエンコードします。</span><span class="sxs-lookup"><span data-stu-id="ef539-124">This operation takes the LOB data type column name, a filter string, and base64binary encoded data as parameters.</span></span> <span data-ttu-id="ef539-125">アダプター クライアントでは、フィルター文字列が 1 つだけ一致する行をフェッチを確認する必要があります。それ以外の場合、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] XmlReaderParsingException をスローします。</span><span class="sxs-lookup"><span data-stu-id="ef539-125">Adapter clients must ensure that the filter string fetches exactly one matching row; otherwise the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] throws an XmlReaderParsingException.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="ef539-126">UpdateLOB 操作:</span><span class="sxs-lookup"><span data-stu-id="ef539-126">The UpdateLOB operation:</span></span>  
  > 
  > - <span data-ttu-id="ef539-127">BFILE データ型のサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ef539-127">Is not supported for the BFILE data type.</span></span> <span data-ttu-id="ef539-128">アダプター クライアントは、更新操作を使用してもできます。</span><span class="sxs-lookup"><span data-stu-id="ef539-128">Adapter clients can alternatively use the Update operation.</span></span> <span data-ttu-id="ef539-129">詳細については、[BFILE データ型を含むテーブルに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef539-129">For more information, see [Operations on Tables that contains BFILE Data Types](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span></span>  
  >   -   <span data-ttu-id="ef539-130">トランザクションの一部として実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef539-130">Must be performed as part of a transaction.</span></span> <span data-ttu-id="ef539-131">これは、確実に、 **UseAmbientTransaction**に設定するプロパティをバインドする必要があります**True**します。</span><span class="sxs-lookup"><span data-stu-id="ef539-131">To ensure this, the **UseAmbientTransaction** binding property must be set to **True**.</span></span> <span data-ttu-id="ef539-132">については、 **UseAmbientTransaction**プロパティ、バインドを参照してください[for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="ef539-132">For information about the **UseAmbientTransaction** binding property, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef539-133">ReadLOB と UpdateLOB は、1 つのテーブル行の 1 つの LOB 列を操作します。</span><span class="sxs-lookup"><span data-stu-id="ef539-133">ReadLOB and UpdateLOB operate on a single LOB column in a single table row.</span></span> <span data-ttu-id="ef539-134">複数の行の LOB 列または、単一行内の複数の LOB 列を操作するには、ターゲット各行に含まれる場合は、各ターゲット列に対して ReadLOB または UpdateLOB を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef539-134">To operate on LOB columns in multiple rows or on multiple LOB columns within a single row, you must invoke ReadLOB or UpdateLOB for each target column within each target row.</span></span>  
  
 <span data-ttu-id="ef539-135">詳細については。</span><span class="sxs-lookup"><span data-stu-id="ef539-135">For more information about:</span></span>  
  
- <span data-ttu-id="ef539-136">Oracle データベース テーブルを使用して、UpdateLOB 操作を呼び出す[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[を使用して BizTalk Server で大規模なオブジェクトの種類のデータ テーブルで操作を実行する](https://msdn.microsoft.com/library/cc185405(v=bts.10).aspx)します。</span><span class="sxs-lookup"><span data-stu-id="ef539-136">Invoking the UpdateLOB operation on an Oracle database table using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Performing Operations on Tables with Large Object Types Data by Using BizTalk Server](https://msdn.microsoft.com/library/cc185405(v=bts.10).aspx).</span></span> <span data-ttu-id="ef539-137">(で LOB データ型を読み取るテーブルの選択操作を使用する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="ef539-137">(You should use a table Select operation to read LOB data types in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].)</span></span>  
  
- <span data-ttu-id="ef539-138">WCF サービス モデルを使用して Oracle データベース テーブルで ReadLOB と UpdateLOB の操作を呼び出すを参照してください[WCF サービス モデルを使用して、大きなオブジェクトの型を持つテーブルでの操作を実行](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md)します。</span><span class="sxs-lookup"><span data-stu-id="ef539-138">Invoking ReadLOB and UpdateLOB operations on an Oracle database table using WCF service model, see [Run Operations on Tables with Large Object Types by Using the WCF Service Model](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md).</span></span>  
  
- <span data-ttu-id="ef539-139">メッセージの構造と ReadLOB および UpdateLOB 操作を実行するための SOAP アクションを参照してください[特殊な LOB 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md)します。</span><span class="sxs-lookup"><span data-stu-id="ef539-139">Message structure and SOAP actions for performing ReadLOB and UpdateLOB operations, see [Message Schemas for Special LOB Operations](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef539-140">参照</span><span class="sxs-lookup"><span data-stu-id="ef539-140">See Also</span></span>  
 <span data-ttu-id="ef539-141">[どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="ef539-141">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)</span></span>