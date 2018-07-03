---
title: 'チュートリアル: Oracle データベース アダプターを BizTalk プロジェクトの移行 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a393219-bae8-4e08-acc8-76986600d0de
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdde0ae8992fc9ae0c7dd30b91b7f38733c1de2b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999843"
---
# <a name="tutorial-migrate-biztalk-projects-to-the-oracle-database-adapter"></a><span data-ttu-id="acc4a-102">チュートリアル: Oracle データベース アダプターを BizTalk プロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="acc4a-102">Tutorial: Migrate BizTalk Projects to the Oracle Database adapter</span></span>
<span data-ttu-id="acc4a-103">Microsoft BizTalk Server に付属している Oracle データベースの BizTalk ODBC アダプターは WCF ベース異なります[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]など、多くの点で。</span><span class="sxs-lookup"><span data-stu-id="acc4a-103">The BizTalk ODBC Adapter for Oracle Database that shipped with Microsoft BizTalk Server differs from the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] in many aspects, including:</span></span>  
  
- <span data-ttu-id="acc4a-104">BizTalk プロジェクトの作成、デザイン時エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="acc4a-104">The design-time experience of creating a BizTalk project.</span></span>  
  
- <span data-ttu-id="acc4a-105">メタデータの取得エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="acc4a-105">The metadata retrieval experience.</span></span>  
  
- <span data-ttu-id="acc4a-106">スキーマ ファイル名と名前空間。</span><span class="sxs-lookup"><span data-stu-id="acc4a-106">Schema file name and namespace.</span></span>  
  
- <span data-ttu-id="acc4a-107">データ型のマッピング。</span><span class="sxs-lookup"><span data-stu-id="acc4a-107">Data type mappings.</span></span>  
  
- <span data-ttu-id="acc4a-108">アダプターを使用して実行できる操作。</span><span class="sxs-lookup"><span data-stu-id="acc4a-108">The operations that can be performed using the adapter.</span></span>  
  
- <span data-ttu-id="acc4a-109">BizTalk Server 管理コンソールで物理ポートの構成</span><span class="sxs-lookup"><span data-stu-id="acc4a-109">Physical port configuration in the BizTalk Server Administration console</span></span>  
  
  <span data-ttu-id="acc4a-110">これらの相違点については、トピックで[を移行する BizTalk プロジェクト作成を使用して BizTalk ODBC Adapter for Oracle Database](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e)します。</span><span class="sxs-lookup"><span data-stu-id="acc4a-110">These differences are explained in the topics within [Migrating BizTalk Projects Created Using the BizTalk ODBC Adapter for Oracle Database](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e).</span></span>  
  
  <span data-ttu-id="acc4a-111">ただし、Oracle データベース、BizTalk ODBC アダプターを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースと連携させるため[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="acc4a-111">However, you can make changes to the BizTalk project that was created using the BizTalk ODBC Adapter for Oracle Database and make it work with the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
  <span data-ttu-id="acc4a-112">このチュートリアルでは、Oracle データベース、BizTalk ODBC アダプターを使用して作成された既存の BizTalk プロジェクトにする必要があります変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="acc4a-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the BizTalk ODBC Adapter for Oracle Database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="acc4a-113">説明を簡潔にするため、このチュートリアルでは、BizTalk ODBC Adapter for Oracle Database が参照されます「vPrev Oracle データベース アダプター」として</span><span class="sxs-lookup"><span data-stu-id="acc4a-113">In this tutorial, for the sake of brevity, the BizTalk ODBC Adapter for Oracle Database  will be referred to as “vPrev Oracle Database adapter.”</span></span> <span data-ttu-id="acc4a-114">同様に、vPrev Oracle データベース アダプタを使用する BizTalk プロジェクトとして参照される「vPrev BizTalk プロジェクトです」</span><span class="sxs-lookup"><span data-stu-id="acc4a-114">Similarly, a BizTalk project that uses the vPrev Oracle Database adapter will be referred to as “vPrev BizTalk project.”</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="acc4a-115">このチュートリアルで使用されるサンプル</span><span class="sxs-lookup"><span data-stu-id="acc4a-115">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="acc4a-116">このチュートリアルは、vPrev BizTalk プロジェクトを移行する方法を示すサンプル (Oracle_Migration) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="acc4a-116">This tutorial is based upon a sample (Oracle_Migration) that demonstrates how to migrate a vPrev BizTalk project.</span></span> <span data-ttu-id="acc4a-117">Microsoft とサンプルが提供される[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="acc4a-117">The sample is provided with Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="acc4a-118">詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="acc4a-118">For more information, see [Adapter samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="acc4a-119">前提条件</span><span class="sxs-lookup"><span data-stu-id="acc4a-119">Prerequisites</span></span>  
  
- <span data-ttu-id="acc4a-120">VPrev BizTalk プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="acc4a-120">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="acc4a-121">このチュートリアルには、CUSTOMER テーブルの挿入操作を実行する BizTalk プロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="acc4a-121">This tutorial involves a BizTalk project that performs an Insert operation on a CUSTOMER table.</span></span> <span data-ttu-id="acc4a-122">SCOTT スキーマの下で提供される SQL スクリプトを実行して、CUSTOMER テーブルが作成された、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="acc4a-122">The CUSTOMER table is created under the SCOTT schema by running the SQL scripts provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] samples.</span></span>  
  
- <span data-ttu-id="acc4a-123">VPrev Oracle データベース アダプターを使用して Oracle データベースに対して、挿入操作を実行する要求メッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="acc4a-123">You must have a request message to perform an Insert operation on the Oracle database using the vPrev Oracle Database adapter.</span></span> <span data-ttu-id="acc4a-124">要求メッセージは、vPrev Oracle データベース アダプターを使用して生成する挿入操作のスキーマに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="acc4a-124">The request message must conform to the schema of the Insert operation generated using the vPrev Oracle Database adapter.</span></span>  
  
- <span data-ttu-id="acc4a-125">」の手順を完了する必要があります[の前提条件](../../adapters-and-accelerators/adapter-oracle-database/prerequisites-to-create-oracle-database-applications.md)</span><span class="sxs-lookup"><span data-stu-id="acc4a-125">You must have completed the steps in [Prerequisites](../../adapters-and-accelerators/adapter-oracle-database/prerequisites-to-create-oracle-database-applications.md)</span></span> 
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="acc4a-126">アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。</span><span class="sxs-lookup"><span data-stu-id="acc4a-126">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="acc4a-127">作成された vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="acc4a-127">The key constituents of a vPrev BizTalk project created are:</span></span>  
  
- <span data-ttu-id="acc4a-128">**BizTalk オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="acc4a-128">**BizTalk orchestration**.</span></span> <span data-ttu-id="acc4a-129">これは、簡単なオーケストレーション ポートに送信しますが、Oracle を使用して Oracle データベースに要求メッセージの送信、受信ファイルの場所からの要求メッセージを取得し、応答を受信、ファイルの別の場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="acc4a-129">This is a simple orchestration that picks request messages from a file location, sends the request message to the Oracle database using an Oracle send-receive port, receives the response, and saves it to another file location.</span></span>  
  
- <span data-ttu-id="acc4a-130">**Oracle データベースで実行する操作のスキーマを**します。</span><span class="sxs-lookup"><span data-stu-id="acc4a-130">**Schema for the operation you wish to perform on the Oracle database**.</span></span> <span data-ttu-id="acc4a-131">このチュートリアルには、SCOTT スキーマで顧客テーブルに挿入操作を実行する BizTalk プロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="acc4a-131">This tutorial involves a BizTalk project that performs an Insert operation on the CUSTOMER table in the SCOTT schema.</span></span> <span data-ttu-id="acc4a-132">SCOTT スキーマの下で提供される SQL スクリプトを実行して、CUSTOMER テーブルが作成された、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="acc4a-132">The CUSTOMER table is created under the SCOTT schema by running the SQL scripts provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] samples.</span></span> <span data-ttu-id="acc4a-133">顧客テーブルに対して生成されたスキーマは、CUSTOMERService_CUSTOMER_x5d.xsd です。</span><span class="sxs-lookup"><span data-stu-id="acc4a-133">The schema generated for the CUSTOMER table is CUSTOMERService_CUSTOMER_x5d.xsd.</span></span> <span data-ttu-id="acc4a-134">VPrev Oracle データベース アダプターを使用して、このスキーマが生成されます。</span><span class="sxs-lookup"><span data-stu-id="acc4a-134">This schema is generated using the vPrev Oracle Database adapter.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="acc4a-135">WCF ベースとは異なり[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]vPrev の Oracle データベース アダプタが Oracle データベース テーブルで特定の操作のメタデータの生成をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="acc4a-135">Unlike the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], the vPrev Oracle Database adapter does not support generating metadata for specific operations on an Oracle database table.</span></span> <span data-ttu-id="acc4a-136">既定では、アダプターは、テーブルでサポートされているすべての操作のスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="acc4a-136">By default, the adapter generates schema for all the operations supported on the table.</span></span> <span data-ttu-id="acc4a-137">VPrev Oracle データベース アダプターと WCF ベースのはこのような違いの[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[を移行する BizTalk プロジェクト作成を使用して BizTalk ODBC Adapter for Oracle Database](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e)します。</span><span class="sxs-lookup"><span data-stu-id="acc4a-137">For more such differences between the vPrev Oracle Database adapter and the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Migrating BizTalk Projects Created Using the BizTalk ODBC Adapter for Oracle Database](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e).</span></span>  
  
- <span data-ttu-id="acc4a-138">**要求メッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="acc4a-138">**Request message**.</span></span> <span data-ttu-id="acc4a-139">顧客テーブルに挿入操作を実行する要求メッセージ。</span><span class="sxs-lookup"><span data-stu-id="acc4a-139">The request message to perform an Insert operation on the CUSTOMER table.</span></span> <span data-ttu-id="acc4a-140">要求メッセージのスキーマは、Oracle データベース アダプターの以前のバージョンで表示、挿入操作のスキーマに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="acc4a-140">The schema of the request message conforms to the schema of the Insert operation as surfaced by the previous version of the Oracle Database adapter.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="acc4a-141">BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。</span><span class="sxs-lookup"><span data-stu-id="acc4a-141">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="acc4a-142">この移行のチュートリアルの目的は WCF ベースに準拠したメッセージを処理できるだけ WCF カスタム ポートを使用して、vPrev Oracle データベース アダプターによって生成されたスキーマに準拠している要求メッセージを送信するために、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="acc4a-142">The goal of this migration tutorial is to enable you to send a request message, which conforms to schema generated by vPrev Oracle Database adapter, using a WCF-Custom port that can only process messages conforming to the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="acc4a-143">そのため、簡単に言えばの移行の練習では WCF ベースに準拠していないメッセージを処理する WCF カスタム ポートを構成する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]のスキーマ。</span><span class="sxs-lookup"><span data-stu-id="acc4a-143">So, in short, the migration exercise involves configuring the WCF-Custom port to process messages that do not conform to the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]'s schema.</span></span>  
  
 <span data-ttu-id="acc4a-144">ただし、WCF カスタム ポートを適切に構成できるようにするには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="acc4a-144">However, to be able to configure the WCF-Custom port appropriately, you must perform the following tasks:</span></span>  
  
- <span data-ttu-id="acc4a-145">SCOTT に対する挿入操作のメタデータを生成します。WCF ベースを使用して顧客テーブル[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="acc4a-145">Generate metadata for the Insert operation on the SCOTT.CUSTOMER table using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
- <span data-ttu-id="acc4a-146">WCF ベースを使用して挿入操作を実行するための要求メッセージに vPrev Oracle データベース アダプターを使用して挿入操作を実行するための要求メッセージにマップ[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="acc4a-146">Map the request message for performing an Insert operation using the vPrev Oracle Database adapter to a request message for performing an Insert operation using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
- <span data-ttu-id="acc4a-147">WCF ベースを使用して受信応答メッセージにマップ[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]vPrev Oracle データベース アダプターの応答メッセージにします。</span><span class="sxs-lookup"><span data-stu-id="acc4a-147">Map the response message received using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to the response message for the vPrev Oracle Database adapter.</span></span>  
  
- <span data-ttu-id="acc4a-148">Wcf-custom の Oracle を作成、BizTalk Server 管理コンソールのポートの送信-受信します。</span><span class="sxs-lookup"><span data-stu-id="acc4a-148">Create a WCF-Custom Oracle send-receive port in the BizTalk Server Administration console.</span></span>  
  
- <span data-ttu-id="acc4a-149">要求と応答のマッピングを使用する WCF カスタム ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="acc4a-149">Configure the WCF-Custom port to use the request and response mappings.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="acc4a-150">参照</span><span class="sxs-lookup"><span data-stu-id="acc4a-150">See Also</span></span>  
[<span data-ttu-id="acc4a-151">Biztalk Server の概要</span><span class="sxs-lookup"><span data-stu-id="acc4a-151">Getting started with Biztalk Server</span></span>](../../core/getting-started-with-biztalk-server.md)