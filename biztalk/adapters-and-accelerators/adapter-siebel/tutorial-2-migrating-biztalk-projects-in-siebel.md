---
title: "チュートリアル 2: Siebel に移行する BizTalk プロジェクトの |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a2a1828-8cc8-4b80-99bd-c083c04e5d04
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b8d138d348e750102d82a4aba2e39bc7d119c8c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-2-migrating-biztalk-projects-in-siebel"></a><span data-ttu-id="0902c-102">チュートリアル 2: Siebel の BizTalk プロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="0902c-102">Tutorial 2: Migrating BizTalk Projects in Siebel</span></span>
<span data-ttu-id="0902c-103">Microsoft BizTalk Server に付属している Siebel アダプターの以前のバージョンが WCF ベース異なる[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]など、多くの点で。</span><span class="sxs-lookup"><span data-stu-id="0902c-103">The previous version of the Siebel adapter that shipped with Microsoft BizTalk Server differs from the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in many aspects, including:</span></span>  
  
-   <span data-ttu-id="0902c-104">デザイン時に、BizTalk プロジェクトを作成する操作。</span><span class="sxs-lookup"><span data-stu-id="0902c-104">The design-time experience of creating a BizTalk project.</span></span>  
  
-   <span data-ttu-id="0902c-105">メタデータの取得エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="0902c-105">The metadata retrieval experience.</span></span>  
  
-   <span data-ttu-id="0902c-106">スキーマ ファイル名と名前空間。</span><span class="sxs-lookup"><span data-stu-id="0902c-106">Schema file name and namespace.</span></span>  
  
-   <span data-ttu-id="0902c-107">データは、マッピングを入力します。</span><span class="sxs-lookup"><span data-stu-id="0902c-107">Data type mappings.</span></span>  
  
-   <span data-ttu-id="0902c-108">アダプターを使用して実行できる操作です。</span><span class="sxs-lookup"><span data-stu-id="0902c-108">The operations that can be performed using the adapter.</span></span>  
  
-   <span data-ttu-id="0902c-109">BizTalk Server 管理コンソールで物理ポートの構成</span><span class="sxs-lookup"><span data-stu-id="0902c-109">Physical port configuration in the BizTalk Server Administration console</span></span>  
  
 <span data-ttu-id="0902c-110">これらの相違点が含まれるトピックで説明した[を移行する BizTalk プロジェクト作成を使用して、前のバージョンの Siebel アダプター](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)です。</span><span class="sxs-lookup"><span data-stu-id="0902c-110">These differences are explained in the topics within [Migrating BizTalk Projects Created Using the Previous Version of the Siebel Adapter](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e).</span></span>  
  
 <span data-ttu-id="0902c-111">ただし、アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースで動作させるため[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="0902c-111">However, you can make changes to the BizTalk project created using the previous version of the adapter and make it work with the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
 <span data-ttu-id="0902c-112">このチュートリアルでは、アダプターの以前のバージョンを使用して作成された既存の BizTalk プロジェクトに加える必要があります変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="0902c-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the previous version of the adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0902c-113">ここでは簡略化のため、このチュートリアルでは、Siebel アダプターの以前のバージョンを vPrev Siebel アダプターと呼びます。</span><span class="sxs-lookup"><span data-stu-id="0902c-113">In this tutorial, for the sake of brevity, the previous version of the Siebel adapter will be referred to as vPrev Siebel adapter.</span></span> <span data-ttu-id="0902c-114">同様に、vPrev Siebel アダプターを使用する BizTalk プロジェクトが参照されます vPrev BizTalk プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="0902c-114">Similarly, a BizTalk project that uses the vPrev Siebel adapter will be referred to as vPrev BizTalk project.</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="0902c-115">チュートリアルでは、使用されるサンプル</span><span class="sxs-lookup"><span data-stu-id="0902c-115">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="0902c-116">このチュートリアルは、アカウントの Siebel ビジネス コンポーネントで挿入操作を実行する BizTalk プロジェクトを vPrev 移行する方法を示すサンプル (Siebel_BussComp_Migration) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="0902c-116">This tutorial is based upon a sample (Siebel_BussComp_Migration) that demonstrates how to migrate a vPrev BizTalk project that performs an Insert operation on the Account Siebel business component.</span></span> <span data-ttu-id="0902c-117">サンプルが付属して Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="0902c-117">The sample is provided with Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="0902c-118">詳細については、次を参照してください。[アダプター サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。</span><span class="sxs-lookup"><span data-stu-id="0902c-118">For more information, see [Adapter Sample](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0902c-119">前提条件</span><span class="sxs-lookup"><span data-stu-id="0902c-119">Prerequisites</span></span>  
  
-   <span data-ttu-id="0902c-120">VPrev BizTalk プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="0902c-120">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="0902c-121">このチュートリアルには、アカウントのビジネス コンポーネントで挿入操作を実行する BizTalk プロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0902c-121">This tutorial involves a BizTalk project that performs an Insert operation on the Account business component.</span></span>  
  
-   <span data-ttu-id="0902c-122">VPrev Siebel アダプターを使用してアカウントのビジネス コンポーネントで挿入操作を実行する要求メッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="0902c-122">You must have a request message to perform an Insert operation on the Account business component using the vPrev Siebel adapter.</span></span> <span data-ttu-id="0902c-123">要求メッセージは、vPrev Siebel アダプターを使用して生成する挿入操作のスキーマに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0902c-123">The request message must conform to the schema of the Insert operation generated using the vPrev Siebel adapter.</span></span>  
  
-   <span data-ttu-id="0902c-124">内の手順を完了する必要があります[Siebel アプリケーションを作成するための必要条件](../../adapters-and-accelerators/adapter-siebel/prerequisites-to-create-siebel-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="0902c-124">You must have completed the steps in [Prerequisites to create Siebel applications](../../adapters-and-accelerators/adapter-siebel/prerequisites-to-create-siebel-applications.md).</span></span>  
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="0902c-125">アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。</span><span class="sxs-lookup"><span data-stu-id="0902c-125">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="0902c-126">作成された vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0902c-126">The key constituents of a vPrev BizTalk project created are:</span></span>  
  
-   <span data-ttu-id="0902c-127">**BizTalk オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="0902c-127">**BizTalk orchestration**.</span></span> <span data-ttu-id="0902c-128">これは、ポートの送信、Siebel を使用して、Siebel システムに要求メッセージの送信、受信ファイルの場所からの要求メッセージを取得し、応答を受信、別のファイルの場所に保存する簡単なオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="0902c-128">This is a simple orchestration that picks request messages from a file location, sends the request message to the Siebel system using a Siebel send-receive port, receives the response, and saves it to another file location.</span></span>  
  
-   <span data-ttu-id="0902c-129">**Siebel ビジネス コンポーネントで実行する操作のスキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="0902c-129">**Schema for the operation you wish to perform on the Siebel business component**.</span></span> <span data-ttu-id="0902c-130">このチュートリアルには、アカウントのビジネス コンポーネントで挿入操作を実行する BizTalk プロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0902c-130">This tutorial involves a BizTalk project that performs an Insert operation on the Account business component.</span></span> <span data-ttu-id="0902c-131">アカウントのビジネス コンポーネントに対して生成されたスキーマは、AccountService_Account_x5d.xsd です。</span><span class="sxs-lookup"><span data-stu-id="0902c-131">The schema generated for the Account business component is AccountService_Account_x5d.xsd.</span></span> <span data-ttu-id="0902c-132">このスキーマは、vPrev Siebel アダプターを使用して生成されます。</span><span class="sxs-lookup"><span data-stu-id="0902c-132">This schema is generated using the vPrev Siebel adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0902c-133">WCF ベースとは異なり[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]、vPrev Siebel アダプターはビジネス コンポーネントで特定の操作を生成するメタデータをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="0902c-133">Unlike the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], the vPrev Siebel adapter does not support generating metadata for specific operations on a business component.</span></span> <span data-ttu-id="0902c-134">既定では、アダプターは、ビジネス コンポーネントでサポートされるすべての操作のスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="0902c-134">By default, the adapter generates schema for all the operations supported on the business component.</span></span> <span data-ttu-id="0902c-135">このような複数 vPrev Siebel アダプターと WCF ベースの違いの[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[を移行する BizTalk プロジェクト作成を使用して、前のバージョンの Siebel アダプター](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)です。</span><span class="sxs-lookup"><span data-stu-id="0902c-135">For more such differences between the vPrev Siebel adapter and the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Migrating BizTalk Projects Created Using the Previous Version of the Siebel Adapter](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e).</span></span>  
  
-   <span data-ttu-id="0902c-136">**要求メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="0902c-136">**Request message**.</span></span> <span data-ttu-id="0902c-137">アカウントのビジネス コンポーネントで挿入操作を実行する要求メッセージ。</span><span class="sxs-lookup"><span data-stu-id="0902c-137">The request message to perform an Insert operation on the Account business component.</span></span> <span data-ttu-id="0902c-138">要求メッセージのスキーマは vPrev Siebel アダプター側に表示される、挿入操作のスキーマに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="0902c-138">The schema of the request message conforms to the schema of the Insert operation as surfaced by the vPrev Siebel adapter.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="0902c-139">BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。</span><span class="sxs-lookup"><span data-stu-id="0902c-139">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="0902c-140">この移行チュートリアルの目的は、WCF ベースに準拠したメッセージを処理できるだけ WCF カスタム ポートを使用して、vPrev Siebel アダプターによって生成されたスキーマに準拠した要求メッセージを送信するために[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="0902c-140">The goal of this migration tutorial is to enable you to send a request message, which conforms to schema generated by the vPrev Siebel adapter, using a WCF-Custom port that can only process messages conforming to the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="0902c-141">そのため、簡単に言えば、移行練習では、WCF ベースに準拠していないメッセージを処理する WCF カスタム ポートを構成する[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]のスキーマです。</span><span class="sxs-lookup"><span data-stu-id="0902c-141">So, in short, the migration exercise involves configuring the WCF-Custom port to process messages that do not conform to the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]'s schema.</span></span>  
  
 <span data-ttu-id="0902c-142">ただし、WCF カスタム ポートを適切に構成できるようにするには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0902c-142">However, to be able to configure the WCF-Custom port appropriately, you must perform the following tasks:</span></span>  
  
-   <span data-ttu-id="0902c-143">WCF ベースを使用してアカウントのビジネス コンポーネントに対する挿入操作のメタデータを生成[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="0902c-143">Generate metadata for the Insert operation on the Account business component using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
-   <span data-ttu-id="0902c-144">WCF ベースを使用する挿入操作を実行するための要求メッセージに vPrev Siebel アダプターを使用して挿入操作を実行するための要求メッセージにマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="0902c-144">Map the request message for performing an Insert operation using the vPrev Siebel adapter to a request message for performing an Insert operation using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
-   <span data-ttu-id="0902c-145">WCF ベースを使用して受信した応答メッセージをマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]vPrev Siebel アダプターの応答メッセージにします。</span><span class="sxs-lookup"><span data-stu-id="0902c-145">Map the response message received using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] to the response message for the vPrev Siebel adapter.</span></span>  
  
-   <span data-ttu-id="0902c-146">Wcf-custom Siebel の作成、BizTalk Server 管理コンソールのポートの送信受信します。</span><span class="sxs-lookup"><span data-stu-id="0902c-146">Create a WCF-Custom Siebel send-receive port in the BizTalk Server Administration console.</span></span>  
  
-   <span data-ttu-id="0902c-147">要求と応答のマッピングを使用する WCF カスタム ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="0902c-147">Configure the WCF-Custom port to use the request and response mappings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0902c-148">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0902c-148">In This Section</span></span>  
  
-   [<span data-ttu-id="0902c-149">手順 1: vPrev Oracle データベースでの BizTalk プロジェクトを変更します。</span><span class="sxs-lookup"><span data-stu-id="0902c-149">Step 1: Modify the vPrev BizTalk Project in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/step-1-modify-the-vprev-biztalk-project-in-oracle-database.md)  
  
-   [<span data-ttu-id="0902c-150">手順 2: ORacle データベース アダプターを使用する BizTalk Server 管理コンソールでオーケストレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="0902c-150">Step 2: Configure the Orchestration in BizTalk Server Administration Console to use the ORacle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md)  
  
-   [<span data-ttu-id="0902c-151">手順 3: Siebel アダプターを使用して移行されたアプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="0902c-151">Step 3: Test the Migrated Application with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="0902c-152">参照</span><span class="sxs-lookup"><span data-stu-id="0902c-152">See Also</span></span>  
 [<span data-ttu-id="0902c-153">Siebel アダプタ チュートリアル</span><span class="sxs-lookup"><span data-stu-id="0902c-153">Siebel Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-siebel/siebel-adapter-tutorials.md)