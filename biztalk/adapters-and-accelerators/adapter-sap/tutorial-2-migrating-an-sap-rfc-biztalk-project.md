---
title: 'チュートリアル 2: SAP RFC の BizTalk プロジェクトの移行 |Microsoft ドキュメント'
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
ms.openlocfilehash: 80b5d53904b96267b1877310aa3480ce34a1bedc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218098"
---
# <a name="tutorial-2-migrating-an-sap-rfc-biztalk-project"></a><span data-ttu-id="47630-102">チュートリアル 2: SAP RFC の BizTalk プロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="47630-102">Tutorial 2: Migrating an SAP RFC BizTalk Project</span></span>
<span data-ttu-id="47630-103">Microsoft BizTalk Server に付属している SAP アダプターの以前のバージョンが WCF ベース異なる[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]など、多くの点で。</span><span class="sxs-lookup"><span data-stu-id="47630-103">The previous version of the SAP adapter that shipped with Microsoft BizTalk Server differs from the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in many aspects, including:</span></span>  
  
-   <span data-ttu-id="47630-104">デザイン時に、BizTalk プロジェクトを作成する操作。</span><span class="sxs-lookup"><span data-stu-id="47630-104">The design-time experience of creating a BizTalk project.</span></span>  
  
-   <span data-ttu-id="47630-105">メタデータの取得エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="47630-105">The metadata retrieval experience.</span></span>  
  
-   <span data-ttu-id="47630-106">スキーマ ファイル名と名前空間。</span><span class="sxs-lookup"><span data-stu-id="47630-106">Schema file name and namespace.</span></span>  
  
-   <span data-ttu-id="47630-107">データは、マッピングを入力します。</span><span class="sxs-lookup"><span data-stu-id="47630-107">Data type mappings.</span></span>  
  
-   <span data-ttu-id="47630-108">アダプターを使用して実行できる操作です。</span><span class="sxs-lookup"><span data-stu-id="47630-108">The operations that can be performed using the adapter.</span></span>  
  
-   <span data-ttu-id="47630-109">BizTalk Server 管理コンソールで物理ポートの構成。</span><span class="sxs-lookup"><span data-stu-id="47630-109">Physical port configuration in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="47630-110">これらの相違点が含まれるトピックで説明した[を移行する BizTalk プロジェクト作成を使用して、前のバージョンの SAP アダプター](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37)です。</span><span class="sxs-lookup"><span data-stu-id="47630-110">These differences are explained in the topics within [Migrating BizTalk Projects Created Using the Previous Version of the SAP Adapter](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37).</span></span>  
  
 <span data-ttu-id="47630-111">ただし、アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースで動作させるため[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="47630-111">However, you can make changes to the BizTalk project created using the previous version of the adapter and make it work with the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
 <span data-ttu-id="47630-112">このチュートリアルでは、アダプターの以前のバージョンを使用して作成された既存の BizTalk プロジェクトに加える必要があります変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="47630-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the previous version of the adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47630-113">ここでは簡略化のため、このチュートリアルでは、SAP アダプターの以前のバージョンを vPrev SAP アダプターと呼びます。</span><span class="sxs-lookup"><span data-stu-id="47630-113">In this tutorial, for the sake of brevity, the previous version of the SAP adapter will be referred to as vPrev SAP adapter.</span></span> <span data-ttu-id="47630-114">同様に、vPrev SAP アダプターを使用する BizTalk プロジェクトが参照されます vPrev BizTalk プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="47630-114">Similarly, a BizTalk project that uses the vPrev SAP adapter will be referred to as vPrev BizTalk project.</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="47630-115">チュートリアルでは、使用されるサンプル</span><span class="sxs-lookup"><span data-stu-id="47630-115">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="47630-116">このチュートリアルは、SAP システムで RFC を呼び出す vPrev BizTalk プロジェクトを移行する方法を示すサンプル (SAP_RFC_Migration) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="47630-116">This tutorial is based upon a sample (SAP_RFC_Migration) that demonstrates how to migrate a vPrev BizTalk project that invokes an RFC in an SAP system.</span></span> <span data-ttu-id="47630-117">サンプルが付属して、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="47630-117">The sample is provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="47630-118">詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。</span><span class="sxs-lookup"><span data-stu-id="47630-118">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="47630-119">前提条件</span><span class="sxs-lookup"><span data-stu-id="47630-119">Prerequisites</span></span>  
  
-   <span data-ttu-id="47630-120">VPrev BizTalk プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="47630-120">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="47630-121">このチュートリアルでは、BizTalk プロジェクトを SD_RFC_CUSTOMER_GET RFC を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="47630-121">This tutorial involves a BizTalk project that invokes the SD_RFC_CUSTOMER_GET RFC.</span></span>  
  
-   <span data-ttu-id="47630-122">呼び出す vPrev SAP アダプターを使用して SD_RFC_CUSTOMER_GET RFC を実行する要求メッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="47630-122">You must have a request message to perform to invoke the SD_RFC_CUSTOMER_GET RFC using the vPrev SAP adapter.</span></span> <span data-ttu-id="47630-123">要求メッセージは、vPrev SAP アダプターを使用して生成された RFC のスキーマに準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47630-123">The request message must conform to the schema of the RFC generated using the vPrev SAP adapter.</span></span> <span data-ttu-id="47630-124">このチュートリアルで提供されたサンプルには、この要求メッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="47630-124">The sample provided for this tutorial contains this request message.</span></span>  
  
-   [<span data-ttu-id="47630-125">厳密な名前キー ファイルを作成し、ツールの説明</span><span class="sxs-lookup"><span data-stu-id="47630-125">Create strong-name key file, and learn the tools</span></span>](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="47630-126">アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。</span><span class="sxs-lookup"><span data-stu-id="47630-126">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="47630-127">呼び出す RFC vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="47630-127">The key constituents of a vPrev BizTalk project to invoke an RFC are:</span></span>  
  
-   <span data-ttu-id="47630-128">**BizTalk オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="47630-128">**BizTalk orchestration**.</span></span> <span data-ttu-id="47630-129">これは、ポートの送信、SAP を使用して SAP システムに要求メッセージの送信、受信ファイルの場所からの要求メッセージを取得し、応答を受信、別のファイルの場所に保存する簡単なオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="47630-129">This is a simple orchestration that picks request messages from a file location, sends the request message to the SAP system using an SAP send-receive port, receives the response, and saves it to another file location.</span></span>  
  
-   <span data-ttu-id="47630-130">**スキーマの SAP システムで、呼び出し先 RFC**です。</span><span class="sxs-lookup"><span data-stu-id="47630-130">**Schema for the RFC you want to invoke in the SAP system**.</span></span> <span data-ttu-id="47630-131">このチュートリアルでは、BizTalk プロジェクトを SD_RFC_CUSTOMER_GET RFC を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="47630-131">This tutorial involves a BizTalk project that invokes the SD_RFC_CUSTOMER_GET RFC.</span></span> <span data-ttu-id="47630-132">RFC に対して生成されたスキーマは、SD_RFC_CUSTOMER_GET__x32003.xsd です。</span><span class="sxs-lookup"><span data-stu-id="47630-132">The schema generated for the RFC is SD_RFC_CUSTOMER_GET__x32003.xsd.</span></span> <span data-ttu-id="47630-133">このスキーマは、vPrev SAP アダプターを使用して生成されます。</span><span class="sxs-lookup"><span data-stu-id="47630-133">This schema is generated using the vPrev SAP adapter.</span></span>  
  
-   <span data-ttu-id="47630-134">**要求メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="47630-134">**Request message**.</span></span> <span data-ttu-id="47630-135">SD_RFC_CUSTOMER_GET RFC を起動する要求メッセージ。</span><span class="sxs-lookup"><span data-stu-id="47630-135">The request message to invoke the SD_RFC_CUSTOMER_GET RFC.</span></span> <span data-ttu-id="47630-136">要求メッセージのスキーマは vPrev SAP アダプター側に表示される、SD_RFC_CUSTOMER_GET RFC のスキーマに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="47630-136">The schema of the request message conforms to the schema of the SD_RFC_CUSTOMER_GET RFC as surfaced by the vPrev SAP adapter.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="47630-137">BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。</span><span class="sxs-lookup"><span data-stu-id="47630-137">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="47630-138">この移行チュートリアルの目的は、WCF ベースに準拠したメッセージを処理できるだけ WCF カスタム ポートを使用して、vPrev SAP アダプターによって生成されたスキーマに準拠した要求メッセージを送信するために[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="47630-138">The goal of this migration tutorial is to enable you to send a request message, which conforms to schema generated by the vPrev SAP adapter, using a WCF-Custom port that can only process messages conforming to the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="47630-139">そのため、簡単に言えば、移行練習では、WCF ベースに準拠していないメッセージを処理する WCF カスタム ポートを構成する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]のスキーマです。</span><span class="sxs-lookup"><span data-stu-id="47630-139">So, in short, the migration exercise involves configuring the WCF-Custom port to process messages that do not conform to the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]'s schema.</span></span>  
  
 <span data-ttu-id="47630-140">ただし、WCF カスタム ポートを適切に構成できるようにするには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47630-140">However, to be able to configure the WCF-Custom port appropriately, you must perform the following tasks:</span></span>  
  
-   <span data-ttu-id="47630-141">WCF ベースを使用して SD_RFC_CUSTOMER_GET RFC のメタデータを生成する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="47630-141">Generate metadata for the SD_RFC_CUSTOMER_GET RFC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
-   <span data-ttu-id="47630-142">WCF ベースを使用して、RFC を呼び出すための要求メッセージに vPrev SAP アダプターを使用して、RFC を呼び出すための要求メッセージにマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="47630-142">Map the request message for invoking the RFC using the vPrev SAP adapter to a request message for invoking the RFC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
-   <span data-ttu-id="47630-143">WCF ベースを使用して受信した応答メッセージをマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]vPrev SAP アダプターの応答メッセージにします。</span><span class="sxs-lookup"><span data-stu-id="47630-143">Map the response message received using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to the response message for the vPrev SAP adapter.</span></span>  
  
-   <span data-ttu-id="47630-144">Wcf-custom SAP を作成する BizTalk Server 管理コンソールでポートを送信受信します。</span><span class="sxs-lookup"><span data-stu-id="47630-144">Create a WCF-Custom SAP send-receive port in the BizTalk Server Administration console.</span></span>  
  
-   <span data-ttu-id="47630-145">要求と応答のマッピングを使用する WCF カスタム ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="47630-145">Configure the WCF-Custom port to use the request and response mappings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="47630-146">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="47630-146">In This Section</span></span>  
  
-   [<span data-ttu-id="47630-147">手順 1: RFC を呼び出すため vPrev BizTalk プロジェクトを変更します。</span><span class="sxs-lookup"><span data-stu-id="47630-147">Step 1: Modify the vPrev BizTalk Project for Invoking an RFC</span></span>](../../adapters-and-accelerators/adapter-sap/step-1-modify-the-vprev-biztalk-project-for-invoking-an-rfc.md)  
  
-   [<span data-ttu-id="47630-148">手順 2: BizTalk Server 管理コンソールでオーケストレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="47630-148">Step 2: Configure the Orchestration in BizTalk Server Administration Console</span></span>](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md)  
  
-   [<span data-ttu-id="47630-149">手順 3: 移行後のアプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="47630-149">Step 3: Test the Migrated Application</span></span>](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md)  
  
## <a name="see-also"></a><span data-ttu-id="47630-150">参照</span><span class="sxs-lookup"><span data-stu-id="47630-150">See Also</span></span>  
 [<span data-ttu-id="47630-151">SAP アダプタ チュートリアル</span><span class="sxs-lookup"><span data-stu-id="47630-151">SAP Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)