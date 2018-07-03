---
title: BizTalk Accelerator for SWIFT ランタイム |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- runtime, architecture
- developing, components
- architecture, topology
- messages, message flow diagram
- runtime, components
- SWIFT runtime
- architecture, runtime architecture
- SWIFT network
- A4SWIFT, network
- topology
ms.assetid: c0f59760-7d7d-4b22-a7dc-54e563971d4a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fc0e7a7cb00e16263e537e24abcc144e5c7d0a4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966123"
---
# <a name="biztalk-accelerator-for-swift-runtime"></a><span data-ttu-id="a2968-102">BizTalk Accelerator for SWIFT ランタイム</span><span class="sxs-lookup"><span data-stu-id="a2968-102">BizTalk Accelerator for SWIFT Runtime</span></span>
<span data-ttu-id="a2968-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] 2 つの形式で機能を提供します。 開発資料とランタイム コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="a2968-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides functionality in two forms: development materials and runtime components.</span></span> <span data-ttu-id="a2968-104">開発の資料には、XSD スキーマ、検証ルールとポリシー、およびサンプル コードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2968-104">Development materials include XSD schemas, validation rules and policies, and sample code.</span></span> <span data-ttu-id="a2968-105">ランタイム コンポーネントには、カスタムの SWIFT 逆アセンブラー、カスタムの SWIFT アセンブラー、Message Repair および New Submission のオーケストレーション (MrsrRepair.odx)、および FIN Response Reconciliation のオーケストレーション (FrrMain.odx) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2968-105">Runtime components include the custom SWIFT disassembler, the custom SWIFT assembler, the Message Repair and New Submission orchestration (MrsrRepair.odx), and the FIN Response Reconciliation orchestration (FrrMain.odx).</span></span> <span data-ttu-id="a2968-106">Message Repair and New Submission の詳細については、次を参照してください。 [Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md)します。</span><span class="sxs-lookup"><span data-stu-id="a2968-106">For more information on Message Repair and New Submission, see [Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md).</span></span> <span data-ttu-id="a2968-107">FRR の詳細については、次を参照してください。 [FIN Response Reconciliation](../../adapters-and-accelerators/accelerator-swift/fin-response-reconciliation.md)します。</span><span class="sxs-lookup"><span data-stu-id="a2968-107">For more information on FRR, see [FIN Response Reconciliation](../../adapters-and-accelerators/accelerator-swift/fin-response-reconciliation.md).</span></span>  

 <span data-ttu-id="a2968-108">次の図の高レベルのシステム アーキテクチャを示しています。[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a2968-108">The following figure shows the high-level system architecture of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span>  

 <span data-ttu-id="a2968-109">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-end-to-end.gif "A4SWIFTSystemArchitecture_End_to_End")</span><span class="sxs-lookup"><span data-stu-id="a2968-109">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-end-to-end.gif "A4SWIFTSystemArchitecture_End_to_End")</span></span>  

 <span data-ttu-id="a2968-110">次の図は、A4SWIFT とバックエンド アプリケーション間のメッセージのフローし、A4SWIFT を使用する方法を示しています。 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] Message Repair and New Submission 用 MRSR でフォームのサイト。</span><span class="sxs-lookup"><span data-stu-id="a2968-110">The following figure illustrates how messages flow between A4SWIFT and a back-end application, and how A4SWIFT uses [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forms in MRSR site for Message Repair and New Submission.</span></span>  

 <span data-ttu-id="a2968-111">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswithbackendapplications.gif "A4SWIFTSystemArchitecture_InterfaceswithBackEndApplications")</span><span class="sxs-lookup"><span data-stu-id="a2968-111">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswithbackendapplications.gif "A4SWIFTSystemArchitecture_InterfaceswithBackEndApplications")</span></span>  

 <span data-ttu-id="a2968-112">次の図は、A4SWIFT と SWIFT ネットワークの間のメッセージのフロー方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a2968-112">The following figure illustrates how messages flow between A4SWIFT and the SWIFT Network.</span></span>  

 <span data-ttu-id="a2968-113">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswiththeswiftnetwork.gif "A4SWIFTSystemArchitecture_InterfaceswiththeSWIFTNetwork")</span><span class="sxs-lookup"><span data-stu-id="a2968-113">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswiththeswiftnetwork.gif "A4SWIFTSystemArchitecture_InterfaceswiththeSWIFTNetwork")</span></span>  

 <span data-ttu-id="a2968-114">A4SWIFT のすべてのコンポーネントは、BizTalk Server アプリケーションのコンポーネントの垂直方向に固有の実装として定義できます。</span><span class="sxs-lookup"><span data-stu-id="a2968-114">You can define all A4SWIFT components as vertical-specific implementations of BizTalk Server application components.</span></span> <span data-ttu-id="a2968-115">垂直方向に固有の上に BizTalk アプリケーションの開発を加速する機能を開発およびランタイムを提供する BizTalk アクセラレータ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a2968-115">BizTalk accelerators provide development and runtime functionality to accelerate vertical-specific BizTalk application development on top of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="a2968-116">そのため、A4SWIFT のコンポーネントをすべて (開発またはランタイム) は、規定を遵守し、BizTalk Server アプリケーションのアーキテクチャに適合します。</span><span class="sxs-lookup"><span data-stu-id="a2968-116">Therefore, all A4SWIFT components (development or runtime) abide by, and fit into, the BizTalk Server application architecture.</span></span> <span data-ttu-id="a2968-117">A4SWIFT にランタイム コンポーネントのインストール、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]カスタム コンポーネントとランタイム。</span><span class="sxs-lookup"><span data-stu-id="a2968-117">A4SWIFT installs runtime components into the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] runtime as custom components.</span></span> <span data-ttu-id="a2968-118">マテリアルのコンパイルおよび展開、A4SWIFT の開発後、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SWIFT メッセージングとオートメーションの機能を提供するランタイムを使用しています。</span><span class="sxs-lookup"><span data-stu-id="a2968-118">After development materials are compiled and deployed, A4SWIFT and the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] runtime use them to provide SWIFT messaging and automation functionality.</span></span>  

 <span data-ttu-id="a2968-119">次の図は、BizTalk Server の高度なアプリケーション トポロジを示します。</span><span class="sxs-lookup"><span data-stu-id="a2968-119">The following figure shows the high-level application topology for BizTalk Server.</span></span>  

 <span data-ttu-id="a2968-120">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro1.gif "FSA_Intro1")</span><span class="sxs-lookup"><span data-stu-id="a2968-120">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro1.gif "FSA_Intro1")</span></span>  

 <span data-ttu-id="a2968-121">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーション モデルは、メッセージ ボックス データベースとに、およびメッセージ ボックス データベースからのメッセージ フローを制御するパブリッシャーとサブスクライバーのパターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="a2968-121">The [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application model uses the MessageBox database and the publisher-subscriber pattern that governs message flow into and out of the MessageBox database.</span></span> <span data-ttu-id="a2968-122">BizTalk のアーキテクチャとアプリケーションの設計に関する詳細については、BizTalk Server のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2968-122">For more information about BizTalk architecture and application design, see BizTalk Server Help.</span></span>  

 <span data-ttu-id="a2968-123">A4SWIFT のアプリケーション モデルが継承、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーション モデルへの追加と SWIFT 固有のコンポーネントで SWIFT に関連するソリューションを容易に[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a2968-123">The A4SWIFT application model inherits the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application model and adds to it SWIFT-specific components to facilitate SWIFT-related solutions on [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="a2968-124">次の一覧には、これら A4SWIFT 固有のコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a2968-124">The following list describes these A4SWIFT-specific components:</span></span>  

- <span data-ttu-id="a2968-125">**ランタイム コンポーネントです。**</span><span class="sxs-lookup"><span data-stu-id="a2968-125">**Runtime components.**</span></span> <span data-ttu-id="a2968-126">受信パイプライン、送信パイプライン、Message Repair and New Submission のオーケストレーション、および FIN Response Reconciliation のオーケストレーションで SWIFT アセンブラーで SWIFT 逆アセンブラーです。</span><span class="sxs-lookup"><span data-stu-id="a2968-126">SWIFT disassembler in the receive pipeline, SWIFT assembler in the send pipeline, Message Repair and New Submission orchestration, and FIN Response Reconciliation orchestration.</span></span>  

- <span data-ttu-id="a2968-127">**開発のマテリアルです。**</span><span class="sxs-lookup"><span data-stu-id="a2968-127">**Development materials.**</span></span> <span data-ttu-id="a2968-128">SWIFT スキーマ、ルール、オーケストレーション、および顧客向けのソリューションに含まれており、展開されている実行の実行時にサンプル プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="a2968-128">SWIFT schemas, rules, orchestrations, and sample projects to be included in customer solutions and deployed onto the runtime for execution.</span></span>  

  <span data-ttu-id="a2968-129">このセクションでは、A4SWIFT ランタイムの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2968-129">This section describes the A4SWIFT runtime in detail.</span></span>  

  <span data-ttu-id="a2968-130">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a2968-130">This section contains:</span></span>  

- [<span data-ttu-id="a2968-131">SWIFT 逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="a2968-131">SWIFT Disassembler</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-disassembler.md)  

- [<span data-ttu-id="a2968-132">SWIFT アセンブラー</span><span class="sxs-lookup"><span data-stu-id="a2968-132">SWIFT Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-assembler.md)  

- [<span data-ttu-id="a2968-133">受信場所と InfoPath フォームを介したメッセージの送信</span><span class="sxs-lookup"><span data-stu-id="a2968-133">Submitting Messages Through Receive Locations and InfoPath Forms</span></span>](../../adapters-and-accelerators/accelerator-swift/submitting-messages-through-receive-locations-and-infopath-forms.md)  

- [<span data-ttu-id="a2968-134">メッセージ検証エンジン</span><span class="sxs-lookup"><span data-stu-id="a2968-134">Message Validation Engine</span></span>](../../adapters-and-accelerators/accelerator-swift/message-validation-engine.md)
