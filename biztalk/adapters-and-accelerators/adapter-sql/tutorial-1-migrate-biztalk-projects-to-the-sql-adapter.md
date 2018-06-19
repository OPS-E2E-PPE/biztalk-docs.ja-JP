---
title: 'チュートリアル 1: SQL アダプタを BizTalk プロジェクトの移行 |Microsoft ドキュメント'
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
ms.openlocfilehash: 5ca17095841fb154be9ec34766a34f174414cd82
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225370"
---
# <a name="tutorial-1-migrate-biztalk-projects-to-the-sql-adapter"></a><span data-ttu-id="6ceb0-102">チュートリアル 1: SQL アダプタを BizTalk プロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-102">Tutorial 1: Migrate BizTalk Projects to the SQL adapter</span></span>
<span data-ttu-id="6ceb0-103">以前のバージョンを Microsoft に同梱されている SQL アダプターの[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]WCF ベースとは異なります[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]など、多くの点で。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-103">The previous version of the SQL adapter that shipped with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] differs from the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in many aspects, including:</span></span>  
  
-   <span data-ttu-id="6ceb0-104">デザイン時に、BizTalk プロジェクトを作成する操作。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-104">The design-time experience of creating a BizTalk project.</span></span>  
  
-   <span data-ttu-id="6ceb0-105">メタデータの取得エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-105">The metadata retrieval experience.</span></span>  
  
-   <span data-ttu-id="6ceb0-106">スキーマ ファイル名と名前空間。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-106">Schema file name and namespace.</span></span>  
  
-   <span data-ttu-id="6ceb0-107">データは、マッピングを入力します。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-107">Data type mappings.</span></span>  
  
-   <span data-ttu-id="6ceb0-108">アダプターを使用して実行できる操作です。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-108">The operations that can be performed using the adapter.</span></span>  
  
-   <span data-ttu-id="6ceb0-109">BizTalk Server 管理コンソールで物理ポートの構成</span><span class="sxs-lookup"><span data-stu-id="6ceb0-109">Physical port configuration in the BizTalk Server Administration console</span></span>  
  
 <span data-ttu-id="6ceb0-110">これらの相違点については、移行する BizTalk プロジェクトを作成前のバージョンの使用、SQLadapter 内のトピックで説明します。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-110">These differences are explained in the topics within Migrating BizTalk Projects Created Using the Previous Version of the SQLadapter.</span></span>  
  
 <span data-ttu-id="6ceb0-111">ただし、アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースで動作させるため[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-111">However, you can make changes to the BizTalk project that was created using the previous version of the adapter and make it work with the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 <span data-ttu-id="6ceb0-112">このチュートリアルでは、アダプターの以前のバージョンを使用して作成された既存の BizTalk プロジェクトに加える必要があります変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the previous version of the adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ceb0-113">ここでは簡略化のため、このチュートリアルでは、SQL アダプターの以前のバージョンを vPrev SQL アダプターと呼びます。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-113">In this tutorial, for the sake of brevity, the previous version of the SQL adapter will be referred to as vPrev SQL adapter.</span></span> <span data-ttu-id="6ceb0-114">同様に、vPrev SQL アダプターを使用する BizTalk プロジェクトが参照されます vPrev BizTalk プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-114">Similarly, a BizTalk project that uses the vPrev SQL adapter will be referred to as vPrev BizTalk project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6ceb0-115">このチュートリアルでは、SQL Server データベース テーブルの基本的な挿入操作を実行する vPrev SQL アダプター BizTalk プロジェクトを移行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-115">This tutorial provides guidance on how to migrate a vPrev SQL adapter BizTalk project that performs a basic insert operation on a SQL Server database table.</span></span> <span data-ttu-id="6ceb0-116">このチュートリアルでは新しい vPrev SQL アダプタからの移行に関するすべての可能なシナリオについては説明しません WCF ベース[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-116">This tutorial does not cover all possible scenarios for migration from the vPrev SQL adapter to the new WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="6ceb0-117">基盤としてこの移行のチュートリアルを使用して、既存のプロジェクトに関連する変更を加えるを適宜変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-117">You must use this migration tutorial as a foundation and modify accordingly to make changes that are relevant to your existing project.</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="6ceb0-118">チュートリアルでは、使用されるサンプル</span><span class="sxs-lookup"><span data-stu-id="6ceb0-118">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="6ceb0-119">このチュートリアルは、vPrev BizTalk プロジェクトを移行する方法を示すサンプル (SQL_Migration) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-119">This tutorial is based upon a sample (SQL_Migration) that demonstrates how to migrate a vPrev BizTalk project.</span></span> <span data-ttu-id="6ceb0-120">サンプルが付属して Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-120">The sample is provided with Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="6ceb0-121">詳細については、サンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-121">For more information, see Samples.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6ceb0-122">前提条件</span><span class="sxs-lookup"><span data-stu-id="6ceb0-122">Prerequisites</span></span>  
  
-   <span data-ttu-id="6ceb0-123">VPrev BizTalk プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-123">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="6ceb0-124">このチュートリアルには、SQL Server データベースの Customer テーブルに対して挿入操作を実行する BizTalk プロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-124">This tutorial involves a BizTalk project that performs an Insert operation on a Customer table in the SQL Server database.</span></span> <span data-ttu-id="6ceb0-125">Customer テーブルには、次のデザインがあります。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-125">The Customer table has the following design:</span></span>  
  
    |<span data-ttu-id="6ceb0-126">列名</span><span class="sxs-lookup"><span data-stu-id="6ceb0-126">Column Name</span></span>|<span data-ttu-id="6ceb0-127">Description</span><span class="sxs-lookup"><span data-stu-id="6ceb0-127">Description</span></span>|  
    |-----------------|-----------------|  
    |<span data-ttu-id="6ceb0-128">v_custid</span><span class="sxs-lookup"><span data-stu-id="6ceb0-128">v_custid</span></span>|<span data-ttu-id="6ceb0-129">主キー、整数型、id フィールド</span><span class="sxs-lookup"><span data-stu-id="6ceb0-129">Primary key, integer type, identity field</span></span>|  
    |<span data-ttu-id="6ceb0-130">名前</span><span class="sxs-lookup"><span data-stu-id="6ceb0-130">Name</span></span>|<span data-ttu-id="6ceb0-131">nchar(10) 型</span><span class="sxs-lookup"><span data-stu-id="6ceb0-131">nchar(10) type</span></span>|  
  
-   <span data-ttu-id="6ceb0-132">要求メッセージを vPrev SQL アダプターを使用して SQL Server データベースで挿入操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-132">You must have a request message to perform an Insert operation on the SQL Server database using the vPrev SQL adapter.</span></span> <span data-ttu-id="6ceb0-133">要求メッセージは、vPrev SQL アダプターを使用して生成する挿入操作のスキーマに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-133">The request message must conform to the schema of the Insert operation generated using the vPrev SQL adapter.</span></span>  
  
-   <span data-ttu-id="6ceb0-134">内の手順を完了する必要があります[Before You 開発 BizTalk Applications](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6)です。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-134">You should have completed the steps in [Before You Develop BizTalk Applications](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6).</span></span>  
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="6ceb0-135">アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-135">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="6ceb0-136">作成された vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-136">The key constituents of a vPrev BizTalk project created are:</span></span>  
  
-   <span data-ttu-id="6ceb0-137">**BizTalk オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-137">**BizTalk orchestration**.</span></span> <span data-ttu-id="6ceb0-138">これは、ポートの Wcf-custom を使用して SQL Server データベースに要求メッセージの送受信送信ファイルの場所からの要求メッセージを取得し、応答を受信、別のファイルの場所に保存する簡単なオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-138">This is a simple orchestration that picks request messages from a file location, sends the request message to the SQL Server database using a WCF-Custom send-receive port, receives the response, and saves it to another file location.</span></span>  
  
-   <span data-ttu-id="6ceb0-139">**SQL Server データベースで実行する操作のスキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-139">**Schema for the operation you wish to perform on the SQL Server database**.</span></span> <span data-ttu-id="6ceb0-140">このチュートリアルには、顧客テーブルに Insert 操作を実行する BizTalk プロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-140">This tutorial involves a BizTalk project that performs an Insert operation on the Customer table.</span></span> <span data-ttu-id="6ceb0-141">顧客テーブルに対して生成されたスキーマは、InsertCustomerService.xsd です。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-141">The schema generated for the Customer table is InsertCustomerService.xsd.</span></span> <span data-ttu-id="6ceb0-142">このスキーマは、vPrev SQL アダプターを使用して生成されます。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-142">This schema is generated using the vPrev SQL adapter.</span></span>  
  
-   <span data-ttu-id="6ceb0-143">**要求メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-143">**Request message**.</span></span> <span data-ttu-id="6ceb0-144">顧客テーブルに挿入操作を実行する要求メッセージ。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-144">The request message to perform an Insert operation on the Customer table.</span></span> <span data-ttu-id="6ceb0-145">要求メッセージのスキーマは、SQL アダプターの以前のバージョンで表示、挿入操作のスキーマに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-145">The schema of the request message conforms to the schema of the Insert operation as surfaced by the previous version of the SQL adapter.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="6ceb0-146">BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-146">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="6ceb0-147">この移行チュートリアルの目的は、WCF ベースに準拠したメッセージを処理できるだけ WCF カスタム ポートを使用して、vPrev SQL アダプターによって生成されたスキーマに準拠した要求メッセージを送信するために[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-147">The goal of this migration tutorial is to enable you to send a request message, which conforms to schema generated by vPrev SQL adapter, using a WCF-Custom port that can only process messages conforming to the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="6ceb0-148">そのため、簡単に言えば、移行練習では、WCF ベースに準拠していないメッセージを処理する WCF カスタム ポートを構成する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]のスキーマです。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-148">So, in short, the migration exercise involves configuring the WCF-Custom port to process messages that do not conform to the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]'s schema.</span></span>  
  
 <span data-ttu-id="6ceb0-149">ただし、WCF カスタム ポートを適切に構成できるようにするには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-149">However, to be able to configure the WCF-Custom port appropriately, you must perform the following tasks:</span></span>  
  
-   <span data-ttu-id="6ceb0-150">WCF ベースを使用して、Customer テーブルに対する挿入操作のメタデータを生成[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-150">Generate metadata for the Insert operation on the Customer table using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
-   <span data-ttu-id="6ceb0-151">WCF ベースを使用する挿入操作を実行するための要求メッセージに vPrev SQL アダプターを使用して挿入操作を実行するための要求メッセージにマップ[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-151">Map the request message for performing an Insert operation using the vPrev SQL adapter to a request message for performing an Insert operation using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
-   <span data-ttu-id="6ceb0-152">WCF ベースを使用して受信した応答メッセージをマップ[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]vPrev SQL アダプタの応答メッセージにします。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-152">Map the response message received using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to the response message for the vPrev SQL adapter.</span></span>  
  
-   <span data-ttu-id="6ceb0-153">WCF カスタム SQL を作成する送信の受信ポートの[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-153">Create a WCF-Custom SQL send-receive port in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
-   <span data-ttu-id="6ceb0-154">要求と応答のマッピングを使用する WCF カスタム ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-154">Configure the WCF-Custom port to use the request and response mappings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ceb0-155">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6ceb0-155">In This Section</span></span>  
  
-   [<span data-ttu-id="6ceb0-156">手順 1: vPrev SQL アダプターを使用して BizTalk プロジェクトを変更します。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-156">Step 1: Modify the vPrev BizTalk Project using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md)  
  
-   [<span data-ttu-id="6ceb0-157">手順 2: SQL アダプターを使用して BizTalk Server 管理コンソールでオーケストレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-157">Step 2: Configure the Orchestration in BizTalk Server Administration Console using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)  
  
-   [<span data-ttu-id="6ceb0-158">手順 3: SQL アダプターを使用する移行されたアプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="6ceb0-158">Step 3: Test the Migrated Application that uses the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="6ceb0-159">参照</span><span class="sxs-lookup"><span data-stu-id="6ceb0-159">See Also</span></span>  
 [<span data-ttu-id="6ceb0-160">SQL アダプタ チュートリアル</span><span class="sxs-lookup"><span data-stu-id="6ceb0-160">SQL Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md)