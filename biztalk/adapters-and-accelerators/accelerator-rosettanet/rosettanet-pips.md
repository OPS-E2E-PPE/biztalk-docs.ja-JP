---
title: RosettaNet Pip |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PIPs, clusters
- RosettaNet, PIPs
- PIPs, PIP specifications
- PIPs, segments
- PIPs, RosettaNet
- DTDs, DTD files
ms.assetid: 2f7e8db3-9ccb-403a-9fe7-58fbba3c4cb1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20c29c3f295d4401b30bfeecc32d9df3aa532e16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282048"
---
# <a name="rosettanet-pips"></a><span data-ttu-id="ecf5b-102">RosettaNet Pip</span><span class="sxs-lookup"><span data-stu-id="ecf5b-102">RosettaNet PIPs</span></span>
<span data-ttu-id="ecf5b-103">RosettaNet 組織では、作成し、Partner Interface Process (Pip) のすべての RosettaNet メッセージ交換の共通のビジネス プロセス定義を提供するを保持します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-103">The RosettaNet organization creates and maintains Partner Interface Processes (PIPs) to provide common business-process definitions for all RosettaNet message exchanges.</span></span>  
  
 <span data-ttu-id="ecf5b-104">各 PIP 仕様では、ドキュメント型定義 (DTD) ファイルとメッセージ ガイドライン ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-104">Each PIP specification provides a document type definition (DTD) file and a message guideline document.</span></span> <span data-ttu-id="ecf5b-105">DTD ファイルは、service content のメッセージの構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-105">The DTD file defines the service-content message structure.</span></span> <span data-ttu-id="ecf5b-106">人間が判読できる HTML ファイルには、メッセージ ガイドライン ドキュメントには、要素レベルの制約を指定します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-106">The message-guideline document, which is a human-readable HTML file, specifies element-level constraints.</span></span> <span data-ttu-id="ecf5b-107">同時に、ビジネス プロセスの完全な定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-107">Together, they provide a complete definition of the business process.</span></span>  
  
 <span data-ttu-id="ecf5b-108">PIP 仕様の詳細については、RosettaNet の Web サイトを参照してください。 [ http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859)します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-108">For more information about PIP specifications, see the RosettaNet Web site at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859).</span></span>  
  
## <a name="pip-contents"></a><span data-ttu-id="ecf5b-109">PIP の内容</span><span class="sxs-lookup"><span data-stu-id="ecf5b-109">PIP Contents</span></span>  
 <span data-ttu-id="ecf5b-110">PIP 仕様は、次を行います。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-110">A PIP specification does the following:</span></span>  
  
- <span data-ttu-id="ecf5b-111">実装するパブリック プロセスのパターンについて説明します</span><span class="sxs-lookup"><span data-stu-id="ecf5b-111">Describes which public process pattern it implements</span></span>  
  
- <span data-ttu-id="ecf5b-112">パブリック プロセスを構成する方法について説明します</span><span class="sxs-lookup"><span data-stu-id="ecf5b-112">Describes how to configure the public process</span></span>  
  
- <span data-ttu-id="ecf5b-113">PIP 内で交換するドキュメントへの参照を提供します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-113">Provides references to the documents to exchange within the PIP</span></span>  
  
  <span data-ttu-id="ecf5b-114">PIP 仕様には、次の 3 つの主要な部分が含まれています: Business Operational View (BOV)、機能サービス ビュー (FSV)、および実装 Framework ビュー (IFV)。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-114">A PIP specification includes three major parts: a Business Operational View (BOV), Functional Service View (FSV), and an Implementation Framework View (IFV).</span></span> <span data-ttu-id="ecf5b-115">これらの各ビューには、要素レベルの制約を指定します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-115">Each of these views specifies element-level constraints:</span></span>  
  
- <span data-ttu-id="ecf5b-116">BOV には、ビジネス データ エンティティのセマンティクスとビジネス プロセス フローを指定します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-116">The BOV specifies the semantics of business data entities and the business process flow.</span></span> <span data-ttu-id="ecf5b-117">これは、開始時刻、終了状態、およびパートナーの役割について説明します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-117">It describes start and end states, and partner roles.</span></span> <span data-ttu-id="ecf5b-118">これには、ロール、および詳細情報のセキュリティ、監査、およびプロセス コントロール間の相互作用について説明します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-118">It describes the interaction between roles, and details security, audit, and process controls.</span></span> <span data-ttu-id="ecf5b-119">これは、ビジネス ドキュメントとビジネス データ エンティティを指定します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-119">It specifies the business documents and business data entities.</span></span>  
  
- <span data-ttu-id="ecf5b-120">FSV には、ネットワーク コンポーネント サービス、エージェント、および相互作用を指定します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-120">The FSV specifies network component services, agents, and interactions.</span></span> <span data-ttu-id="ecf5b-121">Pip を実行するために必要なネットワーク コンポーネントのデザインを提供し、可能なネットワーク コンポーネントの相互作用について説明します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-121">It provides the network component design required to run the PIPs, and describes possible network component interactions.</span></span>  
  
- <span data-ttu-id="ecf5b-122">IFV は、ネットワーク プロトコルのメッセージ形式と PIP を実行するために必要な通信要件を指定します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-122">The IFV specifies the network-protocol message formats and communication requirements required to run the PIP.</span></span>  
  
## <a name="clusters-and-segments"></a><span data-ttu-id="ecf5b-123">クラスターとセグメント</span><span class="sxs-lookup"><span data-stu-id="ecf5b-123">Clusters and Segments</span></span>  
 <span data-ttu-id="ecf5b-124">(クラスター) の高度なビジネス機能とサブ関数 (セグメント) では、Pip を分類します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-124">You categorize PIPs by a high-level business function (cluster) and a subfunction (segment).</span></span> <span data-ttu-id="ecf5b-125">クラスターとセグメントは、ビジネス メッセージを認識可能なカテゴリに分類します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-125">Clusters and segments organize business messages into recognizable categories.</span></span> <span data-ttu-id="ecf5b-126">次の表は、これらのクラスターとセグメントを示します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-126">The following table lists these clusters and segments.</span></span>  
  
|<span data-ttu-id="ecf5b-127">クラスター</span><span class="sxs-lookup"><span data-stu-id="ecf5b-127">Clusters</span></span>|<span data-ttu-id="ecf5b-128">セグメント</span><span class="sxs-lookup"><span data-stu-id="ecf5b-128">Segments</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="ecf5b-129">0:RosettaNet のサポート</span><span class="sxs-lookup"><span data-stu-id="ecf5b-129">0: RosettaNet Support</span></span>|<span data-ttu-id="ecf5b-130">0A:管理</span><span class="sxs-lookup"><span data-stu-id="ecf5b-130">0A: Administrative</span></span><br /><br /> <span data-ttu-id="ecf5b-131">0 の C:Testing (テスト)</span><span class="sxs-lookup"><span data-stu-id="ecf5b-131">0C: Testing</span></span>|  
|<span data-ttu-id="ecf5b-132">1:パートナー製品とサービス レビュー</span><span class="sxs-lookup"><span data-stu-id="ecf5b-132">1: Partner Product & Service Review</span></span>|<span data-ttu-id="ecf5b-133">1 A:パートナーのレビュー</span><span class="sxs-lookup"><span data-stu-id="ecf5b-133">1A: Partner Review</span></span><br /><br /> <span data-ttu-id="ecf5b-134">1 B:製品とサービス レビュー</span><span class="sxs-lookup"><span data-stu-id="ecf5b-134">1B: Product & Service Review</span></span>|  
|<span data-ttu-id="ecf5b-135">2:製品情報</span><span class="sxs-lookup"><span data-stu-id="ecf5b-135">2: Product Information</span></span>|<span data-ttu-id="ecf5b-136">2 A:配布準備</span><span class="sxs-lookup"><span data-stu-id="ecf5b-136">2A: Preparation for Distribution</span></span><br /><br /> <span data-ttu-id="ecf5b-137">2 B:製品変更通知</span><span class="sxs-lookup"><span data-stu-id="ecf5b-137">2B: Product Change Notification</span></span><br /><br /> <span data-ttu-id="ecf5b-138">2 C:製品設計情報</span><span class="sxs-lookup"><span data-stu-id="ecf5b-138">2C: Product Design Information</span></span><br /><br /> <span data-ttu-id="ecf5b-139">2D:Collaborative Design & Engineering 部門</span><span class="sxs-lookup"><span data-stu-id="ecf5b-139">2D: Collaborative Design & Engineering</span></span>|  
|<span data-ttu-id="ecf5b-140">3:注文管理</span><span class="sxs-lookup"><span data-stu-id="ecf5b-140">3: Order Management</span></span>|<span data-ttu-id="ecf5b-141">3 A:見積もりと注文エントリ</span><span class="sxs-lookup"><span data-stu-id="ecf5b-141">3A: Quote & Order Entry</span></span><br /><br /> <span data-ttu-id="ecf5b-142">3 B:輸送と配布</span><span class="sxs-lookup"><span data-stu-id="ecf5b-142">3B: Transportation & Distribution</span></span><br /><br /> <span data-ttu-id="ecf5b-143">3 C:Finance (&) を返します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-143">3C: Returns & Finance</span></span><br /><br /> <span data-ttu-id="ecf5b-144">3D:製品の構成</span><span class="sxs-lookup"><span data-stu-id="ecf5b-144">3D: Product Configuration</span></span>|  
|<span data-ttu-id="ecf5b-145">4:Inventory Management</span><span class="sxs-lookup"><span data-stu-id="ecf5b-145">4: Inventory Management</span></span>|<span data-ttu-id="ecf5b-146">4A:コラボレーションの予測</span><span class="sxs-lookup"><span data-stu-id="ecf5b-146">4A: Collaborative Forecasting</span></span><br /><br /> <span data-ttu-id="ecf5b-147">4 B:在庫の割り当て</span><span class="sxs-lookup"><span data-stu-id="ecf5b-147">4B: Inventory Allocation</span></span><br /><br /> <span data-ttu-id="ecf5b-148">4 C:インベントリ レポート</span><span class="sxs-lookup"><span data-stu-id="ecf5b-148">4C: Inventory Reporting</span></span><br /><br /> <span data-ttu-id="ecf5b-149">4 D:在庫の補充</span><span class="sxs-lookup"><span data-stu-id="ecf5b-149">4D: Inventory Replenishment</span></span><br /><br /> <span data-ttu-id="ecf5b-150">4E:Sales のレポート</span><span class="sxs-lookup"><span data-stu-id="ecf5b-150">4E: Sales Reporting</span></span><br /><br /> <span data-ttu-id="ecf5b-151">4F:価格保証</span><span class="sxs-lookup"><span data-stu-id="ecf5b-151">4F: Price Protection</span></span>|  
|<span data-ttu-id="ecf5b-152">5:Marketing Information Management</span><span class="sxs-lookup"><span data-stu-id="ecf5b-152">5: Marketing Information Management</span></span>|<span data-ttu-id="ecf5b-153">5A:潜在顧客の営業案件管理</span><span class="sxs-lookup"><span data-stu-id="ecf5b-153">5A: Lead Opportunity Management</span></span><br /><br /> <span data-ttu-id="ecf5b-154">5 B:マーケティング キャンペーン管理</span><span class="sxs-lookup"><span data-stu-id="ecf5b-154">5B: Marketing Campaign Management</span></span>|  
|<span data-ttu-id="ecf5b-155">6:サービスとサポート</span><span class="sxs-lookup"><span data-stu-id="ecf5b-155">6: Service and Support</span></span>|<span data-ttu-id="ecf5b-156">6A:提供し、管理の保証、サービス パッケージ、およびサービスのコントラクト</span><span class="sxs-lookup"><span data-stu-id="ecf5b-156">6A: Provide and Administer Warranties, Service Packages, and Contract Services</span></span><br /><br /> <span data-ttu-id="ecf5b-157">6B:提供し、管理 (6 a に統合) 資産の管理</span><span class="sxs-lookup"><span data-stu-id="ecf5b-157">6B: Provide and Administer Asset Management (Merged with 6A)</span></span><br /><br /> <span data-ttu-id="ecf5b-158">6C:テクニカル サポートとサービスの管理</span><span class="sxs-lookup"><span data-stu-id="ecf5b-158">6C: Technical Support and Service Management</span></span>|  
|<span data-ttu-id="ecf5b-159">7:Manufacturing</span><span class="sxs-lookup"><span data-stu-id="ecf5b-159">7: Manufacturing</span></span>|<span data-ttu-id="ecf5b-160">7A:デザインの転送</span><span class="sxs-lookup"><span data-stu-id="ecf5b-160">7A: Design Transfer</span></span><br /><br /> <span data-ttu-id="ecf5b-161">7 B:製造 WO と WIP を管理します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-161">7B: Manage Manufacturing WO & WIP</span></span><br /><br /> <span data-ttu-id="ecf5b-162">7 C:製造情報を配布します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-162">7C: Distribute Manufacturing Information</span></span>|  
  
 <span data-ttu-id="ecf5b-163">各セグメントには、特定のメッセージ Pip の数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-163">Each segment includes a number of specific message PIPs.</span></span> <span data-ttu-id="ecf5b-164">たとえば、3A4 PIP は、注文管理クラスター (クラスター 3) と見積もりと注文エントリ セグメント (セグメント A のクラスター 3) の一部です。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-164">For example, the 3A4 PIP is a part of the Order Management cluster (Cluster 3) and the Quote and Order Entry segment (Segment A of Cluster 3).</span></span> <span data-ttu-id="ecf5b-165">このセグメントには、その他の関連メッセージ Pip には、次のようが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-165">This segment includes other related message PIPs, as follows:</span></span>  
  
 <span data-ttu-id="ecf5b-166">クラスター 3:注文管理</span><span class="sxs-lookup"><span data-stu-id="ecf5b-166">Cluster 3: Order Management</span></span>  
  
-   <span data-ttu-id="ecf5b-167">セグメント a:見積もりと注文エントリ</span><span class="sxs-lookup"><span data-stu-id="ecf5b-167">Segment A: Quote and Order Entry</span></span>  
  
    -   <span data-ttu-id="ecf5b-168">PIP 3A1:見積もりを要求します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-168">PIP 3A1: Request Quote</span></span>  
  
    -   <span data-ttu-id="ecf5b-169">PIP 3 A 2:Request Price and Availability</span><span class="sxs-lookup"><span data-stu-id="ecf5b-169">PIP 3A2: Request Price and Availability</span></span>  
  
    -   <span data-ttu-id="ecf5b-170">PIP 3A3:ショッピング カート転送を要求します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-170">PIP 3A3: Request Shopping Cart Transfer</span></span>  
  
    -   <span data-ttu-id="ecf5b-171">PIP 3A4:注文書を管理します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-171">PIP 3A4: Manage Purchase Order</span></span>  
  
    -   <span data-ttu-id="ecf5b-172">PIP 3A5:クエリの注文の状態</span><span class="sxs-lookup"><span data-stu-id="ecf5b-172">PIP 3A5: Query Order Status</span></span>  
  
    -   <span data-ttu-id="ecf5b-173">PIP 3A6:注文の状態を配布します。</span><span class="sxs-lookup"><span data-stu-id="ecf5b-173">PIP 3A6: Distribute Order Status</span></span>  
  
    -   <span data-ttu-id="ecf5b-174">…</span><span class="sxs-lookup"><span data-stu-id="ecf5b-174">…</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecf5b-175">参照</span><span class="sxs-lookup"><span data-stu-id="ecf5b-175">See Also</span></span>  
 <span data-ttu-id="ecf5b-176">[RosettaNet および CIDX メッセージ規格](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span><span class="sxs-lookup"><span data-stu-id="ecf5b-176">[RosettaNet and CIDX Messaging Standards](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span></span>  
 [<span data-ttu-id="ecf5b-177">RNIF 規格</span><span class="sxs-lookup"><span data-stu-id="ecf5b-177">RNIF Standard</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)