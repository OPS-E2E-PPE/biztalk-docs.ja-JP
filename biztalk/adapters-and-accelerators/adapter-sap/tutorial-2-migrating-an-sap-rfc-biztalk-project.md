---
title: 'チュートリアル 2: SAP の RFC BizTalk プロジェクトの移行 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, BizTalk project from previous version of the SAP adapter
- migration
- migrating, SAP RFC BizTalk project
ms.assetid: b4943613-23d2-4869-b033-ec07daabfac5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf741fdbbf996fa54c227cc879c850304413d25f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978987"
---
# <a name="tutorial-2-migrating-an-sap-rfc-biztalk-project"></a><span data-ttu-id="8c0be-102">チュートリアル 2: SAP の RFC BizTalk プロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="8c0be-102">Tutorial 2: Migrating an SAP RFC BizTalk Project</span></span>
<span data-ttu-id="8c0be-103">WCF ベースの Microsoft BizTalk Server に同梱されている SAP アダプターの以前のバージョンとは異なる[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]など、多くの点で。</span><span class="sxs-lookup"><span data-stu-id="8c0be-103">The previous version of the SAP adapter that shipped with Microsoft BizTalk Server differs from the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in many aspects, including:</span></span>  
  
- <span data-ttu-id="8c0be-104">BizTalk プロジェクトの作成、デザイン時エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="8c0be-104">The design-time experience of creating a BizTalk project.</span></span>  
  
- <span data-ttu-id="8c0be-105">メタデータの取得エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="8c0be-105">The metadata retrieval experience.</span></span>  
  
- <span data-ttu-id="8c0be-106">スキーマ ファイル名と名前空間。</span><span class="sxs-lookup"><span data-stu-id="8c0be-106">Schema file name and namespace.</span></span>  
  
- <span data-ttu-id="8c0be-107">データ型のマッピング。</span><span class="sxs-lookup"><span data-stu-id="8c0be-107">Data type mappings.</span></span>  
  
- <span data-ttu-id="8c0be-108">アダプターを使用して実行できる操作。</span><span class="sxs-lookup"><span data-stu-id="8c0be-108">The operations that can be performed using the adapter.</span></span>  
  
- <span data-ttu-id="8c0be-109">BizTalk Server 管理コンソールで物理ポートの構成。</span><span class="sxs-lookup"><span data-stu-id="8c0be-109">Physical port configuration in the BizTalk Server Administration console.</span></span>  
  
  <span data-ttu-id="8c0be-110">これらの相違点については、トピックで[を移行する BizTalk プロジェクト作成を使用して、前のバージョン、SAP アダプターの](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37)します。</span><span class="sxs-lookup"><span data-stu-id="8c0be-110">These differences are explained in the topics within [Migrating BizTalk Projects Created Using the Previous Version of the SAP Adapter](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37).</span></span>  
  
  <span data-ttu-id="8c0be-111">ただし、アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースと連携させるため[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8c0be-111">However, you can make changes to the BizTalk project created using the previous version of the adapter and make it work with the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
  <span data-ttu-id="8c0be-112">このチュートリアルでは、アダプターの以前のバージョンを使用して作成された既存の BizTalk プロジェクトにする必要があります変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c0be-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the previous version of the adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c0be-113">説明を簡潔にするため、このチュートリアルでは SAP アダプターの以前のバージョンを vPrev SAP アダプターとして指す場合は。</span><span class="sxs-lookup"><span data-stu-id="8c0be-113">In this tutorial, for the sake of brevity, the previous version of the SAP adapter will be referred to as vPrev SAP adapter.</span></span> <span data-ttu-id="8c0be-114">同様に、vPrev SAP アダプターを使用する BizTalk プロジェクトは vPrev BizTalk プロジェクトに参照されます。</span><span class="sxs-lookup"><span data-stu-id="8c0be-114">Similarly, a BizTalk project that uses the vPrev SAP adapter will be referred to as vPrev BizTalk project.</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="8c0be-115">このチュートリアルで使用されるサンプル</span><span class="sxs-lookup"><span data-stu-id="8c0be-115">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="8c0be-116">このチュートリアルは、SAP システムでの RFC を呼び出す vPrev BizTalk プロジェクトを移行する方法を示すサンプル (SAP_RFC_Migration) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="8c0be-116">This tutorial is based upon a sample (SAP_RFC_Migration) that demonstrates how to migrate a vPrev BizTalk project that invokes an RFC in an SAP system.</span></span> <span data-ttu-id="8c0be-117">サンプルが付属、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8c0be-117">The sample is provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="8c0be-118">詳細については、[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c0be-118">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8c0be-119">前提条件</span><span class="sxs-lookup"><span data-stu-id="8c0be-119">Prerequisites</span></span>  
  
-   <span data-ttu-id="8c0be-120">VPrev BizTalk プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="8c0be-120">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="8c0be-121">このチュートリアルでは、BizTalk プロジェクトを SD_RFC_CUSTOMER_GET RFC を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c0be-121">This tutorial involves a BizTalk project that invokes the SD_RFC_CUSTOMER_GET RFC.</span></span>  
  
-   <span data-ttu-id="8c0be-122">呼び出す vPrev SAP アダプターを使用して、SD_RFC_CUSTOMER_GET RFC を実行する要求メッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="8c0be-122">You must have a request message to perform to invoke the SD_RFC_CUSTOMER_GET RFC using the vPrev SAP adapter.</span></span> <span data-ttu-id="8c0be-123">要求メッセージは、RFC vPrev SAP アダプターを使用して生成のスキーマに準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c0be-123">The request message must conform to the schema of the RFC generated using the vPrev SAP adapter.</span></span> <span data-ttu-id="8c0be-124">このチュートリアルでは提供されたサンプルには、この要求メッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8c0be-124">The sample provided for this tutorial contains this request message.</span></span>  
  
-   [<span data-ttu-id="8c0be-125">厳密な名前のキー ファイルの作成と、ツールの説明</span><span class="sxs-lookup"><span data-stu-id="8c0be-125">Create strong-name key file, and learn the tools</span></span>](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="8c0be-126">アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。</span><span class="sxs-lookup"><span data-stu-id="8c0be-126">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="8c0be-127">RFC を呼び出す vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8c0be-127">The key constituents of a vPrev BizTalk project to invoke an RFC are:</span></span>  
  
-   <span data-ttu-id="8c0be-128">**BizTalk オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="8c0be-128">**BizTalk orchestration**.</span></span> <span data-ttu-id="8c0be-129">これは、簡単なオーケストレーション ポートに送信しますが、SAP を使用して SAP システムに要求メッセージの送信、受信ファイルの場所からの要求メッセージを取得し、応答を受信し、別のファイルの場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="8c0be-129">This is a simple orchestration that picks request messages from a file location, sends the request message to the SAP system using an SAP send-receive port, receives the response, and saves it to another file location.</span></span>  
  
-   <span data-ttu-id="8c0be-130">**SAP システムが呼び出す RFC のスキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="8c0be-130">**Schema for the RFC you want to invoke in the SAP system**.</span></span> <span data-ttu-id="8c0be-131">このチュートリアルでは、BizTalk プロジェクトを SD_RFC_CUSTOMER_GET RFC を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c0be-131">This tutorial involves a BizTalk project that invokes the SD_RFC_CUSTOMER_GET RFC.</span></span> <span data-ttu-id="8c0be-132">RFC に対して生成されたスキーマは、SD_RFC_CUSTOMER_GET__x32003.xsd です。</span><span class="sxs-lookup"><span data-stu-id="8c0be-132">The schema generated for the RFC is SD_RFC_CUSTOMER_GET__x32003.xsd.</span></span> <span data-ttu-id="8c0be-133">VPrev SAP アダプターを使用して、このスキーマが生成されます。</span><span class="sxs-lookup"><span data-stu-id="8c0be-133">This schema is generated using the vPrev SAP adapter.</span></span>  
  
-   <span data-ttu-id="8c0be-134">**要求メッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="8c0be-134">**Request message**.</span></span> <span data-ttu-id="8c0be-135">SD_RFC_CUSTOMER_GET RFC を呼び出す要求メッセージ。</span><span class="sxs-lookup"><span data-stu-id="8c0be-135">The request message to invoke the SD_RFC_CUSTOMER_GET RFC.</span></span> <span data-ttu-id="8c0be-136">要求メッセージのスキーマは vPrev SAP アダプター、SD_RFC_CUSTOMER_GET RFC のスキーマに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="8c0be-136">The schema of the request message conforms to the schema of the SD_RFC_CUSTOMER_GET RFC as surfaced by the vPrev SAP adapter.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="8c0be-137">BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。</span><span class="sxs-lookup"><span data-stu-id="8c0be-137">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="8c0be-138">この移行のチュートリアルの目的は WCF ベースに準拠したメッセージを処理できるだけ WCF カスタム ポートを使用して、vPrev SAP アダプターによって生成されたスキーマに準拠している要求メッセージを送信できるように、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8c0be-138">The goal of this migration tutorial is to enable you to send a request message, which conforms to schema generated by the vPrev SAP adapter, using a WCF-Custom port that can only process messages conforming to the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="8c0be-139">そのため、簡単に言えばの移行の練習では WCF ベースに準拠していないメッセージを処理する WCF カスタム ポートを構成する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]のスキーマ。</span><span class="sxs-lookup"><span data-stu-id="8c0be-139">So, in short, the migration exercise involves configuring the WCF-Custom port to process messages that do not conform to the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]'s schema.</span></span>  
  
 <span data-ttu-id="8c0be-140">ただし、WCF カスタム ポートを適切に構成できるようにするには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c0be-140">However, to be able to configure the WCF-Custom port appropriately, you must perform the following tasks:</span></span>  
  
- <span data-ttu-id="8c0be-141">WCF ベースを使用して、SD_RFC_CUSTOMER_GET RFC のメタデータを生成[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8c0be-141">Generate metadata for the SD_RFC_CUSTOMER_GET RFC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
- <span data-ttu-id="8c0be-142">WCF ベースを使用して、RFC を呼び出すための要求メッセージに vPrev SAP アダプターを使用して、RFC を呼び出すための要求メッセージにマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8c0be-142">Map the request message for invoking the RFC using the vPrev SAP adapter to a request message for invoking the RFC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
- <span data-ttu-id="8c0be-143">WCF ベースを使用して受信応答メッセージにマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]vPrev SAP アダプターの応答メッセージにします。</span><span class="sxs-lookup"><span data-stu-id="8c0be-143">Map the response message received using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to the response message for the vPrev SAP adapter.</span></span>  
  
- <span data-ttu-id="8c0be-144">Wcf-custom の SAP の作成、BizTalk Server 管理コンソールのポートの送信-受信します。</span><span class="sxs-lookup"><span data-stu-id="8c0be-144">Create a WCF-Custom SAP send-receive port in the BizTalk Server Administration console.</span></span>  
  
- <span data-ttu-id="8c0be-145">要求と応答のマッピングを使用する WCF カスタム ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="8c0be-145">Configure the WCF-Custom port to use the request and response mappings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c0be-146">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8c0be-146">In This Section</span></span>  
  
-   [<span data-ttu-id="8c0be-147">手順 1: RFC を呼び出すように vPrev BizTalk プロジェクトを変更する</span><span class="sxs-lookup"><span data-stu-id="8c0be-147">Step 1: Modify the vPrev BizTalk Project for Invoking an RFC</span></span>](../../adapters-and-accelerators/adapter-sap/step-1-modify-the-vprev-biztalk-project-for-invoking-an-rfc.md)  
  
-   [<span data-ttu-id="8c0be-148">手順 2: BizTalk Server 管理コンソールでオーケストレーションを構成する</span><span class="sxs-lookup"><span data-stu-id="8c0be-148">Step 2: Configure the Orchestration in BizTalk Server Administration Console</span></span>](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md)  
  
-   [<span data-ttu-id="8c0be-149">手順 3: 移行されたアプリケーションをテストする</span><span class="sxs-lookup"><span data-stu-id="8c0be-149">Step 3: Test the Migrated Application</span></span>](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md)  
  
## <a name="see-also"></a><span data-ttu-id="8c0be-150">参照</span><span class="sxs-lookup"><span data-stu-id="8c0be-150">See Also</span></span>  
 [<span data-ttu-id="8c0be-151">SAP アダプター チュートリアル</span><span class="sxs-lookup"><span data-stu-id="8c0be-151">SAP Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)