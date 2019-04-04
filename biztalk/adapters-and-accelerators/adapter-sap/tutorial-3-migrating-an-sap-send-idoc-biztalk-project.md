---
title: 'チュートリアル 3: SAP を移行する IDOC の BizTalk プロジェクトの送信 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, SAP Send IDOC BizTalk project
- migration
ms.assetid: c0a11432-5388-4054-8996-08a957cc02eb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9aaf4fae9afaad2900f0354aec9f1eeb3f3de0ee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966451"
---
# <a name="tutorial-3-migrating-an-sap-send-idoc-biztalk-project"></a><span data-ttu-id="24c0d-102">チュートリアル 3: を SAP IDOC 送信 BizTalk プロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="24c0d-102">Tutorial 3: Migrating an SAP Send IDOC BizTalk Project</span></span>
<span data-ttu-id="24c0d-103">WCF ベースの Microsoft BizTalk Server に同梱されている SAP アダプターの以前のバージョンとは異なる[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]など、多くの点で。</span><span class="sxs-lookup"><span data-stu-id="24c0d-103">The previous version of the SAP adapter that shipped with Microsoft BizTalk Server differs from the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in many aspects, including:</span></span>  
  
- <span data-ttu-id="24c0d-104">BizTalk プロジェクトの作成、デザイン時エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="24c0d-104">The design-time experience of creating a BizTalk project.</span></span>  
  
- <span data-ttu-id="24c0d-105">メタデータの取得エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="24c0d-105">The metadata retrieval experience.</span></span>  
  
- <span data-ttu-id="24c0d-106">スキーマ ファイル名と名前空間。</span><span class="sxs-lookup"><span data-stu-id="24c0d-106">Schema file name and namespace.</span></span>  
  
- <span data-ttu-id="24c0d-107">データ型のマッピング。</span><span class="sxs-lookup"><span data-stu-id="24c0d-107">Data type mappings.</span></span>  
  
- <span data-ttu-id="24c0d-108">アダプターを使用して実行できる操作。</span><span class="sxs-lookup"><span data-stu-id="24c0d-108">The operations that can be performed using the adapter.</span></span>  
  
- <span data-ttu-id="24c0d-109">BizTalk Server 管理コンソールで物理ポートの構成。</span><span class="sxs-lookup"><span data-stu-id="24c0d-109">Physical port configuration in the BizTalk Server Administration console.</span></span>  
  
  <span data-ttu-id="24c0d-110">これらの相違点については、トピックで[を移行する BizTalk プロジェクト作成を使用して、前のバージョン、SAP アダプターの](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37)します。</span><span class="sxs-lookup"><span data-stu-id="24c0d-110">These differences are explained in the topics within [Migrating BizTalk Projects Created Using the Previous Version of the SAP Adapter](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37).</span></span>  
  
  <span data-ttu-id="24c0d-111">ただし、アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースと連携させるため[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="24c0d-111">However, you can make changes to the BizTalk project created using the previous version of the adapter and make it work with the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
  <span data-ttu-id="24c0d-112">このチュートリアルでは、アダプターの以前のバージョンを使用して作成された既存の BizTalk プロジェクトにする必要があります変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="24c0d-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the previous version of the adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24c0d-113">説明を簡潔にするため、このチュートリアルでは SAP アダプターの以前のバージョンを vPrev SAP アダプターとして指す場合は。</span><span class="sxs-lookup"><span data-stu-id="24c0d-113">In this tutorial, for the sake of brevity, the previous version of the SAP adapter will be referred to as vPrev SAP adapter.</span></span> <span data-ttu-id="24c0d-114">同様に、vPrev SAP アダプターを使用する BizTalk プロジェクトは vPrev BizTalk プロジェクトに参照されます。</span><span class="sxs-lookup"><span data-stu-id="24c0d-114">Similarly, a BizTalk project that uses the vPrev SAP adapter will be referred to as vPrev BizTalk project.</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="24c0d-115">このチュートリアルで使用されるサンプル</span><span class="sxs-lookup"><span data-stu-id="24c0d-115">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="24c0d-116">このチュートリアルは、SAP システムに IDOC を送信する vPrev BizTalk プロジェクトを移行する方法を示すサンプル (SendIDOC_Migration) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="24c0d-116">This tutorial is based upon a sample (SendIDOC_Migration) that demonstrates how to migrate a vPrev BizTalk project that sends an IDOC to an SAP system.</span></span> <span data-ttu-id="24c0d-117">サンプルが付属、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="24c0d-117">The sample is provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="24c0d-118">詳細については、[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24c0d-118">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="24c0d-119">前提条件</span><span class="sxs-lookup"><span data-stu-id="24c0d-119">Prerequisites</span></span>  
  
-   <span data-ttu-id="24c0d-120">VPrev BizTalk プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="24c0d-120">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="24c0d-121">このチュートリアルには、SAP システムに BOMDOC IDOC を送信する BizTalk プロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="24c0d-121">This tutorial involves a BizTalk project that sends a BOMDOC IDOC to an SAP system.</span></span>  
  
-   <span data-ttu-id="24c0d-122">VPrev SAP アダプターを使用して、SAP システムに送信するフラットファイル BOMDOC IDOC が必要です。</span><span class="sxs-lookup"><span data-stu-id="24c0d-122">You must have a flat-file BOMDOC IDOC to send to the SAP system using the vPrev SAP adapter.</span></span> <span data-ttu-id="24c0d-123">このチュートリアルでは提供されたサンプルには、このフラット ファイル IDOC が含まれています。</span><span class="sxs-lookup"><span data-stu-id="24c0d-123">The sample provided for this tutorial contains this flat-file IDOC.</span></span>  
  
-   [<span data-ttu-id="24c0d-124">厳密な名前のキー ファイルの作成と、ツールの説明</span><span class="sxs-lookup"><span data-stu-id="24c0d-124">Create strong-name key file, and learn the tools</span></span>](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="24c0d-125">アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。</span><span class="sxs-lookup"><span data-stu-id="24c0d-125">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="24c0d-126">IDOC を送信する vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="24c0d-126">The key constituents of a vPrev BizTalk project to send an IDOC are:</span></span>  
  
-   <span data-ttu-id="24c0d-127">**BizTalk オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="24c0d-127">**BizTalk orchestration**.</span></span> <span data-ttu-id="24c0d-128">これは、ファイルの場所からフラット ファイル IDOC を取得し、SAP を使用して SAP システムに IDOC の送信ポートを送信する簡単なオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="24c0d-128">This is a simple orchestration that picks a flat-file IDOC from a file location and sends the IDOC to the SAP system using an SAP send port.</span></span> <span data-ttu-id="24c0d-129">BizTalk プロジェクトには、オーケストレーションで使用できるように、XML、フラット ファイル IDOC に変換するフラット ファイル逆アセンブラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="24c0d-129">The BizTalk project contains a flat-file disassembler to convert the flat-file IDOC to an XML, so that it can be used in an orchestration.</span></span> <span data-ttu-id="24c0d-130">XML IDOC が SAP に送信ポート vPrev によって使用される、前に、フラット ファイル アセンブラーを使用してフラット ファイル IDOC に変換されます。</span><span class="sxs-lookup"><span data-stu-id="24c0d-130">Before the XML IDOC is consumed by the vPrev SAP send port, it is converted back into a flat-file IDOC using a flat-file assembler.</span></span>  
  
-   <span data-ttu-id="24c0d-131">**SAP システムに送信する IDOC のスキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="24c0d-131">**Schema for the IDOC you want to send to the SAP system**.</span></span> <span data-ttu-id="24c0d-132">このチュートリアルでは、BOMDOC01 IDOC を SAP システムに送信する BizTalk プロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="24c0d-132">For this tutorial, you take a BizTalk project that sends BOMDOC01 IDOC to the SAP system.</span></span> <span data-ttu-id="24c0d-133">IDOC に対して生成されたスキーマは、BOMDOC01.xsd です。</span><span class="sxs-lookup"><span data-stu-id="24c0d-133">The schema generated for the IDOC is BOMDOC01.xsd.</span></span> <span data-ttu-id="24c0d-134">VPrev SAP アダプターを使用して、このスキーマが生成されます。</span><span class="sxs-lookup"><span data-stu-id="24c0d-134">This schema is generated using the vPrev SAP adapter.</span></span>  
  
-   <span data-ttu-id="24c0d-135">**フラット ファイル IDOC**します。</span><span class="sxs-lookup"><span data-stu-id="24c0d-135">**The flat-file IDOC**.</span></span> <span data-ttu-id="24c0d-136">これは、フラット ファイル IDOC を SAP システムに送信されます。</span><span class="sxs-lookup"><span data-stu-id="24c0d-136">This is the flat-file IDOC that is sent to the SAP system.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="24c0d-137">BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。</span><span class="sxs-lookup"><span data-stu-id="24c0d-137">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="24c0d-138">この移行のチュートリアルの目的は、vPrev SAP アダプターの送信ポートではなく Wcf-custom 送信ポートを使用して SAP システムにフラット ファイル IDOC を送信するためです。</span><span class="sxs-lookup"><span data-stu-id="24c0d-138">The goal of this migration tutorial is to enable you to send a flat-file IDOC to an SAP system using a WCF-Custom send port instead of the send port for the vPrev SAP adapter.</span></span> <span data-ttu-id="24c0d-139">どのような設定は、Wcf-custom 送信ポートに必要な詳細については、前に、まず vPrev 送信 IDOC のオーケストレーションに必要などのような物理ポートを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24c0d-139">Before understanding what settings are required for the WCF-Custom send port, you must first understand what physical ports are required for the vPrev send IDOC orchestration:</span></span>  
  
- <span data-ttu-id="24c0d-140">ファイルは、フラット ファイル IDOC を取得するポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="24c0d-140">A file receive port that picks the flat-file IDOC.</span></span> <span data-ttu-id="24c0d-141">このポートは、フラット ファイルを vPrev SAP アダプターを使用して生成されたスキーマ (BOMDOC01.xsd) に準拠した XML に変換するのに BizTalk アプリケーションで使用可能なフラット ファイル逆アセンブラー パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="24c0d-141">This port uses the flat-file disassembler pipeline, available in the BizTalk application, to convert the flat-file into an XML that conforms to the schema (BOMDOC01.xsd) generated using the vPrev SAP adapter.</span></span>  
  
- <span data-ttu-id="24c0d-142">VPrev SAP では、フラット ファイル IDOC を SAP システムに送信ポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="24c0d-142">A vPrev SAP send port that sends the flat-file IDOC to the SAP system.</span></span> <span data-ttu-id="24c0d-143">フラット ファイルを送信する前に、ポートは、フラット ファイル アセンブラーを使用して XML IDOC フラット ファイル IDOC に変換します。</span><span class="sxs-lookup"><span data-stu-id="24c0d-143">Before sending the flat-file, the port uses the flat-file assembler to convert the XML IDOC into a flat-file IDOC.</span></span>  
  
  <span data-ttu-id="24c0d-144">既存の vPrev BizTalk プロジェクトを移行するは、ファイルを変更する必要はありません受信ポートをフラット ファイル IDOC を取得し、フラット ファイル IDOC をフラット ファイル逆アセンブラーを使用して XML に変換します。</span><span class="sxs-lookup"><span data-stu-id="24c0d-144">To migrate your existing vPrev BizTalk project, you do not need to change the file receive port that picks the flat-file IDOC and converts the flat-file IDOC to XML using a flat-file disassembler.</span></span> <span data-ttu-id="24c0d-145">適切な構成設定で新しい Wcf-custom 送信ポートを構成する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="24c0d-145">You only need to configure a new WCF-Custom send port with the right configuration settings.</span></span> <span data-ttu-id="24c0d-146">このチュートリアルは、WCF ベースを使用して SAP システムに Idoc を送信する Wcf-custom 送信ポートを構成する方法を示します[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="24c0d-146">This tutorial demonstrates how to configure the WCF-Custom send port to send IDOCs to an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="24c0d-147">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="24c0d-147">In This Section</span></span>  
  
-   [<span data-ttu-id="24c0d-148">手順 1: IDOC を送信するための vPrev BizTalk プロジェクトを構築して展開する</span><span class="sxs-lookup"><span data-stu-id="24c0d-148">Step 1: Build and Deploy the vPrev BizTalk Project for Sending an IDOC</span></span>](../../adapters-and-accelerators/adapter-sap/step-1-build-and-deploy-the-vprev-biztalk-project-for-sending-an-idoc.md)  
  
-   [<span data-ttu-id="24c0d-149">手順 2: WCF-Custom の一方向の送信ポートを構成する</span><span class="sxs-lookup"><span data-stu-id="24c0d-149">Step 2: Configure a WCF-Custom One-way Send Port</span></span>](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-send-port.md)  
  
-   [<span data-ttu-id="24c0d-150">手順 3: 移行されたアプリケーションをテストする</span><span class="sxs-lookup"><span data-stu-id="24c0d-150">Step 3: Test the Migrated Application</span></span>](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md)  
  
## <a name="see-also"></a><span data-ttu-id="24c0d-151">参照</span><span class="sxs-lookup"><span data-stu-id="24c0d-151">See Also</span></span>  
 [<span data-ttu-id="24c0d-152">SAP アダプター チュートリアル</span><span class="sxs-lookup"><span data-stu-id="24c0d-152">SAP Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)