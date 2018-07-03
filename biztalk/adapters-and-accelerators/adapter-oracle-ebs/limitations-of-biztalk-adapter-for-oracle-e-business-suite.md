---
title: BizTalk adapter for Oracle E-business Suite の制限事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 149cee03-43cd-4cb3-a937-6565f5e96ce5
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6de75a2955632f4f8e0daae2a2035e90f1f2fca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988395"
---
# <a name="limitations-of-biztalk-adapter-for-oracle-e-business-suite"></a><span data-ttu-id="3225e-102">BizTalk adapter for Oracle E-business Suite の制限事項</span><span class="sxs-lookup"><span data-stu-id="3225e-102">Limitations of BizTalk Adapter for Oracle E-Business Suite</span></span>
## <a name="general-limitations"></a><span data-ttu-id="3225e-103">一般的な制限事項</span><span class="sxs-lookup"><span data-stu-id="3225e-103">General Limitations</span></span>  
 <span data-ttu-id="3225e-104">次の制限事項を呼びます[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="3225e-104">The following are known limitations for [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:</span></span>  
  
- <span data-ttu-id="3225e-105">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] XML ゲートウェイ、アドバンスド キュー、およびビジネス イベントはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="3225e-105">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support XML Gateway, Advanced Queuing, and Business Events.</span></span>  
  
   <span data-ttu-id="3225e-106">ただし、次のように、ビジネス イベントの制限を回避取得できます。</span><span class="sxs-lookup"><span data-stu-id="3225e-106">However, you can get around the Business Events limitation in the following way:</span></span>  
  
  1. <span data-ttu-id="3225e-107">Oracle のビジネス イベント システムでは、ビジネス イベントが発生したときに、カスタム PL/SQL プロシージャを呼び出すためのサブスクリプションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3225e-107">In Oracle Business Events System, create a subscription to invoke a custom PL/SQL procedure when a business event occurs.</span></span>  
  
  2. <span data-ttu-id="3225e-108">ビジネス イベントを受け取るカスタム PL/SQL プロシージャを記述します。</span><span class="sxs-lookup"><span data-stu-id="3225e-108">Write a custom PL/SQL procedure that receives the business event.</span></span>  
  
  3. <span data-ttu-id="3225e-109">テーブルに結果のデータ (イベントとイベント ペイロード) を格納するのにには、カスタムの PL/SQL 手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="3225e-109">Use the custom PL/SQL procedure to store the resultant data (event and event payload) in a table.</span></span>  
  
  4. <span data-ttu-id="3225e-110">使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ポーリングまたはテーブルから通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="3225e-110">Use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll or receive notifications from the table.</span></span>  
  
- <span data-ttu-id="3225e-111">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] XML 型をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3225e-111">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support XML Types.</span></span>  
  
- <span data-ttu-id="3225e-112">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Null の VARRAY で最初の要素の値を設定するクライアントを有効にしません。</span><span class="sxs-lookup"><span data-stu-id="3225e-112">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not enable clients to set the value of the first element in a VARRAY to NULL.</span></span>  
  
- <span data-ttu-id="3225e-113">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]のフィールドを含むレコードのないサポートは、レコードの種類の PL/SQL テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="3225e-113">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support records that contain fields of type PL/SQL tables of RECORD type.</span></span>  
  
- <span data-ttu-id="3225e-114">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]は循環参照があるユーザー定義型 (Udt) をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3225e-114">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support User-Defined Types (UDTs) that have circular references.</span></span>  
  
- <span data-ttu-id="3225e-115">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] (レコードの種類、テーブル型、UDT、および VARRAY) などの複合型、BFILE データ型をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3225e-115">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support the BFILE data type inside complex types (such as RECORD type, TABLE type, UDT, and VARRAY).</span></span>  
  
- <span data-ttu-id="3225e-116">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]のみに最大 2 つのレベルの入れ子の UDT をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3225e-116">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports UDT nesting only up to two levels.</span></span>  
  
- <span data-ttu-id="3225e-117">PL/SQL のテーブルを除く、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]はパッケージ内で定義されている Udt をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3225e-117">Except for PL/SQL tables, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that are defined inside a package.</span></span>  
  
- <span data-ttu-id="3225e-118">BizTalk Server でアダプターを使用する場合は、WCF カスタム資格情報の送信ポートが正しくない、要求メッセージは処理されません。</span><span class="sxs-lookup"><span data-stu-id="3225e-118">When using the adapters with BizTalk Server, if the credentials on the WCF-custom send port are incorrect, the request messages are not processed.</span></span> <span data-ttu-id="3225e-119">正しい資格情報を指定すると、Oracle E-business Suite にメッセージを送信し、応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="3225e-119">After you specify the correct credentials, the message is sent to Oracle E-Business Suite and a response is received.</span></span> <span data-ttu-id="3225e-120">ただし、応答メッセージでは、出力ポートを使用できません。</span><span class="sxs-lookup"><span data-stu-id="3225e-120">However, the response message is not available to the out port.</span></span> <span data-ttu-id="3225e-121">このようなシナリオでは、ホスト インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3225e-121">In such scenarios, you may need to restart the host instance.</span></span>  
  
## <a name="limitations-due-to-odpnet"></a><span data-ttu-id="3225e-122">ODP.NET に関する制約</span><span class="sxs-lookup"><span data-stu-id="3225e-122">Limitations Due to ODP.NET</span></span>  
 <span data-ttu-id="3225e-123">次の制限事項を呼びます[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ODP.NET の制限のため。</span><span class="sxs-lookup"><span data-stu-id="3225e-123">The following are known limitations for [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] due to the limitation of ODP.NET:</span></span>  
  
- <span data-ttu-id="3225e-124">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]数値フィールドでインデックス化されていない PL/SQL テーブルをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="3225e-124">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support PL/SQL tables that are not indexed by a numeric field.</span></span>  
  
- <span data-ttu-id="3225e-125">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]は任意の要素が含まれていない連想配列をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3225e-125">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support associative arrays that do not contain any element.</span></span>  
  
- <span data-ttu-id="3225e-126">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]はローカル タイム ゾーンの属性 (TimeStampLTZ) を持つ TimeStamp データ型が含まれている Udt をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3225e-126">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that contain the TimeStamp data type with local time zone attributes (TimeStampLTZ).</span></span>  
  
- <span data-ttu-id="3225e-127">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]が含まれている Udt をサポートしていませんが、"."</span><span class="sxs-lookup"><span data-stu-id="3225e-127">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that contain a “.”</span></span> <span data-ttu-id="3225e-128">(期間)、名前にします。</span><span class="sxs-lookup"><span data-stu-id="3225e-128">(period) in their names.</span></span>  
  
- <span data-ttu-id="3225e-129">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] IN OUT パラメーターとして BLOB、CLOB、NCLOB データ型が含まれている Udt をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3225e-129">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that contain BLOB, CLOB, and NCLOB data types as an IN OUT parameter.</span></span>  
  
- <span data-ttu-id="3225e-130">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Varray の Varray の次の単純型をサポートしていません: BFILE、IntervalDS、IntervalYM、TimeStampLTZ、および TimeStampTZ します。</span><span class="sxs-lookup"><span data-stu-id="3225e-130">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support Varray of Varray of the following simple types: BFILE, IntervalDS, IntervalYM, TimeStampLTZ, and TimeStampTZ.</span></span>  
  
- <span data-ttu-id="3225e-131">連想配列の制限のため PL/SQL テーブルまたは次のデータ型のいずれかが含まれているレコードの PL/SQL テーブルでサポートされていない、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="3225e-131">Due to the limitation of associative arrays, PL/SQL tables or PL/SQL tables of records that contain any of the following data types are not supported in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:</span></span>  
  
  -   <span data-ttu-id="3225e-132">BFILE</span><span class="sxs-lookup"><span data-stu-id="3225e-132">BFILE</span></span>  
  
  -   <span data-ttu-id="3225e-133">BLOB</span><span class="sxs-lookup"><span data-stu-id="3225e-133">BLOB</span></span>  
  
  -   <span data-ttu-id="3225e-134">CLOB</span><span class="sxs-lookup"><span data-stu-id="3225e-134">CLOB</span></span>  
  
  -   <span data-ttu-id="3225e-135">IntervalDS</span><span class="sxs-lookup"><span data-stu-id="3225e-135">IntervalDS</span></span>  
  
  -   <span data-ttu-id="3225e-136">IntervalYM</span><span class="sxs-lookup"><span data-stu-id="3225e-136">IntervalYM</span></span>  
  
  -   <span data-ttu-id="3225e-137">Long</span><span class="sxs-lookup"><span data-stu-id="3225e-137">Long</span></span>  
  
  -   <span data-ttu-id="3225e-138">NCLOB</span><span class="sxs-lookup"><span data-stu-id="3225e-138">NCLOB</span></span>  
  
  -   <span data-ttu-id="3225e-139">RowID</span><span class="sxs-lookup"><span data-stu-id="3225e-139">RowID</span></span>  
  
  -   <span data-ttu-id="3225e-140">TimeStamp</span><span class="sxs-lookup"><span data-stu-id="3225e-140">TimeStamp</span></span>  
  
  -   <span data-ttu-id="3225e-141">TimeStampLTZ</span><span class="sxs-lookup"><span data-stu-id="3225e-141">TimeStampLTZ</span></span>  
  
  -   <span data-ttu-id="3225e-142">TimeStampTZ</span><span class="sxs-lookup"><span data-stu-id="3225e-142">TimeStampTZ</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3225e-143">参照</span><span class="sxs-lookup"><span data-stu-id="3225e-143">See Also</span></span>  
 [<span data-ttu-id="3225e-144">BizTalk Adapter for Oracle E-Business Suite について</span><span class="sxs-lookup"><span data-stu-id="3225e-144">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)