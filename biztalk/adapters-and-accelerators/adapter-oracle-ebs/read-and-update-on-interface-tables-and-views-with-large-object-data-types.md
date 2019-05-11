---
title: インターフェイス テーブル、インターフェイス ビュー、テーブル、および LOB データを格納するビューに対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f6e8db6-ba68-4e3f-84b2-1cc31ce89bcb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c134719da5d7cfb8f6997495a01eb529c5ec0241
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374822"
---
# <a name="operations-on-interface-tables-interface-views-tables-and-views-that-contain-lob-data"></a><span data-ttu-id="8c8e7-102">インターフェイス テーブル、インターフェイス ビュー、テーブル、および LOB データを格納するビューに対する操作</span><span class="sxs-lookup"><span data-stu-id="8c8e7-102">Operations on Interface Tables, Interface Views, Tables, and Views That Contain LOB Data</span></span>
<span data-ttu-id="8c8e7-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle のラージ オブジェクト (LOB) データ型のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] provides support for the Oracle large object (LOB) data types:</span></span>  
  
- <span data-ttu-id="8c8e7-104">バイナリ ラージ オブジェクト (BLOB)</span><span class="sxs-lookup"><span data-stu-id="8c8e7-104">Binary large object (BLOB)</span></span>  
  
- <span data-ttu-id="8c8e7-105">文字ラージ オブジェクト (CLOB)</span><span class="sxs-lookup"><span data-stu-id="8c8e7-105">Character large object (CLOB)</span></span>  
  
- <span data-ttu-id="8c8e7-106">各国語文字ラージ オブジェクト (NCLOB)</span><span class="sxs-lookup"><span data-stu-id="8c8e7-106">National character large object (NCLOB)</span></span>  
  
- <span data-ttu-id="8c8e7-107">バイナリ ファイル (BFILE)。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-107">Binary file (BFILE).</span></span> <span data-ttu-id="8c8e7-108">詳細については、次を参照してください。[テーブルを含む BFILE データ型に対する演算](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-108">For more information, see [Operations on Tables That Contain BFILE Data Types](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span></span>  
  
  <span data-ttu-id="8c8e7-109">基になる Oracle データベースで LOB データ型を使用して、大量のデータを格納する最大 4 ギガバイト (GB)。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-109">In the underlying Oracle database, LOB data types are used to store large amounts of data, up to 4 gigabytes (GB).</span></span> <span data-ttu-id="8c8e7-110">BFILE データ型を除くは、LOB データ型は、入力と出力のストリーミングの両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-110">Except for the BFILE data type, LOB data types support both input and output streaming.</span></span>  

## <a name="operations-for-tables-and-views"></a><span data-ttu-id="8c8e7-111">テーブルおよびビューの操作</span><span class="sxs-lookup"><span data-stu-id="8c8e7-111">Operations for tables and views</span></span>  
 <span data-ttu-id="8c8e7-112">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サーフェスのインターフェイス テーブル、インターフェイス ビュー、テーブル、および LOB 列を含むビューの次の操作。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-112">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] surfaces the following operations for interface tables, interface views, tables and views that contain LOB columns:</span></span>  
  
- <span data-ttu-id="8c8e7-113">**Read_\<LOBColName\>**:`Read_<LOBColName>`インターフェイス テーブル、インターフェイス ビュー、テーブルおよび BLOB、CLOB、NCLOB、BFILE の列を含むビューの操作が表示される場所\<LOBColName\>か、BLOB、CLOB、NCLOB、BFILE、型の列の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-113">**Read_\<LOBColName\>**: The `Read_<LOBColName>` operation is surfaced for interface tables, interface views, tables and views that contain BLOB, CLOB, NCLOB, and BFILE columns, where \<LOBColName\> is the name of the column of type BLOB, CLOB, NCLOB or BFILE.</span></span> <span data-ttu-id="8c8e7-114">による、Read_\<LOBColName\>操作、アダプター クライアントはデータ ストリームとしての LOB 列の値を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-114">By using the Read_\<LOBColName\> operation, adapter clients can read values in an LOB column as a data stream.</span></span> <span data-ttu-id="8c8e7-115">この操作は、フィルター文字列をパラメーターとして受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-115">This operation takes a filter string as parameter.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="8c8e7-116">`Read_<LOBColName>`操作は、WCF サービス モデル内の LOB データの入力ストリームをサポートするために設計されています。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-116">The `Read_<LOBColName>` operation is designed to support input streaming of LOB data in the WCF service model.</span></span> <span data-ttu-id="8c8e7-117">WCF チャネル モデルから LOB データを読み取るテーブルの選択操作を使用する必要がありますまたは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-117">You should use a table Select operation to read LOB data from a WCF channel model or [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
- <span data-ttu-id="8c8e7-118">**Update_\<LOBColName\>**:`Update_<LOBColName>`インターフェイス テーブルとのみ列を含む BLOB、CLOB、NCLOB、テーブルの操作が表示される場所\<LOBColName\>型の列の名前を指定し、BLOB、CLOB、NCLOB します。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-118">**Update_\<LOBColName\>**: The `Update_<LOBColName>` operation is surfaced for interface tables and tables only that contain BLOB, CLOB, and NCLOB columns, where \<LOBColName\> is the name of the column of type BLOB, CLOB, and NCLOB.</span></span> <span data-ttu-id="8c8e7-119">による、Update_\<LOBColName\>操作、アダプター クライアントは、LOB の列の値を更新できます。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-119">By using the Update_\<LOBColName\> operation, adapter clients can update values in an LOB column.</span></span> <span data-ttu-id="8c8e7-120">BLOB データの種類の CLOB、NCLOB データ型で、この操作は、パラメーターとして文字列のフィルターは、この操作は、パラメーターとして base64binary でエンコードされたデータを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-120">For the BLOB data type, this operation takes base64binary encoded data as the parameter, whereas for the CLOB and NCLOB data types, this operation takes a string filter as the parameter.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="8c8e7-121">`Update_<LOBColName>`操作。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-121">The `Update_<LOBColName>` operation:</span></span>  
  > 
  > - <span data-ttu-id="8c8e7-122">BFILE データ型のサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-122">Is not supported for the BFILE data type.</span></span> <span data-ttu-id="8c8e7-123">アダプター クライアントは、更新操作を使用してもできます。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-123">Adapter clients can alternatively use the Update operation.</span></span> <span data-ttu-id="8c8e7-124">詳細については、次を参照してください。[テーブルを含む BFILE データ型に対する演算](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-124">For more information, see [Operations on Tables That Contain BFILE Data Types](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span></span>  
  >   -   <span data-ttu-id="8c8e7-125">公開されませんビューとビューのインターフェイスします。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-125">Is not exposed for interface views and views.</span></span>  
  >   -   <span data-ttu-id="8c8e7-126">トランザクションの一部として実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-126">Must be performed as part of a transaction.</span></span> <span data-ttu-id="8c8e7-127">これは、確実に、 **UseAmbientTransaction**に設定するプロパティをバインドする必要があります**True**します。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-127">To ensure this, the **UseAmbientTransaction** binding property must be set to **True**.</span></span> <span data-ttu-id="8c8e7-128">については、 **UseAmbientTransaction**プロパティ、バインドを参照してください[BizTalk Adapter for Oracle E-business Suite バインド プロパティの Rad](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-128">For information about the **UseAmbientTransaction** binding property, see [Rad about the  BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8c8e7-129">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サーフェスを`Read_<LOBColName>`と`Update_<LOBColName>`テーブル内の各 LOB 列を操作します。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-129">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] surfaces a `Read_<LOBColName>` and an `Update_<LOBColName>` operation for each LOB column in a table.</span></span> <span data-ttu-id="8c8e7-130">そのため、(LOBCol1 および LOBCol2) テーブルに 2 つの LOB 列がある場合がある 2 つ`Read_<LOBColName>`操作 (Read_LOBCol1 および Read_LOBCol2) と 2 つの`Update_<LOBColName>`操作 (Update_LOBCol1 および Update_LOBCol2)。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-130">So, if there are two LOB columns in a table (LOBCol1 and LOBCol2), you have two `Read_<LOBColName>` operations (Read_LOBCol1 and Read_LOBCol2) and two `Update_<LOBColName>` operations (Update_LOBCol1 and Update_LOBCol2).</span></span>  
  
## <a name="more-good-info"></a><span data-ttu-id="8c8e7-131">詳細な情報</span><span class="sxs-lookup"><span data-stu-id="8c8e7-131">More good info</span></span>  
  
- <span data-ttu-id="8c8e7-132">呼び出す、`Read_<LOBColName>`と`Update_<LOBColName>`Oracle E-business Suite を使用して基になるデータベースのテーブルに対する操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[大規模なデータ型を使用して BizTalk Server でのテーブルでの操作を実行](../../adapters-and-accelerators/adapter-sql/run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-132">Invoking the `Read_<LOBColName>` and `Update_<LOBColName>` operations on a table in the underlying database in Oracle E-Business Suite using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Run Operations on Tables with Large Data Types Using BizTalk Server](../../adapters-and-accelerators/adapter-sql/run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter.md).</span></span>  
  
- <span data-ttu-id="8c8e7-133">メッセージの構造体とを実行するための SOAP アクションの`Read_<LOBColName>`と`Update_<LOBColName>`操作で、[特殊な LOB 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-special-lob-operations1.md)します。</span><span class="sxs-lookup"><span data-stu-id="8c8e7-133">Message structure and SOAP actions for performing `Read_<LOBColName>` and `Update_<LOBColName>` operations, see [Message Schemas for Special LOB Operations](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-special-lob-operations1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c8e7-134">参照</span><span class="sxs-lookup"><span data-stu-id="8c8e7-134">See Also</span></span>  
 <span data-ttu-id="8c8e7-135">[どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="8c8e7-135">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>