---
title: メッセージの強化のチュートリアル |Microsoft Docs
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
ms.openlocfilehash: c2760cfa52fc7e761829d3005bfecbb8bb40a728
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303696"
---
# <a name="message-enrichment-tutorial"></a><span data-ttu-id="45f74-102">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="45f74-102">Message Enrichment Tutorial</span></span>
<span data-ttu-id="45f74-103">このチュートリアルは、Microsoft の使用に関する詳しい手順を示します[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]特定のビジネス問題を解決する: メッセージの強化に関する問題。</span><span class="sxs-lookup"><span data-stu-id="45f74-103">This tutorial provides step-by-step procedures for using Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to solve a particular business problem: the message enrichment problem.</span></span> <span data-ttu-id="45f74-104">メッセージ強化のチュートリアルを追加、または強化する必要がある場合は HL7 に準拠していないことが完了していないメッセージについて説明します。</span><span class="sxs-lookup"><span data-stu-id="45f74-104">The message enrichment tutorial describes a situation in which you have to add to, or enrich, a message that is not HL7-compliant and/or is incomplete.</span></span> <span data-ttu-id="45f74-105">これは、患者の登録アプリケーションなど、アプリケーションで発生する可能性や、Microsoft からの XML データを含むメッセージを作成する場合に発生することができます[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="45f74-105">This can occur with an application, such as a patient registration application, or it can occur when you are populating a message with XML data from Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="45f74-106">このチュートリアルでは、BTAHL7 でメッセージをキャプチャし、患者記録データベースからなど、不足しているあらゆるデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="45f74-106">In this tutorial, you capture the messages with BTAHL7, and provide any missing data, for example, from a patient records database.</span></span> <span data-ttu-id="45f74-107">メッセージを変換し、研究室、保険、または (最小限の下位レイヤー プロトコル) の MLLP アダプターを使用して、従来の基幹業務 (LOB) アプリケーションに送信します。</span><span class="sxs-lookup"><span data-stu-id="45f74-107">You then convert the message and send it to a laboratory, insurance, or any legacy line-of-business (LOB) application using the MLLP (Minimal Lower Layer Protocol) adapter.</span></span>  
  
 <span data-ttu-id="45f74-108">このチュートリアルで「ドアベル」登録患者トリガー イベントを SOAP アダプター経由で、ここでは XML 形式のメッセージの場合を送信する Web サービス クライアント (WSClient.exe) アプリケーションを使用する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]BTAHL7 でします。</span><span class="sxs-lookup"><span data-stu-id="45f74-108">In this tutorial, you use a Web service client (WSClient.exe) application to send an XML-formatted message, in this case a "doorbell" Register Patient trigger event, through the SOAP adapter to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] with BTAHL7.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="45f74-109">SOAP メッセージを受信ポート、およびルートの Web サービスとして公開されたオーケストレーションにメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="45f74-109">receives the message in a SOAP receive port, and routes the message to an orchestration published as a Web service.</span></span> <span data-ttu-id="45f74-110">XML メッセージには、患者の名と社会保障番号が含まれています。</span><span class="sxs-lookup"><span data-stu-id="45f74-110">The XML message contains a patient name and social security number.</span></span> <span data-ttu-id="45f74-111">メッセージを強化し、スキーマ、マップ、および変換を使用して、HL7 形式にメッセージを変換します。</span><span class="sxs-lookup"><span data-stu-id="45f74-111">You augment the message, and use schemas, a map, and a transform to convert the message into HL7 format.</span></span> <span data-ttu-id="45f74-112">保険、研究室に MLLP アダプターを介して送信を LOB アプリケーションまたはします。</span><span class="sxs-lookup"><span data-stu-id="45f74-112">You will then send it through an MLLP adapter to the laboratory, insurance, or LOB application.</span></span>  
  
 <span data-ttu-id="45f74-113">次の図は、チュートリアルのプロセス フローを示しています。</span><span class="sxs-lookup"><span data-stu-id="45f74-113">The following figure shows the process flow of the tutorial.</span></span>  
  
 <span data-ttu-id="45f74-114">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-msgenrichtutarch.gif "hl7_msgenrichtutarch")</span><span class="sxs-lookup"><span data-stu-id="45f74-114">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-msgenrichtutarch.gif "hl7_msgenrichtutarch")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45f74-115">このチュートリアルは、Windows Server Standard、Enterprise、Datacenter が必要です。 または、Web Edition および、MLLP を含むカスタム BTAHL7 インストールは、ツールをテストします。</span><span class="sxs-lookup"><span data-stu-id="45f74-115">This tutorial requires Windows Server Standard, Enterprise, Datacenter, or Web Edition, and a custom BTAHL7 installation that includes the MLLP test tools.</span></span> <span data-ttu-id="45f74-116">さらに、知っておくべきで[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]での開発[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]情報と[HL7 アクセラレータと BizTalk ツールの使用について説明します](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)します。</span><span class="sxs-lookup"><span data-stu-id="45f74-116">Additionally, you should be familiar with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] development in [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] and the information found in [learn about the HL7 accelerator and the BizTalk tools available](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="45f74-117">アセンブリを展開解除、送信ポートを停止によってエラーを回避でき、受信前のチュートリアルで使用する場所を無効にします。</span><span class="sxs-lookup"><span data-stu-id="45f74-117">You can avoid errors by undeploying assemblies, stopping send ports, and disabling receive locations that you used in previous tutorials.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="45f74-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="45f74-118">In this section</span></span>  
  
-   [<span data-ttu-id="45f74-119">ステップ 1: アプリケーション プール ID の構成</span><span class="sxs-lookup"><span data-stu-id="45f74-119">Step 1: Configure Application Pool Identity</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-application-pool-identity.md)  
  
-   [<span data-ttu-id="45f74-120">手順 2:新しいプロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="45f74-120">Step 2: Create a New Project</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md)  
  
-   [<span data-ttu-id="45f74-121">ステップ 3:アセンブリへの厳密な名前の割り当て</span><span class="sxs-lookup"><span data-stu-id="45f74-121">Step 3: Assign a Strong Name to the Assembly</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)  
  
-   [<span data-ttu-id="45f74-122">手順 4:スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="45f74-122">Step 4: Create the Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md)  
  
-   [<span data-ttu-id="45f74-123">手順 5:スキーマのプロパティの昇格</span><span class="sxs-lookup"><span data-stu-id="45f74-123">Step 5: Promote Schema Properties</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-promote-schema-properties.md)  
  
-   [<span data-ttu-id="45f74-124">手順 6:スキーマの検証</span><span class="sxs-lookup"><span data-stu-id="45f74-124">Step 6: Validate the Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)  
  
-   [<span data-ttu-id="45f74-125">手順 7:プロジェクトの署名とビルド</span><span class="sxs-lookup"><span data-stu-id="45f74-125">Step 7: Sign and Build the Projects</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-sign-and-build-the-projects.md)  
  
-   [<span data-ttu-id="45f74-126">手順 8:BizTalk マッパーを使用したマップの作成</span><span class="sxs-lookup"><span data-stu-id="45f74-126">Step 8: Create a Map with BizTalk Mapper</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md)  
  
-   [<span data-ttu-id="45f74-127">手順 9:マップ プロジェクトの検証とビルド</span><span class="sxs-lookup"><span data-stu-id="45f74-127">Step 9: Validate and Build the Map Project</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md)  
  
-   [<span data-ttu-id="45f74-128">手順 10: オーケストレーションの作成</span><span class="sxs-lookup"><span data-stu-id="45f74-128">Step 10: Create an Orchestration</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md)  
  
-   [<span data-ttu-id="45f74-129">手順 11: オーケストレーション変数の作成</span><span class="sxs-lookup"><span data-stu-id="45f74-129">Step 11: Create Orchestration Variables</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md)  
  
-   [<span data-ttu-id="45f74-130">手順 12: オーケストレーション図形の構成</span><span class="sxs-lookup"><span data-stu-id="45f74-130">Step 12: Configure Orchestration Shapes</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md)  
  
-   [<span data-ttu-id="45f74-131">手順 13: ポートの作成と構成</span><span class="sxs-lookup"><span data-stu-id="45f74-131">Step 13: Create and Configure Ports</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md)  
  
-   [<span data-ttu-id="45f74-132">手順 14: Web サービスとしてのオーケストレーションの公開</span><span class="sxs-lookup"><span data-stu-id="45f74-132">Step 14: Publish the Orchestration as a Web Service</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md)  
  
-   [<span data-ttu-id="45f74-133">手順 15: 送信ポートと受信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="45f74-133">Step 15: Configure the Send and Receive Ports</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md)  
  
-   [<span data-ttu-id="45f74-134">手順 16: オーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="45f74-134">Step 16: Start the Orchestration</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md)  
  
-   [<span data-ttu-id="45f74-135">手順 17: WSClient アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="45f74-135">Step 17: Create the WSClient Application</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md)  
  
-   [<span data-ttu-id="45f74-136">手順 18: 新しいメッセージ強化ソリューションのテスト</span><span class="sxs-lookup"><span data-stu-id="45f74-136">Step 18: Test Your New Message Enrichment Solution</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-18-test-your-new-message-enrichment-solution.md)