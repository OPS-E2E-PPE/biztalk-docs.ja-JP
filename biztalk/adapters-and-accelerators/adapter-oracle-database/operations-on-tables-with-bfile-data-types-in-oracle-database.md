---
title: Oracle データベースで BFILE データ型を持つテーブルに対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, on tables with BFILE data types
- BFILE data type
- BFILE
ms.assetid: 7937564e-4423-459f-9824-6a27113ebfb3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab9885497468f91b309eb51ac0abbf4c0807ca76
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998259"
---
# <a name="operations-on-tables-with-bfile-data-types-in-oracle-database"></a><span data-ttu-id="5ceea-102">Oracle データベースで BFILE データ型を持つテーブルに対する操作</span><span class="sxs-lookup"><span data-stu-id="5ceea-102">Operations on Tables With BFILE Data Types in Oracle Database</span></span>
<span data-ttu-id="5ceea-103">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] BFILE データ型をテーブルとストアド プロシージャでサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5ceea-103">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports the BFILE data type in tables and stored procedures.</span></span> <span data-ttu-id="5ceea-104">次の表は、実行された操作に基づいて、アダプターによって公開される BFILE データ型と LOB 成果物 (テーブルまたはプロシージャ) アクセスをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="5ceea-104">The following table summarizes the BFILE data type exposed by the adapter based on the operation performed and the LOB artifact (table/procedure) accessed:</span></span>  
  
|<span data-ttu-id="5ceea-105">成果物</span><span class="sxs-lookup"><span data-stu-id="5ceea-105">Artifact</span></span>|<span data-ttu-id="5ceea-106">演算</span><span class="sxs-lookup"><span data-stu-id="5ceea-106">Operation</span></span>|<span data-ttu-id="5ceea-107">BFILE col/パラメーターの公開されるデータ型</span><span class="sxs-lookup"><span data-stu-id="5ceea-107">Data type exposed for BFILE col/param</span></span>|<span data-ttu-id="5ceea-108">コメント</span><span class="sxs-lookup"><span data-stu-id="5ceea-108">Comments</span></span>|  
|--------------|---------------|--------------------------------------------|--------------|  
|<span data-ttu-id="5ceea-109">TABLE</span><span class="sxs-lookup"><span data-stu-id="5ceea-109">TABLE</span></span>|<span data-ttu-id="5ceea-110">INSERT</span><span class="sxs-lookup"><span data-stu-id="5ceea-110">INSERT</span></span>|<span data-ttu-id="5ceea-111">String</span><span class="sxs-lookup"><span data-stu-id="5ceea-111">String</span></span>|<span data-ttu-id="5ceea-112">BFILE 列に挿入するファイルに論理 Oracle ディレクトリ パスを表します</span><span class="sxs-lookup"><span data-stu-id="5ceea-112">Represents the logical Oracle directory path to the file to be inserted into the BFILE column</span></span><br /><br /> <span data-ttu-id="5ceea-113">例:</span><span class="sxs-lookup"><span data-stu-id="5ceea-113">E.g.</span></span> <span data-ttu-id="5ceea-114">Oracle での論理ディレクトリの MYDIR の MYDIR/screen.jpg</span><span class="sxs-lookup"><span data-stu-id="5ceea-114">MYDIR/screen.jpg where MYDIR is a logical directory in Oracle</span></span>|  
|<span data-ttu-id="5ceea-115">TABLE</span><span class="sxs-lookup"><span data-stu-id="5ceea-115">TABLE</span></span>|<span data-ttu-id="5ceea-116">UPDATE</span><span class="sxs-lookup"><span data-stu-id="5ceea-116">UPDATE</span></span>|<span data-ttu-id="5ceea-117">String</span><span class="sxs-lookup"><span data-stu-id="5ceea-117">String</span></span>|<span data-ttu-id="5ceea-118">BFILE 列を更新するファイルに論理 Oracle ディレクトリ パスを表します</span><span class="sxs-lookup"><span data-stu-id="5ceea-118">Represents the logical Oracle directory path to the file to be updated into the BFILE column</span></span>|  
|<span data-ttu-id="5ceea-119">TABLE</span><span class="sxs-lookup"><span data-stu-id="5ceea-119">TABLE</span></span>|<span data-ttu-id="5ceea-120">SELECT</span><span class="sxs-lookup"><span data-stu-id="5ceea-120">SELECT</span></span>|<span data-ttu-id="5ceea-121">byte[]</span><span class="sxs-lookup"><span data-stu-id="5ceea-121">byte[]</span></span>|<span data-ttu-id="5ceea-122">BFILE を構成するバイナリ データを表します</span><span class="sxs-lookup"><span data-stu-id="5ceea-122">Represents the binary data constituting the BFILE</span></span>|  
|<span data-ttu-id="5ceea-123">ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="5ceea-123">STORED PROC</span></span>|<span data-ttu-id="5ceea-124">PARAM で</span><span class="sxs-lookup"><span data-stu-id="5ceea-124">IN PARAM</span></span>|<span data-ttu-id="5ceea-125">String</span><span class="sxs-lookup"><span data-stu-id="5ceea-125">String</span></span>|<span data-ttu-id="5ceea-126">BFILE 列に挿入するファイルに論理 Oracle ディレクトリ パスを表します</span><span class="sxs-lookup"><span data-stu-id="5ceea-126">Represents the logical Oracle directory path to the file to be inserted into the BFILE column</span></span><br /><br /> <span data-ttu-id="5ceea-127">例:</span><span class="sxs-lookup"><span data-stu-id="5ceea-127">E.g.</span></span> <span data-ttu-id="5ceea-128">Oracle での論理ディレクトリの MYDIR の MYDIR/screen.jpg</span><span class="sxs-lookup"><span data-stu-id="5ceea-128">MYDIR/screen.jpg where MYDIR is a logical directory in Oracle</span></span>|  
|<span data-ttu-id="5ceea-129">ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="5ceea-129">STORED PROC</span></span>|<span data-ttu-id="5ceea-130">OUT パラメーター</span><span class="sxs-lookup"><span data-stu-id="5ceea-130">OUT PARAM</span></span>|<span data-ttu-id="5ceea-131">String</span><span class="sxs-lookup"><span data-stu-id="5ceea-131">String</span></span>|<span data-ttu-id="5ceea-132">BFILE 列に挿入するファイルに論理 Oracle ディレクトリ パスを表します</span><span class="sxs-lookup"><span data-stu-id="5ceea-132">Represents the logical Oracle directory path to the file to be inserted into the BFILE column</span></span><br /><br /> <span data-ttu-id="5ceea-133">例:</span><span class="sxs-lookup"><span data-stu-id="5ceea-133">E.g.</span></span> <span data-ttu-id="5ceea-134">Oracle での論理ディレクトリの MYDIR の MYDIR/screen.jpg</span><span class="sxs-lookup"><span data-stu-id="5ceea-134">MYDIR/screen.jpg where MYDIR is a logical directory in Oracle</span></span>|  
|<span data-ttu-id="5ceea-135">ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="5ceea-135">STORED PROC</span></span>|<span data-ttu-id="5ceea-136">INOUT パラメーター</span><span class="sxs-lookup"><span data-stu-id="5ceea-136">INOUT PARAM</span></span>|<span data-ttu-id="5ceea-137">サポートされていません</span><span class="sxs-lookup"><span data-stu-id="5ceea-137">Not Supported</span></span>|-|  
  
 <span data-ttu-id="5ceea-138">特別な操作 ReadLOB は BFILE データ型を持つテーブルでもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5ceea-138">The special operation ReadLOB is also supported on tables with BFILE data type.</span></span> <span data-ttu-id="5ceea-139">UpdateLOB 操作がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5ceea-139">The UpdateLOB operation is not supported.</span></span> <span data-ttu-id="5ceea-140">アダプター クライアントは、更新操作を代わりに使用できます。</span><span class="sxs-lookup"><span data-stu-id="5ceea-140">Adapter clients can alternately use the UPDATE operation.</span></span>  
  
 <span data-ttu-id="5ceea-141">詳細については。</span><span class="sxs-lookup"><span data-stu-id="5ceea-141">For more information about:</span></span>  
  
- <span data-ttu-id="5ceea-142">使用して BFILE データ型を含むテーブルでの操作を実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[BizTalk Server を使用して Oracle データベースで BFILE データ型を持つテーブルに対する操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-bfile-data-types-in-oracle-db-using-biztalk.md)します。</span><span class="sxs-lookup"><span data-stu-id="5ceea-142">Performing operations on tables containing BFILE data types by using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Run operations on Tables with BFILE Data Types in Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-bfile-data-types-in-oracle-db-using-biztalk.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ceea-143">参照</span><span class="sxs-lookup"><span data-stu-id="5ceea-143">See Also</span></span>  
 <span data-ttu-id="5ceea-144">[どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="5ceea-144">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>