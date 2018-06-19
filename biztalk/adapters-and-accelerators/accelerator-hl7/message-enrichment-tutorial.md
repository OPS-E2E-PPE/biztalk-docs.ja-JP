---
title: メッセージの強化チュートリアル |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial
- message enrichment tutorial, about the tutorial
- messages, tutorial
- tutorials, message enrichment tutorial
ms.assetid: 4ffb047f-457a-4a80-b7ec-4b61ae16f35f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 532fc0e8a9aeefbc35a892277c68be8d640b5588
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205234"
---
# <a name="message-enrichment-tutorial"></a><span data-ttu-id="c06c1-102">メッセージの強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="c06c1-102">Message Enrichment Tutorial</span></span>
<span data-ttu-id="c06c1-103">このチュートリアルを使用するための手順の説明[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]特定のビジネス問題を解決する: メッセージの強化に関する問題です。</span><span class="sxs-lookup"><span data-stu-id="c06c1-103">This tutorial provides step-by-step procedures for using [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to solve a particular business problem: the message enrichment problem.</span></span> <span data-ttu-id="c06c1-104">メッセージの強化のチュートリアルでは、する必要がある追加、または強化する場合、HL7 準拠ではありませんやが完了するメッセージについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-104">The message enrichment tutorial describes a situation in which you have to add to, or enrich, a message that is not HL7-compliant and/or is incomplete.</span></span> <span data-ttu-id="c06c1-105">これは、患者登録アプリケーションなど、アプリケーションで発生する可能性やから XML データを含むメッセージを作成する場合に発生することができます[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c06c1-105">This can occur with an application, such as a patient registration application, or it can occur when you are populating a message with XML data from [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c06c1-106">このチュートリアルでは、BTAHL7 でメッセージをキャプチャし、患者のレコードをデータベースからなど、不足しているデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-106">In this tutorial, you capture the messages with BTAHL7, and provide any missing data, for example, from a patient records database.</span></span> <span data-ttu-id="c06c1-107">メッセージを変換し、実験、保険、または (最小限の低いレイヤー プロトコル) MLLP アダプターを使用して、レガシ基幹業務 (LOB) アプリケーションに送信します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-107">You then convert the message and send it to a laboratory, insurance, or any legacy line-of-business (LOB) application using the MLLP (Minimal Lower Layer Protocol) adapter.</span></span>  
  
 <span data-ttu-id="c06c1-108">このチュートリアルではイベントを送信する XML 形式のメッセージの場合は、ここでは、「ドアベル」患者の登録トリガー、SOAP アダプターから Web サービス クライアント (WSClient.exe) アプリケーションを使用する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]BTAHL7 でします。</span><span class="sxs-lookup"><span data-stu-id="c06c1-108">In this tutorial, you use a Web service client (WSClient.exe) application to send an XML-formatted message, in this case a "doorbell" Register Patient trigger event, through the SOAP adapter to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] with BTAHL7.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c06c1-109">SOAP メッセージを受信ポート、およびルートの Web サービスとして公開されたオーケストレーションにメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-109"> receives the message in a SOAP receive port, and routes the message to an orchestration published as a Web service.</span></span> <span data-ttu-id="c06c1-110">XML メッセージには、患者の名前と社会保障番号が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c06c1-110">The XML message contains a patient name and social security number.</span></span> <span data-ttu-id="c06c1-111">メッセージが強化され、HL7 形式にメッセージを変換するスキーマ、マップ、および変換を使用します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-111">You augment the message, and use schemas, a map, and a transform to convert the message into HL7 format.</span></span> <span data-ttu-id="c06c1-112">研究、保険に MLLP アダプターを介して送信し、または LOB アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="c06c1-112">You will then send it through an MLLP adapter to the laboratory, insurance, or LOB application.</span></span>  
  
 <span data-ttu-id="c06c1-113">次の図は、チュートリアルのプロセス フローを示しています。</span><span class="sxs-lookup"><span data-stu-id="c06c1-113">The following figure shows the process flow of the tutorial.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-msgenrichtutarch.gif "hl7_msgenrichtutarch")  
  
> [!NOTE]
>  <span data-ttu-id="c06c1-114">このチュートリアルは、Windows Server Standard、Enterprise、Datacenter が必要です。 または、Web Edition、および、MLLP を含むカスタム BTAHL7 インストール ツールをテストします。</span><span class="sxs-lookup"><span data-stu-id="c06c1-114">This tutorial requires Windows Server Standard, Enterprise, Datacenter, or Web Edition, and a custom BTAHL7 installation that includes the MLLP test tools.</span></span> <span data-ttu-id="c06c1-115">さらに、する必要があります慣れて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で開発[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]情報および[HL7 アクセラレータと使用可能な BizTalk ツールについて説明](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)です。</span><span class="sxs-lookup"><span data-stu-id="c06c1-115">Additionally, you should be familiar with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] development in [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] and the information found in [learn about the HL7 accelerator and the BizTalk tools available](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c06c1-116">アセンブリを展開解除、送信ポートを停止によってエラーを回避することができ、受信前のチュートリアルで使用される場所を無効にします。</span><span class="sxs-lookup"><span data-stu-id="c06c1-116">You can avoid errors by undeploying assemblies, stopping send ports, and disabling receive locations that you used in previous tutorials.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c06c1-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c06c1-117">In this section</span></span>  
  
-   [<span data-ttu-id="c06c1-118">手順 1: アプリケーション プール Id を構成します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-118">Step 1: Configure Application Pool Identity</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-application-pool-identity.md)  
  
-   [<span data-ttu-id="c06c1-119">手順 2: 新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-119">Step 2: Create a New Project</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md)  
  
-   [<span data-ttu-id="c06c1-120">手順 3: アセンブリに厳密な名前を割り当てます</span><span class="sxs-lookup"><span data-stu-id="c06c1-120">Step 3: Assign a Strong Name to the Assembly</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)  
  
-   [<span data-ttu-id="c06c1-121">手順 4: スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-121">Step 4: Create the Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md)  
  
-   [<span data-ttu-id="c06c1-122">手順 5: スキーマのプロパティを昇格させる</span><span class="sxs-lookup"><span data-stu-id="c06c1-122">Step 5: Promote Schema Properties</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-promote-schema-properties.md)  
  
-   [<span data-ttu-id="c06c1-123">手順 6: スキーマを検証します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-123">Step 6: Validate the Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)  
  
-   [<span data-ttu-id="c06c1-124">手順 7: 署名し、プロジェクトのビルド</span><span class="sxs-lookup"><span data-stu-id="c06c1-124">Step 7: Sign and Build the Projects</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-sign-and-build-the-projects.md)  
  
-   [<span data-ttu-id="c06c1-125">手順 8: BizTalk マッパーでマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-125">Step 8: Create a Map with BizTalk Mapper</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md)  
  
-   [<span data-ttu-id="c06c1-126">手順 9: 検証プロジェクトをビルド マップ</span><span class="sxs-lookup"><span data-stu-id="c06c1-126">Step 9: Validate and Build the Map Project</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md)  
  
-   [<span data-ttu-id="c06c1-127">手順 10: オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-127">Step 10: Create an Orchestration</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md)  
  
-   [<span data-ttu-id="c06c1-128">手順 11: オーケストレーション変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-128">Step 11: Create Orchestration Variables</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md)  
  
-   [<span data-ttu-id="c06c1-129">手順 12: オーケストレーション図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-129">Step 12: Configure Orchestration Shapes</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md)  
  
-   [<span data-ttu-id="c06c1-130">手順 13: を作成し、ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-130">Step 13: Create and Configure Ports</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md)  
  
-   [<span data-ttu-id="c06c1-131">手順 14: Web サービスとしてのオーケストレーションを公開します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-131">Step 14: Publish the Orchestration as a Web Service</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md)  
  
-   [<span data-ttu-id="c06c1-132">手順 15 は、送信を構成し、受信ポート</span><span class="sxs-lookup"><span data-stu-id="c06c1-132">Step 15: Configure the Send and Receive Ports</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md)  
  
-   [<span data-ttu-id="c06c1-133">手順 16.、オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-133">Step 16: Start the Orchestration</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md)  
  
-   [<span data-ttu-id="c06c1-134">手順 17: クライアント アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-134">Step 17: Create the WSClient Application</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md)  
  
-   [<span data-ttu-id="c06c1-135">手順 18: 新しいメッセージの強化ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="c06c1-135">Step 18: Test Your New Message Enrichment Solution</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-18-test-your-new-message-enrichment-solution.md)