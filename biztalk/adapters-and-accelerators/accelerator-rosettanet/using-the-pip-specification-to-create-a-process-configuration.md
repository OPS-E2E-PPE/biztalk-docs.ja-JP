---
title: PIP 仕様を使用して、プロセス構成を作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PIPs, PIP settings
- PIPs, PIP secifications
- process configuration, PIPs
- PIPs, process configuration
ms.assetid: 64f0f5fb-f880-4ef1-95d7-2575b8d0bcff
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21933797f37b32a4131c57181829f2380bafe061
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299920"
---
# <a name="using-the-pip-specification-to-create-a-process-configuration"></a><span data-ttu-id="071c6-102">PIP 仕様を使用して、プロセス構成を作成するには</span><span class="sxs-lookup"><span data-stu-id="071c6-102">Using the PIP Specification to Create a Process Configuration</span></span>
<span data-ttu-id="071c6-103">RosettaNet 組織 (RosettaNet.org) から、プロセス PIP (Partner Interface) をダウンロードした後、ダウンロード パッケージには、PIP 仕様のドキュメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="071c6-103">After you download a Partner Interface Process (PIP) from the RosettaNet organization (from RosettaNet.org), the download package includes a PIP specification document.</span></span> <span data-ttu-id="071c6-104">このドキュメントにはでプロセス構成を作成するときに使用するには、どのような設定に関するガイダンスが含まれています、[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="071c6-104">This document contains guidance on what settings to use when you create a process configuration in the [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console.</span></span>  
  
## <a name="how-pip-settings-map-to-the-pip-specification"></a><span data-ttu-id="071c6-105">PIP の PIP 仕様にマップを設定する方法</span><span class="sxs-lookup"><span data-stu-id="071c6-105">How PIP Settings Map to the PIP Specification</span></span>  
 <span data-ttu-id="071c6-106">次の表では、PIP 設定が RosettaNet PIP 仕様の情報にマップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="071c6-106">The following table describes how PIP settings map to information in the RosettaNet PIP specification.</span></span>  
  
|<span data-ttu-id="071c6-107">プロセス構成設定</span><span class="sxs-lookup"><span data-stu-id="071c6-107">Process Configuration setting</span></span>|<span data-ttu-id="071c6-108">PIP 仕様の情報</span><span class="sxs-lookup"><span data-stu-id="071c6-108">Information in the PIP specification</span></span>|  
|-----------------------------------|------------------------------------------|  
|<span data-ttu-id="071c6-109">プロセス コード</span><span class="sxs-lookup"><span data-stu-id="071c6-109">Process Code</span></span>|<span data-ttu-id="071c6-110">たとえば、「pip3a4」など、タイトル ページの小見出し</span><span class="sxs-lookup"><span data-stu-id="071c6-110">Subheading on the title page, for example, "PIP3A4"</span></span>|  
|<span data-ttu-id="071c6-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="071c6-111">Version</span></span>|<span data-ttu-id="071c6-112">[タイトル] ページで、たとえば「02.02.00」などの PIP バージョン識別子の小見出し</span><span class="sxs-lookup"><span data-stu-id="071c6-112">PIP Version Identifier subheading on the title page, for example, "02.02.00"</span></span>|  
|<span data-ttu-id="071c6-113">[処理名]</span><span class="sxs-lookup"><span data-stu-id="071c6-113">Process name</span></span>|<span data-ttu-id="071c6-114">たとえば、発注要求"、タイトル ページの小見出し</span><span class="sxs-lookup"><span data-stu-id="071c6-114">Subheading on the title page, for example, "Request Purchase Order"</span></span>|  
|<span data-ttu-id="071c6-115">[説明] \([全般] タブ)</span><span class="sxs-lookup"><span data-stu-id="071c6-115">Description (General tab)</span></span>|<span data-ttu-id="071c6-116">セクション 3.1、ビジネス プロセスの定義</span><span class="sxs-lookup"><span data-stu-id="071c6-116">Section 3.1, Business Process Definition</span></span>|  
|<span data-ttu-id="071c6-117">否認不可が必要</span><span class="sxs-lookup"><span data-stu-id="071c6-117">Non-Repudiation Required</span></span>|<span data-ttu-id="071c6-118">表 3-3:ビジネス アクティビティ パフォーマンス コントロール</span><span class="sxs-lookup"><span data-stu-id="071c6-118">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="071c6-119">時間 (秒) を確認するには</span><span class="sxs-lookup"><span data-stu-id="071c6-119">Time to Acknowledge (Seconds)</span></span>|<span data-ttu-id="071c6-120">表 3-3:ビジネス アクティビティ パフォーマンス コントロール</span><span class="sxs-lookup"><span data-stu-id="071c6-120">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="071c6-121">承認が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="071c6-121">Is Authorization Required?</span></span>|<span data-ttu-id="071c6-122">表 3-3:ビジネス アクティビティ パフォーマンス コントロール</span><span class="sxs-lookup"><span data-stu-id="071c6-122">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="071c6-123">永続的な機密性の必要性は、します。</span><span class="sxs-lookup"><span data-stu-id="071c6-123">Is Persistent Confidentiality Required</span></span>|<span data-ttu-id="071c6-124">(PIP 仕様から参照なし)</span><span class="sxs-lookup"><span data-stu-id="071c6-124">(No reference from the PIP specification)</span></span>|  
|<span data-ttu-id="071c6-125">セキュリティで保護されたトランスポートのために必要なのですか。</span><span class="sxs-lookup"><span data-stu-id="071c6-125">Is Secure Transport Required?</span></span>|<span data-ttu-id="071c6-126">表 4-3:メッセージ交換コントロール</span><span class="sxs-lookup"><span data-stu-id="071c6-126">Table 4-3: Message Exchange Controls</span></span>|  
|<span data-ttu-id="071c6-127">シングル アクションします。</span><span class="sxs-lookup"><span data-stu-id="071c6-127">Is Single Action</span></span>|<span data-ttu-id="071c6-128">セクション 4.3、取り引きダイアログ仕様</span><span class="sxs-lookup"><span data-stu-id="071c6-128">Section 4.3, Business Transaction Dialog Specification</span></span>|  
|<span data-ttu-id="071c6-129">[発信元とコンテンツの否認不可]</span><span class="sxs-lookup"><span data-stu-id="071c6-129">Non-Repudiation of Origin and Content</span></span>|<span data-ttu-id="071c6-130">表 3-3:ビジネス アクティビティ パフォーマンス コントロール</span><span class="sxs-lookup"><span data-stu-id="071c6-130">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="071c6-131">再試行の回数</span><span class="sxs-lookup"><span data-stu-id="071c6-131">Retry Count</span></span>|<span data-ttu-id="071c6-132">表 3-3:ビジネス アクティビティ パフォーマンス コントロール</span><span class="sxs-lookup"><span data-stu-id="071c6-132">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="071c6-133">実行する時間</span><span class="sxs-lookup"><span data-stu-id="071c6-133">Time to Perform</span></span>|<span data-ttu-id="071c6-134">表 3-3:ビジネス アクティビティ パフォーマンス コントロール</span><span class="sxs-lookup"><span data-stu-id="071c6-134">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="071c6-135">名前</span><span class="sxs-lookup"><span data-stu-id="071c6-135">Name</span></span>|<span data-ttu-id="071c6-136">表 3-3:ビジネス アクティビティ パフォーマンス コントロール (アクティビティ名)</span><span class="sxs-lookup"><span data-stu-id="071c6-136">Table 3-3: Business Activity Performance Controls (Activity Name)</span></span>|  
|<span data-ttu-id="071c6-137">型</span><span class="sxs-lookup"><span data-stu-id="071c6-137">Type</span></span>|<span data-ttu-id="071c6-138">(将来使用するために、PIP 仕様から参照なし)</span><span class="sxs-lookup"><span data-stu-id="071c6-138">(No reference from the PIP specification - for future use)</span></span>|  
|<span data-ttu-id="071c6-139">[説明] \([開始側] タブと [応答側] タブ)</span><span class="sxs-lookup"><span data-stu-id="071c6-139">Description (Initiator and Response tabs)</span></span>|<span data-ttu-id="071c6-140">表 3-4:PIP ビジネス ドキュメント</span><span class="sxs-lookup"><span data-stu-id="071c6-140">Table 3-4: PIP Business Documents</span></span>|  
|<span data-ttu-id="071c6-141">[名前] \([開始側] タブと [応答側] タブ)</span><span class="sxs-lookup"><span data-stu-id="071c6-141">Name (Initiator and Response tabs)</span></span>|<span data-ttu-id="071c6-142">表 3-4:PIP ビジネス ドキュメント</span><span class="sxs-lookup"><span data-stu-id="071c6-142">Table 3-4: PIP Business Documents</span></span>|  
|<span data-ttu-id="071c6-143">[ロール] \([開始側] タブと [応答側] タブ)</span><span class="sxs-lookup"><span data-stu-id="071c6-143">Role (Initiator and Response tabs)</span></span>|<span data-ttu-id="071c6-144">表 3-1:パートナーのロールの説明</span><span class="sxs-lookup"><span data-stu-id="071c6-144">Table 3-1: Partner Role Descriptions</span></span>|  
|<span data-ttu-id="071c6-145">[ロールの説明] \([開始側] タブと [応答側] タブ)</span><span class="sxs-lookup"><span data-stu-id="071c6-145">Role Description (Initiator and Response tabs)</span></span>|<span data-ttu-id="071c6-146">表 3-1:パートナーのロールの説明</span><span class="sxs-lookup"><span data-stu-id="071c6-146">Table 3-1: Partner Role Descriptions</span></span>|  
|<span data-ttu-id="071c6-147">[ロールの種類] \([開始側] タブと [応答側] タブ)</span><span class="sxs-lookup"><span data-stu-id="071c6-147">Role Type (Initiator and Response tabs)</span></span>|<span data-ttu-id="071c6-148">表 3-1:パートナーのロールの説明</span><span class="sxs-lookup"><span data-stu-id="071c6-148">Table 3-1: Partner Role Descriptions</span></span>|  
|<span data-ttu-id="071c6-149">サービス</span><span class="sxs-lookup"><span data-stu-id="071c6-149">Service</span></span>|<span data-ttu-id="071c6-150">表 4-1:ネットワーク コンポーネントの仕様</span><span class="sxs-lookup"><span data-stu-id="071c6-150">Table 4-1: Network Component Specification</span></span>|  
|<span data-ttu-id="071c6-151">サービスの分類</span><span class="sxs-lookup"><span data-stu-id="071c6-151">Service Classification</span></span>|<span data-ttu-id="071c6-152">表 4-1:ネットワーク コンポーネントの仕様</span><span class="sxs-lookup"><span data-stu-id="071c6-152">Table 4-1: Network Component Specification</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="071c6-153">参照</span><span class="sxs-lookup"><span data-stu-id="071c6-153">See Also</span></span>  
 [<span data-ttu-id="071c6-154">プロセス構成を作成または編集する方法</span><span class="sxs-lookup"><span data-stu-id="071c6-154">How to Create or Edit a Process Configuration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)