---
title: 'チュートリアル 2: Siebel のプロジェクトを移行する BizTalk |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a2a1828-8cc8-4b80-99bd-c083c04e5d04
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ada19454c3d2aef1c725987d8d37f7b98a2d1c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996435"
---
# <a name="tutorial-2-migrating-biztalk-projects-in-siebel"></a><span data-ttu-id="b324e-102">チュートリアル 2: Siebel の BizTalk プロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="b324e-102">Tutorial 2: Migrating BizTalk Projects in Siebel</span></span>
<span data-ttu-id="b324e-103">WCF ベースの Microsoft BizTalk Server に付属する Siebel アダプターの以前のバージョンとは異なる[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]など、多くの点で。</span><span class="sxs-lookup"><span data-stu-id="b324e-103">The previous version of the Siebel adapter that shipped with Microsoft BizTalk Server differs from the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in many aspects, including:</span></span>  
  
- <span data-ttu-id="b324e-104">BizTalk プロジェクトの作成、デザイン時エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="b324e-104">The design-time experience of creating a BizTalk project.</span></span>  
  
- <span data-ttu-id="b324e-105">メタデータの取得エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="b324e-105">The metadata retrieval experience.</span></span>  
  
- <span data-ttu-id="b324e-106">スキーマ ファイル名と名前空間。</span><span class="sxs-lookup"><span data-stu-id="b324e-106">Schema file name and namespace.</span></span>  
  
- <span data-ttu-id="b324e-107">データ型のマッピング。</span><span class="sxs-lookup"><span data-stu-id="b324e-107">Data type mappings.</span></span>  
  
- <span data-ttu-id="b324e-108">アダプターを使用して実行できる操作。</span><span class="sxs-lookup"><span data-stu-id="b324e-108">The operations that can be performed using the adapter.</span></span>  
  
- <span data-ttu-id="b324e-109">BizTalk Server 管理コンソールで物理ポートの構成</span><span class="sxs-lookup"><span data-stu-id="b324e-109">Physical port configuration in the BizTalk Server Administration console</span></span>  
  
  <span data-ttu-id="b324e-110">これらの相違点については、トピックで[を移行する BizTalk プロジェクト作成を使用して前のバージョンの Siebel アダプター](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)します。</span><span class="sxs-lookup"><span data-stu-id="b324e-110">These differences are explained in the topics within [Migrating BizTalk Projects Created Using the Previous Version of the Siebel Adapter](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e).</span></span>  
  
  <span data-ttu-id="b324e-111">ただし、アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースと連携させるため[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b324e-111">However, you can make changes to the BizTalk project created using the previous version of the adapter and make it work with the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
  <span data-ttu-id="b324e-112">このチュートリアルでは、アダプターの以前のバージョンを使用して作成された既存の BizTalk プロジェクトにする必要があります変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="b324e-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the previous version of the adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b324e-113">説明を簡潔にするため、このチュートリアルでは、vPrev Siebel アダプターと Siebel アダプターの以前のバージョンに参照されます。</span><span class="sxs-lookup"><span data-stu-id="b324e-113">In this tutorial, for the sake of brevity, the previous version of the Siebel adapter will be referred to as vPrev Siebel adapter.</span></span> <span data-ttu-id="b324e-114">同様に、vPrev Siebel アダプターを使用する BizTalk プロジェクトは vPrev BizTalk プロジェクトとしてに参照されます。</span><span class="sxs-lookup"><span data-stu-id="b324e-114">Similarly, a BizTalk project that uses the vPrev Siebel adapter will be referred to as vPrev BizTalk project.</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="b324e-115">このチュートリアルで使用されるサンプル</span><span class="sxs-lookup"><span data-stu-id="b324e-115">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="b324e-116">このチュートリアルは、アカウントの Siebel ビジネス コンポーネントに対して、挿入操作を実行する vPrev BizTalk プロジェクトを移行する方法を示すサンプル (Siebel_BussComp_Migration) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="b324e-116">This tutorial is based upon a sample (Siebel_BussComp_Migration) that demonstrates how to migrate a vPrev BizTalk project that performs an Insert operation on the Account Siebel business component.</span></span> <span data-ttu-id="b324e-117">Microsoft とサンプルが提供される[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b324e-117">The sample is provided with Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="b324e-118">詳細については、[アダプター サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b324e-118">For more information, see [Adapter Sample](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b324e-119">前提条件</span><span class="sxs-lookup"><span data-stu-id="b324e-119">Prerequisites</span></span>  
  
-   <span data-ttu-id="b324e-120">VPrev BizTalk プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="b324e-120">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="b324e-121">このチュートリアルには、アカウントのビジネス コンポーネントに対して、挿入操作を実行する BizTalk プロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b324e-121">This tutorial involves a BizTalk project that performs an Insert operation on the Account business component.</span></span>  
  
-   <span data-ttu-id="b324e-122">VPrev Siebel アダプターを使用して、アカウントのビジネス コンポーネントに対して、挿入操作を実行する要求メッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="b324e-122">You must have a request message to perform an Insert operation on the Account business component using the vPrev Siebel adapter.</span></span> <span data-ttu-id="b324e-123">要求メッセージは、vPrev Siebel アダプターを使用して生成する挿入操作のスキーマに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b324e-123">The request message must conform to the schema of the Insert operation generated using the vPrev Siebel adapter.</span></span>  
  
-   <span data-ttu-id="b324e-124">」の手順を完了する必要があります[Siebel アプリケーションを作成するための必要条件](../../adapters-and-accelerators/adapter-siebel/prerequisites-to-create-siebel-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="b324e-124">You must have completed the steps in [Prerequisites to create Siebel applications](../../adapters-and-accelerators/adapter-siebel/prerequisites-to-create-siebel-applications.md).</span></span>  
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="b324e-125">アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。</span><span class="sxs-lookup"><span data-stu-id="b324e-125">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="b324e-126">作成された vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b324e-126">The key constituents of a vPrev BizTalk project created are:</span></span>  
  
- <span data-ttu-id="b324e-127">**BizTalk オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="b324e-127">**BizTalk orchestration**.</span></span> <span data-ttu-id="b324e-128">これは、ポートの送信、Siebel を使用して Siebel システムに要求メッセージの送信、受信ファイルの場所からの要求メッセージを取得し、応答を受信、ファイルの別の場所に保存する簡単なオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="b324e-128">This is a simple orchestration that picks request messages from a file location, sends the request message to the Siebel system using a Siebel send-receive port, receives the response, and saves it to another file location.</span></span>  
  
- <span data-ttu-id="b324e-129">**Siebel ビジネス コンポーネントに実行する操作のスキーマを**します。</span><span class="sxs-lookup"><span data-stu-id="b324e-129">**Schema for the operation you wish to perform on the Siebel business component**.</span></span> <span data-ttu-id="b324e-130">このチュートリアルには、アカウントのビジネス コンポーネントに対して、挿入操作を実行する BizTalk プロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b324e-130">This tutorial involves a BizTalk project that performs an Insert operation on the Account business component.</span></span> <span data-ttu-id="b324e-131">アカウントのビジネス コンポーネントに対して生成されたスキーマは、AccountService_Account_x5d.xsd です。</span><span class="sxs-lookup"><span data-stu-id="b324e-131">The schema generated for the Account business component is AccountService_Account_x5d.xsd.</span></span> <span data-ttu-id="b324e-132">VPrev の Siebel アダプターを使用して、このスキーマが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b324e-132">This schema is generated using the vPrev Siebel adapter.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="b324e-133">WCF ベースとは異なり[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]、vPrev Siebel アダプターは特定のビジネス コンポーネント操作のメタデータの生成をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b324e-133">Unlike the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], the vPrev Siebel adapter does not support generating metadata for specific operations on a business component.</span></span> <span data-ttu-id="b324e-134">既定では、アダプターは、ビジネス コンポーネントでサポートされているすべての操作のスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="b324e-134">By default, the adapter generates schema for all the operations supported on the business component.</span></span> <span data-ttu-id="b324e-135">はこのような違いについて vPrev Siebel アダプターと WCF ベース[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[を移行する BizTalk プロジェクト作成を使用して前のバージョンの Siebel アダプター](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)します。</span><span class="sxs-lookup"><span data-stu-id="b324e-135">For more such differences between the vPrev Siebel adapter and the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Migrating BizTalk Projects Created Using the Previous Version of the Siebel Adapter](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e).</span></span>  
  
- <span data-ttu-id="b324e-136">**要求メッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="b324e-136">**Request message**.</span></span> <span data-ttu-id="b324e-137">アカウントのビジネス コンポーネントに対して、挿入操作を実行する要求メッセージ。</span><span class="sxs-lookup"><span data-stu-id="b324e-137">The request message to perform an Insert operation on the Account business component.</span></span> <span data-ttu-id="b324e-138">要求メッセージのスキーマは vPrev Siebel アダプター、挿入操作のスキーマに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="b324e-138">The schema of the request message conforms to the schema of the Insert operation as surfaced by the vPrev Siebel adapter.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="b324e-139">BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。</span><span class="sxs-lookup"><span data-stu-id="b324e-139">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="b324e-140">この移行のチュートリアルの目的は WCF ベースに準拠したメッセージを処理できるだけ WCF カスタム ポートを使用して、vPrev Siebel アダプターによって生成されたスキーマに準拠している要求メッセージを送信できるように、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b324e-140">The goal of this migration tutorial is to enable you to send a request message, which conforms to schema generated by the vPrev Siebel adapter, using a WCF-Custom port that can only process messages conforming to the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="b324e-141">そのため、簡単に言えばの移行の練習では WCF ベースに準拠していないメッセージを処理する WCF カスタム ポートを構成する[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]のスキーマ。</span><span class="sxs-lookup"><span data-stu-id="b324e-141">So, in short, the migration exercise involves configuring the WCF-Custom port to process messages that do not conform to the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]'s schema.</span></span>  
  
 <span data-ttu-id="b324e-142">ただし、WCF カスタム ポートを適切に構成できるようにするには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b324e-142">However, to be able to configure the WCF-Custom port appropriately, you must perform the following tasks:</span></span>  
  
- <span data-ttu-id="b324e-143">WCF ベースを使用してアカウントのビジネス コンポーネントに対する挿入操作のメタデータを生成[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b324e-143">Generate metadata for the Insert operation on the Account business component using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
- <span data-ttu-id="b324e-144">WCF ベースを使用して挿入操作を実行するための vPrev Siebel アダプターの要求メッセージを使用して挿入操作を実行するための要求メッセージにマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b324e-144">Map the request message for performing an Insert operation using the vPrev Siebel adapter to a request message for performing an Insert operation using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
- <span data-ttu-id="b324e-145">WCF ベースを使用して受信応答メッセージにマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]vPrev Siebel アダプターの応答メッセージにします。</span><span class="sxs-lookup"><span data-stu-id="b324e-145">Map the response message received using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] to the response message for the vPrev Siebel adapter.</span></span>  
  
- <span data-ttu-id="b324e-146">Wcf-custom Siebel を作成、BizTalk Server 管理コンソールのポートの送信-受信します。</span><span class="sxs-lookup"><span data-stu-id="b324e-146">Create a WCF-Custom Siebel send-receive port in the BizTalk Server Administration console.</span></span>  
  
- <span data-ttu-id="b324e-147">要求と応答のマッピングを使用する WCF カスタム ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="b324e-147">Configure the WCF-Custom port to use the request and response mappings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b324e-148">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b324e-148">In This Section</span></span>  
  
-   [<span data-ttu-id="b324e-149">手順 1: vPrev BizTalk プロジェクトで Oracle データベースを変更します。</span><span class="sxs-lookup"><span data-stu-id="b324e-149">Step 1: Modify the vPrev BizTalk Project in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/step-1-modify-the-vprev-biztalk-project-in-oracle-database.md)  
  
-   [<span data-ttu-id="b324e-150">手順 2: ORacle データベース アダプターを使用する BizTalk Server 管理コンソールでオーケストレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="b324e-150">Step 2: Configure the Orchestration in BizTalk Server Administration Console to use the ORacle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md)  
  
-   [<span data-ttu-id="b324e-151">手順 3: Siebel アダプターを使用して移行されたアプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="b324e-151">Step 3: Test the Migrated Application with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="b324e-152">参照</span><span class="sxs-lookup"><span data-stu-id="b324e-152">See Also</span></span>  
 [<span data-ttu-id="b324e-153">Siebel アダプターのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="b324e-153">Siebel Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-siebel/siebel-adapter-tutorials.md)