---
title: "チュートリアル: Oracle データベース アダプターの BizTalk プロジェクトの移行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a393219-bae8-4e08-acc8-76986600d0de
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0948e79b7f236bb20bbff9101195809bcc921a68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-migrate-biztalk-projects-to-the-oracle-database-adapter"></a><span data-ttu-id="c2fa5-102">チュートリアル: Oracle データベース アダプターを BizTalk プロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-102">Tutorial: Migrate BizTalk Projects to the Oracle Database adapter</span></span>
<span data-ttu-id="c2fa5-103">Microsoft BizTalk Server に付属している Oracle データベースの BizTalk ODBC アダプターは WCF ベース異なります[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]など、多くの点で。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-103">The BizTalk ODBC Adapter for Oracle Database that shipped with Microsoft BizTalk Server differs from the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] in many aspects, including:</span></span>  
  
-   <span data-ttu-id="c2fa5-104">デザイン時に、BizTalk プロジェクトを作成する操作。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-104">The design-time experience of creating a BizTalk project.</span></span>  
  
-   <span data-ttu-id="c2fa5-105">メタデータの取得エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-105">The metadata retrieval experience.</span></span>  
  
-   <span data-ttu-id="c2fa5-106">スキーマ ファイル名と名前空間。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-106">Schema file name and namespace.</span></span>  
  
-   <span data-ttu-id="c2fa5-107">データは、マッピングを入力します。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-107">Data type mappings.</span></span>  
  
-   <span data-ttu-id="c2fa5-108">アダプターを使用して実行できる操作です。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-108">The operations that can be performed using the adapter.</span></span>  
  
-   <span data-ttu-id="c2fa5-109">BizTalk Server 管理コンソールで物理ポートの構成</span><span class="sxs-lookup"><span data-stu-id="c2fa5-109">Physical port configuration in the BizTalk Server Administration console</span></span>  
  
 <span data-ttu-id="c2fa5-110">これらの相違点が含まれるトピックで説明した[を移行する BizTalk プロジェクトが作成を使用して BizTalk ODBC Adapter 用 Oracle Database](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e)です。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-110">These differences are explained in the topics within [Migrating BizTalk Projects Created Using the BizTalk ODBC Adapter for Oracle Database](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e).</span></span>  
  
 <span data-ttu-id="c2fa5-111">ただし、Oracle データベースの BizTalk ODBC アダプターを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースで動作させるため[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-111">However, you can make changes to the BizTalk project that was created using the BizTalk ODBC Adapter for Oracle Database and make it work with the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
 <span data-ttu-id="c2fa5-112">このチュートリアルでは、Oracle データベースの BizTalk ODBC アダプターを使用して作成された既存の BizTalk プロジェクトに加える必要があります変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the BizTalk ODBC Adapter for Oracle Database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2fa5-113">ここでは簡略化のため、このチュートリアルでは、ODBC 用 BizTalk アダプター Oracle データベースが参照されます「vPrev Oracle データベース アダプター」として</span><span class="sxs-lookup"><span data-stu-id="c2fa5-113">In this tutorial, for the sake of brevity, the BizTalk ODBC Adapter for Oracle Database  will be referred to as “vPrev Oracle Database adapter.”</span></span> <span data-ttu-id="c2fa5-114">同様に、vPrev Oracle データベース アダプターを使用する BizTalk プロジェクトが参照されますとして「vPrev BizTalk プロジェクトです」</span><span class="sxs-lookup"><span data-stu-id="c2fa5-114">Similarly, a BizTalk project that uses the vPrev Oracle Database adapter will be referred to as “vPrev BizTalk project.”</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="c2fa5-115">チュートリアルでは、使用されるサンプル</span><span class="sxs-lookup"><span data-stu-id="c2fa5-115">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="c2fa5-116">このチュートリアルは、vPrev BizTalk プロジェクトを移行する方法を示すサンプル (Oracle_Migration) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-116">This tutorial is based upon a sample (Oracle_Migration) that demonstrates how to migrate a vPrev BizTalk project.</span></span> <span data-ttu-id="c2fa5-117">サンプルが付属して Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-117">The sample is provided with Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="c2fa5-118">詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-118">For more information, see [Adapter samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c2fa5-119">前提条件</span><span class="sxs-lookup"><span data-stu-id="c2fa5-119">Prerequisites</span></span>  
  
-   <span data-ttu-id="c2fa5-120">VPrev BizTalk プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-120">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="c2fa5-121">このチュートリアルには、CUSTOMER テーブルで Insert 操作を実行する BizTalk プロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-121">This tutorial involves a BizTalk project that performs an Insert operation on a CUSTOMER table.</span></span> <span data-ttu-id="c2fa5-122">SCOTT スキーマの下で提供される SQL スクリプトを実行して、CUSTOMER テーブルが作成された、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]サンプルです。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-122">The CUSTOMER table is created under the SCOTT schema by running the SQL scripts provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] samples.</span></span>  
  
-   <span data-ttu-id="c2fa5-123">要求メッセージを vPrev Oracle データベース アダプターを使用して Oracle データベースで挿入操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-123">You must have a request message to perform an Insert operation on the Oracle database using the vPrev Oracle Database adapter.</span></span> <span data-ttu-id="c2fa5-124">要求メッセージは、vPrev Oracle データベース アダプターを使用して生成する挿入操作のスキーマに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-124">The request message must conform to the schema of the Insert operation generated using the vPrev Oracle Database adapter.</span></span>  
  
-   <span data-ttu-id="c2fa5-125">内の手順を完了する必要があります[の前提条件](../../adapters-and-accelerators/adapter-oracle-database/prerequisites-to-create-oracle-database-applications.md)</span><span class="sxs-lookup"><span data-stu-id="c2fa5-125">You must have completed the steps in [Prerequisites](../../adapters-and-accelerators/adapter-oracle-database/prerequisites-to-create-oracle-database-applications.md)</span></span> 
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="c2fa5-126">アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-126">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="c2fa5-127">作成された vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-127">The key constituents of a vPrev BizTalk project created are:</span></span>  
  
-   <span data-ttu-id="c2fa5-128">**BizTalk オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-128">**BizTalk orchestration**.</span></span> <span data-ttu-id="c2fa5-129">これは、ポートの送信、Oracle を使用して Oracle データベースに要求メッセージの送信、受信ファイルの場所からの要求メッセージを取得し、応答を受信、別のファイルの場所に保存する簡単なオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-129">This is a simple orchestration that picks request messages from a file location, sends the request message to the Oracle database using an Oracle send-receive port, receives the response, and saves it to another file location.</span></span>  
  
-   <span data-ttu-id="c2fa5-130">**Oracle データベースで実行する操作のスキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-130">**Schema for the operation you wish to perform on the Oracle database**.</span></span> <span data-ttu-id="c2fa5-131">このチュートリアルには、SCOTT スキーマ内の CUSTOMER テーブルに対して挿入操作を実行する BizTalk プロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-131">This tutorial involves a BizTalk project that performs an Insert operation on the CUSTOMER table in the SCOTT schema.</span></span> <span data-ttu-id="c2fa5-132">SCOTT スキーマの下で提供される SQL スクリプトを実行して、CUSTOMER テーブルが作成された、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]サンプルです。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-132">The CUSTOMER table is created under the SCOTT schema by running the SQL scripts provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] samples.</span></span> <span data-ttu-id="c2fa5-133">顧客テーブルに対して生成されたスキーマは、CUSTOMERService_CUSTOMER_x5d.xsd です。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-133">The schema generated for the CUSTOMER table is CUSTOMERService_CUSTOMER_x5d.xsd.</span></span> <span data-ttu-id="c2fa5-134">このスキーマは、vPrev Oracle データベース アダプターを使用して生成されます。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-134">This schema is generated using the vPrev Oracle Database adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c2fa5-135">WCF ベースとは異なり[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、vPrev Oracle データベース アダプターは、Oracle データベース テーブルで特定の操作を生成するメタデータをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-135">Unlike the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], the vPrev Oracle Database adapter does not support generating metadata for specific operations on an Oracle database table.</span></span> <span data-ttu-id="c2fa5-136">既定では、アダプターは、テーブルでサポートされるすべての操作のスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-136">By default, the adapter generates schema for all the operations supported on the table.</span></span> <span data-ttu-id="c2fa5-137">このような複数 vPrev Oracle データベース アダプターと WCF ベースの違いの[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[を移行する BizTalk プロジェクトが作成を使用して BizTalk ODBC Adapter 用 Oracle Database](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e)です。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-137">For more such differences between the vPrev Oracle Database adapter and the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Migrating BizTalk Projects Created Using the BizTalk ODBC Adapter for Oracle Database](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e).</span></span>  
  
-   <span data-ttu-id="c2fa5-138">**要求メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-138">**Request message**.</span></span> <span data-ttu-id="c2fa5-139">顧客テーブルに挿入操作を実行する要求メッセージ。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-139">The request message to perform an Insert operation on the CUSTOMER table.</span></span> <span data-ttu-id="c2fa5-140">要求メッセージのスキーマは、Oracle データベース アダプターの以前のバージョンで表示、挿入操作のスキーマに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-140">The schema of the request message conforms to the schema of the Insert operation as surfaced by the previous version of the Oracle Database adapter.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="c2fa5-141">BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-141">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="c2fa5-142">この移行チュートリアルの目的は、WCF ベースに準拠したメッセージを処理できるだけ WCF カスタム ポートを使用して、vPrev Oracle データベース アダプターによって生成されたスキーマに準拠した要求メッセージを送信するために[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-142">The goal of this migration tutorial is to enable you to send a request message, which conforms to schema generated by vPrev Oracle Database adapter, using a WCF-Custom port that can only process messages conforming to the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="c2fa5-143">そのため、簡単に言えば、移行練習では、WCF ベースに準拠していないメッセージを処理する WCF カスタム ポートを構成する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]のスキーマです。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-143">So, in short, the migration exercise involves configuring the WCF-Custom port to process messages that do not conform to the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]'s schema.</span></span>  
  
 <span data-ttu-id="c2fa5-144">ただし、WCF カスタム ポートを適切に構成できるようにするには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-144">However, to be able to configure the WCF-Custom port appropriately, you must perform the following tasks:</span></span>  
  
-   <span data-ttu-id="c2fa5-145">SCOTT に対する挿入操作のメタデータを生成します。WCF ベースを使用して顧客テーブル[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-145">Generate metadata for the Insert operation on the SCOTT.CUSTOMER table using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
-   <span data-ttu-id="c2fa5-146">WCF ベースを使用する挿入操作を実行するための要求メッセージに vPrev Oracle データベース アダプターを使用して挿入操作を実行するための要求メッセージにマップ[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-146">Map the request message for performing an Insert operation using the vPrev Oracle Database adapter to a request message for performing an Insert operation using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
-   <span data-ttu-id="c2fa5-147">WCF ベースを使用して受信した応答メッセージをマップ[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]vPrev Oracle データベース アダプターの応答メッセージにします。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-147">Map the response message received using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to the response message for the vPrev Oracle Database adapter.</span></span>  
  
-   <span data-ttu-id="c2fa5-148">Wcf-custom Oracle を作成、BizTalk Server 管理コンソールのポートの送信受信します。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-148">Create a WCF-Custom Oracle send-receive port in the BizTalk Server Administration console.</span></span>  
  
-   <span data-ttu-id="c2fa5-149">要求と応答のマッピングを使用する WCF カスタム ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="c2fa5-149">Configure the WCF-Custom port to use the request and response mappings.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="c2fa5-150">参照</span><span class="sxs-lookup"><span data-stu-id="c2fa5-150">See Also</span></span>  
[<span data-ttu-id="c2fa5-151">Biztalk Server の概要</span><span class="sxs-lookup"><span data-stu-id="c2fa5-151">Getting started with Biztalk Server</span></span>](../../core/getting-started-with-biztalk-server.md)