---
title: BizTalk accelerator for HL7 開始 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.gettingstarted
helpviewer_keywords:
- BizTalk Accelerator for HL7
- BizTalk Accelerator for HL7, getting started
- getting started
ms.assetid: e842d501-2037-4fd6-a518-d29b25877250
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14559d888bc020a5772fbbc6eddf3ba4fdb4beb0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989603"
---
# <a name="get-started-with-the-biztalk-accelerator-for-hl7"></a><span data-ttu-id="67893-102">BizTalk accelerator for HL7 開始します。</span><span class="sxs-lookup"><span data-stu-id="67893-102">Get started with the BizTalk Accelerator for HL7</span></span>
<span data-ttu-id="67893-103">Microsoft を使用して[!INCLUDE[HL7_CurrentVersion_FirstRef_md](../../includes/hl7-currentversion-firstref-md.md)]、医療のコンピューター システム間でビジネス プロセスを開発することができます。</span><span class="sxs-lookup"><span data-stu-id="67893-103">Using the Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef_md](../../includes/hl7-currentversion-firstref-md.md)], you can develop business processes between your health care computer systems.</span></span> <span data-ttu-id="67893-104">使用して[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]開発者、IT プロフェッショナル、およびインターフェイス アナリストは、医療アプリケーション間でのエンド ツー エンドの統合 BTAHL7 ベース ソリューションの開発に共通の環境で作業できます。</span><span class="sxs-lookup"><span data-stu-id="67893-104">By using [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)], developers, IT professionals, and interface analysts can work in a common environment to develop end-to-end integrated BTAHL7-based solutions across health care applications.</span></span>  
  
 <span data-ttu-id="67893-105">具体的で[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]ことができます。</span><span class="sxs-lookup"><span data-stu-id="67893-105">More specifically, with [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] you can:</span></span>  
  
- <span data-ttu-id="67893-106">**医療のアプリケーション統合を簡素化**します。</span><span class="sxs-lookup"><span data-stu-id="67893-106">**Simplify health care application integration**.</span></span> <span data-ttu-id="67893-107">ビルド、管理、および追跡を使用して分散型ビジネス プロセス、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]開発環境。</span><span class="sxs-lookup"><span data-stu-id="67893-107">Build, manage, and track distributed business processes using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] development environment.</span></span>  
  
- <span data-ttu-id="67893-108">**医療アプリケーション間での臨床データ交換を標準化**します。</span><span class="sxs-lookup"><span data-stu-id="67893-108">**Standardize clinical data interchange between medical applications**.</span></span> <span data-ttu-id="67893-109">アプリケーション間の既存のデータ転送の変換、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]標準。</span><span class="sxs-lookup"><span data-stu-id="67893-109">Transform existing data transmission between applications to the [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] standard.</span></span>  
  
- <span data-ttu-id="67893-110">**効率を高める**します。</span><span class="sxs-lookup"><span data-stu-id="67893-110">**Increase efficiency**.</span></span> <span data-ttu-id="67893-111">最小限の介入を医療アプリケーション間のすべての通信プロセスを自動化します。</span><span class="sxs-lookup"><span data-stu-id="67893-111">Automate all communication processes between medical applications with minimal manual intervention.</span></span>  

<span data-ttu-id="67893-112">役割に固有の情報を使用する方法について説明します[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]を病院および企業間取引の医療ソリューションを自動化する医療分野内でエンタープライズ アプリケーション統合 (EAI) を容易にする.</span><span class="sxs-lookup"><span data-stu-id="67893-112">This section provides role-specific information about how you can use [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] and [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] to facilitate Enterprise Application Integration (EAI) within hospitals and the healthcare arena to automate business-to-business healthcare solutions.</span></span>  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]<span data-ttu-id="67893-113"> ソリューションの種類ごとに、チュートリアルの形式で 4 つの独立したシナリオを提供します。</span><span class="sxs-lookup"><span data-stu-id="67893-113"> provides four separate scenarios in tutorial format for each type of solution.</span></span> <span data-ttu-id="67893-114">これらのチュートリアルを開始する前の基本的な概念を理解する必要があります[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]、ツールやソリューションを構築するために必要なプロセスを[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="67893-114">Before you begin these tutorials, you should understand the fundamental concepts in [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)], and the tools and processes that are required to start building solutions with [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)].</span></span>  

> [!TIP] 
> <span data-ttu-id="67893-115">これらのレッスンを開始する前に[HL7 アクセラレータと BizTalk ツールの使用について説明します](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)します。</span><span class="sxs-lookup"><span data-stu-id="67893-115">Before you begin these lessons, [learn about the HL7 accelerator and the BizTalk tools available](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).</span></span>  
  
 <span data-ttu-id="67893-116">次の説明には、それぞれの基本的な知識[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]チュートリアル。</span><span class="sxs-lookup"><span data-stu-id="67893-116">The following descriptions provide a general understanding of each [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] tutorial.</span></span>  
  
## <a name="end-to-end-tutorial"></a><span data-ttu-id="67893-117">エンド ツー エンドのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="67893-117">End-to-End tutorial</span></span>  
 <span data-ttu-id="67893-118">[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]エンド ツー エンドのチュートリアルによって、サブスクライバーとパブリッシャーのシナリオでビジネス プロセスを容易に詳細な手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="67893-118">The [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] End-to-End tutorial provides you with detailed steps to facilitate business processes in a subscriber and publisher scenario.</span></span> <span data-ttu-id="67893-119">このシナリオでは、たとえば、入学退院と転送システムの発行元が特定のサブスクライバーにメッセージを送信する状況。</span><span class="sxs-lookup"><span data-stu-id="67893-119">This scenario is a situation in which a publisher, for example, an Admissions Discharge and Transfer system sends a message to specific subscribers.</span></span>  
  
 <span data-ttu-id="67893-120">メッセージをルーティング、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]インターフェイス エンジンは、さらに受け取ると、プロセス、検証、書式を再設定、およびをサブスクライバーにメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="67893-120">The message routes to the [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] Interface Engine, which in turn receives, processes, validates, reformats, and then routes the message to the subscribers.</span></span> <span data-ttu-id="67893-121">このシナリオではサブスクライバーには、病院の情報システムおよび薬剤システムです。</span><span class="sxs-lookup"><span data-stu-id="67893-121">The subscribers in this scenario are a Hospital Information System and a Pharmacy System.</span></span>  
  
 <span data-ttu-id="67893-122">このシナリオでは、ファイルと最小限の下位レイヤー プロトコル (MLLP) の両方の種類のアダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="67893-122">This scenario uses both File and Minimal Lower Layer Protocol (MLLP) adapter types.</span></span> <span data-ttu-id="67893-123">パブリッシャーは、サブスクライバーを意識する必要はありません、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]インターフェイス エンジンは、メッセージの処理後、パブリッシャーに適切な受信確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="67893-123">The publisher does not need to be aware of the subscribers, and the [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] Interface Engine sends an appropriate acknowledgement to the publisher after processing the message.</span></span>  
  
## <a name="interrogative-tutorial"></a><span data-ttu-id="67893-124">Interrogative チュートリアル</span><span class="sxs-lookup"><span data-stu-id="67893-124">Interrogative tutorial</span></span>  
 <span data-ttu-id="67893-125">[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] Interrogative チュートリアルは詳細な手順を実装するため、組織内のサブシステム間のクエリ応答システム。</span><span class="sxs-lookup"><span data-stu-id="67893-125">The [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] Interrogative tutorial provides you with detailed steps for implementing a query-response system between sub-systems within an organization.</span></span> <span data-ttu-id="67893-126">このシナリオは、入学で基幹業務 (LOB) アプリケーションで、放電し、転送システムでは、病院情報システムは、患者の結果を得るためにクエリを送信します。</span><span class="sxs-lookup"><span data-stu-id="67893-126">In this scenario, a line-of-business (LOB) application in the Admissions, Discharge, and Transfer system sends a query to the Hospital Information System to obtain patient lab results.</span></span> <span data-ttu-id="67893-127">病院の情報システムは、クエリを受信した後、クエリを発行したシステムに戻したり、要求されたデータを送信します。</span><span class="sxs-lookup"><span data-stu-id="67893-127">After the Hospital Information System receives the query, it sends the requested data back to the system that issued the query.</span></span>  
  
 <span data-ttu-id="67893-128">このシナリオでは、受信確認を含むすべてのメッセージのトランスポート プロトコルとして MLLP を使用します。</span><span class="sxs-lookup"><span data-stu-id="67893-128">This scenario uses MLLP as the transport protocol for all messages, including acknowledgments.</span></span>  
  
## <a name="message-enrichment-tutorial"></a><span data-ttu-id="67893-129">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="67893-129">Message enrichment tutorial</span></span>  
 <span data-ttu-id="67893-130">[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]強化のチュートリアルによって、特定のビジネス上の問題を解決するために詳細な手順を提供します。 メッセージ強化シナリオ。</span><span class="sxs-lookup"><span data-stu-id="67893-130">The [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] Enrichment tutorial provides you with detailed steps to solve a particular business problem: the message-enrichment scenario.</span></span> <span data-ttu-id="67893-131">メッセージ強化シナリオを追加、または強化する必要がある場合は HL7 に準拠していないことが完了していないメッセージです。</span><span class="sxs-lookup"><span data-stu-id="67893-131">The message-enrichment scenario is a situation in which you have to add to, or enrich, a message that is not HL7-compliant and/or is incomplete.</span></span> <span data-ttu-id="67893-132">このような状況は、アプリケーションでは、患者登録アプリケーションなど、または XML データからのメッセージを作成するときに発生する可能性が[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="67893-132">This situation can occur with an application, such as a patient-registration application, or when you are populating a message with XML data from [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="67893-133">メッセージをキャプチャするシナリオでは、メッセージの強化、 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]、患者レコード データベースからなど、不足しているあらゆるデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="67893-133">In the message enrichment scenario, you capture the messages with [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)], and provide any missing data, for example, from a patient-records database.</span></span> <span data-ttu-id="67893-134">メッセージを変換し、研究室、保険、または MLLP アダプターを使用して、従来の基幹業務 (LOB) アプリケーションに送信します。</span><span class="sxs-lookup"><span data-stu-id="67893-134">You then convert the message and send it to a laboratory, insurance, or any legacy line-of-business (LOB) application using the MLLP adapter.</span></span>  
  
## <a name="batching-tutorial"></a><span data-ttu-id="67893-135">バッチ処理のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="67893-135">Batching tutorial</span></span>  
 <span data-ttu-id="67893-136">[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]バッチ処理のチュートリアルによってバッチ処理されたメッセージを送受信するための詳細な手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="67893-136">The [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] Batching tutorial provides you with detailed steps to receive and send batched messages.</span></span> <span data-ttu-id="67893-137">バッチ処理と、1 つの複合メッセージとしてグループの個々 のメッセージ (または受信確認) を送受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67893-137">Batching involves receiving and/or sending a group of individual messages (or acknowledgments) as a single composite message.</span></span>  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]<span data-ttu-id="67893-138"> 次のメッセージのバッチ処理状況をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="67893-138"> supports the following three message batching scenarios:</span></span>  
  
- <span data-ttu-id="67893-139">**断片化した受信バッチ**します。</span><span class="sxs-lookup"><span data-stu-id="67893-139">**Fragmented inbound batch**.</span></span> <span data-ttu-id="67893-140">このシナリオで[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]HL7 メッセージのバッチを受信し、送信先システムに、個々 のメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="67893-140">In this scenario, [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] receives an HL7 message batch, and then routes the individual messages to the destination system.</span></span>  
  
- <span data-ttu-id="67893-141">**バッチ処理/バッチ アウト**します。[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]バッチ内の個々 のメッセージを確認し、HL7 メッセージのバッチを受信ファイルと送信先システムにメッセージのバッチをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="67893-141">**Batch in/batch out**. [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] receives an HL7 message batch, verifies the individual messages within the batch, and then routes the message batch to the destination system.</span></span>  
  
- <span data-ttu-id="67893-142">**バッチ (または、送信バッチ処理) を作成**です。</span><span class="sxs-lookup"><span data-stu-id="67893-142">**Create batch (or outbound batching)**.</span></span> [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]<span data-ttu-id="67893-143"> 個々 のメッセージを受信し、送信先システムにルーティングする前にバッチとしてします。</span><span class="sxs-lookup"><span data-stu-id="67893-143"> receives individual messages and batches them before routing them to the destination system.</span></span>  
  
## <a name="tutorial-links"></a><span data-ttu-id="67893-144">チュートリアルのリンク</span><span class="sxs-lookup"><span data-stu-id="67893-144">Tutorial links</span></span>  
  
-   [<span data-ttu-id="67893-145">エンド ツー エンドのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="67893-145">End-to-End Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)  
  
-   [<span data-ttu-id="67893-146">Interrogative チュートリアル</span><span class="sxs-lookup"><span data-stu-id="67893-146">Interrogative Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)  
  
-   [<span data-ttu-id="67893-147">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="67893-147">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)  
  
-   [<span data-ttu-id="67893-148">バッチ処理のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="67893-148">Batching Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)
  
## <a name="see-also"></a><span data-ttu-id="67893-149">参照</span><span class="sxs-lookup"><span data-stu-id="67893-149">See also</span></span>
  
[<span data-ttu-id="67893-150">障碍がある方のためのユーザー補助機能</span><span class="sxs-lookup"><span data-stu-id="67893-150">Accessibility for People with Disabilities</span></span>](../../adapters-and-accelerators/accelerator-hl7/accessibility-for-people-with-disabilities5.md)