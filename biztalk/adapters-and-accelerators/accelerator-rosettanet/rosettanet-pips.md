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
ms.openlocfilehash: 8891979352ce47e18c8cfda80162b3683002c6f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989251"
---
# <a name="rosettanet-pips"></a><span data-ttu-id="16989-102">RosettaNet Pip</span><span class="sxs-lookup"><span data-stu-id="16989-102">RosettaNet PIPs</span></span>
<span data-ttu-id="16989-103">RosettaNet 組織は PIP (Partner Interface Processes) の作成および保守を行って、すべての RosettaNet メッセージ交換のための共通のビジネス プロセス定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="16989-103">The RosettaNet organization creates and maintains Partner Interface Processes (PIPs) to provide common business-process definitions for all RosettaNet message exchanges.</span></span>  
  
 <span data-ttu-id="16989-104">PIP 仕様ごとに、文書型定義 (DTD) ファイルとメッセージ ガイドライン ドキュメントがあります。</span><span class="sxs-lookup"><span data-stu-id="16989-104">Each PIP specification provides a document type definition (DTD) file and a message guideline document.</span></span> <span data-ttu-id="16989-105">DTD ファイルは、Service Content のメッセージ構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="16989-105">The DTD file defines the service-content message structure.</span></span> <span data-ttu-id="16989-106">HTML ファイル形式のメッセージ ガイドライン ドキュメントは、要素レベルでの制約を指定します。</span><span class="sxs-lookup"><span data-stu-id="16989-106">The message-guideline document, which is a human-readable HTML file, specifies element-level constraints.</span></span> <span data-ttu-id="16989-107">この 2 つにより、ビジネス プロセスが詳細に定義されます。</span><span class="sxs-lookup"><span data-stu-id="16989-107">Together, they provide a complete definition of the business process.</span></span>  
  
 <span data-ttu-id="16989-108">PIP 仕様の詳細については、RosettaNet の Web サイトを参照してください。 [ http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859)します。</span><span class="sxs-lookup"><span data-stu-id="16989-108">For more information about PIP specifications, see the RosettaNet Web site at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859).</span></span>  
  
## <a name="pip-contents"></a><span data-ttu-id="16989-109">PIP の内容</span><span class="sxs-lookup"><span data-stu-id="16989-109">PIP Contents</span></span>  
 <span data-ttu-id="16989-110">PIP 仕様の内容は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="16989-110">A PIP specification does the following:</span></span>  
  
- <span data-ttu-id="16989-111">実装するパブリック プロセスのパターンについて説明する。</span><span class="sxs-lookup"><span data-stu-id="16989-111">Describes which public process pattern it implements</span></span>  
  
- <span data-ttu-id="16989-112">パブリック プロセスを構成する方法について説明する。</span><span class="sxs-lookup"><span data-stu-id="16989-112">Describes how to configure the public process</span></span>  
  
- <span data-ttu-id="16989-113">PIP 内で交換できる文書への参照を提供する。</span><span class="sxs-lookup"><span data-stu-id="16989-113">Provides references to the documents to exchange within the PIP</span></span>  
  
  <span data-ttu-id="16989-114">PIP 仕様は、BOV (Business Operational View)、FSV (Functional Service View)、IFV (Implementation Framework View) の 3 つに大きく分かれます。</span><span class="sxs-lookup"><span data-stu-id="16989-114">A PIP specification includes three major parts: a Business Operational View (BOV), Functional Service View (FSV), and an Implementation Framework View (IFV).</span></span> <span data-ttu-id="16989-115">これらの各ビューは、要素レベルの制約を指定します。</span><span class="sxs-lookup"><span data-stu-id="16989-115">Each of these views specifies element-level constraints:</span></span>  
  
- <span data-ttu-id="16989-116">BOV は、ビジネス データ エンティティの意味とビジネス処理フローを指定します。</span><span class="sxs-lookup"><span data-stu-id="16989-116">The BOV specifies the semantics of business data entities and the business process flow.</span></span> <span data-ttu-id="16989-117">開始状態と終了状態、およびパートナーのロールについて記述します。</span><span class="sxs-lookup"><span data-stu-id="16989-117">It describes start and end states, and partner roles.</span></span> <span data-ttu-id="16989-118">ロール間での相互処理について説明し、セキュリティ、監査、およびプロセス コントロールの詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="16989-118">It describes the interaction between roles, and details security, audit, and process controls.</span></span> <span data-ttu-id="16989-119">ビジネス ドキュメントとビジネス データ エンティティを指定します。</span><span class="sxs-lookup"><span data-stu-id="16989-119">It specifies the business documents and business data entities.</span></span>  
  
- <span data-ttu-id="16989-120">FSV は、ネットワーク コンポーネント サービス、エージェント、および操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="16989-120">The FSV specifies network component services, agents, and interactions.</span></span> <span data-ttu-id="16989-121">PIP を実行するために必要なネットワーク コンポーネント設計を提供し、可能なネットワーク コンポーネント操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="16989-121">It provides the network component design required to run the PIPs, and describes possible network component interactions.</span></span>  
  
- <span data-ttu-id="16989-122">IFV は、ネットワーク プロトコルのメッセージ形式と PIP を実行するために必要な通信要件を指定します。</span><span class="sxs-lookup"><span data-stu-id="16989-122">The IFV specifies the network-protocol message formats and communication requirements required to run the PIP.</span></span>  
  
## <a name="clusters-and-segments"></a><span data-ttu-id="16989-123">クラスターおよびセグメント</span><span class="sxs-lookup"><span data-stu-id="16989-123">Clusters and Segments</span></span>  
 <span data-ttu-id="16989-124">PIP は、高度のビジネス関数 (クラスター) とサブ関数 (セグメント) によって分類します。</span><span class="sxs-lookup"><span data-stu-id="16989-124">You categorize PIPs by a high-level business function (cluster) and a subfunction (segment).</span></span> <span data-ttu-id="16989-125">メッセージはクラスターとセグメントによって、わかりやすいカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="16989-125">Clusters and segments organize business messages into recognizable categories.</span></span> <span data-ttu-id="16989-126">次の表に、これらのクラスターとセグメントの一覧です。</span><span class="sxs-lookup"><span data-stu-id="16989-126">The following table lists these clusters and segments.</span></span>  
  
|<span data-ttu-id="16989-127">Clusters</span><span class="sxs-lookup"><span data-stu-id="16989-127">Clusters</span></span>|<span data-ttu-id="16989-128">セグメント</span><span class="sxs-lookup"><span data-stu-id="16989-128">Segments</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="16989-129">0: RosettaNet のサポート</span><span class="sxs-lookup"><span data-stu-id="16989-129">0: RosettaNet Support</span></span>|<span data-ttu-id="16989-130">0A : Administrative (管理)</span><span class="sxs-lookup"><span data-stu-id="16989-130">0A: Administrative</span></span><br /><br /> <span data-ttu-id="16989-131">0C : Testing (テスト)</span><span class="sxs-lookup"><span data-stu-id="16989-131">0C: Testing</span></span>|  
|<span data-ttu-id="16989-132">1: パートナーの製品とサービス レビュー</span><span class="sxs-lookup"><span data-stu-id="16989-132">1: Partner Product & Service Review</span></span>|<span data-ttu-id="16989-133">1A : Partner Review (パートナーのレビュー)</span><span class="sxs-lookup"><span data-stu-id="16989-133">1A: Partner Review</span></span><br /><br /> <span data-ttu-id="16989-134">1B : Product & Service Review (製品とサービスのレビュー)</span><span class="sxs-lookup"><span data-stu-id="16989-134">1B: Product & Service Review</span></span>|  
|<span data-ttu-id="16989-135">2: 製品情報</span><span class="sxs-lookup"><span data-stu-id="16989-135">2: Product Information</span></span>|<span data-ttu-id="16989-136">2A : Preparation for Distribution (配信の準備)</span><span class="sxs-lookup"><span data-stu-id="16989-136">2A: Preparation for Distribution</span></span><br /><br /> <span data-ttu-id="16989-137">2B : Product Change Notification (製品変更通知)</span><span class="sxs-lookup"><span data-stu-id="16989-137">2B: Product Change Notification</span></span><br /><br /> <span data-ttu-id="16989-138">2C : Product Design Information (製品設計情報)</span><span class="sxs-lookup"><span data-stu-id="16989-138">2C: Product Design Information</span></span><br /><br /> <span data-ttu-id="16989-139">2D : Collaborative Design & Engineering (共同の設計とエンジニアリング)</span><span class="sxs-lookup"><span data-stu-id="16989-139">2D: Collaborative Design & Engineering</span></span>|  
|<span data-ttu-id="16989-140">3: 注文管理</span><span class="sxs-lookup"><span data-stu-id="16989-140">3: Order Management</span></span>|<span data-ttu-id="16989-141">3A : Quote & Order Entry (見積もりと注文の入力)</span><span class="sxs-lookup"><span data-stu-id="16989-141">3A: Quote & Order Entry</span></span><br /><br /> <span data-ttu-id="16989-142">3B : Transportation & Distribution (配送と配信)</span><span class="sxs-lookup"><span data-stu-id="16989-142">3B: Transportation & Distribution</span></span><br /><br /> <span data-ttu-id="16989-143">3C : Returns & Finance (返品と財務管理)</span><span class="sxs-lookup"><span data-stu-id="16989-143">3C: Returns & Finance</span></span><br /><br /> <span data-ttu-id="16989-144">3D : Product Configuration (製品の構成)</span><span class="sxs-lookup"><span data-stu-id="16989-144">3D: Product Configuration</span></span>|  
|<span data-ttu-id="16989-145">4: 在庫管理</span><span class="sxs-lookup"><span data-stu-id="16989-145">4: Inventory Management</span></span>|<span data-ttu-id="16989-146">4A : Collaborative Forecasting (協働的需要予測)</span><span class="sxs-lookup"><span data-stu-id="16989-146">4A: Collaborative Forecasting</span></span><br /><br /> <span data-ttu-id="16989-147">4B : Inventory Allocation (在庫の割り当て)</span><span class="sxs-lookup"><span data-stu-id="16989-147">4B: Inventory Allocation</span></span><br /><br /> <span data-ttu-id="16989-148">4C : Inventory Reporting (在庫のレポート)</span><span class="sxs-lookup"><span data-stu-id="16989-148">4C: Inventory Reporting</span></span><br /><br /> <span data-ttu-id="16989-149">4D : Inventory Replenishment (在庫の補充)</span><span class="sxs-lookup"><span data-stu-id="16989-149">4D: Inventory Replenishment</span></span><br /><br /> <span data-ttu-id="16989-150">4E : Sales Reporting (売上レポート)</span><span class="sxs-lookup"><span data-stu-id="16989-150">4E: Sales Reporting</span></span><br /><br /> <span data-ttu-id="16989-151">4F : Price Protection (価格の保護)</span><span class="sxs-lookup"><span data-stu-id="16989-151">4F: Price Protection</span></span>|  
|<span data-ttu-id="16989-152">5: マーケティング情報の管理</span><span class="sxs-lookup"><span data-stu-id="16989-152">5: Marketing Information Management</span></span>|<span data-ttu-id="16989-153">5A : Lead Opportunity Management (見込み顧客管理)</span><span class="sxs-lookup"><span data-stu-id="16989-153">5A: Lead Opportunity Management</span></span><br /><br /> <span data-ttu-id="16989-154">5B : Marketing Campaign Management (マーケティング キャンペーン管理)</span><span class="sxs-lookup"><span data-stu-id="16989-154">5B: Marketing Campaign Management</span></span>|  
|<span data-ttu-id="16989-155">6: サービスとサポート</span><span class="sxs-lookup"><span data-stu-id="16989-155">6: Service and Support</span></span>|<span data-ttu-id="16989-156">6A : Provide and Administer Warranties, Service Packages, and Contract Services (保証、サービス パッケージ、および契約サービスの提供と管理)</span><span class="sxs-lookup"><span data-stu-id="16989-156">6A: Provide and Administer Warranties, Service Packages, and Contract Services</span></span><br /><br /> <span data-ttu-id="16989-157">6B : Provide and Administer Asset Management (資産管理の提供と管理) (6A に統合）</span><span class="sxs-lookup"><span data-stu-id="16989-157">6B: Provide and Administer Asset Management (Merged with 6A)</span></span><br /><br /> <span data-ttu-id="16989-158">6C : Technical Support and Service Management (技術サポートとサービスの管理)</span><span class="sxs-lookup"><span data-stu-id="16989-158">6C: Technical Support and Service Management</span></span>|  
|<span data-ttu-id="16989-159">7: 製造</span><span class="sxs-lookup"><span data-stu-id="16989-159">7: Manufacturing</span></span>|<span data-ttu-id="16989-160">7A : Design Transfer (デザインの転送)</span><span class="sxs-lookup"><span data-stu-id="16989-160">7A: Design Transfer</span></span><br /><br /> <span data-ttu-id="16989-161">7B : Manage Manufacturing WO & WIP (製造する WO と WIP の管理)</span><span class="sxs-lookup"><span data-stu-id="16989-161">7B: Manage Manufacturing WO & WIP</span></span><br /><br /> <span data-ttu-id="16989-162">7C : Distribute Manufacturing Information (製造情報の配布)</span><span class="sxs-lookup"><span data-stu-id="16989-162">7C: Distribute Manufacturing Information</span></span>|  
  
 <span data-ttu-id="16989-163">各セグメントには、特定のメッセージ PIP 番号が含まれています。</span><span class="sxs-lookup"><span data-stu-id="16989-163">Each segment includes a number of specific message PIPs.</span></span> <span data-ttu-id="16989-164">たとえば 3A4 PIP は、注文管理クラスター (クラスター 3)、および見積もりと注文エントリ セグメント (セグメント A のクラスター 3) の一部です。</span><span class="sxs-lookup"><span data-stu-id="16989-164">For example, the 3A4 PIP is a part of the Order Management cluster (Cluster 3) and the Quote and Order Entry segment (Segment A of Cluster 3).</span></span> <span data-ttu-id="16989-165">このセグメントには、次に示す他の関連メッセージ PIP が含まれます。</span><span class="sxs-lookup"><span data-stu-id="16989-165">This segment includes other related message PIPs, as follows:</span></span>  
  
 <span data-ttu-id="16989-166">クラスタ 3 : Order Management (注文の管理)</span><span class="sxs-lookup"><span data-stu-id="16989-166">Cluster 3: Order Management</span></span>  
  
-   <span data-ttu-id="16989-167">セグメント A : Quote and Order Entry (見積もりと注文の入力)</span><span class="sxs-lookup"><span data-stu-id="16989-167">Segment A: Quote and Order Entry</span></span>  
  
    -   <span data-ttu-id="16989-168">PIP 3A1 : Request Quote (見積もりの要求)</span><span class="sxs-lookup"><span data-stu-id="16989-168">PIP 3A1: Request Quote</span></span>  
  
    -   <span data-ttu-id="16989-169">PIP 3A2 : Request Price and Availability (価格とアベイラビリティの要求)</span><span class="sxs-lookup"><span data-stu-id="16989-169">PIP 3A2: Request Price and Availability</span></span>  
  
    -   <span data-ttu-id="16989-170">PIP 3A3 : Request Shopping Cart Transfer (ショッピング カーと転送の要求)</span><span class="sxs-lookup"><span data-stu-id="16989-170">PIP 3A3: Request Shopping Cart Transfer</span></span>  
  
    -   <span data-ttu-id="16989-171">PIP 3A4 : Manage Purchase Order (発注の要求)</span><span class="sxs-lookup"><span data-stu-id="16989-171">PIP 3A4: Manage Purchase Order</span></span>  
  
    -   <span data-ttu-id="16989-172">PIP 3A5 : Query Order Status (注文状態の照会)</span><span class="sxs-lookup"><span data-stu-id="16989-172">PIP 3A5: Query Order Status</span></span>  
  
    -   <span data-ttu-id="16989-173">PIP 3A6 : Distribute Order Status (注文状態の配信)</span><span class="sxs-lookup"><span data-stu-id="16989-173">PIP 3A6: Distribute Order Status</span></span>  
  
    -   <span data-ttu-id="16989-174">…</span><span class="sxs-lookup"><span data-stu-id="16989-174">…</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16989-175">参照</span><span class="sxs-lookup"><span data-stu-id="16989-175">See Also</span></span>  
 <span data-ttu-id="16989-176">[RosettaNet および CIDX メッセージ規格](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span><span class="sxs-lookup"><span data-stu-id="16989-176">[RosettaNet and CIDX Messaging Standards](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span></span>  
 [<span data-ttu-id="16989-177">RNIF 規格</span><span class="sxs-lookup"><span data-stu-id="16989-177">RNIF Standard</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)