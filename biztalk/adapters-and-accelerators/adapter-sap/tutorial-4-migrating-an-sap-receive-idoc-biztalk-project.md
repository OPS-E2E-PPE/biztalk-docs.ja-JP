---
title: 'チュートリアル 4: 移行を SAP IDOC 受信 BizTalk プロジェクト |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, SAP Receive IDOC BizTalk project
- migrating, SAP Receive IDOC BizTalk project
- migration
ms.assetid: 74b667d8-2d8c-4c15-9dd2-f13521404b85
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e943c3663767d2b684b0f4657f639d752705b86f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011259"
---
# <a name="tutorial-4-migrating-an-sap-receive-idoc-biztalk-project"></a><span data-ttu-id="01f81-102">チュートリアル 4: 移行を SAP IDOC 受信 BizTalk プロジェクト</span><span class="sxs-lookup"><span data-stu-id="01f81-102">Tutorial 4: Migrating an SAP Receive IDOC BizTalk Project</span></span>
<span data-ttu-id="01f81-103">WCF ベースの Microsoft BizTalk Server に同梱されている SAP アダプターの以前のバージョンとは異なる[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]など、多くの点で。</span><span class="sxs-lookup"><span data-stu-id="01f81-103">The previous version of the SAP adapter that shipped with Microsoft BizTalk Server differs from the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in many aspects, including:</span></span>  
  
- <span data-ttu-id="01f81-104">BizTalk プロジェクトの作成、デザイン時エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="01f81-104">The design-time experience of creating a BizTalk project.</span></span>  
  
- <span data-ttu-id="01f81-105">メタデータの取得エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="01f81-105">The metadata retrieval experience.</span></span>  
  
- <span data-ttu-id="01f81-106">スキーマ ファイル名と名前空間。</span><span class="sxs-lookup"><span data-stu-id="01f81-106">Schema file name and namespace.</span></span>  
  
- <span data-ttu-id="01f81-107">データ型のマッピング。</span><span class="sxs-lookup"><span data-stu-id="01f81-107">Data type mappings.</span></span>  
  
- <span data-ttu-id="01f81-108">アダプターを使用して実行できる操作。</span><span class="sxs-lookup"><span data-stu-id="01f81-108">The operations that can be performed using the adapter.</span></span>  
  
- <span data-ttu-id="01f81-109">BizTalk Server 管理コンソールで物理ポートの構成。</span><span class="sxs-lookup"><span data-stu-id="01f81-109">Physical port configuration in the BizTalk Server Administration console.</span></span>  
  
  <span data-ttu-id="01f81-110">これらの相違点については、トピックで[を移行する BizTalk プロジェクト作成を使用して、前のバージョン、SAP アダプターの](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37)します。</span><span class="sxs-lookup"><span data-stu-id="01f81-110">These differences are explained in the topics within [Migrating BizTalk Projects Created Using the Previous Version of the SAP Adapter](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37).</span></span>  
  
  <span data-ttu-id="01f81-111">ただし、アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースと連携させるため[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="01f81-111">However, you can make changes to the BizTalk project created using the previous version of the adapter and make it work with the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
  <span data-ttu-id="01f81-112">このチュートリアルでは、アダプターの以前のバージョンを使用して作成された既存の BizTalk プロジェクトにする必要があります変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="01f81-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the previous version of the adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01f81-113">説明を簡潔にするため、このチュートリアルでは SAP アダプターの以前のバージョンを vPrev SAP アダプターとして指す場合は。</span><span class="sxs-lookup"><span data-stu-id="01f81-113">In this tutorial, for the sake of brevity, the previous version of the SAP adapter will be referred to as vPrev SAP adapter.</span></span> <span data-ttu-id="01f81-114">同様に、vPrev SAP アダプターを使用する BizTalk プロジェクトは vPrev BizTalk プロジェクトに参照されます。</span><span class="sxs-lookup"><span data-stu-id="01f81-114">Similarly, a BizTalk project that uses the vPrev SAP adapter will be referred to as vPrev BizTalk project.</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="01f81-115">このチュートリアルで使用されるサンプル</span><span class="sxs-lookup"><span data-stu-id="01f81-115">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="01f81-116">このチュートリアルは、SAP システムからフラット ファイル IDOC を受信する vPrev BizTalk プロジェクトを移行する方法を示すサンプル (ReceiveIDOC_Migration) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="01f81-116">This tutorial is based upon a sample (ReceiveIDOC_Migration) that demonstrates how to migrate a vPrev BizTalk project that receives a flat-file IDOC from an SAP system.</span></span> <span data-ttu-id="01f81-117">サンプルが付属、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="01f81-117">The sample is provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="01f81-118">詳細については、[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01f81-118">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="01f81-119">前提条件</span><span class="sxs-lookup"><span data-stu-id="01f81-119">Prerequisites</span></span>  
  
-   <span data-ttu-id="01f81-120">VPrev BizTalk プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="01f81-120">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="01f81-121">このチュートリアルには、SAP システムから ORDERS03 IDOC を受信する BizTalk プロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="01f81-121">This tutorial involves a BizTalk project that receives an ORDERS03 IDOC from an SAP system.</span></span>  
  
-   [<span data-ttu-id="01f81-122">厳密な名前のキー ファイルの作成と、ツールの説明</span><span class="sxs-lookup"><span data-stu-id="01f81-122">Create strong-name key file, and learn the tools</span></span>](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)

  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="01f81-123">アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。</span><span class="sxs-lookup"><span data-stu-id="01f81-123">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="01f81-124">IDOC を受信する vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="01f81-124">The key constituents of a vPrev BizTalk project to receive an IDOC are:</span></span>  
  
-   <span data-ttu-id="01f81-125">**BizTalk オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="01f81-125">**BizTalk orchestration**.</span></span> <span data-ttu-id="01f81-126">これは、単純な SAP で構成されるオーケストレーションの受信フラット ファイル IDOC を SAP システムから受信するポート。</span><span class="sxs-lookup"><span data-stu-id="01f81-126">This is a simple orchestration that consists of an SAP receive port that receives a flat-file IDOC from an SAP system.</span></span> <span data-ttu-id="01f81-127">BizTalk プロジェクトには、オーケストレーションで使用できるように、XML、フラット ファイル IDOC に変換するフラット ファイル逆アセンブラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="01f81-127">The BizTalk project contains a flat-file disassembler to convert the flat-file IDOC to an XML, so that it can be used in an orchestration.</span></span> <span data-ttu-id="01f81-128">で XML IDOC を file ポート経由のファイルの場所にコピーすると、前に、フラット ファイル アセンブラーを使用してフラット ファイル IDOC に変換されます。</span><span class="sxs-lookup"><span data-stu-id="01f81-128">Before the XML IDOC is copied to a file location through a file port, it is converted back into a flat-file IDOC using a flat-file assembler.</span></span>  
  
-   <span data-ttu-id="01f81-129">**SAP システムに送信する IDOC のスキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="01f81-129">**Schema for the IDOC you want to send to the SAP system**.</span></span> <span data-ttu-id="01f81-130">このチュートリアルには、SAP システムから ORDERS03 IDOC を受信する BizTalk プロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="01f81-130">This tutorial involves a BizTalk project that receives ORDERS03 IDOC from the SAP system.</span></span> <span data-ttu-id="01f81-131">IDOC に対して生成されたスキーマは、ORDERS03.xsd です。</span><span class="sxs-lookup"><span data-stu-id="01f81-131">The schema generated for the IDOC is ORDERS03.xsd.</span></span> <span data-ttu-id="01f81-132">VPrev SAP アダプターを使用して、このスキーマが生成されます。</span><span class="sxs-lookup"><span data-stu-id="01f81-132">This schema is generated using the vPrev SAP adapter.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="01f81-133">BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。</span><span class="sxs-lookup"><span data-stu-id="01f81-133">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="01f81-134">この移行のチュートリアルの目的は、vPrev SAP アダプターの送信ポートではなく Wcf-custom 送信ポートを使用して SAP システムからフラット ファイル IDOC を受信するためです。</span><span class="sxs-lookup"><span data-stu-id="01f81-134">The goal of this migration tutorial is to enable you to receive a flat-file IDOC from an SAP system using a WCF-Custom send port instead of the send port for the vPrev SAP adapter.</span></span> <span data-ttu-id="01f81-135">どのような設定は、Wcf-custom 送信ポートに必要な詳細については、前に、まず vPrev 送信 IDOC のオーケストレーションに必要などのような物理ポートを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01f81-135">Before understanding what settings are required for the WCF-Custom send port, you must first understand what physical ports are required for the vPrev send IDOC orchestration.</span></span>  
  
- <span data-ttu-id="01f81-136">VPrev SAP では、SAP システムからフラット ファイル IDOC を受信するポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="01f81-136">A vPrev SAP receive port that receives a flat-file IDOC from an SAP system.</span></span> <span data-ttu-id="01f81-137">ポートもこれに変換が使用可能なフラット ファイル逆アセンブラーを使用して XML IDOC vPrev BizTalk アプリケーションの一部として。</span><span class="sxs-lookup"><span data-stu-id="01f81-137">The port also converts this to an XML IDOC using a flat-file disassembler, which is available as part of the vPrev BizTalk application.</span></span> <span data-ttu-id="01f81-138">XML の IDOC は vPrev SAP アダプターを使用して作成されたスキーマ (ORDERS03.xsd) に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="01f81-138">The XML IDOC conforms to the schema (ORDERS03.xsd) that you generated using the vPrev SAP adapter.</span></span>  
  
- <span data-ttu-id="01f81-139">IDOC をフォルダーにコピーする file 送信ポート。</span><span class="sxs-lookup"><span data-stu-id="01f81-139">A file send port which copies the IDOC to folder.</span></span> <span data-ttu-id="01f81-140">また、このポートは、XML IDOC をフラット ファイル IDOC に変換するのに BizTalk アプリケーションで使用可能なフラット ファイル アセンブラー パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="01f81-140">This port also uses the flat-file assembler pipeline, available in the BizTalk application, to convert the XML IDOC to a flat-file IDOC.</span></span>  
  
  <span data-ttu-id="01f81-141">既存の vPrev BizTalk プロジェクトを移行するには、フラット ファイル IDOC をフォルダーにコピーする file 送信ポートを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="01f81-141">To migrate your existing vPrev BizTalk project, you do not need to change the file send port that copies the flat-file IDOC to a folder.</span></span> <span data-ttu-id="01f81-142">新しい構成するだけで済みます Wcf-custom 受信ポートを適切な構成設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="01f81-142">You only need to configure a new WCF-Custom receive port with the right configuration settings.</span></span> <span data-ttu-id="01f81-143">このチュートリアルは、Wcf-custom を構成する方法を示します受信 WCF ベースを使用して SAP システムから Idoc を受信するポート[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="01f81-143">This tutorial demonstrates how to configure the WCF-Custom receive port to receive IDOCs from an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="01f81-144">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="01f81-144">In This Section</span></span>  
  
-   [<span data-ttu-id="01f81-145">手順 1: IDOC を受信するための vPrev BizTalk プロジェクトを構築して展開する</span><span class="sxs-lookup"><span data-stu-id="01f81-145">Step 1: Build and Deploy the vPrev BizTalk Project for Receiving an IDOC</span></span>](../../adapters-and-accelerators/adapter-sap/step-1-build-and-deploy-the-vprev-biztalk-project-for-receiving-an-idoc.md)  
  
-   [<span data-ttu-id="01f81-146">手順 2: WCF-Custom の一方向の受信ポートを構成する</span><span class="sxs-lookup"><span data-stu-id="01f81-146">Step 2: Configure a WCF-Custom One-way Receive Port</span></span>](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md)  
  
-   [<span data-ttu-id="01f81-147">手順 3: 移行されたアプリケーションをテストする</span><span class="sxs-lookup"><span data-stu-id="01f81-147">Step 3: Test the Migrated Application</span></span>](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md)  
  
## <a name="see-also"></a><span data-ttu-id="01f81-148">参照</span><span class="sxs-lookup"><span data-stu-id="01f81-148">See Also</span></span>  
 [<span data-ttu-id="01f81-149">SAP アダプター チュートリアル</span><span class="sxs-lookup"><span data-stu-id="01f81-149">SAP Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)