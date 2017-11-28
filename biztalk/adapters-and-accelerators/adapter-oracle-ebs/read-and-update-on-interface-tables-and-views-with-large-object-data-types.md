---
title: "インターフェイス テーブル、インターフェイス ビュー、テーブル、および LOB データを含むビューでの操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f6e8db6-ba68-4e3f-84b2-1cc31ce89bcb
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a0804aa58174912a29cec9039d55579e4e705a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-interface-tables-interface-views-tables-and-views-that-contain-lob-data"></a><span data-ttu-id="455f1-102">インターフェイス テーブル、インターフェイス ビュー、テーブル、および LOB データを含むビューでの操作</span><span class="sxs-lookup"><span data-stu-id="455f1-102">Operations on Interface Tables, Interface Views, Tables, and Views That Contain LOB Data</span></span>
<span data-ttu-id="455f1-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle ラージ オブジェクト (LOB) データ型のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="455f1-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] provides support for the Oracle large object (LOB) data types:</span></span>  
  
-   <span data-ttu-id="455f1-104">バイナリ ラージ オブジェクト (BLOB)</span><span class="sxs-lookup"><span data-stu-id="455f1-104">Binary large object (BLOB)</span></span>  
  
-   <span data-ttu-id="455f1-105">文字ラージ オブジェクト (CLOB)</span><span class="sxs-lookup"><span data-stu-id="455f1-105">Character large object (CLOB)</span></span>  
  
-   <span data-ttu-id="455f1-106">各国語文字ラージ オブジェクト (NCLOB)</span><span class="sxs-lookup"><span data-stu-id="455f1-106">National character large object (NCLOB)</span></span>  
  
-   <span data-ttu-id="455f1-107">バイナリ ファイル (BFILE)。</span><span class="sxs-lookup"><span data-stu-id="455f1-107">Binary file (BFILE).</span></span> <span data-ttu-id="455f1-108">詳細については、次を参照してください。[テーブルを含む BFILE データ型の演算](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)です。</span><span class="sxs-lookup"><span data-stu-id="455f1-108">For more information, see [Operations on Tables That Contain BFILE Data Types](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span></span>  
  
 <span data-ttu-id="455f1-109">基になる Oracle データベースで LOB データ型が大量のデータの格納に使用される最大 4 ギガバイト (GB)。</span><span class="sxs-lookup"><span data-stu-id="455f1-109">In the underlying Oracle database, LOB data types are used to store large amounts of data, up to 4 gigabytes (GB).</span></span> <span data-ttu-id="455f1-110">BFILE データ型を除くは、LOB データ型は、入力と出力ストリームの両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="455f1-110">Except for the BFILE data type, LOB data types support both input and output streaming.</span></span>  

## <a name="operations-for-tables-and-views"></a><span data-ttu-id="455f1-111">テーブルやビューの操作</span><span class="sxs-lookup"><span data-stu-id="455f1-111">Operations for tables and views</span></span>  
 <span data-ttu-id="455f1-112">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]インターフェイス テーブル、インターフェイス ビュー、テーブルやビューの LOB 列を含む次の操作を表示します。</span><span class="sxs-lookup"><span data-stu-id="455f1-112">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] surfaces the following operations for interface tables, interface views, tables and views that contain LOB columns:</span></span>  
  
-   <span data-ttu-id="455f1-113">**Read_\<LOBColName >**:`Read_<LOBColName>`インターフェイス テーブル、インターフェイス ビュー、テーブルおよび BLOB、CLOB、NCLOB、BFILE の列を含むビューの操作が表示される場所\<LOBColName > の名前を指定しますBLOB、CLOB、NCLOB または BFILE 型の列です。</span><span class="sxs-lookup"><span data-stu-id="455f1-113">**Read_\<LOBColName>**: The `Read_<LOBColName>` operation is surfaced for interface tables, interface views, tables and views that contain BLOB, CLOB, NCLOB, and BFILE columns, where \<LOBColName> is the name of the column of type BLOB, CLOB, NCLOB or BFILE.</span></span> <span data-ttu-id="455f1-114">による、Read_\<LOBColName > 操作、アダプターのクライアントはデータ ストリームとしての LOB 列の値を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="455f1-114">By using the Read_\<LOBColName> operation, adapter clients can read values in an LOB column as a data stream.</span></span> <span data-ttu-id="455f1-115">この操作は、フィルター文字列をパラメーターとして受け取ります。</span><span class="sxs-lookup"><span data-stu-id="455f1-115">This operation takes a filter string as parameter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="455f1-116">`Read_<LOBColName>`操作は、WCF サービス モデルでの LOB データの入力ストリーミングをサポートするために設計されています。</span><span class="sxs-lookup"><span data-stu-id="455f1-116">The `Read_<LOBColName>` operation is designed to support input streaming of LOB data in the WCF service model.</span></span> <span data-ttu-id="455f1-117">WCF チャネル モデルから LOB データを読み取るテーブルの選択操作を使用する必要がありますまたは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="455f1-117">You should use a table Select operation to read LOB data from a WCF channel model or [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
-   <span data-ttu-id="455f1-118">**Update_\<LOBColName >**:`Update_<LOBColName>`インターフェイス テーブルとのみ列を含む BLOB、CLOB、NCLOB、テーブルの操作が表示される場所\<LOBColName > BLOB、CLOB の型の列の名前を指定しますや nclob を使用します。</span><span class="sxs-lookup"><span data-stu-id="455f1-118">**Update_\<LOBColName>**: The `Update_<LOBColName>` operation is surfaced for interface tables and tables only that contain BLOB, CLOB, and NCLOB columns, where \<LOBColName> is the name of the column of type BLOB, CLOB, and NCLOB.</span></span> <span data-ttu-id="455f1-119">Update_ を使用して、\<LOBColName > 操作、アダプターのクライアントは、LOB の列の値を更新できます。</span><span class="sxs-lookup"><span data-stu-id="455f1-119">By using the Update_\<LOBColName> operation, adapter clients can update values in an LOB column.</span></span> <span data-ttu-id="455f1-120">BLOB データ型のこの操作では CLOB や NCLOB データ型の場合は、この操作は、パラメーターとして文字列のフィルターをかかります。 一方、base64binary でエンコードされたデータをパラメーターとして受け取ります。</span><span class="sxs-lookup"><span data-stu-id="455f1-120">For the BLOB data type, this operation takes base64binary encoded data as the parameter, whereas for the CLOB and NCLOB data types, this operation takes a string filter as the parameter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="455f1-121">`Update_<LOBColName>`操作。</span><span class="sxs-lookup"><span data-stu-id="455f1-121">The `Update_<LOBColName>` operation:</span></span>  
    >   
    >  -   <span data-ttu-id="455f1-122">BFILE データ型のサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="455f1-122">Is not supported for the BFILE data type.</span></span> <span data-ttu-id="455f1-123">アダプターのクライアントは、更新操作を使用またはできます。</span><span class="sxs-lookup"><span data-stu-id="455f1-123">Adapter clients can alternatively use the Update operation.</span></span> <span data-ttu-id="455f1-124">詳細については、次を参照してください。[テーブルを含む BFILE データ型の演算](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)です。</span><span class="sxs-lookup"><span data-stu-id="455f1-124">For more information, see [Operations on Tables That Contain BFILE Data Types](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span></span>  
    > -   <span data-ttu-id="455f1-125">公開されませんビューとビューのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="455f1-125">Is not exposed for interface views and views.</span></span>  
    > -   <span data-ttu-id="455f1-126">トランザクションの一部として実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="455f1-126">Must be performed as part of a transaction.</span></span> <span data-ttu-id="455f1-127">これには、ことを確認する、 **UseAmbientTransaction** binding プロパティを設定する必要があります**True**です。</span><span class="sxs-lookup"><span data-stu-id="455f1-127">To ensure this, the **UseAmbientTransaction** binding property must be set to **True**.</span></span> <span data-ttu-id="455f1-128">については、 **UseAmbientTransaction**バインディング プロパティを参照してください[BizTalk Adapter for Oracle E-business Suite バインド プロパティに関する Rad](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="455f1-128">For information about the **UseAmbientTransaction** binding property, see [Rad about the  BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="455f1-129">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サーフェス、`Read_<LOBColName>`と`Update_<LOBColName>`テーブル内の各 LOB 列を操作します。</span><span class="sxs-lookup"><span data-stu-id="455f1-129">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] surfaces a `Read_<LOBColName>` and an `Update_<LOBColName>` operation for each LOB column in a table.</span></span> <span data-ttu-id="455f1-130">そのため、(LOBCol1 および LOBCol2) テーブルに 2 つの LOB 列がある場合がある 2 つ`Read_<LOBColName>`操作 (Read_LOBCol1 および Read_LOBCol2) と 2 つの`Update_<LOBColName>`操作 (Update_LOBCol1 および Update_LOBCol2)。</span><span class="sxs-lookup"><span data-stu-id="455f1-130">So, if there are two LOB columns in a table (LOBCol1 and LOBCol2), you have two `Read_<LOBColName>` operations (Read_LOBCol1 and Read_LOBCol2) and two `Update_<LOBColName>` operations (Update_LOBCol1 and Update_LOBCol2).</span></span>  
  
## <a name="more-good-info"></a><span data-ttu-id="455f1-131">詳細な情報</span><span class="sxs-lookup"><span data-stu-id="455f1-131">More good info</span></span>  
  
-   <span data-ttu-id="455f1-132">呼び出す、`Read_<LOBColName>`と`Update_<LOBColName>`Oracle E-business Suite を使用して基になるデータベース内のテーブルに対する操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[大規模なデータ型を使用して BizTalk Server を持つテーブルでの操作を実行](../../adapters-and-accelerators/adapter-sql/run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="455f1-132">Invoking the `Read_<LOBColName>` and `Update_<LOBColName>` operations on a table in the underlying database in Oracle E-Business Suite using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Run Operations on Tables with Large Data Types Using BizTalk Server](../../adapters-and-accelerators/adapter-sql/run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter.md).</span></span>  
  
-   <span data-ttu-id="455f1-133">メッセージの構造とを実行するための SOAP アクションの`Read_<LOBColName>`と`Update_<LOBColName>`操作で、[特別な LOB 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-special-lob-operations1.md)です。</span><span class="sxs-lookup"><span data-stu-id="455f1-133">Message structure and SOAP actions for performing `Read_<LOBColName>` and `Update_<LOBColName>` operations, see [Message Schemas for Special LOB Operations](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-special-lob-operations1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="455f1-134">参照</span><span class="sxs-lookup"><span data-stu-id="455f1-134">See Also</span></span>  
 <span data-ttu-id="455f1-135">[どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="455f1-135">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>