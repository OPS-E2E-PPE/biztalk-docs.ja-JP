---
title: "PIP 仕様を使用して、プロセス構成を作成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PIPs, PIP settings
- PIPs, PIP secifications
- process configuration, PIPs
- PIPs, process configuration
ms.assetid: 64f0f5fb-f880-4ef1-95d7-2575b8d0bcff
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 777f32e5a9e035f6009f5450eb48ae8286159f05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-pip-specification-to-create-a-process-configuration"></a><span data-ttu-id="21ce9-102">PIP 仕様を使用して、プロセス構成を作成するには</span><span class="sxs-lookup"><span data-stu-id="21ce9-102">Using the PIP Specification to Create a Process Configuration</span></span>
<span data-ttu-id="21ce9-103">ダウンロードした後、プロセス PIP (Partner Interface)、RosettaNet 組織 (RosettaNet.org) から、ダウンロード パッケージには、PIP 仕様ドキュメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="21ce9-103">After you download a Partner Interface Process (PIP) from the RosettaNet organization (from RosettaNet.org), the download package includes a PIP specification document.</span></span> <span data-ttu-id="21ce9-104">このドキュメントには、[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] 管理コンソールでプロセス構成を作成する場合に使用する設定についてのガイダンスが記載されています。</span><span class="sxs-lookup"><span data-stu-id="21ce9-104">This document contains guidance on what settings to use when you create a process configuration in the [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console.</span></span>  
  
## <a name="how-pip-settings-map-to-the-pip-specification"></a><span data-ttu-id="21ce9-105">PIP 設定と PIP 仕様の対応関係</span><span class="sxs-lookup"><span data-stu-id="21ce9-105">How PIP Settings Map to the PIP Specification</span></span>  
 <span data-ttu-id="21ce9-106">次の表に、PIP 設定と RosettaNet PIP 仕様の情報の対応関係を示します。</span><span class="sxs-lookup"><span data-stu-id="21ce9-106">The following table describes how PIP settings map to information in the RosettaNet PIP specification.</span></span>  
  
|<span data-ttu-id="21ce9-107">プロセス構成設定</span><span class="sxs-lookup"><span data-stu-id="21ce9-107">Process Configuration setting</span></span>|<span data-ttu-id="21ce9-108">PIP 仕様の情報</span><span class="sxs-lookup"><span data-stu-id="21ce9-108">Information in the PIP specification</span></span>|  
|-----------------------------------|------------------------------------------|  
|<span data-ttu-id="21ce9-109">[プロセス コード]</span><span class="sxs-lookup"><span data-stu-id="21ce9-109">Process Code</span></span>|<span data-ttu-id="21ce9-110">たとえば「PIP3A4」など、タイトル ページの小見出し</span><span class="sxs-lookup"><span data-stu-id="21ce9-110">Subheading on the title page, for example, "PIP3A4"</span></span>|  
|<span data-ttu-id="21ce9-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="21ce9-111">Version</span></span>|<span data-ttu-id="21ce9-112">たとえば「02.02.00」など、タイトル ページの PIP バージョン識別子の小見出し</span><span class="sxs-lookup"><span data-stu-id="21ce9-112">PIP Version Identifier subheading on the title page, for example, "02.02.00"</span></span>|  
|<span data-ttu-id="21ce9-113">[処理名]</span><span class="sxs-lookup"><span data-stu-id="21ce9-113">Process name</span></span>|<span data-ttu-id="21ce9-114">たとえば「発注要求」など、タイトル ページの小見出し</span><span class="sxs-lookup"><span data-stu-id="21ce9-114">Subheading on the title page, for example, "Request Purchase Order"</span></span>|  
|<span data-ttu-id="21ce9-115">[説明] ([全般] タブ)</span><span class="sxs-lookup"><span data-stu-id="21ce9-115">Description (General tab)</span></span>|<span data-ttu-id="21ce9-116">セクション 3.1、ビジネス プロセス定義</span><span class="sxs-lookup"><span data-stu-id="21ce9-116">Section 3.1, Business Process Definition</span></span>|  
|<span data-ttu-id="21ce9-117">[否認不可の必要性]</span><span class="sxs-lookup"><span data-stu-id="21ce9-117">Non-Repudiation Required</span></span>|<span data-ttu-id="21ce9-118">表 3-3: ビジネス アクティビティ パフォーマンス コントロール</span><span class="sxs-lookup"><span data-stu-id="21ce9-118">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="21ce9-119">時間 (秒) を確認するには</span><span class="sxs-lookup"><span data-stu-id="21ce9-119">Time to Acknowledge (Seconds)</span></span>|<span data-ttu-id="21ce9-120">表 3-3: ビジネス アクティビティ パフォーマンス コントロール</span><span class="sxs-lookup"><span data-stu-id="21ce9-120">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="21ce9-121">[認証の必要性]</span><span class="sxs-lookup"><span data-stu-id="21ce9-121">Is Authorization Required?</span></span>|<span data-ttu-id="21ce9-122">表 3-3: ビジネス アクティビティ パフォーマンス コントロール</span><span class="sxs-lookup"><span data-stu-id="21ce9-122">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="21ce9-123">[永続的な機密性の必要性]</span><span class="sxs-lookup"><span data-stu-id="21ce9-123">Is Persistent Confidentiality Required</span></span>|<span data-ttu-id="21ce9-124">(PIP 仕様からの参照なし)</span><span class="sxs-lookup"><span data-stu-id="21ce9-124">(No reference from the PIP specification)</span></span>|  
|<span data-ttu-id="21ce9-125">[セキュリティで保護されたトランスポートの必要性]</span><span class="sxs-lookup"><span data-stu-id="21ce9-125">Is Secure Transport Required?</span></span>|<span data-ttu-id="21ce9-126">表 4-3: メッセージ交換コントロール</span><span class="sxs-lookup"><span data-stu-id="21ce9-126">Table 4-3: Message Exchange Controls</span></span>|  
|<span data-ttu-id="21ce9-127">[シングル アクション]</span><span class="sxs-lookup"><span data-stu-id="21ce9-127">Is Single Action</span></span>|<span data-ttu-id="21ce9-128">セクション 4.3、取り引きダイアログ仕様</span><span class="sxs-lookup"><span data-stu-id="21ce9-128">Section 4.3, Business Transaction Dialog Specification</span></span>|  
|<span data-ttu-id="21ce9-129">[発信元とコンテンツの否認不可]</span><span class="sxs-lookup"><span data-stu-id="21ce9-129">Non-Repudiation of Origin and Content</span></span>|<span data-ttu-id="21ce9-130">表 3-3: ビジネス アクティビティ パフォーマンス コントロール</span><span class="sxs-lookup"><span data-stu-id="21ce9-130">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="21ce9-131">再試行の回数</span><span class="sxs-lookup"><span data-stu-id="21ce9-131">Retry Count</span></span>|<span data-ttu-id="21ce9-132">表 3-3: ビジネス アクティビティ パフォーマンス コントロール</span><span class="sxs-lookup"><span data-stu-id="21ce9-132">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="21ce9-133">[実行までの時間]</span><span class="sxs-lookup"><span data-stu-id="21ce9-133">Time to Perform</span></span>|<span data-ttu-id="21ce9-134">表 3-3: ビジネス アクティビティ パフォーマンス コントロール</span><span class="sxs-lookup"><span data-stu-id="21ce9-134">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="21ce9-135">名前</span><span class="sxs-lookup"><span data-stu-id="21ce9-135">Name</span></span>|<span data-ttu-id="21ce9-136">表 3-3: ビジネス アクティビティ パフォーマンス コントロール (アクティビティ名)</span><span class="sxs-lookup"><span data-stu-id="21ce9-136">Table 3-3: Business Activity Performance Controls (Activity Name)</span></span>|  
|<span data-ttu-id="21ce9-137">型</span><span class="sxs-lookup"><span data-stu-id="21ce9-137">Type</span></span>|<span data-ttu-id="21ce9-138">(PIP 仕様からの参照なし - 将来使用予定)</span><span class="sxs-lookup"><span data-stu-id="21ce9-138">(No reference from the PIP specification - for future use)</span></span>|  
|<span data-ttu-id="21ce9-139">[説明] ([開始側] タブと [応答側] タブ)</span><span class="sxs-lookup"><span data-stu-id="21ce9-139">Description (Initiator and Response tabs)</span></span>|<span data-ttu-id="21ce9-140">表 3-4: PIP ビジネス ドキュメント</span><span class="sxs-lookup"><span data-stu-id="21ce9-140">Table 3-4: PIP Business Documents</span></span>|  
|<span data-ttu-id="21ce9-141">[名前] ([開始側] タブと [応答側] タブ)</span><span class="sxs-lookup"><span data-stu-id="21ce9-141">Name (Initiator and Response tabs)</span></span>|<span data-ttu-id="21ce9-142">表 3-4: PIP ビジネス ドキュメント</span><span class="sxs-lookup"><span data-stu-id="21ce9-142">Table 3-4: PIP Business Documents</span></span>|  
|<span data-ttu-id="21ce9-143">[ロール] ([開始側] タブと [応答側] タブ)</span><span class="sxs-lookup"><span data-stu-id="21ce9-143">Role (Initiator and Response tabs)</span></span>|<span data-ttu-id="21ce9-144">表 3-1: パートナーのロールの説明</span><span class="sxs-lookup"><span data-stu-id="21ce9-144">Table 3-1: Partner Role Descriptions</span></span>|  
|<span data-ttu-id="21ce9-145">[ロールの説明] ([開始側] タブと [応答側] タブ)</span><span class="sxs-lookup"><span data-stu-id="21ce9-145">Role Description (Initiator and Response tabs)</span></span>|<span data-ttu-id="21ce9-146">表 3-1: パートナーのロールの説明</span><span class="sxs-lookup"><span data-stu-id="21ce9-146">Table 3-1: Partner Role Descriptions</span></span>|  
|<span data-ttu-id="21ce9-147">[ロールの種類] ([開始側] タブと [応答側] タブ)</span><span class="sxs-lookup"><span data-stu-id="21ce9-147">Role Type (Initiator and Response tabs)</span></span>|<span data-ttu-id="21ce9-148">表 3-1: パートナーのロールの説明</span><span class="sxs-lookup"><span data-stu-id="21ce9-148">Table 3-1: Partner Role Descriptions</span></span>|  
|<span data-ttu-id="21ce9-149">サービス</span><span class="sxs-lookup"><span data-stu-id="21ce9-149">Service</span></span>|<span data-ttu-id="21ce9-150">表 4-1: ネットワーク コンポーネントの仕様</span><span class="sxs-lookup"><span data-stu-id="21ce9-150">Table 4-1: Network Component Specification</span></span>|  
|<span data-ttu-id="21ce9-151">[サービスの分類]</span><span class="sxs-lookup"><span data-stu-id="21ce9-151">Service Classification</span></span>|<span data-ttu-id="21ce9-152">表 4-1: ネットワーク コンポーネントの仕様</span><span class="sxs-lookup"><span data-stu-id="21ce9-152">Table 4-1: Network Component Specification</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21ce9-153">参照</span><span class="sxs-lookup"><span data-stu-id="21ce9-153">See Also</span></span>  
 [<span data-ttu-id="21ce9-154">作成またはプロセス構成を編集する方法</span><span class="sxs-lookup"><span data-stu-id="21ce9-154">How to Create or Edit a Process Configuration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)