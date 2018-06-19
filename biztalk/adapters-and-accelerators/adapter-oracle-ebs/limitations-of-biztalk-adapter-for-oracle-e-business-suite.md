---
title: BizTalk adapter for Oracle E-business Suite の制限事項 |Microsoft ドキュメント
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
ms.openlocfilehash: e7611c56fbd24c7c7cf09d38d376df585b72b284
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216274"
---
# <a name="limitations-of-biztalk-adapter-for-oracle-e-business-suite"></a><span data-ttu-id="d2913-102">BizTalk adapter for Oracle E-business Suite の制限事項</span><span class="sxs-lookup"><span data-stu-id="d2913-102">Limitations of BizTalk Adapter for Oracle E-Business Suite</span></span>
## <a name="general-limitations"></a><span data-ttu-id="d2913-103">一般的な制限事項</span><span class="sxs-lookup"><span data-stu-id="d2913-103">General Limitations</span></span>  
 <span data-ttu-id="d2913-104">次はの既知の制限[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d2913-104">The following are known limitations for [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:</span></span>  
  
-   <span data-ttu-id="d2913-105">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] XML Gateway、アドバンスド キュー、およびビジネス イベントはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="d2913-105">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support XML Gateway, Advanced Queuing, and Business Events.</span></span>  
  
     <span data-ttu-id="d2913-106">ただし、次のように、ビジネス イベントの制限を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="d2913-106">However, you can get around the Business Events limitation in the following way:</span></span>  
  
    1.  <span data-ttu-id="d2913-107">Oracle のビジネス イベント システムでは、プロシージャを呼び出すカスタム PL/SQL ビジネス イベント発生時にサブスクリプションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d2913-107">In Oracle Business Events System, create a subscription to invoke a custom PL/SQL procedure when a business event occurs.</span></span>  
  
    2.  <span data-ttu-id="d2913-108">ビジネス イベントを受け取るカスタム PL/SQL プロシージャを記述します。</span><span class="sxs-lookup"><span data-stu-id="d2913-108">Write a custom PL/SQL procedure that receives the business event.</span></span>  
  
    3.  <span data-ttu-id="d2913-109">テーブルに結果データ (イベントおよびイベント ペイロード) を格納するカスタムの PL/SQL 手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d2913-109">Use the custom PL/SQL procedure to store the resultant data (event and event payload) in a table.</span></span>  
  
    4.  <span data-ttu-id="d2913-110">使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]をポーリングまたはテーブルから通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="d2913-110">Use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll or receive notifications from the table.</span></span>  
  
-   <span data-ttu-id="d2913-111">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] XML 型をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d2913-111">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support XML Types.</span></span>  
  
-   <span data-ttu-id="d2913-112">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を NULL に VARRAY で最初の要素の値を設定するクライアントを有効にしません。</span><span class="sxs-lookup"><span data-stu-id="d2913-112">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not enable clients to set the value of the first element in a VARRAY to NULL.</span></span>  
  
-   <span data-ttu-id="d2913-113">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]のフィールドを含むサポート レコードいないは、レコード型の PL/SQL テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="d2913-113">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support records that contain fields of type PL/SQL tables of RECORD type.</span></span>  
  
-   <span data-ttu-id="d2913-114">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]循環参照が含まれるユーザー定義型 (Udt) をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d2913-114">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support User-Defined Types (UDTs) that have circular references.</span></span>  
  
-   <span data-ttu-id="d2913-115">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] (レコード型、テーブルの種類、UDT、および VARRAY) などの複合型の内部 BFILE データ型をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d2913-115">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support the BFILE data type inside complex types (such as RECORD type, TABLE type, UDT, and VARRAY).</span></span>  
  
-   <span data-ttu-id="d2913-116">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]のみに最大 2 つのレベルの入れ子の UDT をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d2913-116">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports UDT nesting only up to two levels.</span></span>  
  
-   <span data-ttu-id="d2913-117">PL/SQL テーブルを除く、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]はパッケージ内で定義されている Udt をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d2913-117">Except for PL/SQL tables, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that are defined inside a package.</span></span>  
  
-   <span data-ttu-id="d2913-118">BizTalk Server にアダプターを使用する場合は、WCF カスタム資格情報の送信ポートが正しくない場合、要求メッセージは処理されません。</span><span class="sxs-lookup"><span data-stu-id="d2913-118">When using the adapters with BizTalk Server, if the credentials on the WCF-custom send port are incorrect, the request messages are not processed.</span></span> <span data-ttu-id="d2913-119">正しい資格情報を指定すると後、は、Oracle E-business Suite にメッセージを送信し、応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="d2913-119">After you specify the correct credentials, the message is sent to Oracle E-Business Suite and a response is received.</span></span> <span data-ttu-id="d2913-120">ただし、応答メッセージでは、出力ポートを使用できません。</span><span class="sxs-lookup"><span data-stu-id="d2913-120">However, the response message is not available to the out port.</span></span> <span data-ttu-id="d2913-121">このようなシナリオでは、ホスト インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2913-121">In such scenarios, you may need to restart the host instance.</span></span>  
  
## <a name="limitations-due-to-odpnet"></a><span data-ttu-id="d2913-122">ODP.NET のための制限事項</span><span class="sxs-lookup"><span data-stu-id="d2913-122">Limitations Due to ODP.NET</span></span>  
 <span data-ttu-id="d2913-123">次はの既知の制限[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ODP.NET の制限のため。</span><span class="sxs-lookup"><span data-stu-id="d2913-123">The following are known limitations for [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] due to the limitation of ODP.NET:</span></span>  
  
-   <span data-ttu-id="d2913-124">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]数値フィールドをインデックス化されていない PL/SQL テーブルをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d2913-124">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support PL/SQL tables that are not indexed by a numeric field.</span></span>  
  
-   <span data-ttu-id="d2913-125">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]は含まれていない任意の要素の連想配列をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d2913-125">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support associative arrays that do not contain any element.</span></span>  
  
-   <span data-ttu-id="d2913-126">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]はローカル タイム ゾーンの属性 (TimeStampLTZ) を持つ TimeStamp データ型が含まれている Udt をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d2913-126">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that contain the TimeStamp data type with local time zone attributes (TimeStampLTZ).</span></span>  
  
-   <span data-ttu-id="d2913-127">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Udt を含むをサポートしていない、"です"。</span><span class="sxs-lookup"><span data-stu-id="d2913-127">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that contain a “.”</span></span> <span data-ttu-id="d2913-128">(期間)、名前にします。</span><span class="sxs-lookup"><span data-stu-id="d2913-128">(period) in their names.</span></span>  
  
-   <span data-ttu-id="d2913-129">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] IN OUT パラメーターとして BLOB、CLOB、および NCLOB データ型が含まれている Udt をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d2913-129">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that contain BLOB, CLOB, and NCLOB data types as an IN OUT parameter.</span></span>  
  
-   <span data-ttu-id="d2913-130">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Varray の Varray の次の単純型をサポートしていません: BFILE、IntervalDS、IntervalYM、TimeStampLTZ、および TimeStampTZ です。</span><span class="sxs-lookup"><span data-stu-id="d2913-130">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support Varray of Varray of the following simple types: BFILE, IntervalDS, IntervalYM, TimeStampLTZ, and TimeStampTZ.</span></span>  
  
-   <span data-ttu-id="d2913-131">連想配列の制限、により PL/SQL テーブルまたはデータ型を次のいずれかが含まれるレコードの PL/SQL テーブルでサポートされていない、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d2913-131">Due to the limitation of associative arrays, PL/SQL tables or PL/SQL tables of records that contain any of the following data types are not supported in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:</span></span>  
  
    -   <span data-ttu-id="d2913-132">BFILE</span><span class="sxs-lookup"><span data-stu-id="d2913-132">BFILE</span></span>  
  
    -   <span data-ttu-id="d2913-133">BLOB</span><span class="sxs-lookup"><span data-stu-id="d2913-133">BLOB</span></span>  
  
    -   <span data-ttu-id="d2913-134">CLOB</span><span class="sxs-lookup"><span data-stu-id="d2913-134">CLOB</span></span>  
  
    -   <span data-ttu-id="d2913-135">IntervalDS</span><span class="sxs-lookup"><span data-stu-id="d2913-135">IntervalDS</span></span>  
  
    -   <span data-ttu-id="d2913-136">IntervalYM</span><span class="sxs-lookup"><span data-stu-id="d2913-136">IntervalYM</span></span>  
  
    -   <span data-ttu-id="d2913-137">Long</span><span class="sxs-lookup"><span data-stu-id="d2913-137">Long</span></span>  
  
    -   <span data-ttu-id="d2913-138">NCLOB</span><span class="sxs-lookup"><span data-stu-id="d2913-138">NCLOB</span></span>  
  
    -   <span data-ttu-id="d2913-139">RowID</span><span class="sxs-lookup"><span data-stu-id="d2913-139">RowID</span></span>  
  
    -   <span data-ttu-id="d2913-140">TimeStamp</span><span class="sxs-lookup"><span data-stu-id="d2913-140">TimeStamp</span></span>  
  
    -   <span data-ttu-id="d2913-141">TimeStampLTZ</span><span class="sxs-lookup"><span data-stu-id="d2913-141">TimeStampLTZ</span></span>  
  
    -   <span data-ttu-id="d2913-142">TimeStampTZ</span><span class="sxs-lookup"><span data-stu-id="d2913-142">TimeStampTZ</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2913-143">参照</span><span class="sxs-lookup"><span data-stu-id="d2913-143">See Also</span></span>  
 [<span data-ttu-id="d2913-144">Oracle E-business Suite の BizTalk アダプターを理解します。</span><span class="sxs-lookup"><span data-stu-id="d2913-144">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)