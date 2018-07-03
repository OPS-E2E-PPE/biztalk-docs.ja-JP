---
title: 'チュートリアル 1: SQL アダプタを BizTalk プロジェクトの移行 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b4d2dbb-e37c-4d70-831f-3bdac3c28c97
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea64d98404d247a47e8cad8df421c81752fe63e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013307"
---
# <a name="tutorial-1-migrate-biztalk-projects-to-the-sql-adapter"></a><span data-ttu-id="8906e-102">チュートリアル 1: SQL アダプタを BizTalk プロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="8906e-102">Tutorial 1: Migrate BizTalk Projects to the SQL adapter</span></span>
<span data-ttu-id="8906e-103">以前のバージョンを Microsoft に同梱されている SQL アダプターの[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]WCF ベースのとは異なる[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]など、多くの点で。</span><span class="sxs-lookup"><span data-stu-id="8906e-103">The previous version of the SQL adapter that shipped with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] differs from the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in many aspects, including:</span></span>  
  
- <span data-ttu-id="8906e-104">BizTalk プロジェクトの作成、デザイン時エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="8906e-104">The design-time experience of creating a BizTalk project.</span></span>  
  
- <span data-ttu-id="8906e-105">メタデータの取得エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="8906e-105">The metadata retrieval experience.</span></span>  
  
- <span data-ttu-id="8906e-106">スキーマ ファイル名と名前空間。</span><span class="sxs-lookup"><span data-stu-id="8906e-106">Schema file name and namespace.</span></span>  
  
- <span data-ttu-id="8906e-107">データ型のマッピング。</span><span class="sxs-lookup"><span data-stu-id="8906e-107">Data type mappings.</span></span>  
  
- <span data-ttu-id="8906e-108">アダプターを使用して実行できる操作。</span><span class="sxs-lookup"><span data-stu-id="8906e-108">The operations that can be performed using the adapter.</span></span>  
  
- <span data-ttu-id="8906e-109">BizTalk Server 管理コンソールで物理ポートの構成</span><span class="sxs-lookup"><span data-stu-id="8906e-109">Physical port configuration in the BizTalk Server Administration console</span></span>  
  
  <span data-ttu-id="8906e-110">移行する BizTalk プロジェクト作成を使用して、前のバージョン、SQLadapter の内のトピックでは、これらの相違点がについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8906e-110">These differences are explained in the topics within Migrating BizTalk Projects Created Using the Previous Version of the SQLadapter.</span></span>  
  
  <span data-ttu-id="8906e-111">ただし、アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースと連携させるため[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8906e-111">However, you can make changes to the BizTalk project that was created using the previous version of the adapter and make it work with the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
  <span data-ttu-id="8906e-112">このチュートリアルでは、アダプターの以前のバージョンを使用して作成された既存の BizTalk プロジェクトにする必要があります変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="8906e-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the previous version of the adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8906e-113">説明を簡潔にするため、このチュートリアルでは以前のバージョンの SQL アダプターを vPrev SQL アダプターとして指す場合は。</span><span class="sxs-lookup"><span data-stu-id="8906e-113">In this tutorial, for the sake of brevity, the previous version of the SQL adapter will be referred to as vPrev SQL adapter.</span></span> <span data-ttu-id="8906e-114">同様に、vPrev SQL アダプタを使用する BizTalk プロジェクトは vPrev BizTalk プロジェクトに参照されます。</span><span class="sxs-lookup"><span data-stu-id="8906e-114">Similarly, a BizTalk project that uses the vPrev SQL adapter will be referred to as vPrev BizTalk project.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="8906e-115">このチュートリアルでは、SQL Server データベースのテーブルの基本的な挿入操作を実行する vPrev SQL アダプター BizTalk プロジェクトを移行する方法のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="8906e-115">This tutorial provides guidance on how to migrate a vPrev SQL adapter BizTalk project that performs a basic insert operation on a SQL Server database table.</span></span> <span data-ttu-id="8906e-116">このチュートリアルでは、新しい vPrev SQL アダプタからの移行に関するすべての考えられるシナリオについては説明しません WCF ベース[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8906e-116">This tutorial does not cover all possible scenarios for migration from the vPrev SQL adapter to the new WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="8906e-117">基盤として、この移行のチュートリアルを使用して、既存のプロジェクトに関連する変更を適宜変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8906e-117">You must use this migration tutorial as a foundation and modify accordingly to make changes that are relevant to your existing project.</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="8906e-118">このチュートリアルで使用されるサンプル</span><span class="sxs-lookup"><span data-stu-id="8906e-118">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="8906e-119">このチュートリアルは、vPrev BizTalk プロジェクトを移行する方法を示すサンプル (SQL_Migration) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="8906e-119">This tutorial is based upon a sample (SQL_Migration) that demonstrates how to migrate a vPrev BizTalk project.</span></span> <span data-ttu-id="8906e-120">Microsoft とサンプルが提供される[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8906e-120">The sample is provided with Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="8906e-121">詳細については、サンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8906e-121">For more information, see Samples.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8906e-122">前提条件</span><span class="sxs-lookup"><span data-stu-id="8906e-122">Prerequisites</span></span>  
  
-   <span data-ttu-id="8906e-123">VPrev BizTalk プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="8906e-123">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="8906e-124">このチュートリアルには、SQL Server データベースの Customer テーブルに対して挿入操作を実行する BizTalk プロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8906e-124">This tutorial involves a BizTalk project that performs an Insert operation on a Customer table in the SQL Server database.</span></span> <span data-ttu-id="8906e-125">Customer テーブルには、次のデザインがあります。</span><span class="sxs-lookup"><span data-stu-id="8906e-125">The Customer table has the following design:</span></span>  
  
    |<span data-ttu-id="8906e-126">列名</span><span class="sxs-lookup"><span data-stu-id="8906e-126">Column Name</span></span>|<span data-ttu-id="8906e-127">説明</span><span class="sxs-lookup"><span data-stu-id="8906e-127">Description</span></span>|  
    |-----------------|-----------------|  
    |<span data-ttu-id="8906e-128">v_custid</span><span class="sxs-lookup"><span data-stu-id="8906e-128">v_custid</span></span>|<span data-ttu-id="8906e-129">プライマリ キーの整数型、id フィールド</span><span class="sxs-lookup"><span data-stu-id="8906e-129">Primary key, integer type, identity field</span></span>|  
    |<span data-ttu-id="8906e-130">名前</span><span class="sxs-lookup"><span data-stu-id="8906e-130">Name</span></span>|<span data-ttu-id="8906e-131">nchar(10) 型</span><span class="sxs-lookup"><span data-stu-id="8906e-131">nchar(10) type</span></span>|  
  
-   <span data-ttu-id="8906e-132">VPrev SQL アダプターを使用して SQL Server データベースに対して、挿入操作を実行する要求メッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="8906e-132">You must have a request message to perform an Insert operation on the SQL Server database using the vPrev SQL adapter.</span></span> <span data-ttu-id="8906e-133">要求メッセージは、vPrev SQL アダプタを使用して生成する挿入操作のスキーマに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8906e-133">The request message must conform to the schema of the Insert operation generated using the vPrev SQL adapter.</span></span>  
  
-   <span data-ttu-id="8906e-134">」の手順を完了する必要があります[Before You 開発 BizTalk Applications](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6)します。</span><span class="sxs-lookup"><span data-stu-id="8906e-134">You should have completed the steps in [Before You Develop BizTalk Applications](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6).</span></span>  
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="8906e-135">アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。</span><span class="sxs-lookup"><span data-stu-id="8906e-135">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="8906e-136">作成された vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8906e-136">The key constituents of a vPrev BizTalk project created are:</span></span>  
  
-   <span data-ttu-id="8906e-137">**BizTalk オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="8906e-137">**BizTalk orchestration**.</span></span> <span data-ttu-id="8906e-138">これは、簡単なオーケストレーション ポート送信 WCF カスタムを使用して SQL Server データベースに要求メッセージの送信、受信ファイルの場所からの要求メッセージを取得し、応答を受信、ファイルの別の場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="8906e-138">This is a simple orchestration that picks request messages from a file location, sends the request message to the SQL Server database using a WCF-Custom send-receive port, receives the response, and saves it to another file location.</span></span>  
  
-   <span data-ttu-id="8906e-139">**SQL Server データベースで実行する操作のスキーマを**します。</span><span class="sxs-lookup"><span data-stu-id="8906e-139">**Schema for the operation you wish to perform on the SQL Server database**.</span></span> <span data-ttu-id="8906e-140">このチュートリアルには、顧客テーブルに挿入操作を実行する BizTalk プロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8906e-140">This tutorial involves a BizTalk project that performs an Insert operation on the Customer table.</span></span> <span data-ttu-id="8906e-141">顧客テーブルに対して生成されたスキーマは、InsertCustomerService.xsd です。</span><span class="sxs-lookup"><span data-stu-id="8906e-141">The schema generated for the Customer table is InsertCustomerService.xsd.</span></span> <span data-ttu-id="8906e-142">VPrev SQL アダプターを使用して、このスキーマが生成されます。</span><span class="sxs-lookup"><span data-stu-id="8906e-142">This schema is generated using the vPrev SQL adapter.</span></span>  
  
-   <span data-ttu-id="8906e-143">**要求メッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="8906e-143">**Request message**.</span></span> <span data-ttu-id="8906e-144">顧客テーブルに挿入操作を実行する要求メッセージ。</span><span class="sxs-lookup"><span data-stu-id="8906e-144">The request message to perform an Insert operation on the Customer table.</span></span> <span data-ttu-id="8906e-145">要求メッセージのスキーマは、SQL アダプターの以前のバージョンで表示、挿入操作のスキーマに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="8906e-145">The schema of the request message conforms to the schema of the Insert operation as surfaced by the previous version of the SQL adapter.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="8906e-146">BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。</span><span class="sxs-lookup"><span data-stu-id="8906e-146">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="8906e-147">この移行のチュートリアルの目的は WCF ベースに準拠したメッセージを処理できるだけ WCF カスタム ポートを使用して、vPrev SQL アダプターによって生成されたスキーマに準拠している要求メッセージを送信するために、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8906e-147">The goal of this migration tutorial is to enable you to send a request message, which conforms to schema generated by vPrev SQL adapter, using a WCF-Custom port that can only process messages conforming to the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="8906e-148">そのため、簡単に言えばの移行の練習では WCF ベースに準拠していないメッセージを処理する WCF カスタム ポートを構成する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]のスキーマ。</span><span class="sxs-lookup"><span data-stu-id="8906e-148">So, in short, the migration exercise involves configuring the WCF-Custom port to process messages that do not conform to the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]'s schema.</span></span>  
  
 <span data-ttu-id="8906e-149">ただし、WCF カスタム ポートを適切に構成できるようにするには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8906e-149">However, to be able to configure the WCF-Custom port appropriately, you must perform the following tasks:</span></span>  
  
- <span data-ttu-id="8906e-150">WCF ベースを使用して、Customer テーブルに対する挿入操作のメタデータを生成[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8906e-150">Generate metadata for the Insert operation on the Customer table using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
- <span data-ttu-id="8906e-151">WCF ベースを使用して挿入操作を実行するための要求メッセージに vPrev SQL アダプターを使用して挿入操作を実行するための要求メッセージにマップ[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8906e-151">Map the request message for performing an Insert operation using the vPrev SQL adapter to a request message for performing an Insert operation using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
- <span data-ttu-id="8906e-152">WCF ベースを使用して受信応答メッセージにマップ[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]vPrev SQL アダプターの応答メッセージにします。</span><span class="sxs-lookup"><span data-stu-id="8906e-152">Map the response message received using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to the response message for the vPrev SQL adapter.</span></span>  
  
- <span data-ttu-id="8906e-153">WCF カスタム SQL の作成でポートの送信、受信、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="8906e-153">Create a WCF-Custom SQL send-receive port in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
- <span data-ttu-id="8906e-154">要求と応答のマッピングを使用する WCF カスタム ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="8906e-154">Configure the WCF-Custom port to use the request and response mappings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8906e-155">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8906e-155">In This Section</span></span>  
  
-   [<span data-ttu-id="8906e-156">手順 1: vPrev BizTalk プロジェクトの SQL アダプタの使用を変更します。</span><span class="sxs-lookup"><span data-stu-id="8906e-156">Step 1: Modify the vPrev BizTalk Project using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md)  
  
-   [<span data-ttu-id="8906e-157">手順 2: SQL アダプターを使用して BizTalk Server 管理コンソールでオーケストレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="8906e-157">Step 2: Configure the Orchestration in BizTalk Server Administration Console using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)  
  
-   [<span data-ttu-id="8906e-158">手順 3: SQL アダプタを使用する移行されたアプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="8906e-158">Step 3: Test the Migrated Application that uses the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="8906e-159">参照</span><span class="sxs-lookup"><span data-stu-id="8906e-159">See Also</span></span>  
 [<span data-ttu-id="8906e-160">SQL アダプターのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="8906e-160">SQL Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md)